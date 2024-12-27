## Go Ultimate: The ultimate go cheatsheet you’ll ever need

#### Arrays and Slices Operations

```
| Data Structure | Syntax               | Time Complexity | Space Complexity | Description                                        |
|----------------|----------------------|-----------------|------------------|----------------------------------------------------|
| Array          | `var arr [n]T`       | O(1)            | O(n)             | Declares an array of type `T` with fixed size `n`. |
|                | `arr[index]`         | O(1)            | O(1)             | Accesses the element at the specified index.       |
|                | `arr[index] = value` | O(1)            | O(1)             | Updates the element at the specified index.        |
```

#### Slices

```
| Data Structure | Syntax                                  | Time Complexity | Space Complexity | Description                                           |
|----------------|-----------------------------------------|-----------------|------------------|-------------------------------------------------------|
| Slice          | `slice := arr[start:end]`               | O(1)            | O(1)             | Creates a slice from an array or another slice.       |
|                | `slice := make([]T, length, capacity)`  | O(1)            | O(n)             | Creates a slice with specified length and capacity.   |
|                | `append(slice, value)`                  | Amortized O(1)  | O(n)             | Appends an element to the end of the slice.           |
|                | `len(slice)`                            | O(1)            | O(1)             | Returns the number of elements in the slice.          |
|                | `cap(slice)`                            | O(1)            | O(1)             | Returns the capacity of the slice.                    |
|                | `copy(dst, src)`                        | O(n)            | O(1)             | Copies elements from `src` to `dst`.                  |
```

#### Maps and Structs Operations

```
| Data Structure | Syntax                    | Time Complexity| Space Complexity| Description                                                     |
|----------------|---------------------------|----------------|-----------------|-----------------------------------------------------------------|
| Map            | `m := make(map[K]V)`      | O(1)           | O(n)            | Creates a new empty map with key type `K` and value type `V`.   |
|                | `m[key] = value`          | Average O(1)   | O(1)            | Inserts or updates a key-value pair in the map.                 |
|                | `value = m[key]`          | Average O(1)   | O(1)            | Retrieves the value associated with the key.                    |
|                | `delete(m, key)`          | Average O(1)   | O(1)            | Removes a key-value pair from the map.                          |
|                | `value, exists := m[key]` | Average O(1)   | O(1)            | Checks if a key exists in the map.                              |
|                | `len(m)`                  | O(1)           | O(1)            | Returns the number of key-value pairs in the map.               |
```

#### Structs

```
| Data Structure | Syntax                               | Time Complexity | Space Complexity | Description                                     |
|----------------|--------------------------------------|-----------------|------------------|-------------------------------------------------|
| Struct         | `type Person struct { Name string }` | O(1)            | O(1)             | Defines a new struct type `Person`.             |
|                | `p := Person{Name: "Alice"}`         | O(1)            | O(1)             | Creates a new instance of `Person`.             |
|                | `p.Name`                             | O(1)            | O(1)             | Accesses or modifies a field in the struct.     |
|                | Embedded Structs                     | O(1)            | O(1)             | Structs can contain other structs.              |
|                | Tags                                 | O(1)            | O(1)             | Struct fields can have tags for metadata.       |
```

#### String and Iterator Manipulations

```
| Function                 | Syntax                               |Time Complexity | Space Complexity| Description                                                     |
|--------------------------|--------------------------------------|----------------|-----------------|-----------------------------------------------------------------|
| Length                   | `len(s)`                             | O(1)           | O(1)            | Returns the length of the string.                               |
| Concatenation            | `s = s1 + s2`                        | O(n)           | O(n)            | Concatenates two strings.                                       |
| Substring                | `substr = s[start:end]`              | O(1)           | O(1)            | Extracts a substring from the string.                           |
| Contains                 | `strings.Contains(s, substr)`        | O(n)           | O(1)            | Checks if `substr` is within `s`.                               |
| Split                    | `strings.Split(s, sep)`              | O(n)           | O(n)            | Splits a string into substrings separated by `sep`.             |
| Replace                  | `strings.Replace(s, old, new, n)`    | O(n)           | O(n)            | Replaces occurrences of `old` with `new`.                       |
| ToUpper                  | `strings.ToUpper(s)`                 | O(n)           | O(n)            | Converts the string to uppercase.                               |
| TrimSpace                | `strings.TrimSpace(s)`               | O(n)           | O(n)            | Trims leading and trailing whitespace.                          |
| Index                    | `strings.Index(s, substr)`           | O(n)           | O(1)            | Returns the index of the first occurrence of`substr`.           |
| Join                     | `strings.Join(slice, sep)`           | O(n)           | O(n)            | Joins elements of a slice into a single string.                 |
```

#### Iteration

```
| Loop Type      | Syntax                                   | Time Complexity | Space Complexity | Description                                     |
|----------------|------------------------------------------|-----------------|------------------|-------------------------------------------------|
| For Loop       | `for i := 0; i < n; i++ {}`              | O(n)            | O(1)             | Standard loop from `0` to `n-1`.                |
| For Range      | `for index, value := range collection {}`| O(n)            | O(1)             | Iterates over elements in a collection.         |
| Infinite Loop  | `for { /* code */ }`                     | Depends         | O(1)             | Creates an infinite loop until break condition. |
```

