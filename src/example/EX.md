### For-learning-Go-Tutorial
Go语言各种值类型，包括字符串、整数、浮点数、布尔值等。下面是一些基本示例。

下面我以一个简单的string例子开始吧。
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
打印输出:
```go
$ go run values.go
golang
1+1 = 2
10.0/2.0 = 5
false
true
false
```
这是最基本的语法，相信通过这个简单的例子大家已经初步对Go语言由了基本认识，那接下来开启Go的世界！
