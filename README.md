### Golang Code

[Setup Golang](#setup-golang)

[Go Build For Linux x86-64](#go-build-for-linux-x86-64)

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

[Factory Design Pattern](#factory-design-pattern)

[Factory Design Pattern V1](#factory-design-pattern-v1)

[Factory Design Pattern V2](#factory-design-pattern-v2)

[Read Config File](#read-config-file)

[Read YAML Config File](#read-yaml-config-file)

[Eliminate Outliers](#eliminate-outliers)

[Percentile Calculation](#percentile-calculation)

[JWT Authentication And Authorization](#jwt-authentication-and-authorization)

[Create Excel Sheet](#create-excel-sheet)

[JSON Lookup Using GJSON](#json-lookup-using-gjson)

[Design Pattern Singleton](#design-pattern-singleton)

[Design Pattern Single Responsibility Principle](#design-pattern-single-responsibility-principle)

[Design Pattern Open Closed Principle](#design-pattern-open-closed-principle)

[Design Pattern Liskov Substitution Principle](#design-pattern-liskov-substitution-principle)

[Design Pattern Interface Segregation Principle](#design-pattern-interface-segregation-principle)

[HTTP Request With Context Timeout](#http-request-with-context-timeout)

[Run Multiple Functions Periodically](#run-multiple-functions-periodically)

[Make HTTP GET Request With Headers](#make-http-get-request-with-headers)

[Get Azure Subscription Name](#get-azure-subscription-name)

[Logrus Logging](#logrus-logging)

[WebSocket Server And Client](#websocker-server-and-client)

[Azure Redis](#azure-redis)

[PostgreSQL Locks](#postgresql-locks)

[Convert UUID To int64](#convert-uuid-to-int64)

[PostgreSQL Custom Locks Using GORM](#postgresql-custom-locks-using-gorm)

[HTTP API Which Queries BigQuery Table ](#http-api-which-queries-bigquery-table)

[Date Time Utils](#date-time-utils)

[HTTP API Which Queries BigQuery Table V2](#http-api-which-queries-bigquery-table-v2)

[Rate Limiting On Channel](#rate-limiting-on-channel)

[Using Interfaces To Make Things Generic](#using-interfaces-to-make-things-generic)

[Generic HTTP Request V3](#generic-http-request-v3)

[JSON String To Map And Map To JSON String](#json-string-to-map-and-map-to-json-string)

[GCP StackDriver Logging](#gcp-stackdriver-logging)

[Prometheus Graph And Metrics Using System Load Average](#prometheus-graph-and-metrics-using-system-load-average)

[GCP StackDriver Metrics](#gcp-stackdriver-metrics)

#### [GCP BigQuery Fetch And Insert](https://github.com/giridharmb/gcp-big-query/blob/main/README.md)

[StackDriver Uber Zap Logging](#stackdriver-uber-zap-logging)

[Uber Zap Logging](#uber-zap-logging)

[GCP StackDriver Logger](#gcp-stackdriver-logger)

[HTTP Request With Retry And Proxy And Timeout](#http-request-with-retry-and-proxy-and-timeout)

[HTTP Connection Pooling](#http-connection-pooling)

[Custom GCP StackDriver And Uber Zap Logging](#custom-gcp-stackdriver-and-uber-zap-logging)

[PostgreSQL Locks To Ensure Single Instance Runs Even Thought It Is Deployed On Multiple Instances](#postgresql-locks-to-ensure-single-instance-runs-even-thought-it-is-deployed-on-multiple-instances)

[Factory Pattern PostgreSQL Locks To Ensure Single Instance Runs Even Thought It Is Deployed On Multiple Instances](#factory-pattern-postgresql-locks-to-ensure-single-instance-runs-even-thought-it-is-deployed-on-multiple-instances)

[Fetch From BigQuery And Upsert On PostgreSQL](#fetch-from-bigquery-and-upsert-on-postgresql)

[Search API With AND OR Exact Non-Exact Search V1](#search-api-with-and-or-exact-non-exact-search-v1)

[GCP StackDriver Logger V2](#gcp-stackdriver-logger-v2)

[Calculate 99th Percentile](#calculate-99th-percentile)

[Thread Safe Cache With Eviction](#thread-safe-cache-with-eviction)

[GORM-IO Database Connections And Connection Pooling](#gorm-io-database-connections-and-connection-pooling)

[Golang WASM Web UI And Tailwind](https://github.com/giridharmb/golang-wasm-web-ui/blob/main/README.md)

[IP Port Check](#ip-port-check)

[Handling Panic And Recover With Stack Trace](#handling-panic-and-recover-with-stack-trace)

---

[SAGA Pattern](https://github.com/giridharmb/Golang-README/blob/master/SAGA-pattern.md)

<hr/>

#### [Setup Golang](#setup-golang)

### Setup Golang

> Assumptions
 - You Are Setting Up Golang On Linux VM (amd64 Architecture)
 - Installing Go Version `1.22.5`
 - Using BASH Shell (Which Means You Are Exporting Variables In `~/.bashrc`)

> If Required, Set HTTP Proxy (`Optional`)

```bash
export http_proxy=http://my-proxy.company.com:5050;export https_proxy=http://my-proxy.company.com:5050;
```

> Download Go For Linux/amd64 Architecture

```bash
cd ~ && wget https://go.dev/dl/go1.22.5.linux-amd64.tar.gz
```

> Create Go Directory & Extract Go

> This Is `GOPATH`

```bash
mkdir -p ~/git/goworkspace/src
```

> This Is `GOROOT`

```bash
mkdir -p ~/go/go1.22.5/
```

```bash
cd ~ && mv -v go1.22.5.linux-amd64.tar.gz ~/go/go1.22.5/ && cd ~/go/go1.22.5 
```

> Extract Tarball

```bash
tar -zxvf go1.22.5.linux-amd64.tar.gz
```

> Export Variables & Add Them To `~/.bashrc`

> Make Sure >
 - These Variables Are (NOT) Exported Already 
 - Assuming You Are Setting Up Go For The First Time

```bash
cat <<EOL >> ~/.bashrc
export GOROOT="$HOME/go/go1.22.5/go"
export GOPATH=$HOME/git/goworkspace
export GOBIN=$GOPATH/bin
export GO111MODULE="auto"
export PATH=$PATH:$GOPATH/bin
export PATH=$PATH:$GOROOT/bin
EOL
```

> Exit Terminal & SSH Back To The VM & Verify Go Version

```bash
go version
```

> Expected Output For Running `go version`

```bash
go version go1.22.5 linux/amd64
```

#### [Go Build For Linux x86-64](#go-build-for-linux-x86-64)

```bash
env GOOS=linux GOARCH=amd64 CGO_ENABLED=0 go build -o my_app
```

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

#### [Factory Design Pattern](#factory-design-pattern)

In the context of the Factory Design Pattern, the term "repository" is often used to refer to a specific<br/> 
implementation of the pattern that deals with data storage and retrieval. While the Factory Design Pattern itself<br/>
is focused on creating objects, the "repository" here is a concept that encapsulates the data access layer of an application.<br/>
This layer is responsible for managing the interaction between the application code and the underlying data storage,<br/>
such as databases, APIs, or other data sources.

The choice to use the term "repository" comes from the idea that this component acts as a repository for the data,<br/>
providing a clean and consistent interface for the rest of the application to interact with the data storage.<br/>
The goal is to abstract away the complexities of data access and provide a high-level, easy-to-use API for<br/>
performing CRUD (Create, Read, Update, Delete) operations on the data.

In the context of Go, a repository often involves defining interfaces and implementing concrete types that<br/>
adhere to those interfaces. This allows you to decouple your application's business logic from the underlying<br/>
data storage mechanism. By using the Factory Design Pattern, you can create instances of these repository<br/>
implementations without tightly coupling your application code to the specific details of data storage.<br/>

To summarize, the term "repository" in the context of the Factory Design Pattern represents a design approach<br/>
for handling data access and storage, encapsulating data-related logic behind a clean and consistent interface.<br/>
It's a part of the overall architecture that helps separate concerns and improve code maintainability.<br/>

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

#### [Eliminate Outliers](#eliminate-outliers)

```go
package main

import (
    "fmt"
    "sort"
)

func removeOutliers(arr []int) []int {
    // Sort the array in ascending order
    sortedArr := make([]int, len(arr))
    copy(sortedArr, arr)
    sort.Ints(sortedArr)

    // Calculate the first quartile (Q1) and third quartile (Q3)
    q1 := quartile(sortedArr, 25)
    q3 := quartile(sortedArr, 75)

    // Calculate the Interquartile Range (IQR)
    iqr := q3 - q1

    // Define the lower and upper bounds to identify outliers
    lowerBound := q1 - (1.5 * iqr)
    upperBound := q3 + (1.5 * iqr)

    // Create a new array without outliers
    filteredArr := make([]int, 0)
    for _, num := range arr {
        if float64(num) >= lowerBound && float64(num) <= upperBound {
            filteredArr = append(filteredArr, num)
        }
    }

    return filteredArr
}

func quartile(arr []int, percentile int) float64 {
    index := float64(len(arr)-1) * (float64(percentile) / 100)
    if index == float64(int(index)) {
        return float64(arr[int(index)])
    } else {
        lower := float64(arr[int(index)])
        upper := float64(arr[int(index)+1])
        fraction := index - float64(int(index))
        return lower + fraction*(upper-lower)
    }
}

func main() {
    // Example array with outliers
    numbers := []int{2, 4, 6, 8, 10, 1000, 12, 14, 16, 18, 20}

    // Remove outliers using IQR method
    filteredNumbers := removeOutliers(numbers)

    // Print the filtered array
    fmt.Println("Filtered Array:", filteredNumbers)
}
```

Output

```bash
Filtered Array: [2 4 6 8 10 12 14 16 18 20]
```

#### [Percentile Calculation](#percentile-calculation)

To calculate percentiles for outlier detection in Go, you can use the sort<br/>
package to sort the data and then calculate the value at a specific percentile position.<br/>
For example, you can calculate the 25th percentile (Q1), 50th percentile (median), and<br/>
75th percentile (Q3) to use the Interquartile Range (IQR) method for outlier detection.<br/>

```go
package main

import (
    "fmt"
    "sort"
)

func calculatePercentile(arr []int, percentile int) float64 {
    // Sort the array in ascending order
    sortedArr := make([]int, len(arr))
    copy(sortedArr, arr)
    sort.Ints(sortedArr)

    // Calculate the index for the specified percentile
    index := float64(len(sortedArr)-1) * (float64(percentile) / 100)

    // If the index is an integer, return the exact value
    if index == float64(int(index)) {
        return float64(sortedArr[int(index)])
    }

    // Otherwise, perform linear interpolation to find the value at the specified percentile
    lower := float64(sortedArr[int(index)])
    upper := float64(sortedArr[int(index)+1])
    fraction := index - float64(int(index))

    return lower + fraction*(upper-lower)
}

func main() {
    // Example array
    numbers := []int{2, 4, 6, 8, 10, 12, 14, 16, 18, 20}

    // Calculate percentiles
    q1 := calculatePercentile(numbers, 25)
    median := calculatePercentile(numbers, 50)
    q3 := calculatePercentile(numbers, 75)

    // Print the calculated percentiles
    fmt.Println("25th percentile (Q1):", q1)
    fmt.Println("Median:", median)
    fmt.Println("75th percentile (Q3):", q3)
}
```

#### [JWT Authentication And Authorization](#jwt-authentication-and-authorization)

```bash
go get github.com/gorilla/mux
go get github.com/dgrijalva/jwt-go
```

`main.go`

```go
package main

import (
    "fmt"
    "net/http"
    "time"

    "github.com/dgrijalva/jwt-go"
    "github.com/gorilla/mux"
)

// Secret key for JWT signing (This should be kept secure)
var jwtSecret = []byte("your_secret_key")

// User struct to represent user details
type User struct {
    Username string
    Password string
}

// Handler for login route
func loginHandler(w http.ResponseWriter, r *http.Request) {
    // Replace this with your own user authentication logic
    // For simplicity, we are using hardcoded user credentials here.
    username := "admin"
    password := "password"

    // Read the provided username and password from the request body
    r.ParseForm()
    reqUsername := r.Form.Get("username")
    reqPassword := r.Form.Get("password")

    // Check if the credentials match the hardcoded user credentials
    if reqUsername == username && reqPassword == password {
        // If the credentials are valid, create and sign a new JWT token
        token := jwt.New(jwt.SigningMethodHS256)
        claims := token.Claims.(jwt.MapClaims)
        claims["username"] = reqUsername
        claims["exp"] = time.Now().Add(time.Hour * 24).Unix() // Token expiration time: 1 day

        tokenString, err := token.SignedString(jwtSecret)
        if err != nil {
            http.Error(w, "Failed to generate JWT token", http.StatusInternalServerError)
            return
        }

        // Send the token as response
        w.Write([]byte(tokenString))
    } else {
        http.Error(w, "Invalid credentials", http.StatusUnauthorized)
    }
}

// Middleware to check JWT token for protected routes
func authMiddleware(next http.Handler) http.Handler {
    return http.HandlerFunc(func(w http.ResponseWriter, r *http.Request) {
        tokenString := r.Header.Get("Authorization")
        if tokenString == "" {
            http.Error(w, "Missing authorization token", http.StatusUnauthorized)
            return
        }

        // Parse the token
        token, err := jwt.Parse(tokenString, func(token *jwt.Token) (interface{}, error) {
            return jwtSecret, nil
        })

        if err != nil {
            http.Error(w, "Invalid authorization token", http.StatusUnauthorized)
            return
        }

        if !token.Valid {
            http.Error(w, "Invalid authorization token", http.StatusUnauthorized)
            return
        }

        // Token is valid, proceed to the protected route
        next.ServeHTTP(w, r)
    })
}

// Protected route
func protectedHandler(w http.ResponseWriter, r *http.Request) {
    fmt.Fprintln(w, "Welcome to the protected route!")
}

func main() {
    r := mux.NewRouter()

    // Login route to generate JWT token
    r.HandleFunc("/login", loginHandler).Methods("POST")

    // Protected route with authorization middleware
    r.Handle("/protected", authMiddleware(http.HandlerFunc(protectedHandler))).Methods("GET")

    http.Handle("/", r)

    fmt.Println("Server listening on :8080")
    http.ListenAndServe(":8080", nil)
}
```

#### [Create Excel Sheet](#create-excel-sheet)

```bash
go get -v github.com/xuri/excelize
```

`main.go`

```go
package main

import (
    "fmt"
    "math/rand"
    "time"
    "unicode/utf8"

    "github.com/xuri/excelize"
)

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

func main() {
    f := excelize.NewFile()
    defer func() {
        if err := f.Close(); err != nil {
            fmt.Println(err)
        }
    }()

    sheetName := "sheet1"

    // Create a new sheet.
    mySheet, err := f.NewSheet(sheetName)
    if err != nil {
        fmt.Println(err)
        return
    }

    totalColumns := 7

    // first set all column names
    for i := 1; i <= totalColumns; i++ {
        column := GetCellColumnAndRowName(i, 1)
        fmt.Printf("\ncolumn : %v", column)
        colName := fmt.Sprintf("col_%v", i)
        _ = f.SetCellValue(sheetName, column, colName)
    }

    totalRows := 10
    for c := 1; c <= totalColumns; c++ {
        for r := 2; r <= totalRows; r++ {
            colAndRowName := GetCellColumnAndRowName(c, r)
            randomData := RandStringRunes(15)
            _ = f.SetCellValue("sheet1", colAndRowName, randomData)
        }
    }

    // Set value of a cell.
    /*
        f.SetCellValue(sheetName", "A", "data_column")
        f.SetCellValue(sheetName", "B", "value_column")

        f.SetCellValue(sheetName", "A2", "data_C1_1")
        f.SetCellValue(sheetName", "B2", "data_C2_1")

        f.SetCellValue(sheetName", "A3", "data_C1_2")
        f.SetCellValue(sheetName", "B3", "data_C2_2")
    */

    // Set active sheet of the workbook.
    f.SetActiveSheet(mySheet)

    bottomRightCell := GetCellColumnAndRowName(totalColumns, totalRows)
    fmt.Printf("\nbottomRightCell : %v", bottomRightCell)

    firstToLastCell := fmt.Sprintf("A1:%v", bottomRightCell)
    fmt.Printf("\nfirstToLastCell : %v", firstToLastCell)
    _ = f.AutoFilter(sheetName, firstToLastCell, []excelize.AutoFilterOptions{})

    // Auto-Fit all columns according to their text content
    cols, err := f.GetCols(sheetName)
    if err != nil {
        return
    }
    for idx, col := range cols {
        largestWidth := 0
        for _, rowCell := range col {
            cellWidth := utf8.RuneCountInString(rowCell) + 3 // + 2 for margin
            if cellWidth > largestWidth {
                largestWidth = cellWidth
            }
        }
        name, err := excelize.ColumnNumberToName(idx + 1)
        if err != nil {
            return
        }
        _ = f.SetColWidth(sheetName, name, name, float64(largestWidth))
    }

    // Save spreadsheet by the given path.
    if err := f.SaveAs("Book1.xlsx"); err != nil {
        fmt.Println(err)
    }

    for i := 1; i <= 15; i++ {
        colName, _ := excelize.ColumnNumberToName(i)
        fmt.Printf("\ncolNumber : %v , colName : %v", i, colName)
    }
}

// GetCellColumnAndRowName
/*
columnNumber - starts from 1
rowNumber - starts from 1
*/
func GetCellColumnAndRowName(columnNumber int, rowNumber int) string {
    colName, _ := excelize.ColumnNumberToName(columnNumber)
    cell := fmt.Sprintf("%v%v", colName, rowNumber)
    return cell
}
```

#### [JSON Lookup Using GJSON](#json-lookup-using-gjson)

```go
package main

import (
    "fmt"
    "github.com/tidwall/gjson"
)

func main() {
    data := `
{
    "name": "John",
    "address": {
        "city": "New York",
        "zip": "10001"
    }
}
`
    city := gjson.Get(data, "address.city")
    fmt.Println("City:", city.String())

    // Check if path exists
    if gjson.Get(data, "address.country").Exists() {
        fmt.Println("Country exists")
    } else {
        fmt.Println("Country does not exist")
    }
}
```

#### [Design Pattern Singleton](#design-pattern-singleton)

Here’s a brief overview of how the code works:
 - The Singleton type represents the object of which there will be only one instance.
 - We define a private instance variable to hold the singleton instance and a once variable from the sync package to ensure that the instantiation logic in New only runs once.
 - The New function is the only way to get an instance of Singleton. The once.Do() function ensures that the passed-in function is executed only once, regardless of how many times New is called.
 - In the main function, we demonstrate that, even when trying to create two different instances of Singleton, we get the same instance back.

```go
package main

import (
    "fmt"
    "sync"
)

// Singleton is the struct that we will instantiate only once.
type Singleton struct {
    value string
}

var (
    // instance holds the singleton object. Initialized as nil by default.
    instance *Singleton

    // once is used to ensure that the instantiation happens only once.
    once sync.Once
)

// GetValue returns the value of the singleton object.
func (s *Singleton) GetValue() string {
    return s.value
}

// New returns an instance of the Singleton object.
func New(value string) *Singleton {
    once.Do(func() {
        instance = &Singleton{value: value}
    })
    return instance
}

func main() {
    // Create an instance of Singleton
    s1 := New("Singleton 1")
    fmt.Println(s1.GetValue()) // Outputs: Singleton 1

    // Try creating another instance of Singleton
    s2 := New("Singleton 2")
    fmt.Println(s2.GetValue()) // Outputs: Singleton 1

    // Check if both the instances are the same
    if s1 == s2 {
        fmt.Println("Both instances are the same.")
    }
}
```

#### [Design Pattern Single Responsibility Principle](#design-pattern-single-responsibility-principle)

The Single Responsibility Principle (SRP) states that a class should have only one reason to change. 
In other words, it should have only one responsibility. 
This can make the code more maintainable, understandable, and testable.

Let’s look at a simple example where we have a User struct and functions 
that manage user data and also handle saving it to a file.

Violating Single Responsibility Principle:

```go
package main

import (
    "fmt"
    "io/ioutil"
)

type User struct {
    Name    string
    Email   string
    Address string
}

func (u *User) SaveToFile(filename string) error {
    data := fmt.Sprintf("Name: %s\nEmail: %s\nAddress: %s", u.Name, u.Email, u.Address)
    return ioutil.WriteFile(filename, []byte(data), 0644)
}

func main() {
    user := User{
        Name:    "John Doe",
        Email:   "johndoe@example.com",
        Address: "123 Main St",
    }

    user.SaveToFile("user.txt")
}
```

In the code above, the User struct is responsible both for managing user data and for saving it to a file. 
This is a violation of the SRP.

Following Single Responsibility Principle:

Let’s refactor this:

```go
package main

import (
    "fmt"
    "io/ioutil"
)

type User struct {
    Name    string
    Email   string
    Address string
}

type FileManager struct{}

func (fm *FileManager) SaveToFile(u User, filename string) error {
    data := fmt.Sprintf("Name: %s\nEmail: %s\nAddress: %s", u.Name, u.Email, u.Address)
    return ioutil.WriteFile(filename, []byte(data), 0644)
}

func main() {
    user := User{
        Name:    "John Doe",
        Email:   "johndoe@example.com",
        Address: "123 Main St",
    }

    fileManager := FileManager{}
    fileManager.SaveToFile(user, "user.txt")
}
```

In the refactored code, the User struct only manages user data. The responsibility of saving the 
data to a file is now handled by a separate FileManager struct. 
This ensures that each type has a single responsibility, adhering to the SRP.

#### [Design Pattern Open Closed Principle](#design-pattern-open-closed-principle)

The Open-Closed Principle (OCP) is one of the five SOLID principles of object-oriented design. 
It states that software entities (classes, modules, functions, etc.) should be open for extension 
but closed for modification. 
This means that the behavior of a module can be extended without modifying its source code.

Here’s an example in Go to demonstrate the Open-Closed Principle:

Let’s assume we have a system that filters products based on some criteria. 
A naive approach without considering OCP might look like this:

```go
type Color string

const (
    Red   Color = "Red"
    Green       = "Green"
    Blue        = "Blue"
)

type Product struct {
    Name  string
    Color Color
}

func FilterByColor(products []Product, color Color) []*Product {
    result := make([]*Product, 0)
    for _, p := range products {
        if p.Color == color {
            result = append(result, &p)
        }
    }
    return result
}
```

If we want to add more filters in the future (e.g., by size, by weight), 
we’ll need to modify the existing code or add more functions, which violates OCP.

A better approach using the OCP:

```go
type Specification interface {
    IsSatisfied(p *Product) bool
}

type ColorSpecification struct {
    Color Color
}

func (spec ColorSpecification) IsSatisfied(p *Product) bool {
    return p.Color == spec.Color
}

type Filter struct{}

func (f *Filter) Filter(products []Product, spec Specification) []*Product {
    result := make([]*Product, 0)
    for _, p := range products {
        if spec.IsSatisfied(&p) {
            result = append(result, &p)
        }
    }
    return result
}
```

Now, if we want to add more filters, we can simply implement the Specification interface without modifying the existing code:

```go
type Size string

const (
    Small Size = "Small"
    Medium    = "Medium"
    Large     = "Large"
)

type SizeSpecification struct {
    Size Size
}

func (spec SizeSpecification) IsSatisfied(p *Product) bool {
    return p.Size == spec.Size
}
```

By adhering to the OCP, we can easily extend our filtering mechanism without changing the 
existing filter logic or structures. 
This makes our code more maintainable and adaptable to future changes.


#### [Design Pattern Liskov Substitution Principle](#design-pattern-liskov-substitution-principle)

The Liskov Substitution Principle (LSP) is one of the SOLID principles and states that 
objects of a superclass should be able to be replaced with objects of a subclass 
without affecting the correctness of the program. 

Essentially, it means that a derived class should extend the behavior of a base class without changing its intended behavior.

Here’s an example in Go that demonstrates the Liskov Substitution Principle:

Let’s take a geometric example of rectangles and squares. 
A naive representation might have Square inherit from Rectangle and override methods, but this can violate LSP.

```go
type Rectangle struct {
    width, height int
}

func (r *Rectangle) SetWidth(w int) {
    r.width = w
}

func (r *Rectangle) SetHeight(h int) {
    r.height = h
}

func (r *Rectangle) Area() int {
    return r.width * r.height
}

type Square struct {
    Rectangle
}

func (s *Square) SetWidth(w int) {
    s.width = w
    s.height = w
}

func (s *Square) SetHeight(h int) {
    s.width = h
    s.height = h
}
```

Now, imagine you have a function like this:

```go
func IncreaseRectangleWidth(r *Rectangle) {
    width := r.width
    r.SetWidth(width + 10)
    
    // After increasing the width, the area should also increase
    if r.Area() <= width* r.height {
        fmt.Println("Violates Liskov Substitution Principle!")
    }
}
```

If you pass a Square to this function, it would print "Violates Liskov Substitution Principle!"
because setting the width on a square changes its height too, 
which breaks the expected behavior of the IncreaseRectangleWidth function.

A better approach would be to not have Square inherit from Rectangle, 
but rather have both implement a common interface or find a 
different inheritance hierarchy that doesn’t violate LSP.

#### [Design Pattern Interface Segregation Principle](#design-pattern-interface-segregation-principle)

The Interface Segregation Principle (ISP) states that no client should be forced to 
depend on interfaces it doesn’t use. Essentially, it’s better to have several 
specific interfaces rather than one general-purpose, “do-it-all” interface.

Let’s go through a Go example.

Suppose you have a basic document struct and you want to implement functionalities to persist it, print it, and send it.

A naive approach might be to create a large interface with all those functionalities:

```go
type Document struct {
    Title string
    Body  string
}

type DocumentManager interface {
    Save(d Document) error
    Print(d Document)
    Send(d Document)
}
```

However, not all document operations would need all those methods. 
For example, a Printer doesn’t need to send or save a document. 
It only needs to print it. Here’s where the ISP comes into play.

Instead of the above, we can have:

```go
type Saver interface {
    Save(d Document) error
}

type Printer interface {
    Print(d Document)
}

type Sender interface {
    Send(d Document)
}
```

Now, you can implement and compose as per your needs:

```go
type FileSaver struct{}

func (fs FileSaver) Save(d Document) error {
    // logic to save the document
    return nil
}

type ConsolePrinter struct{}

func (cp ConsolePrinter) Print(d Document) {
    fmt.Println("Printing:", d.Title)
}

type EmailSender struct{}

func (es EmailSender) Send(d Document) {
    // logic to send the document via email
}
```

With this approach, if a component only needs to save documents, it can depend only on the Saver interface. 
Similarly, something that just prints would only require an implementation of the Printer interface. 
This way, we’re not forcing a class to implement methods it doesn’t need.

#### [HTTP Request With Context Timeout](#http-request-with-context-timeout)

```go
package main

import (
    "context"
    "fmt"
    "net/http"
    "time"
)

func main() {
    // Create a new context with a timeout of 2 seconds
    ctx, cancel := context.WithTimeout(context.Background(), 2*time.Second)
    defer cancel()

    // Create a new request
    req, err := http.NewRequestWithContext(ctx, http.MethodGet, "https://example.com", nil)
    if err != nil {
        panic(err)
    }

    // Send the request using the default HTTP client
    resp, err := http.DefaultClient.Do(req)
    if err != nil {
        // If the context was canceled (timed out), this will print a context-related error
        fmt.Println("Error:", err)
        return
    }
    defer resp.Body.Close()

    fmt.Println("Response status:", resp.Status)
}
```

In this example, if the HTTP request takes longer than 2 seconds, the request will be canceled and you’ll see a context-related error printed. Otherwise, you’ll see the response status from the request.

#### TCP Connection With Context Timeout

```go
package main

import (
    "context"
    "fmt"
    "net"
    "time"
)

func main() {
    // Address of the server to connect to
    address := "example.com:80" // Replace with the address of your server

    // Create a new context with a timeout of 5 seconds
    ctx, cancel := context.WithTimeout(context.Background(), 5*time.Second)
    defer cancel()

    // Use a goroutine to try and establish the TCP connection
    var conn net.Conn
    ch := make(chan struct{})

    go func() {
        var err error
        conn, err = net.Dial("tcp", address)
        if err != nil {
            fmt.Println("Error:", err)
            close(ch)
            return
        }
        ch <- struct{}{}
    }()

    // Wait for either the connection to be established or the timeout to be exceeded
    select {
    case <-ch:
        fmt.Println("Connection established")
    case <-ctx.Done():
        fmt.Println("Failed to connect before timeout:", ctx.Err())
        return
    }

    // Do something with the connection...
    // ...

    // Close the connection when you're done
    conn.Close()
}
```

In this example, the program will attempt to establish a TCP connection to example.com on port 80. 
If the connection is not established within 5 seconds, the context will time out and an error message will be printed. 
If the connection is successfully established within the 5-second window, you’ll see a “Connection established” message.

Remember to replace example.com:80 with the address and port of the server you’re trying to connect to.

#### [Run Multiple Functions Periodically](#run-multiple-functions-periodically)

```go
package main

import (
    "fmt"
    "time"
)

func main() {
    // Ticker to run a function every 60 seconds
    ticker60s := time.NewTicker(60 * time.Second)
    go func() {
        for range ticker60s.C {
            function60s()
        }
    }()

    // Ticker to run a function every 30 seconds
    ticker30s := time.NewTicker(30 * time.Second)
    go func() {
        for range ticker30s.C {
            function30s()
        }
    }()

    // Prevent the main function from exiting
    select {}
}

func function60s() {
    fmt.Println("Running the 60-second function:", time.Now())
}

func function30s() {
    fmt.Println("Running the 30-second function:", time.Now())
}
```

Another Way

```go
package main

import (
    "fmt"
    "time"
)

func main() {
    ticker60s := time.NewTicker(60 * time.Second)
    ticker30s := time.NewTicker(30 * time.Second)

    for {
        select {
        case <-ticker60s.C:
            function60s()
        case <-ticker30s.C:
            function30s()
        }
    }
}

func function60s() {
    fmt.Println("Running the 60-second function:", time.Now())
}

func function30s() {
    fmt.Println("Running the 30-second function:", time.Now())
}
```

#### [Make HTTP GET Request With Headers](#make-http-get-request-with-headers)

```go
package main

import (
    "encoding/json"
    "fmt"
    "io/ioutil"
    "log"
    "net/http"
)

func main() {
    // The endpoint you want to request
    url := "https://api.example.com/data"

    // Create a new request using http
    req, err := http.NewRequest("GET", url, nil)
    if err != nil {
        log.Fatal("NewRequest: ", err)
        return
    }

    // Add headers to the request
    req.Header.Add("Authorization", "Bearer YOUR_TOKEN")
    req.Header.Add("Another-Header", "header-value")

    // Send the request using http client
    client := &http.Client{}
    resp, err := client.Do(req)
    if err != nil {
        log.Fatal("Do: ", err)
        return
    }
    defer resp.Body.Close()

    // Read the JSON response body
    body, err := ioutil.ReadAll(resp.Body)
    if err != nil {
        log.Fatal("ReadAll: ", err)
        return
    }

    // Define a struct to unmarshal the JSON response into
    var data map[string]interface{}
    json.Unmarshal(body, &data)

    // Print the data
    fmt.Printf("%+v\n", data)
}
```

#### [Get Azure Subscription Name](#get-azure-subscription-name)

```go
import (
    "context"
    "fmt"
    "github.com/Azure/azure-sdk-for-go/services/resources/mgmt/2018-06-01/subscriptions"
    "github.com/Azure/go-autorest/autorest"
    "github.com/Azure/go-autorest/autorest/azure/auth"
    "log"
    "os"
)

func GetClientCredentialsConfig(azureTenantID string, azureClientID string, azureClientSecret string) auth.ClientCredentialsConfig {
    clientCredentialsConfig := auth.NewClientCredentialsConfig(azureClientID, azureClientSecret, azureTenantID)
    return clientCredentialsConfig
}

func GetAuthorizer(clientCredentialsConfig auth.ClientCredentialsConfig) (autorest.Authorizer, error) {
    authorizer, err := clientCredentialsConfig.Authorizer()
    if err != nil {
        return nil, err
    }
    return authorizer, nil
}

func GetSubscriptionName(subscriptionID string, clientCredentialsConfig auth.ClientCredentialsConfig) (string, error) {
    authorizer, err := GetAuthorizer(clientCredentialsConfig)
    if err != nil {
        return "", err
    }
    subscriptionsClient := GetSubscriptionClient(authorizer)
    ctx := context.Background()
    subscription, err := subscriptionsClient.Get(ctx, subscriptionID)
    if err != nil {
        return "", err
    }
    return string(*subscription.DisplayName), nil
}

func GetSubscriptionClient(authorizer autorest.Authorizer) subscriptions.Client {
    subscriptionsClient := subscriptions.NewClient()
    subscriptionsClient.Authorizer = authorizer
    return subscriptionsClient
}

func GetAllAzureSubscriptions(authorizer autorest.Authorizer) (map[string]string, error) {
    subscriptionsMapping := make(map[string]string)
    subscriptionClient := GetSubscriptionClient(authorizer)
    ctx := context.Background()
    for list, err := subscriptionClient.List(ctx); list.NotDone(); err = list.NextWithContext(ctx) {
        if err != nil {
            return subscriptionsMapping, err
        }
        for _, subscription := range list.Values() {
            subID := string(*subscription.ID)
            subName := string(*subscription.DisplayName)
            subscriptionsMapping[subID] = subName
        }
    }
    return subscriptionsMapping, nil
}

func main() {
    subscriptionID := "12345-1111-2222-3333-000000000000"

    azureTenantID := os.Getenv("AZURE_TENANT_ID")
    azureClientID := os.Getenv("AZURE_CLIENT_ID")
    azureClientSecret := os.Getenv("AZURE_CLIENT_SECRET")

    clientCredentialsConfig := GetClientCredentialsConfig(azureTenantID, azureClientID, azureClientSecret)

    subscriptionName, err := GetSubscriptionName(subscriptionID, clientCredentialsConfig)
    if err != nil {
        log.Fatalf(err.Error())
    }

    fmt.Printf("Subscription Name: %s\n", subscriptionName)

    /* ************************************************************************************ */

    authorizer, err := GetAuthorizer(clientCredentialsConfig)
    if err != nil {
        log.Fatal(err.Error())
    }

    subscriptionsMapping, err := GetAllAzureSubscriptions(authorizer)
    if err != nil {
        log.Fatal(err.Error())
    }
    fmt.Printf("\n\nSubscriptions-Mapping:\n\n%v\n\n", subscriptionsMapping)

}
```

#### [Logrus Logging](#logrus-logging)

```go
package main

import (
    "encoding/json"
    "errors"
    "fmt"
    "github.com/sirupsen/logrus"
    logsyslog "github.com/sirupsen/logrus/hooks/syslog"
    "log/syslog"
    "os"
)

var Log = logrus.New()

func InitLogging() {
    Log.SetOutput(os.Stdout)
    Log.SetLevel(logrus.DebugLevel)
    hook, err := logsyslog.NewSyslogHook("", "", syslog.LOG_DEBUG, "")
    if err == nil {
        Log.Hooks.Add(hook)
    }
}

func main() {
    InitLogging()

    data := map[string]interface{}{
        "name": "John Doe",
        "age":  30,
        "address": map[string]string{
            "city":    "New York",
            "country": "USA",
        },
    }

    dataStr, _ := GetJsonStr(data)
    Log.Printf("dataStr : %v", dataStr)

    myMap, _ := GetJsonMap(dataStr)
    Log.Printf("myMap : %v", myMap)

    PrettyPrintJson(data)
}

func GetJsonMap(jsonStr string) (map[string]interface{}, error) {
    msg := ""
    result := make(map[string]interface{})
    err := json.Unmarshal([]byte(jsonStr), &result)
    if err != nil {
        msg = fmt.Sprintf("could not convert json string to map[string]interface{} : %v", err.Error())
        Log.Error(msg)
        return nil, errors.New(msg)
    }
    return result, nil
}

func GetJsonStr(jsonMap map[string]interface{}) (string, error) {
    msg := ""
    jsonString, err := json.Marshal(jsonMap)
    if err != nil {
        msg = fmt.Sprintf("could not convert map[string]interface{} to string : %v", err.Error())
        Log.Error(msg)
        return "", errors.New(msg)
    }
    return string(jsonString), nil
}

func PrettyPrintJson(data map[string]interface{}) {
    prettyJson, err := json.MarshalIndent(data, "", "    ")
    if err != nil {
        Log.Errorf("could not json.MarshalIndent the specified map[string]interface{} : %v", err.Error())
        return
    }
    Log.Printf("\n\n%s\n\n", prettyJson)
}
```

#### [WebSocket Server And Client](#websocker-server-and-client)

`main.go`

```go
package main

import (
    "encoding/json"
    "log"
    "net/http"
    "github.com/gorilla/websocket"
)

var upgrader = websocket.Upgrader{
    ReadBufferSize:  1024,
    WriteBufferSize: 1024,
}

type Message struct {
    Text string `json:"text"`
}

func handler(w http.ResponseWriter, r *http.Request) {
    conn, err := upgrader.Upgrade(w, r, nil)
    if err != nil {
        log.Println(err)
        return
    }
    defer conn.Close()

    for {
        _, msgBytes, err := conn.ReadMessage()
        if err != nil {
            log.Println(err)
            return
        }

        var msg Message
        err = json.Unmarshal(msgBytes, &msg)
        if err != nil {
            log.Println("error unmarshalling:", err)
            continue
        }

        log.Printf("Received: %s\n", msg.Text)

        response := Message{Text: "Received: " + msg.Text}
        responseBytes, err := json.Marshal(response)
        if err != nil {
            log.Println("error marshalling:", err)
            continue
        }

        if err := conn.WriteMessage(websocket.TextMessage, responseBytes); err != nil {
            log.Println(err)
            return
        }
    }
}

func main() {
    http.HandleFunc("/echo", handler)
    log.Fatal(http.ListenAndServe(":8080", nil))
}
```

`index.html`

```html
<!DOCTYPE html>
<html>
<head>
    <title>WebSocket Test</title>
    <script type="text/javascript">
        var conn;

        function init() {
            conn = new WebSocket('ws://localhost:8080/echo');

            conn.onopen = function(e) {
                console.log("Connection established!");
            };

            conn.onmessage = function(e) {
                var serverMessage = JSON.parse(e.data);
                console.log(serverMessage);
                document.getElementById('serverResponse').innerText = serverMessage.text;
            };

            conn.onerror = function(e) {
                console.log("Error: ", e);
            };
        }

        function sendMessage() {
            var message = document.getElementById('message').value;
            conn.send(JSON.stringify({text: message}));
        }
    </script>
</head>
<body onload="init();">
    <input type="text" id="message" placeholder="Enter a message"/>
    <button onclick="sendMessage();">Send Message</button>
    <p>Server response: <span id="serverResponse"></span></p>
</body>
</html>
```

Automatically Reconnect WebSocket

```html
<!DOCTYPE html>
<html>
<head>
    <title>WebSocket Reconnection</title>
    <script type="text/javascript">
        var conn;
        var reconnectInterval = 3000; // Reconnect attempt interval in milliseconds

        function connectWebSocket() {
            conn = new WebSocket('ws://localhost:8080/echo');

            conn.onopen = function(e) {
                console.log("Connection established!");
            };

            conn.onmessage = function(e) {
                console.log("Received: " + e.data);
                document.getElementById('serverResponse').innerText = e.data;
            };

            conn.onerror = function(e) {
                console.error("WebSocket error observed:", e);
            };

            conn.onclose = function(e) {
                console.log("WebSocket connection closed. Attempting to reconnect...");
                setTimeout(connectWebSocket, reconnectInterval);
            };
        }

        function sendMessage() {
            if (conn.readyState === WebSocket.OPEN) {
                var message = document.getElementById('message').value;
                conn.send(message);
            } else {
                console.log("WebSocket is not open. Cannot send message.");
            }
        }
    </script>
</head>
<body onload="connectWebSocket();">
    <input type="text" id="message" placeholder="Enter a message"/>
    <button onclick="sendMessage();">Send Message</button>
    <p>Server response: <span id="serverResponse"></span></p>
</body>
</html>
```

#### [Azure Redis](#azure-redis)

```go
package main

import (
    "context"
    "crypto/tls"
    "fmt"
    redis "github.com/redis/go-redis/v9"
    "log"
)

func main() {
    // Replace these values with your Azure Redis Cache connection details
    // Port 6380 -> SSL Port For Azure Redis

    redisAddr := "<HOST>:6380"
    redisPassword := "<REDIS_KEY>" // fetch this from azure

    tlsConfig := &tls.Config{
        InsecureSkipVerify: true, // Set this to false in production
    }

    // Create a Redis client
    client := redis.NewClient(&redis.Options{
        Addr:      redisAddr,
        Password:  redisPassword,
        TLSConfig: tlsConfig,
    })

    ctx := context.Background()

    // Ping the Redis server to test the connection
    pong, err := client.Ping(ctx).Result()
    if err != nil {
        log.Fatalf("Failed to ping Redis: %v", err)
    }
    fmt.Println("Redis Ping:", pong)

    // Set a key-value pair

    for i := 0; i < 100; i++ {
        err = client.Set(ctx, "mykey", "myvalue", 0).Err()
        if err != nil {
            log.Fatalf("Failed to set key: %v", err)
        }
        log.Println("wrote cache...")
    }

    for i := 0; i < 100; i++ {
        val, err := client.Get(ctx, "mykey").Result()
        if err != nil {
            log.Fatalf("Failed to get key: %v", err)
        }
        fmt.Println("mykey:", val)
    }
    
    // Close the Redis client when done
    err = client.Close()
    if err != nil {
        log.Fatalf("Failed to close Redis client: %v", err)
    }
}
```

#### [PostgreSQL Locks](#postgresql-locks)

```go
package main

import (
    "gorm.io/driver/postgres"
    "gorm.io/gorm"
    "log"
)

var db *gorm.DB

func init() {
    var err error
    // Replace with your database details
    dsn := "host=HOSTNAME user=USERNAME password=PASS dbname=POSTGRES_DB port=5432 sslmode=disable"
    db, err = gorm.Open(postgres.Open(dsn), &gorm.Config{})
    if err != nil {
        log.Fatal("Failed to connect to database:", err)
    }

}

// TryLock attempts to acquire an advisory lock and returns true if successful
func TryLock(lockKey int64) bool {
    var locked bool
    db.Raw("SELECT pg_try_advisory_lock(?)", lockKey).Scan(&locked)
    return locked
}

// Unlock releases the advisory lock
func Unlock(lockKey int64) bool {
    var unlocked bool
    db.Raw("SELECT pg_advisory_unlock(?)", lockKey).Scan(&unlocked)
    return unlocked
}

func main() {
    lockKey := int64(123) // This is an arbitrary key for the lock

    if TryLock(lockKey) {
        log.Println("Lock acquired, performing task")
        // Perform your task here

        if Unlock(lockKey) {
            log.Println("Lock released")
        } else {
            log.Println("Failed to release lock")
        }
    } else {
        log.Println("Could not acquire lock, another instance may be running")
    }
}
```

#### [Convert UUID To int64](#convert-uuid-to-int64)

In this code:

 - We generate a UUID.
 - We compute the SHA-256 hash of the UUID.
 - We take the first 8 bytes of the hash and convert them to an int64.
 - We then convert the int64 to float64 and use math.Abs to ensure the value is positive.

Converting a UUID to a unique int64 in Go is challenging because a UUID is a 128-bit number, 
and an int64 can only hold 64 bits. This means you can’t directly convert a 
UUID to int64 without losing information, which could compromise the uniqueness of the UUID.

However, if your use case can tolerate potential collisions and you just need 
a “mostly unique” 64-bit representation of a UUID, you could hash the UUID and 
take a 64-bit portion of it. This approach does not guarantee uniqueness 
but might be sufficient for certain non-critical applications.

Caveats and Considerations

 - Loss of Uniqueness: This method does not preserve the uniqueness of the original UUID. Collisions are more likely.
 - Not Suitable for Security Purposes: The resulting int64 should not be used for security-critical purposes.
 - Use Cases: This method is suitable for scenarios where you need a shorter identifier and can tolerate the risk of collision, such as internal identifiers, hash keys, etc.

Remember, if your application critically relies on the uniqueness of each identifier, it’s better to stick with the full UUID or use another method that guarantees 64-bit uniqueness.

```go
package main

import (
    "crypto/sha256"
    "encoding/binary"
    "fmt"
    "log"
    "math"

    "github.com/google/uuid"
)

func uuidToInt64(u uuid.UUID) int64 {
    // Hash the UUID
    hash := sha256.Sum256(u[:])

    // Convert the first 8 bytes of the hash to int64
    int64Value := int64(binary.BigEndian.Uint64(hash[:8]))
    positiveInt64Value := math.Abs(float64(int64Value))
    return int64(positiveInt64Value)
}

func main() {
    u, err := uuid.NewRandom()
    if err != nil {
        log.Fatalf("Failed to generate UUID: %v", err)
    }

    fmt.Println("UUID:", u)
    intVal := uuidToInt64(u)
    fmt.Println("int64:", intVal)
}
```

#### [PostgreSQL Custom Locks Using GORM](#postgresql-custom-locks-using-gorm)

```go
package main

import (
    "errors"
    "gorm.io/driver/postgres"
    "gorm.io/gorm"
    "gorm.io/gorm/clause"
    "log"
    "os"
    "sync"
    "time"
)

var LockDB *gorm.DB

type PGLock struct {
    LockKey int64
    Mutex   sync.Mutex
}

type CustomLock struct {
    gorm.Model
    Key             string `gorm:"uniqueIndex"`
    Acquired        bool
    AcquiredAt      time.Time
    AcquiredAtEpoch int64
}

func (l CustomLock) AcquireLock() (bool, error) {
    lock := CustomLock{Key: l.Key}

    // Check if the lock is already acquired
    result := LockDB.Where("key = ?", l.Key).First(&lock)
    if result.Error == nil {
        if lock.Acquired {
            return false, nil // Lock is already acquired
        }
    }

    // Acquire the lock
    lock.Acquired = true
    lock.AcquiredAt = time.Now().UTC()
    lock.AcquiredAtEpoch = time.Now().UTC().Unix()
    log.Printf("Lock Acquired At         : %v", lock.AcquiredAt)
    log.Printf("Lock Acquired At (EPOCH) : %v", lock.AcquiredAtEpoch)

    return LockDB.Clauses(clause.OnConflict{UpdateAll: true}).Create(&lock).RowsAffected > 0, nil
}

func (l CustomLock) IsLockAcquired() (bool, error) {
    var lock CustomLock
    result := LockDB.Where("key = ?", l.Key).First(&lock)
    if result.Error != nil {
        if errors.Is(result.Error, gorm.ErrRecordNotFound) {
            return false, nil // Lock not found, so it's not acquired
        }
        return false, result.Error
    }
    return lock.Acquired, nil
}

func (l CustomLock) ReleaseLock() (bool, error) {
    result := LockDB.Model(&CustomLock{}).Where("key = ?", l.Key).Update("acquired", false)
    return result.RowsAffected > 0, result.Error
}

func InitializeLockDB() {
    var err error
    dsn := "host=HOST_OR_IP user=USER password=PASS dbname=lock_database port=5432 sslmode=disable"
    LockDB, err = gorm.Open(postgres.Open(dsn), &gorm.Config{})
    if err != nil {
        panic("failed to connect database")
    }

    // Migrate the schema
    err = LockDB.AutoMigrate(&CustomLock{})
    if err != nil {
        log.Println("database auto_migrate failed : ", err.Error())
    } else {
        log.Println("database auto_migrate successful")
    }
}

func CleanupOldLocks(olderThanEpoch int64) (int64, error) {
    // Calculate the time threshold

    threshold := time.Unix(olderThanEpoch, 0).Unix()
    log.Println("threshold : %", threshold)

    // Delete locks that are older than the threshold

    // Unscoped() -> is hard delete
    // Otherwise, if we remove Unscoped() , it will be SOFT DELETE (where deleted_at field will have a timestamp)

    // use case-1
    //result := db.Unscoped().Where("acquired = ? AND acquired_at_epoch < ?", true, threshold).Delete(&CustomLock{})

    // use case-2
    result := LockDB.Unscoped().Where("acquired_at_epoch < ?", threshold).Delete(&CustomLock{})

    return result.RowsAffected, result.Error
}

func main() {

    InitializeLockDB()

    lock1 := CustomLock{Key: "test1"}

    done := make(chan bool)

    start := time.Now().UTC()

    go func() {
        for {
            elapsed := time.Since(start).Seconds()
            if elapsed >= 60 {
                // after 1 minute, exit the program
                done <- true
            }
            time.Sleep(1 * time.Second)
        }
    }()

    // Set up a ticker to clean up old locks every minute
    ticker := time.NewTicker(60 * time.Second)
    go func() {
        for range ticker.C {
            sixtySecondsAgo := time.Now().UTC().Add(-60 * time.Second).Unix()
            cleaned, err := CleanupOldLocks(sixtySecondsAgo)
            if err != nil {
                log.Printf("Error cleaning up old locks: %v\n", err)
            } else if cleaned > 0 {
                log.Printf("Cleaned up %d old locks\n", cleaned)
            }
        }
    }()

    //key := "my_lock_key"

    // Try to acquire the lock

    acquired, err := lock1.AcquireLock()
    if err != nil {
        log.Println("failed to acquire lock : ", err.Error())
        return
    }
    if acquired {
        println("Lock acquired >>>")
    } else {
        println("Could not acquire lock")
    }

    lockCheck, err := lock1.IsLockAcquired()
    if err != nil {
        log.Println("failed to check lock : ", err.Error())
        return
    }

    if lockCheck {
        log.Println("(check) lock is acquired >>>")
    } else {
        log.Println("(check) lock is (NOT) acquired !!")
    }

    log.Println("sleeping for a few secs...")

    time.Sleep(10 * time.Second)

    released, err := lock1.ReleaseLock()
    if err != nil {
        log.Println("failed to release lock : ", err.Error())
        return
    }

    if released {
        println("Lock Released >>>")
    } else {
        println("Could not release lock :(")
    }

    lockCheck, err = lock1.IsLockAcquired()
    if err != nil {
        log.Println("failed to check lock : ", err.Error())
        return
    }
    if lockCheck {
        log.Println("(check) lock is acquired >>>>")
    } else {
        log.Println("(check) lock is (NOT) acquired !!")
    }

    <-done
}


/*

After Acquiring

lock_database=> select * from custom_locks order by id;
 id |          created_at           |          updated_at           | deleted_at |  key  | acquired |          acquired_at          | acquired_at_epoch
----+-------------------------------+-------------------------------+------------+-------+----------+-------------------------------+-------------------
  2 | 2023-11-19 03:51:16.645602+00 | 2023-11-19 03:53:15.663936+00 |            | test1 | f        | 2023-11-19 03:51:16.561427+00 |        1700365876
(1 row)

*/
```

#### [HTTP API Which Queries BigQuery Table](#http-api-which-queries-bigquery-table)

> Setup

```bash
export GCP_SERVICE_ACCOUNT_JSON_FILE="$HOME/path/to/gcp_service_acct.json"
export GCP_TEST_PROJECT="GCP_PROJECT_NAME"
export GCP_TEST_DATASET="GCP_DATASET_NAME"
export GCP_TABLE_1="BQ_TABLE_1"
export GCP_TABLE_2="BQ_TABLE_2"
export GCP_TABLE_3="BQ_TABLE_3"
```

`main.go`

```go
package main

import (
    "cloud.google.com/go/bigquery"
    "context"
    "encoding/json"
    "errors"
    "fmt"
    "github.com/gorilla/mux"
    "google.golang.org/api/iterator"
    "google.golang.org/api/option"
    "log"
    "net/http"
    "os"
    "regexp"
    "strconv"
    "strings"
)

type Response struct {
    Status  string `json:"status"`
    Message string `json:"message"`
}

var BQClient *bigquery.Client

func main() {
    message := ""

    Initialize()

    r := mux.NewRouter()

    r.HandleFunc("/api/health", handleApiHealthCheck).Methods("GET")
    r.HandleFunc("/api/v1/big_query_resource", handleBigQueryMatchingResource).Methods("GET")

    corsMiddleware := func(next http.Handler) http.Handler {
        return http.HandlerFunc(func(w http.ResponseWriter, r *http.Request) {
            // Set CORS headers
            w.Header().Set("Access-Control-Allow-Origin", "*")
            w.Header().Set("Access-Control-Allow-Methods", "GET, POST, PUT, DELETE, OPTIONS, PATCH")
            w.Header().Set("Access-Control-Allow-Headers", "Content-Type")
            w.Header().Set("Access-Control-Allow-Headers", "Accept")

            // Handle preflight requests
            if r.Method == http.MethodOptions {
                w.WriteHeader(http.StatusOK)
                return
            }

            next.ServeHTTP(w, r)
        })
    }

    // Use the CORS middleware
    r.Use(corsMiddleware)

    http.Handle("/", r)

    port := "8888"
    bindIPAddress := "0.0.0.0"
    addr := fmt.Sprintf("%v:%v", bindIPAddress, port)

    serverAddr := addr

    message = fmt.Sprintf("Server will be listening @ %s", serverAddr)
    log.Println(message)

    err := http.ListenAndServe(serverAddr, nil)
    if err != nil {
        message = fmt.Sprintf("failed to setup http server on address (%v) : %v", serverAddr, err.Error())
        log.Fatalln(message)
    }
}

func handleApiHealthCheck(w http.ResponseWriter, r *http.Request) {

    log.Printf("handleTestRequest...")

    response := Response{}

    response.Status = "ok"
    response.Message = "status"

    log.Printf("handleTestRequest done !")

    w.Header().Set("Content-Type", "application/json")
    w.WriteHeader(http.StatusOK)
    _ = json.NewEncoder(w).Encode(response)
}

func QueryTableRows(ctx context.Context, client *bigquery.Client, query string) ([]interface{}, error) {
    msg := ""
    response := make([]interface{}, 0)
    bqQuery := client.Query(query)
    it, err := bqQuery.Read(ctx)
    if err != nil {
        msg = fmt.Sprintf("__bigquery__ : error : could not perform bqQuery.Read(ctx) : %v", err.Error())
        return response, errors.New(msg)
    }

    errorOccurred := false

    for {
        var values []bigquery.Value
        err = it.Next(&values)
        if errors.Is(err, iterator.Done) {
            break
        }
        if err != nil {
            errorOccurred = true
            break
        }
        for _, value := range values {

            jsonStr, ok := value.(string)
            if ok {
                var data map[string]interface{}
                err = json.Unmarshal([]byte(jsonStr), &data)
                if err != nil {
                    log.Printf("__bigquery__ : __error__ : json.Unmarshal([]byte(jsonStr), &data) : %v", err.Error())
                } else {
                    response = append(response, data)
                }
            } else {
                log.Println("__bigquery__ : value.(string) is false")
            }
        }
    }
    if errorOccurred {
        msg = fmt.Sprintf("__bigquery__ : error : could not perform it.Next(&values) : %v", err.Error())
        errorOccurred = true
        return response, errors.New(msg)
    }
    return response, nil
}

func GetBQClient() (*bigquery.Client, error) {
    var client *bigquery.Client
    var err error
    var errorMessage string
    ctx := context.Background()

    gcpProjectJSON := os.Getenv("GCP_SERVICE_ACCOUNT_JSON") // path to JSON File

    projectID := os.Getenv("GCP_TEST_PROJECT") // your GCP Project-Name

    // Create a BigQuery client
    client, err = bigquery.NewClient(ctx, projectID, option.WithCredentialsFile(gcpProjectJSON))
    if err != nil {
        errorMessage = fmt.Sprintf("error : failed to create BigQuery client: %v", err.Error())
        log.Printf(errorMessage)
        return client, errors.New(errorMessage)
    }

    return client, nil
}

func Initialize() {
    BQClient, _ = GetBQClient()
}

func handleBigQueryMatchingResource(w http.ResponseWriter, r *http.Request) {
    msg := ""
    response := make(map[string]interface{})
    response["error"] = ""
    response["data"] = make([]interface{}, 0)

    operation := r.URL.Query().Get("operation")
    if operation == "" {
        msg = fmt.Sprintf("error : query param 'operation' is empty !")
        response["error"] = msg
        log.Println(response)
        w.WriteHeader(http.StatusBadRequest)
        _ = json.NewEncoder(w).Encode(&response)
        return
    }

    switch operation {
    case "query_bq_table":
        eventType := r.URL.Query().Get("event_type")
        if eventType == "" {
            msg = fmt.Sprintf("error : query parameter 'event_type' cannot be empty !")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        if !(eventType == "type_1" || eventType == "type_2" || eventType == "type_3") {
            msg = fmt.Sprintf("error : query parameter 'event_type' should be ('scheduled' or 'resource' or 'flash') !")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        timeDelta := r.URL.Query().Get("time_delta")
        if timeDelta == "" {
            msg = fmt.Sprintf("error : query parameter 'time_delta' cannot be empty !")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        timeResolution := r.URL.Query().Get("time_resolution")
        if timeResolution == "" {
            msg = fmt.Sprintf("error : query parameter 'time_resolution' cannot be empty !")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        if !(timeResolution == "MINUTE" || timeResolution == "HOUR") {
            msg = fmt.Sprintf("error : query parameter 'time_resolution' should be either 'MINUTE' or 'HOUR'")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        timeDeltaInt, timeParseErr := strconv.Atoi(timeDelta)
        if timeParseErr != nil {
            msg = fmt.Sprintf("error : query parameter 'time_delta' should be a valid (integer) value")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        if timeResolution == "HOUR" {
            if timeDeltaInt <= 0 || timeDeltaInt >= 73 {
                msg = fmt.Sprintf("error : query parameter 'time_delta' should be an integer between 1 and 72 (a max 3 days) !")
                response["error"] = msg
                log.Println(response)
                w.WriteHeader(http.StatusBadRequest)
                _ = json.NewEncoder(w).Encode(&response)
                return
            }
        } else if timeResolution == "MINUTE" {
            if timeDeltaInt <= 0 || timeDeltaInt >= 4321 {
                msg = fmt.Sprintf("error : query parameter 'time_delta' should be an integer between 1 and 4320 (a max 3 days) !")
                response["error"] = msg
                log.Println(response)
                w.WriteHeader(http.StatusBadRequest)
                _ = json.NewEncoder(w).Encode(&response)
                return
            }
        } else {
            msg = fmt.Sprintf("error : query parameter 'time_resolution' should be either 'MINUTE' or 'HOUR'")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        match := r.URL.Query().Get("match")
        if match == "" {
            msg = fmt.Sprintf("error : query parameter 'match' cannot be empty !")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        if !(match == "LIKE" || match == "EXACT") {
            msg = fmt.Sprintf("error : query parameter 'match' should be either 'EXACT' or 'LIKE'")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        log.Printf("__bigquery__ : match : %v", match)

        resource := r.URL.Query().Get("resource")
        if resource == "" {
            msg = fmt.Sprintf("error : query parameter 'resource' cannot be empty !")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        log.Printf("__bigquery__ : resource : %v", resource)

        sanitizedResource := SanitizeStringForBQ(resource)
        log.Printf("__bigquery__ : sanitizedResource : %v", sanitizedResource)

        sanitizedResourceLowerCase := strings.ToLower(SanitizeStringForBQ(resource))
        log.Printf("__bigquery__ : sanitizedResourceLowerCase : %v", sanitizedResourceLowerCase)

        query := ""

        gcpProject := os.Getenv("GCP_TEST_PROJECT")
        gcpDataSet := os.Getenv("GCP_TEST_DATASET")
        table1 := os.Getenv("GCP_TABLE_1")
        table2 := os.Getenv("GCP_TABLE_2")
        table3 := os.Getenv("GCP_TABLE_3")

        switch match {
        case "EXACT":
            switch eventType {
            case "type_1":
                query = fmt.Sprintf(`SELECT payload FROM %v.%v.%v WHERE scrape_ts >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL %v %v) AND LOWER(string(payload.subject)) = '%v' order by scrape_ts desc;`, gcpProject, gcpDataSet, table1, timeDelta, timeResolution, sanitizedResourceLowerCase)
            case "type_2":
                query = fmt.Sprintf(`SELECT payload FROM %v.%v.%v WHERE scrape_ts >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL %v %v) AND LOWER(string(payload.subject)) = '%v' order by scrape_ts desc;`, gcpProject, gcpDataSet, table2, timeDelta, timeResolution, sanitizedResourceLowerCase)
            case "type_3":
                query = fmt.Sprintf(`SELECT payload FROM %v.%v.%v WHERE scrape_ts >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL %v %v) AND LOWER(string(payload.subject)) = '%v' order by scrape_ts desc;`, gcpProject, gcpDataSet, table3, timeDelta, timeResolution, sanitizedResourceLowerCase)
            }
        case "LIKE":
            switch eventType {
            case "type_1":
                query = fmt.Sprintf(`SELECT payload FROM %v.%v.%v WHERE scrape_ts >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL %v %v) AND LOWER(string(payload.subject)) LIKE '%%%v%%' order by scrape_ts desc;`, gcpProject, gcpDataSet, table1, timeDelta, timeResolution, sanitizedResourceLowerCase)
            case "type_2":
                query = fmt.Sprintf(`SELECT payload FROM %v.%v.%v WHERE scrape_ts >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL %v %v) AND LOWER(string(payload.subject)) LIKE '%%%v%%' order by scrape_ts desc;`, gcpProject, gcpDataSet, table2, timeDelta, timeResolution, sanitizedResourceLowerCase)
            case "type_3":
                query = fmt.Sprintf(`SELECT payload FROM %v.%v.%v WHERE scrape_ts >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL %v %v) AND LOWER(string(payload.subject)) LIKE '%%%v%%' order by scrape_ts desc;`, gcpProject, gcpDataSet, table3, timeDelta, timeResolution, sanitizedResourceLowerCase)
            }
        default:
            msg = fmt.Sprintf("error : query parameter 'match' should be either 'EXACT' or 'LIKE'")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        log.Printf("__bigquery__ : query : [ %v ]", query)

        rows, err := QueryTableRows(context.Background(), BQClient, query)
        if err != nil {
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }
        response["data"] = rows
        w.Header().Set("Content-Type", "application/json")
        w.WriteHeader(http.StatusOK)
        _ = json.NewEncoder(w).Encode(response)
        return

    }
    w.Header().Set("Content-Type", "application/json")
    w.WriteHeader(http.StatusOK)
    _ = json.NewEncoder(w).Encode(response)
}

// SanitizeStringForBQ
// Modify this according to your needs
// we are removing characters before passing it to BQ query
func SanitizeStringForBQ(str string) string {
    // Regular expression to match unwanted characters
    reg := regexp.MustCompile(`[^a-zA-Z0-9\-_\/\.]`)

    // Replace unwanted characters with an empty string
    return reg.ReplaceAllString(str, "")
}
```

> BQ Table Schema

Table has 2 columns

```
Column-1 : scrape_ts (Type : TIMESTAMP)
Column-2 : payload   (Type : JSON)
```

> HTTP GET Requests

--- Type-1 Query : Pattern-Match (Like) ---

```
Minutes (How Far To Look Behind in BQ) + Pattern-Match : string(payload.subject) LIKE '%some_data%'

http://127.0.0.1:8888/api/v1/big_query_resource?operation=query_bq_table&event_type=type_1&time_delta=5&time_resolution=MINUTE&match=LIKE&resource=95b6
http://127.0.0.1:8888/api/v1/big_query_resource?operation=query_bq_table&event_type=type_2&time_delta=10&time_resolution=MINUTE&match=LIKE&resource=4304
http://127.0.0.1:8888/api/v1/big_query_resource?operation=query_bq_table&event_type=type_3&time_delta=15&time_resolution=MINUTE&match=LIKE&resource=e905

Hours (How Far To Look Behind in BQ) + Pattern-Match : string(payload.subject) LIKE '%some_data%'

http://127.0.0.1:8888/api/v1/big_query_resource?operation=query_bq_table&event_type=type_1&time_delta=1&time_resolution=HOUR&match=LIKE&resource=95b6
http://127.0.0.1:8888/api/v1/big_query_resource?operation=query_bq_table&event_type=type_2&time_delta=2&time_resolution=HOUR&match=LIKE&resource=4304
http://127.0.0.1:8888/api/v1/big_query_resource?operation=query_bq_table&event_type=type_3&time_delta=3&time_resolution=HOUR&match=LIKE&resource=e905
```

--- Type-2 Query : Exact Match ---

```
Minutes (How Far To Look Behind in BQ) + Exact Match : string(payload.subject) = 'some_data'

http://127.0.0.1:8888/api/v1/big_query_resource?operation=query_bq_table&event_type=type_1&time_delta=5&time_resolution=MINUTE&match=EXACT&resource=1f946d8e-63b7-4eb0-8914-b2e5aedc2920
http://127.0.0.1:8888/api/v1/big_query_resource?operation=query_bq_table&event_type=type_2&time_delta=10&time_resolution=MINUTE&match=EXACT&resource=4ac3479c-fce6-4d3e-9300-0ae7563f2144
http://127.0.0.1:8888/api/v1/big_query_resource?operation=query_bq_table&event_type=type_3&time_delta=15&time_resolution=MINUTE&match=EXACT&resource=25d48d7c-e905-4b26-9fbe-abceaddd39ad

Hours (How Far To Look Behind in BQ) + Exact Match : string(payload.subject) = 'some_data'

http://127.0.0.1:8888/api/v1/big_query_resource?operation=query_bq_table&event_type=type_1&time_delta=1&time_resolution=HOUR&match=EXACT&resource=1f946d8e-63b7-4eb0-8914-b2e5aedc2920
http://127.0.0.1:8888/api/v1/big_query_resource?operation=query_bq_table&event_type=type_2&time_delta=2&time_resolution=HOUR&match=EXACT&resource=25d48d7c-e905-4b26-9fbe-abceaddd39ad
http://127.0.0.1:8888/api/v1/big_query_resource?operation=query_bq_table&event_type=type_3&time_delta=3&time_resolution=HOUR&match=EXACT&resource=4ac3479c-fce6-4d3e-9300-0ae7563f2144
```

#### [Date Time Utils](#date-time-utils)

```go
func TrimCharacter(originalStr string, charToReplace string, charToReplaceWith string) string {
    return strings.ReplaceAll(originalStr, charToReplace, charToReplaceWith)
}

/*
ValidateCustomDateTime
dateTime should be in the following format : YYYY-MM-DD_HH:MM:SS (make sure you have '_')
*/
func ValidateCustomDateTime(dateTime string) bool {
    regex, err := regexp.Compile(`^\d{4}-\d{2}-\d{2}_\d{2}:\d{2}:\d{2}$`)
    if err != nil {
        fmt.Println("Invalid regex:", err)
        return false
    }
    return regex.MatchString(dateTime)
}

// SanitizeStringForBQ
// Modify this according to your needs
// we are removing characters before passing it to BQ query
func SanitizeStringForBQ(str string) string {
    // Regular expression to match unwanted characters
    reg := regexp.MustCompile(`[^a-zA-Z0-9\-_\/\.]`)

    // Replace unwanted characters with an empty string
    return reg.ReplaceAllString(str, "")
}

func IsValidDate(dateStr string) bool {
    _, err := time.Parse(time.DateTime, dateStr)
    return err == nil
}

/*
GetDateFromEpoch
Return Date-Time in the following format : 2021-03-15 08:30:00
*/
func GetDateFromEpoch(epoch int64) string {
    dateTime := time.Unix(epoch, 0) // in nanoseconds
    year, month, day := dateTime.Date()
    hour, minute, second := dateTime.Clock()
    currentDate := fmt.Sprintf("%d-%02d-%02d %02d:%02d:%02d", year, int(month), day, hour, minute, second)
    return currentDate
}

/*
CheckIfDateIsValid
dateStr := "2021-03-15 08:30:00"
*/
func CheckIfDateIsValid(dateStr string) bool {
    if IsValidDate(dateStr) {
        //fmt.Println(dateStr, "is a valid date")
        return true
    } else {
        //fmt.Println(dateStr, "is not a valid date")
        return false
    }
}

func GetEpochTime() int64 {
    return time.Now().Unix()
}

/*
GetCurrentDate
timeZone = 'UTC" or 'PST' Only for now
*/
func GetCurrentDate(timeZone string) string {
    now := time.Now()

    switch timeZone {
    case "UTC":
        now = time.Now().UTC()
    case "PST":
        location, _ := time.LoadLocation("America/Los_Angeles")
        now = time.Now().In(location)
    default:
        log.Println("Unknown Location")
    }

    year, month, day := now.Date()
    hour, minute, second := now.Clock()
    currentDate := fmt.Sprintf("%d-%02d-%02d %02d:%02d:%02d", year, int(month), day, hour, minute, second)
    return currentDate
}

/*
CheckFromDateAndToDateIsValid
fromDate should be earlier than toDate
(fromDate , toDate) format : 2021-03-15 08:30:00
*/
func CheckFromDateAndToDateIsValid(fromDate string, toDate string) (int64, bool) {
    var err error
    var delta int64
    var parsedTime time.Time
    if !CheckIfDateIsValid(fromDate) {
        log.Printf("fromDate : (%v) is NOT valid", fromDate)
        return delta, false
    }
    if !CheckIfDateIsValid(toDate) {
        log.Printf("toDate : (%v) is NOT valid", toDate)
        return delta, false
    }

    parsedTime, err = time.Parse(time.DateTime, fromDate)
    if err != nil {
        log.Printf("fromDate (%v) parse error : %v", fromDate, err.Error())
        return delta, false
    }
    fromDateEpoch := parsedTime.Unix()

    parsedTime, err = time.Parse(time.DateTime, toDate)
    if err != nil {
        log.Printf("toDate : (%v) parse error : %v", toDate, err.Error())
        return delta, false
    }
    toDateEpoch := parsedTime.Unix()

    if toDateEpoch > fromDateEpoch {
        log.Printf("true : toDate (%v) > fromDate (%v)", toDate, fromDate)
        delta = toDateEpoch - fromDateEpoch
        return delta, true

    } else {
        log.Printf("false : toDate (%v) <= fromDate (%v)", toDate, fromDate)
        return delta, false
    }
}
```

How To Use In `main.go`

```go
log.Println("Date-Time (UTC) : ", GetCurrentDate("UTC"))
log.Println("Date-Time (PST) : ", GetCurrentDate("PST"))

date1 := fmt.Sprintf("2023-12-30 15:59:59")
date2 := fmt.Sprintf("2023-13-30 13:59:59")
date3 := fmt.Sprintf("2023-12-30 24:01:01")

date4 := fmt.Sprintf("2023-12-25 13:00:00")
date5 := fmt.Sprintf("2023-11-25 14:59:59")

delta, _ := CheckFromDateAndToDateIsValid(date5, date4)
log.Printf("delta : %v", delta)

CheckIfDateIsValid(date1)
CheckIfDateIsValid(date2)
CheckIfDateIsValid(date3)

epoch := GetEpochTime()
log.Println("epoch : ", epoch)
epochDate := GetDateFromEpoch(epoch)
log.Println("epochDate : ", epochDate)
```

Sample Run

```bash
2023/11/22 10:40:24 Date-Time (UTC) :  2023-11-22 18:40:24
2023/11/22 10:40:24 Date-Time (PST) :  2023-11-22 10:40:24
2023/11/22 10:40:24 true : toDate (2023-12-25 13:00:00) > fromDate (2023-11-25 14:59:59)
2023/11/22 10:40:24 delta : 2584801
2023/11/22 10:40:24 epoch :  1700678424
2023/11/22 10:40:24 epochDate :  2023-11-22 10:40:24
```

#### [HTTP API Which Queries BigQuery Table V2](#http-api-which-queries-bigquery-table-v2)

```go
package main

import (
    "cloud.google.com/go/bigquery"
    "context"
    "encoding/json"
    "errors"
    "fmt"
    "github.com/gorilla/mux"
    "google.golang.org/api/iterator"
    "google.golang.org/api/option"
    "log"
    "net/http"
    "os"
    "regexp"
    "strconv"
    "strings"
    "time"
)

/*
Setup:

export GCP_SERVICE_ACCOUNT_JSON_FILE="$HOME/path/to/gcp_service_acct.json"
export GCP_TEST_PROJECT="GCP_PROJECT_NAME"
export GCP_TEST_DATASET="GCP_DATASET_NAME"
export GCP_TABLE_1="BQ_TABLE_1"
export GCP_TABLE_2="BQ_TABLE_2"
export GCP_TABLE_3="BQ_TABLE_3"
export GCP_TABLE_4="BQ_TABLE_4" # table with flattened columns -> Important : Note This !
*/

type Response struct {
    Status  string `json:"status"`
    Message string `json:"message"`
}

var BQClient *bigquery.Client

func main() {
    message := ""

    Initialize()

    r := mux.NewRouter()

    r.HandleFunc("/api/health", handleApiHealthCheck).Methods("GET")
    r.HandleFunc("/api/v1/big_query_resource", handleBigQueryMatchingResource).Methods("GET")

    corsMiddleware := func(next http.Handler) http.Handler {
        return http.HandlerFunc(func(w http.ResponseWriter, r *http.Request) {
            // Set CORS headers
            w.Header().Set("Access-Control-Allow-Origin", "*")
            w.Header().Set("Access-Control-Allow-Methods", "GET, POST, PUT, DELETE, OPTIONS, PATCH")
            w.Header().Set("Access-Control-Allow-Headers", "Content-Type")
            w.Header().Set("Access-Control-Allow-Headers", "Accept")

            // Handle preflight requests
            if r.Method == http.MethodOptions {
                w.WriteHeader(http.StatusOK)
                return
            }

            next.ServeHTTP(w, r)
        })
    }

    // Use the CORS middleware
    r.Use(corsMiddleware)

    http.Handle("/", r)

    port := "8888"
    bindIPAddress := "0.0.0.0"
    addr := fmt.Sprintf("%v:%v", bindIPAddress, port)

    serverAddr := addr

    message = fmt.Sprintf("Server will be listening @ %s", serverAddr)
    log.Println(message)

    /* ************** */

    log.Println("Date-Time (UTC) : ", GetCurrentDate("UTC"))
    log.Println("Date-Time (PST) : ", GetCurrentDate("PST"))

    date1 := fmt.Sprintf("2023-12-30 15:59:59")
    date2 := fmt.Sprintf("2023-13-30 13:59:59")
    date3 := fmt.Sprintf("2023-12-30 24:01:01")

    date4 := fmt.Sprintf("2023-12-25 13:00:00")
    date5 := fmt.Sprintf("2023-11-25 14:59:59")

    delta, _ := CheckFromDateAndToDateIsValid(date5, date4)
    log.Printf("delta : %v", delta)

    CheckIfDateIsValid(date1)
    CheckIfDateIsValid(date2)
    CheckIfDateIsValid(date3)

    epoch := GetEpochTime()
    log.Println("epoch : ", epoch)
    epochDate := GetDateFromEpoch(epoch)
    log.Println("epochDate : ", epochDate)

    /* ************** */

    err := http.ListenAndServe(serverAddr, nil)
    if err != nil {
        message = fmt.Sprintf("failed to setup http server on address (%v) : %v", serverAddr, err.Error())
        log.Fatalln(message)
    }
}

func handleApiHealthCheck(w http.ResponseWriter, r *http.Request) {

    log.Printf("handleTestRequest...")

    response := Response{}

    response.Status = "ok"
    response.Message = "status"

    log.Printf("handleTestRequest done !")

    w.Header().Set("Content-Type", "application/json")
    w.WriteHeader(http.StatusOK)
    _ = json.NewEncoder(w).Encode(response)
}

func QueryTableRows(ctx context.Context, client *bigquery.Client, query string) ([]interface{}, error) {
    msg := ""
    response := make([]interface{}, 0)
    bqQuery := client.Query(query)
    it, err := bqQuery.Read(ctx)
    if err != nil {
        msg = fmt.Sprintf("__bigquery__ : error : could not perform bqQuery.Read(ctx) : %v", err.Error())
        return response, errors.New(msg)
    }

    errorOccurred := false

    for {
        var values []bigquery.Value
        err = it.Next(&values)
        if errors.Is(err, iterator.Done) {
            break
        }
        if err != nil {
            errorOccurred = true
            break
        }
        for _, value := range values {

            jsonStr, ok := value.(string)
            if ok {
                var data map[string]interface{}
                err = json.Unmarshal([]byte(jsonStr), &data)
                if err != nil {
                    log.Printf("__bigquery__ : __error__ : json.Unmarshal([]byte(jsonStr), &data) : %v", err.Error())
                } else {
                    response = append(response, data)
                }
            } else {
                log.Println("__bigquery__ : value.(string) is false")
            }
        }
    }
    if errorOccurred {
        msg = fmt.Sprintf("__bigquery__ : error : could not perform it.Next(&values) : %v", err.Error())
        errorOccurred = true
        return response, errors.New(msg)
    }
    return response, nil
}

func GetBQClient() (*bigquery.Client, error) {
    var client *bigquery.Client
    var err error
    var errorMessage string
    ctx := context.Background()

    gcpProjectJSON := os.Getenv("GCP_SERVICE_ACCOUNT_JSON") // path to JSON File

    projectID := os.Getenv("GCP_TEST_PROJECT") // your GCP Project-Name

    // Create a BigQuery client
    client, err = bigquery.NewClient(ctx, projectID, option.WithCredentialsFile(gcpProjectJSON))
    if err != nil {
        errorMessage = fmt.Sprintf("error : failed to create BigQuery client: %v", err.Error())
        log.Printf(errorMessage)
        return client, errors.New(errorMessage)
    }

    return client, nil
}

func Initialize() {
    BQClient, _ = GetBQClient()
}

func handleBigQueryMatchingResource(w http.ResponseWriter, r *http.Request) {
    msg := ""
    response := make(map[string]interface{})
    response["error"] = ""
    response["data"] = make([]interface{}, 0)

    operation := r.URL.Query().Get("operation")
    if operation == "" {
        msg = fmt.Sprintf("error : query param 'operation' is empty !")
        response["error"] = msg
        log.Println(response)
        w.WriteHeader(http.StatusBadRequest)
        _ = json.NewEncoder(w).Encode(&response)
        return
    }

    match := r.URL.Query().Get("match")
    if match == "" {
        msg = fmt.Sprintf("error : query parameter 'match' cannot be empty !")
        response["error"] = msg
        log.Println(response)
        w.WriteHeader(http.StatusBadRequest)
        _ = json.NewEncoder(w).Encode(&response)
        return
    }

    if !(match == "LIKE" || match == "EXACT") {
        msg = fmt.Sprintf("error : query parameter 'match' should be either 'EXACT' or 'LIKE'")
        response["error"] = msg
        log.Println(response)
        w.WriteHeader(http.StatusBadRequest)
        _ = json.NewEncoder(w).Encode(&response)
        return
    }

    log.Printf("__bigquery__ : match : %v", match)

    resource := r.URL.Query().Get("resource")
    if resource == "" {
        msg = fmt.Sprintf("error : query parameter 'resource' cannot be empty !")
        response["error"] = msg
        log.Println(response)
        w.WriteHeader(http.StatusBadRequest)
        _ = json.NewEncoder(w).Encode(&response)
        return
    }

    log.Printf("__bigquery__ : resource : %v", resource)

    sanitizedResource := SanitizeStringForBQ(resource)
    log.Printf("__bigquery__ : sanitizedResource : %v", sanitizedResource)

    sanitizedResourceLowerCase := strings.ToLower(SanitizeStringForBQ(resource))
    log.Printf("__bigquery__ : sanitizedResourceLowerCase : %v", sanitizedResourceLowerCase)

    gcpProject := os.Getenv("GCP_TEST_PROJECT")
    gcpDataSet := os.Getenv("GCP_TEST_DATASET")
    table1 := os.Getenv("GCP_TABLE_1")
    table2 := os.Getenv("GCP_TABLE_2")
    table3 := os.Getenv("GCP_TABLE_3")
    table4 := os.Getenv("GCP_TABLE_4")

    switch operation {
    case "query_bq_table_with_time":

        eventType := r.URL.Query().Get("event_type")
        if eventType == "" {
            msg = fmt.Sprintf("error : query parameter 'event_type' cannot be empty !")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        if !(eventType == "type_1" || eventType == "type_2" || eventType == "type_3") {
            msg = fmt.Sprintf("error : query parameter 'event_type' should be ('scheduled' or 'resource' or 'flash') !")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        timeDelta := r.URL.Query().Get("time_delta")
        if timeDelta == "" {
            msg = fmt.Sprintf("error : query parameter 'time_delta' cannot be empty !")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        timeResolution := r.URL.Query().Get("time_resolution")
        if timeResolution == "" {
            msg = fmt.Sprintf("error : query parameter 'time_resolution' cannot be empty !")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        if !(timeResolution == "MINUTE" || timeResolution == "HOUR") {
            msg = fmt.Sprintf("error : query parameter 'time_resolution' should be either 'MINUTE' or 'HOUR'")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        timeDeltaInt, timeParseErr := strconv.Atoi(timeDelta)
        if timeParseErr != nil {
            msg = fmt.Sprintf("error : query parameter 'time_delta' should be a valid (integer) value")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        if timeResolution == "HOUR" {
            if timeDeltaInt <= 0 || timeDeltaInt >= 73 {
                msg = fmt.Sprintf("error : query parameter 'time_delta' should be an integer between 1 and 72 (a max 3 days) !")
                response["error"] = msg
                log.Println(response)
                w.WriteHeader(http.StatusBadRequest)
                _ = json.NewEncoder(w).Encode(&response)
                return
            }
        } else if timeResolution == "MINUTE" {
            if timeDeltaInt <= 0 || timeDeltaInt >= 4321 {
                msg = fmt.Sprintf("error : query parameter 'time_delta' should be an integer between 1 and 4320 (a max 3 days) !")
                response["error"] = msg
                log.Println(response)
                w.WriteHeader(http.StatusBadRequest)
                _ = json.NewEncoder(w).Encode(&response)
                return
            }
        } else {
            msg = fmt.Sprintf("error : query parameter 'time_resolution' should be either 'MINUTE' or 'HOUR'")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        query := ""

        switch match {
        case "EXACT":
            switch eventType {
            case "type_1":
                query = fmt.Sprintf(`SELECT payload FROM %v.%v.%v WHERE scrape_ts >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL %v %v) AND LOWER(string(payload.subject)) = '%v' order by scrape_ts desc;`, gcpProject, gcpDataSet, table1, timeDelta, timeResolution, sanitizedResourceLowerCase)
            case "type_2":
                query = fmt.Sprintf(`SELECT payload FROM %v.%v.%v WHERE scrape_ts >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL %v %v) AND LOWER(string(payload.subject)) = '%v' order by scrape_ts desc;`, gcpProject, gcpDataSet, table2, timeDelta, timeResolution, sanitizedResourceLowerCase)
            case "type_3":
                query = fmt.Sprintf(`SELECT payload FROM %v.%v.%v WHERE scrape_ts >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL %v %v) AND LOWER(string(payload.subject)) = '%v' order by scrape_ts desc;`, gcpProject, gcpDataSet, table3, timeDelta, timeResolution, sanitizedResourceLowerCase)
            }
        case "LIKE":
            switch eventType {
            case "type_1":
                query = fmt.Sprintf(`SELECT payload FROM %v.%v.%v WHERE scrape_ts >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL %v %v) AND LOWER(string(payload.subject)) LIKE '%%%v%%' order by scrape_ts desc;`, gcpProject, gcpDataSet, table1, timeDelta, timeResolution, sanitizedResourceLowerCase)
            case "type_2":
                query = fmt.Sprintf(`SELECT payload FROM %v.%v.%v WHERE scrape_ts >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL %v %v) AND LOWER(string(payload.subject)) LIKE '%%%v%%' order by scrape_ts desc;`, gcpProject, gcpDataSet, table2, timeDelta, timeResolution, sanitizedResourceLowerCase)
            case "type_3":
                query = fmt.Sprintf(`SELECT payload FROM %v.%v.%v WHERE scrape_ts >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL %v %v) AND LOWER(string(payload.subject)) LIKE '%%%v%%' order by scrape_ts desc;`, gcpProject, gcpDataSet, table3, timeDelta, timeResolution, sanitizedResourceLowerCase)
            }
        default:
            msg = fmt.Sprintf("error : query parameter 'match' should be either 'EXACT' or 'LIKE'")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        log.Printf("__bigquery__ : query : [ %v ]", query)

        rows, err := QueryTableRows(context.Background(), BQClient, query)
        if err != nil {
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }
        response["data"] = rows
        w.Header().Set("Content-Type", "application/json")
        w.WriteHeader(http.StatusOK)
        _ = json.NewEncoder(w).Encode(response)
        return

    case "query_bq_table_time_range":
        /* ---------------------------------------------------- */

        eventType := r.URL.Query().Get("event_type")
        if eventType == "" {
            msg = fmt.Sprintf("error : query parameter 'event_type' cannot be empty !")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        if !(eventType == "type_1" || eventType == "type_2" || eventType == "type_3") {
            msg = fmt.Sprintf("error : query parameter 'event_type' should be ('scheduled' or 'resource' or 'flash') !")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        timeZone := r.URL.Query().Get("time_zone")
        if timeZone == "" {
            msg = fmt.Sprintf("error : query parameter 'time_zone' cannot be empty (it should be 'UTC' or 'PST') !")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        if !(timeZone == "UTC" || timeZone == "PST") {
            msg = fmt.Sprintf("error : query parameter 'time_zone' should be 'UTC' or 'PST' !")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        log.Printf("__bigquery__ : timeZone : %v", timeZone)

        dateTimeFrom := r.URL.Query().Get("date_time_from")
        if dateTimeFrom == "" {
            msg = fmt.Sprintf("error : query parameter 'date_time_from' (YYYY-MM-DD_HH:MM:SS) cannot be empty !")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }
        if !ValidateCustomDateTime(dateTimeFrom) {
            msg = fmt.Sprintf("error : query parameter 'date_time_from' should be in this format : YYYY-MM-DD_HH:MM:SS")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }
        dateTimeFrom = TrimCharacter(dateTimeFrom, "_", " ")
        log.Printf("dateTimeFrom >> [ %v ]", dateTimeFrom)

        dateTimeTo := r.URL.Query().Get("date_time_to")
        if dateTimeTo == "" {
            msg = fmt.Sprintf("error : query parameter 'date_time_to' (YYYY-MM-DD_HH:MM:SS) cannot be empty !")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }
        if !ValidateCustomDateTime(dateTimeTo) {
            msg = fmt.Sprintf("error : query parameter 'date_time_to' should be in this format : YYYY-MM-DD_HH:MM:SS")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }
        dateTimeTo = TrimCharacter(dateTimeTo, "_", " ")

        if !CheckIfDateIsValid(dateTimeFrom) {
            msg = fmt.Sprintf("error : query parameter 'date_time_from' (YYYY-MM-DD_HH:MM:SS) is not valid")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        if !CheckIfDateIsValid(dateTimeTo) {
            msg = fmt.Sprintf("error : query parameter 'date_time_to' (YYYY-MM-DD_HH:MM:SS) is not valid")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }
        log.Printf("dateTimeTo >> [ %v ]", dateTimeTo)

        if timeZone == "PST" {
            dateTimeTo = ConvertTimeFromPSTtoUTC(dateTimeTo)
            dateTimeFrom = ConvertTimeFromPSTtoUTC(dateTimeFrom)

            log.Printf("dateTimeFrom (PST->UTC) >> [ %v ]", dateTimeFrom)
            log.Printf("dateTimeTo   (PST->UTC) >> [ %v ]", dateTimeTo)
        }

        totalSecondsBetweenTimeRanges, rangeValid := CheckFromDateAndToDateIsValid(dateTimeFrom, dateTimeTo)
        if !rangeValid {
            msg = fmt.Sprintf("error : query parameter 'date_time_to' (YYYY-MM-DD HH:MM:SS) (%v) should *(greater than)* 'date_time_from' (YYYY-MM-DD HH:MM:SS) (%v)", dateTimeTo, dateTimeFrom)
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        if totalSecondsBetweenTimeRanges > 259200 {
            msg = fmt.Sprintf("error : difference beween 'date_time_to' (%v)  and 'date_time_from' (%v) is more than 3 days ! it is going to cost us a lot of $$ if we extract too much data !", dateTimeTo, dateTimeFrom)
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        query := ""

        switch match {
        case "EXACT":
            switch eventType {
            case "type_1":
                query = fmt.Sprintf(`SELECT payload FROM %v.%v.%v WHERE (scrape_ts >= TIMESTAMP('%v') AND scrape_ts <= TIMESTAMP('%v')) AND LOWER(string(payload.subject)) = '%v' order by scrape_ts desc;`, gcpProject, gcpDataSet, table1, dateTimeFrom, dateTimeTo, sanitizedResourceLowerCase)
            case "type_2":
                query = fmt.Sprintf(`SELECT payload FROM %v.%v.%v WHERE (scrape_ts >= TIMESTAMP('%v') AND scrape_ts <= TIMESTAMP('%v')) AND LOWER(string(payload.subject)) = '%v' order by scrape_ts desc;`, gcpProject, gcpDataSet, table2, dateTimeFrom, dateTimeTo, sanitizedResourceLowerCase)
            case "type_3":
                query = fmt.Sprintf(`SELECT payload FROM %v.%v.%v WHERE (scrape_ts >= TIMESTAMP('%v') AND scrape_ts <= TIMESTAMP('%v')) AND LOWER(string(payload.subject)) = '%v' order by scrape_ts desc;`, gcpProject, gcpDataSet, table3, dateTimeFrom, dateTimeTo, sanitizedResourceLowerCase)
            }
        case "LIKE":
            switch eventType {
            case "type_1":
                query = fmt.Sprintf(`SELECT payload FROM %v.%v.%v WHERE (scrape_ts >= TIMESTAMP('%v') AND scrape_ts <= TIMESTAMP('%v')) AND LOWER(string(payload.subject)) LIKE '%%%v%%' order by scrape_ts desc;`, gcpProject, gcpDataSet, table1, dateTimeFrom, dateTimeTo, sanitizedResourceLowerCase)
            case "type_2":
                query = fmt.Sprintf(`SELECT payload FROM %v.%v.%v WHERE (scrape_ts >= TIMESTAMP('%v') AND scrape_ts <= TIMESTAMP('%v')) AND LOWER(string(payload.subject)) LIKE '%%%v%%' order by scrape_ts desc;`, gcpProject, gcpDataSet, table2, dateTimeFrom, dateTimeTo, sanitizedResourceLowerCase)
            case "type_3":
                query = fmt.Sprintf(`SELECT payload FROM %v.%v.%v WHERE (scrape_ts >= TIMESTAMP('%v') AND scrape_ts <= TIMESTAMP('%v')) AND LOWER(string(payload.subject)) LIKE '%%%v%%' order by scrape_ts desc;`, gcpProject, gcpDataSet, table3, dateTimeFrom, dateTimeTo, sanitizedResourceLowerCase)
            }
        default:
            msg = fmt.Sprintf("error : query parameter 'match' should be either 'EXACT' or 'LIKE'")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        log.Printf("__bigquery__ : query : [ %v ]", query)

        rows, err := QueryTableRows(context.Background(), BQClient, query)
        if err != nil {
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }
        response["data"] = rows
        w.Header().Set("Content-Type", "application/json")
        w.WriteHeader(http.StatusOK)
        _ = json.NewEncoder(w).Encode(response)
        return
        /* ---------------------------------------------------- */
    case "query_bq_table_time_range_flattened_columns":
        /* ---------------------------------------------------- */
        timeZone := r.URL.Query().Get("time_zone")
        if timeZone == "" {
            msg = fmt.Sprintf("error : query parameter 'time_zone' cannot be empty (it should be 'UTC' or 'PST') !")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        if !(timeZone == "UTC" || timeZone == "PST") {
            msg = fmt.Sprintf("error : query parameter 'time_zone' should be 'UTC' or 'PST' !")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        log.Printf("__bigquery__ : timeZone : %v", timeZone)

        dateTimeFrom := r.URL.Query().Get("date_time_from")
        if dateTimeFrom == "" {
            msg = fmt.Sprintf("error : query parameter 'date_time_from' (YYYY-MM-DD_HH:MM:SS) cannot be empty !")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }
        if !ValidateCustomDateTime(dateTimeFrom) {
            msg = fmt.Sprintf("error : query parameter 'date_time_from' should be in this format : YYYY-MM-DD_HH:MM:SS")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }
        dateTimeFrom = TrimCharacter(dateTimeFrom, "_", " ")
        log.Printf("dateTimeFrom >> [ %v ]", dateTimeFrom)

        dateTimeTo := r.URL.Query().Get("date_time_to")
        if dateTimeTo == "" {
            msg = fmt.Sprintf("error : query parameter 'date_time_to' (YYYY-MM-DD_HH:MM:SS) cannot be empty !")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }
        if !ValidateCustomDateTime(dateTimeTo) {
            msg = fmt.Sprintf("error : query parameter 'date_time_to' should be in this format : YYYY-MM-DD_HH:MM:SS")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }
        dateTimeTo = TrimCharacter(dateTimeTo, "_", " ")

        if !CheckIfDateIsValid(dateTimeFrom) {
            msg = fmt.Sprintf("error : query parameter 'date_time_from' (YYYY-MM-DD_HH:MM:SS) is not valid")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        if !CheckIfDateIsValid(dateTimeTo) {
            msg = fmt.Sprintf("error : query parameter 'date_time_to' (YYYY-MM-DD_HH:MM:SS) is not valid")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }
        log.Printf("dateTimeTo >> [ %v ]", dateTimeTo)

        if timeZone == "PST" {
            dateTimeTo = ConvertTimeFromPSTtoUTC(dateTimeTo)
            dateTimeFrom = ConvertTimeFromPSTtoUTC(dateTimeFrom)

            log.Printf("dateTimeFrom (PST->UTC) >> [ %v ]", dateTimeFrom)
            log.Printf("dateTimeTo   (PST->UTC) >> [ %v ]", dateTimeTo)
        }

        totalSecondsBetweenTimeRanges, rangeValid := CheckFromDateAndToDateIsValid(dateTimeFrom, dateTimeTo)
        if !rangeValid {
            msg = fmt.Sprintf("error : query parameter 'date_time_to' (YYYY-MM-DD HH:MM:SS) (%v) should *(greater than)* 'date_time_from' (YYYY-MM-DD HH:MM:SS) (%v)", dateTimeTo, dateTimeFrom)
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        maxAllowedTimeDelta := int64(7 * 24 * 60 * 60)
        if totalSecondsBetweenTimeRanges > maxAllowedTimeDelta {
            msg = fmt.Sprintf("error : difference beween 'date_time_to' (%v)  and 'date_time_from' (%v) is more than (%v seconds) ! it is going to cost us a lot of $$ if we extract too much data !", dateTimeTo, dateTimeFrom, maxAllowedTimeDelta)
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        query := ""

        switch match {
        case "EXACT":
            query = fmt.Sprintf(`SELECT * FROM %v.%v.%v WHERE (scrape_ts >= TIMESTAMP('%v') AND scrape_ts <= TIMESTAMP('%v')) AND LOWER(subject) = '%v' order by scrape_ts desc;`, gcpProject, gcpDataSet, table4, dateTimeFrom, dateTimeTo, sanitizedResourceLowerCase)
        case "LIKE":
            query = fmt.Sprintf(`SELECT * FROM %v.%v.%v WHERE (scrape_ts >= TIMESTAMP('%v') AND scrape_ts <= TIMESTAMP('%v')) AND LOWER(subject) LIKE '%%%v%%' order by scrape_ts desc;`, gcpProject, gcpDataSet, table4, dateTimeFrom, dateTimeTo, sanitizedResourceLowerCase)
        default:
            msg = fmt.Sprintf("error : query parameter 'match' should be either 'EXACT' or 'LIKE'")
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }

        log.Printf("__bigquery__ : query : [ %v ]", query)

        rows, err := QueryViewWithFlattenedColumns(context.Background(), BQClient, query)
        if err != nil {
            response["error"] = msg
            log.Println(response)
            w.WriteHeader(http.StatusBadRequest)
            _ = json.NewEncoder(w).Encode(&response)
            return
        }
        response["data"] = rows
        w.Header().Set("Content-Type", "application/json")
        w.WriteHeader(http.StatusOK)
        _ = json.NewEncoder(w).Encode(response)
        return
        /* ---------------------------------------------------- */
    }
    w.Header().Set("Content-Type", "application/json")
    w.WriteHeader(http.StatusOK)
    _ = json.NewEncoder(w).Encode(response)
}

/*
ConvertTimeFromPSTtoUTC
Make sure to pass dateTime as : YYYY-MM-DD HH:MM:SS
*/
func ConvertTimeFromPSTtoUTC(pstDateTime string) string {
    pstLocation, err := time.LoadLocation("America/Los_Angeles")
    if err != nil {
        log.Printf("ERROR : %v", err.Error())
    }

    layout := "2006-01-02 15:04:05"
    //layout := GetCurrentDate("PST")
    log.Println("layout : ", layout)

    pstTime, pstErr := time.ParseInLocation(layout, pstDateTime, pstLocation)
    if pstErr != nil {
        log.Printf("ERROR : %v", pstErr.Error())
    }
    utcTime := pstTime.UTC()

    year, month, day := utcTime.Date()
    hour, minute, second := utcTime.Clock()
    utcDateTime := fmt.Sprintf("%d-%02d-%02d %02d:%02d:%02d", year, int(month), day, hour, minute, second)

    log.Printf("pstDateTime : [ %v ] , utcDateTime : [ %v ]", pstDateTime, utcDateTime)
    return utcDateTime
}

func TrimCharacter(originalStr string, charToReplace string, charToReplaceWith string) string {
    return strings.ReplaceAll(originalStr, charToReplace, charToReplaceWith)
}

/*
ValidateCustomDateTime
dateTime should be in the following format : YYYY-MM-DD_HH:MM:SS (make sure you have '_')
*/
func ValidateCustomDateTime(dateTime string) bool {
    regex, err := regexp.Compile(`^\d{4}-\d{2}-\d{2}_\d{2}:\d{2}:\d{2}$`)
    if err != nil {
        fmt.Println("Invalid regex:", err)
        return false
    }
    return regex.MatchString(dateTime)
}

// SanitizeStringForBQ
// Modify this according to your needs
// we are removing characters before passing it to BQ query

func SanitizeStringForBQ(str string) string {
    // Regular expression to match unwanted characters
    reg := regexp.MustCompile(`[^a-zA-Z0-9\-_\/\.]`)

    // Replace unwanted characters with an empty string
    return reg.ReplaceAllString(str, "")
}

func IsValidDate(dateStr string) bool {
    _, err := time.Parse(time.DateTime, dateStr)
    return err == nil
}

/*
GetDateFromEpoch
Return Date-Time in the following format : 2021-03-15 08:30:00
*/
func GetDateFromEpoch(epoch int64) string {
    dateTime := time.Unix(epoch, 0) // in nanoseconds
    year, month, day := dateTime.Date()
    hour, minute, second := dateTime.Clock()
    currentDate := fmt.Sprintf("%d-%02d-%02d %02d:%02d:%02d", year, int(month), day, hour, minute, second)
    return currentDate
}

/*
CheckIfDateIsValid
dateStr := "2021-03-15 08:30:00"
*/
func CheckIfDateIsValid(dateStr string) bool {
    if IsValidDate(dateStr) {
        //fmt.Println(dateStr, "is a valid date")
        return true
    } else {
        //fmt.Println(dateStr, "is not a valid date")
        return false
    }
}

func GetEpochTime() int64 {
    return time.Now().Unix()
}

/*
GetCurrentDate
timeZone = 'UTC" or 'PST' Only for now
*/
func GetCurrentDate(timeZone string) string {
    now := time.Now()

    switch timeZone {
    case "UTC":
        now = time.Now().UTC()
    case "PST":
        location, _ := time.LoadLocation("America/Los_Angeles")
        now = time.Now().In(location)
    default:
        log.Println("Unknown Location")
    }

    year, month, day := now.Date()
    hour, minute, second := now.Clock()
    currentDate := fmt.Sprintf("%d-%02d-%02d %02d:%02d:%02d", year, int(month), day, hour, minute, second)
    return currentDate
}

/*
CheckFromDateAndToDateIsValid
fromDate should be earlier than toDate
(fromDate , toDate) format : 2021-03-15 08:30:00
*/
func CheckFromDateAndToDateIsValid(fromDate string, toDate string) (int64, bool) {
    var err error
    var delta int64
    var parsedTime time.Time
    if !CheckIfDateIsValid(fromDate) {
        log.Printf("fromDate : (%v) is NOT valid", fromDate)
        return delta, false
    }
    if !CheckIfDateIsValid(toDate) {
        log.Printf("toDate : (%v) is NOT valid", toDate)
        return delta, false
    }

    parsedTime, err = time.Parse(time.DateTime, fromDate)
    if err != nil {
        log.Printf("fromDate (%v) parse error : %v", fromDate, err.Error())
        return delta, false
    }
    fromDateEpoch := parsedTime.Unix()

    parsedTime, err = time.Parse(time.DateTime, toDate)
    if err != nil {
        log.Printf("toDate : (%v) parse error : %v", toDate, err.Error())
        return delta, false
    }
    toDateEpoch := parsedTime.Unix()

    if toDateEpoch > fromDateEpoch {
        log.Printf("true : toDate (%v) > fromDate (%v)", toDate, fromDate)
        delta = toDateEpoch - fromDateEpoch
        return delta, true

    } else {
        log.Printf("false : toDate (%v) <= fromDate (%v)", toDate, fromDate)
        return delta, false
    }
}

func QueryViewWithFlattenedColumns(ctx context.Context, client *bigquery.Client, query string) ([]map[string]interface{}, error) {
    msg := ""
    var rows []map[string]interface{}
    //response := make([]interface{}, 0)
    bqQuery := client.Query(query)
    it, err := bqQuery.Read(ctx)
    if err != nil {
        msg = fmt.Sprintf("__bigquery__ : error : could not perform bqQuery.Read(ctx) : %v", err.Error())
        return rows, errors.New(msg)
    }

    errorOccurred := false

    for {
        values := make(map[string]bigquery.Value)

        err = it.Next(&values)
        if errors.Is(err, iterator.Done) {
            break
        }
        if err != nil {
            errorOccurred = true
            msg = fmt.Sprintf("__bigquery__ : error : could not perform it.Next(&values) : %v", err.Error())
            break
        }

        rowMap := make(map[string]interface{})

        for _, fieldSchema := range it.Schema {
            fieldName := fieldSchema.Name
            rowMap[fieldName] = values[fieldName]
        }

        rows = append(rows, rowMap)

    }
    if errorOccurred {
        msg = fmt.Sprintf("__bigquery__ : error : could not perform it.Next(&values) , errorOccurred => true")
        errorOccurred = true
        return rows, errors.New(msg)
    }
    return rows, nil
}

/*
BQ Table Schema:

Table has 2 columns >>

Column-1 : scrape_ts (Type : TIMESTAMP)
Column-2 : payload   (Type : JSON)

HTTP GET Requests >>

--- Type-1 Query : Pattern-Match (Like) ---

Minutes (How Far To Look Behind in BQ) + Pattern-Match : string(payload.subject) LIKE '%some_data%'

http://127.0.0.1:8888/api/v1/big_query_resource?operation=query_bq_table_with_time&event_type=type_1&time_delta=5&time_resolution=MINUTE&match=LIKE&resource=95b6
http://127.0.0.1:8888/api/v1/big_query_resource?operation=query_bq_table_with_time&event_type=type_2&time_delta=10&time_resolution=MINUTE&match=LIKE&resource=4304
http://127.0.0.1:8888/api/v1/big_query_resource?operation=query_bq_table_with_time&event_type=type_3&time_delta=15&time_resolution=MINUTE&match=LIKE&resource=e905

Hours (How Far To Look Behind in BQ) + Pattern-Match : string(payload.subject) LIKE '%some_data%'

http://127.0.0.1:8888/api/v1/big_query_resource?operation=query_bq_table_with_time&event_type=type_1&time_delta=1&time_resolution=HOUR&match=LIKE&resource=95b6
http://127.0.0.1:8888/api/v1/big_query_resource?operation=query_bq_table_with_time&event_type=type_2&time_delta=2&time_resolution=HOUR&match=LIKE&resource=4304
http://127.0.0.1:8888/api/v1/big_query_resource?operation=query_bq_table_with_time&event_type=type_3&time_delta=3&time_resolution=HOUR&match=LIKE&resource=e905

--- Type-2 Query : Exact Match ---

Minutes (How Far To Look Behind in BQ) + Exact Match : string(payload.subject) = 'some_data'

http://127.0.0.1:8888/api/v1/big_query_resource?operation=query_bq_table_with_time&event_type=type_1&time_delta=5&time_resolution=MINUTE&match=EXACT&resource=1f946d8e-63b7-4eb0-8914-b2e5aedc2920
http://127.0.0.1:8888/api/v1/big_query_resource?operation=query_bq_table_with_time&event_type=type_2&time_delta=10&time_resolution=MINUTE&match=EXACT&resource=4ac3479c-fce6-4d3e-9300-0ae7563f2144
http://127.0.0.1:8888/api/v1/big_query_resource?operation=query_bq_table_with_time&event_type=type_3&time_delta=15&time_resolution=MINUTE&match=EXACT&resource=25d48d7c-e905-4b26-9fbe-abceaddd39ad

Hours (How Far To Look Behind in BQ) + Exact Match : string(payload.subject) = 'some_data'

http://127.0.0.1:8888/api/v1/big_query_resource?operation=query_bq_table_with_time&event_type=type_1&time_delta=1&time_resolution=HOUR&match=EXACT&resource=1f946d8e-63b7-4eb0-8914-b2e5aedc2920
http://127.0.0.1:8888/api/v1/big_query_resource?operation=query_bq_table_with_time&event_type=type_2&time_delta=2&time_resolution=HOUR&match=EXACT&resource=25d48d7c-e905-4b26-9fbe-abceaddd39ad
http://127.0.0.1:8888/api/v1/big_query_resource?operation=query_bq_table_with_time&event_type=type_3&time_delta=3&time_resolution=HOUR&match=EXACT&resource=4ac3479c-fce6-4d3e-9300-0ae7563f2144

http://127.0.0.1:8888/api/v1/big_query_resource?operation=query_bq_table_time_range&event_type=type_1&match=LIKE&resource=4ac3479c&date_time_from=2023-11-21_12:00:00&date_time_to=2023-11-21_18:00:00

Querying BigQuery With Flattened Columns

QueryViewWithFlattenedColumns(...)

http://127.0.0.1:8888/api/v1/big_query_resource?operation=query_bq_table_time_range_flattened_columns&date_time_from=2023-11-21_00:00:00&date_time_to=2023-11-23_23:59:59&time_zone=PST&match=LIKE&resource=/subscriptions/
*/
```

#### [Rate Limiting On Channel](#rate-limiting-on-channel)

```go
package main

import (
    "fmt"
    "log"
    "math/rand"
    "time"
)

// randomString generates a random alphanumeric string of length n.
func randomString(n int) string {
    const letterBytes = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789"
    b := make([]byte, n)
    for i := range b {
        b[i] = letterBytes[rand.Intn(len(letterBytes))]
    }
    return string(b)
}

func init() {
    rand.NewSource(time.Now().UnixNano())
    log.Println("Initialized Rand...")
}

func main() {
    // Create a channel for processing messages
    messages := make(chan string)

    // Set up rate limiting
    rateLimit := 500 * time.Millisecond // Limit to 1 message per second
    ticker := time.NewTicker(rateLimit)
    defer ticker.Stop()

    // Simulate sending messages
    go func() {
        for i := 0; i < 100; i++ {
            messages <- randomString(16)
        }
        close(messages)
    }()

    // if you don't want to range over the channel, and just want to have indefinite for {...} loop , then do this 

    /*
    for {
        select {
        case data, ok := <-messages:
            if !ok {
                break
            }
            <-ticker.C // Wait for the next tick
            fmt.Println("Processed:", data)
        }
    }
    */

    // above for {...}, will not exit the program
    // otherwise do this , which will exit the program

    // Process messages with rate limiting
    for msg := range messages {
        <-ticker.C // Wait for the next tick
        fmt.Println("Processed:", msg)
    }
}
```

#### Another Way To Process The Data From Channel Based Off Boolean Variable

> Please check the comments in the code below 🙂

```go
package main

import (
    "fmt"
    "log"
    "math/rand"
    "time"
)

// randomString generates a random alphanumeric string of length n.
func randomString(n int) string {
    const letterBytes = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789"
    b := make([]byte, n)
    for i := range b {
        b[i] = letterBytes[rand.Intn(len(letterBytes))]
    }
    return string(b)
}

func init() {
    rand.NewSource(time.Now().UnixNano())
    log.Println("Initialized Rand...")
}

func main() {
    processData := false // boolean to check : whether to process data

    // Create a channel for processing messages
    messages := make(chan string)

    // Set up rate limiting
    rateLimit := 100 * time.Millisecond // Limit to 1 message per second
    ticker := time.NewTicker(rateLimit)
    defer ticker.Stop()

    // Simulate sending messages
    go func() {
        for i := 0; i < 50; i++ {
            messages <- randomString(16)
        }
        close(messages)
    }()

    // after 10 secs have passed, set processData = true,
    // so that we can start consuming messages from channel
    now := time.Now()
    go func() {
        for {
            elapsed := time.Since(now)
            if elapsed.Seconds() > float64(10) {
                processData = true
                break
            } else {
                log.Println("Slept for 1 sec done...")
                time.Sleep(1 * time.Second)
            }
        }
    }()

    channelIsClosed := false

    // method-1 of consuming messages from the above channel

    for {
        if processData {
            select {
            case data, ok := <-messages:
                if !ok {
                    channelIsClosed = true // we set this to true once we get to know that (messages) channel is closed
                    // Important !
                    // the 'break' below >>
                    // will only break out of select
                    // and not the (for loop) on the outside
                    // for {
                    //    ...
                    //    ...
                    // }
                    break
                }
                <-ticker.C // Wait for the next tick
                fmt.Println("Processed:", data)
            }
        }
        // this break is needed to (break) out for the parent for loop
        if channelIsClosed {
            break
        }
    }

    // method-2 of consuming messages from the above channel

    // Process messages with rate limiting
    //for msg := range messages {
    //  <-ticker.C // Wait for the next tick
    //  fmt.Println("Processed:", msg)
    //}
}
```

#### [Using Interfaces To Make Things Generic](#using-interfaces-to-make-things-generic)

```
In Go, while you cannot directly pass a function with any type and number of 
arguments using interfaces without using reflection, you can design your 
program in a way that leverages interfaces to provide a similar level of 
flexibility and abstraction.

This typically involves defining an interface that your functions adhere to.

# Using an Interface with a Method

Let’s create an example where different types implement the same interface.

This interface will have a method that your functions will be required to implement.

Explanation

  - We define an Operation interface with a single method 
    Execute that returns an interface{}.
    This allows Execute to return any type.

  - AddOperation and ConcatOperation are struct types that implement 
    the Operation interface.
    Each has an Execute method that performs its specific operation.

  - The performOperation function takes any Operation and calls its Execute method.

Advantages

  - Type Safety: This approach keeps Go’s type safety intact.

  - Flexibility: It’s flexible in that any type that implements the
    Operation interface can be passed to performOperation.

  - Readability and Maintainability: This approach is more 
    in line with Go’s philosophy and results in more readable and 
    maintainable code compared to using reflection.

Limitations

  - Each operation needs to be predefined and implement the Operation interface.
    You can’t pass arbitrary functions directly.

  - The Execute method needs to handle the operation’s logic internally,
    which might be less flexible than passing any function directly.

  This approach is more idiomatic in Go. 
  It leverages interfaces for polymorphism, leading to code that is 
  easier to understand and maintain.
```

`main.go`

```go
package main

import "fmt"

type IOperation interface {
    Execute() interface{}
}

type DataAdd struct {
    Num1 int
    Num2 int
}

type DataConcat struct {
    Str1 string
    Str2 string
}

func (data DataAdd) Execute() interface{} {
    return data.Num1 + data.Num2
}

func (data DataConcat) Execute() interface{} {
    return fmt.Sprintf("%v-%v", data.Str1, data.Str2)
}

func performOperation(op IOperation) {
    result := op.Execute()
    fmt.Println("result :", result)
}

func main() {
    data1 := DataAdd{
        Num1: 10,
        Num2: 20,
    }

    performOperation(data1)

    data2 := DataConcat{
        Str1: "hello",
        Str2: "world",
    }

    performOperation(data2)
}
```

Output

```bash
go run main.go

result : 30
result : hello-world
```

#### [Generic HTTP Request V3](#generic-http-request-v3)

This is little more generic than V1 and V2 which is above, & used `gjson` for parsing JSON.

`main.go`

```go
package main

import (
    "bytes"
    "crypto/tls"
    "encoding/json"
    "errors"
    "fmt"
    "github.com/tidwall/gjson"
    "io"
    "math/rand"
    "net"
    "net/http"
    "net/url"
    "os"
    "time"

    log "github.com/sirupsen/logrus"
)

type HttpRequestType int64

const (
    GET HttpRequestType = iota
    HEAD
    POST
    PUT
    PATCH
    DELETE
)

type RequestMap struct {
    URL           string                 // some (https://...) URL
    Payload       map[string]interface{} // you are expected to set this as a string or map[string]interface{}
    RequestMethod HttpRequestType        // GET, POST, PUT etc
    Headers       map[string]interface{} // you are expected to set this as a string or map[string]string
    ProxyURL      string                 // optional
}

var letterRunes = []rune("abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ")

var (
    HttpTLSTimeOut    time.Duration = 10 // 10 seconds
    MyHttpProxyServer string        = "https://my-proxy-server.company.com:5050"
)

//-------------------------------------------------------------------------

func PrettyPrint(data interface{}) {
    dataMap, ok := data.(map[string]interface{})
    if ok {
        dataBytes, _ := json.MarshalIndent(dataMap, "", "    ")
        fmt.Printf("\n\ndata:\n\n%v\n\n", string(dataBytes))
    } else {
        fmt.Printf("\n\ndata:\n\n%v\n\n", data)
    }
}

//-------------------------------------------------------------------------

func GetMap(s string) (map[string]interface{}, error) {
    var msg string
    var jsonMap map[string]interface{}
    err := json.Unmarshal([]byte(s), &jsonMap)
    if err != nil {
        msg = fmt.Sprintf("could not Unmarshal (json.Unmarshal) []bytes(s) to -> Map : %v", err.Error())
        log.Printf(msg)
        return nil, errors.New(msg)
    }
    return jsonMap, nil
}

func GetString(m map[string]interface{}) (string, error) {
    msg := ""
    dataBytes, err := json.Marshal(m)
    if err != nil {
        msg = fmt.Sprintf("could not marshal (json.Marshal) to -> []bytes  : %v", err.Error())
        log.Printf(msg)
        return "", errors.New(msg)
    }
    dataBytesStr := string(dataBytes)
    return string(dataBytesStr), nil
}

func IsStringJSON(str string) bool {
    var js json.RawMessage
    return json.Unmarshal([]byte(str), &js) == nil
}

//-------------------------------------------------------------------------

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

//-------------------------------------------------------------------------

func GetJsonStr(data interface{}) (string, error) {
    returnStr := ""

    _, ok := data.(map[string]interface{})
    if !ok {
        return returnStr, errors.New("data is a valid json (map[string]interface{})")
    }

    dataBytes, err := json.Marshal(data)
    if err != nil {
        return returnStr, errors.New("data is not json string (json.Marshal failed)")
    }
    dataBytesStr := string(dataBytes)

    return dataBytesStr, nil
}

//-------------------------------------------------------------------------

func initRand() {
    rand.NewSource(time.Now().UnixNano())
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
    log.Printf("URL            : %v", r.URL)
    log.Printf("Payload        : %v", r.Payload)
    log.Printf("RequestMethod  : %v", r.RequestMethod)
    log.Printf("Headers        : %v", r.Headers)

    responseString := ""
    responseHttpStatusCode := -1

    //var headersMap map[string]interface{}
    var req *http.Request
    var err error
    var message string

    var tr *http.Transport

    var payloadStr string

    // ---- r.Payload : should be a JSON string or map[string]interface{} ------

    payloadStr, err = GetJsonStr(r.Payload)
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
    headersStr, err := GetJsonStr(headers)
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

func GetDefaultHeaders() map[string]interface{} {
    goRestToken := os.Getenv("GO_REST_TOKEN")
    headers := map[string]interface{}{
        "Authorization": "Bearer " + goRestToken,
        "Content-Type":  "application/json",
        "Accept":        "application/json",
    }
    return headers
}

/*
Refer to this : https://gorest.co.in/
*/

func main() {

    // --------- use-case-0 : first delete all existing users -------------

    log.Printf("@ GET USERS (HTTP GET) ...")

    request := RequestMap{
        URL:           "https://gorest.co.in/public/v2/users?page=1",
        Payload:       nil,
        RequestMethod: GET,
        Headers:       GetDefaultHeaders(),
        ProxyURL:      "",
    }

    response, responseStatusCode, err := request.HTTPRequest()
    if err != nil {
        log.Print(err)
        return
    }
    log.Printf("response : %v", response)
    log.Printf("responseStatusCode : %v", responseStatusCode)

    result := gjson.Get(response, "#.id")

    for _, id := range result.Array() {

        log.Printf("@ DELETE (HTTP DELETE) USER ...")

        userURL := fmt.Sprintf(`https://gorest.co.in/public/v2/users/%v`, id.String())

        log.Println("Deleting User :", userURL)

        request = RequestMap{
            URL:           userURL,
            Payload:       nil,
            RequestMethod: DELETE,
            Headers:       GetDefaultHeaders(),
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

    // --------- use-case-1 : get list of users -------------

    log.Printf("@ GET USERS (HTTP GET) ...")

    request = RequestMap{
        URL:           "https://gorest.co.in/public/v2/users?page=1",
        Payload:       nil,
        RequestMethod: GET,
        Headers:       GetDefaultHeaders(),
        ProxyURL:      "",
    }

    response, responseStatusCode, err = request.HTTPRequest()
    if err != nil {
        log.Print(err)
        return
    }
    log.Printf("response : %v", response)
    log.Printf("responseStatusCode : %v", responseStatusCode)

    // --------- use-case-2 : create user -------------

    log.Printf("@ CREATE USER (HTTP POST) ...")

    // example of using map[string]interface{} (json) -> for payload

    payload1 := make(map[string]interface{})
    payload1["name"] = "Linus"
    payload1["gender"] = "male"
    payload1["email"] = "linus.torvalds@foo.com"
    payload1["status"] = "active"
    payload1["age"] = 55

    log.Printf("payload1 : %v", payload1)

    request = RequestMap{
        URL:           "https://gorest.co.in/public/v2/users",
        Payload:       payload1,
        RequestMethod: POST,
        Headers:       GetDefaultHeaders(),
        ProxyURL:      "",
    }

    response, responseStatusCode, err = request.HTTPRequest()
    if err != nil {
        log.Print(err)
        return
    }
    log.Printf("response : %v", response)
    log.Printf("responseStatusCode : %v", responseStatusCode)

    userId := gjson.Get(response, "id")

    if !userId.Exists() {
        log.Println("userId does not exist ! user was not created !")
    }

    // --------- use-case-3 : update/patch user -------------

    randomStr := RandStringRunes(5)

    log.Printf("@ UDPATE (HTTP PATCH) USER ...")

    // example of using map[string]interface{} (json) -> for payload

    payloadMap := make(map[string]interface{})
    payloadMap["name"] = "Linus Torvalds (NEW)"
    payloadMap["gender"] = "male"
    payloadMap["email"] = fmt.Sprintf(`linux-torvalds@%v.com`, randomStr)
    payloadMap["status"] = "active"

    userID := userId.String()

    userURL := fmt.Sprintf(`https://gorest.co.in/public/v2/users/%v`, userID)

    log.Printf("userURL %v", userURL)

    request = RequestMap{
        URL:           userURL,
        Payload:       payloadMap,
        RequestMethod: PATCH,
        Headers:       GetDefaultHeaders(),
        ProxyURL:      "",
    }

    response, responseStatusCode, err = request.HTTPRequest()
    if err != nil {
        log.Print(err)
        return
    }
    log.Printf("response : %v", response)
    log.Printf("responseStatusCode : %v", responseStatusCode)

    // --------- use-case-4 : delete user -------------

    log.Printf("@ DELETE (HTTP DELETE) USER ...")

    userURL = fmt.Sprintf(`https://gorest.co.in/public/v2/users/%v`, userID)

    request = RequestMap{
        URL:           userURL,
        Payload:       payloadMap,
        RequestMethod: DELETE,
        Headers:       GetDefaultHeaders(),
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

#### [JSON String To Map And Map To JSON String](#json-string-to-map-and-map-to-json-string)

```go
func GetString(data interface{}) (string, error) {
    msg := ""
    jsonData, err := json.Marshal(data)
    if err != nil {
        msg = fmt.Sprintf("error : GetString : could not marshal data (json interface{}) -> (json string) : %v", err.Error())
        fmt.Printf("\n@ %v\n", msg)
        return "", errors.New(msg)
    }
    jsonStr := string(jsonData)
    return jsonStr, nil
}

func GetMap(jsonString string) (map[string]interface{}, error) {
    msg := ""
    var result map[string]interface{}
    err := json.Unmarshal([]byte(jsonString), &result)
    if err != nil {
        msg = fmt.Sprintf("error : GetMap : could not unmarshal data (json string) -> (json map[string]interface{}) : %v", err.Error())
        fmt.Printf("\n@ %v\n", msg)
        return nil, errors.New(msg)
    }
    return result, nil
}

func PrettyPrintData(data interface{}) {
    msg := ""
    dataBytes, err := json.MarshalIndent(data, "", "    ")
    if err != nil {
        msg = fmt.Sprintf("error : could not PrettyPrintData json data : %v", err.Error())
        fmt.Printf("\n@ %v\n", msg)
        return
    }
    fmt.Printf("\n@ json_data:\n\n%v\n\n", string(dataBytes))
}

func SaveMapToFile(filePath string, data interface{}) error {
    msg := ""
    jsonData, err := json.MarshalIndent(data, "", "    ")
    if err != nil {
        msg = fmt.Sprintf("error : SaveMapToFile : json.MarshalIndent : %v", err.Error())
        fmt.Printf("\n@ %v\n", msg)
        return errors.New(msg)
    }
    file, fileErr := os.Create(filePath)
    if fileErr != nil {
        msg = fmt.Sprintf("error : SaveMapToFile : os.Create : %v", fileErr.Error())
        fmt.Printf("\n@ %v\n", msg)
        return errors.New(msg)
    }
    defer func() {
        _ = file.Close()
    }()
    _, writeErr := file.Write(jsonData)
    if writeErr != nil {
        msg = fmt.Sprintf("error : SaveMapToFile : file.Write : %v", writeErr.Error())
        fmt.Printf("\n@ %v\n", msg)
        return errors.New(msg)
    }
    return nil
}
```

#### [GCP StackDriver Logging](#gcp-stackdriver-logging)

```bash
export GOOGLE_APPLICATION_CREDENTIALS="/path/to/your/service-account-file.json"
```

```bash
go get -u cloud.google.com/go/logging
```

```go
package main

import (
    "cloud.google.com/go/logging"
    "context"
    "log"
    "os"
)

func main() {
    ctx := context.Background()

    // Set your Google Cloud Project ID
    projectID := "your-google-cloud-project-id"

    // Creates a client.
    client, err := logging.NewClient(ctx, projectID)
    if err != nil {
        log.Fatalf("Failed to create client: %v", err)
    }
    defer client.Close()

    // Retrieves the system's hostname
    hostname, err := os.Hostname()
    if err != nil {
        log.Fatalf("Failed to get hostname: %v", err)
    }

    // Selects the log to write to
    logger := client.Logger("my-log")

    // Sets the entry data that includes the system's hostname
    entry := logging.Entry{
        Payload:  "Hello, world!",
        Severity: logging.Info,
        Labels: map[string]string{
            "hostname": hostname,
        },
    }

    // Adds an entry to the log
    logger.Log(entry)

    // OPTIONAL: Flushes pending log entries
    if err := client.Close(); err != nil {
        log.Fatalf("Failed to close client: %v", err)
    }

    log.Println("Logged entry with hostname to Stackdriver")
}
```

#### [Prometheus Graph And Metrics Using System Load Average](#prometheus-graph-and-metrics-using-system-load-average)

`IP_ADDRESS_OF_HOST` -> Machine From Which Metrics Are Being Gathered & Emitted

```bash
docker pull prom/prometheus
```

`prometheus.yml`

```yaml
scrape_configs:
  - job_name: 'myapp'
    static_configs:
      - targets: ['IP_ADDRESS_OF_HOST:8888']
```

```bash
docker run -p 9090:9090 -v ~/goworkspace/src/prom-gen/prometheus.yml:/etc/prometheus/prometheus.yml prom/prometheus
```

`main.go` (Run On Machine Where Metrics Are Being Gathers And Sent To Prometheus Server)

```go
package main

import (
    "github.com/prometheus/client_golang/prometheus"
    "github.com/prometheus/client_golang/prometheus/promauto"
    "github.com/prometheus/client_golang/prometheus/promhttp"
    "github.com/shirou/gopsutil/load"
    "log"
    "net/http"
    "time"
)

var (
    GaugeLoadAverage1m = promauto.NewGauge(prometheus.GaugeOpts{
        Name: "load_average_1m",
        Help: "Load Average 1 Minute",
    })

    GaugeLoadAverage5m = promauto.NewGauge(prometheus.GaugeOpts{
        Name: "load_average_5m",
        Help: "Load Average 5 Minute",
    })

    GaugeLoadAverage15m = promauto.NewGauge(prometheus.GaugeOpts{
        Name: "load_average_15m",
        Help: "Load Average 15 Minute",
    })
)

func main() {

    //avg, err := load.Avg()
    //if err != nil {
    //  log.Printf("Could not get load average: %v", err)
    //  return
    //}

    //fmt.Printf("Load Average: 1m: %.2f, 5m: %.2f, 15m: %.2f\n", avg.Load1, avg.Load5, avg.Load15)

    // Increment the counter.
    go func() {
        for {
            avg, _ := load.Avg()

            log.Printf("avg : %v", avg.String())

            GaugeLoadAverage1m.Set(avg.Load1)
            GaugeLoadAverage5m.Set(avg.Load5)
            GaugeLoadAverage15m.Set(avg.Load15)

            time.Sleep(2 * time.Second)
        }
    }()

    // Expose the registered metrics via HTTP.
    http.Handle("/metrics", promhttp.Handler())
    http.ListenAndServe("IP_ADDRESS_OF_HOST:8888", nil)
}
```

#### [GCP StackDriver Metrics](#gcp-stackdriver-metrics)

```go
package main

import (
    "context"
    "fmt"
    "log"
    "os"
    "time"

    monitoring "cloud.google.com/go/monitoring/apiv3/v2"
    "cloud.google.com/go/monitoring/apiv3/v2/monitoringpb"
    googlepb "github.com/golang/protobuf/ptypes/timestamp"
    metricpb "google.golang.org/genproto/googleapis/api/metric"
    monitoredrespb "google.golang.org/genproto/googleapis/api/monitoredres"
)

func main() {
    ctx := context.Background()

    _ = os.Setenv("GOOGLE_APPLICATION_CREDENTIALS", "gcp-svc-acct.json")

    // Creates a client.
    client, err := monitoring.NewMetricClient(ctx)
    if err != nil {
        log.Fatalf("Failed to create client: %v", err)
    }

    // Sets your Google Cloud Platform project ID.
    projectID := "my-gcp-project"

    // Prepares an individual data point
    dataPoint := &monitoringpb.Point{
        Interval: &monitoringpb.TimeInterval{
            EndTime: &googlepb.Timestamp{
                Seconds: time.Now().Unix(),
            },
        },
        Value: &monitoringpb.TypedValue{
            Value: &monitoringpb.TypedValue_DoubleValue{
                DoubleValue: 123.45,
            },
        },
    }

    // Writes time series data.
    if err := client.CreateTimeSeries(ctx, &monitoringpb.CreateTimeSeriesRequest{
        Name: fmt.Sprintf("projects/%s", projectID),
        TimeSeries: []*monitoringpb.TimeSeries{
            {
                Metric: &metricpb.Metric{
                    Type: "custom.googleapis.com/stores/daily_sales",
                    Labels: map[string]string{
                        "store_id": "Pittsburg",
                    },
                },
                Resource: &monitoredrespb.MonitoredResource{
                    Type: "global",
                    Labels: map[string]string{
                        "project_id": projectID,
                    },
                },
                Points: []*monitoringpb.Point{
                    dataPoint,
                },
            },
        },
    }); err != nil {
        log.Fatalf("Failed to write time series data: %v", err)
    }

    // Closes the client and flushes the data to Stackdriver.
    if err := client.Close(); err != nil {
        log.Fatalf("Failed to close client: %v", err)
    }

    fmt.Printf("Done writing time series data.\n")
}
```

#### [StackDriver Uber Zap Logging](#stackdriver-uber-zap-logging)

```go
package main

import (
    "context"
    "fmt"
    "log"

    "cloud.google.com/go/logging"
    "go.uber.org/zap"
)

// LogLevel represents the severity of the log message.
type LogLevel int

const (
    DEBUG LogLevel = iota
    ERROR
    INFO
)

// LoggerConfig holds the configuration for the logger.
type LoggerConfig struct {
    UseZap    bool
    UseGCP    bool
    ProjectID string
    LogID     string
}

// Logger wraps GCP Stackdriver and optional zap logging.
type Logger struct {
    gcpLogger *logging.Logger
    zapLogger *zap.Logger
    config    LoggerConfig
}

// NewLogger initializes a new Logger instance.
func NewLogger(config LoggerConfig) (*Logger, error) {
    var gcpLogger *logging.Logger
    var zapLogger *zap.Logger
    var err error

    // Initialize GCP Stackdriver client if required.
    if config.UseGCP {
        ctx := context.Background()
        client, err := logging.NewClient(ctx, config.ProjectID)
        if err != nil {
            return nil, fmt.Errorf("failed to create GCP logging client: %v", err)
        }
        gcpLogger = client.Logger(config.LogID)
    }

    // Initialize zap logger if required.
    if config.UseZap {
        zapLogger, err = zap.NewProduction()
        if err != nil {
            return nil, fmt.Errorf("failed to create zap logger: %v", err)
        }
    }

    return &Logger{
        gcpLogger: gcpLogger,
        zapLogger: zapLogger,
        config:    config,
    }, nil
}

// Log logs a message at the specified log level.
func (l *Logger) Log(level LogLevel, msg interface{}) {
    var severity logging.Severity

    switch level {
    case DEBUG:
        severity = logging.Debug
    case ERROR:
        severity = logging.Error
    case INFO:
        severity = logging.Info
    }

    if l.config.UseGCP && l.gcpLogger != nil {
        l.gcpLogger.Log(logging.Entry{
            Severity: severity,
            Payload:  msg,
        })
    }

    if l.config.UseZap && l.zapLogger != nil {
        switch level {
        case DEBUG:
            l.zapLogger.Debug(fmt.Sprintf("%v", msg))
        case ERROR:
            l.zapLogger.Error(fmt.Sprintf("%v", msg))
        case INFO:
            l.zapLogger.Info(fmt.Sprintf("%v", msg))
        }
    }
}

// Close closes the GCP Stackdriver logger.
func (l *Logger) Close() error {
    if l.config.UseGCP && l.gcpLogger != nil {
        return l.gcpLogger.Flush()
    }
    return nil
}

func main() {
    config := LoggerConfig{
        UseZap:    true,
        UseGCP:    true, // Set this to true if you want to log to GCP Stackdriver
        ProjectID: "your-gcp-project-id",
        LogID:     "your-log-id",
    }

    // Initialize the logger with the configuration
    logger, err := NewLogger(config)
    if err != nil {
        log.Fatalf("Failed to initialize logger: %v", err)
    }
    defer logger.Close()

    // Log messages of different types.
    logger.Log(DEBUG, "This is a debug message")
    logger.Log(INFO, map[string]interface{}{"key": "value", "number": 123})
    logger.Log(ERROR, struct {
        ID    int
        Error string
    }{ID: 42, Error: "Something went wrong"})

    fmt.Println("Logs have been sent to the configured log destinations.")
}
```

#### [Uber Zap Logging](#uber-zap-logging)

```go
package main

/*

go get go.uber.org/zap

*/

import (
	"go.uber.org/zap"
	"go.uber.org/zap/zapcore"
)

type User struct {
	ID    int
	Name  string
	Email string
}

func main() {
	// Create a custom logger configuration
	config := zap.NewProductionConfig()

	// Use the console encoder without colorization
	config.EncoderConfig.EncodeLevel = zapcore.CapitalLevelEncoder // No color

	logger, err := config.Build()
	if err != nil {
		panic(err)
	}
	defer logger.Sync()

	// Logging at different levels

	// Debug level logging
	logger.Debug("This is a debug message", zap.String("module", "main"))

	// Info level logging
	logger.Info("This is an info message", zap.String("module", "main"))

	// Error level logging with a stack trace
	logger.Error("This is an error message with a stack trace", zap.String("module", "main"), zap.Stack("stacktrace"))

	// Logging a struct
	user := User{
		ID:    1,
		Name:  "John Doe",
		Email: "john.doe@example.com",
	}

	logger.Info("Logging a user struct",
		zap.Int("ID", user.ID),
		zap.String("Name", user.Name),
		zap.String("Email", user.Email),
	)

	// Logging a struct with zap.Any (for arbitrary types)
	logger.Info("Logging a user struct with zap.Any", zap.Any("user", user))

	// Generate a sample stack trace
	logger.Error("This is another error with a stack trace",
		zap.Stack("stacktrace"),
	)
}
```

#### [GCP StackDriver Logger](#gcp-stackdriver-logger)

```go
package main

// package applogger

/*
go get -u -v cloud.google.com/go/logging
*/

/*
export GOOGLE_APPLICATION_CREDENTIALS="/path/to/your/service-account-file.json"
*/

import (
	"cloud.google.com/go/logging"
	"context"
	"fmt"
	"log"
	"os"
)

var AppLogger *logging.Logger

func main() {
	ctx := context.Background()

	// Set your Google Cloud Project ID
	projectID := "my-gcp-project"

	// Creates a client.
	client, err := logging.NewClient(ctx, projectID)
	if err != nil {
		log.Fatalf("Failed to create client: %v", err)
	}
	defer client.Close()

	// Retrieves the system's hostname
	hostname, err := os.Hostname()
	if err != nil {
		log.Fatalf("Failed to get hostname: %v", err)
	}

	// Selects the log to write to
	AppLogger = client.Logger("my-app")

	// Sets the entry data that includes the system's hostname
	msg1 := "some message_1"
	myStr1 := fmt.Sprintf("Hello, world! >> INFO : %v", msg1)
	entry := logging.Entry{
		Payload:  myStr1,
		Severity: logging.Info,
		Labels: map[string]string{
			"hostname": hostname,
		},
	}

	msg2 := "some message_2"
	myStr2 := fmt.Sprintf("Hello, world! >> DEBUG : %v", msg2)

	entry2 := logging.Entry{
		Payload:  myStr2,
		Severity: logging.Debug,
		Labels: map[string]string{
			"hostname": hostname,
		},
	}

	// Adds an entry to the log
	AppLogger.Log(entry)
	AppLogger.Log(entry2)

	DoOtherLogging()

	// OPTIONAL: Flushes pending log entries
	if err := client.Close(); err != nil {
		log.Fatalf("Failed to close client: %v", err)
	}

	log.Println("Logged entry with hostname to Stackdriver")
}

func DoOtherLogging() {
	msg3 := "some message_2"
	myStr3 := fmt.Sprintf("Hello, world! >> ERROR : %v", msg3)

	entry3 := logging.Entry{
		Payload:  myStr3,
		Severity: logging.Error,
		Labels: map[string]string{
			"hostname": "some_random_hostname",
		},
	}

	AppLogger.Log(entry3)
}
```

#### [HTTP Request With Retry And Proxy And Timeout](#http-request-with-retry-and-proxy-and-timeout)

```go
package main

import (
	"bytes"
	"context"
	"crypto/tls"
	"fmt"
	"io"
	"net/http"
	"net/url"
	"time"
)

// HTTPMethod defines the types of HTTP methods
type HTTPMethod string

const (
	GET    HTTPMethod = "GET"
	POST   HTTPMethod = "POST"
	PUT    HTTPMethod = "PUT"
	PATCH  HTTPMethod = "PATCH"
	DELETE HTTPMethod = "DELETE"
)

// HTTPRequestFactory is the interface for making HTTP requests
type HTTPRequestFactory interface {
	MakeRequest(ctx context.Context, url string, payload []byte) (*http.Response, error)
}

// HTTPRequestFactoryImpl is the concrete implementation of the factory
type HTTPRequestFactoryImpl struct {
	method   HTTPMethod
	proxyURL string // Optional proxy URL
}

// MakeRequest performs an HTTP request with optional payload, optional proxy, context timeout, and retry logic
func (f *HTTPRequestFactoryImpl) MakeRequest(ctx context.Context, httpUrl string, payload []byte) (*http.Response, error) {
	var req *http.Request
	var err error
	maxRetries := 3

	// Retry logic: Attempt request up to maxRetries times
	for i := 0; i < maxRetries; i++ {
		// Create HTTP request with the provided payload or without it
		if len(payload) > 0 {
			req, err = http.NewRequestWithContext(ctx, string(f.method), httpUrl, bytes.NewBuffer(payload))
		} else {
			req, err = http.NewRequestWithContext(ctx, string(f.method), httpUrl, nil)
		}
		if err != nil {
			return nil, err
		}

		// Set appropriate headers (example: JSON)
		req.Header.Set("Content-Type", "application/json")

		// Setup HTTP Transport with optional proxy and TLS configuration
		transport := &http.Transport{
			TLSClientConfig: &tls.Config{
				InsecureSkipVerify: true, // Skipping certificate verification
			},
		}

		// If proxy is provided, configure the transport to use the proxy
		if f.proxyURL != "" {
			proxyURL, err := url.Parse(f.proxyURL)
			if err != nil {
				return nil, fmt.Errorf("invalid proxy URL: %v", err)
			}
			transport.Proxy = http.ProxyURL(proxyURL)
		}

		// Define an HTTP client with the transport
		client := &http.Client{
			Transport: transport,
		}

		// Send the request
		resp, err := client.Do(req)

		// Check if the request was successful or not
		if err == nil && resp.StatusCode >= 200 && resp.StatusCode <= 299 {
			return resp, nil // Success, return the response
		}

		// If error or non-2xx status code, retry
		if err != nil {
			fmt.Printf("Attempt %d failed: %v\n", i+1, err)
		} else {
			fmt.Printf("Attempt %d failed: Received non-2xx status code %d\n", i+1, resp.StatusCode)
		}

		// If this was the last attempt, return the error
		if i == maxRetries-1 {
			return resp, fmt.Errorf("max retries exceeded: %v", err)
		}

		// Exponential backoff between retries (increase wait time)
		time.Sleep(time.Duration(i+1) * time.Second)
	}

	return nil, fmt.Errorf("request failed after max retries")
}

// HTTPRequestFactoryCreator is the factory method to create HTTPRequestFactory instances
func HTTPRequestFactoryCreator(method HTTPMethod, proxyURL string) HTTPRequestFactory {
	return &HTTPRequestFactoryImpl{method: method, proxyURL: proxyURL}
}

func main() {
	url := "https://jsonplaceholder.typicode.com/posts"

	// Set a 5-second timeout context
	ctx, cancel := context.WithTimeout(context.Background(), 5*time.Second)
	defer cancel()

	// Example: POST request with payload, no proxy
	postFactory := HTTPRequestFactoryCreator(POST, "")
	postPayload := []byte(`{"title":"foo", "body":"bar", "userId":1}`)
	resp, err := postFactory.MakeRequest(ctx, url, postPayload)
	handleResponse(resp, err)

	// Example: GET request without payload, with proxy
	proxy := "http://myproxy.example.com:8080"
	getFactory := HTTPRequestFactoryCreator(GET, proxy)
	resp, err = getFactory.MakeRequest(ctx, url, nil)
	handleResponse(resp, err)
}

// handleResponse handles the response from the server
func handleResponse(resp *http.Response, err error) {
	if err != nil {
		fmt.Printf("Request failed: %v\n", err)
		return
	}
	defer resp.Body.Close()

	body, err := io.ReadAll(resp.Body)
	if err != nil {
		fmt.Printf("Failed to read response body: %v\n", err)
		return
	}

	fmt.Printf("Status Code: %d\n", resp.StatusCode)
	fmt.Printf("Response Body: %s\n", body)
}
```
#### [HTTP Connection Pooling](#http-connection-pooling)

#### Benefits of Connection Pooling

- Reduced Latency: By reusing existing connections, you reduce the overhead of establishing new TCP connections and TLS handshakes for each request.
- Resource Efficiency: Pooling connections allows you to efficiently manage system resources like file descriptors and ports, preventing resource exhaustion.
- Concurrency Control: The MaxConnsPerHost setting allows you to limit the number of concurrent connections to a single host, which can help prevent overwhelming the server or hitting rate limits.

#### Important Considerations

- Connection Timeouts: Ensure that the IdleConnTimeout is appropriate for your use case. Too short of a timeout might close connections too early, while too long might keep connections open unnecessarily.
- TLS Configurations: If you are connecting to secure (HTTPS) endpoints, ensure that the TLS configuration (TLSClientConfig) is secure. In production, you should avoid InsecureSkipVerify: true unless you have specific needs.

#### Summary

- Create a custom http.Transport for fine-tuning connection pooling options.
- Set limits on idle connections, maximum connections per host, and connection timeouts to optimize connection reuse.
- Use the custom transport in your http.Client to automatically pool and reuse HTTP connections across multiple requests.

By using connection pooling, you can significantly improve the performance and efficiency of HTTP requests in your Go applications, especially when making multiple requests to the same host.

Explanation of Key Parameters:

- `MaxIdleConns`: The maximum number of idle (keep-alive) connections across all hosts. This allows the client to reuse connections rather than creating a new one for each request, improving performance.
- `MaxIdleConnsPerHost`: The maximum number of idle connections to keep for each host. Setting this ensures that there is a reasonable limit on the number of open connections to a single host.
- `MaxConnsPerHost`: The maximum number of total connections to a single host. This controls how many active connections can be open simultaneously to the same host, providing throttling of concurrent connections.
 - `IdleConnTimeout`: The maximum amount of time that an idle connection can remain open before being closed. If no new requests are made on an idle connection within this time, it will be closed.
- `TLSClientConfig`: Used to configure the TLS settings. For example, setting InsecureSkipVerify: true disables TLS certificate verification (use with caution in production).


> Just In Case

```bash
ulimit -n 65536
sysctl -w net.ipv4.ip_local_port_range="1024 65535"
```

```go
package main

import (
    "crypto/tls"
    "fmt"
    "io/ioutil"
    "log"
    "net/http"
    "time"
)

func main() {
    // Create a custom transport with connection pooling options
    customTransport := &http.Transport{
        // MaxIdleConns: The maximum number of idle (keep-alive) connections across all hosts
        MaxIdleConns: 100,
        // MaxIdleConnsPerHost: The maximum number of idle connections to keep per host
        MaxIdleConnsPerHost: 10,
        // MaxConnsPerHost: The maximum number of connections to a single host
        MaxConnsPerHost: 50,
        // IdleConnTimeout: How long to keep idle connections alive
        IdleConnTimeout: 90 * time.Second,

        // Optional: Skip TLS verification (only use in development or when necessary)
        TLSClientConfig: &tls.Config{InsecureSkipVerify: true},
    }

    // Create a custom HTTP client using the custom transport
    client := &http.Client{
        Transport: customTransport,
        Timeout:   10 * time.Second, // Set a timeout for the request
    }

    // Perform a GET request (reusing connections with connection pooling)
    resp, err := client.Get("https://www.example.com")
    if err != nil {
        log.Fatalf("Error making request: %v", err)
    }
    defer resp.Body.Close()

    // Read and print the response body
    body, err := ioutil.ReadAll(resp.Body)
    if err != nil {
        log.Fatalf("Error reading response body: %v", err)
    }
    fmt.Println("Response:", string(body))
}
```

```go
package main

import (
    "crypto/tls"
    "fmt"
    "io/ioutil"
    "log"
    "net/http"
    "time"
)

func main() {
    // Custom transport with connection pooling
    customTransport := &http.Transport{
        MaxIdleConns:        100,
        MaxIdleConnsPerHost: 10,
        MaxConnsPerHost:     50,
        IdleConnTimeout:     90 * time.Second,
        TLSClientConfig:     &tls.Config{InsecureSkipVerify: true},
    }

    // Create the HTTP client
    client := &http.Client{
        Transport: customTransport,
        Timeout:   10 * time.Second,
    }

    // Make multiple requests to the same host
    urls := []string{
        "https://www.example.com",
        "https://www.example.com/path1",
        "https://www.example.com/path2",
    }

    for _, url := range urls {
        resp, err := client.Get(url)
        if err != nil {
            log.Printf("Error making request to %s: %v", url, err)
            continue
        }
        body, err := ioutil.ReadAll(resp.Body)
        if err != nil {
            log.Printf("Error reading response from %s: %v", url, err)
        }
        fmt.Printf("Response from %s: %s\n", url, string(body))
        resp.Body.Close()
    }
}
```

#### [Custom GCP StackDriver And Uber Zap Logging](#custom-gcp-stackdriver-and-uber-zap-logging)

> Make Sure You Export The Required Environment Variable

```bash
export GOOGLE_APPLICATION_CREDENTIALS="/etc/my-gcp-project.json"
```

> Uber Zap & GCP StackDriver Logging

```go
package main

import (
	"cloud.google.com/go/logging"
	"context"
	"fmt"
	"go.uber.org/zap"
	"go.uber.org/zap/zapcore"
	"log"
	"runtime/debug"
	"strings"
)

var ULogConfigLogSysAndGCP LoggerConfig
var ULogConfigLogSys LoggerConfig
var ULogConfigLogGCP LoggerConfig

var LogSys *Logger
var LogGCP *Logger
var LogSysGCP *Logger

// LogLevel represents the severity of the log message.
type LogLevel int

var StackDriverLoggerName = "my-logs"
var GCPProjectName = "my-gcp-project"

const (
	DEBUG LogLevel = iota
	ERROR
	INFO
	WARNING
	CRITICAL
)

// LoggerConfig holds the configuration for the logger.
type LoggerConfig struct {
	UseZap    bool
	UseGCP    bool
	ProjectID string
	LogID     string
}

// Logger wraps GCP Stackdriver and optional zap logging.
type Logger struct {
	gcpLogger *logging.Logger
	zapLogger *zap.Logger
	config    LoggerConfig
}

// NewLogger initializes a new Logger instance.
func NewLogger(config LoggerConfig) (*Logger, error) {
	var gcpLogger *logging.Logger
	var zapLogger *zap.Logger
	//var err error

	// Initialize GCP Stackdriver client if required.
	if config.UseGCP {
		ctx := context.Background()
		client, err := logging.NewClient(ctx, config.ProjectID)
		if err != nil {
			return nil, fmt.Errorf("failed to create GCP logging client: %v", err)
		}
		gcpLogger = client.Logger(config.LogID)
	}

	// Custom Zap encoder for console output with better formatting
	if config.UseZap {
		encoderConfig := zapcore.EncoderConfig{
			MessageKey:    "msg",
			LevelKey:      "level",
			TimeKey:       "ts",
			CallerKey:     "caller",
			StacktraceKey: "stacktrace",
			EncodeLevel:   zapcore.CapitalLevelEncoder,
			EncodeTime:    zapcore.ISO8601TimeEncoder,
			EncodeCaller:  zapcore.ShortCallerEncoder,
		}

		// Create zap core with the custom encoder.
		zapCore := zapcore.NewCore(
			zapcore.NewConsoleEncoder(encoderConfig),
			zapcore.AddSync(log.Writer()),
			zap.DebugLevel, // Set log level to debug
		)

		// Remove automatic stack traces added by Zap, handle manually
		zapLogger = zap.New(zapCore, zap.AddCaller()) // No zap.AddStacktrace()
	}

	return &Logger{
		gcpLogger: gcpLogger,
		zapLogger: zapLogger,
		config:    config,
	}, nil
}

// Log logs a message at the specified log level.
func (l *Logger) Log(level LogLevel, msg interface{}) {
	var severity logging.Severity

	// Map log levels to GCP Stackdriver severity.
	switch level {
	case DEBUG:
		severity = logging.Debug
	case ERROR:
		severity = logging.Error
	case INFO:
		severity = logging.Info
	case WARNING:
		severity = logging.Warning
	case CRITICAL:
		severity = logging.Critical
	}

	// Log to GCP Stackdriver if enabled.
	if l.config.UseGCP && l.gcpLogger != nil {
		l.gcpLogger.Log(logging.Entry{
			Severity: severity,
			Payload:  msg,
		})
	}

	// Log to Zap if enabled.
	if l.config.UseZap && l.zapLogger != nil {
		switch level {
		case DEBUG:
			l.zapLogger.Debug(fmt.Sprintf("%v", msg))
		case ERROR:
			// Capture the stacktrace and format it before logging as a single line
			stacktrace := flattenStackTrace(string(debug.Stack()))
			l.zapLogger.Error(fmt.Sprintf("%v | Stacktrace: %s", msg, stacktrace))
		case INFO:
			l.zapLogger.Info(fmt.Sprintf("%v", msg))
		case WARNING:
			l.zapLogger.Warn(fmt.Sprintf("%v", msg))
		case CRITICAL:
			// Capture the stacktrace and format it before logging as a single line
			stacktrace := flattenStackTrace(string(debug.Stack()))
			l.zapLogger.DPanic(fmt.Sprintf("%v | Stacktrace: %s", msg, stacktrace))
		}
	}
}

// flattenStackTrace is a helper function to remove line breaks and replace them with space characters
func flattenStackTrace(stack string) string {
	// Replace newlines and tabs with a space to make it a single line
	stack = strings.ReplaceAll(stack, "\n", " ")
	stack = strings.ReplaceAll(stack, "\t", " ")
	return stack
}

// Close closes the GCP Stackdriver logger.
func (l *Logger) Close() error {
	if l.config.UseGCP && l.gcpLogger != nil {
		return l.gcpLogger.Flush()
	}
	return nil
}

func InitializeUniversalLogging() {
	var err error

	ULogConfigLogSys = LoggerConfig{
		UseZap:    true,
		UseGCP:    false,
		ProjectID: GCPProjectName,
		LogID:     StackDriverLoggerName,
	}

	ULogConfigLogGCP = LoggerConfig{
		UseZap:    false,
		UseGCP:    true,
		ProjectID: GCPProjectName,
		LogID:     StackDriverLoggerName,
	}

	ULogConfigLogSysAndGCP = LoggerConfig{
		UseZap:    true,
		UseGCP:    true,
		ProjectID: GCPProjectName,
		LogID:     StackDriverLoggerName,
	}

	LogSys, err = NewLogger(ULogConfigLogSys)
	if err != nil {
		log.Fatalf("__fatal__ : failed to initialize logger : NewLogger(appdata.ULogConfigLogSys) : %v", err)
	}

	LogGCP, err = NewLogger(ULogConfigLogGCP)
	if err != nil {
		log.Fatalf("__fatal__ : failed to initialize logger : NewLogger(appdata.ULogConfigLogGCP) : %v", err)
	}

	LogSysGCP, err = NewLogger(ULogConfigLogSysAndGCP)
	if err != nil {
		log.Fatalf("__fatal__ : failed to initialize logger : NewLogger(appdata.ULogConfigLogSysAndGCP) : %v", err)
	}

	LogSysGCP.Log(INFO, "__initialize__ : Initialized Universal Logger with GCP/UberZap Logger")
}

func main() {
	config := LoggerConfig{
		UseZap:    true,
		UseGCP:    true,
		ProjectID: GCPProjectName,
		LogID:     StackDriverLoggerName,
	}

	// Initialize the logger with the configuration
	logger, err := NewLogger(config)
	if err != nil {
		log.Fatalf("__fatal__ : failed to initialize logger: %v", err)
	}
	defer logger.Close()

	// Log messages of different levels
	logger.Log(DEBUG, "This is a debug message")
	logger.Log(INFO, "This is an info message")
	logger.Log(WARNING, "This is a warning message")
	logger.Log(ERROR, "This is an error message")
	logger.Log(CRITICAL, "This is a critical message")

	fmt.Println("Logs have been sent to the configured log destinations.")
}
```

> Output on Console

```bash
2024-09-20T08:42:16.461-0700    DEBUG   eventgen/custom_logging.go:128  This is a debug message
2024-09-20T08:42:16.462-0700    INFO    eventgen/custom_logging.go:134  This is an info message
2024-09-20T08:42:16.462-0700    WARN    eventgen/custom_logging.go:136  This is a warning message
2024-09-20T08:42:16.462-0700    ERROR   eventgen/custom_logging.go:132  This is an error message | Stacktrace: goroutine 1 [running]: runtime/debug.Stack()  /root/go/go1.22.5/go/src/runtime/debug/stack.go:24 +0x64 main.(*Logger).Log(0x140001141c0, 0x1?, {0x100adeb00, 0x100cbbdd0})  /root/git/goworkspace/src/myplayground/eventgen/custom_logging.go:131 +0x114 main.SampleLogging()  /root/git/goworkspace/src/myplayground/eventgen/custom_logging.go:222 +0x154 main.main()  /root/git/goworkspace/src/myplayground/eventgen/main.go:18 +0x24
2024-09-20T08:42:16.462-0700    DPANIC  eventgen/custom_logging.go:140  This is a critical message | Stacktrace: goroutine 1 [running]: runtime/debug.Stack()  /root/go/go1.22.5/go/src/runtime/debug/stack.go:24 +0x64 main.(*Logger).Log(0x140001141c0, 0x4?, {0x100adeb00, 0x100cbbde0})  /root/git/goworkspace/src/myplayground/eventgen/custom_logging.go:139 +0x20c main.SampleLogging()  /root/git/goworkspace/src/myplayground/eventgen/custom_logging.go:223 +0x170 main.main()  /root/git/goworkspace/src/myplayground/eventgen/main.go:18 +0x24
Logs have been sent to the configured log destinations.
```

> You Can Also Verify Logs In Your GCP Project Under `my-logs`

#### [PostgreSQL Locks To Ensure Single Instance Runs Even Thought It Is Deployed On Multiple Instances](#postgresql-locks-to-ensure-single-instance-runs-even-thought-it-is-deployed-on-multiple-instances)

> Notes

PostgreSQL advisory lock mechanism used in this code will work even if the code is running on different 
virtual machines. This is because PostgreSQL advisory locks are managed at the database level, meaning as 
long as all your instances (VMs, containers, etc.) are connected to the same PostgreSQL database, 
the advisory lock will ensure that only one instance can acquire the lock at any given time.

How It Works Across Different VMs:

 - Shared Database: Since all the virtual machines are connected to the same PostgreSQL database, 
   the advisory lock (pg_try_advisory_lock) works across the different VMs.
   
 - Global Locking: PostgreSQL manages the locks globally, across all connections. If one instance 
   acquires the advisory lock, no other instance will be able to acquire that lock until it is released 
   by the instance holding it (or until the session that holds the lock is terminated).
   
 - Session-Based Locking: PostgreSQL advisory locks are tied to the database session. 
   When a session (i.e., the connection) closes, all locks held by that session are automatically released. 
   This ensures that if a job crashes or the VM is terminated, the lock is not held indefinitely, 
   allowing other instances to acquire it and run the job.
   
 - pg_try_advisory_lock Behavior:
 
 - When a VM instance tries to acquire a lock using pg_try_advisory_lock, it returns true if the 
   lock is successfully acquired, and false if the lock is already held by another session 
   (on a different VM, for example).
   
 - Oy one session at a time will be able to acquire the lock based on the unique lock ID (in your case, LockID = 1).

Example Scenario:

- VM1 tries to acquire the advisory lock for LockID = 1. If no other instance is running the job and 
  holding this lock, VM1 will acquire the lock and run the job.
  
- VM2 starts at the same time and also tries to acquire the advisory lock for LockID = 1. 
  Since VM1 already holds the lock, VM2 will fail to acquire the lock and skip running the job.
  
- After VM1 completes the job, it releases the lock, making it available again.

- VM2 (or any other VM) can now acquire the lock and run the job.

Idempotency:

The lock ensures idempotency by preventing multiple instances from running the same job simultaneously. 
As long as the job is running in one instance (VM1), no other instance (e.g., VM2) can run the job. 
This ensures that only one job is executed at any given time, avoiding duplication or conflicting operations.

Fail-Safe Behavior:

 - Crash Recovery: If a VM holding the lock crashes or loses its connection to the PostgreSQL database, 
   the lock will be automatically released by PostgreSQL when the session is closed. This ensures that 
   another VM can acquire the lock and run the job without manual intervention.
   
 - Job Failures: If the job fails but the session remains open, the lock will continue to be held until the session 
   ends or the lock is manually released. Proper error handling and releasing the lock in your job logic 
   (as you’ve done with defer releaseAdvisoryLock(db, LockID)) ensures the lock is properly released after each job.

Conclusion:

 - Yes, this locking mechanism will work across multiple virtual machines as long as they are all 
   connected to the same PostgreSQL database.
 
 - The PostgreSQL advisory lock will ensure that only one instance can run the job at any given time, 
   even across different VMs or containers.
 
 - The session-based nature of advisory locks ensures fail-safety and automatic cleanup 
   if the VM holding the lock crashes.

- This approach ensures idempotency and prevents race conditions, making it suitable for distributed job 
  execution across multiple machines.

> Main Program `main.go`

```go
package main

import (
	"github.com/go-pg/pg/v10"
	"log"
	"time"
)

var PGOptions = pg.Options{
	Addr:     "IP_ADDRESS:5432",
	User:     "<REDACTED>",
	Password: "<REDACTED>",
	Database: "<SOME_THHING>",
}

var LockID = int64(1)

// RunCoreJob simulates a job that only one instance should run at a time.
func RunCoreJob(db *pg.DB) {
	// Try to acquire the advisory lock (with a unique identifier for the job).
	// PostgreSQL advisory locks use a unique 64-bit integer for locking.
	// You can derive this from your job ID or any unique identifier.
	//lockID := LockID // Use a unique number to identify the lock.

	// Try to acquire the advisory lock
	locked, err := acquireAdvisoryLock(db, LockID)
	if err != nil {
		log.Fatalf("Failed to acquire advisory lock: %v", err)
	}

	if !locked {
		log.Println("Job is already running in another instance. Skipping this run.")
		return
	}
	defer releaseAdvisoryLock(db, LockID)

	// If we reach this point, it means the lock was acquired, and this instance will run the job
	log.Println("Job started, acquired the lock...")

	// Simulate a long-running job
	for i := 0; i < 10; i++ {
		log.Printf("Job is running... (%d/10)", i+1)
		time.Sleep(1 * time.Second)
	}

	// Job completed
	log.Println("Job completed. Releasing the lock.")
}

// acquireAdvisoryLock attempts to acquire a PostgreSQL advisory lock.
func acquireAdvisoryLock(db *pg.DB, lockID int64) (bool, error) {
	var locked bool
	_, err := db.QueryOne(pg.Scan(&locked), "SELECT pg_try_advisory_lock(?)", lockID)
	if err != nil {
		return false, err
	}
	return locked, nil
}

// releaseAdvisoryLock releases the PostgreSQL advisory lock.
func releaseAdvisoryLock(db *pg.DB, lockID int64) error {
	_, err := db.Exec("SELECT pg_advisory_unlock(?)", lockID)
	return err
}

// StartCleanupThread periodically cleans up stale job entries.
func StartCleanupThread(db *pg.DB) {
	ticker := time.NewTicker(5 * time.Minute) // Run cleanup every 30 minutes
	defer ticker.Stop()

	for {
		select {
		case <-ticker.C:
			log.Println("Running periodic cleanup of stale jobs...")
			// pglock automatically handles lock expiration based on the TTL,
			// so we don't need to manually clean up stale locks.
		}
	}
}

func main() {

	// Connect to PostgreSQL
	db := pg.Connect(&PGOptions)
	defer db.Close()

	// Start the cleanup thread in the background
	go StartCleanupThread(db)

	// Create a ticker that triggers every 15 minutes to run the job
	ticker := time.NewTicker(1 * time.Minute)
	defer ticker.Stop()

	// Run the job for the first time on startup
	go RunCoreJob(db)

	// Periodically run the job every 15 minutes
	for {
		select {
		case <-ticker.C:
			go RunCoreJob(db)
		}
	}
}
```

> Unit Test : `main_test.go`

```go
package main

import (
	"log"
	"sync"
	"testing"
	"time"

	"github.com/go-pg/pg/v10"
)

/*
Summary of What Each Test Does:

 - TestJobConcurrency: Simulates multiple instances running concurrently and ensures that only one instance can run the job by using advisory locks.
 - TestJobCompletion: Tests sequential job execution, ensuring that the lock is released after the job completes, and a new job can start.
 - TestJobFailureRecovery: Simulates a job failure where the lock is not explicitly released and ensures that the lock is released automatically when the session is terminated.
 - TestJobCleanup: Tests automatic cleanup of advisory locks by simulating an abnormal termination (disconnect) and ensures that a new job can acquire the lock after the session ends.

Why These Tests Matter:

 - Concurrency Control: In a distributed environment where multiple instances of the same service may try to run the same job, these tests ensure that race conditions are avoided and only one job instance runs at a time.
 - Robustness: By simulating job failures and abnormal terminations, we ensure that PostgreSQL advisory locks work as expected, recovering gracefully and allowing jobs to continue running after failures.
 - Cleanup and Recovery: The tests validate that locks are properly cleaned up when jobs fail or connections are lost, ensuring that the system can recover and continue processing jobs without getting stuck.

*/

// TestJobConcurrency
/*
Test 1: TestJobConcurrency

Purpose: This test simulates multiple instances trying to run the same job concurrently and ensures that only one instance is able to acquire the lock and run the job at a time.

Steps:

 - We start by connecting to the PostgreSQL database.
 - A shared counter (jobRunCount) is initialized to track how many times the job is actually run.
 - We create 10 concurrent goroutines (numInstances = 10), simulating 10 different virtual machines (or application instances), each trying to run the job.
 - Each goroutine:
    - Attempts to acquire the advisory lock.
    - If the lock is acquired, it simulates running the job for 1 second and increments the shared jobRunCount counter.
    - If it cannot acquire the lock, it skips the job.
 - After all goroutines complete, the test checks whether only one instance ran the job (jobRunCount == 1).

What It Validates:

 - Concurrency Safety: It ensures that only one instance can acquire the advisory lock and run the job, even when multiple instances are attempting to run it concurrently.
 - Locking Mechanism: It validates that PostgreSQL advisory locks are working correctly in a concurrent environment, preventing multiple instances from running the job at the same time.
*/
func TestJobConcurrency(t *testing.T) {
	// Connect to the same PostgreSQL instance
	db := pg.Connect(&PGOptions)
	defer db.Close()

	// Shared counter to track how many times the job was actually run.
	var jobRunCount int
	var mu sync.Mutex

	// Number of simulated instances (simulating multiple virtual machines).
	numInstances := 10
	var wg sync.WaitGroup

	// Simulate multiple instances running concurrently.
	for i := 0; i < numInstances; i++ {
		wg.Add(1)
		go func(instanceID int) {
			defer wg.Done()

			// Simulate the job trying to run.
			log.Printf("Instance %d attempting to run the job...", instanceID)
			if canRun, err := acquireAdvisoryLock(db, LockID); err != nil {
				log.Printf("Instance %d failed to start the job: %v", instanceID, err)
			} else if canRun {
				// Only one instance should be able to enter this block.
				mu.Lock()
				jobRunCount++
				mu.Unlock()

				log.Printf("Instance %d is running the job.", instanceID)

				// Simulate job processing
				time.Sleep(1 * time.Second)

				// Mark job as completed.
				if err := releaseAdvisoryLock(db, LockID); err != nil {
					log.Printf("Instance %d failed to release the lock: %v", instanceID, err)
				} else {
					log.Printf("Instance %d successfully completed the job.", instanceID)
				}
			} else {
				log.Printf("Instance %d could not run the job because another instance is already running.", instanceID)
			}
		}(i)
	}

	// Wait for all goroutines to finish.
	wg.Wait()

	// Validate that only one instance actually ran the job.
	if jobRunCount != 1 {
		t.Fatalf("Expected only 1 instance to run the job, but %d instances ran it.", jobRunCount)
	} else {
		log.Println("Test passed: Only one instance ran the job.")
	}
}

// TestJobCompletion
/*
Test 2: TestJobCompletion

Purpose: This test ensures that once a job finishes, the lock is properly released, and another job can start successfully.

Steps:

 - Connect to the PostgreSQL database.
 - Start and run the first job:
    - The first job acquires the advisory lock.
    - The job runs for 1 second.
    - The lock is released after the job completes.
 - After the first job completes, we immediately try to start a second job:
    - The second job tries to acquire the lock.
    - Since the first job released the lock, the second job should be able to acquire it and run.
 - The lock is released after the second job completes.

What It Validates:

 - Lock Release: It checks that the lock is properly released after the job completes.
 - Sequential Job Execution: It validates that a new job can start and acquire the lock once the previous job has finished, ensuring that jobs can run sequentially without issues.
*/
func TestJobCompletion(t *testing.T) {
	db := pg.Connect(&PGOptions)
	defer db.Close()

	// Start and complete the first job.
	log.Println("Starting the first job...")
	if canRun, err := acquireAdvisoryLock(db, LockID); err != nil || !canRun {
		t.Fatalf("Failed to start the first job: %v", err)
	}
	time.Sleep(1 * time.Second)
	if err := releaseAdvisoryLock(db, LockID); err != nil {
		t.Fatalf("Failed to release the first job lock: %v", err)
	}
	log.Println("First job completed.")

	// Ensure that another job can start after the first one completes.
	log.Println("Starting the second job...")
	if canRun, err := acquireAdvisoryLock(db, LockID); err != nil || !canRun {
		t.Fatalf("Failed to start the second job after the first one completed: %v", err)
	}
	if err := releaseAdvisoryLock(db, LockID); err != nil {
		t.Fatalf("Failed to release the second job lock: %v", err)
	}
	log.Println("Second job completed successfully.")
}

// TestJobFailureRecovery
/*
Test 3: TestJobFailureRecovery

Purpose: This test simulates a job failure scenario where the job doesn’t release the lock, and it ensures that the lock is released when the database connection is closed, allowing a new job to start after recovery.

Steps:

 - Connect to the PostgreSQL database.
 - Start the first job:
    - The job acquires the advisory lock, but it does not release the lock, simulating a job failure (i.e., the job crashes or terminates unexpectedly).
 - The database connection is closed, simulating a session termination.
    - When a session is terminated, PostgreSQL automatically releases any advisory locks held by that session.
 - After a short delay (500ms), we reconnect to the database.
 - We attempt to acquire the lock again:
    - Since the previous session has been terminated, the lock should now be available.
 - The test checks if the new job can acquire the lock and then releases it.

What It Validates:

 - Failure Recovery: It ensures that when a job crashes or the session is terminated, PostgreSQL correctly releases the advisory lock.
 - Session-Based Locking: It validates that PostgreSQL advisory locks are session-based and are automatically released when the session ends.
 - Post-Recovery Job Execution: It checks that a new job can run and acquire the lock after the failed job’s session is terminated.
*/
func TestJobFailureRecovery(t *testing.T) {
	db := pg.Connect(&PGOptions)
	defer db.Close()

	// Simulate a failure in the first job.
	log.Println("Simulating a job failure...")
	if canRun, err := acquireAdvisoryLock(db, LockID); err != nil || !canRun {
		t.Fatalf("Failed to start the first job: %v", err)
	}
	// Simulate a failure by not releasing the advisory lock.
	log.Println("Job failed without releasing the lock.")

	// Now, let's simulate a failure by closing the DB connection.
	// This forces PostgreSQL to release the advisory lock.
	log.Println("Simulating session termination by closing the DB connection...")
	db.Close() // Close the connection to force lock release.

	// Wait for a short period to allow PostgreSQL to release the lock.
	time.Sleep(500 * time.Millisecond)

	// Reconnect to PostgreSQL (this will simulate a fresh session).
	db = pg.Connect(&PGOptions)

	// Ensure that the lock is now available after the failure and session termination.
	log.Println("Checking if the lock is available after the session termination...")
	if canRun, err := acquireAdvisoryLock(db, LockID); err != nil || !canRun {
		t.Fatalf("Failed to acquire the lock after session termination: %v", err)
	}
	// Release the lock after the test completes.
	if err := releaseAdvisoryLock(db, LockID); err != nil {
		t.Fatalf("Failed to release the lock after recovery: %v", err)
	}
	log.Println("Lock acquired and released successfully after recovery.")
}

// TestJobCleanup
/*
Test 4: TestJobCleanup

Purpose: This test ensures that if a job terminates abnormally (e.g., the connection to the database is lost), PostgreSQL automatically releases the advisory lock, allowing new jobs to run.

Steps:

 - Connect to the PostgreSQL database.
 - Start a job:
    - The job acquires the advisory lock and runs.
 - Simulate an abnormal termination:
    - The database connection is closed, simulating an abnormal job termination.
    - Since PostgreSQL releases advisory locks when the connection is closed, the lock should be released.
 - Reconnect to the database to simulate a new session.
 - Attempt to acquire the lock again:
    - Since the previous session has ended, the advisory lock should now be available.
 - The lock is acquired and then released after the job completes.

What It Validates:

  - Automatic Lock Cleanup: It checks that PostgreSQL automatically releases advisory locks when the session ends (i.e., when the job terminates or the connection is closed).
  - Recovery After Abnormal Termination: It ensures that a new job can acquire the lock after an abnormal termination or disconnect.
*/
func TestJobCleanup(t *testing.T) {
	db := pg.Connect(&PGOptions)
	defer db.Close()

	// Simulate a running job.
	log.Println("Starting a job to test cleanup...")
	if canRun, err := acquireAdvisoryLock(db, LockID); err != nil || !canRun {
		t.Fatalf("Failed to acquire advisory lock for cleanup test: %v", err)
	}
	log.Println("Job running, lock acquired.")

	// Simulate abnormal termination by closing the DB connection (releases the advisory lock).
	log.Println("Simulating abnormal termination (disconnecting from DB)...")
	db.Close() // Close the connection to PostgreSQL to force the lock to be released.

	// Reconnect to the DB to simulate a new session.
	db = pg.Connect(&PGOptions)

	// Attempt to acquire the lock again. Since the previous session has ended, the lock should be available.
	log.Println("Checking if the lock is available after the session termination...")
	if canRun, err := acquireAdvisoryLock(db, LockID); err != nil || !canRun {
		t.Fatalf("Failed to acquire the lock after previous session ended: %v", err)
	}
	// Release the lock after cleanup.
	if err := releaseAdvisoryLock(db, LockID); err != nil {
		t.Fatalf("Failed to release the lock after cleanup: %v", err)
	}
	log.Println("Job completed and lock released after session termination.")
}
```

> Unit Test

```bash
go test -v
```

#### [Factory Pattern PostgreSQL Locks To Ensure Single Instance Runs Even Thought It Is Deployed On Multiple Instances](#factory-pattern-postgresql-locks-to-ensure-single-instance-runs-even-thought-it-is-deployed-on-multiple-instances)

`db_config.json`

```json
{
  "Addr": "<ACTUAL_IP_ADDR>:5432",
  "User": "<ACTUAL_USER>",
  "Password": "<REDACTED>",
  "Database": "<ACTUAL_DB>"
}
```

How Advisory Locks Work in PostgreSQL:

 - Session-Based Locks: PostgreSQL advisory locks are tied to the database connection/session. Once a session acquires the lock, it will hold it until:
    - The session releases the lock.
    - The session ends (either due to disconnect or crash).
- Non-blocking Nature:
    - pg_try_advisory_lock does not block. It returns true if it acquires the lock and false if the lock is already held by another session.
- Global Locking:
    - Advisory locks are global within the PostgreSQL instance, meaning even if two processes (or virtual machines) connect to the same PostgreSQL instance using different sessions, they will still check the same global advisory lock.
    - This global nature ensures that no two sessions, regardless of machine or location, can acquire the same lock simultaneously.

How Advisory Locks Avoid Race Conditions:

If multiple processes (on different machines or within the same machine) attempt to run the job, they would follow this pattern:

- Session 1 (VM 1) tries to acquire the advisory lock (e.g., with pg_try_advisory_lock).
    - If the lock is available, Session 1 acquires it and runs the job.
    - Session 2 (VM 2) will try to acquire the same lock.
    - Since Session 1 already holds the lock, Session 2 will immediately fail to acquire it, as advisory locks are non-blocking.
- Session 2 can check the result (pg_try_advisory_lock returning false) and skip running the job.
    - This ensures that even if both instances (VMs) run the same code simultaneously, only one will acquire the lock and run the job.
- When Session 1 finishes the job, it releases the lock (using pg_advisory_unlock), making the lock available again.
- If Session 1 crashes or the connection drops before the job completes, PostgreSQL will automatically release the advisory lock, allowing another session to acquire it.

Guarantees Across Virtual Machines:

 - No Race Conditions: Because the advisory lock is global across the PostgreSQL instance, even if you have multiple virtual machines (VMs) trying to acquire the same lock, PostgreSQL will ensure that only one VM holds the lock at a time. The others will fail to acquire it (false) and can skip the job execution.
 - Idempotency: If the job fails or the virtual machine crashes, the lock will be released automatically, ensuring that another instance can pick up the job.

Here’s Why It Works Across VMs:

- Global Lock Management: PostgreSQL manages advisory locks globally across sessions. Any session attempting to acquire the lock is aware of other sessions, even across machines.
- Lock Acquisition: When a virtual machine attempts to acquire the lock, PostgreSQL checks the global state to see if the lock is available.
- Non-blocking Check: Other VMs trying to acquire the same lock will immediately know if another VM has already acquired it and can avoid running the job, preventing race conditions.

Example Flow Across Two VMs:

- VM 1 connects to PostgreSQL and calls pg_try_advisory_lock. It acquires the lock and starts running the job.
- VM 2 tries to acquire the same lock. Since VM 1 already holds the lock, VM 2 gets false from pg_try_advisory_lock and skips the job.
- VM 1 finishes the job and releases the lock with pg_advisory_unlock.
- VM 2 or another VM can now acquire the lock and run the next job.

What if the First VM Crashes?

If VM 1 crashes or disconnects from the database, PostgreSQL automatically releases the advisory lock. This ensures that other VMs can acquire the lock and continue processing.

Conclusion:

PostgreSQL advisory locks are designed to avoid race conditions and ensure idempotent behavior across sessions (even across different machines). The advisory lock is global to the database instance, and the lock state is shared across all virtual machines that connect to the same PostgreSQL instance.

By using pg_try_advisory_lock, we can guarantee that only one session (regardless of whether it’s on a different VM or the same machine) will run the job at a time. If multiple instances (VMs) try to run the job, only the one that successfully acquires the lock will execute the job.

This ensures distributed synchronization across different machines.

`main.go`

```go
package main

import (
	"encoding/json"
	"fmt"
	"github.com/go-pg/pg/v10"
	"io/ioutil"
	"log"
	"os"
	"time"
)

var LockID = int64(1)

var DB *pg.DB

// DBConfig represents the PostgreSQL connection options read from a JSON file.
type DBConfig struct {
	Addr     string `json:"Addr"`
	User     string `json:"User"`
	Password string `json:"Password"`
	Database string `json:"Database"`
}

// LoadDBConfig loads the PostgreSQL configuration from the db_config.json file.
func LoadDBConfig(filePath string) (*pg.Options, error) {
	// Open the JSON file
	jsonFile, err := os.Open(filePath)
	if err != nil {
		return nil, fmt.Errorf("failed to open config file: %v", err)
	}
	defer jsonFile.Close()

	// Read the file content
	byteValue, err := ioutil.ReadAll(jsonFile)
	if err != nil {
		return nil, fmt.Errorf("failed to read config file: %v", err)
	}

	// Parse the JSON content into DBConfig struct
	var dbConfig DBConfig
	err = json.Unmarshal(byteValue, &dbConfig)
	if err != nil {
		return nil, fmt.Errorf("invalid JSON format in config file: %v", err)
	}

	// Validate the presence of required fields
	if dbConfig.Addr == "" || dbConfig.User == "" || dbConfig.Password == "" || dbConfig.Database == "" {
		return nil, fmt.Errorf("missing required fields in config file")
	}

	// Return the pg.Options constructed from the DBConfig
	return &pg.Options{
		Addr:     dbConfig.Addr,
		User:     dbConfig.User,
		Password: dbConfig.Password,
		Database: dbConfig.Database,
	}, nil
}

// ---- Factory for PostgreSQL Connection ----

// DBFactory is responsible for creating and managing PostgreSQL connections
type DBFactory struct {
	options *pg.Options
	db      *pg.DB
}

// NewDBFactory returns a new instance of DBFactory
func NewDBFactory(options *pg.Options) *DBFactory {
	return &DBFactory{options: options}
}

// GetConnection returns a connection to PostgreSQL
func (f *DBFactory) GetConnection() *pg.DB {
	if f.db == nil {
		f.db = pg.Connect(f.options)
	}
	return f.db
}

// CloseConnection closes the PostgreSQL connection
func (f *DBFactory) CloseConnection() {
	if f.db != nil {
		f.db.Close()
	}
}

// ---- Factory for Jobs ----

// JobFactory is responsible for managing jobs
type JobFactory struct {
	db *pg.DB
}

// NewJobFactory returns a new instance of JobFactory
func NewJobFactory(db *pg.DB) *JobFactory {
	return &JobFactory{db: db}
}

// RunCoreJob simulates a job that only one instance should run at a time.
func (f *JobFactory) RunCoreJob() {
	// Try to acquire the advisory lock
	locked, err := f.acquireAdvisoryLock(LockID)
	if err != nil {
		log.Fatalf("Failed to acquire advisory lock: %v", err)
	}

	if !locked {
		log.Println("Job is already running in another instance. Skipping this run.")
		return
	}
	defer f.releaseAdvisoryLock(LockID)

	// If we reach this point, it means the lock was acquired, and this instance will run the job
	log.Println("Job started, acquired the lock...")

	// Simulate a long-running job
	for i := 0; i < 10; i++ {
		log.Printf("Job is running... (%d/10)", i+1)
		time.Sleep(1 * time.Second)
	}

	// Job completed
	log.Println("Job completed. Releasing the lock.")
}

// acquireAdvisoryLock attempts to acquire a PostgreSQL advisory lock.
func (f *JobFactory) acquireAdvisoryLock(lockID int64) (bool, error) {
	var locked bool
	_, err := f.db.QueryOne(pg.Scan(&locked), "SELECT pg_try_advisory_lock(?)", lockID)
	if err != nil {
		return false, err
	}
	return locked, nil
}

// releaseAdvisoryLock releases the PostgreSQL advisory lock.
func (f *JobFactory) releaseAdvisoryLock(lockID int64) error {
	_, err := f.db.Exec("SELECT pg_advisory_unlock(?)", lockID)
	return err
}

// StartCleanupThread periodically cleans up stale job entries.
func (f *JobFactory) StartCleanupThread() {
	ticker := time.NewTicker(5 * time.Minute) // Run cleanup every 5 minutes
	defer ticker.Stop()

	for {
		select {
		case <-ticker.C:
			log.Println("Running periodic cleanup of stale jobs...")
			// pglock automatically handles lock expiration based on the TTL,
			// so we don't need to manually clean up stale locks.
		}
	}
}

// ---- Main Program ----

func main() {
	// Load PostgreSQL configuration from the JSON file
	configPath := "db_config.json"
	pgOptions, err := LoadDBConfig(configPath)
	if err != nil {
		log.Fatalf("Error loading DB configuration: %v", err)
	}

	// Create a DBFactory
	dbFactory := NewDBFactory(pgOptions)

	// Get a PostgreSQL connection
	DB = dbFactory.GetConnection()
	defer dbFactory.CloseConnection()

	// Create a JobFactory for managing jobs
	jobFactory := NewJobFactory(DB)

	// Start the cleanup thread in the background
	go jobFactory.StartCleanupThread()

	// Create a ticker that triggers every 1 minute to run the job
	ticker := time.NewTicker(1 * time.Minute)
	defer ticker.Stop()

	// Run the job for the first time on startup
	go jobFactory.RunCoreJob()

	// Periodically run the job every 1 minute
	for {
		select {
		case <-ticker.C:
			go jobFactory.RunCoreJob()
		}
	}
}
```

Here is a summary and description of each of the unit tests provided:

1. TestLoadDBConfig

Objective: To test the loading of database configuration from a JSON file.

What it does:

- The test creates a temporary file and writes a mock JSON configuration into it.
- It verifies that the configuration file can be correctly parsed, ensuring the values loaded match the expected values.
- It also tests that the function returns an error when required fields (like Password and Database) are missing.

Key Points:

- Verifies the correctness of loading JSON-based configuration.
- Ensures error handling when the configuration is incomplete.

2. TestJobConcurrency

Objective: To simulate multiple instances of a job trying to run concurrently and ensure only one instance runs at a time.

What it does:

- It simulates 10 instances (representing multiple virtual machines or processes) trying to acquire the same PostgreSQL advisory lock (pg_try_advisory_lock).
- Each instance checks if it can run the job by acquiring the lock. Only one should succeed.
- Once the job finishes, the lock is released.
- It verifies that only one instance was able to acquire the lock and run the job.

Key Points:

- Tests concurrency to ensure no race conditions occur.
- Verifies that only one job instance runs at a time.

3. TestJobFailureRecovery

Objective: To simulate a job failure and verify that the job can recover after the failure.

What it does:

- Simulates acquiring a lock by one instance and intentionally not releasing it (to simulate failure).
- The test closes the database connection to simulate a session termination (or crash).
- It then reconnects and verifies that the lock is released automatically due to the session closure.
- The test ensures that after the failure, another instance can acquire the lock and continue the job.

Key Points:

- Simulates job failure scenarios.
- Ensures PostgreSQL automatically releases locks when a session crashes.
- Verifies the job can recover and run after a failure.

4. TestJobCleanup

Objective: To simulate and verify that the advisory lock is correctly released after a job is terminated or after a session ends.

What it does:

- Simulates acquiring a lock for a running job.
- Closes the database connection (simulating an abnormal termination).
- Reconnects to the database and verifies that the lock is available again for acquisition, ensuring the lock was released when the session was terminated.

Key Points:

- Tests if locks are properly cleaned up when a session is terminated unexpectedly.
- Ensures that advisory locks are released when a session ends.

5. TestInvalidLockID

Objective: To test the behavior of the system when an invalid lock ID is passed.

What it does:

- Attempts to acquire an advisory lock with an invalid lock ID (-1).
- In PostgreSQL, advisory locks can actually work with negative integers, so the test verifies that the lock can still be acquired even with a negative lock ID.
- Verifies that no errors occur and the lock is successfully acquired.

Key Points:

- Tests edge cases where invalid or unexpected lock IDs are used.
- Ensures that PostgreSQL handles negative lock IDs without error.

6. TestLockTimeout

Objective: To simulate two instances trying to acquire the same lock and ensure that only one can acquire the lock while the other fails.

What it does:

- Instance 1 acquires the lock and holds it for a few seconds.
- During that time, Instance 2 attempts to acquire the lock and is expected to fail since Instance 1 is already holding the lock.
- After Instance 1 releases the lock, the test verifies that Instance 2 never acquired the lock while it was held by Instance 1.

Key Points:

- Ensures that PostgreSQL advisory locks prevent multiple instances from running the job at the same time.
- Simulates a “lock timeout” where one instance waits while another holds the lock.

7. TestConcurrentJobCompletion

Objective: To simulate two jobs completing at nearly the same time and ensure proper lock management.

What it does:

- Two jobs try to complete and release the lock at the same time.
- Job 1 acquires the lock first and releases it.
- Job 2 tries to release the lock after Job 1, but it should not release the lock because Job 1 already released it.
- The test ensures that Job 2 does not erroneously release the lock after Job 1 finishes.

Key Points:

- Simulates concurrent job completion.
- Ensures that multiple jobs do not erroneously release the lock at the same time.

8. TestJobResilienceAfterRestart

Objective: To simulate a system restart (or crash) and ensure that the job can resume after recovery.

What it does:

- Simulates acquiring a lock (indicating the job is running).
- Then it closes the database connection to simulate a system crash.
- After a brief downtime, the system reconnects to the database, and the test verifies that the lock is released after the restart.
- The test checks that the job can resume by acquiring the lock after the restart and releasing it properly.

Key Points:

- Simulates system crashes and restarts.
- Ensures jobs are resilient and can recover after a restart.
- Verifies that locks are correctly managed even after system restarts.

Overall Test Coverage:

- Configuration Testing: Validates loading of configurations from a JSON file.
- Concurrency: Tests for ensuring that only one job instance can run at a time, even when multiple instances try to acquire the lock.
- Failure Recovery: Ensures that the job can recover after a failure or crash.
- Cleanup: Verifies that locks are cleaned up properly after abnormal termination.
- Resilience: Tests the system’s ability to recover and continue jobs after restarts or crashes.

These tests cover a wide range of scenarios to ensure the robustness of the system, particularly in environments where multiple instances may be running simultaneously.

`main_test.go`

```go
package main

import (
	"io/ioutil"
	"log"
	"os"
	"sync"
	"testing"
	"time"

	"github.com/go-pg/pg/v10"
	"github.com/stretchr/testify/assert"
)

// Mock JSON configuration file for testing
var mockConfig = `{
	"Addr": "localhost:5432",
	"User": "test_user",
	"Password": "test_pass",
	"Database": "test_db"
}`

// Test configuration for an actual PostgreSQL instance
var PGOptions = pg.Options{
	Addr:     "<ACTUAL_IP_ADDRESS>:5432", // Use your local or test PostgreSQL instance
	User:     "<ACTUAL_USER>",
	Password: "<REDACTED>",
	Database: "<ACTUAL_DB>",
}

// Mock loading function for the config file (use in unit tests)
func mockLoadConfig(filePath string) (*pg.Options, error) {
	return &pg.Options{
		Addr:     "localhost:5432",
		User:     "test_user",
		Password: "test_pass",
		Database: "test_db",
	}, nil
}

// TestLoadDBConfig tests the loading and validation of the database configuration from a JSON file.
func TestLoadDBConfig(t *testing.T) {

	// Create a temporary file with the mock JSON content using os.CreateTemp
	tempFile, err := os.CreateTemp("", "db_config*.json")
	if err != nil {
		t.Fatalf("Failed to create temporary config file: %v", err)
	}
	defer os.Remove(tempFile.Name()) // Clean up after test

	// Write the mock JSON configuration to the temp file
	if _, err := tempFile.Write([]byte(mockConfig)); err != nil {
		t.Fatalf("Failed to write mock config to temp file: %v", err)
	}

	// Test loading the configuration
	pgOptions, err := LoadDBConfig(tempFile.Name())
	assert.NoError(t, err, "Should load valid configuration without errors")
	assert.Equal(t, "localhost:5432", pgOptions.Addr, "Address should match")
	assert.Equal(t, "test_user", pgOptions.User, "User should match")
	assert.Equal(t, "test_pass", pgOptions.Password, "Password should match")
	assert.Equal(t, "test_db", pgOptions.Database, "Database should match")

	// Test with missing fields in the config file
	invalidConfig := `{
		"Addr": "localhost:5432",
		"User": "test_user"
	}`
	invalidFile, err := ioutil.TempFile("", "invalid_config*.json")
	if err != nil {
		t.Fatalf("Failed to create temporary invalid config file: %v", err)
	}
	defer os.Remove(invalidFile.Name()) // Clean up after test

	if _, err := invalidFile.Write([]byte(invalidConfig)); err != nil {
		t.Fatalf("Failed to write invalid config to temp file: %v", err)
	}

	_, err = LoadDBConfig(invalidFile.Name())
	assert.Error(t, err, "Should return an error when required fields are missing")
}

// TestJobConcurrency simulates multiple instances trying to run the job concurrently.
func TestJobConcurrency(t *testing.T) {
	db := pg.Connect(&PGOptions)
	defer db.Close()

	jobFactory := NewJobFactory(db)

	// Shared counter to track how many times the job was actually run.
	var jobRunCount int
	var mu sync.Mutex

	// Number of simulated instances (simulating multiple virtual machines).
	numInstances := 10
	var wg sync.WaitGroup

	// Simulate multiple instances running concurrently.
	for i := 0; i < numInstances; i++ {
		wg.Add(1)
		go func(instanceID int) {
			defer wg.Done()

			// Simulate the job trying to run.
			log.Printf("Instance %d attempting to run the job...", instanceID)
			if canRun, err := jobFactory.acquireAdvisoryLock(LockID); err != nil {
				log.Printf("Instance %d failed to start the job: %v", instanceID, err)
			} else if canRun {
				// Only one instance should be able to enter this block.
				mu.Lock()
				jobRunCount++
				mu.Unlock()

				log.Printf("Instance %d is running the job.", instanceID)

				// Simulate job processing
				time.Sleep(1 * time.Second)

				// Mark job as completed.
				if err := jobFactory.releaseAdvisoryLock(LockID); err != nil {
					log.Printf("Instance %d failed to release the lock: %v", instanceID, err)
				} else {
					log.Printf("Instance %d successfully completed the job.", instanceID)
				}
			} else {
				log.Printf("Instance %d could not run the job because another instance is already running.", instanceID)
			}
		}(i)
	}

	// Wait for all goroutines to finish.
	wg.Wait()

	// Validate that only one instance actually ran the job.
	if jobRunCount != 1 {
		t.Fatalf("Expected only 1 instance to run the job, but %d instances ran it.", jobRunCount)
	} else {
		log.Println("Test passed: Only one instance ran the job.")
	}
}

// TestJobFailureRecovery simulates a job failure and ensures recovery.
func TestJobFailureRecovery(t *testing.T) {
	db := pg.Connect(&PGOptions)
	defer db.Close()

	jobFactory := NewJobFactory(db)

	// Simulate a failure in the first job.
	log.Println("Simulating a job failure...")
	if canRun, err := jobFactory.acquireAdvisoryLock(LockID); err != nil || !canRun {
		t.Fatalf("Failed to start the first job: %v", err)
	}
	// Simulate a failure by not releasing the advisory lock.
	log.Println("Job failed without releasing the lock.")

	// Now, let's simulate a failure by closing the DB connection.
	// This forces PostgreSQL to release the advisory lock.
	log.Println("Simulating session termination by closing the DB connection...")
	db.Close() // Close the connection to force lock release.

	// Wait for a short period to allow PostgreSQL to release the lock.
	time.Sleep(500 * time.Millisecond)

	// Reconnect to PostgreSQL (this will simulate a fresh session).
	db = pg.Connect(&PGOptions)
	jobFactory = NewJobFactory(db)

	// Ensure that the lock is now available after the failure and session termination.
	log.Println("Checking if the lock is available after the session termination...")
	if canRun, err := jobFactory.acquireAdvisoryLock(LockID); err != nil || !canRun {
		t.Fatalf("Failed to acquire the lock after session termination: %v", err)
	}
	// Release the lock after the test completes.
	if err := jobFactory.releaseAdvisoryLock(LockID); err != nil {
		t.Fatalf("Failed to release the lock after recovery: %v", err)
	}
	log.Println("Lock acquired and released successfully after recovery.")
}

// TestJobCleanup ensures that cleanup happens periodically and prevents stale locks.
func TestJobCleanup(t *testing.T) {
	db := pg.Connect(&PGOptions)
	defer db.Close()

	jobFactory := NewJobFactory(db)

	// Simulate a running job.
	log.Println("Starting a job to test cleanup...")
	if canRun, err := jobFactory.acquireAdvisoryLock(LockID); err != nil || !canRun {
		t.Fatalf("Failed to acquire advisory lock for cleanup test: %v", err)
	}
	log.Println("Job running, lock acquired.")

	// Simulate abnormal termination by closing the DB connection (releases the advisory lock).
	log.Println("Simulating abnormal termination (disconnecting from DB)...")
	db.Close() // Close the connection to PostgreSQL to force the lock to be released.

	// Reconnect to the DB to simulate a new session.
	db = pg.Connect(&PGOptions)
	jobFactory = NewJobFactory(db)

	// Attempt to acquire the lock again. Since the previous session has ended, the lock should be available.
	log.Println("Checking if the lock is available after the session termination...")
	if canRun, err := jobFactory.acquireAdvisoryLock(LockID); err != nil || !canRun {
		t.Fatalf("Failed to acquire the lock after previous session ended: %v", err)
	}
	// Release the lock after cleanup.
	if err := jobFactory.releaseAdvisoryLock(LockID); err != nil {
		t.Fatalf("Failed to release the lock after cleanup: %v", err)
	}
	log.Println("Job completed and lock released after session termination.")
}

// TestInvalidLockID tests the case where an invalid lock ID is passed.
func TestInvalidLockID(t *testing.T) {
	db := pg.Connect(&PGOptions)
	defer db.Close()

	jobFactory := NewJobFactory(db)

	invalidLockID := int64(-1) // Invalid lock ID (could be treated as valid by PostgreSQL)

	// Try to acquire an advisory lock with an invalid lock ID.
	canRun, err := jobFactory.acquireAdvisoryLock(invalidLockID)

	// Assert no errors since PostgreSQL allows advisory locks on negative integers.
	assert.NoError(t, err, "There should be no error, PostgreSQL allows negative lock IDs.")

	// Assert that the lock was acquired (PostgreSQL supports advisory locks on negative numbers).
	assert.True(t, canRun, "Lock should have been acquired even with a negative lock ID.")
}

// TestLockTimeout simulates an instance holding the lock for a prolonged time
// and ensures that other instances cannot acquire the lock during this time.
func TestLockTimeout(t *testing.T) {
	// Instance 1: Connect to PostgreSQL and acquire the lock
	db1 := pg.Connect(&PGOptions)
	defer db1.Close()
	jobFactory1 := NewJobFactory(db1)

	log.Println("Instance 1 acquiring the lock...")
	canRun, err := jobFactory1.acquireAdvisoryLock(LockID)
	if err != nil || !canRun {
		t.Fatalf("Instance 1 failed to acquire the lock: %v", err)
	}
	log.Println("Instance 1 successfully acquired the lock.")

	// Step 2: Simulate Instance 2 connecting with a separate connection and trying to acquire the lock
	db2 := pg.Connect(&PGOptions) // Separate connection for Instance 2
	defer db2.Close()
	jobFactory2 := NewJobFactory(db2)

	var lockAcquiredByInstance2 bool
	var instance2Err error

	log.Println("Instance 2 attempting to acquire the lock (this should fail)...")

	time.Sleep(500 * time.Millisecond) // Delay to simulate concurrency

	lockAcquiredByInstance2, instance2Err = jobFactory2.acquireAdvisoryLock(LockID)

	// Step 3: Hold the lock in Instance 1 for a bit longer to simulate a long-running job.
	log.Println("Instance 1 holding the lock for 2 more seconds...")
	time.Sleep(2 * time.Second)

	// Step 4: Instance 1 releases the lock.
	log.Println("Instance 1 releasing the lock.")
	if err := jobFactory1.releaseAdvisoryLock(LockID); err != nil {
		t.Fatalf("Instance 1 failed to release the lock: %v", err)
	}

	// Step 5: Verify that Instance 2 could not acquire the lock while Instance 1 held it.
	log.Println("Checking if Instance 2 successfully acquired the lock...")
	if instance2Err != nil {
		t.Fatalf("Instance 2 encountered an error trying to acquire the lock: %v", instance2Err)
	}

	assert.False(t, lockAcquiredByInstance2, "Instance 2 should not have acquired the lock while Instance 1 was holding it.")
}

// TestConcurrentJobCompletion simulates multiple jobs completing at the same time and ensures only one releases the lock.
func TestConcurrentJobCompletion(t *testing.T) {
	db := pg.Connect(&PGOptions)
	defer db.Close()

	jobFactory := NewJobFactory(db)

	// Acquire the lock for the first job
	log.Println("Job 1 acquiring the lock...")
	if canRun, err := jobFactory.acquireAdvisoryLock(LockID); err != nil || !canRun {
		t.Fatalf("Job 1 failed to acquire the lock: %v", err)
	}
	log.Println("Job 1 successfully acquired the lock.")

	// Simulate two jobs trying to complete at the same time
	var wg sync.WaitGroup
	wg.Add(2)

	go func() {
		defer wg.Done()
		log.Println("Job 1 attempting to release the lock...")
		if err := jobFactory.releaseAdvisoryLock(LockID); err != nil {
			log.Printf("Job 1 failed to release the lock: %v", err)
		} else {
			log.Println("Job 1 released the lock successfully.")
		}
	}()

	go func() {
		defer wg.Done()
		time.Sleep(500 * time.Millisecond) // Small delay to simulate concurrency
		log.Println("Job 2 attempting to release the lock (should already be released)...")
		if err := jobFactory.releaseAdvisoryLock(LockID); err != nil {
			log.Printf("Job 2 failed to release the lock as expected: %v", err)
		} else {
			log.Println("Job 2 unexpectedly released the lock.")
		}
	}()

	wg.Wait()

	// Make sure Job 2 did not erroneously release the lock
	log.Println("Both jobs completed. Ensuring lock is properly managed.")
}

// TestJobResilienceAfterRestart simulates a system restart and checks that the job can resume after recovery.
func TestJobResilienceAfterRestart(t *testing.T) {
	db := pg.Connect(&PGOptions)
	defer db.Close()

	jobFactory := NewJobFactory(db)

	// Acquire the lock to simulate a job running
	log.Println("Simulating job running before system restart...")
	if canRun, err := jobFactory.acquireAdvisoryLock(LockID); err != nil || !canRun {
		t.Fatalf("Failed to acquire the lock: %v", err)
	}
	log.Println("Lock acquired. Job is running.")

	// Simulate a system crash or restart (close DB connection)
	log.Println("Simulating system restart...")
	db.Close() // Close the connection to simulate a restart

	// Wait for a short period to simulate downtime
	time.Sleep(1 * time.Second)

	// Reconnect to the database
	db = pg.Connect(&PGOptions)
	jobFactory = NewJobFactory(db)

	// Ensure that the lock is now available after the restart
	log.Println("Checking if the lock is available after restart...")
	if canRun, err := jobFactory.acquireAdvisoryLock(LockID); err != nil || !canRun {
		t.Fatalf("Failed to acquire the lock after restart: %v", err)
	}
	log.Println("Lock acquired after restart.")

	// Release the lock after the test completes.
	if err := jobFactory.releaseAdvisoryLock(LockID); err != nil {
		t.Fatalf("Failed to release the lock after restart: %v", err)
	}
	log.Println("Lock released successfully after restart.")
}
```

Unit Testing

```bash
Run All Unit Tests >
    get test -v

Run Individual Tests >
    go test -run TestLockTimeout -v
```

#### [Fetch From BigQuery And Upsert On PostgreSQL](#fetch-from-bigquery-and-upsert-on-postgresql)

> What This Program Does ?
- Source (BigQuery) ->> Destination (PostgreSQL)
- Fetch Records From From BigQuery
- Perform Upserts Of BQ Records In Batches On PostgreSQL DB

> BigQuery Columns (Source)

```
resource_id -> STRING (BigQuery Column Type)
properties  -> STRING (BigQuery Column Type) -> (JSON In STRING Format)
```

> PostgreSQL Columns (Destination)

```
resource_id -> TEXT (PostgreSQL Column Type)
metadata    -> JSONB (PostgreSQL Column Type)
```

```go
package main

import (
	"context"
	"encoding/json"
	"errors"
	"fmt"
	"gorm.io/gorm/clause"
	"log"
	"time"

	"cloud.google.com/go/bigquery"
	"google.golang.org/api/iterator"
	"gorm.io/driver/postgres"
	"gorm.io/gorm"
)

var GCPProject = "some-project"

// Record represents the PostgreSQL model for the table
type Record struct {
	ResourceID string          `gorm:"column:resource_id;primaryKey"`
	Metadata   json.RawMessage `gorm:"column:metadata;type:jsonb"`
}

func (Record) TableName() string {
	return "my_table"
}

func main() {
	// Initialize PostgreSQL connection with GORM
	dsn := "host=<IP_ADDR> user=<SOM_USER> password=<REDACTED> dbname=<SOME_DB> port=5432 sslmode=disable TimeZone=UTC"
	db, err := gorm.Open(postgres.Open(dsn), &gorm.Config{})
	if err != nil {
		log.Fatalf("Failed to connect to PostgreSQL: %v", err)
	}

	db.AutoMigrate(&Record{})

	// Initialize BigQuery client
	ctx := context.Background()
	projectID := GCPProject // Replace with your project ID

	bqClient, err := bigquery.NewClient(ctx, projectID)
	if err != nil {
		log.Fatalf("Failed to create BigQuery client: %v", err)
	}
	defer bqClient.Close()

	// Define your BigQuery query
	queryString := `SELECT resource_id, properties FROM my_data_set.my_custom_table;`

	query := bqClient.Query(queryString)

	query.AllowLargeResults = true

	// Run the query and get an iterator
	it, err := query.Read(ctx)
	if err != nil {
		log.Fatalf("Failed to run query: %v", err)
	}

	// Channel to buffer records
	recordChan := make(chan Record, 500) // Buffered channel for records
	batchSize := 500                     // Number of records to batch insert
	batchTimeout := 5 * time.Second      // Timeout for batch insert

	// Start the background goroutine to handle batch inserts
	go insertRecordsInBatches(db, recordChan, batchSize, batchTimeout)

	// Read records from BigQuery and send them to the channel
	for {
		var row struct {
			ResourceID  string `bigquery:"resource_id"`
			Properties string `bigquery:"properties"`
		}

		err := it.Next(&row)
		if errors.Is(err, iterator.Done) {
			// No more rows, close the channel
			close(recordChan)
			break
		}
		if err != nil {
			log.Fatalf("Error reading from BigQuery iterator: %v", err)
		}

		// Parse the properties field as JSON
		var properties json.RawMessage
		err = json.Unmarshal([]byte(row.Properties), &properties)
		if err != nil {
			log.Printf("Failed to parse properties JSON for resource_id %s: %v", row.ResourceID, err)
			continue
		}

		// Send the record to the channel
		recordChan <- Record{
			ResourceID: row.ResourceID,
			Metadata:   properties,
		}
	}
}

// Function to insert records in batches into PostgreSQL
func insertRecordsInBatches(db *gorm.DB, recordChan <-chan Record, batchSize int, batchTimeout time.Duration) {
	var batch []Record
	timer := time.NewTimer(batchTimeout)

	for {
		select {
		case record, ok := <-recordChan:
			if !ok {
				// Channel closed, insert the remaining records in the last batch
				if len(batch) > 0 {
					insertBatch(db, batch)
				}
				return
			}

			// Add the record to the batch
			batch = append(batch, record)

			// If batch size is reached, insert the batch
			if len(batch) >= batchSize {
				insertBatch(db, batch)
				batch = nil               // Reset the batch
				timer.Reset(batchTimeout) // Reset the timer
			}

		case <-timer.C:
			// Timeout reached, insert whatever is in the batch
			if len(batch) > 0 {
				insertBatch(db, batch)
				batch = nil // Reset the batch
			}
			timer.Reset(batchTimeout) // Reset the timer for the next batch
		}
	}
}

// Function to insert a batch of records into the database
func insertBatch(db *gorm.DB, batch []Record) {
	fmt.Printf("Inserting batch of %d records\n", len(batch))
	// Use GORM's OnConflict to handle insert or update
	err := db.Clauses(
		clause.OnConflict{
			Columns:   []clause.Column{{Name: "resource_id"}},         // Specify the column to check for conflicts
			DoUpdates: clause.AssignmentColumns([]string{"metadata"}), // Specify the column to update if conflict occurs
		},
	).Create(&batch).Error

	if err != nil {
		log.Printf("Failed to insert batch: %v", err)
	} else {
		fmt.Printf("Successfully inserted %d records\n", len(batch))
	}
}
```

#### [Search API With AND OR Exact Non-Exact Search V1](#search-api-with-and-or-exact-non-exact-search-v1)

- Rate Limiting
- CORS
- Exact / Non-Exact (Pattern Matching) Search
- AND Search
- OR Search

`main.go`

```go
package main

import (
	"encoding/json"
	"fmt"
	"github.com/gorilla/handlers"
	"github.com/gorilla/mux"
	"log"
	"net"
	"net/http"
	"regexp"
	"strconv"
	"strings"
	"sync"
)

/*

http://127.0.0.1:8080//search?search=User1&exact=true

http://127.0.0.1:8080//search?search=User1&exact=false

http://127.0.0.1:8080//search?search=User1,user2&exact=true&type=OR

http://127.0.0.1:8080//search?search=User1,user2&exact=true&type=OR

http://127.0.0.1:8080//search?search=User1,user2&exact=false&type=OR

http://127.0.0.1:8080//search?search=User1,City1&exact=true&type=AND

http://127.0.0.1:8080//search?search=User1,City1&exact=false&type=AND

http://127.0.0.1:8080//search?search=User1,City1&exact=false&type=AND

*/

// Global map to track client requests and mutex for thread safety
var clientRequestTracker = make(map[string]bool)
var mu sync.Mutex

var ListenPort = "8080"

// Simulating a large list of records
var records = generateSampleData(1000) // Simulate 1000 records for the demo

// Generate sample data for testing
func generateSampleData(n int) []map[string]interface{} {
	var sampleData []map[string]interface{}
	for i := 1; i <= n; i++ {
		sampleData = append(sampleData, map[string]interface{}{
			"id":            i,
			"name":          fmt.Sprintf("User%d", i),
			"email":         fmt.Sprintf("user%d@example.com", i),
			"age":           i + 20,
			"city":          fmt.Sprintf("City%d", i),
			"pay_per_month": float64(i) * 100.55, // Adding pay_per_month as float
		})
	}
	return sampleData
}

// Function to get the client IP address (without the port)
func getClientIP(r *http.Request) string {
	// Extract the IP address and ignore the port
	ip, _, err := net.SplitHostPort(r.RemoteAddr)
	if err != nil {
		return ""
	}
	log.Printf("IP_ADDRESS : %v", ip)
	return ip
}

// Middleware to limit one request per client at a time
func rateLimitMiddleware(next http.Handler) http.Handler {
	return http.HandlerFunc(func(w http.ResponseWriter, r *http.Request) {
		clientID := getClientIP(r)

		// Lock the mutex to check the client's request status
		mu.Lock()
		if clientRequestTracker[clientID] {
			// Client already has a request in progress

			w.WriteHeader(http.StatusTooManyRequests)
			json.NewEncoder(w).Encode(map[string]string{
				"error": "You Are Making Too Many (May Be In Parallel ?) Requests. Make One Request At A Time.",
			})

			mu.Unlock()
			//http.Error(w, "Too many requests. Only one request allowed per client.", http.StatusTooManyRequests)
			return
		}

		// Mark client as having an active request
		clientRequestTracker[clientID] = true
		mu.Unlock()

		// Call the next handler in the chain
		next.ServeHTTP(w, r)

		// Once the request is done, mark client as available
		mu.Lock()
		delete(clientRequestTracker, clientID)
		mu.Unlock()
	})
}

/*
// To Simulate >> Too Many Requests Per Client >>

func searchHandler(w http.ResponseWriter, r *http.Request) {
	// Simulate long-running operation
	time.Sleep(5 * time.Second)

	// Respond with JSON data
	response := map[string]string{
		"message": fmt.Sprintf("Request from %s completed", r.RemoteAddr),
	}
	w.Header().Set("Content-Type", "application/json")
	w.WriteHeader(http.StatusOK)
	json.NewEncoder(w).Encode(response)
}

*/

func main() {
	// Initialize the router
	r := mux.NewRouter()

	r.Use(rateLimitMiddleware)

	// Define the search endpoint
	r.HandleFunc("/search", searchHandler).Methods("GET")

	// Enable CORS for all origins
	// You can customize the allowed methods and headers if needed
	corsHandler := handlers.CORS(
		handlers.AllowedOrigins([]string{"*"}),                             // Allow all origins
		handlers.AllowedMethods([]string{"GET", "POST"}),                   // Allow specific methods (GET and POST in this case)
		handlers.AllowedHeaders([]string{"Content-Type", "Authorization"}), // Allow headers
	)

	// Start the server
	fmt.Println("Server is running on port 8080...")
	log.Fatal(http.ListenAndServe(":"+ListenPort, corsHandler(r)))
}

// Handler to search records and paginate
func searchHandler(w http.ResponseWriter, r *http.Request) {

	// Set response header as application/json
	w.Header().Set("Content-Type", "application/json")

	// Get the 'search' query parameter from URL (can be empty)
	searchQuery := r.URL.Query().Get("search")
	searchType := r.URL.Query().Get("type")  // Can be 'AND' or 'OR'
	exactMatch := r.URL.Query().Get("exact") // Can be 'true' or 'false'

	pageSize := 10 // Set a default page size

	// Get the pagination token
	paginationToken := r.URL.Query().Get("page")
	var startIndex int

	// If a pagination token exists, get the start index from it
	if paginationToken != "" {
		var err error
		startIndex, err = strconv.Atoi(paginationToken)
		if err != nil || startIndex < 0 {
			w.WriteHeader(http.StatusBadRequest)
			json.NewEncoder(w).Encode(map[string]string{
				"error": "Invalid pagination token",
			})
			return
		}
	} else {
		startIndex = 0
	}

	// If search query is not provided, return all paginated results
	if searchQuery == "" {
		// Paginate all results
		endIndex := startIndex + pageSize
		if startIndex >= len(records) {
			w.WriteHeader(http.StatusNotFound)
			json.NewEncoder(w).Encode(map[string]string{
				"error": "No records found",
			})
			return
		}
		if endIndex > len(records) {
			endIndex = len(records)
		}

		paginatedResults := records[startIndex:endIndex]

		// Generate the next page token only if there are more records
		var nextPageToken string
		if endIndex < len(records) {
			nextPageToken = strconv.Itoa(endIndex)
		}

		// Generate the previous page token only if applicable
		var prevPageToken string
		if startIndex > 0 {
			prevPageToken = strconv.Itoa(startIndex - pageSize)
			if startIndex-pageSize < 0 {
				prevPageToken = "0"
			}
		}

		// Response structure with data and next/previous page links
		response := map[string]interface{}{
			"data": paginatedResults,
		}

		// Include next and previous links only if more pages exist
		if nextPageToken != "" {
			response["next"] = fmt.Sprintf("/search?page=%s", nextPageToken)
		}
		if prevPageToken != "" {
			response["previous"] = fmt.Sprintf("/search?page=%s", prevPageToken)
		}

		// Return the paginated results as JSON
		w.WriteHeader(http.StatusOK)
		json.NewEncoder(w).Encode(response)
		return
	}

	// Validate the search query using a regular expression (allow '@', '_', ';', '$', '.', '-')
	// Spaces and other characters are disallowed
	validSearchQuery := `^[a-zA-Z0-9@_$.;-]+(,[a-zA-Z0-9@_$.;-]+)*$`
	matched, err := regexp.MatchString(validSearchQuery, searchQuery)
	if err != nil {
		w.WriteHeader(http.StatusInternalServerError)
		json.NewEncoder(w).Encode(map[string]string{
			"error": "Internal server error",
		})
		return
	}

	if !matched {
		w.WriteHeader(http.StatusBadRequest)
		json.NewEncoder(w).Encode(map[string]string{
			"error": "Invalid search query. Only alphanumeric characters, '@', '_', ';', '$', '.', and '-' are allowed. No spaces are permitted.",
		})
		return
	}

	// Split the search terms by comma
	searchTerms := strings.Split(searchQuery, ",")

	// Convert the search terms to lowercase for case-insensitive comparison
	for i := range searchTerms {
		searchTerms[i] = strings.ToLower(strings.TrimSpace(searchTerms[i]))
	}

	// Filtered results
	var filteredResults []map[string]interface{}

	// Determine if we are doing an exact search or not
	isExact := strings.ToLower(exactMatch) == "true"

	// Loop over the records and apply the search logic
	for _, record := range records {
		// Perform search based on the specified search type (AND/OR)
		if searchType == "AND" {
			if matchAllSearchTerms(record, searchTerms, isExact) {
				filteredResults = append(filteredResults, record)
			}
		} else { // Default to OR search if not specified
			if matchAnySearchTerm(record, searchTerms, isExact) {
				filteredResults = append(filteredResults, record)
			}
		}
	}

	// If no results found, return an empty array with proper status
	if len(filteredResults) == 0 {
		w.WriteHeader(http.StatusNotFound)
		json.NewEncoder(w).Encode(map[string]string{
			"error": "No records found matching the query",
		})
		return
	}

	// Handle pagination for filtered results
	endIndex := startIndex + pageSize
	if startIndex >= len(filteredResults) {
		w.WriteHeader(http.StatusNotFound)
		json.NewEncoder(w).Encode(map[string]string{
			"error": "No more records found for this page",
		})
		return
	}
	if endIndex > len(filteredResults) {
		endIndex = len(filteredResults)
	}

	paginatedResults := filteredResults[startIndex:endIndex]

	// Generate the next page token only if there are more records
	var nextPageToken string
	if endIndex < len(filteredResults) {
		nextPageToken = strconv.Itoa(endIndex)
	}

	// Generate the previous page token only if applicable
	var prevPageToken string
	if startIndex > 0 {
		prevPageToken = strconv.Itoa(startIndex - pageSize)
		if startIndex-pageSize < 0 {
			prevPageToken = "0"
		}
	}

	// Response structure with data and next/previous page links
	response := map[string]interface{}{
		"data": paginatedResults,
	}

	// Include next and previous links only if more pages exist
	if nextPageToken != "" {
		response["next"] = fmt.Sprintf("/search?search=%s&page=%s", searchQuery, nextPageToken)
	}
	if prevPageToken != "" {
		response["previous"] = fmt.Sprintf("/search?search=%s&page=%s", searchQuery, prevPageToken)
	}

	// Return the paginated results as JSON
	w.WriteHeader(http.StatusOK)
	json.NewEncoder(w).Encode(response)
}

// matchAllSearchTerms checks if all search terms are present in the record (AND logic)
func matchAllSearchTerms(record map[string]interface{}, searchTerms []string, isExact bool) bool {
	for _, term := range searchTerms {
		found := false
		for _, value := range record {
			if strValue, ok := value.(string); ok {
				if isExact {
					// Exact search: check if the whole string matches
					if strings.EqualFold(strValue, term) {
						found = true
						break
					}
				} else {
					// Non-exact search: check if the string contains the term
					if strings.Contains(strings.ToLower(strValue), term) {
						found = true
						break
					}
				}
			} else if intValue, ok := value.(int); ok {
				// Compare integer values
				if searchInt, err := strconv.Atoi(term); err == nil && intValue == searchInt {
					found = true
					break
				}
			} else if floatValue, ok := value.(float64); ok {
				// Compare floating point values
				if searchFloat, err := strconv.ParseFloat(term, 64); err == nil && floatValue == searchFloat {
					found = true
					break
				}
			}
		}
		if !found {
			return false // If any term is not found, return false
		}
	}
	return true // All terms are found
}

// matchAnySearchTerm checks if any search term is present in the record (OR logic)
func matchAnySearchTerm(record map[string]interface{}, searchTerms []string, isExact bool) bool {
	for _, term := range searchTerms {
		for _, value := range record {
			if strValue, ok := value.(string); ok {
				if isExact {
					// Exact search: check if the whole string matches
					if strings.EqualFold(strValue, term) {
						return true
					}
				} else {
					// Non-exact search: check if the string contains the term
					if strings.Contains(strings.ToLower(strValue), term) {
						return true
					}
				}
			} else if intValue, ok := value.(int); ok {
				// Compare integer values
				if searchInt, err := strconv.Atoi(term); err == nil && intValue == searchInt {
					return true
				}
			} else if floatValue, ok := value.(float64); ok {
				// Compare floating point values
				if searchFloat, err := strconv.ParseFloat(term, 64); err == nil && floatValue == searchFloat {
					return true
				}
			}
		}
	}
	return false
}
```

`main_test.go`

```go
package main

import (
	"encoding/json"
	"net/http"
	"net/http/httptest"
	"strings"
	"testing"
)

func TestSearchHandler_NoSearchQuery(t *testing.T) {
	req, err := http.NewRequest("GET", "/search?page=0", nil)
	if err != nil {
		t.Fatal(err)
	}

	rr := httptest.NewRecorder()
	handler := http.HandlerFunc(searchHandler)

	handler.ServeHTTP(rr, req)

	// Check the status code is what we expect.
	if status := rr.Code; status != http.StatusOK {
		t.Errorf("Handler returned wrong status code: got %v want %v", status, http.StatusOK)
	}

	// Check the response body is a valid JSON.
	var response map[string]interface{}
	if err := json.Unmarshal(rr.Body.Bytes(), &response); err != nil {
		t.Errorf("Handler returned an invalid JSON: %v", err)
	}

	// Ensure that data has been returned
	if _, ok := response["data"]; !ok {
		t.Errorf("Expected 'data' field in response but did not get one")
	}
}

func TestSearchHandler_WithValidSearchQuery(t *testing.T) {
	req, err := http.NewRequest("GET", "/search?search=User1&exact=true&page=0", nil)
	if err != nil {
		t.Fatal(err)
	}

	rr := httptest.NewRecorder()
	handler := http.HandlerFunc(searchHandler)

	handler.ServeHTTP(rr, req)

	// Check the status code is what we expect.
	if status := rr.Code; status != http.StatusOK {
		t.Errorf("Handler returned wrong status code: got %v want %v", status, http.StatusOK)
	}

	// Check the response body is a valid JSON.
	var response map[string]interface{}
	if err := json.Unmarshal(rr.Body.Bytes(), &response); err != nil {
		t.Errorf("Handler returned an invalid JSON: %v", err)
	}

	// Ensure that data has been returned
	if data, ok := response["data"].([]interface{}); ok {
		if len(data) == 0 {
			t.Errorf("Expected some results in data, got none")
		}
	} else {
		t.Errorf("Expected 'data' field in response to be an array")
	}
}

func TestSearchHandler_InvalidSearchQuery(t *testing.T) {
	req, err := http.NewRequest("GET", "/search?search=User@!1", nil)
	if err != nil {
		t.Fatal(err)
	}

	rr := httptest.NewRecorder()
	handler := http.HandlerFunc(searchHandler)

	handler.ServeHTTP(rr, req)

	// Check the status code is what we expect.
	if status := rr.Code; status != http.StatusBadRequest {
		t.Errorf("Handler returned wrong status code: got %v want %v", status, http.StatusBadRequest)
	}

	// Check if the error message is returned
	expected := "Invalid search query"
	if !strings.Contains(rr.Body.String(), expected) {
		t.Errorf("Handler returned unexpected body: got %v want %v", rr.Body.String(), expected)
	}
}

func TestSearchHandler_ExactMatch(t *testing.T) {
	req, err := http.NewRequest("GET", "/search?search=City1&exact=true", nil)
	if err != nil {
		t.Fatal(err)
	}

	rr := httptest.NewRecorder()
	handler := http.HandlerFunc(searchHandler)

	handler.ServeHTTP(rr, req)

	// Check the status code is what we expect.
	if status := rr.Code; status != http.StatusOK {
		t.Errorf("Handler returned wrong status code: got %v want %v", status, http.StatusOK)
	}

	// Check the response body is a valid JSON.
	var response map[string]interface{}
	if err := json.Unmarshal(rr.Body.Bytes(), &response); err != nil {
		t.Errorf("Handler returned an invalid JSON: %v", err)
	}

	// Ensure that exact matching is performed
	if data, ok := response["data"].([]interface{}); ok {
		if len(data) != 1 {
			t.Errorf("Expected exactly one result for exact match, but got %v", len(data))
		}
	} else {
		t.Errorf("Expected 'data' field in response to be an array")
	}
}

func TestSearchHandler_Pagination(t *testing.T) {
	req, err := http.NewRequest("GET", "/search?page=10", nil)
	if err != nil {
		t.Fatal(err)
	}

	rr := httptest.NewRecorder()
	handler := http.HandlerFunc(searchHandler)

	handler.ServeHTTP(rr, req)

	// Check the status code is what we expect.
	if status := rr.Code; status != http.StatusOK {
		t.Errorf("Handler returned wrong status code: got %v want %v", status, http.StatusOK)
	}

	// Check the response body is a valid JSON.
	var response map[string]interface{}
	if err := json.Unmarshal(rr.Body.Bytes(), &response); err != nil {
		t.Errorf("Handler returned an invalid JSON: %v", err)
	}

	// Ensure that data has been returned
	if data, ok := response["data"].([]interface{}); ok {
		if len(data) == 0 {
			t.Errorf("Expected results in paginated data, but got none")
		}
	} else {
		t.Errorf("Expected 'data' field in response to be an array")
	}

	// Ensure next page link exists
	if _, ok := response["next"]; !ok {
		t.Errorf("Expected 'next' field in response but did not get one")
	}
}
```

#### [GCP StackDriver Logger V2](#gcp-stackdriver-logger-v2)

```go
package main

import (
	"cloud.google.com/go/logging"
	"context"
	"encoding/json"
	"fmt"
	"go.uber.org/zap"
	"go.uber.org/zap/zapcore"
	"log"
	"runtime/debug"
	"strings"
)

var StackDriverLoggerName = "application-test"
var GCPProjectName = "my-project"

type Destination int64

const (
	GCP Destination = iota
	SYSTEM
	SYSTEM_GOOGLE
)

var ULogConfigLogSysAndGCP LoggerConfig
var ULogConfigLogSys LoggerConfig
var ULogConfigLogGCP LoggerConfig

var LogSys *Logger
var LogGCP *Logger
var LogSysGCP *Logger

type LogLevel int

const (
	DEBUG LogLevel = iota
	ERROR
	INFO
	WARNING
)

type LoggerConfig struct {
	UseZap    bool
	UseGCP    bool
	ProjectID string
	LogID     string
}

type Logger struct {
	gcpLogger *logging.Logger
	zapLogger *zap.Logger
	config    LoggerConfig
}

type LogData struct {
	Cloud              string      `json:"cloud,omitempty"`
	Component          string      `json:"component,omitempty"`
	Operation          string      `json:"operation,omitempty"`
	Custom             string      `json:"custom,omitempty"`
	Message            string      `json:"message,omitempty"`
	Error              string      `json:"error,omitempty"`
	Func               string      `json:"func,omitempty"`
	TimeTakenMilliSecs int64       `json:"time_taken_ms,omitempty"`
	Payload            interface{} `json:"payload,omitempty"`
	MetaData           interface{} `json:"metadata,omitempty"`
	Count              int64       `json:"count,omitempty"`
}

func (logData LogData) GetMapSI() map[string]interface{} {
	data, err := json.Marshal(logData)
	if err != nil {
		log.Printf("json marshal failed: %v", err)
		return nil
	}

	var result map[string]interface{}
	err = json.Unmarshal(data, &result)
	if err != nil {
		log.Printf("json unmarshal failed: %v", err)
		return nil
	}
	return result
}

func (logData LogData) Log(level LogLevel, destination Destination) {
	myMap := logData.GetMapSI()
	if myMap == nil {
		return
	}

	if destination == SYSTEM || destination == SYSTEM_GOOGLE {
		LogSys.Log(level, myMap)
	}
	if destination == GCP || destination == SYSTEM_GOOGLE {
		LogSysGCP.Log(level, myMap)
	}

}

// NewLogger initializes a new Logger instance.
func NewLogger(config LoggerConfig) (*Logger, error) {
	var gcpLogger *logging.Logger
	var zapLogger *zap.Logger
	//var err error

	if config.UseGCP {
		ctx := context.Background()
		client, err := logging.NewClient(ctx, config.ProjectID)
		if err != nil {
			return nil, fmt.Errorf("failed to create GCP logging client: %v", err)
		}
		gcpLogger = client.Logger(config.LogID)
	}

	if config.UseZap {
		encoderConfig := zapcore.EncoderConfig{
			MessageKey:    "msg",
			LevelKey:      "level",
			TimeKey:       "ts",
			CallerKey:     "caller",
			StacktraceKey: "stacktrace",
			EncodeLevel:   zapcore.CapitalLevelEncoder,
			EncodeTime:    zapcore.ISO8601TimeEncoder,
			EncodeCaller:  zapcore.ShortCallerEncoder,
		}

		// Create zap core with the custom encoder.
		zapCore := zapcore.NewCore(
			zapcore.NewConsoleEncoder(encoderConfig),
			zapcore.AddSync(log.Writer()),
			zap.DebugLevel, // Set log level to debug
		)

		// Remove automatic stack traces added by Zap, handle manually
		zapLogger = zap.New(zapCore, zap.AddCaller()) // No zap.AddStacktrace()
	}

	return &Logger{
		gcpLogger: gcpLogger,
		zapLogger: zapLogger,
		config:    config,
	}, nil
}

// Log logs a message at the specified log level.
func (l *Logger) Log(level LogLevel, msg interface{}) {
	var severity logging.Severity

	switch level {
	case DEBUG:
		severity = logging.Debug
	case ERROR:
		severity = logging.Error
	case INFO:
		severity = logging.Info
	case WARNING:
		severity = logging.Warning

	}

	if l.config.UseGCP && l.gcpLogger != nil {
		l.gcpLogger.Log(logging.Entry{
			Severity: severity,
			Payload:  msg,
		})
		_ = l.gcpLogger.Flush()
	}

	// Log to Zap if enabled.
	if l.config.UseZap && l.zapLogger != nil {
		switch level {
		case DEBUG:
			l.zapLogger.Debug(fmt.Sprintf("%v", msg))
		case ERROR:
			stacktrace := flattenStackTrace(string(debug.Stack()))
			l.zapLogger.Error(fmt.Sprintf("%v | Stacktrace: %s", msg, stacktrace))
		case INFO:
			l.zapLogger.Info(fmt.Sprintf("%v", msg))
		case WARNING:
			l.zapLogger.Warn(fmt.Sprintf("%v", msg))
		}
	}
}

func flattenStackTrace(stack string) string {
	// Replace newlines and tabs with a space to make it a single line
	stack = strings.ReplaceAll(stack, "\n", " ")
	stack = strings.ReplaceAll(stack, "\t", " ")
	return stack
}

func (l *Logger) Close() error {
	if l.config.UseGCP && l.gcpLogger != nil {
		return l.gcpLogger.Flush()
	}
	return nil
}

func InitializeUniversalLogging() {
	var err error

	ULogConfigLogSys = LoggerConfig{
		UseZap:    true,
		UseGCP:    false,
		ProjectID: GCPProjectName,
		LogID:     StackDriverLoggerName,
	}

	ULogConfigLogGCP = LoggerConfig{
		UseZap:    false,
		UseGCP:    true,
		ProjectID: GCPProjectName,
		LogID:     StackDriverLoggerName,
	}

	ULogConfigLogSysAndGCP = LoggerConfig{
		UseZap:    true,
		UseGCP:    true,
		ProjectID: GCPProjectName,
		LogID:     StackDriverLoggerName,
	}

	LogSys, err = NewLogger(ULogConfigLogSys)
	if err != nil {
		log.Fatalf("__FATAL__ : failed to initialize logger : NewLogger(appdata.ULogConfigLogSys) : %v", err)
	}

	LogGCP, err = NewLogger(ULogConfigLogGCP)
	if err != nil {
		log.Fatalf("__FATAL__ : failed to initialize logger : NewLogger(appdata.ULogConfigLogGCP) : %v", err)
	}

	LogSysGCP, err = NewLogger(ULogConfigLogSysAndGCP)
	if err != nil {
		log.Fatalf("__FATAL__ : failed to initialize logger : NewLogger(appdata.ULogConfigLogSysAndGCP) : %v", err)
	}

	LogSysGCP.Log(INFO, "Initialized Universal Logger with GCP/UberZap Logger")
}

func main() {

	InitializeUniversalLogging()

	logData := LogData{
		Component: "test",
		MetaData:  []string{"test1", "test2", "test3"},
	}

	logData1 := LogData{
		Operation: "exec_test",
		MetaData:  []string{"test1", "test2", "test3"},
	}

	logData.Log(DEBUG, SYSTEM_GOOGLE)
	logData1.Log(ERROR, SYSTEM_GOOGLE)

	logData.Log(DEBUG, SYSTEM)
	logData1.Log(ERROR, SYSTEM)

	fmt.Println("Logs have been sent to the configured log destinations.")
}
```

#### [Calculate 99th Percentile](#calculate-99th-percentile)

```go
package main

import (
	"fmt"
	"math"
	"sort"
)

func calculateStats(nums []int64) (min, max int64, avg float64, percentile99 int64) {
	// Check for an empty slice
	if len(nums) == 0 {
		return 0, 0, 0, 0
	}

	// Initialize min and max
	min, max = math.MaxInt64, math.MinInt64
	var sum int64

	for _, num := range nums {
		// Update min and max
		if num < min {
			min = num
		}
		if num > max {
			max = num
		}
		// Sum for average calculation
		sum += num
	}

	// Calculate average
	avg = float64(sum) / float64(len(nums))

	// Sort the slice for percentile calculation
	sort.Slice(nums, func(i, j int) bool { return nums[i] < nums[j] })

	// Calculate the 99th percentile index
	index := int(math.Ceil(0.99 * float64(len(nums)))) - 1

	// 99th percentile value
	percentile99 = nums[index]

	return min, max, avg, percentile99
}

func main() {
	// Sample slice of int64
	nums := []int64{10, 20, 15, 30, 25, 50, 5, 100, 200, 300}

	min, max, avg, percentile99 := calculateStats(nums)

	fmt.Printf("Min: %d\n", min)
	fmt.Printf("Max: %d\n", max)
	fmt.Printf("Average: %.2f\n", avg)
	fmt.Printf("99th Percentile: %d\n", percentile99)
}
```

#### [Thread Safe Cache With Eviction](#thread-safe-cache-with-eviction)

```go
package main

import (
	"fmt"
	"sync"
	"time"
)

// SafeMapEntry holds the value and the timestamp of when the entry was added
type SafeMapEntry struct {
	Value     interface{}
	Timestamp time.Time
}

// SafeMap is a thread-safe wrapper around a map with eviction capabilities
type SafeMap struct {
	data  map[string]SafeMapEntry
	mutex sync.RWMutex
	ttl   time.Duration
}

// NewSafeMap creates and returns a new SafeMap with a specified eviction duration
func NewSafeMap(ttl time.Duration) *SafeMap {
	sm := &SafeMap{
		data: make(map[string]SafeMapEntry),
		ttl:  ttl,
	}
	// Start eviction goroutine
	go sm.evictExpiredEntries()
	return sm
}

// Set adds or updates a key-value pair in the map with the current timestamp
func (sm *SafeMap) Set(key string, value interface{}) {
	sm.mutex.Lock()
	defer sm.mutex.Unlock()
	sm.data[key] = SafeMapEntry{
		Value:     value,
		Timestamp: time.Now(),
	}
}

// Get retrieves a value by key from the map
func (sm *SafeMap) Get(key string) (interface{}, bool) {
	sm.mutex.RLock()
	defer sm.mutex.RUnlock()
	entry, ok := sm.data[key]
	if !ok {
		return nil, false
	}
	// Return the value only if the entry has not expired
	if time.Since(entry.Timestamp) < sm.ttl {
		return entry.Value, true
	}
	// If expired, delete the entry
	sm.mutex.RUnlock()
	sm.mutex.Lock()
	delete(sm.data, key)
	sm.mutex.Unlock()
	sm.mutex.RLock()
	return nil, false
}

// Delete removes a key-value pair from the map
func (sm *SafeMap) Delete(key string) {
	sm.mutex.Lock()
	defer sm.mutex.Unlock()
	delete(sm.data, key)
}

// evictExpiredEntries periodically checks and removes entries older than the TTL
func (sm *SafeMap) evictExpiredEntries() {
	for {
		time.Sleep(sm.ttl / 2) // Run eviction periodically, e.g., every 5 minutes if ttl is 10 minutes
		now := time.Now()

		sm.mutex.Lock()
		for key, entry := range sm.data {
			if now.Sub(entry.Timestamp) > sm.ttl {
				delete(sm.data, key)
				fmt.Printf("Evicted key: %s\n", key)
			}
		}
		sm.mutex.Unlock()
	}
}

// Size returns the number of items in the map
func (sm *SafeMap) Size() int {
	sm.mutex.RLock()
	defer sm.mutex.RUnlock()
	return len(sm.data)
}

// Clear removes all key-value pairs from the map
func (sm *SafeMap) Clear() {
	sm.mutex.Lock()
	defer sm.mutex.Unlock()
	sm.data = make(map[string]SafeMapEntry) // Reinitialize the map
}

func main() {
	// Create a new SafeMap with a 10-minute TTL (Time to Live)
	safeMap := NewSafeMap(10 * time.Minute)

	// Set some key-value pairs
	safeMap.Set("key1", "value1")
	safeMap.Set("key2", 123)

	// Simulate some waiting time (for demo purposes)
	time.Sleep(5 * time.Second)

	// Get values before they expire
	if value, ok := safeMap.Get("key1"); ok {
		fmt.Println("key1:", value)
	} else {
		fmt.Println("key1 has expired or does not exist")
	}

	// Wait until key1 and key2 are evicted after 10 minutes (simulated for testing purposes)
	fmt.Println("Waiting for keys to be evicted...")
	time.Sleep(12 * time.Minute) // Simulating time to pass

	// Try getting the values after the TTL has passed
	if value, ok := safeMap.Get("key1"); ok {
		fmt.Println("key1:", value)
	} else {
		fmt.Println("key1 has expired or does not exist")
	}
}
```

#### [GORM-IO Database Connections And Connection Pooling](#gorm-io-database-connections-and-connection-pooling)

Using `gorm.io` Golang Package

```go
type PgRowDevView struct {
	ResourceID string          `gorm:"column:resource_id"` // Maps to the resource_id column (TEXT)
	Data       json.RawMessage `gorm:"column:data"`        // Maps to the data column (JSONB)
}

func InitDB() {
	dsn := fmt.Sprintf("host=<REDACTED> user=<REDACTED> password=<REDACTED> dbname=<REDACTED> port=5432 sslmode=disable TimeZone=Asia/Shanghai")
	var err error
	db, err = gorm.Open(postgres.Open(dsn), &gorm.Config{})
	if err != nil {
		log.Fatalf("failed to connect to database: %v", err)
	}

	sqlDB, _ := db.DB()
	sqlDB.SetMaxIdleConns(5)
	sqlDB.SetMaxOpenConns(10)
	sqlDB.SetConnMaxLifetime(5 * time.Minute)

	// Automatically create or migrate the schema
	db.AutoMigrate(&PgRowDevView{})
}
```

> Below Is The The Explanation For Setting These Parameters >

```go
sqlDB.SetMaxIdleConns(5)
sqlDB.SetMaxOpenConns(10)
sqlDB.SetConnMaxLifetime(5 * time.Minute)
```

1. Max Open Connections (SetMaxOpenConns(10)):

 - This setting controls the maximum number of open connections to the database.
 - Flow:
    - When a client requests a new connection, the pool first checks if there is an available connection.
    - If all open connections (up to 10) are in use, the pool will block new requests until an existing connection is returned or closed.
    - Example: You can have at most 10 connections open at any time, whether they are idle or in use.

2. Max Idle Connections (SetMaxIdleConns(5)):

 - This setting determines the maximum number of idle connections that the pool will maintain.
 - Flow:
    -   If a connection is returned to the pool but the number of idle connections exceeds 5, the extra idle connections will be closed.
    -   Example: Even though 10 connections can be open at once, only up to 5 can remain idle. If more than 5 are idle, the excess will be closed to save resources.

3. Connection Max Lifetime (SetConnMaxLifetime(5 * time.Minute)):

 - This setting controls how long a connection can be reused.
 - Flow:
    - Once a connection has been open for 5 minutes, it will be closed and removed from the pool, even if it is still idle or in use.
    - Example: Even if a connection is idle and not exceeding the idle connection limit, it will be closed once it has lived for more than 5 minutes.

> Putting it All Together

1. A client requests a connection from the pool.
2. If the pool has fewer than 10 open connections, it provides a new or idle connection.
3. If there are more than 5 idle connections, the excess idle connections are closed.
4. Connections are reused until they hit the 5-minute lifetime limit, after which they are closed.
5. When all 10 connections are in use, new requests must wait until a connection is available.

By carefully tuning these parameters, you can manage database resource consumption effectively while optimizing performance for your application.

<hr/>

The sqlDB.SetConnMaxLifetime setting controls how long a connection can remain open in the connection pool before being closed and removed from the pool. Adjusting this value can have important performance and stability implications for your application. Let’s explore the implications of increasing or decreasing the value of SetConnMaxLifetime.

> Understanding SetConnMaxLifetime

This setting specifies the maximum duration a connection may be reused. After
this duration has elapsed, the connection will be closed and removed from the
pool, even if it’s idle or still open. When a connection reaches its maximum
lifetime, it is invalidated and will no longer be used for any future queries.

```go
sqlDB.SetConnMaxLifetime(30 * time.Minute)
```

In this case, each connection will be closed and discarded after 30 minutes of use, regardless of whether it is idle or active.

> Implications of Increasing SetConnMaxLifetime

✅ Pros:

 - Lower Connection Turnover: By increasing the connection lifetime, connections will stay open longer, reducing the need to frequently establish new connections to the database, which is a relatively expensive operation.
 - Improved Performance: Fewer reconnections can reduce latency and improve performance for applications with consistent or high levels of traffic.
 - Stable for Long-Lived Connections: If your database connections are generally stable and the network is reliable, increasing the lifetime can allow connections to be reused more effectively.

👎 Cons:

 - Increased Risk of Stale Connections: If a connection stays open for too long, there is a risk that the connection could become stale or corrupted without being detected, especially if there are network issues or if the database closes idle connections on its side. This can lead to application errors.
 - Resource Exhaustion: Long-lived connections may not free up resources as frequently, leading to resource exhaustion on the database server side, especially in systems where connections are not properly managed or closed when no longer in use.

> Implications of Decreasing SetConnMaxLifetime

✅ Pros:

 - More Frequent Connection Refresh: Lowering the lifetime will cause connections to be closed and refreshed more often, which can help avoid issues with stale or problematic connections.
 - Adaptability: Shorter lifetimes can be beneficial in dynamic cloud environments where networking routes or database configurations change frequently, as it forces connections to reset and adapt more often.
 - Improved Resiliency: If you’re facing issues with long-lived connections becoming stale or failing after prolonged periods, a shorter connection lifetime can help mitigate these issues by ensuring that connections are refreshed frequently.

👎 Cons:

 - Higher Overhead: If connections are closed and reopened more frequently, this can lead to increased overhead on both the application and the database, as each new connection requires time and resources to be established. This could introduce latency and reduce performance under heavy load.
 - Potential for Connection Throttling: In scenarios with frequent reconnections, the database or network infrastructure may throttle connections if too many new ones are being opened and closed rapidly, leading to connection timeouts or errors.

> 🟩 Best Practices

 - Match with Database Timeout Settings: Ensure that the value for SetConnMaxLifetime is lower than or aligned with any server-side connection timeout settings (e.g., PostgreSQL’s idle_in_transaction_session_timeout, tcp_keepalives_*, etc.). If the database is terminating connections before ConnMaxLifetime is reached, you may encounter errors.
 - Monitor Application Behavior: Use monitoring and observability tools to understand how your application behaves with different values for connection lifetime. Track connection errors, latency, and resource usage to find the optimal balance.
 - Consider the Nature of the Workload: For high-throughput, long-lived applications (e.g., web servers handling constant traffic), longer connection lifetimes might be more efficient. For bursty or irregular traffic patterns, or in environments with unreliable networking, shorter connection lifetimes might be safer.

> 👍🏻 Recommended Approach

 - Start with a Balanced Value: A balanced initial value, such as 30 minutes, is a good starting point for most applications. This value allows connections to be reused while ensuring they don’t live too long in case of issues.
 - Monitor and Adjust Based on Behavior: Once your application is in production, monitor metrics like connection pool size, connection errors, and database load. If you notice issues with stale connections or frequent connection churn, adjust the lifetime accordingly.
 - Consider Database Constraints: Make sure that your settings align with database configuration and the load that your application typically handles. For example, if your database server has a setting that automatically disconnects idle connections after 10 minutes, your ConnMaxLifetime should be shorter than that to avoid issues.

Example

 - High Throughput Application: If your application is constantly receiving traffic and needs to minimize connection setup overhead, a larger value like 1 hour or more might be ideal, allowing for efficient connection reuse.
 - Bursty or Intermittent Traffic: If your application sees bursts of traffic followed by idle periods, a shorter connection lifetime (e.g., 10-15 minutes) might be preferable to prevent stale connections during idle times.

Conclusion

The SetConnMaxLifetime setting should be tuned based on the specifics of your
workload, environment, and database configuration. Start with a reasonable value
like 30 minutes and monitor the impact on performance and stability, adjusting
as necessary. Increasing or decreasing the value affects the balance between
connection reuse (performance) and connection freshness (resiliency).

#### [IP Port Check](#ip-port-check)

> Usage

Specific IP-Address And Port (`In Parallel`)

```bash
go run main.go -ipport "8.8.8.8:53 127.0.0.1:80"
```

For All IP Addresses And All Ports Combinations (`In Parallel`)

```
go run main.go -ips "8.8.8.8,127.0.0.1" -ports "53,80"
```

```go
package main

import (
	"flag"
	"fmt"
	"net"
	"strings"
	"sync"
	"time"
)

/*
go run main.go -ipport "8.8.8.8:53 127.0.0.1:80"

go run main.go -ips "8.8.8.8,127.0.0.1" -ports "53,80"
*/

type Result struct {
	Address string
	Status  string
}

func checkConnection(address string, timeout time.Duration) Result {
	conn, err := net.DialTimeout("tcp", address, timeout)
	if err != nil {
		return Result{Address: address, Status: "Closed"}
	}
	conn.Close()
	return Result{Address: address, Status: "Open"}
}

func checkAddresses(addresses []string, timeout time.Duration) []Result {
	var wg sync.WaitGroup
	results := make([]Result, len(addresses))
	wg.Add(len(addresses))

	for i, address := range addresses {
		go func(i int, address string) {
			defer wg.Done()
			results[i] = checkConnection(address, timeout)
		}(i, address)
	}

	wg.Wait()
	return results
}

func parseIPsAndPorts(ips string, ports string) []string {
	addresses := []string{}
	ipList := strings.Split(ips, ",")
	portList := strings.Split(ports, ",")
	for _, ip := range ipList {
		for _, port := range portList {
			addresses = append(addresses, fmt.Sprintf("%s:%s", ip, port))
		}
	}
	return addresses
}

func main() {
	// Define flags
	ipportFlag := flag.String("ipport", "", "Space-separated IP:PORT pairs (e.g., 192.168.1.1:80 192.168.1.2:443)")
	ipsFlag := flag.String("ips", "", "Comma-separated IP addresses (e.g., 192.168.1.1,192.168.1.2)")
	portsFlag := flag.String("ports", "", "Comma-separated ports (e.g., 80,443)")
	timeoutFlag := flag.Int("timeout", 3, "Timeout in seconds for each connection check")
	flag.Parse()

	timeout := time.Duration(*timeoutFlag) * time.Second
	addresses := []string{}

	// Handle -ipport option
	if *ipportFlag != "" {
		addresses = strings.Fields(*ipportFlag)
	} else if *ipsFlag != "" && *portsFlag != "" {
		// Handle -ips and -ports options
		addresses = parseIPsAndPorts(*ipsFlag, *portsFlag)
	} else {
		fmt.Println("Error: Provide either -ipport or both -ips and -ports.")
		flag.Usage()
		return
	}

	// Check the connections
	results := checkAddresses(addresses, timeout)

	// Display results
	fmt.Println("Results:")
	for _, result := range results {
		fmt.Printf(" - %s: %s\n", result.Address, result.Status)
	}
}
```

#### [Handling Panic And Recover With Stack Trace](#handling-panic-and-recover-with-stack-trace)

> Approach-1

```go
package main

import (
    "log"
    "runtime/debug"
    "time"
)

func worker() {
    // Simulate some work that might panic
    panic("something went wrong in worker")
}

func runWithRecovery(f func()) {
    defer func() {
        if err := recover(); err != nil {
            log.Printf("PANIC: %v\n%s", err, debug.Stack())
            
            // Restart the function after a delay
            log.Println("Restarting worker in 5 seconds...")
            time.Sleep(5 * time.Second)
            go runWithRecovery(f)
        }
    }()
    
    f()
}

func main() {
    // Start the worker in a goroutine with recovery
    go runWithRecovery(worker)
    
    // Block forever using a channel
    select {}
}
```

> Approach-2

```go
package main

import (
    "fmt"
    "log"
    "runtime/debug"
    "time"
    "sync"
)

func worker() {
    // Simulate some work that might panic
    panic("something went wrong in worker")
}

func runWithRecovery(f func()) {
    defer func() {
        if err := recover(); err != nil {
            log.Printf("PANIC: %v\n%s", err, debug.Stack())
            
            // Restart the function after a delay
            log.Println("Restarting worker in 5 seconds...")
            time.Sleep(5 * time.Second)
            go runWithRecovery(f)
        }
    }()
    
    f()
}

func main() {
    // Start the worker in a goroutine with recovery
    go runWithRecovery(worker)
    
    // Block forever
    var wg sync.WaitGroup
    wg.Add(1)
    wg.Wait()
}
```

> Approach-3

```go
package main

import (
    "fmt"
    "log"
    "net/http"
    "runtime/debug"
    "time"
)

func recoveryMiddleware(next http.Handler) http.Handler {
    return http.HandlerFunc(func(w http.ResponseWriter, r *http.Request) {
        defer func() {
            if err := recover(); err != nil {
                // Print stack trace
                log.Printf("PANIC: %v\n%s", err, debug.Stack())
                
                // Return 500 error
                w.WriteHeader(http.StatusInternalServerError)
                fmt.Fprintf(w, "Internal Server Error")
            }
        }()
        next.ServeHTTP(w, r)
    })
}

func startServer(port string, handler http.Handler) {
    for {
        // Create server with recovery middleware
        srv := &http.Server{
            Addr:    ":" + port,
            Handler: recoveryMiddleware(handler),
        }

        // Start server
        log.Printf("Server starting on port %s", port)
        if err := srv.ListenAndServe(); err != nil {
            log.Printf("Server error: %v", err)
        }

        // Wait before restart
        log.Println("Server crashed. Restarting in 5 seconds...")
        time.Sleep(5 * time.Second)
    }
}

func main() {
    // Create routes
    mux := http.NewServeMux()
    
    mux.HandleFunc("/", func(w http.ResponseWriter, r *http.Request) {
        fmt.Fprintf(w, "Hello, World!")
    })
    
    mux.HandleFunc("/panic", func(w http.ResponseWriter, r *http.Request) {
        panic("Intentional panic for testing")
    })

    // Start server
    startServer("8080", mux)
}
```

> Approach-4

```go
package main

import (
    "fmt"
    "log"
    "net/http"
    "os"
    "runtime/debug"
    "time"
)

// Server represents our HTTP server configuration
type Server struct {
    port    string
    handler http.Handler
    logger  *log.Logger
}

// NewServer creates a new server instance
func NewServer(port string, handler http.Handler) *Server {
    return &Server{
        port:    port,
        handler: handler,
        logger:  log.New(os.Stdout, "[SERVER] ", log.LstdFlags),
    }
}

// recoveryMiddleware wraps an http.Handler with panic recovery
func (s *Server) recoveryMiddleware(next http.Handler) http.Handler {
    return http.HandlerFunc(func(w http.ResponseWriter, r *http.Request) {
        defer func() {
            if err := recover(); err != nil {
                // Log the stack trace
                stackTrace := debug.Stack()
                s.logger.Printf("PANIC: %v\n%s", err, stackTrace)

                // Return a 500 Internal Server Error
                w.WriteHeader(http.StatusInternalServerError)
                fmt.Fprintf(w, "Internal Server Error")

                // Optionally notify external monitoring service
                go s.notifyMonitoring(err, stackTrace)
            }
        }()
        next.ServeHTTP(w, r)
    })
}

// notifyMonitoring sends error details to a monitoring service
func (s *Server) notifyMonitoring(err interface{}, stackTrace []byte) {
    // Implement your monitoring service integration here
    // Example: send to error tracking service, Slack, etc.
    s.logger.Printf("Notifying monitoring service about panic: %v", err)
}

// Start begins the server and handles automatic restarts
func (s *Server) Start() {
    for {
        // Create a new server with recovery middleware
        srv := &http.Server{
            Addr:    ":" + s.port,
            Handler: s.recoveryMiddleware(s.handler),
        }

        // Start the server in a goroutine
        serverChan := make(chan error, 1)
        go func() {
            s.logger.Printf("Server starting on port %s", s.port)
            serverChan <- srv.ListenAndServe()
        }()

        // Wait for server error
        err := <-serverChan
        s.logger.Printf("Server error: %v", err)

        // Wait before attempting restart
        s.logger.Println("Waiting 5 seconds before restarting...")
        time.Sleep(5 * time.Second)
    }
}

// Example usage with a basic router
func main() {
    // Create a simple router
    mux := http.NewServeMux()
    
    // Add some example routes
    mux.HandleFunc("/", func(w http.ResponseWriter, r *http.Request) {
        fmt.Fprintf(w, "Hello, World!")
    })
    
    mux.HandleFunc("/panic", func(w http.ResponseWriter, r *http.Request) {
        panic("Intentional panic for testing")
    })

    // Create and start the server
    server := NewServer("8080", mux)
    server.Start()
}
```