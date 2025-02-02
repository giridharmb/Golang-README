## Saga Pattern

#### The Saga Pattern is used to manage distributed transactions and long-running business processes across multiple services or components that cannot rely on a single ACID transaction. In a microservices architecture, where each service has its own database, a traditional two-phase commit can be too rigid or impractical. Instead, a saga coordinates a series of local transactions—each committed independently—while ensuring that if one step fails, previous actions can be “compensated” (i.e., undone) to maintain overall data consistency.

Why Use the Saga Pattern?

 - Distributed Transaction Management:

It provides a way to maintain consistency across services that each have their own database without the heavy overhead of distributed transactions.

 - Resilience and Flexibility:

By isolating business actions into individual steps with compensating actions, a saga allows your system to recover gracefully from failures.

 - Scalability:

Since each local transaction is managed independently, systems can scale better compared to a single, distributed ACID transaction that spans multiple services.

 - Eventual Consistency:

Instead of enforcing strong consistency across the system at all times, sagas embrace eventual consistency, which is often a more practical approach for modern, distributed architectures.

---

Below is an example of how you might implement a simple Saga pattern in Go using PostgreSQL with GORM. In this example, we simulate a money transfer between two accounts with two local transactions (steps):

 1. Debit Account 1
 2. Credit Account 2

Each step includes an action (the local transaction) and a compensation function (to roll back the change if a subsequent step fails). In a real-world system, your saga might span multiple services and use an orchestrator or event-driven approach. Here we keep things simple with synchronous steps and compensation executed in reverse order if one step fails.

- Note:

This example assumes that you have a running PostgreSQL database and the proper DSN string. You should replace "host=localhost user=youruser password=yourpassword dbname=yourdb port=5432 sslmode=disable" with your actual connection details. Also, error handling, logging, and production concerns (like retries or timeouts) may need additional attention in a real implementation.

---

```go
package main

import (
	"fmt"
	"log"

	"gorm.io/driver/postgres"
	"gorm.io/gorm"
)

// Account represents a simple bank account.
type Account struct {
	ID      int64   `gorm:"primaryKey"`
	Balance float64
}

// SagaStep defines a step in the saga, including the action and its compensation.
type SagaStep struct {
	Name         string
	Action       func(tx *gorm.DB) error
	Compensation func(tx *gorm.DB) error
}

// Saga coordinates the execution of steps.
type Saga struct {
	DB    *gorm.DB
	Steps []SagaStep
}

// Execute runs each step in sequence. If any step fails, it executes
// compensation functions for previously successful steps in reverse order.
func (s *Saga) Execute() error {
	completedSteps := []SagaStep{}

	for _, step := range s.Steps {
		// Execute each action within its own transaction.
		err := s.DB.Transaction(func(tx *gorm.DB) error {
			log.Printf("Executing step: %s", step.Name)
			if err := step.Action(tx); err != nil {
				return err
			}
			return nil
		})

		if err != nil {
			log.Printf("Step failed: %s, error: %v", step.Name, err)
			// Execute compensations for previously completed steps in reverse order.
			for i := len(completedSteps) - 1; i >= 0; i-- {
				compStep := completedSteps[i]
				compErr := s.DB.Transaction(func(tx *gorm.DB) error {
					log.Printf("Compensating step: %s", compStep.Name)
					return compStep.Compensation(tx)
				})
				if compErr != nil {
					log.Printf("Failed to compensate step %s: %v", compStep.Name, compErr)
				}
			}
			return fmt.Errorf("saga failed on step '%s': %w", step.Name, err)
		}
		// Add the successful step to the list.
		completedSteps = append(completedSteps, step)
	}
	return nil
}

func main() {
	// Replace with your PostgreSQL DSN.
	dsn := "host=localhost user=youruser password=yourpassword dbname=yourdb port=5432 sslmode=disable"
	db, err := gorm.Open(postgres.Open(dsn), &gorm.Config{})
	if err != nil {
		log.Fatalf("failed to connect database: %v", err)
	}

	// Auto-migrate the Account model.
	if err := db.AutoMigrate(&Account{}); err != nil {
		log.Fatalf("failed to migrate database: %v", err)
	}

	// Example account IDs and transfer amount.
	account1ID := int64(1)
	account2ID := int64(2)
	transferAmount := 100.0

	// Setup the saga with two steps.
	saga := Saga{
		DB: db,
		Steps: []SagaStep{
			{
				Name: "Debit Account 1",
				Action: func(tx *gorm.DB) error {
					var account Account
					if err := tx.First(&account, account1ID).Error; err != nil {
						return err
					}
					if account.Balance < transferAmount {
						return fmt.Errorf("insufficient funds in account %d", account1ID)
					}
					account.Balance -= transferAmount
					return tx.Save(&account).Error
				},
				Compensation: func(tx *gorm.DB) error {
					// Refund the debit if subsequent steps fail.
					var account Account
					if err := tx.First(&account, account1ID).Error; err != nil {
						return err
					}
					account.Balance += transferAmount
					return tx.Save(&account).Error
				},
			},
			{
				Name: "Credit Account 2",
				Action: func(tx *gorm.DB) error {
					var account Account
					if err := tx.First(&account, account2ID).Error; err != nil {
						return err
					}
					account.Balance += transferAmount
					return tx.Save(&account).Error
				},
				Compensation: func(tx *gorm.DB) error {
					// Revert the credit if needed.
					var account Account
					if err := tx.First(&account, account2ID).Error; err != nil {
						return err
					}
					account.Balance -= transferAmount
					return tx.Save(&account).Error
				},
			},
		},
	}

	// Execute the saga.
	if err := saga.Execute(); err != nil {
		log.Printf("Saga execution failed: %v", err)
	} else {
		log.Println("Saga executed successfully")
	}
}
```