#### Goroutines

```
| Operation   | Syntax                 | Time Complexity | Space Complexity | Description                                   |
|-------------|------------------------|-----------------|------------------|-----------------------------------------------|
| Start       | `go functionName()`    | O(1)            | O(1)             | Starts a new goroutine to run `functionName`. |
```

#### Channels

```
| Operation     | Syntax                          | Time Complexity | Space Complexity | Description                                     |
|---------------|---------------------------------|-----------------|------------------|-------------------------------------------------|
| Create        | `ch := make(chan T)`            | O(1)            | O(1)             | Creates an unbuffered channel of type `T`.      |
| Buffered      | `ch := make(chan T, capacity)`  | O(1)            | O(n)             | Creates a buffered channel with capacity.       |
| Send          | `ch <- value`                   | O(1)            | O(1)             | Sends a value to the channel.                   |
| Receive       | `value := <-ch`                 | O(1)            | O(1)             | Receives a value from the channel.              |
| Close         | `close(ch)`                     | O(1)            | O(1)             | Closes the channel.                             |
| Select        | `select { case ... }`           | O(1) per case   | O(1)             | Waits on multiple channel operations.           |
| Default Case  | `default:`                      | O(1)            | O(1)             | Executes when no other case is ready.           |
```

#### Synchronization Primitives

```
| Primitive     | Syntax                             | Time Complexity | Space Complexity | Description                                     |
|---------------|------------------------------------|-----------------|------------------|-------------------------------------------------|
| WaitGroup     | `var wg sync.WaitGroup`            | O(1)            | O(1)             | Synchronizes multiple goroutines.               |
|               | `wg.Add(delta)`                    | O(1)            | O(1)             | Adds delta to the WaitGroup counter.            |
|               | `wg.Done()`                        | O(1)            | O(1)             | Decrements the WaitGroup counter by one.        |
|               | `wg.Wait()`                        | O(1)            | O(1)             | Blocks until the WaitGroup counter is zero.     |
| Mutex         | `var mu sync.Mutex`                | O(1)            | O(1)             | Ensures mutual exclusion for critical sections. |
|               | `mu.Lock()`                        | O(1)            | O(1)             | Locks the mutex.                                |
|               | `mu.Unlock()`                      | O(1)            | O(1)             | Unlocks the mutex.                              |
| RWMutex       | `var rwmu sync.RWMutex`            | O(1)            | O(1)             | Allows multiple readers, single writer.         |
|               | `rwmu.RLock()`                     | O(1)            | O(1)             | Locks the mutex for reading.                    |
|               | `rwmu.RUnlock()`                   | O(1)            | O(1)             | Unlocks the read mutex.                         |
|               | `rwmu.Lock()`                      | O(1)            | O(1)             | Locks the mutex for writing.                    |
|               | `rwmu.Unlock()`                    | O(1)            | O(1)             | Unlocks the write mutex.                        |
| Once          | `var once sync.Once`               | O(1)            | O(1)             | Ensures a function is only called once.         |
|               | `once.Do(func())`                  | O(1)            | O(1)             | Calls the function if not already done.         |
| Cond          | `var cond *sync.Cond`              | O(1)            | O(1)             | Implements condition variables.                 |
|               | `cond.Wait()`                      | O(1)            | O(1)             | Waits for a signal.                             |
|               | `cond.Signal()`                    | O(1)            | O(1)             | Wakes one goroutine waiting on cond.            |
|               | `cond.Broadcast()`                 | O(1)            | O(1)             | Wakes all goroutines waiting on cond.           |
```

#### File I/O and System Operations

```
| Operation   | Syntax                             | Time Complexity | Space Complexity | Description                                      |
|-------------|------------------------------------|-----------------|------------------|--------------------------------------------------|
| Open File   | `file, err := os.Open(filename)`   | O(1)*           | O(1)             | Opens a file for reading.                        |
| Create File | `file, err := os.Create(filename)` | O(1)*           | O(1)             | Creates or truncates a file for writing.         |
| Read        | `n, err := file.Read(buf)`         | O(n)*           | O(1)             | Reads data into buffer `buf`.                    |
| Write       | `n, err := file.Write(data)`       | O(n)*           | O(1)             | Writes data from `data` to the file.             |
| Close       | `err := file.Close()`              | O(1)*           | O(1)             | Closes the file.                                 |
| Stat        | `info, err := os.Stat(filename)`   | O(1)*           | O(1)             | Gets file information.                           |
| Remove      | `err := os.Remove(filename)`       | O(1)*           | O(1)             | Deletes a file.                                  |
```

#### Error Handling and Debugging

