### For-learning-Go-Tutorial
Go语言各种值类型，包括字符串、整数、浮点数、布尔值等。下面是一些基本示例。

Go语言最主要的特性：
* 自动垃圾回收
* 更丰富的内置类型
* 函数多返回值
* 错误处理
* 匿名函数和闭包
* 类型和接口
* 并发编程
* 反射
* 语言交互性



下面我以一个简单的string例子开始吧。

```go
package main
import "fmt"
func main() {
    fmt.Println("go" + "lang")

    fmt.Println("1+1 =", 1+1)
    fmt.Println("10.0/2.0 =", 10.0/2.0)
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
