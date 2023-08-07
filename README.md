### Golang Snippets

[Server Sent Events](#server-sent-events)

[Golang Sessions](#golang-sessions)

[Create Random String Of Fixed Length](#create-random-string-of-fixed-length)

[Check If String Is Valid JSON](#check-if-string-is-valid-json)

[Convert JSON To String And String To JSON](#convert-json-to-string-and-string-to-json)

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

[Read And Write To Channel](#read-and-write-to-channel)

[RabbitMQ Producer And Consumer](#rabbitmq-producer-and-consumer)

[Generic HTTP Request V1](#generic-http-request-v1)

[Generic HTTP Request V2](#generic-http-request-v2)

[Panic And Recover](#panic-and-recover)

[HTTP Web Server And REST API](https://github.com/giridharmb/golang-http-server-rest-api)

[PostgreSQL And HTTP REST API](https://github.com/giridharmb/golang-pgsql-http-rest-api)

[User Prompts And Inputs](#user-prompts-and-inputs)

[Reading YAML](#reading-yaml)

[MongoDB Context With Cancel](#mongodb-context-with-cancel)

[Encoding And Decoding](#encoding-and-decoding)

[HTTP File Upload Client And Server](#http-file-upload-client-and-server)

[Azure Resource Graph Query](#azure-resource-graph-query)

[Worker Pools](#worker-pools)

[Worker Pool V2](#worker-pool-v2)

[Worker Pool V3](#worker-pool-v3)

[Ubuntu Service File Running Binary](#ubuntu-service-file-running-binary)

[Parse EMail Address](#parse-email-address)

[Return Channel From Function V1](#return-channel-from-function-v1)

[Return Channel From Function V2](#return-channel-from-function-v2)

[Return Channel From Function V3](#return-channel-from-function-v3)

[Factory Design Pattern V1](#factory-design-pattern-v1)

[Factory Design Pattern V2](#factory-design-pattern-v2)

[Read Config File](#read-config-file)

[Read YAML Config File](#read-yaml-config-file)

<hr/>

#### [Server Sent Events](#server-sent-events)

`main.go`

```golang
package main

import (
    "bytes"
    "encoding/json"
    "fmt"
    "github.com/gofiber/adaptor/v2"
    "github.com/gofiber/fiber/v2"
    "log"
    "math/rand"
    "net/http"
    "time"
)

type Client struct {
    name   string
    events chan *MetaData
}
type MetaData struct {
    Data map[string]interface{}
}

func main() {

    app := fiber.New()
    app.Get("/sse", adaptor.HTTPHandler(handler(dashboardHandler)))
    _ = app.Listen(":3000")
}

func handler(f http.HandlerFunc) http.Handler {
    return f
}

func dashboardHandler(w http.ResponseWriter, r *http.Request) {

    client := &Client{name: r.RemoteAddr, events: make(chan *MetaData, 10)}

    log.Printf("r.RemoteAddr : %v", r.RemoteAddr)

    go updateMetaData(client)

    w.Header().Set("Access-Control-Allow-Origin", "*")
    w.Header().Set("Access-Control-Allow-Headers", "Content-Type")
    w.Header().Set("Content-Type", "text/event-stream")
    w.Header().Set("Cache-Control", "no-cache")
    w.Header().Set("Connection", "keep-alive")

    timeout := time.After(1 * time.Second)

    select {

    case ev := <-client.events:
        var buf bytes.Buffer
        enc := json.NewEncoder(&buf)
        _ = enc.Encode(ev)
        _, _ = fmt.Fprintf(w, "data: %v\n\n", buf.String())
        fmt.Printf("data: %v\n", buf.String())

    case <-timeout:
        _, _ = fmt.Fprintf(w, ": nothing to sent\n\n")
    }

    if f, ok := w.(http.Flusher); ok {
        f.Flush()
    }
}

func updateMetaData(client *Client) {
    for {
        myMap := make(map[string]interface{})
        myMap["rs"] = GetRandomString()
        myMap["rn"] = GetRandomNumber()

        db := &MetaData{Data: myMap}
        client.events <- db
    }
}

var letterRunesSet = []rune("abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ")

func GetRandomString() string {
    n := 10 // length of string
    rand.Seed(time.Now().UnixNano())
    b := make([]rune, n)
    for i := range b {
        b[i] = letterRunesSet[rand.Intn(len(letterRunesSet))]
    }
    return string(b)
}

func GetRandomNumber() int {
    rand.Seed(time.Now().UnixNano())
    max := 300
    min := 100
    rand.Seed(time.Now().UnixNano())
    return rand.Intn(max-min) + min
}
```

`index.html`

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>Blank HTML5</title>
        <script src="http://ajax.googleapis.com/ajax/libs/jquery/1.8.3/jquery.min.js"></script>
    </head>
    <body>
        <p>This is my HTML5 Boilerplate.</p>
    </body>
</html>

<script>
window.addEventListener('DOMContentLoaded', (event) => {
    const source = new EventSource("http://localhost:3000/sse");
    source.onmessage = (event) => {
        console.log("OnMessage Called:")
        console.log(event)
        console.log(JSON.parse(event.data))
    }
});
</script>
```

#### [Golang Sessions](#golang-sessions)

```golang
package main

import (
    "fmt"
    "log"
    "net/http"

    "github.com/gorilla/sessions"
)

var cookie *sessions.CookieStore

func init() {
    cookie = sessions.NewCookieStore([]byte("Golang-Blogs"))
}

func home(w http.ResponseWriter, r *http.Request) {
    session, _ := cookie.Get(r, "Golang-session")
    var authenticated interface{} = session.Values["authenticated"]
    if authenticated != nil {
        isAuthenticated := session.Values["authenticated"].(bool)
        if !isAuthenticated {
            http.Error(w, "UnAuthorized to Access this Page.", http.StatusForbidden)
            return
        }
        fmt.Fprintf(w, "Authenticated User's Home Page")
    }

}

func login(w http.ResponseWriter, r *http.Request) {
    session, _ := cookie.Get(r, "Golang-session")
    session.Values["authenticated"] = true
    session.Save(r, w)
    fmt.Fprintf(w, "Successfully Logged In")
}

func logout(w http.ResponseWriter, r *http.Request) {
    session, _ := cookie.Get(r, "Golang-session")
    session.Values["authenticated"] = false
    session.Save(r, w)
    fmt.Fprintf(w, "Successfully Logged Out")
}

func main() {
    http.HandleFunc("/", home)
    http.HandleFunc("/login", login)
    http.HandleFunc("/logout", logout)
    err := http.ListenAndServe(":8080", nil)
    if err != nil {
        log.Fatal("Error Starting the HTTP Server : ", err)
        return
    }
}
```

#### [Create Random String Of Fixed Length](#create-random-string-of-fixed-length)
```golang
func init() {
    rand.Seed(time.Now().UnixNano())
}

var letterRunes = []rune("abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ")

func RandStringRunes(n int) string {
    b := make([]rune, n)
    for i := range b {
        b[i] = letterRunes[rand.Intn(len(letterRunes))]
    }
    return string(b)
}
```

#### [Check If String Is Valid JSON](#check-if-string-is-valid-json)

```golang
func IsJSON(str string) bool {
    var js json.RawMessage
    return json.Unmarshal([]byte(str), &js) == nil
}

func IsMap(data interface{}) bool {
    if data == nil {
        return false
    } else {
        return reflect.ValueOf(data).Kind() == reflect.Map
    }
}

func IsString(data interface{}) bool {
    if data == nil {
        return false
    } else {
        return reflect.ValueOf(data).Kind() == reflect.String
    }
}
```
#### [Convert JSON To String And String To JSON](#convert-json-to-string-and-string-to-json)

```golang

// main.go

package main

import (
    "encoding/json"
    "fmt"
)

func main() {

    // ---(1)--- Convert JSON (Map) to String -----------

    //-----------  simple JSON -----------

    map1 := map[string]string{
        "a": "apple",
        "b": "banana",
    }
    jsonStr, err := json.Marshal(map1)
    if err != nil {
        fmt.Printf("Error: %s", err.Error())
    } else {
        fmt.Println(string(jsonStr))
    }

    //-----------  nested JSON -----------

    var x = map[string]map[string]string{}

    x["fruits"] = map[string]string{}
    x["colors"] = map[string]string{}

    x["fruits"]["a"] = "apple"
    x["fruits"]["b"] = "banana"

    x["colors"]["r"] = "red"
    x["colors"]["b"] = "blue"

    jsonStr, err = json.Marshal(x)
    if err != nil {
        fmt.Printf("\nERROR: could not marshal json map : %v", err.Error())
    } else {
        fmt.Println(string(jsonStr))
    }

    // ---(2)--- Convert String to JSON (Map) -----------

    var jsonMap map[string]interface{}
    jsonString := fmt.Sprintf(`{"x": "123", "y": 10.44, "z": [1,2,3,4], "xyz" : {"x1":11, "x2": [1,2,3,4,5,6]}}`)
    err = json.Unmarshal([]byte(jsonString), &jsonMap)
    if err != nil {
        fmt.Printf("\nERROR : could not unmarshal json string : %v", err.Error())
        return
    }
    fmt.Println(jsonMap)

}
```

Output `go run main.go`

```
{"a":"apple","b":"banana"}
{"colors":{"b":"blue","r":"red"},"fruits":{"a":"apple","b":"banana"}}
map[x:123 xyz:map[x1:11 x2:[1 2 3 4 5 6]] y:10.44 z:[1 2 3 4]]
```

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

#### [Read And Write To Channel](#read-and-write-to-channel)

```golang
package main

import (
    "log"
    "math/rand"
    "sync"
    "time"
)

/*
What does this program do ?

1. create a function 'getRandomNumber'
    > which generates a random number between max(=300) and min(=100)

2. create 3 different goroutines

    goroutine-1:
        > in a for loop:
            > get a random number using 'getRandomNumber'
            > put the value into channel 'channelSend'

    goroutine-2:
        > in a for loop:
            > read the value from channel 'channelSend' , and
            > insert the value into another channel 'channelReceive'

    goroutine-3:
        > in a for loop
            > read the value from channel 'channelReceive'
            > log the value on stdout.

3. after MaxTimeSeconds(=10 secs) have been lapsed
    > gracefully close all the channels
    > then exit.
*/

var (
    MaxTimeSeconds float64 = 10
)

func getRandomNumber() int {
    max := 300
    min := 100
    rand.Seed(time.Now().UnixNano())
    return rand.Intn(max-min) + min
}

func generateRandomAndPush(wg *sync.WaitGroup, myChannel chan int) {
    defer wg.Done()
    start := time.Now()
    for {
        myChannel <- getRandomNumber()
        time.Sleep(2 * time.Second)
        duration := time.Since(start)
        totalTimeElapsed := duration.Seconds()
        log.Printf("> total time elapsed : %v", totalTimeElapsed)
        if totalTimeElapsed > MaxTimeSeconds {
            close(myChannel)
            log.Printf("@ channelSend is closed.")
            return
        }
    }
}

func getFromChannelAndPush(wg *sync.WaitGroup, getChannel chan int, pushChannel chan int) {
    defer wg.Done()
    for {
        receivedData, ok := <-getChannel
        if !ok {
            log.Printf("@ not more data from <-getChannel !")
            close(pushChannel)
            log.Printf("@ pushChannel is closed.")
            return
        } else {
            pushChannel <- receivedData
        }
    }
}

func receiveData(wg *sync.WaitGroup, receiveFromChannel chan int, done chan bool) {
    defer func() {
        wg.Done()
        done <- true
    }()
    for {
        receivedData, ok := <-receiveFromChannel
        if !ok {
            log.Printf("@ no data from <-receiveFromChannel !")
            return
        }
        log.Printf("> receivedData : %v", receivedData)
    }
}

func main() {
    channelSend := make(chan int)
    channelReceive := make(chan int)

    done := make(chan bool)

    var wg sync.WaitGroup

    wg.Add(1)
    go generateRandomAndPush(&wg, channelSend)

    wg.Add(1)
    go getFromChannelAndPush(&wg, channelSend, channelReceive)

    wg.Add(1)
    go receiveData(&wg, channelReceive, done)

    log.Printf("waiting...")

    wg.Wait()

    log.Printf("done waiting !")

    <-done

    log.Printf("done <- true")
}

/*
Sample Rnn:

2009/11/10 23:00:00 waiting...
2009/11/10 23:00:00 > receivedData : 100
2009/11/10 23:00:02 > total time elapsed : 2
2009/11/10 23:00:02 > receivedData : 277
2009/11/10 23:00:04 > total time elapsed : 4
2009/11/10 23:00:04 > receivedData : 150
2009/11/10 23:00:06 > total time elapsed : 6
2009/11/10 23:00:06 > receivedData : 156
2009/11/10 23:00:08 > total time elapsed : 8
2009/11/10 23:00:08 > receivedData : 117
2009/11/10 23:00:10 > total time elapsed : 10
2009/11/10 23:00:10 > receivedData : 286
2009/11/10 23:00:12 > total time elapsed : 12
2009/11/10 23:00:12 @ channelSend is closed.
2009/11/10 23:00:12 @ not more data from <-channelSend !
2009/11/10 23:00:12 @ channelReceive is closed.
2009/11/10 23:00:12 @ no data from <-channelReceive !
2009/11/10 23:00:12 done waiting !
2009/11/10 23:00:12 done <- true

Program exited.
*/
```

#### [RabbitMQ Producer And Consumer](#rabbitmq-producer-and-consumer)

- FYI : Run Both Producer And Consumer Programs At The Same Time
- Producer -> Will Publish Messages
- Consumer -> Will Consume Messages
- Producer Will Exit Atfer 20 Seconds

*Producer* (`main.go`)

```golang
package main

import (
    "encoding/json"
    "fmt"
    "os"
    "time"

    log "github.com/sirupsen/logrus"
    amqp "github.com/streadway/amqp"
)

func failOnError(err error, msg string) bool {
    if err != nil {
        log.Errorf("%v : %v", msg, err.Error())
        return true
    }
    return false
}

var (
    // environment variables : 'MQUSER' , 'MQPASS', 'MQHOST'
    // please set them !

    MQUSER string = "" // MQ Username
    MQPASS string = "" // MQ Password
    MQHOST string = "" // MQ Hostname , Ex: my-mq-server.company.com
)

func initApp() bool {

    // check if ENV Variables are set.

    MQUSER = os.Getenv("MQUSER")
    if MQUSER == "" {
        log.Error("please set 'MQUSER' environment variable !")
        return false
    }

    MQPASS = os.Getenv("MQPASS")
    if MQPASS == "" {
        log.Error("please set 'MQPASS' environment variable !")
        return false
    }

    MQHOST = os.Getenv("MQHOST")
    if MQHOST == "" {
        log.Error("please set 'MQHOST' environment variable !")
        return false
    }
    return true
}

func publishMessage(queueName string, exchange string, data interface{}) {

    connectionString := fmt.Sprintf("amqp://%v:%v@%v:5672", MQUSER, MQPASS, MQHOST)
    // log.Printf("connectionString %v", connectionString)
    conn, err := amqp.Dial(connectionString)
    if failOnError(err, "Failed to connect to RabbitMQ") {
        return
    }
    defer conn.Close()

    ch, err := conn.Channel()
    if failOnError(err, "Failed to open a channel") {
        return
    }

    defer ch.Close()

    q, err := ch.QueueDeclare(
        queueName, // name
        false,     // durable
        false,     // delete when unused
        false,     // exclusive
        false,     // no-wait
        nil,       // arguments
    )
    if failOnError(err, "Failed to declare a queue") {
        return
    }

    body := ""

    jsonStr, err := json.Marshal(data)
    if err != nil {
        log.Errorf("could not marshal json data : %v", err.Error())
    } else {
        body = string(jsonStr)
        log.Printf("body : (%v)", body)
    }
    err = ch.Publish(
        exchange, // exchange
        q.Name,   // routing key
        false,    // mandatory
        false,    // immediate
        amqp.Publishing{
            ContentType: "text/plain",
            Body:        []byte(body),
        })
    if failOnError(err, "Failed to publish a message") {
        return
    }

    log.Printf(" [x] Sent %s\n", body)
}

func main() {

    successfullyInitialized := initApp()
    if !successfullyInitialized {
        return
    }

    done := make(chan bool)

    data1 := "hello_world"
    data2 := make(map[string]interface{})
    data2["x"] = []int{1, 2, 3, 4, 5}
    data2["y"] = "data"
    data3 := true

    data4 := "__done__"

    go func() {
        start := time.Now()
        for {
            time.Sleep(500 * time.Millisecond)
            publishMessage("test-queue", "", data1)
            publishMessage("test-queue", "", data2)
            publishMessage("test-queue", "", data3)
            duration := time.Since(start)
            totalTimeElapsed := duration.Seconds()
            log.Printf("totalTimeElapsed : %v", totalTimeElapsed)
            if totalTimeElapsed > 20 {
                publishMessage("test-queue", "", data4)
                done <- true
            }
        }
    }()

    log.Printf("waiting for done <- true")

    <-done

    log.Printf("Done sending : __done__ to consumer.")
}

/*
Producer Output:

INFO[0000] waiting for done <- true
INFO[0001] body : ("hello_world")
INFO[0001]  [x] Sent "hello_world"
INFO[0003] body : ({"x":[1,2,3,4,5],"y":"data"})
INFO[0003]  [x] Sent {"x":[1,2,3,4,5],"y":"data"}
INFO[0005] body : (true)
INFO[0005]  [x] Sent true
INFO[0005] totalTimeElapsed : 5.578337558
INFO[0007] body : ("hello_world")
INFO[0007]  [x] Sent "hello_world"
INFO[0008] body : ({"x":[1,2,3,4,5],"y":"data"})
INFO[0008]  [x] Sent {"x":[1,2,3,4,5],"y":"data"}
INFO[0010] body : (true)
INFO[0010]  [x] Sent true
INFO[0010] totalTimeElapsed : 10.917071813
INFO[0012] body : ("hello_world")
INFO[0012]  [x] Sent "hello_world"
INFO[0014] body : ({"x":[1,2,3,4,5],"y":"data"})
INFO[0014]  [x] Sent {"x":[1,2,3,4,5],"y":"data"}
INFO[0015] body : (true)
INFO[0015]  [x] Sent true
INFO[0016] totalTimeElapsed : 16.243441629
INFO[0017] body : ("hello_world")
INFO[0017]  [x] Sent "hello_world"
INFO[0019] body : ({"x":[1,2,3,4,5],"y":"data"})
INFO[0019]  [x] Sent {"x":[1,2,3,4,5],"y":"data"}
INFO[0021] body : (true)
INFO[0021]  [x] Sent true
INFO[0021] totalTimeElapsed : 21.572205004
INFO[0022] body : ("__done__")
INFO[0022]  [x] Sent "__done__"
INFO[0023] Done sending : __done__ to consumer.
*/
```

*Consumer* (`main.go`)

```golang
package main

import (
    "encoding/json"
    "fmt"
    "os"

    log "github.com/sirupsen/logrus"
    amqp "github.com/streadway/amqp"
)

func failOnError(err error, msg string) bool {
    if err != nil {
        log.Errorf("%v : %v", msg, err.Error())
        return true
    }
    return false
}

var (
    // environment variables : 'MQUSER' , 'MQPASS', 'MQHOST'
    // please set them !

    MQUSER string = "" // MQ Username
    MQPASS string = "" // MQ Password
    MQHOST string = "" // MQ Hostname , Ex: my-mq-server.company.com
)

func initApp() bool {

    // check if ENV Variables are set.

    MQUSER = os.Getenv("MQUSER")
    if MQUSER == "" {
        log.Error("please set 'MQUSER' environment variable !")
        return false
    }

    MQPASS = os.Getenv("MQPASS")
    if MQPASS == "" {
        log.Error("please set 'MQPASS' environment variable !")
        return false
    }

    MQHOST = os.Getenv("MQHOST")
    if MQHOST == "" {
        log.Error("please set 'MQHOST' environment variable !")
        return false
    }
    return true
}

func consumeMessage(queueName string, exchange string) {

    doneMessage := "__done__"
    connectionString := fmt.Sprintf("amqp://%v:%v@%v:5672", MQUSER, MQPASS, MQHOST)
    // log.Printf("connectionString %v", connectionString)
    conn, err := amqp.Dial(connectionString)
    if failOnError(err, "Failed to connect to RabbitMQ") {
        return
    }
    defer conn.Close()

    ch, err := conn.Channel()
    if failOnError(err, "Failed to open a channel") {
        return
    }

    defer ch.Close()

    q, err := ch.QueueDeclare(
        queueName, // name
        false,     // durable
        false,     // delete when unused
        false,     // exclusive
        false,     // no-wait
        nil,       // arguments
    )
    if failOnError(err, "Failed to declare a queue") {
        return
    }

    msgs, err := ch.Consume(
        q.Name, // queue
        "",     // consumer
        true,   // auto-ack
        false,  // exclusive
        false,  // no-local
        false,  // no-wait
        nil,    // args
    )
    if failOnError(err, "Failed to register a consumer") {
        return
    }

    forever := make(chan bool)

    var jsonMap interface{}

    go func() {
        for d := range msgs {
            err = json.Unmarshal([]byte(d.Body), &jsonMap)
            if err != nil {
                log.Errorf("Could not unmarshal json data : %v", err.Error())
            }
            log.Printf("Received Message : %v", jsonMap)
            // log.Printf("Received a message: %s", d.Body)
            doneMsg, ok := jsonMap.(string)
            if ok {
                if doneMsg == doneMessage {
                    log.Printf("Received Final : %v", doneMessage)
                    log.Printf("Will stop listening for further messages getting published...")
                    forever <- true
                }
            }
        }
    }()

    log.Printf(" [*] Waiting for messages. To exit press CTRL+C")
    <-forever
    log.Printf("Done with the consumer.")
}

func main() {

    successfullyInitialized := initApp()
    if !successfullyInitialized {
        return
    }

    consumeMessage("test-queue", "")

}

/*
Consumer Output:

INFO[0001]  [*] Waiting for messages. To exit press CTRL+C
INFO[0001] Received Message : hello_world
INFO[0001] Received Message : map[x:[1 2 3 4 5] y:data]
INFO[0001] Received Message : true
INFO[0002] Received Message : hello_world
INFO[0004] Received Message : map[x:[1 2 3 4 5] y:data]
INFO[0005] Received Message : true
INFO[0008] Received Message : hello_world
INFO[0009] Received Message : map[x:[1 2 3 4 5] y:data]
INFO[0011] Received Message : true
INFO[0013] Received Message : hello_world
INFO[0014] Received Message : map[x:[1 2 3 4 5] y:data]
INFO[0016] Received Message : true
INFO[0018] Received Message : __done__
INFO[0018] Received Final : __done__
INFO[0018] Will stop listening for further messages getting published...
INFO[0018] Done with the consumer.
*/
```

#### [Generic HTTP Request V1](#generic-http-request-v1)

```golang
package main

import (
    "bytes"
    "crypto/tls"
    "encoding/json"
    "errors"
    "fmt"
    "io/ioutil"
    "math/rand"
    "net"
    "net/http"
    "net/url"
    "reflect"
    "time"

    log "github.com/sirupsen/logrus"
)

type HttpRequestType int64

var (
    HttpTLSTimeOut time.Duration = 10 // 10 seconds
    MyHTTPProxy    string        = "http://my-proxy-server.company.com:5050"
)

var letterRunes = []rune("abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ")

const (
    GET HttpRequestType = iota
    HEAD
    POST
    PUT
    PATCH
    DELETE
)

type Request struct {
    URL           string
    Payload       string
    RequestMethod HttpRequestType
    Headers       string
    ProxyURL      string
}

type RequestMap struct {
    URL           string
    Payload       interface{} // you are expected to set this as a string or map[string]interface{}
    RequestMethod HttpRequestType
    Headers       interface{} // you are expected to set this as a string or map[string]string
    ProxyURL      string
}

func (r HttpRequestType) String() string {
    switch r {
    case GET:
        return "GET"
    case HEAD:
        return "HEAD"
    case POST:
        return "POST"
    case PUT:
        return "PUT"
    case PATCH:
        return "PATCH"
    case DELETE:
        return "DELETE"
    }
    return "UNKNOWN"
}

type IHTTPRequest interface {
    HTTPRequest() (string, *http.Response, error)
}

type IHTTPRequestMap interface {
    HTTPRequest() (string, *http.Response, error)
}

func IsMap(data interface{}) bool {
    if data == nil {
        return false
    } else {
        return reflect.ValueOf(data).Kind() == reflect.Map
    }
}

func IsString(data interface{}) bool {
    if data == nil {
        return false
    } else {
        return reflect.ValueOf(data).Kind() == reflect.String
    }
}

func IsJSON(str string) bool {
    var js json.RawMessage
    return json.Unmarshal([]byte(str), &js) == nil
}

func initRand() {
    rand.Seed(time.Now().UnixNano())
}

func RandStringRunes(n int) string {
    initRand()
    b := make([]rune, n)
    for i := range b {
        b[i] = letterRunes[rand.Intn(len(letterRunes))]
    }
    return string(b)
}

func (r RequestMap) HTTPRequest() (string, int, error) {
    log.Printf("URL : %v", r.URL)
    log.Printf("Payload : %v", r.Payload)
    log.Printf("RequestMethod : %v", r.RequestMethod)
    log.Printf("Headers : %v", r.Headers)

    responseString := ""
    responseHttpStatusCode := -1

    var headersMap map[string]interface{}
    var req *http.Request
    var err error
    var message string

    var tr *http.Transport

    payloadBytes := make([]byte, 0)
    payloadStr := ""

    headersBytes := make([]byte, 0)
    headersStr := ""

    // ---- r.Headers : should be a JSON string or map[string]string ------

    if IsString(r.Headers) {
        // if headers is string
        headersStr = r.Headers.(string)
        if !IsJSON(headersStr) {
            message = fmt.Sprintf("headers is not a valid JSON")
            log.Error(message)
            return responseString, responseHttpStatusCode, errors.New(message)
        }
        log.Printf("headers is a valid JSON STRING")
    } else {
        // if it is map[string]string or map[string]interface{}
        if IsMap(r.Headers) {
            log.Printf("headers is a valid map")
            headersBytes, err = json.Marshal(r.Headers)
            if err != nil {
                message = fmt.Sprintf("could not marshal json headers map to string : %v", err.Error())
                log.Error(message)
                return responseString, responseHttpStatusCode, errors.New(message)
            }
            headersStr = string(headersBytes)
            // log.Printf("headersStr : %v", headersStr)
        } else {
            // If is NOT a map
            log.Printf("headers is not a map")
            headersStr = ""
        }
    }

    // ---- r.Payload : should be a JSON string or map[string]interface{} ------

    if IsString(r.Payload) {
        // if it is a string
        payloadStr = r.Payload.(string)
        if !IsJSON(headersStr) {
            message = fmt.Sprintf("payload is not a valid JSON")
            log.Error(message)
            return responseString, responseHttpStatusCode, errors.New(message)
        }
        log.Printf("payload is a valid JSON string")
    } else {
        if IsMap(r.Payload) {
            // if it is map[string]string or map[string]interface{}
            log.Printf("payload is a valid map")
            payloadBytes, err = json.Marshal(r.Payload)
            if err != nil {
                message = fmt.Sprintf("could not marshal json payload map to string : %v", err.Error())
                log.Error(message)
                return responseString, responseHttpStatusCode, errors.New(message)
            }
            payloadStr = string(payloadBytes)
            log.Printf("payloadStr : %v", payloadStr)
        } else {
            // If is NOT a map
            log.Printf("payload is not a map")
            payloadStr = ""
        }
    }

    if r.ProxyURL == "" {
        tr = &http.Transport{
            TLSClientConfig: &tls.Config{InsecureSkipVerify: true},
            Dial: (&net.Dialer{
                Timeout:   0,
                KeepAlive: 0,
            }).Dial,
            TLSHandshakeTimeout: HttpTLSTimeOut * time.Second,
        }
    } else {
        proxyUrl, _ := url.Parse(MyHTTPProxy)
        tr = &http.Transport{
            TLSClientConfig: &tls.Config{InsecureSkipVerify: true},
            Dial: (&net.Dialer{
                Timeout:   0,
                KeepAlive: 0,
            }).Dial,
            Proxy:               http.ProxyURL(proxyUrl),
            TLSHandshakeTimeout: HttpTLSTimeOut * time.Second,
        }
    }

    if payloadStr == "" {
        req, err = http.NewRequest(r.RequestMethod.String(), r.URL, nil)
        if err != nil {
            message = fmt.Sprintf("could not create a new http request : %v", err.Error())
            log.Error(message)
            return responseString, responseHttpStatusCode, errors.New(message)
        }
    } else {
        req, err = http.NewRequest(r.RequestMethod.String(), r.URL, bytes.NewBuffer([]byte(payloadStr)))
        if err != nil {
            message = fmt.Sprintf("could not create a new http request : %v", err.Error())
            log.Error(message)
            return responseString, responseHttpStatusCode, errors.New(message)
        }
    }

    err = json.Unmarshal([]byte(headersStr), &headersMap)
    if err != nil {
        message = fmt.Sprintf("could not unmarshal headers json string : %v", err.Error())
        log.Error(message)
        return responseString, responseHttpStatusCode, errors.New(message)
    }

    if len(headersMap) != 0 {
        for key, value := range headersMap {
            valueStr, ok := value.(string)
            if !ok {
                continue
            }
            req.Header.Set(key, valueStr)
        }
    }

    req.Header.Set("Connection", "close")

    client := &http.Client{Transport: tr}

    resp, err := client.Do(req)
    if err != nil {
        message = fmt.Sprintf("http client could not execute a http request : %v", err.Error())
        log.Error(message)
        return responseString, responseHttpStatusCode, errors.New(message)
    }
    defer resp.Body.Close()

    body, err := ioutil.ReadAll(resp.Body)
    if err != nil {
        message = fmt.Sprintf("could not read http response body : %v", err.Error())
        log.Error(message)
        return responseString, responseHttpStatusCode, errors.New(message)
    }
    // convert body to string
    responseString = string(body)
    responseHttpStatusCode = resp.StatusCode
    return responseString, responseHttpStatusCode, nil
}

/*
Refer to this : https://gorest.co.in/
*/

func main() {

    randomStr := RandStringRunes(5)

    // --------- user-case-1 : get list of users -------------

    log.Printf("@ GET USERS (HTTP GET) ...")

    headers := fmt.Sprintf(`{
        "Authorization":"Bearer WHT469Z2H7EQ9TFUNMSPHAMPF9JBV<REDACTED>", 
        "Content-Type" : "application/json",
        "Accept" : "application/json"
    }`)
    request := RequestMap{
        URL:           "https://gorest.co.in/public/v2/users?page=1",
        Payload:       "",
        RequestMethod: GET,
        Headers:       headers,
        ProxyURL:      "",
    }
    response, responseStatusCode, err := request.HTTPRequest()
    if err != nil {
        log.Print(err)
        return
    }
    log.Printf("response : %v", response)
    log.Printf("responseStatusCode : %v", responseStatusCode)

    // --------- user-case-2 : create user -------------

    log.Printf("@ CREATE USER (HTTP POST) ...")

    payload := fmt.Sprintf(`{"name":"Linus Torvalds", "gender":"male", "email":"linus.torvalds@%v.com", "status":"active"}`, randomStr)

    log.Printf("payload : %v", payload)

    request = RequestMap{
        URL:           "https://gorest.co.in/public/v2/users",
        Payload:       payload,
        RequestMethod: POST,
        Headers:       headers,
        ProxyURL:      "",
    }

    response, responseStatusCode, err = request.HTTPRequest()
    if err != nil {
        log.Print(err)
        return
    }
    log.Printf("response : %v", response)
    log.Printf("responseStatusCode : %v", responseStatusCode)

    var jsonMap map[string]interface{}
    err = json.Unmarshal([]byte(response), &jsonMap)
    if err != nil {
        log.Errorf("could not convert response (string) to json map : %v", err.Error())
        return
    }

    log.Printf("jsonMap : %v", jsonMap)

    userID := jsonMap["id"].(float64)

    log.Printf("userID : (%v)", userID)

    // --------- user-case-3 : update/patch user -------------

    randomStr = RandStringRunes(5)

    log.Printf("@ UDPATE (HTTP PATCH) USER ...")

    payloadMap := make(map[string]string)
    payloadMap["name"] = "Linus Torvalds (NEW)"
    payloadMap["gender"] = "male"
    payloadMap["email"] = fmt.Sprintf(`linux-torvalds@%v.com`, randomStr)
    payloadMap["status"] = "active"

    headersMap := make(map[string]string)
    headersMap["Authorization"] = "Bearer WHT469Z2H7EQ9TFUNMSPHAMPF9JBV<REDACTED>"
    headersMap["Content-Type"] = "application/json"
    headersMap["Accept"] = "application/json"

    userURL := fmt.Sprintf(`https://gorest.co.in/public/v2/users/%v`, userID)

    log.Printf("userURL %v", userURL)

    request = RequestMap{
        URL:           userURL,
        Payload:       payloadMap,
        RequestMethod: PATCH,
        Headers:       headersMap,
        ProxyURL:      "",
    }

    response, responseStatusCode, err = request.HTTPRequest()
    if err != nil {
        log.Print(err)
        return
    }
    log.Printf("response : %v", response)
    log.Printf("responseStatusCode : %v", responseStatusCode)

    // --------- user-case-3 : delete user -------------

    log.Printf("@ DELETE (HTTP DELETE) USER ...")

    request = RequestMap{
        URL:           userURL,
        Payload:       payloadMap,
        RequestMethod: DELETE,
        Headers:       headersMap,
        ProxyURL:      "",
    }

    response, responseStatusCode, err = request.HTTPRequest()
    if err != nil {
        log.Print(err)
        return
    }
    log.Printf("response : %v", response)
    log.Printf("responseStatusCode : %v", responseStatusCode)
}
```

Output

```bash
# go run main.go
INFO[0000] @ GET USERS (HTTP GET) ...
INFO[0000] URL : https://gorest.co.in/public/v2/users?page=1
INFO[0000] Payload :
INFO[0000] RequestMethod : GET
INFO[0000] Headers : {
        "Authorization":"Bearer WHT469Z2H7EQ9TFUNMSPHAMPF9JBV<REDACTED>",
        "Content-Type" : "application/json",
        "Accept" : "application/json"
    }
INFO[0000] headers is a valid JSON STRING
INFO[0000] payload is a valid JSON string
INFO[0001] response : [{"id":5313,"name":"Linus Torvalds","email":"linus.torvalds@whUTo.com","gender":"male","status":"active"},{"id":5312,"name":"Linus Torvalds","email":"linus.torvalds@HQwWI.com","gender":"male","status":"active"},{"id":5309,"name":"Linus Torvalds","email":"linus.torvalds@wPVTR.com","gender":"male","status":"active"},{"id":5307,"name":"Linus Torvalds","email":"linus.torvalds@nPqFq.com","gender":"male","status":"active"},{"id":5290,"name":"Linus Torvalds","email":"linus.torvalds@antimicrosoft.com","gender":"male","status":"active"},{"id":3901,"name":"Damodara Bhat","email":"bhat_damodara@waters.co","gender":"female","status":"inactive"},{"id":3893,"name":"Chidaatma Iyengar I","email":"i_iyengar_chidaatma@king.io","gender":"male","status":"active"},{"id":3891,"name":"Rev. Brahmabrata Patil","email":"brahmabrata_patil_rev@bahringer.info","gender":"male","status":"inactive"},{"id":3890,"name":"Msgr. Atreyi Gowda","email":"atreyi_msgr_gowda@barton.com","gender":"male","status":"active"},{"id":3889,"name":"Balaaditya Joshi Jr.","email":"balaaditya_joshi_jr@ratke-oreilly.info","gender":"female","status":"active"},{"id":3888,"name":"Aasha Kocchar","email":"kocchar_aasha@funk.com","gender":"female","status":"active"},{"id":3887,"name":"Ramesh Ahuja DVM","email":"dvm_ahuja_ramesh@west.biz","gender":"male","status":"inactive"},{"id":3886,"name":"Manjusha Kakkar CPA","email":"kakkar_cpa_manjusha@reichert-barrows.io","gender":"male","status":"active"},{"id":3884,"name":"Tanushri Iyer","email":"iyer_tanushri@renner.name","gender":"male","status":"inactive"},{"id":3883,"name":"Niro Verma","email":"niro_verma@nicolas.name","gender":"male","status":"inactive"},{"id":3882,"name":"Devagya Tandon","email":"devagya_tandon@bosco.org","gender":"female","status":"active"},{"id":3881,"name":"Mani Pilla","email":"mani_pilla@kilback.name","gender":"female","status":"inactive"},{"id":3879,"name":"Dhyaneshwar Desai","email":"desai_dhyaneshwar@lueilwitz.co","gender":"female","status":"active"},{"id":3878,"name":"Ankal Chopra","email":"chopra_ankal@olson-schaden.com","gender":"female","status":"inactive"},{"id":3876,"name":"Gotum Shukla","email":"shukla_gotum@mcclure.com","gender":"male","status":"inactive"}]
INFO[0001] responseStatusCode : 200
INFO[0001] @ CREATE USER (HTTP POST) ...
INFO[0001] payload : {"name":"Linus Torvalds", "gender":"male", "email":"linus.torvalds@DGYIc.com", "status":"active"}
INFO[0001] URL : https://gorest.co.in/public/v2/users
INFO[0001] Payload : {"name":"Linus Torvalds", "gender":"male", "email":"linus.torvalds@DGYIc.com", "status":"active"}
INFO[0001] RequestMethod : POST
INFO[0001] Headers : {
        "Authorization":"Bearer WHT469Z2H7EQ9TFUNMSPHAMPF9JBV<REDACTED>",
        "Content-Type" : "application/json",
        "Accept" : "application/json"
    }
INFO[0001] headers is a valid JSON STRING
INFO[0001] payload is a valid JSON string
INFO[0002] response : {"id":5315,"name":"Linus Torvalds","email":"linus.torvalds@DGYIc.com","gender":"male","status":"active"}
INFO[0002] responseStatusCode : 201
INFO[0002] jsonMap : map[email:linus.torvalds@DGYIc.com gender:male id:5315 name:Linus Torvalds status:active]
INFO[0002] userID : (5315)
INFO[0002] @ UDPATE (HTTP PATCH) USER ...
INFO[0002] userURL https://gorest.co.in/public/v2/users/5315
INFO[0002] URL : https://gorest.co.in/public/v2/users/5315
INFO[0002] Payload : map[email:linux-torvalds@NLOgj.com gender:male name:Linus Torvalds (NEW) status:active]
INFO[0002] RequestMethod : PATCH
INFO[0002] Headers : map[Accept:application/json Authorization:Bearer WHT469Z2H7EQ9TFUNMSPHAMPF9JBV<REDACTED> Content-Type:application/json]
INFO[0002] headers is a valid map
INFO[0002] payload is a valid map
INFO[0002] payloadStr : {"email":"linux-torvalds@NLOgj.com","gender":"male","name":"Linus Torvalds (NEW)","status":"active"}
INFO[0003] response : {"email":"linux-torvalds@NLOgj.com","name":"Linus Torvalds (NEW)","gender":"male","status":"active","id":5315}
INFO[0003] responseStatusCode : 200
INFO[0003] @ DELETE (HTTP DELETE) USER ...
INFO[0003] URL : https://gorest.co.in/public/v2/users/5315
INFO[0003] Payload : map[email:linux-torvalds@NLOgj.com gender:male name:Linus Torvalds (NEW) status:active]
INFO[0003] RequestMethod : DELETE
INFO[0003] Headers : map[Accept:application/json Authorization:Bearer WHT469Z2H7EQ9TFUNMSPHAMPF9JBV<REDACTED> Content-Type:application/json]
INFO[0003] headers is a valid map
INFO[0003] payload is a valid map
INFO[0003] payloadStr : {"email":"linux-torvalds@NLOgj.com","gender":"male","name":"Linus Torvalds (NEW)","status":"active"}
INFO[0004] response :
INFO[0004] responseStatusCode : 204
```

#### [Generic HTTP Request V2](#generic-http-request-v2)

```go
package main

import (
    "bytes"
    "crypto/tls"
    "encoding/json"
    "errors"
    "fmt"
    "io"
    "math/rand"
    "net"
    "net/http"
    "net/url"
    "reflect"
    "time"

    log "github.com/sirupsen/logrus"
)

type HttpRequestType int64

var (
    HttpTLSTimeOut    time.Duration = 10 // 10 seconds
    MyHttpProxyServer string        = "https://my-proxy-server.company.com:5050"
)

var letterRunes = []rune("abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ")

const (
    GET HttpRequestType = iota
    HEAD
    POST
    PUT
    PATCH
    DELETE
)

type RequestMap struct {
    URL           string
    Payload       interface{} // you are expected to set this as a string or map[string]interface{}
    RequestMethod HttpRequestType
    Headers       interface{} // you are expected to set this as a string or map[string]string
    ProxyURL      string
}

//--------------------------------------------------------------------------------------------------------------------

type String string

type Map map[string]interface{}

type IString interface {
    GetMap() (Map, error)
}

type IMap interface {
    GetString() (String, error)
}

func (s String) GetMap() (Map, error) {
    var msg string
    var jsonMap Map
    err := json.Unmarshal([]byte(s), &jsonMap)
    if err != nil {
        msg = fmt.Sprintf("could not Unmarshal (json.Unmarshal) []bytes(s) to -> Map : %v", err.Error())
        log.Printf(msg)
        return nil, errors.New(msg)
    }
    return jsonMap, nil
}

func (m Map) GetString() (String, error) {
    msg := ""
    dataBytes, err := json.Marshal(m)
    if err != nil {
        msg = fmt.Sprintf("could not marshal (json.Marshal) to -> []bytes  : %v", err.Error())
        log.Printf(msg)
        return "", errors.New(msg)
    }
    dataBytesStr := string(dataBytes)
    return String(dataBytesStr), nil
}

//--------------------------------------------------------------------------------------------------------------------

func (r HttpRequestType) String() string {
    switch r {
    case GET:
        return "GET"
    case HEAD:
        return "HEAD"
    case POST:
        return "POST"
    case PUT:
        return "PUT"
    case PATCH:
        return "PATCH"
    case DELETE:
        return "DELETE"
    }
    return "UNKNOWN"
}

type IHTTPRequest interface {
    HTTPRequest() (string, *http.Response, error)
}

type IHTTPRequestMap interface {
    HTTPRequest() (string, *http.Response, error)
}

//---------------------------------------------------------------------------

func IsMap(data interface{}) bool {
    if data == nil {
        return false
    } else {
        return reflect.ValueOf(data).Kind() == reflect.Map
    }
}

func IsString(data interface{}) bool {
    if data == nil {
        return false
    } else {
        return reflect.ValueOf(data).Kind() == reflect.String
    }
}

func IsStringJSON(str string) bool {
    var js json.RawMessage
    return json.Unmarshal([]byte(str), &js) == nil
}

func GetJsonData(data interface{}) (string, error) {
    returnStr := ""
    if IsString(data) {
        if data == "" {
            return "", nil
        } else {
            if IsStringJSON(data.(string)) {
                return data.(string), nil
            } else {
                return returnStr, errors.New("data is not json string")
            }
        }
    } else if IsMap(data) {
        dataBytes, err := json.Marshal(data)
        if err != nil {
            return returnStr, errors.New("data is not json string (json.Marshal failed)")
        }
        dataBytesStr := string(dataBytes)
        return dataBytesStr, nil
    } else {
        return returnStr, errors.New("data is neither a json string not a map[string]interface{}")
    }
}

//---------------------------------------------------------------------------

func initRand() {
    rand.Seed(time.Now().UnixNano())
}

func RandStringRunes(n int) string {
    initRand()
    b := make([]rune, n)
    for i := range b {
        b[i] = letterRunes[rand.Intn(len(letterRunes))]
    }
    return string(b)
}

//---------------------------------------------------------------------------

func (r RequestMap) HTTPRequest() (string, int, error) {
    log.Printf("URL : %v", r.URL)
    log.Printf("Payload : %v", r.Payload)
    log.Printf("RequestMethod : %v", r.RequestMethod)
    log.Printf("Headers : %v", r.Headers)

    responseString := ""
    responseHttpStatusCode := -1

    //var headersMap map[string]interface{}
    var req *http.Request
    var err error
    var message string

    var tr *http.Transport

    var payloadStr string

    // ---- r.Payload : should be a JSON string or map[string]interface{} ------

    payloadStr, err = GetJsonData(r.Payload)
    if err != nil {
        message = fmt.Sprintf("r.Payload : %v", err.Error())
        log.Error(message)
        return responseString, responseHttpStatusCode, errors.New(message)
    }

    tr = CreateHttpTransport(r.ProxyURL)

    req, err = CreateHttpRequest(r.RequestMethod, payloadStr, r.URL)
    if err != nil {
        message = fmt.Sprintf("forming http request error : %v", err.Error())
        log.Printf(message)
        return responseString, responseHttpStatusCode, errors.New(message)
    }

    // ---- r.Headers : should be a JSON string or map[string]string ------

    err = SetHeaders(r.Headers, req)
    if err != nil {
        message = fmt.Sprintf("error in setting headers : %v", err.Error())
        log.Printf(message)
        return responseString, responseHttpStatusCode, errors.New(message)
    }

    responseString, responseHttpStatusCode, err = PerformHttpRequest(req, tr)
    if err != nil {
        message = fmt.Sprintf("error in HttpRequest : %v", err.Error())
        log.Printf(message)
        return responseString, responseHttpStatusCode, errors.New(message)
    }

    return responseString, responseHttpStatusCode, nil
}

func PerformHttpRequest(req *http.Request, tr *http.Transport) (responseString string, responseHttpStatusCode int, err error) {
    message := ""

    responseString = ""
    responseHttpStatusCode = -1
    err = nil

    client := &http.Client{Transport: tr}

    resp, err := client.Do(req)
    if err != nil {
        message = fmt.Sprintf("http client could not execute a http request : %v", err.Error())
        log.Error(message)
        return responseString, responseHttpStatusCode, errors.New(message)
    }
    defer func() {
        _ = resp.Body.Close()
    }()

    body, err := io.ReadAll(resp.Body)
    if err != nil {
        message = fmt.Sprintf("could not read http response body : %v", err.Error())
        log.Error(message)
        return responseString, responseHttpStatusCode, errors.New(message)
    }
    // convert body to string
    responseString = string(body)
    responseHttpStatusCode = resp.StatusCode
    return responseString, responseHttpStatusCode, nil
}

func CreateHttpRequest(httpRequestType HttpRequestType, jsonPayload string, httpURL string) (*http.Request, error) {
    var err error
    var req *http.Request
    message := ""

    if jsonPayload == "" {
        req, err = http.NewRequest(httpRequestType.String(), httpURL, nil)
        if err != nil {
            message = fmt.Sprintf("could not create a new http request : %v", err.Error())
            log.Error(message)
            return req, errors.New(message)
        }
    } else {
        req, err = http.NewRequest(httpRequestType.String(), httpURL, bytes.NewBuffer([]byte(jsonPayload)))
        if err != nil {
            message = fmt.Sprintf("could not create a new http request : %v", err.Error())
            log.Error(message)
            return req, errors.New(message)
        }
    }
    return req, nil
}

func CreateHttpTransport(proxyURL string) *http.Transport {
    var tr *http.Transport
    if proxyURL == "" {
        tr = &http.Transport{
            TLSClientConfig: &tls.Config{InsecureSkipVerify: true},
            DialContext: (&net.Dialer{
                Timeout:   0,
                KeepAlive: 0,
            }).DialContext,
            TLSHandshakeTimeout: HttpTLSTimeOut * time.Second,
        }
    } else {
        proxyUrl, _ := url.Parse(proxyURL)
        tr = &http.Transport{
            TLSClientConfig: &tls.Config{InsecureSkipVerify: true},
            DialContext: (&net.Dialer{
                Timeout:   0,
                KeepAlive: 0,
            }).DialContext,
            Proxy:               http.ProxyURL(proxyUrl),
            TLSHandshakeTimeout: HttpTLSTimeOut * time.Second,
        }
    }
    return tr
}

func SetHeaders(headers interface{}, req *http.Request) error {
    var headersMap map[string]interface{}
    message := ""
    headersStr, err := GetJsonData(headers)
    if err != nil {
        message = fmt.Sprintf("could not get json data from headers (interface{}) : %v", err.Error())
        log.Printf(message)
        return errors.New(message)
    }
    // no headers to set
    if headersStr == "" {
        return nil
    }

    err = json.Unmarshal([]byte(headersStr), &headersMap)
    if err != nil {
        message = fmt.Sprintf("could not unmarshal headers json string : %v", err.Error())
        log.Printf(message)
        return errors.New(message)
    }

    if len(headersMap) != 0 {
        for key, value := range headersMap {
            valueStr, ok := value.(string)
            if !ok {
                continue
            }
            req.Header.Set(key, valueStr)
        }
    }
    req.Header.Set("Connection", "close")
    return nil
}

/*
Refer to this : https://gorest.co.in/
*/

func main() {

    randomStr := RandStringRunes(5)

    var jsonMap map[string]interface{}

    // --------- user-case-1 : get list of users -------------

    log.Printf("@ GET USERS (HTTP GET) ...")

    // example of using string (json) -> for headers
    headers1 := fmt.Sprintf(`{
        "Authorization":"Bearer cf1bbab12c76f3ccc87d9b<REDACTED>"
        "Content-Type" : "application/json",
        "Accept" : "application/json"
    }`)

    request := RequestMap{
        URL:           "https://gorest.co.in/public/v2/users?page=1",
        Payload:       "",
        RequestMethod: GET,
        Headers:       headers1,
        ProxyURL:      "",
    }
    response, responseStatusCode, err := request.HTTPRequest()
    if err != nil {
        log.Print(err)
        return
    }
    log.Printf("response : %v", response)
    log.Printf("responseStatusCode : %v", responseStatusCode)

    // --------- user-case-2 : create user -------------

    log.Printf("@ CREATE USER (HTTP POST) ...")

    //---------------------------------------------------------------------------

    // example of using map[string]interface{} (json) -> for payload

    payload1 := make(map[string]interface{})
    payload1["name"] = "Linus"
    payload1["gender"] = "male"
    payload1["email"] = "linus.torvalds@foo.com"
    payload1["status"] = "active"
    payload1["age"] = 55

    log.Printf("payload1 : %v", payload1)

    // example of using map[string]interface{} (json) -> for headers

    headers2 := make(map[string]interface{})
    headers2["Authorization"] = "cf1bbab12c76f3ccc87d9b<REDACTED>"
    headers2["Content-Type"] = "application/json"
    headers2["Accept"] = "application/json"

    request = RequestMap{
        URL:           "https://gorest.co.in/public/v2/users",
        Payload:       payload1,
        RequestMethod: POST,
        Headers:       headers2,
        ProxyURL:      "",
    }

    response, responseStatusCode, err = request.HTTPRequest()
    if err != nil {
        log.Print(err)
        return
    }
    log.Printf("response : %v", response)
    log.Printf("responseStatusCode : %v", responseStatusCode)

    jsonMap = make(map[string]interface{})

    err = json.Unmarshal([]byte(response), &jsonMap)
    if err != nil {
        log.Errorf("could not convert response (string) to json map : %v", err.Error())
        return
    }

    log.Printf("jsonMap : %v", jsonMap)

    //---------------------------------------------------------------------------

    // example of using string (json) -> for payload

    payload2 := fmt.Sprintf(`{"name":"Linus Torvalds", "gender":"male", "email":"linus.torvalds@%v.com", "status":"active"}`, randomStr)

    log.Printf("payload2 : %v", payload2)

    request = RequestMap{
        URL:           "https://gorest.co.in/public/v2/users",
        Payload:       payload2,
        RequestMethod: POST,
        Headers:       headers1,
        ProxyURL:      "",
    }

    response, responseStatusCode, err = request.HTTPRequest()
    if err != nil {
        log.Print(err)
        return
    }
    log.Printf("response : %v", response)
    log.Printf("responseStatusCode : %v", responseStatusCode)

    jsonMap = make(map[string]interface{})

    err = json.Unmarshal([]byte(response), &jsonMap)
    if err != nil {
        log.Errorf("could not convert response (string) to json map : %v", err.Error())
        return
    }

    log.Printf("jsonMap : %v", jsonMap)

    userID := jsonMap["id"].(float64)

    log.Printf("userID : (%v)", userID)

    // --------- user-case-3 : update/patch user -------------

    randomStr = RandStringRunes(5)

    log.Printf("@ UDPATE (HTTP PATCH) USER ...")

    // example of using map[string]interface{} (json) -> for payload

    payloadMap := make(map[string]string)
    payloadMap["name"] = "Linus Torvalds (NEW)"
    payloadMap["gender"] = "male"
    payloadMap["email"] = fmt.Sprintf(`linux-torvalds@%v.com`, randomStr)
    payloadMap["status"] = "active"

    // example of using map[string]interface{} (json) -> for headers

    headersMap := make(map[string]string)
    headersMap["Authorization"] = "Bearer cf1bbab12c76f3ccc87d9b<REDACTED>"
    headersMap["Content-Type"] = "application/json"
    headersMap["Accept"] = "application/json"

    userURL := fmt.Sprintf(`https://gorest.co.in/public/v2/users/%v`, userID)

    log.Printf("userURL %v", userURL)

    request = RequestMap{
        URL:           userURL,
        Payload:       payloadMap,
        RequestMethod: PATCH,
        Headers:       headersMap,
        ProxyURL:      "",
    }

    response, responseStatusCode, err = request.HTTPRequest()
    if err != nil {
        log.Print(err)
        return
    }
    log.Printf("response : %v", response)
    log.Printf("responseStatusCode : %v", responseStatusCode)

    // --------- user-case-3 : delete user -------------

    log.Printf("@ DELETE (HTTP DELETE) USER ...")

    request = RequestMap{
        URL:           userURL,
        Payload:       payloadMap,
        RequestMethod: DELETE,
        Headers:       headersMap,
        ProxyURL:      "",
    }

    response, responseStatusCode, err = request.HTTPRequest()
    if err != nil {
        log.Print(err)
        return
    }
    log.Printf("response : %v", response)
    log.Printf("responseStatusCode : %v", responseStatusCode)
}
```

Output

```bash
❯ go run main.go
INFO[0000] @ GET USERS (HTTP GET) ...
INFO[0000] URL : https://gorest.co.in/public/v2/users?page=1
INFO[0000] Payload :
INFO[0000] RequestMethod : GET
INFO[0000] Headers : {
        "Authorization":"Bearer cf1bbab12c76f3ccc87d9b6ec940484<REDACTED>",
        "Content-Type" : "application/json",
        "Accept" : "application/json"
    }
INFO[0001] response : [{"id":6257,"name":"Gautam Verma","email":"verma_gautam@klocko.info","gender":"male","status":"active"},{"id":6256,"name":"Gajbaahu Mukhopadhyay","email":"mukhopadhyay_gajbaahu@cole.org","gender":"male","status":"active"},{"id":6252,"name":"Mr. Chakrika Arora","email":"chakrika_arora_mr@dubuque.com","gender":"female","status":"inactive"},{"id":6251,"name":"Shrishti Namboothiri","email":"shrishti_namboothiri@rutherford-oreilly.io","gender":"male","status":"inactive"},{"id":6250,"name":"Bhisham Guneta","email":"bhisham_guneta@heidenreich-dickinson.name","gender":"male","status":"inactive"},{"id":6249,"name":"Ananta Bharadwaj","email":"bharadwaj_ananta@franecki.info","gender":"female","status":"inactive"},{"id":6248,"name":"Adinath Devar IV","email":"iv_devar_adinath@reichert-jast.name","gender":"male","status":"active"},{"id":6247,"name":"Vidhur Pothuvaal","email":"pothuvaal_vidhur@dibbert.org","gender":"female","status":"active"},{"id":6246,"name":"Shivakari Saini","email":"shivakari_saini@schultz-mcdermott.name","gender":"female","status":"inactive"},{"id":6245,"name":"Rev. Dandapaani Banerjee","email":"banerjee_rev_dandapaani@koss.info","gender":"male","status":"active"}]
INFO[0001] responseStatusCode : 200
INFO[0001] @ CREATE USER (HTTP POST) ...
INFO[0001] payload1 : map[age:55 email:linus.torvalds@foo.com gender:male name:Linus status:active]
INFO[0001] URL : https://gorest.co.in/public/v2/users
INFO[0001] Payload : map[age:55 email:linus.torvalds@foo.com gender:male name:Linus status:active]
INFO[0001] RequestMethod : POST
INFO[0001] Headers : map[Accept:application/json Authorization:cf1bbab12c76f3ccc87d9b6ec940484<REDACTED> Content-Type:application/json]
INFO[0001] response : {"message":"Authentication failed"}
INFO[0001] responseStatusCode : 401
INFO[0001] jsonMap : map[message:Authentication failed]
INFO[0001] payload2 : {"name":"Linus Torvalds", "gender":"male", "email":"linus.torvalds@wMESY.com", "status":"active"}
INFO[0001] URL : https://gorest.co.in/public/v2/users
INFO[0001] Payload : {"name":"Linus Torvalds", "gender":"male", "email":"linus.torvalds@wMESY.com", "status":"active"}
INFO[0001] RequestMethod : POST
INFO[0001] Headers : {
        "Authorization":"Bearer cf1bbab12c76f3ccc87d9b6ec940484<REDACTED>",
        "Content-Type" : "application/json",
        "Accept" : "application/json"
    }
INFO[0001] response : {"id":6378,"name":"Linus Torvalds","email":"linus.torvalds@wMESY.com","gender":"male","status":"active"}
INFO[0001] responseStatusCode : 201
INFO[0001] jsonMap : map[email:linus.torvalds@wMESY.com gender:male id:6378 name:Linus Torvalds status:active]
INFO[0001] userID : (6378)
INFO[0001] @ UDPATE (HTTP PATCH) USER ...
INFO[0001] userURL https://gorest.co.in/public/v2/users/6378
INFO[0001] URL : https://gorest.co.in/public/v2/users/6378
INFO[0001] Payload : map[email:linux-torvalds@UmTCK.com gender:male name:Linus Torvalds (NEW) status:active]
INFO[0001] RequestMethod : PATCH
INFO[0001] Headers : map[Accept:application/json Authorization:Bearer cf1bbab12c76f3ccc87d9b6ec940484<REDACTED> Content-Type:application/json]
INFO[0002] response : {"email":"linux-torvalds@UmTCK.com","name":"Linus Torvalds (NEW)","gender":"male","status":"active","id":6378}
INFO[0002] responseStatusCode : 200
INFO[0002] @ DELETE (HTTP DELETE) USER ...
INFO[0002] URL : https://gorest.co.in/public/v2/users/6378
INFO[0002] Payload : map[email:linux-torvalds@UmTCK.com gender:male name:Linus Torvalds (NEW) status:active]
INFO[0002] RequestMethod : DELETE
INFO[0002] Headers : map[Accept:application/json Authorization:Bearer cf1bbab12c76f3ccc87d9b6ec940484<REDACTED> Content-Type:application/json]
INFO[0003] response :
INFO[0003] responseStatusCode : 204
```

#### [Panic And Recover](#panic-and-recover)

```golang
package main

import (
    "encoding/json"
    "errors"
    "fmt"
    "io/ioutil"
    "log"
    "os"
)

// DO CAUSE PANIC !
// This is just an example to show recover()

func mayPanic() {
    panic("a problem")
}

func readFile(myFile string) (data interface{}, err error) {
    message := ""
    fileBytes, err := ioutil.ReadFile(myFile)
    if err != nil {
        message = fmt.Sprintf("readFile() : there was an error reading the file : (%v) : %v", myFile, err.Error())
        log.Printf(message)
        return data, errors.New(message)
    }

    err = json.Unmarshal(fileBytes, &data)
    if err != nil {
        message = fmt.Sprintf("readFile() : there was an error unmarshalling json for the file : (%v) : %v", myFile, err.Error())
        log.Printf(message)
        return data, errors.New(message)
    }
    return data, nil

}

func doStuff() (data map[string]string, err error) {
    defer func() {
        if r := recover(); r != nil {
            log.Printf("Recovered in doStuff() Error: %v", r)
            // find out exactly what the error was and set err
            switch x := r.(type) {
            case string:
                log.Println("r.type == string")
                err = errors.New(x)
            case error:
                log.Println("r.type == error")
                err = x
            default:
                log.Println("r.type == default")
                err = errors.New("defer : unknown panic in")
            }
        }
    }()

    // initialize data
    data = make(map[string]string)

    data["name"] = "giridhar"
    data["company"] = "google"

    myData, err := readFile("my_data_.json")
    if err != nil {
        panic(err)
    }
    log.Printf("file was read successfully.")
    log.Printf("file contents:")
    log.Printf("%v", myData)

    // //////////// pretty print the JSON data | start ///////////////////////////

    dataBytes, err := json.MarshalIndent(myData, "", "    ")
    if err != nil {
        panic(err)
        //log.Printf("could not pretty pring the json data : %v", err.Error())
        //os.Exit(1)
    }
    fmt.Printf("\npretty json:\n")
    fmt.Printf("\n\n%v\n\n", string(dataBytes))

    // //////////// pretty print the JSON data | end ///////////////////////////

    return data, nil
}

func main() {
    someData, err := doStuff()
    if err != nil {
        log.Printf("main() : %v", err.Error())
        os.Exit(1)
    }
    log.Printf("someData : %v", someData)
}
```

Sample JSON File : `my_data.json` (Change It To Introduce Errors In The above code)

```json
[
  {
    "_id": "62195a4394aa157c5d182c13",
    "index": 0,
    "guid": "10b56e50-048f-4a53-8ef3-6ea1a4a2401f",
    "isActive": false,
    "balance": "$3,108.51",
    "picture": "http://placehold.it/32x32",
    "age": 37,
    "eyeColor": "blue",
    "name": "Pennington Hendrix",
    "gender": "male",
    "company": "DAIDO",
    "email": "penningtonhendrix@daido.com",
    "phone": "+1 (943) 556-2230",
    "address": "476 Gerritsen Avenue, Zarephath, South Dakota, 3797",
    "about": "Aute reprehenderit ipsum nisi pariatur veniam deserunt qui laborum. Nisi id pariatur mollit et velit minim occaecat Lorem sint. Do consequat officia qui magna sit eiusmod excepteur irure consequat. Velit est irure ad pariatur cupidatat proident cupidatat deserunt. Duis ex enim voluptate deserunt in commodo. Esse magna eiusmod aliquip quis irure sunt sit culpa officia voluptate eu nisi ad adipisicing. Velit ut minim est reprehenderit in esse consectetur ut irure.\r\n",
    "registered": "2015-05-07T05:10:07 +07:00",
    "latitude": 31.067813,
    "longitude": 68.588042,
    "tags": [
      "id",
      "eiusmod",
      "sint"
    ],
    "friends": [
      {
        "id": 0,
        "name": "Wooten Bartlett"
      }
    ],
    "greeting": "Hello, Pennington Hendrix! You have 1 unread messages.",
    "favoriteFruit": "apple"
  }
]
```

#### [User Prompts And Inputs](#user-prompts-and-inputs)

How to implement text input prompt

```golang
package main

import (
    "bufio"
    "fmt"
    "os"
    "strings"
)

// StringPrompt asks for a string value using the label
func StringPrompt(label string) string {
    var s string
    r := bufio.NewReader(os.Stdin)
    for {
        fmt.Fprint(os.Stderr, label+" ")
        s, _ = r.ReadString('\n')
        if s != "" {
            break
        }
    }
    return strings.TrimSpace(s)
}

func main() {
    name := StringPrompt("What is your name?")
    fmt.Printf("Hello, %s!\n", name)
}
```

How to implement password input prompt


```golang
package main

import (
    "fmt"
    "os"
    "syscall"

    "golang.org/x/term"
)

// PasswordPrompt asks for a string value using the label.
// The entered value will not be displayed on the screen
// while typing.
func PasswordPrompt(label string) string {
    var s string
    for {
        fmt.Fprint(os.Stderr, label+" ")
        b, _ := term.ReadPassword(int(syscall.Stdin))
        s = string(b)
        if s != "" {
            break
        }
    }
    fmt.Println()
    return s
}

func main() {
    password := PasswordPrompt("What is your password?")
    fmt.Printf("Oh, I see! Your password is %q\n", password)
}
```

How to implement Yes/No prompt

```golang
package main

import (
    "bufio"
    "fmt"
    "os"
    "strings"
)

// YesNoPrompt asks yes/no questions using the label.
func YesNoPrompt(label string, def bool) bool {
    choices := "Y/n"
    if !def {
        choices = "y/N"
    }

    r := bufio.NewReader(os.Stdin)
    var s string

    for {
        fmt.Fprintf(os.Stderr, "%s (%s) ", label, choices)
        s, _ = r.ReadString('\n')
        s = strings.TrimSpace(s)
        if s == "" {
            return def
        }
        s = strings.ToLower(s)
        if s == "y" || s == "yes" {
            return true
        }
        if s == "n" || s == "no" {
            return false
        }
    }
}

func main() {
    ok := YesNoPrompt("Dev.to is awesome!", true)
    if ok {
        fmt.Println("Agree!")
    } else {
        fmt.Println("Huh?")
    }
}
```

How to implement interactive checkboxes

```golang
package main

import (
    "fmt"
    "strings"

    "github.com/AlecAivazis/survey/v2"
)

func Checkboxes(label string, opts []string) []string {
    res := []string{}
    prompt := &survey.MultiSelect{
        Message: label,
        Options: opts,
    }
    survey.AskOne(prompt, &res)

    return res
}

func main() {
    answers := Checkboxes(
        "Which are your favourite programming languages?",
        []string{
            "C",
            "Python",
            "Java",
            "C++",
            "C#",
            "Visual Basic",
            "JavaScript",
            "PHP",
            "Assembly Language",
            "SQL",
            "Groovy",
            "Classic Visual Basic",
            "Fortran",
            "R",
            "Ruby",
            "Swift",
            "MATLAB",
            "Go",
            "Prolog",
            "Perl",
        },
    )
    s := strings.Join(answers, ", ")
    fmt.Println("Oh, I see! You like", s)
}
```

#### [Reading YAML](#reading-yaml)

`main.go`

```golang
package main

import (
    yaml "gopkg.in/yaml.v3"
    "io/ioutil"
    "log"
)

func main() {

    yfile, err := ioutil.ReadFile("test.yaml")

    if err != nil {

        log.Fatal(err)
    }

    data := make(map[string]interface{})

    err2 := yaml.Unmarshal(yfile, &data)
    if err2 != nil {
        log.Fatal(err2)
    }

    for key, value := range data {
        dbName := key
        log.Printf("dbName : %v", dbName)
        for key2, value2 := range value.(map[string]interface{}) {
            tableName := key2
            log.Printf("tableName : %v", tableName)
            tableItems := value2.([]interface{})
            for _, tableItem := range tableItems {
                log.Printf("tableItem : %v", tableItem)
            }
        }
    }
}

/*
Output

# go run main.go
2022/03/15 14:56:52 dbName : db1
2022/03/15 14:56:52 tableName : schema1.table1
2022/03/15 14:56:52 tableItem : col1
2022/03/15 14:56:52 tableItem : col2
2022/03/15 14:56:52 tableName : schema2.table2
2022/03/15 14:56:52 tableItem : col3
2022/03/15 14:56:52 tableItem : col4
2022/03/15 14:56:52 tableItem : col5
2022/03/15 14:56:52 dbName : db2
2022/03/15 14:56:52 tableName : schema2.table4
2022/03/15 14:56:52 tableItem : col20
2022/03/15 14:56:52 tableItem : col21
2022/03/15 14:56:52 tableItem : col22
2022/03/15 14:56:52 tableName : schema1.table3
2022/03/15 14:56:52 tableItem : col10
2022/03/15 14:56:52 tableItem : col11
*/
```

`test.yaml`

```yaml
---
db1:
  schema1.table1:
    - col1
    - col2
  schema2.table2:
    - col3
    - col4
    - col5

db2:
  schema1.table3:
    - col10
    - col11
  schema2.table4:
    - col20
    - col21
    - col22
```

#### [MongoDB Context With Cancel](#mongodb-context-with-cancel)

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

    ctx, cancel := context.WithTimeout(context.Background(),
        30*time.Second)
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

#### [Encoding And Decoding](#encoding-and-decoding)

```go
package main

import (
    "bytes"
    b64 "encoding/base64"
    "encoding/gob"
    "encoding/json"
    "errors"
    "fmt"
    "log"
)

// Reference
// Decode : https://go.dev/play/p/sye-MyuD110
// Encode : https://go.dev/play/p/GdEEDCa6V2U

// Working Example:
// https://go.dev/play/p/bMNZUXcfc7E

type Map struct {
    Data map[string]interface{}
}

type EncodedData struct {
    EncodedString string
}

type MapInterface interface {
    GetByteArray() ([]byte, error)
    Base64Encode() (string, error)
    PrettyPrint()
}

type EncodedDataInterface interface {
    Base64Decode() (map[string]interface{}, error)
}

// ------------------------------------------------------------------------------

func (encodedData EncodedData) Base64Decode() (map[string]interface{}, error) {
    msg := ""
    sDec, err := b64.StdEncoding.DecodeString(encodedData.EncodedString)
    if err != nil {
        msg = fmt.Sprintf("error : Base64Decode : could not perform a base64 decode : %v", err.Error())
        return nil, errors.New(msg)
    }

    myData, err := ConvertToInterface(sDec)
    if err != nil {
        msg = fmt.Sprintf("error : Base64Decode : could not convert array of bytes -> interface{} : %v", err.Error())
        return nil, errors.New(msg)
    }
    return myData, nil
}

// ------------------------------------------------------------------------------

func (data Map) GetByteArray() ([]byte, error) {
    msg := ""
    var buf bytes.Buffer
    enc := gob.NewEncoder(&buf)
    err := enc.Encode(data.Data)
    if err != nil {
        msg = fmt.Sprintf("error : GetBytes() : could not encode data : %v", err.Error())
        return nil, errors.New(msg)
    }
    return buf.Bytes(), nil
}

func (data Map) Base64Encode() (string, error) {
    msg := ""
    byteArray, err := data.GetByteArray()
    if err != nil {
        msg = fmt.Sprintf("error : GetMap() : could not convert data (map) to byte[] : %v", err.Error())
        return "", errors.New(msg)
    }
    sEnc := b64.StdEncoding.EncodeToString(byteArray)
    return sEnc, nil
}

func (data Map) PrettyPrint() {
    dataBytes, err := json.MarshalIndent(data.Data, "", "    ")
    if err != nil {
        log.Printf("error : could not MarshalIndent json : %v", err.Error())
        return
    }
    fmt.Printf("\n%v\n\n", string(dataBytes))
}

func ConvertToInterface(data []byte) (map[string]interface{}, error) {
    msg := ""
    buf := bytes.NewBuffer(data)
    dec := gob.NewDecoder(buf)
    myData := make(map[string]interface{})
    if err := dec.Decode(&myData); err != nil {
        msg = fmt.Sprintf("error : ConvertToInterface : could not convert data (array of bytes) to interface{} : %v", err.Error())
        return nil, errors.New(msg)
    }
    return myData, nil
}

func PrettyPrintData(data interface{}) {
    dataBytes, err := json.MarshalIndent(data, "", "    ")
    if err != nil {
        log.Printf("error : could not MarshalIndent json : %v", err.Error())
        return
    }
    fmt.Printf("\n%v\n\n", string(dataBytes))
}

func main() {

    log.Printf("Standard & URL : Encoding/Decoding")

    log.Println()

    // ----------------------------------------------------------------------

    data := "https://www.some-host.com/data?param1='{abc123!?$*&()-=@~}'"
    
    log.Printf("@ Standard Encoding : Data To Encode : %v", data)

    log.Println()

    sEnc := b64.StdEncoding.EncodeToString([]byte(data))
    log.Printf("@ Base-64 Standard Encoded String : %v", sEnc)

    sDec, _ := b64.StdEncoding.DecodeString(sEnc)
    decodedStr := string(sDec)
    log.Printf("@ Base-64 Standard Decoded String : %v", decodedStr)

    log.Println()

    uEnc := b64.URLEncoding.EncodeToString([]byte(data))
    log.Printf("@ Base-64 URL Encoded String : %v", uEnc)

    uDec, _ := b64.URLEncoding.DecodeString(uEnc)
    log.Printf("@ Base-64 URL Decoded String : %v", string(uDec))

    log.Println()

    // ----------------------------------------------------------------------

    log.Printf("Encoding/Decoding of map[string]interface{}")

    log.Println()

    // ----------------------------------------------------------------------

    myData1 := make(map[string]interface{})
    myData1["hello"] = "world"
    myData1["test"] = []int64{1, 2, 3, 4}
    myData1["x"] = 4.556

    // ----------------------------------------------------------------------

    log.Printf("Data To Encode : %v", myData1)

    log.Println()

    d1 := Map{Data: myData1}

    dataEncoded, _ := d1.Base64Encode()

    log.Printf("> dataEncoded : %v", dataEncoded)

    d2 := EncodedData{EncodedString: dataEncoded}

    myMap, _ := d2.Base64Decode()

    log.Printf("> After Decoding : myMap :")

    PrettyPrintData(myMap)

}
```

#### Output

```bash
2022/08/19 10:08:12 Standard & URL : Encoding/Decoding
2022/08/19 10:08:12
2022/08/19 10:08:12 @ Standard Encoding : Data To Encode : https://www.some-host.com/data?param1='{abc123!?$*&()-=@~}'
2022/08/19 10:08:12
2022/08/19 10:08:12 @ Base-64 Standard Encoded String : aHR0cHM6Ly93d3cuc29tZS1ob3N0LmNvbS9kYXRhP3BhcmFtMT0ne2FiYzEyMyE/JComKCktPUB+fSc=
2022/08/19 10:08:12 @ Base-64 Standard Decoded String : https://www.some-host.com/data?param1='{abc123!?$*&()-=@~}'
2022/08/19 10:08:12
2022/08/19 10:08:12 @ Base-64 URL Encoded String : aHR0cHM6Ly93d3cuc29tZS1ob3N0LmNvbS9kYXRhP3BhcmFtMT0ne2FiYzEyMyE_JComKCktPUB-fSc=
2022/08/19 10:08:12 @ Base-64 URL Decoded String : https://www.some-host.com/data?param1='{abc123!?$*&()-=@~}'
2022/08/19 10:08:12
2022/08/19 10:08:12 Encoding/Decoding of map[string]interface{}
2022/08/19 10:08:12
2022/08/19 10:08:12 Data To Encode : map[hello:world test:[1 2 3 4] x:4.556]
2022/08/19 10:08:12
2022/08/19 10:08:12 > dataEncoded : Dv+BBAEC/4IAAQwBEAAAM/+CAAMFaGVsbG8Gc3RyaW5nDAcABXdvcmxkBHRlc3QHW11pbnQ2NP+DAgEC/4QAAQQAAB//hAYABAIEBggBeAdmbG9hdDY0CAoA+NNNYhBYORJA
2022/08/19 10:08:12 > After Decoding : myMap :

{
    "hello": "world",
    "test": [
        1,
        2,
        3,
        4
    ],
    "x": 4.556
}
```

#### [HTTP File Upload Client And Server](#http-file-upload-client-and-server)

How To Run `Server` (Assuming Client/Server Is On 'localhost')

```bash
go run main.go -destination_directory="/var/www/html/files"
```

How To Run `Client` (Assuming Client/Server Is On 'localhost')

```bash
go run main.go -file="random-file.txt" -upload_url="http://localhost:1234/upload"
```

`Server` (main.go)

```go
package main

import (
    "flag"
    "fmt"
    "io/ioutil"
    "log"
    "net/http"
)

var DestinationDir string

func uploadFile(w http.ResponseWriter, r *http.Request) {
    log.Println("File Upload Endpoint Hit")

    // Parse our multipart form, 10 << 20 specifies a maximum -> upload of 10 MB files.

    // 314572800 = 300MB
    err := r.ParseMultipartForm(314572800)
    if err != nil {
        log.Printf("error in parsing of multipart-form : %v", err.Error())
        return
    }

    // FormFile returns the first file for the given key `myFile`
    // it also returns the FileHeader so that we can get the Filename,
    // the Header and the size of the file
    file, handler, err := r.FormFile("myFile")
    if err != nil {
        log.Printf("Error Retrieving the form file (expecting 'myFile') : %v", err.Error())
        return
    }
    defer func() {
        _ = file.Close()
    }()
    log.Printf("Uploaded File : %+v\n", handler.Filename)
    log.Printf("File Size     : %+v\n", handler.Size)
    log.Printf("MIME Header   : %+v\n", handler.Header)

    // read all the contents of our uploaded file into a
    // byte array
    fileBytes, err := ioutil.ReadAll(file)
    if err != nil {
        log.Printf("Error in reading the file : %v", err.Error())
        return
    }

    targetFile := DestinationDir + "/" + handler.Filename

    log.Printf("targetFile : (%v)", targetFile)

    err = ioutil.WriteFile(targetFile, fileBytes, 0644)
    if err != nil {
        log.Printf("could not write file (%v) : %v", targetFile, err.Error())
        return
    }

    log.Printf("File saved to : (%v)", targetFile)

    // return that we have successfully uploaded our file!
    _, _ = fmt.Fprintf(w, "Successfully Uploaded File\n")

}

func setupRoutesAndListen() {
    http.HandleFunc("/upload", uploadFile)
    err := http.ListenAndServe(":1234", nil)
    if err != nil {
        log.Printf("Error in starting the http server  : %v", err.Error())
        return
    }
}

func main() {
    DestinationDir = "/tmp"
    destinationDirPtr := flag.String("destination_directory", "/tmp", "destination folder where files would be uploaded")
    flag.Parse()

    DestinationDir = *destinationDirPtr

    if DestinationDir == "" {
        log.Printf("please provide destination directory where files would be uploaded/written. Ex: -destination_directory='/tmp'")
        return
    }
    log.Println("Welcome To HTTP File Upload Server.")
    setupRoutesAndListen()
}
```

`Client` (main.go)

```go
package main

import (
    "bytes"
    "flag"
    "io"
    "log"
    "mime/multipart"
    "net/http"
    "os"
    "path/filepath"
)

func main() {

    filePathPtr := flag.String("file", "/tmp/foo.txt", "file to upload")
    uploadURLPtr := flag.String("upload_url", "http://localhost:1234/upload", "url for uploading the file")

    flag.Parse()

    filePath := *filePathPtr
    uploadURL := *uploadURLPtr

    if filePath == "" {
        log.Printf("please provide valid file,  Ex: -file='/tmp/random.txt'")
        return
    }

    if uploadURL == "" {
        log.Printf("please provide valid upload URL, Ex: -upload_url='http://localhost:1234/upload'")
        return
    }

    file, err := os.Open(filePath)
    if err != nil {
        log.Printf("error : could not open file (%v) : %v", filePath, err.Error())
        return
    }
    defer func() {
        _ = file.Close()
    }()

    body := &bytes.Buffer{}
    writer := multipart.NewWriter(body)
    part, err := writer.CreateFormFile("myFile", filepath.Base(file.Name()))
    if err != nil {
        log.Printf("error : could not CreateFormFile for (%v) : %v", filePath, err.Error())
        return
    }
    
    _, err = io.Copy(part, file)
    if err != nil {
        log.Printf("could not perform an io.Copy :%v", err.Error())
        return
    }

    _ = writer.Close()

    r, err := http.NewRequest("POST", uploadURL, body)
    if err != nil {
        log.Printf("could not perform a http post to upload file (%v) , please check the upload URL (%v) again : %v", filePath, uploadURL, err.Error())
        return
    }
    r.Header.Add("Content-Type", writer.FormDataContentType())
    client := &http.Client{}
    _, err = client.Do(r)
    if err != nil {
        log.Printf("could not perform an upload (client.Do) for the given file (%v) , please check the upload URL (%v) and file path again : %v", filePath, uploadURL, err.Error())
        return
    }
}
```

Sample Run (on 'localhost' or '127.0.0.1')

`Start Server`

```bash
$ go run main.go -destination_directory="/tmp"
2022/10/12 21:05:44 Welcome To HTTP File Upload Server.
```

`Upload File Using Client`

```bash
$ go run main.go -file="random.bin" -upload_url="http://localhost:1234/upload"
```

`Logs On Server`

```bash
$ go run main.go -destination_directory="/tmp"
2022/10/12 21:05:44 Welcome To HTTP File Upload Server.

2022/10/12 21:06:18 File Upload Endpoint Hit
2022/10/12 21:06:18 Uploaded File : random.bin
2022/10/12 21:06:18 File Size     : 102400000
2022/10/12 21:06:18 MIME Header   : map[Content-Disposition:[form-data; name="myFile"; filename="random.bin"] Content-Type:[application/octet-stream]]
2022/10/12 21:06:18 targetFile : (/tmp/random.bin)
2022/10/12 21:06:18 File saved to : (/tmp/random.bin)
```

#### [Azure Resource Graph Query](#azure-resource-graph-query)

```go
package main

import (
    "context"
    "encoding/json"
    "fmt"
    "github.com/Azure/azure-sdk-for-go/sdk/azcore"
    "github.com/Azure/azure-sdk-for-go/sdk/azcore/arm"
    "github.com/Azure/azure-sdk-for-go/sdk/azcore/cloud"
    "github.com/Azure/azure-sdk-for-go/sdk/azcore/policy"
    "github.com/Azure/azure-sdk-for-go/sdk/azcore/to"
    "github.com/Azure/azure-sdk-for-go/sdk/azidentity"
    "github.com/Azure/azure-sdk-for-go/sdk/resourcemanager/resourcegraph/armresourcegraph"
    "log"
    "os"
)

func main() {

    azureTenantID := os.Getenv("AZURE_TENANT_ID")
    if azureTenantID == "" {
        log.Printf("ERROR : environment varilabe 'AZURE_TENANT_ID' is missing !")
        return
    }

    azureClientID := os.Getenv("AZURE_CLIENT_ID")
    if azureClientID == "" {
        log.Printf("ERROR : environment varilabe 'AZURE_CLIENT_ID' is missing !")
        return
    }

    azureClientSecret := os.Getenv("AZURE_CLIENT_SECRET")
    if azureClientSecret == "" {
        log.Printf("ERROR : environment varilabe 'AZURE_CLIENT_SECRET' is missing !")
        return
    }

    cred, err := azidentity.NewClientSecretCredential(azureTenantID, azureClientID, azureClientSecret, nil)
    if err != nil {
        log.Fatalf("failed to obtain a credential: %v", err)
    }
    opts := policy.TokenRequestOptions{Scopes: []string{"https://management.core.windows.net//.default"}}
    azToken, err := cred.GetToken(context.Background(), opts)
    log.Printf("Token : %v", azToken.Token)

    options := arm.ClientOptions{
        ClientOptions: azcore.ClientOptions{
            Cloud: cloud.AzurePublic,
        },
    }
    client, err := armresourcegraph.NewClient(cred, &options)
    if err != nil {
        log.Printf("ERROR : could not create new ARM RG client : %v", err.Error())
        return
    }

    response, err := client.Resources(context.Background(),
        armresourcegraph.QueryRequest{
            Query:         to.Ptr("Resources | where type =~ 'Microsoft.Compute/virtualMachines' | summarize count() by tostring(properties.storageProfile.osDisk.osType)"),
            Subscriptions: nil,
            //Subscriptions: []*string{to.Ptr("00000000-0000-0000-0000-000000000000")},
        }, nil)
    if err != nil {
        log.Printf("ERROR : could not fetch resources using RG client : %v", err.Error())
        return
    }
    responseData := response.Data
    PrettyPrintData(responseData)
}

func PrettyPrintData(data interface{}) {
    dataBytes, err := json.MarshalIndent(data, "", "    ")
    if err != nil {
        log.Printf("error : could not MarshalIndent json : %v", err.Error())
        return
    }
    fmt.Printf("\n%v\n\n", string(dataBytes))
}
```

Output

```bash
$ go run main.go
```

```bash
2022/11/11 13:34:20 Token : <TOKEN_REDACTED>

[
    {
        "count_": 800,
        "properties_storageProfile_osDisk_osType": "Windows"
    },
    {
        "count_": 1200,
        "properties_storageProfile_osDisk_osType": "Linux"
    }
]
```

#### Using `Azure Resource Graph Query` , Fetch All Virtual Machines

```go
package main

import (
    "context"
    "encoding/json"
    "errors"
    "fmt"
    "github.com/Azure/azure-sdk-for-go/sdk/azcore"
    "github.com/Azure/azure-sdk-for-go/sdk/azcore/arm"
    "github.com/Azure/azure-sdk-for-go/sdk/azcore/cloud"
    "github.com/Azure/azure-sdk-for-go/sdk/azcore/policy"
    "github.com/Azure/azure-sdk-for-go/sdk/azcore/to"
    "github.com/Azure/azure-sdk-for-go/sdk/azidentity"
    "github.com/Azure/azure-sdk-for-go/sdk/resourcemanager/resourcegraph/armresourcegraph"
    "io/ioutil"
    "log"
    "math"
    "os"
    "sync"
    "time"
)

func main() {

    azureTenantID := os.Getenv("AZURE_TENANT_ID")
    if azureTenantID == "" {
        log.Printf("ERROR : environment varilabe 'AZURE_TENANT_ID' is missing !")
        return
    }

    azureClientID := os.Getenv("AZURE_CLIENT_ID")
    if azureClientID == "" {
        log.Printf("ERROR : environment varilabe 'AZURE_CLIENT_ID' is missing !")
        return
    }

    azureClientSecret := os.Getenv("AZURE_CLIENT_SECRET")
    if azureClientSecret == "" {
        log.Printf("ERROR : environment varilabe 'AZURE_CLIENT_SECRET' is missing !")
        return
    }

    cred, err := azidentity.NewClientSecretCredential(azureTenantID, azureClientID, azureClientSecret, nil)
    if err != nil {
        log.Fatalf("failed to obtain a credential: %v", err)
        return
    }
    //opts := policy.TokenRequestOptions{Scopes: []string{"https://management.core.windows.net//.default"}}
    //azToken, err := cred.GetToken(context.Background(), opts)
    //log.Printf("Token : %v", azToken.Token)

    totalRecords, err := GetTotalCountVirtualMachines(cred)
    if err != nil {
        log.Printf("ERROR : %v", err.Error())
        return
    }

    log.Printf("Total Count of VMs : %v", totalRecords)

    pagesToFetch := int32(1000)

    numberOfThreads := 4
    myRanges := SplitNum(int(totalRecords), numberOfThreads)
    fmt.Printf("myRanges : %v", myRanges)

    var wg sync.WaitGroup

    finalResults := make(map[int][]interface{})

    for index, data := range myRanges {
        wg.Add(1)
        go func(wg *sync.WaitGroup, indexValue int, myData Range) {
            defer wg.Done()
            start := myData.Start
            end := myData.End
            records, err := GetVMRecordsFromStardToEnd(start, end, pagesToFetch, cred)
            if err != nil {
                log.Printf("OOPS : main() : %v", err.Error())
                return
            }
            finalResults[indexValue] = records
        }(&wg, index, data)
    }

    wg.Wait()

    allRecords := make([]interface{}, 0)

    for _, results := range finalResults {
        for _, data := range results {
            allRecords = append(allRecords, data)
        }
    }

    WriteInterfaceToFile("azure_data.json", allRecords)
}

func PrettyPrintData(data interface{}) {
    dataBytes, err := json.MarshalIndent(data, "", "    ")
    if err != nil {
        log.Printf("error : could not MarshalIndent json : %v", err.Error())
        return
    }
    fmt.Printf("\n%v\n\n", string(dataBytes))
}

func WriteInterfaceToFile(fileName string, data interface{}) {
    file, _ := json.MarshalIndent(data, "", " ")
    _ = ioutil.WriteFile(fileName, file, 0644)
}

func GetVMRecordsFromStardToEnd(start int32, end int32, pagesToFetch int32, cred *azidentity.ClientSecretCredential) ([]interface{}, error) {
    message := ""
    allResources := make([]interface{}, 0)
    for x := start; x <= end; x += pagesToFetch {
        records, err := GetVMRecords(x, pagesToFetch, cred)
        if err != nil {
            message = fmt.Sprintf("OOPS : func GetVMRecordsFromStardToEnd() : (ERROR) : %v", err.Error())
            return nil, errors.New(message)
        }
        for _, data := range records {
            allResources = append(allResources, data)
        }
        log.Printf("func GetVMRecordsFromStardToEnd() : len(allResources) : %v", len(allResources))
    }
    return allResources, nil
}

func GetVMRecords(pageStart int32, pagesToFetch int32, cred *azidentity.ClientSecretCredential) ([]interface{}, error) {
    message := ""

    retryOptions := policy.RetryOptions{
        MaxRetries: 100,
        RetryDelay: 15 * time.Second,
    }

    options := arm.ClientOptions{
        ClientOptions: azcore.ClientOptions{
            Cloud: cloud.AzurePublic,
            Retry: retryOptions,
        },
    }

    client, err := armresourcegraph.NewClient(cred, &options)
    if err != nil {
        message = fmt.Sprintf("ERROR : could not create new ARM RG client : %v", err.Error())
        return nil, errors.New(message)
    }

    allResources := make([]interface{}, 0)

    queryRequestOptions := armresourcegraph.QueryRequestOptions{
        Skip: &pageStart,
        Top:  &pagesToFetch,
    }

    resourceResponse, err := client.Resources(context.Background(),
        armresourcegraph.QueryRequest{
            Query:         to.Ptr("Resources | where type =~ 'Microsoft.Compute/virtualMachines'"),
            Subscriptions: nil,
            Options:       &queryRequestOptions,
        }, nil)
    if err != nil {
        message = fmt.Sprintf("ERROR : could not fetch resources using RG client : (%v)", err.Error())
        return nil, errors.New(message)
    }

    resourceDataList := resourceResponse.Data.([]interface{})

    for _, data := range resourceDataList {
        allResources = append(allResources, data)
    }

    log.Printf("func GetVMRecords() : pageStart : %v , pagesToFetch : %v, records-fetched : %v", pageStart, pagesToFetch, len(allResources))

    return resourceDataList, nil
}

func GetTotalCountVirtualMachines(cred *azidentity.ClientSecretCredential) (float64, error) {
    msg := ""
    retryOptions := policy.RetryOptions{
        MaxRetries: 100,
        RetryDelay: 15 * time.Second,
    }

    options := arm.ClientOptions{
        ClientOptions: azcore.ClientOptions{
            Cloud: cloud.AzurePublic,
            Retry: retryOptions,
        },
    }
    client, err := armresourcegraph.NewClient(cred, &options)
    if err != nil {
        msg = fmt.Sprintf("ERROR : could not create new ARM RG client : %v", err.Error())
        return 0, errors.New(msg)
    }

    response, err := client.Resources(context.Background(),
        armresourcegraph.QueryRequest{
            Query:         to.Ptr("Resources | where type == 'microsoft.compute/virtualmachines' | summarize count()"),
            Subscriptions: nil,
        }, nil)
    if err != nil {
        log.Printf("ERROR : could not exec resource graph query : %v", err.Error())
        return 0, err
    }
    log.Printf("GetTotalCountVirtualMachines() : Total Count of VMs >")
    //PrettyPrintData(response.Data)
    data := response.Data
    records := data.([]interface{})
    if len(records) == 0 {
        return 0, errors.New("func GetTotalCountVirtualMachines() : number of records is ZERO")
    }
    firstRecord := records[0]
    recordMap, ok := firstRecord.(map[string]interface{})
    if !ok {
        return 0, errors.New("func GetTotalCountVirtualMachines() : firstRecord is NOT a map[string]interface{}")
    }
    totalCountResult, ok := recordMap["count_"]
    if !ok {
        return 0, errors.New("func GetTotalCountVirtualMachines() : recordMap['count_'] does not exist")
    }
    totalCount := totalCountResult.(float64)
    return totalCount, nil
}

type Range struct {
    Start int32
    End   int32
}

func SplitNum(myNumber int, chunks int) []Range {

    average := int(math.Floor(float64(myNumber) / float64(chunks)))

    fmt.Printf("\n average : %v \n", average)

    reminder := myNumber % int(math.Floor(float64(average)))

    fmt.Printf("\n reminder : %v \n", reminder)

    finalRange := make([]Range, 0)

    var start int32
    var end int32

    for x := 0; x < chunks; x++ {
        if x == 0 {
            start = int32(0)
        } else {
            start = int32(x * average)
        }

        if x == chunks-1 {
            end = int32(myNumber - 1)
        } else {
            end = int32((x * average) + (average - 1))
        }

        myRange := Range{
            Start: start,
            End:   end,
        }
        finalRange = append(finalRange, myRange)
    }

    log.Printf("func : SplitNum(myNumber : %v, chunks : %v) -> finalRange -> %v", myNumber, chunks, finalRange)

    return finalRange
}
```

#### [Worker Pools](#worker-pools)

```go
package main

import (
    "crypto/md5"
    "encoding/hex"
    "fmt"
    "log"
    "time"
)

type Input struct {
    Data int
}

type Output struct {
    HashValue string
}

func GenerateInputs() []Input {
    myUUIDList := make([]Input, 0)
    for i := 1000; i < 1100; i++ {
        myData := Input{Data: i}
        myUUIDList = append(myUUIDList, myData)
    }
    return myUUIDList
}

func ExecuteWorkerPoolJobs() []Output {
    jobs := make(chan Input, 1)
    results := make(chan Output, 1)
    resultList := make([]Output, 0)
    maxNumberOfWorkers := 3

    uuidList := GenerateInputs()

    log.Printf("Done generating UUID List of Inputs.")

    waitChannel := make(chan struct{})

    for w := 1; w <= maxNumberOfWorkers; w++ {
        go Worker(jobs, results)
    }

    go func() {
        for _, uuid := range uuidList {
            jobs <- uuid
        }
        close(jobs)
    }()

    go func() {
        for i := 0; i < len(uuidList); i++ {
            result := <-results
            resultList = append(resultList, result)
        }
        close(waitChannel)
    }()

    <-waitChannel

    return resultList
}

func Worker(jobs <-chan Input, results chan<- Output) {
    counter := 1
    for {
        job, ok := <-jobs
        if !ok {
            break
        }
        dataStr := fmt.Sprintf("%v", job.Data)
        hash := GetMD5HashForString(dataStr)
        log.Printf("(%v) : hashWorker : job => %v , hash => %v", counter, job, hash)
        counter++
        output := Output{HashValue: hash}
        results <- output
    }
}

func main() {
    hashList := ExecuteWorkerPoolJobs()
    log.Printf("Total Length of output : %v", len(hashList))
    for _, data := range hashList {
        log.Printf("Hash of data : %v", data.HashValue)
    }
}

func GetMD5HashForString(text string) string {
    time.Sleep(2 * time.Second)
    hasher := md5.New()
    hasher.Write([]byte(text))
    md5Value := hex.EncodeToString(hasher.Sum(nil))
    return md5Value
}
```

Output

```bash
$ go run main.go
2022/11/20 19:26:33 Done generating UUID List of Inputs.
2022/11/20 19:26:35 (1) : hashWorker : job => {1000} , hash => a9b7ba70783b617e9998dc4dd82eb3c5
2022/11/20 19:26:35 (1) : hashWorker : job => {1001} , hash => b8c37e33defde51cf91e1e03e51657da
2022/11/20 19:26:35 (1) : hashWorker : job => {1002} , hash => fba9d88164f3e2d9109ee770223212a0
2022/11/20 19:26:37 (2) : hashWorker : job => {1005} , hash => 2387337ba1e0b0249ba90f55b2ba2521
2022/11/20 19:26:37 (2) : hashWorker : job => {1003} , hash => aa68c75c4a77c87f97fb686b2f068676
2022/11/20 19:26:37 (2) : hashWorker : job => {1004} , hash => fed33392d3a48aa149a87a38b875ba4a
2022/11/20 19:26:39 (3) : hashWorker : job => {1007} , hash => d7322ed717dedf1eb4e6e52a37ea7bcd
2022/11/20 19:26:39 (3) : hashWorker : job => {1008} , hash => 1587965fb4d4b5afe8428a4a024feb0d
...
...
<truncated>
```

#### [Worker Pool V2](#worker-pool-v2)

```go
package main

import (
    "crypto/md5"
    "encoding/hex"
    "fmt"
    "log"
    "time"
)

type Input struct {
    Data int
}

type Output struct {
    HashValue string
}

type InputGenerator func() []Input

type PoolWorkerData struct {
    Input
    Output
    MaxWorkers int
    IGen       InputGenerator
}

type PoolWorkerInterface interface {
    ExecutePoolWorkerJobs() []Output
}

func (d PoolWorkerData) ExecutePoolWorkerJobs() []Output {
    jobs := make(chan Input, 1)
    results := make(chan Output, 1)

    resultsList := make([]Output, 0)
    maxNumberOfWorkers := d.MaxWorkers
    inputList := d.IGen()
    log.Printf("Done generating input list.")
    waitChannel := make(chan struct{})

    wp := WorkProcessor{
        JobsChannel:    jobs,
        ResultsChannel: results,
        FDProcessor:    GetMD5Hash,
    }

    for w := 1; w <= maxNumberOfWorkers; w++ {
        go wp.WorkerV1()
    }

    go func() {
        for _, job := range inputList {
            jobs <- job
        }
        close(jobs)
    }()

    go func() {
        for i := 0; i < len(inputList); i++ {
            result := <-results
            resultsList = append(resultsList, result)
        }
        close(waitChannel)
    }()

    <-waitChannel

    return resultsList
}

/*
FetchInputs ...
*/
func FetchInputs() []Input {
    myDataList := make([]Input, 0)
    for i := 1000; i < 1020; i++ {
        myData := Input{Data: i}
        myDataList = append(myDataList, myData)
    }
    return myDataList
}

type DataProcessor func(data interface{}) interface{}

type WorkProcessor struct {
    JobsChannel    chan Input
    ResultsChannel chan Output
    FDProcessor    DataProcessor
}

type WorkProcessorInterface interface {
    WorkerV1()
}

func (wp WorkProcessor) WorkerV1() {
    for {
        job, ok := <-wp.JobsChannel
        if !ok {
            break
        }
        myInput := job.Data
        myResult := wp.FDProcessor(myInput)
        log.Printf("WorkerV1() : myInput => %v , myResult => %v", myInput, myResult)
        myOutput := Output{HashValue: myResult.(string)}
        wp.ResultsChannel <- myOutput
    }
}

func main() {

    poolWorkerData := PoolWorkerData{
        Input:      Input{},
        Output:     Output{},
        MaxWorkers: 3,
        IGen:       FetchInputs,
    }

    hashList := poolWorkerData.ExecutePoolWorkerJobs()

    // print the results

    log.Printf("Total Results : %v", len(hashList))
    for _, data := range hashList {
        log.Printf("Hash of data : %v", data.HashValue)
    }
}

func GetMD5Hash(data interface{}) interface{} {
    text := fmt.Sprintf("%v", data)
    time.Sleep(2 * time.Second)
    hasher := md5.New()
    hasher.Write([]byte(text))
    md5Value := hex.EncodeToString(hasher.Sum(nil))
    return md5Value
}
```

Output

```bash
go run main.go
```

```
2022/11/21 12:03:43 Done generating input list.
2022/11/21 12:03:45 WorkerV1() : myInput => 1002 , myResult => fba9d88164f3e2d9109ee770223212a0
2022/11/21 12:03:45 WorkerV1() : myInput => 1001 , myResult => b8c37e33defde51cf91e1e03e51657da
2022/11/21 12:03:45 WorkerV1() : myInput => 1000 , myResult => a9b7ba70783b617e9998dc4dd82eb3c5
2022/11/21 12:03:47 WorkerV1() : myInput => 1004 , myResult => fed33392d3a48aa149a87a38b875ba4a
2022/11/21 12:03:47 WorkerV1() : myInput => 1005 , myResult => 2387337ba1e0b0249ba90f55b2ba2521
2022/11/21 12:03:47 WorkerV1() : myInput => 1003 , myResult => aa68c75c4a77c87f97fb686b2f068676
2022/11/21 12:03:49 WorkerV1() : myInput => 1006 , myResult => 9246444d94f081e3549803b928260f56
2022/11/21 12:03:49 WorkerV1() : myInput => 1008 , myResult => 1587965fb4d4b5afe8428a4a024feb0d
2022/11/21 12:03:49 WorkerV1() : myInput => 1007 , myResult => d7322ed717dedf1eb4e6e52a37ea7bcd
2022/11/21 12:03:51 WorkerV1() : myInput => 1009 , myResult => 31b3b31a1c2f8a370206f111127c0dbd
2022/11/21 12:03:51 WorkerV1() : myInput => 1011 , myResult => 7f975a56c761db6506eca0b37ce6ec87
2022/11/21 12:03:51 WorkerV1() : myInput => 1010 , myResult => 1e48c4420b7073bc11916c6c1de226bb
2022/11/21 12:03:53 WorkerV1() : myInput => 1012 , myResult => f33ba15effa5c10e873bf3842afb46a6
2022/11/21 12:03:53 WorkerV1() : myInput => 1014 , myResult => 766d856ef1a6b02f93d894415e6bfa0e
2022/11/21 12:03:53 WorkerV1() : myInput => 1013 , myResult => 6b180037abbebea991d8b1232f8a8ca9
2022/11/21 12:03:55 WorkerV1() : myInput => 1017 , myResult => 5d616dd38211ebb5d6ec52986674b6e4
2022/11/21 12:03:55 WorkerV1() : myInput => 1016 , myResult => 08fe2621d8e716b02ec0da35256a998d
2022/11/21 12:03:55 WorkerV1() : myInput => 1015 , myResult => 298923c8190045e91288b430794814c4
2022/11/21 12:03:57 WorkerV1() : myInput => 1019 , myResult => 03e0704b5690a2dee1861dc3ad3316c9
2022/11/21 12:03:57 WorkerV1() : myInput => 1018 , myResult => ef50c335cca9f340bde656363ebd02fd
2022/11/21 12:03:57 Total Results : 20
2022/11/21 12:03:57 Hash of data : fba9d88164f3e2d9109ee770223212a0
2022/11/21 12:03:57 Hash of data : b8c37e33defde51cf91e1e03e51657da
2022/11/21 12:03:57 Hash of data : a9b7ba70783b617e9998dc4dd82eb3c5
2022/11/21 12:03:57 Hash of data : fed33392d3a48aa149a87a38b875ba4a
2022/11/21 12:03:57 Hash of data : 2387337ba1e0b0249ba90f55b2ba2521
2022/11/21 12:03:57 Hash of data : aa68c75c4a77c87f97fb686b2f068676
2022/11/21 12:03:57 Hash of data : 9246444d94f081e3549803b928260f56
2022/11/21 12:03:57 Hash of data : 1587965fb4d4b5afe8428a4a024feb0d
2022/11/21 12:03:57 Hash of data : d7322ed717dedf1eb4e6e52a37ea7bcd
2022/11/21 12:03:57 Hash of data : 31b3b31a1c2f8a370206f111127c0dbd
2022/11/21 12:03:57 Hash of data : 7f975a56c761db6506eca0b37ce6ec87
2022/11/21 12:03:57 Hash of data : 1e48c4420b7073bc11916c6c1de226bb
2022/11/21 12:03:57 Hash of data : f33ba15effa5c10e873bf3842afb46a6
2022/11/21 12:03:57 Hash of data : 766d856ef1a6b02f93d894415e6bfa0e
2022/11/21 12:03:57 Hash of data : 6b180037abbebea991d8b1232f8a8ca9
2022/11/21 12:03:57 Hash of data : 5d616dd38211ebb5d6ec52986674b6e4
2022/11/21 12:03:57 Hash of data : 08fe2621d8e716b02ec0da35256a998d
2022/11/21 12:03:57 Hash of data : 298923c8190045e91288b430794814c4
2022/11/21 12:03:57 Hash of data : 03e0704b5690a2dee1861dc3ad3316c9
2022/11/21 12:03:57 Hash of data : ef50c335cca9f340bde656363ebd02fd
```

#### [Worker Pool V3](#worker-pool-v3)

```go
package main

import (
    "crypto/md5"
    "encoding/hex"
    "fmt"
    "log"
    "time"
)

/* ******************************** Core Data Structures ***************************************** */
/* Change this dependng on what is your input/output */

type Input struct {
    Data int
}

type Output struct {
    HashValue string
}

/* ******************************** Worker Pools ***************************************** */

type InputGenerator func() []Input

type PoolWorkerData struct {
    Input
    Output
    MaxWorkers int
    IGen       InputGenerator
}

type PoolWorkerInterface interface {
    ExecutePoolWorkerJobs() []Output
}

func (d PoolWorkerData) ExecutePoolWorkerJobs() []Output {
    jobs := make(chan Input, 1)
    results := make(chan Output, 1)

    resultsList := make([]Output, 0) // return this at the end of the function

    maxNumberOfWorkers := d.MaxWorkers

    inputList := d.IGen() // generate inputs

    log.Printf("Done generating input list.")

    waitChannel := make(chan struct{})

    wp := WorkProcessor{
        JobsChannel:       jobs,
        ResultsChannel:    results,
        FuncDataProcessor: GetMD5Hash,
    }

    df := DataFeeder{
        InputList:   inputList,
        JobsChannel: jobs,
    }

    de := DataExtractor{
        TotalInputLength: len(inputList),
        ResultsChannel:   results,
        WaitChannel:      waitChannel,
    }

    df.FeedDataIntoChannel()

    for w := 1; w <= maxNumberOfWorkers; w++ {
        go wp.PoolWorker()
    }

    resultsList = de.ExtractAllData()

    return resultsList
}

/* ******************************** Data Extractor ***************************************** */

type DataExtractor struct {
    TotalInputLength int
    ResultsChannel   chan Output
    WaitChannel      chan struct{}
}

type DataFeeder struct {
    InputList   []Input
    JobsChannel chan Input
}

type DataExtractorInterface interface {
    ExtractAllData() []Output
}

type DataFeederInterface interface {
    FeedDataIntoChannel()
}

func (df DataFeeder) FeedDataIntoChannel() {
    go func() {
        for _, job := range df.InputList {
            df.JobsChannel <- job
        }
        close(df.JobsChannel)
    }()
}

func (de DataExtractor) ExtractAllData() []Output {
    resultsList := make([]Output, 0)

    go func() {
        for i := 0; i < de.TotalInputLength; i++ {
            result := <-de.ResultsChannel
            resultsList = append(resultsList, result)
        }
        close(de.WaitChannel)
    }()
    <-de.WaitChannel
    return resultsList
}

/* ******************************** Work Processor ***************************************** */

type DataProcessor func(data interface{}) interface{}

type WorkProcessor struct {
    JobsChannel       chan Input
    ResultsChannel    chan Output
    FuncDataProcessor DataProcessor
}

type WorkProcessorInterface interface {
    PoolWorker()
}

func (wp WorkProcessor) PoolWorker() {
    for {
        job, ok := <-wp.JobsChannel
        if !ok {
            break
        }
        myInput := job.Data
        myResult := wp.FuncDataProcessor(myInput)
        log.Printf("PoolWorker() : myInput => %v , myResult => %v", myInput, myResult)
        myOutput := Output{HashValue: myResult.(string)}
        wp.ResultsChannel <- myOutput
    }
}

/* ******************************** main() ***************************************** */

func main() {

    poolWorkerData := PoolWorkerData{
        Input:      Input{},
        Output:     Output{},
        MaxWorkers: 3,
        IGen:       GenerateInputs,
    }

    resultList := poolWorkerData.ExecutePoolWorkerJobs()

    // print the results

    log.Printf("Total Results : %v", len(resultList))
    for _, data := range resultList {
        log.Printf("Hash of data : %v", data.HashValue)
    }
}

/* ******************************** Helper Functions ***************************************** */

func GenerateInputs() []Input {
    log.Printf("$$ GenerateInputs()...")
    myDataList := make([]Input, 0)
    for i := 1000; i < 1020; i++ {
        myData := Input{Data: i}
        myDataList = append(myDataList, myData)
    }
    return myDataList
}

func GetMD5Hash(data interface{}) interface{} {
    text := fmt.Sprintf("%v", data)
    time.Sleep(2 * time.Second)
    hasher := md5.New()
    hasher.Write([]byte(text))
    md5Value := hex.EncodeToString(hasher.Sum(nil))
    return md5Value
}
```

#### [Ubuntu Service File Running Binary](#ubuntu-service-file-running-binary)

Generate Binary

```bash
go build -o /bin/fileuploader
```

Service File `/lib/systemd/system/fileuploader.service`

```ini
[Unit]
Description=File Upload Server
ConditionPathExists=/var/www/html/upload_dir

[Service]
Type=simple
User=root
Group=root
ExecStart=/bin/fileuploader -destination_directory=/var/www/html/upload_dir
Restart=on-failure
RestartSec=10
StandardOutput=syslog
StandardError=syslog
SyslogIdentifier=fileuploader

[Install]
WantedBy=multi-user.target
```

Create Softlink

```bash
ln -s /lib/systemd/system/fileuploader.service /etc/systemd/system/fileuploader.service
```

Enable Service

```bash
systemctl enable /lib/systemd/system/fileuploader.service
```

Restart Service

```bash
systemctl stop fileuploader;sleep 3; systemctl start fileuploader;
```

#### [Parse EMail Address](#parse-email-address)

```go
package main

import (
    "fmt"
    "net/mail"
)

func validMailAddress(address string) (string, bool) {
    addr, err := mail.ParseAddress(address)
    if err != nil {
        return "", false
    }
    return addr.Address, true
}

var addresses = []string{
    "foo@gmail.com",
    "Gopher <from@example.com>",
    "example",
}

func main() {
    for _, a := range addresses {
        if addr, ok := validMailAddress(a); ok {
            fmt.Printf("value: %-30s valid email: %-10t address: %s\n", a, ok, addr)
        } else {
            fmt.Printf("value: %-30s valid email: %-10t\n", a, ok)
        }
    }
}
```

Output

```bash
value: foo@gmail.com                  valid email: true       address: foo@gmail.com
value: Gopher <from@example.com>      valid email: true       address: from@example.com
value: example                        valid email: false     
```

#### [Return Channel From Function](#return-channel-from-function)

```go
package main

import (
    "encoding/json"
    "fmt"
    "log"
    "math/rand"
    "sync"
    "time"
)

func GenerateChan(nums []int) <-chan int {
    out := make(chan int)
    go func() {
        for _, n := range nums {
            time.Sleep(500 * time.Millisecond)
            out <- n
        }
        close(out)
    }()

    return out
}

func GenerateInputData() []int {
    myRandomList := make([]int, 0)

    for i := 1; i <= 27; i++ {
        myRandomList = append(myRandomList, GetRandomNumber())
    }
    return myRandomList
}

func main() {

    myRandomList := GenerateInputData()

    chunkSize := 6

    chunks := BreakIntoMultipleChunks(myRandomList, chunkSize)

    fmt.Printf("\n------------[chunks (input)]------------\n")

    PrettyPrintData(chunks)

    fmt.Printf("\n------------[sequential_processing]------------\n\n")

    for _, chunk := range chunks {
        ProcessChunkDataSequentially(chunk)
    }

    fmt.Printf("\n------------[parallel_processing]------------\n\n")

    var wg sync.WaitGroup

    for _, chunk := range chunks {
        wg.Add(1)
        go ProcessChunkDataInParallel(&wg, chunk)
    }
    wg.Wait()
}

func ProcessChunkDataInParallel(wg *sync.WaitGroup, myChunk []int) {
    defer wg.Done()
    dataChan := GenerateChan(myChunk)
    for {
        data, ok := <-dataChan
        if !ok {
            break
        }
        log.Printf("ProcessChunkDataInParallel() : received data from chan : %v", data)
    }
}

func ProcessChunkDataSequentially(myChunk []int) {
    dataChan := GenerateChan(myChunk)
    for {
        data, ok := <-dataChan
        if !ok {
            break
        }
        log.Printf("ProcessChunkDataSequentially() : received data from chan : %v", data)
    }
}

func GetRandomNumber() int {
    max := 900
    min := 100
    rand.Seed(time.Now().UnixNano())
    return rand.Intn(max-min) + min
}

func PrettyPrintData(data interface{}) {
    dataBytes, err := json.MarshalIndent(data, "", "    ")
    if err != nil {
        log.Printf("error : could not MarshalIndent json : %v", err.Error())
        return
    }
    fmt.Printf("\n%v\n\n", string(dataBytes))
}

func BreakIntoMultipleChunks(slice []int, chunkSize int) [][]int {
    var chunks [][]int
    for i := 0; i < len(slice); i += chunkSize {
        end := i + chunkSize

        // necessary check to avoid slicing beyond slice capacity
        if end > len(slice) {
            end = len(slice)
        }

        chunks = append(chunks, slice[i:end])
    }

    return chunks
}
```

Output

```bash
❯ go run main.go
```

```bash
------------[chunks (input)]------------

[
    [
        186,
        719,
        425,
        336,
        382,
        449
    ],
    [
        747,
        881,
        864,
        496,
        539,
        607
    ],
    [
        426,
        818,
        764,
        781,
        336,
        668
    ],
    [
        591,
        136,
        639,
        874,
        686,
        633
    ],
    [
        222,
        237,
        296
    ]
]


------------[sequential_processing]------------

2022/12/14 11:31:58 ProcessChunkDataSequentially() : received data from chan : 186
2022/12/14 11:31:58 ProcessChunkDataSequentially() : received data from chan : 719
2022/12/14 11:31:59 ProcessChunkDataSequentially() : received data from chan : 425
2022/12/14 11:31:59 ProcessChunkDataSequentially() : received data from chan : 336
2022/12/14 11:32:00 ProcessChunkDataSequentially() : received data from chan : 382
2022/12/14 11:32:00 ProcessChunkDataSequentially() : received data from chan : 449
2022/12/14 11:32:01 ProcessChunkDataSequentially() : received data from chan : 747
2022/12/14 11:32:01 ProcessChunkDataSequentially() : received data from chan : 881
2022/12/14 11:32:02 ProcessChunkDataSequentially() : received data from chan : 864
2022/12/14 11:32:02 ProcessChunkDataSequentially() : received data from chan : 496
2022/12/14 11:32:03 ProcessChunkDataSequentially() : received data from chan : 539
2022/12/14 11:32:03 ProcessChunkDataSequentially() : received data from chan : 607
2022/12/14 11:32:04 ProcessChunkDataSequentially() : received data from chan : 426
2022/12/14 11:32:04 ProcessChunkDataSequentially() : received data from chan : 818
2022/12/14 11:32:05 ProcessChunkDataSequentially() : received data from chan : 764
2022/12/14 11:32:05 ProcessChunkDataSequentially() : received data from chan : 781
2022/12/14 11:32:06 ProcessChunkDataSequentially() : received data from chan : 336
2022/12/14 11:32:06 ProcessChunkDataSequentially() : received data from chan : 668
2022/12/14 11:32:07 ProcessChunkDataSequentially() : received data from chan : 591
2022/12/14 11:32:07 ProcessChunkDataSequentially() : received data from chan : 136
2022/12/14 11:32:08 ProcessChunkDataSequentially() : received data from chan : 639
2022/12/14 11:32:08 ProcessChunkDataSequentially() : received data from chan : 874
2022/12/14 11:32:09 ProcessChunkDataSequentially() : received data from chan : 686
2022/12/14 11:32:09 ProcessChunkDataSequentially() : received data from chan : 633
2022/12/14 11:32:10 ProcessChunkDataSequentially() : received data from chan : 222
2022/12/14 11:32:10 ProcessChunkDataSequentially() : received data from chan : 237
2022/12/14 11:32:11 ProcessChunkDataSequentially() : received data from chan : 296

------------[parallel_processing]------------

2022/12/14 11:32:11 ProcessChunkDataInParallel() : received data from chan : 591
2022/12/14 11:32:11 ProcessChunkDataInParallel() : received data from chan : 222
2022/12/14 11:32:11 ProcessChunkDataInParallel() : received data from chan : 186
2022/12/14 11:32:11 ProcessChunkDataInParallel() : received data from chan : 747
2022/12/14 11:32:11 ProcessChunkDataInParallel() : received data from chan : 426
2022/12/14 11:32:12 ProcessChunkDataInParallel() : received data from chan : 818
2022/12/14 11:32:12 ProcessChunkDataInParallel() : received data from chan : 237
2022/12/14 11:32:12 ProcessChunkDataInParallel() : received data from chan : 136
2022/12/14 11:32:12 ProcessChunkDataInParallel() : received data from chan : 719
2022/12/14 11:32:12 ProcessChunkDataInParallel() : received data from chan : 881
2022/12/14 11:32:12 ProcessChunkDataInParallel() : received data from chan : 864
2022/12/14 11:32:12 ProcessChunkDataInParallel() : received data from chan : 764
2022/12/14 11:32:12 ProcessChunkDataInParallel() : received data from chan : 639
2022/12/14 11:32:12 ProcessChunkDataInParallel() : received data from chan : 296
2022/12/14 11:32:12 ProcessChunkDataInParallel() : received data from chan : 425
2022/12/14 11:32:13 ProcessChunkDataInParallel() : received data from chan : 496
2022/12/14 11:32:13 ProcessChunkDataInParallel() : received data from chan : 336
2022/12/14 11:32:13 ProcessChunkDataInParallel() : received data from chan : 874
2022/12/14 11:32:13 ProcessChunkDataInParallel() : received data from chan : 781
2022/12/14 11:32:13 ProcessChunkDataInParallel() : received data from chan : 686
2022/12/14 11:32:13 ProcessChunkDataInParallel() : received data from chan : 336
2022/12/14 11:32:13 ProcessChunkDataInParallel() : received data from chan : 382
2022/12/14 11:32:13 ProcessChunkDataInParallel() : received data from chan : 539
2022/12/14 11:32:14 ProcessChunkDataInParallel() : received data from chan : 633
2022/12/14 11:32:14 ProcessChunkDataInParallel() : received data from chan : 607
2022/12/14 11:32:14 ProcessChunkDataInParallel() : received data from chan : 668
2022/12/14 11:32:14 ProcessChunkDataInParallel() : received data from chan : 449
```

#### [Return Channel From Function V2](#return-channel-from-function-v2)

Using `generics`

```go
package main

import (
    "encoding/json"
    "fmt"
    "log"
    "math/rand"
    "time"
)

func CreateDataChannelAndPushData(totalListsToGenerate int, countOfElementsPerSlice int) <-chan []int {
    out := make(chan []int)
    go func() {
        // generate a total of (totalListsToGenerate) lists
        // each list having a total of (countOfElementsPerSlice) elements
        for i := 0; i < totalListsToGenerate; i++ {
            mySlice := GenerateData(countOfElementsPerSlice)

            chunkSize := 10

            // if length of (mySlice) is 100 (total elements in the slice)
            // then break it down into chunks of (chunkSize) elements
            // listOfListOfItems is [][]int
            listOfListOfItems := BreakIntoMultipleChunks(mySlice, chunkSize)
            for _, slice := range listOfListOfItems {
                // here length of (slice) will be 10
                fmt.Printf("\n---[slice]---\n\n")
                PrettyPrintData(slice)
                time.Sleep(500 * time.Millisecond)
                // push (slice) onto the return channel
                out <- slice
            }
        }
        close(out)
    }()
    return out
}

func GenerateData(countOfElements int) []int {
    myRandomList := make([]int, 0)
    for i := 0; i < countOfElements; i++ {
        myRandomList = append(myRandomList, GetRandomNumber())
    }
    return myRandomList
}

func main() {
    fmt.Printf("\n----[sequential_processing]----\n\n")
    ProcessDataFromChannel()
}

func ProcessDataFromChannel() {
    totalListsToGenerate := 5
    countOfElementsPerSlice := 14
    dataChan := CreateDataChannelAndPushData(totalListsToGenerate, countOfElementsPerSlice)
    for {
        data, ok := <-dataChan
        if !ok {
            break
        }
        log.Printf("ProcessDataFromChannel() : received data from chan : %v", data)
    }
}

func GetRandomNumber() int {
    max := 900
    min := 100
    rand.Seed(time.Now().UnixNano())
    return rand.Intn(max-min) + min
}

func PrettyPrintData(data interface{}) {
    dataBytes, err := json.MarshalIndent(data, "", "    ")
    if err != nil {
        log.Printf("error : could not MarshalIndent json : %v", err.Error())
        return
    }
    fmt.Printf("\n%v\n\n", string(dataBytes))
}

func BreakIntoMultipleChunks[T any](slice []T, chunkSize int) [][]T {
    var chunks [][]T
    for i := 0; i < len(slice); i += chunkSize {
        end := i + chunkSize

        // necessary check to avoid slicing beyond slice capacity
        if end > len(slice) {
            end = len(slice)
        }

        chunks = append(chunks, slice[i:end])
    }

    return chunks
}
```

#### [Return Channel From Function V3](#return-channel-from-function-v3)

Using `Slice` as a type of `[]int`

```go
package main

import (
    "encoding/json"
    "fmt"
    "log"
    "math/rand"
    "time"
)

type Slice []int

type ISlice interface {
    BreakSlice(chunkSize int) []Slice
}

func (d Slice) BreakSlice(chunkSize int) []Slice {
    listOfListOfItems := BreakIntoMultipleChunks(d, chunkSize)
    return listOfListOfItems
}

func CreateDataChannelAndPushData(totalListsToGenerate int, countOfElementsPerSlice int) <-chan Slice {
    out := make(chan Slice)
    go func() {
        // generate a total of (totalListsToGenerate) lists
        // each list having a total of (countOfElementsPerSlice) elements
        for i := 0; i < totalListsToGenerate; i++ {
            mySlice := GenerateData(countOfElementsPerSlice)

            chunkSize := 10

            // if length of (mySlice) is 100 (total elements in the slice)
            // then break it down into chunks of (chunkSize) elements
            // sliceList is []Slice

            sliceList := mySlice.BreakSlice(chunkSize)

            for _, slice := range sliceList {
                // here length of (slice) will be 10
                fmt.Printf("\n---[slice]---\n\n")
                PrettyPrintData(slice)
                time.Sleep(500 * time.Millisecond)
                // push (slice) onto the return channel
                out <- slice
            }
        }
        close(out)
    }()
    return out
}

func GenerateData(countOfElements int) Slice {
    //myRandomList := Slice([]int{})
    myRandomList := make(Slice, 0)
    for i := 0; i < countOfElements; i++ {
        myRandomList = append(myRandomList, GetRandomNumber())
    }
    return myRandomList
}

func main() {
    fmt.Printf("\n----[sequential_processing]----\n\n")
    ProcessDataFromChannel()
}

func ProcessDataFromChannel() {

    totalListsToGenerate := 5
    countOfElementsPerSlice := 14
    dataChan := CreateDataChannelAndPushData(totalListsToGenerate, countOfElementsPerSlice)
    for {
        data, ok := <-dataChan
        if !ok {
            break
        }
        log.Printf("ProcessDataFromChannel() : received data from chan : %v", data)
    }
}

func GetRandomNumber() int {
    max := 900
    min := 100
    rand.Seed(time.Now().UnixNano())
    return rand.Intn(max-min) + min
}

func PrettyPrintData(data interface{}) {
    dataBytes, err := json.MarshalIndent(data, "", "    ")
    if err != nil {
        log.Printf("error : could not MarshalIndent json : %v", err.Error())
        return
    }
    fmt.Printf("\n%v\n\n", string(dataBytes))
}

func BreakIntoMultipleChunks(slice Slice, chunkSize int) []Slice {
    var chunks []Slice
    for i := 0; i < len(slice); i += chunkSize {
        end := i + chunkSize

        // necessary check to avoid slicing beyond slice capacity
        if end > len(slice) {
            end = len(slice)
        }

        chunks = append(chunks, slice[i:end])
    }

    return chunks
}
```

#### [Factory Design Pattern V1](#factory-design-pattern-v1)

Making HTTP Request To Different API Endpoints

```go
package main

import "net/http"

type HTTPClient interface {
    Do(req *http.Request) (*http.Response, error)
}
```

```go
package main

import "net/http"

type APIClient1 struct {
    Client *http.Client
}

func (c *APIClient1) Do(req *http.Request) (*http.Response, error) {
    // Customize request or authentication specific to API endpoint 1 if needed
    return c.Client.Do(req)
}

type APIClient2 struct {
    Client *http.Client
}

func (c *APIClient2) Do(req *http.Request) (*http.Response, error) {
    // Customize request or authentication specific to API endpoint 2 if needed
    return c.Client.Do(req)
}
```

```go
package main

import "net/http"

func HTTPClientFactory(apiEndpoint string) HTTPClient {
    switch apiEndpoint {
    case "api1":
        return &APIClient1{
            Client: &http.Client{},
        }

    case "api2":
        return &APIClient2{
            Client: &http.Client{},
        }

    default:
        // Return a default HTTP client or handle error accordingly
        return &http.Client{}
    }
}
```

```go
package main

import (
    "fmt"
    "io/ioutil"
)

func main() {
    // Replace this with your desired API endpoint
    apiEndpoint := "api1"

    // Create the HTTP client based on the selected API endpoint
    client := HTTPClientFactory(apiEndpoint)

    // Replace this with your desired API endpoint URL
    url := "https://api.example.com/endpoint"

    // Create an HTTP request
    req, err := http.NewRequest("GET", url, nil)
    if err != nil {
        fmt.Println("Error creating HTTP request:", err)
        return
    }

    // Make the HTTP request using the selected API client
    resp, err := client.Do(req)
    if err != nil {
        fmt.Println("Error making HTTP request:", err)
        return
    }
    defer resp.Body.Close()

    // Read the response body
    body, err := ioutil.ReadAll(resp.Body)
    if err != nil {
        fmt.Println("Error reading response body:", err)
        return
    }

    fmt.Println("Response:", string(body))
}
```

Sending Notification Via Different Methods (EMail/SMS)

```go
package main

type Notifier interface {
    SendNotification(message string) error
}
```

```go
package main

import "fmt"

type EmailNotifier struct {
    Email string
}

func (en *EmailNotifier) SendNotification(message string) error {
    // Implement the logic to send an email notification.
    fmt.Printf("Sending email to %s: %s\n", en.Email, message)
    return nil
}
```

```go
package main

import "fmt"

type SMSNotifier struct {
    PhoneNumber string
}

func (sn *SMSNotifier) SendNotification(message string) error {
    // Implement the logic to send an SMS notification.
    fmt.Printf("Sending SMS to %s: %s\n", sn.PhoneNumber, message)
    return nil
}
```

```go
package main

func NotifierFactory(notificationType string, recipient string) (Notifier, error) {
    switch notificationType {
    case "email":
        return &EmailNotifier{Email: recipient}, nil

    case "sms":
        return &SMSNotifier{PhoneNumber: recipient}, nil

    default:
        return nil, fmt.Errorf("unsupported notification type: %s", notificationType)
    }
}
```

```go
package main

import "fmt"

func main() {
    // Replace this with your desired notification type and recipient
    notificationType := "email"
    recipient := "user@example.com"

    // Create the notifier based on the selected notification type and recipient
    notifier, err := NotifierFactory(notificationType, recipient)
    if err != nil {
        fmt.Println("Error creating notifier:", err)
        return
    }

    // Send a sample notification
    message := "Hello, this is a test notification!"
    err = notifier.SendNotification(message)
    if err != nil {
        fmt.Println("Error sending notification:", err)
        return
    }
}
```

#### [Factory Design Pattern V2](#factory-design-pattern-v2)

Another Example Of Factory Design Pattern

```go
package main

type Function interface {
    Run(arg1, arg2, arg3 string) // Modify the argument types as per your needs
}
```

```go
package main

import "fmt"

type Function1 struct{}

func (f *Function1) Run(arg1, arg2, arg3 string) {
    fmt.Println("Running Function1 with arguments:", arg1, arg2, arg3)
}

type Function2 struct{}

func (f *Function2) Run(arg1, arg2, arg3 string) {
    fmt.Println("Running Function2 with arguments:", arg1, arg2, arg3)
}

type Function3 struct{}

func (f *Function3) Run(arg1, arg2, arg3 string) {
    fmt.Println("Running Function3 with arguments:", arg1, arg2, arg3)
}
```

```go
package main

func FunctionFactory(functionName string) Function {
    switch functionName {
    case "function1":
        return &Function1{}

    case "function2":
        return &Function2{}

    case "function3":
        return &Function3{}

    default:
        // Return a default function or handle error accordingly
        return nil
    }
}
```

```go
package main

import (
    "fmt"
)

func main() {
    // Replace this with your desired function name
    functionName := "function2"

    // Create the function based on the selected function name
    fn := FunctionFactory(functionName)
    if fn == nil {
        fmt.Println("Invalid function name:", functionName)
        return
    }

    // Call the function with multiple arguments
    arg1 := "Hello"
    arg2 := "Factory"
    arg3 := "Pattern"
    fn.Run(arg1, arg2, arg3)
}
```

One Of Many Operations That Can Be Invoked

```go
package main

type Operation interface {
    Execute()
}
```

```go
package main

import "fmt"

type Operation1 struct{}

func (o *Operation1) Execute() {
    fmt.Println("Executing Operation 1")
}

type Operation2 struct{}

func (o *Operation2) Execute() {
    fmt.Println("Executing Operation 2")
}

type Operation3 struct{}

func (o *Operation3) Execute() {
    fmt.Println("Executing Operation 3")
}
```

```go
package main

func OperationFactory(operationName string) Operation {
    switch operationName {
    case "operation1":
        return &Operation1{}

    case "operation2":
        return &Operation2{}

    case "operation3":
        return &Operation3{}

    default:
        // Return a default operation or handle error accordingly
        return nil
    }
}
```

```go
package main

import (
    "fmt"
)

func main() {
    // Replace this with your desired operation name
    operationName := "operation2"

    // Create the operation based on the selected operation name
    operation := OperationFactory(operationName)
    if operation == nil {
        fmt.Println("Invalid operation name:", operationName)
        return
    }

    // Execute the operation
    operation.Execute()
}
```

#### [Read Config File](#read-config-file)

```bash
go get github.com/go-ini/ini
```

`config.ini`

```ini
[database]
host = localhost
port = 5432
username = myuser
password = mypassword
```

`main.go`

```go
package main

import (
    "fmt"
    "log"

    "gopkg.in/ini.v1"
)

type DatabaseConfig struct {
    Host     string
    Port     int
    Username string
    Password string
}

func main() {
    // Load the config.ini file
    cfg, err := ini.Load("config.ini")
    if err != nil {
        log.Fatalf("Failed to read config file: %v", err)
    }

    // Parse the database section
    databaseSection := cfg.Section("database")

    // Get values from the database section
    host := databaseSection.Key("host").String()
    port, _ := databaseSection.Key("port").Int()
    username := databaseSection.Key("username").String()
    password := databaseSection.Key("password").String()

    // Create a DatabaseConfig instance with the parsed values
    dbConfig := DatabaseConfig{
        Host:     host,
        Port:     port,
        Username: username,
        Password: password,
    }

    // Print the configuration
    fmt.Println("Database Configuration:")
    fmt.Println("Host:", dbConfig.Host)
    fmt.Println("Port:", dbConfig.Port)
    fmt.Println("Username:", dbConfig.Username)
    fmt.Println("Password:", dbConfig.Password)
}
```

#### [Read YAML Config File](#read-yaml-config-file)

```bash
go get gopkg.in/yaml.v3
```

`config.yaml`

```yaml
database:
  host: localhost
  port: 5432
  username: myuser
  password: mypassword

api:
  endpoint: https://api.example.com
  key: abcdef123456

logging:
  level: info
  format: json
```

`main.go`

```go
package main

import (
    "fmt"
    "log"
    "os"

    "gopkg.in/yaml.v3"
)

type DatabaseConfig struct {
    Host     string `yaml:"host"`
    Port     int    `yaml:"port"`
    Username string `yaml:"username"`
    Password string `yaml:"password"`
}

type APIConfig struct {
    Endpoint string `yaml:"endpoint"`
    Key      string `yaml:"key"`
}

type LoggingConfig struct {
    Level  string `yaml:"level"`
    Format string `yaml:"format"`
}

type Config struct {
    Database DatabaseConfig `yaml:"database"`
    API      APIConfig      `yaml:"api"`
    Logging  LoggingConfig  `yaml:"logging"`
}

func main() {
    // Open the config.yaml file
    file, err := os.Open("config.yaml")
    if err != nil {
        log.Fatalf("Failed to open config file: %v", err)
    }
    defer file.Close()

    // Decode the YAML file into the Config struct
    var cfg Config
    decoder := yaml.NewDecoder(file)
    err = decoder.Decode(&cfg)
    if err != nil {
        log.Fatalf("Failed to decode config file: %v", err)
    }

    // Print the configuration
    fmt.Println("Database Configuration:")
    fmt.Println("Host:", cfg.Database.Host)
    fmt.Println("Port:", cfg.Database.Port)
    fmt.Println("Username:", cfg.Database.Username)
    fmt.Println("Password:", cfg.Database.Password)

    fmt.Println("\nAPI Configuration:")
    fmt.Println("Endpoint:", cfg.API.Endpoint)
    fmt.Println("Key:", cfg.API.Key)

    fmt.Println("\nLogging Configuration:")
    fmt.Println("Level:", cfg.Logging.Level)
    fmt.Println("Format:", cfg.Logging.Format)
}
```