Explanation

1. Model Definition:

The Account struct represents a bank account with an ID and a Balance.

2. SagaStep & Saga:
 - Each SagaStep holds:
 - Name: A human-readable name for logging.
 - Action: The function to execute the local transaction.
 - Compensation: The function to undo the action if needed.
 - The Saga struct holds a slice of steps and a reference to the GORM DB connection.

3. Execution Flow:

The Execute method iterates over the steps, executing each within its own GORM transaction. If a step fails, it iterates over the previously completed steps (in reverse order) and executes their compensation actions. This mimics the rollback behavior in a distributed saga pattern.
	
4. Main Function:

 - Sets up the database connection.
 - Auto-migrates the Account model.
 - Creates a saga for a money transfer between two accounts.
 - Executes the saga and logs the result.

This example demonstrates the core idea behind the saga pattern—using compensating transactions to maintain consistency when a multi-step process fails midway. In real distributed systems, you may coordinate saga steps across microservices, possibly using messaging queues or a dedicated saga orchestrator.

---

#### Another Example: Order Processing Saga

Below is an example in Go using GORM with PostgreSQL to simulate an Order Processing Saga. In this scenario, we simulate a two-step process:

1. Reserve Inventory:

Deduct a certain quantity from a product’s stock if there’s enough inventory available.

2. Charge Payment:

Process the payment for the order. (In this example, we simulate a payment failure to demonstrate the compensation.)

If the payment step fails, the saga will execute the compensation action for the inventory reservation (i.e., it will restore the product stock).

- Note:

Replace the PostgreSQL DSN with your actual connection string, and consider adding robust error handling and logging as needed.

---

