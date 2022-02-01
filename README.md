### Golang Snippets

[Check Data Type](#Check-Data-Type)

[Check If String Is JSON](#Check-If-String-Is-JSON)

[Check If String Exists In Slice](#Check-If-String-Exists-In-Slice)

[Interface-Methods](#interface-methods)

[Measure Time Taken To Execute A Function](#measure-time-taken-to-execute-a-function)

[Query Packages Modules Dependeny](#query-packages-modules-dependeny)

[Sys-Log](#sys-log)

[MongoDB Cancel With Context](#MongoDB-Cancel-With-Context)

[Client And Server WebSockets](#client-and-server-websockets)

[Read And Pretty Print JSON File](#read-and-pretty-print-json-file)

[Pretty Print JSON File](#pretty-print-json-file)

[PostgreSQL and JSON](#postgresql-and-json)

<hr/>

#### [Check Data Type](#Check-Data-Type)

How to check the type of a value in Go

```go
package main

import (
	"fmt"
)

func main() {
	a, b, c := "yes", 20.6, false
	d := []int{3, 4, 5, 6}
	e := map[string]string{
		"name":  "jake",
		"email": "jake@example.com",
	}
	fmt.Printf("type of a is %T\n", a)
	fmt.Printf("type of b is %T\n", b)
	fmt.Printf("type of c is %T\n", c)
	fmt.Printf("type of d is %T\n", d)
	fmt.Printf("type of e is %T\n", e)
}
```

Output

```
type of a is string
type of b is float64
type of c is bool
type of d is []int
type of e is map[string]string
```

#### [Check If String Is JSON](#Check-If-String-Is-JSON)

How To Check If Given String Is A Valid JSON

```go
package main

import (
	"encoding/json"
	"fmt"
)

func isJSONString(s string) bool {
	var js string
	return json.Unmarshal([]byte(s), &js) == nil

}

func isJSON(s string) bool {
	var js map[string]interface{}
	return json.Unmarshal([]byte(s), &js) == nil

}

func main() {
	var tests = []string{
		`"Platypus"`,
		`Platypus`,
		`{"id1":"1"}`,
		`{"id2":2}`,
		`{"id3":[1,2,3]}`,
		`[{"x1":"y1"}, {"x2":"y2"}]`,
		`["x3", {"x33":"y33"}]`,
	}

	for _, t := range tests {
		fmt.Printf("isJSONString(%s) = %v\n", t, isJSONString(t))
		fmt.Printf("isJSON(%s) = %v\n\n", t, isJSON(t))
	}

}
```
#### Output

```
Output:

isJSONString("Platypus") = true
isJSON("Platypus") = false

isJSONString(Platypus) = false
isJSON(Platypus) = false

isJSONString({"id1":"1"}) = false
isJSON({"id1":"1"}) = true

isJSONString({"id2":2}) = false
isJSON({"id2":2}) = true

isJSONString({"id3":[1,2,3]}) = false
isJSON({"id3":[1,2,3]}) = true

isJSONString([{"x1":"y1"}, {"x2":"y2"}]) = false
isJSON([{"x1":"y1"}, {"x2":"y2"}]) = false

isJSONString(["x3", {"x33":"y33"}]) = false
isJSON(["x3", {"x33":"y33"}]) = false

Program exited.
```

#### [Check If String Exists In Slice](#Check-If-String-Exists-In-Slice)

```go
package main

import (
	"fmt"
)

// contains checks if a string is present in
// a slice
func contains(s []string, str string) bool {
	for _, v := range s {
		if v == str {
			return true
		}
	}

	return false
}

func main() {
	s := []string{"James", "Wagner", "Christene", "Mike"}
	fmt.Println(contains(s, "James"))
	fmt.Println(contains(s, "Jack"))
}
```

#### Output

```
true
false

Program exited.
```

#### [Interface-Methods](#interface-methods)
```go
package main

import "fmt"

type User struct {
	Name     string
	Email    string
	Notifier UserNotifier
}

type UserNotifier interface {
	SendMessage(user *User, message string) error
}

type EmailNotifier struct {
}

type SmsNotifier struct {
}

func (user *User) notify(message string) error {
	return user.Notifier.SendMessage(user, message)
}

func (notifier SmsNotifier) SendMessage(user *User, message string) error {
	_, err := fmt.Printf("Sending SMS to %s with content %s\n", user.Name, message)
	return err
}

func (notifier EmailNotifier) SendMessage(user *User, message string) error {
	_, err := fmt.Printf("Sending email to %s with content %s\n", user.Name, message)
	return err
}

func main() {
	user1 := User{"Dirk", "dirk@email.com", EmailNotifier{}}
	user2 := User{"Justin", "bieber@email.com", SmsNotifier{}}

	user1.notify("Welcome Email user!")
	user2.notify("Welcome SMS user!")
}
```

```
Output:

# go run main.go

Sending email to Dirk with content Welcome Email user!
Sending SMS to Justin with content Welcome SMS user!
```

#### [Measure Time Taken To Execute A Function](#measure-time-taken-to-execute-a-function)
```go
package main

import "time"
import "fmt"

func elapsed(what string) func() {
	start := time.Now()
	return func() {
		fmt.Printf("\n%s took %v\n", what, time.Since(start))
	}
}

func doSomething() {
	defer elapsed("doSomething")()
	time.Sleep(2 * time.Second)
}

func main() {
	doSomething()
}
```

```
Output:

# go run main.go

doSomething took 2.00109075s
```

#### [Sys-Log](#sys-log)
```go
package main

import "log/syslog"
import "log"

func main() {
	syslogger, err := syslog.New(syslog.LOG_DEBUG, "go_syslog")
	if err != nil {
		log.Fatalf("could not initialize go_syslog : %v", err.Error())
	}
	log.SetOutput(syslogger)
	log.Printf("Log Entry")
}
```

#### [Query Packages Modules Dependeny](#query-packages-modules-dependeny)

```shell
go list -f '{{join .Deps "\n"}}' | xargs go list -f '{{if not .Standard}}{{.ImportPath}}{{end}}'
```

#### Output

```
cloud.google.com/go/compute/metadata
cloud.google.com/go/internal/version
cloud.google.com/go/logging
cloud.google.com/go/logging/apiv2
cloud.google.com/go/logging/internal
github.com/bradfitz/gomemcache/memcache
github.com/go-stack/stack
github.com/golang/groupcache/lru
...
...
...
github.com/jackc/pgpassfile
github.com/jackc/pgproto3/v2
```

```shell
go list -f '{{join .Deps "\n"}}' |  xargs go list -f '{{.ImportPath}}'
```

#### Output

```
bufio
bytes
cloud.google.com/go/compute/metadata
cloud.google.com/go/internal/version
cloud.google.com/go/logging
cloud.google.com/go/logging/apiv2
cloud.google.com/go/logging/internal
compress/flate
...
...
crypto/sha1
crypto/sha256
crypto/sha512
crypto/subtle
crypto/tls
crypto/x509
crypto/x509/internal/macos
crypto/x509/pkix
database/sql
database/sql/driver
encoding
encoding/asn1
encoding/base64
...
...
encoding/pem
errors
flag
fmt
```

#### [MongoDB Cancel With Context](#MongoDB-Cancel-With-Context)

```go
package main

import (
	"context"
	"fmt"
	"time"

	"go.mongodb.org/mongo-driver/bson"
	"go.mongodb.org/mongo-driver/mongo"
	"go.mongodb.org/mongo-driver/mongo/options"
)

// This is a user defined method to close resources.
// This method closes mongoDB connection and cancel context.
func close(client *mongo.Client, ctx context.Context,
	cancel context.CancelFunc) {

	defer cancel()

	defer func() {
		if err := client.Disconnect(ctx); err != nil {
			panic(err)
		}
	}()
}

// This is a user defined method that returns mongo.Client,
// context.Context, context.CancelFunc and error.
// mongo.Client will be used for further database operation.
// context.Context will be used set deadlines for process.
// context.CancelFunc will be used to cancel context and
// resource associated with it.
func connect(uri string) (*mongo.Client, context.Context, context.CancelFunc, error) {

	ctx, cancel := context.WithTimeout(context.Background(), 30*time.Second)
	client, err := mongo.Connect(ctx, options.Client().ApplyURI(uri))
	return client, ctx, cancel, err
}

// insertOne is a user defined method, used to insert
// documents into collection returns result of InsertOne
// and error if any.
func insertOne(client *mongo.Client, ctx context.Context, dataBase, col string, doc interface{}) (*mongo.InsertOneResult, error) {

	// select database and collection ith Client.Database method
	// and Database.Collection method
	collection := client.Database(dataBase).Collection(col)

	// InsertOne accept two argument of type Context
	// and of empty interface
	result, err := collection.InsertOne(ctx, doc)
	return result, err
}

// insertMany is a user defined method, used to insert
// documents into collection returns result of
// InsertMany and error if any.
func insertMany(client *mongo.Client, ctx context.Context, dataBase, col string, docs []interface{}) (*mongo.InsertManyResult, error) {

	// select database and collection ith Client.Database
	// method and Database.Collection method
	collection := client.Database(dataBase).Collection(col)

	// InsertMany accept two argument of type Context
	// and of empty interface
	result, err := collection.InsertMany(ctx, docs)
	return result, err
}

func main() {

	// get Client, Context, CancelFunc and err from connect method.
	client, ctx, cancel, err := connect("mongodb://localhost:27017")
	if err != nil {
		panic(err)
	}

	// Release resource when main function is returned.
	defer close(client, ctx, cancel)

	// Create a object of type interface to store
	// the bson values, that we are inserting into database.
	var document interface{}

	document = bson.D{
		{"rollNo", 175},
		{"maths", 80},
		{"science", 90},
		{"computer", 95},
	}

	// insertOne accepts client , context, database
	// name collection name and an interface that
	// will be inserted into the collection.
	// insertOne returns an error and aresult of
	// insertina single document into the collection.
	insertOneResult, err := insertOne(client, ctx, "gfg",
		"marks", document)

	// handle the error
	if err != nil {
		panic(err)
	}

	// print the insertion id of the document,
	// if it is inserted.
	fmt.Println("Result of InsertOne")
	fmt.Println(insertOneResult.InsertedID)

	// Now will be inserting multiple documents into
	// the collection. create a object of type slice
	// of interface to store multiple documents
	var documents []interface{}

	// Storing into interface list.
	documents = []interface{}{
		bson.D{
			{"rollNo", 153},
			{"maths", 65},
			{"science", 59},
			{"computer", 55},
		},
		bson.D{
			{"rollNo", 162},
			{"maths", 86},
			{"science", 80},
			{"computer", 69},
		},
	}

	// insertMany insert a list of documents into
	// the collection. insertMany accepts client,
	// context, database name collection name
	// and slice of interface. returns error
	// if any and result of multi document insertion.
	insertManyResult, err := insertMany(client, ctx, "gfg",
		"marks", documents)

	// handle the error
	if err != nil {
		panic(err)
	}

	fmt.Println("Result of InsertMany")

	// print the insertion ids of the multiple
	// documents, if they are inserted.
	for id := range insertManyResult.InsertedIDs {
		fmt.Println(id)
	}
}
```

#### [Client And Server WebSockets](#client-and-server-websockets)

## Golang – Using Gorilla Websockets

```
In this tutorial, we’ll be looking at how we can use the 
Gorilla Websocket package in Golang.

This library provides us with easy to write websocket 
client/servers in Go. It has a working production quality 
Go implementation of the websocket protocol, which enables 
us to deal with stateful http connections using websockets.
```

#### Installing Gorilla Websocket Go Package

```
go get github.com/gorilla/websocket
```

#### Websocket application Design

```
Before going on to any examples, let’s first design a 
rough layout of what needs to be done.

Any application using the websocket protocol generally 
needs a client and a server.

The server program binds to a port on the server and starts 
listening for any websocket connections. The connection related 
details are defined by the websocket protocol, which acts over a 
raw HTTP connection.

The client program tries to make a connection with the server 
using a websocket URL. Note that the client program does NOT need 
to be implemented using Golang, although Gorilla provides us with 
APIs for writing clients.

If you have a web application using a separate frontend, generally 
the websocket client would be implemented in that language (Javascript, etc)

However, for the purpose of illustration, we will be writing BOTH 
the client and the server programs in Go.

Now let’s get our client-server architecture running!
```

#### Using Gorilla Websockets – Creating our server

```
The websocket server will be implemented over a regular http server. 
We’ll be using net/http for serving raw HTTP connections.

Now in server.go, let’s write our regular HTTP server and add a 
socketHandler() function to handle the websocket logic.
```

#### server.go

```golang
// server.go
package main
 
import (
    "log"
    "net/http"
    "time"
 
    "github.com/gorilla/websocket"
)
 
var upgrader = websocket.Upgrader{} // use default options
 
func socketHandler(w http.ResponseWriter, r *http.Request) {
    // Upgrade our raw HTTP connection to a websocket based one
    conn, err := upgrader.Upgrade(w, r, nil)
    if err != nil {
        log.Print("Error during connection upgradation:", err)
        return
    }
    defer conn.Close()
 
    // The event loop
    for {
        messageType, message, err := conn.ReadMessage()
        if err != nil {
            log.Println("Error during message reading:", err)
            break
        }
        log.Printf("Received: %s", message)
        err = conn.WriteMessage(messageType, message)
        if err != nil {
            log.Println("Error during message writing:", err)
            break
        }
    }
}
 
func home(w http.ResponseWriter, r *http.Request) {
    fmt.Fprintf(w, "Index Page")
}
 
func main() {
    http.HandleFunc("/socket", socketHandler)
    http.HandleFunc("/", home)
    log.Fatal(http.ListenAndServe("localhost:8080", nil))
}
```

```
The magic that gorilla does is to convert these raw HTTP 
connections into a stateful websocket connection, using a 
connection upgradation. This is why the library uses a struct 
called Upgrader to help us with that.

We use a global upgrader variable to help us convert any 
incoming HTTP connection into websocket protocol, via 
upgrader.Upgrade(). This will return to us a *websocket.Connection, 
which we can now use to deal with the websocket connection.

The server reads messages using conn.ReadMessage() and writes them 
back using conn.WriteMessage()

This server simply echoes any incoming websocket messages back 
to the client, so this shows how websockets can be used for 
full-duplex communication.

Now let’s move onto the client implementation at client.go.
```

#### Now let’s move onto the client implementation at client.go.

```
We will be writing the client also using Gorilla. 
This simple client will keep emitting messages 
after every 1 second. If our entire system works as 
intended, the server will receive packets spaced at 
an interval of 1 second and reply the same message back.

The client will also have functionality to receive 
incoming websocket packets. In our program, we will 
have a separate goroutine handler receiveHandler which 
listens for these incoming packets.
```

#### client.go

```golang
// client.go
package main

import (
	"log"
	"os"
	"os/signal"
	"time"

	"github.com/gorilla/websocket"
)

var done chan interface{}
var interrupt chan os.Signal

func receiveHandler(connection *websocket.Conn) {
	defer close(done)
	for {
		_, msg, err := connection.ReadMessage()
		if err != nil {
			log.Println("Error in receive:", err)
			return
		}
		log.Printf("Received: %s\n", msg)
	}
}

func main() {
	done = make(chan interface{})    // Channel to indicate that the receiverHandler is done
	interrupt = make(chan os.Signal) // Channel to listen for interrupt signal to terminate gracefully

	signal.Notify(interrupt, os.Interrupt) // Notify the interrupt channel for SIGINT

	socketUrl := "ws://localhost:8080" + "/socket"
	conn, _, err := websocket.DefaultDialer.Dial(socketUrl, nil)
	if err != nil {
		log.Fatal("Error connecting to Websocket Server:", err)
	}
	defer conn.Close()
	go receiveHandler(conn)

	// Our main loop for the client
	// We send our relevant packets here
	for {
		select {
		case <-time.After(time.Duration(1) * time.Millisecond * 1000):
			// Send an echo packet every second
			err := conn.WriteMessage(websocket.TextMessage, []byte("Hello from GolangDocs!"))
			if err != nil {
				log.Println("Error during writing to websocket:", err)
				return
			}

		case <-interrupt:
			// We received a SIGINT (Ctrl + C). Terminate gracefully...
			log.Println("Received SIGINT interrupt signal. Closing all pending connections")

			// Close our websocket connection
			err := conn.WriteMessage(websocket.CloseMessage, websocket.FormatCloseMessage(websocket.CloseNormalClosure, ""))
			if err != nil {
				log.Println("Error during closing websocket:", err)
				return
			}

			select {
			case <-done:
				log.Println("Receiver Channel Closed! Exiting....")
			case <-time.After(time.Duration(1) * time.Second):
				log.Println("Timeout in closing receiving channel. Exiting....")
			}
			return
		}
	}
}
```

```
If you observe the code, you’ll notice that I created two channels done 
and interrupt for communication between receiveHandler() and main().

We use an infinite loop for listening to events through channels 
using select. We write a message using conn.WriteMessage() every second. 
If the interrupt signal is activated, any pending connections are closed 
and we exit gracefully!
```

```
The nested select is there to ensure two things:

- If the receiveHandler channel exits, the channel 'done' will be closed. 
  This is the first case <-done condition

- If the 'done' channel does NOT close, there will be a timeout 
  after 1 second, so the program WILL exit after the 1 second timeout

By carefully handling all cases using channels, select, 
you can have a minimal architecture which can be extended easily.

Let’s finally look at the output we get, on running both the 
client and the server!
```

#### [Read And Pretty Print JSON File](#read-and-pretty-print-json-file)

```golang
package main

import (
	"encoding/json"
	"fmt"
	"io/ioutil"
	"os"
)

func main() {

	configFile := "config.json"

	// Open our jsonFile
	jsonFile, err := os.Open("config.json")
	// if we os.Open returns an error then handle it
	if err != nil {
		fmt.Printf("\ncould not open json file : (%v) : %v", configFile, err.Error())
		return
	}
	fmt.Printf("\nsuccessfully opened json file (%v)\n", configFile)
	// defer the closing of our jsonFile so that we can parse it later on
	defer jsonFile.Close()

	byteValue, _ := ioutil.ReadAll(jsonFile)

	var result map[string]interface{}

	err = json.Unmarshal([]byte(byteValue), &result)
	if err != nil {
		fmt.Printf("\nerror : could not unmarshal json : %v", err.Error())
		return
	}

	myValue, ok := result["my_key"].(string)
	if ok {
		fmt.Printf("\n[my_key] : (%v)\n", myValue)
	}

	myFloat, ok := result["my_key_float"].(float64)
	if ok {
		fmt.Printf("\n[my_key_float] : (%v)\n", myFloat)
	}

	myList, ok := result["my_list"].([]interface{})
	if ok {
		fmt.Printf("\n[my_list] : (%v)\n", myList)
	}

	myNestedMap, ok := result["my_nested_data_key"].(map[string]interface{})
	if ok {
		fmt.Printf("\n[my_nested_data_key] : (%v)\n", myNestedMap)
	}

	// -------------- pretty print the json data | start ----------------

	dataBytes, err := json.MarshalIndent(result, "", "    ")
	if err != nil {
		fmt.Printf("\nerror : could not MarshalIndent json : %v", err.Error())
		return
	}
	fmt.Printf("\n\njson:\n\n%v\n", string(dataBytes))
	// -------------- pretty print the json data | end ----------------
}

/*

Output:

# go run main.go

successfully opened json file (config.json)

[my_key] : (my_value)

[my_key_float] : (20.555)

[my_list] : ([1 2 3 4])

[my_nested_data_key] : (map[my_nested_data_value:my_nested_value])


json:

{
    "my_key": "my_value",
    "my_key_float": 20.555,
    "my_key_numeric": 10,
    "my_list": [
        1,
        2,
        3,
        4
    ],
    "my_nested_data_key": {
        "my_nested_data_value": "my_nested_value"
    }
}

*/
```

#### [Pretty Print JSON File](#pretty-print-json-file)

Method-1

```golang
package main

import (
    "encoding/json"
    "fmt"
    "log"
)

func PrettyStruct(data interface{}) (string, error) {
    val, err := json.MarshalIndent(data, "", "    ")
    if err != nil {
        return "", err
    }
    return string(val), nil
}

type Fruit struct {
    Name  string `json:"name"`
    Color string `json:"color"`
}

func main() {
    fruit := Fruit{
        Name:  "Strawberry",
        Color: "red",
    }
    res, err := PrettyStruct(fruit)
    if err != nil {
        log.Fatal(err)
    }
    fmt.Println(res)
}
```

Method-2

```golang
package main

import (
    "bytes"
    "encoding/json"
    "fmt"
    "io"
    "log"
)

func PrettyEncode(data interface{}, out io.Writer) error {
    enc := json.NewEncoder(out)
    enc.SetIndent("", "    ")
    if err := enc.Encode(data); err != nil {
        return err
    }
    return nil
}

type Fruit struct {
    Name  string `json:"name"`
    Color string `json:"color"`
}

func main() {
    fruit := Fruit{
        Name:  "Strawberry",
        Color: "red",
    }
    var buffer bytes.Buffer
    err := PrettyEncode(fruit, &buffer)
    if err != nil {
        log.Fatal(err)
    }
    fmt.Println(buffer.String())
}
```

Method-3

```golang
package main

import (
    "bytes"
    "encoding/json"
    "fmt"
    "log"
)

func PrettyString(str string) (string, error) {
    var prettyJSON bytes.Buffer
    if err := json.Indent(&prettyJSON, []byte(str), "", "    "); err != nil {
        return "", err
    }
    return prettyJSON.String(), nil
}

func main() {
    fruitJSON := `{"name": "Strawberry", "color": "red"}`
    res, err := PrettyString(fruitJSON)
    if err != nil {
        log.Fatal(err)
    }
    fmt.Println(res)
}
```

#### [PostgreSQL and JSON](#postgresql-and-json)

```sql
-- Create a table with a JSONB column.
CREATE TABLE items (
    id SERIAL PRIMARY KEY,
    attrs JSONB
);

-- You can insert any well-formed json input into the column. Note that only
-- lowercase `true` and `false` spellings are accepted.
INSERT INTO items (attrs) VALUES ('{
   "name": "Pasta",
   "ingredients": ["Flour", "Eggs", "Salt", "Water"],
   "organic": true,
   "dimensions": {
      "weight": 500.00
   }
}');

-- Create an index on all key/value pairs in the JSONB column.
CREATE INDEX idx_items_attrs ON items USING gin (attrs);

-- Create an index on a specific key/value pair in the JSONB column.
CREATE INDEX idx_items_attrs_organic ON items USING gin ((attrs->'organic'));

-- The -> operator is used to get the value for a key. The returned value has
-- the type JSONB.
SELECT attrs->'dimensions' FROM items;
SELECT attrs->'dimensions'->'weight' FROM items;

-- Or you can use ->> to do the same thing, but this returns a TEXT value
-- instead.
SELECT attrs->>'dimensions' FROM items;

-- You can use the returned values as normal, although you may need to type
-- cast them first.
SELECT * FROM items WHERE attrs->>'name' ILIKE 'p%';
SELECT * FROM items WHERE (attrs->'dimensions'->>'weight')::numeric < 100.00;

-- Use ? to check for the existence of a specific key.
SELECT * FROM items WHERE attrs ? 'ingredients';

-- The ? operator only works at the top level. If you want to check for the
-- existence of a nested key you can do this:
SELECT * FROM items WHERE attrs->'dimensions' ? 'weight';

-- The ? operator can also be used to check for the existence of a specific
-- text value in json arrays.
SELECT * FROM items WHERE attrs->'ingredients' ? 'Salt';

-- Use @> to check if the JSONB column contains some specific json. This can
-- be useful to filter for a specific key/value pair like so:
SELECT * FROM items WHERE attrs @> '{"organic": true}'::jsonb;
SELECT * FROM items WHERE attrs @> '{"dimensions": {"weight": 10}}'::jsonb;

-- Note that @> looks for *containment*, not for an exact match. The
-- followingquery will return records which have both "Flour" and "Water"
-- as ingredients, rather than *only* "Flour" and "Water" as the ingredients.
SELECT * FROM items WHERE attrs @> '{"ingredients": ["Flour", "Water"]}'::jsonb;
```

Go Code To Query

`Known JSON fields`

When the fields in a JSON/JSONB column are known in advance, you can 
map the contents of the JSON/JSONB column to and from a struct. 
To do this, you'll need make sure the struct implements:

- The driver.Valuer interface, such that it marshals the object into a JSON byte slice that can be understood by the database.

- The sql.Scanner interface, such that it unmarshals a JSON byte slice from the database into the struct fields.

```golang
package main

import (
    "database/sql"
    "database/sql/driver"
    "encoding/json"
    "errors"
    "log"

    _ "github.com/lib/pq"
)

type Item struct {
    ID    int
    Attrs Attrs
}

// The Attrs struct represents the data in the JSON/JSONB column. We can use
// struct tags to control how each field is encoded.
type Attrs struct {
    Name        string   `json:"name,omitempty"`
    Ingredients []string `json:"ingredients,omitempty"`
    Organic     bool     `json:"organic,omitempty"`
    Dimensions  struct {
        Weight float64 `json:"weight,omitempty"`
    } `json:"dimensions,omitempty"`
}

// Make the Attrs struct implement the driver.Valuer interface. This method
// simply returns the JSON-encoded representation of the struct.
func (a Attrs) Value() (driver.Value, error) {
    return json.Marshal(a)
}

// Make the Attrs struct implement the sql.Scanner interface. This method
// simply decodes a JSON-encoded value into the struct fields.
func (a *Attrs) Scan(value interface{}) error {
    b, ok := value.([]byte)
    if !ok {
        return errors.New("type assertion to []byte failed")
    }

    return json.Unmarshal(b, &a)
}

func main() {
    db, err := sql.Open("postgres", "postgres://user:pass@localhost/db")
    if err != nil {
        log.Fatal(err)
    }

    // Initialize a new Attrs struct and add some values.
    attrs := new(Attrs)
    attrs.Name = "Pesto"
    attrs.Ingredients = []string{"Basil", "Garlic", "Parmesan", "Pine nuts", "Olive oil"}
    attrs.Organic = false
    attrs.Dimensions.Weight = 100.00

    // The database driver will call the Value() method and and marshall the
    // attrs struct to JSON before the INSERT.
    _, err = db.Exec("INSERT INTO items (attrs) VALUES($1)", attrs)
    if err != nil {
        log.Fatal(err)
    }

    // Similarly, we can also fetch data from the database, and the driver
    // will call the Scan() method to unmarshal the data to an Attr struct.
    item := new(Item)
    err = db.QueryRow("SELECT id, attrs FROM items ORDER BY id DESC LIMIT 1").Scan(&item.ID, &item.Attrs)
    if err != nil {
        log.Fatal(err)
    }

    // You can then use the struct fields as normal...
    weightKg := item.Attrs.Dimensions.Weight / 1000
    log.Printf("Item: %d, Name: %s, Weight: %.2fkg", item.ID, item.Attrs.Name, weightKg)
}
```

`Unknown JSON fields`

The above pattern works great if you know in advance what keys and 
values your JSON/JSONB data will contain. And it has the major advantage 
of being type safe.

For the times that you don't know this in advance (for example, the data 
contains user-generated keys and values) you can map the contents of the 
JSON/JSONB column to and from a map[string]interface{} instead. The big 
downside of this is that you will need to type assert any values that you 
retrieve from the database in order to use them.

```golang
package main

import (
    "database/sql"
    "database/sql/driver"
    "encoding/json"
    "errors"
    "log"

    _ "github.com/lib/pq"
)

type Item struct {
    ID    int
    Attrs Attrs
}

type Attrs map[string]interface{}

func (a Attrs) Value() (driver.Value, error) {
    return json.Marshal(a)
}

func (a *Attrs) Scan(value interface{}) error {
    b, ok := value.([]byte)
    if !ok {
        return errors.New("type assertion to []byte failed")
    }

    return json.Unmarshal(b, &a)
}

func main() {
    db, err := sql.Open("postgres", "postgres://user:pass@localhost/db")
    if err != nil {
        log.Fatal(err)
    }

    item := new(Item)
    item.Attrs = Attrs{
        "name":        "Passata",
        "ingredients": []string{"Tomatoes", "Onion", "Olive oil", "Garlic"},
        "organic":     true,
        "dimensions": map[string]interface{}{
            "weight": 250.00,
        },
    }

    _, err = db.Exec("INSERT INTO items (attrs) VALUES($1)", item.Attrs)
    if err != nil {
        log.Fatal(err)
    }

    item = new(Item)
    err = db.QueryRow("SELECT id, attrs FROM items ORDER BY id DESC LIMIT 1").Scan(&item.ID, &item.Attrs)
    if err != nil {
        log.Fatal(err)
    }

    name, ok := item.Attrs["name"].(string)
    if !ok {
        log.Fatal("unexpected type for name")
    }
    dimensions, ok := item.Attrs["dimensions"].(map[string]interface{})
    if !ok {
        log.Fatal("unexpected type for dimensions")
    }
    weight, ok := dimensions["weight"].(float64)
    if !ok {
        log.Fatal("unexpected type for weight")
    }
    weightKg := weight / 1000
    log.Printf("%s: %.2fkg", name, weightKg)
}
```