```
| Operation   | Syntax                             | Time Complexity | Space Complexity | Description                                        |
|-------------|------------------------------------|-----------------|------------------|----------------------------------------------------|
| Create      | `err := errors.New("message")`     | O(1)            | O(1)             | Creates a new error with a message.                |
| Return      | `return value, err`                | O(1)            | O(1)             | Returns an error from a function.                  |
| Check       | `if err != nil { /* handle */ }`   | O(1)            | O(1)             | Checks if an error occurred.                       |
| Wrap Error  | `fmt.Errorf("... %w", err)`        | O(1)            | O(1)             | Wraps an existing error with additional context.   |
| Unwrap      | `errors.Unwrap(err)`               | O(1)            | O(1)             | Retrieves the next error in the chain.             |
| Is          | `errors.Is(err, targetErr)`        | O(n)            | O(1)             | Checks if an error matches a target error.         |
| As          | `errors.As(err, &targetType)`      | O(n)            | O(1)             | Checks if an error can be cast to a specific type. |
```

#### Debugging

```
| Tool         | Syntax                            | Description                                       |
|--------------|-----------------------------------|---------------------------------------------------|
| `fmt.Printf` | `fmt.Printf("Value: %v", value)`  | Formats and prints variables for debugging.       |
| `log.Fatal`  | `log.Fatal(err)`                  | Logs an error message and exits the program.      |
| `panic`      | `panic("message")`                | Stops execution and prints a stack trace.         |
| `recover`    | `recover()`                       | Recovers from a panic within a deferred function. |
```

#### Reflection

```
| Operation   | Syntax                             | Time Complexity | Space Complexity | Description                                      |
|-------------|------------------------------------|-----------------|------------------|--------------------------------------------------|
| Get Type    | `t := reflect.TypeOf(x)`           | O(1)            | O(1)             | Retrieves the type of `x`.                       |
| Get Value   | `v := reflect.ValueOf(x)`          | O(1)            | O(1)             | Retrieves the value of `x`.                      |
| Set Value   | `v.Set(newValue)`                  | O(1)            | O(1)             | Sets a new value; `v` must be settable.          |
| Kind        | `k := t.Kind()`                    | O(1)            | O(1)             | Gets the kind of type (`struct`, `int`, etc.).   |
| NumField    | `n := t.NumField()`                | O(1)            | O(1)             | Gets the number of fields in a struct.           |
| Field       | `f := v.Field(i)`                  | O(1)            | O(1)             | Accesses a field by index.                       |
```

#### sync Package

```
| Primitive     | Syntax                                 |Time Complexity | Space Complexity| Description                                                     |
|---------------|----------------------------------------|----------------|-----------------|-----------------------------------------------------------------|
| sync.Map      | `var m sync.Map`                       | O(1)           | O(n)            | A map safe for concurrent use.                                  |
|               | `m.Store(key, value)`                  | O(1)           | O(1)            | Stores a key-value pair.                                        |
|               | `value, ok := m.Load(key)`             | O(1)           | O(1)            | Loads the value for a key.                                      |
|               | `m.Delete(key)`                        | O(1)           | O(1)            | Deletes a key-value pair.                                       |
|               | `m.Range(func(k, v interface{}) bool)` | O(n)           | O(1)            | Iterates over all key-value pairs.                              |
| sync.Pool     | `var p = sync.Pool{New: func() int{}} `| O(1)           | O(n)            | Pool of temporary objects.                                      |
|               | `p.Get()`                              | O(1)           | O(1)            | Retrieves an object from the pool.                              |
|               | `p.Put(x)`                             | O(1)           | O(1)            | Returns an object to the pool.                                  |
```

#### Context Package

```
| Operation     | Syntax                                                    | Description                                                  |
|---------------|-----------------------------------------------------------|--------------------------------------------------------------|
| Background    | `ctx := context.Background()`                             | Returns an empty Context.                                    |
| WithCancel    | `ctx, cancel := context.WithCancel(parentCtx)`            | Creates a cancellable context.                               |
| WithTimeout   | `ctx, cancel := context.WithTimeout(parentCtx, duration)` | Sets a timeout.                                              |
| WithValue     | `ctx := context.WithValue(parentCtx, key, value)`         | Adds a value to the context.                                 |
| Done          | `<-ctx.Done()`                                            | Waits for the context to be cancelled or timed out.          |
| Err           | `err := ctx.Err()`                                        | Returns the error explaining why the context was cancelled.  |
```

#### JSON Encoding and Decoding

```
| Operation   | Syntax                             | Time Complexity | Space Complexity | Description                                      |
|-------------|------------------------------------|-----------------|------------------|--------------------------------------------------|
| Marshal     | `data, err := json.Marshal(v)`     | O(n)            | O(n)             | Converts Go value `v` to JSON.                   |
| Unmarshal   | `err := json.Unmarshal(data, &v)`  | O(n)            | O(n)             | Parses JSON data into Go value `v`.              |
| Decoder     | `dec := json.NewDecoder(r)`        | O(1)            | O(1)             | Creates a JSON decoder from an `io.Reader`.      |
| Encoder     | `enc := json.NewEncoder(w)`        | O(1)            | O(1)             | Creates a JSON encoder to an `io.Writer`.        |
```