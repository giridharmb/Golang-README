### Golang Snippets

#### How to check the type of a value in Go

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

#### Output

```
type of a is string
type of b is float64
type of c is bool
type of d is []int
type of e is map[string]string
```