```go
package main

import (
	"errors"
	"fmt"
	"log"

	"gorm.io/driver/postgres"
	"gorm.io/gorm"
)

// Product represents a simple product with stock.
type Product struct {
	ID    int64  `gorm:"primaryKey"`
	Name  string
	Stock int
}

// Payment simulates a payment record.
type Payment struct {
	ID      int64 `gorm:"primaryKey"`
	OrderID int64
	Amount  float64
	Status  string // e.g., "charged", "refunded"
}

// SagaStep defines a step in the saga, including the action and its compensation.
type SagaStep struct {
	Name         string
	Action       func(tx *gorm.DB) error
	Compensation func(tx *gorm.DB) error
}

// Saga coordinates the execution of steps.
type Saga struct {
	DB    *gorm.DB
	Steps []SagaStep
}

// Execute runs each step sequentially. If any step fails,
// it performs compensation for the previously successful steps in reverse order.
func (s *Saga) Execute() error {
	completedSteps := []SagaStep{}

	for _, step := range s.Steps {
		err := s.DB.Transaction(func(tx *gorm.DB) error {
			log.Printf("Executing step: %s", step.Name)
			return step.Action(tx)
		})
		if err != nil {
			log.Printf("Step failed: %s, error: %v", step.Name, err)
			// Execute compensations for completed steps in reverse order.
			for i := len(completedSteps) - 1; i >= 0; i-- {
				compStep := completedSteps[i]
				compErr := s.DB.Transaction(func(tx *gorm.DB) error {
					log.Printf("Compensating step: %s", compStep.Name)
					return compStep.Compensation(tx)
				})
				if compErr != nil {
					log.Printf("Failed to compensate step %s: %v", compStep.Name, compErr)
				}
			}
			return fmt.Errorf("saga failed on step '%s': %w", step.Name, err)
		}
		completedSteps = append(completedSteps, step)
	}
	return nil
}

func main() {
	// Replace with your actual PostgreSQL connection string.
	dsn := "host=localhost user=youruser password=yourpassword dbname=yourdb port=5432 sslmode=disable"
	db, err := gorm.Open(postgres.Open(dsn), &gorm.Config{})
	if err != nil {
		log.Fatalf("failed to connect to database: %v", err)
	}

	// Auto-migrate the models.
	if err := db.AutoMigrate(&Product{}, &Payment{}); err != nil {
		log.Fatalf("failed to migrate models: %v", err)
	}

	// Initialize a product with stock.
	productID := int64(1)
	initialStock := 10
	product := Product{ID: productID, Name: "Gadget", Stock: initialStock}
	// Upsert the product (insert or update on conflict).
	db.Clauses(gorm.OnConflict{UpdateAll: true}).Create(&product)

	// Order details.
	orderQuantity := 3
	paymentAmount := 299.99 // Example amount.

	// For demonstration, we simulate a payment failure.
	simulatePaymentFailure := true

	// Define the saga steps.
	saga := Saga{
		DB: db,
		Steps: []SagaStep{
			{
				Name: "Reserve Inventory",
				Action: func(tx *gorm.DB) error {
					var prod Product
					if err := tx.First(&prod, productID).Error; err != nil {
						return err
					}
					if prod.Stock < orderQuantity {
						return errors.New("insufficient stock")
					}
					prod.Stock -= orderQuantity
					return tx.Save(&prod).Error
				},
				Compensation: func(tx *gorm.DB) error {
					// Revert the inventory reservation.
					var prod Product
					if err := tx.First(&prod, productID).Error; err != nil {
						return err
					}
					prod.Stock += orderQuantity
					return tx.Save(&prod).Error
				},
			},
			{
				Name: "Charge Payment",
				Action: func(tx *gorm.DB) error {
					if simulatePaymentFailure {
						// Simulate a failure in payment processing.
						return errors.New("payment processing error")
					}
					// In a real scenario, you would integrate with a payment gateway.
					payment := Payment{OrderID: 1, Amount: paymentAmount, Status: "charged"}
					return tx.Create(&payment).Error
				},
				Compensation: func(tx *gorm.DB) error {
					// Compensation for payment: mark payment as refunded.
					var payment Payment
					if err := tx.Where("order_id = ?", 1).First(&payment).Error; err != nil {
						return err
					}
					payment.Status = "refunded"
					return tx.Save(&payment).Error
				},
			},
		},
	}

	// Execute the saga.
	if err := saga.Execute(); err != nil {
		log.Printf("Saga execution failed: %v", err)
	} else {
		log.Println("Saga executed successfully")
	}

	// For demonstration, print the final product stock.
	var finalProduct Product
	if err := db.First(&finalProduct, productID).Error; err != nil {
		log.Printf("failed to fetch product: %v", err)
	} else {
		log.Printf("Final product stock: %d", finalProduct.Stock)
	}
}
```

Explanation

1. Models:

- Product: Represents an item with available stock.
- Payment: Simulates a payment record (in a real-world application, payment processing would likely be more complex).

2. Saga Structure:

- SagaStep: Contains an Action function (the local transaction) and a Compensation function (to undo the action if necessary).
- Saga: Maintains a list of steps and a reference to the database. The Execute method runs each step in a transaction; if a step fails, it triggers compensating actions for previously completed steps in reverse order.

3. Steps in the Saga:

- Reserve Inventory:
The action checks the available stock and deducts the order quantity. The compensation reverses the stock deduction.
- Charge Payment:
The action simulates a payment process. In this example, it is deliberately set to fail (simulatePaymentFailure = true), which triggers the compensation action to “refund” the payment. (In a real-world scenario, this step would interact with an external payment gateway.)

4. Outcome:

- If any step fails, the saga ensures that the side effects of successful steps are undone (e.g., restoring inventory), thereby maintaining system consistency.

This example demonstrates another use case of the Saga pattern, showcasing how you can coordinate local transactions across multiple resources and provide compensation to ensure data consistency even in the presence of failures.