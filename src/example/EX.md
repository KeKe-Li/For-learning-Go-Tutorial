### For-learning-Go-Tutorial
Go语言各种值类型，包括字符串、整数、浮点数、布尔值等。下面是一些基本示例。

```go

package main
import "fmt"
func main() {
    fmt.Println("go" + "lang")

    fmt.Println("1+1 =", 1+1)
    fmt.Println("7.0/3.0 =", 7.0/3.0)
    fmt.Println(true && false)
    fmt.Println(true || false)
    fmt.Println(!true)
}
```

```go
$ go run values.go
golang
1+1 = 2
7.0/3.0 = 2.3333333333333335
false
true
false
```


