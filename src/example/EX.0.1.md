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

接着熟悉下Go环境变量:

```bash
> go env
GO111MODULE="auto"
GOARCH="amd64"
GOBIN="/Users/admin/goTest/bin"
GOCACHE="/Users/admin/Library/Caches/go-build"
GOENV="/Users/admin/Library/Application Support/go/env"
GOEXE=""
GOFLAGS=""
GOHOSTARCH="amd64"
GOHOSTOS="darwin"
GOINSECURE=""
GOMODCACHE="/Users/admin/goTest/pkg/mod"
GONOPROXY=""
GONOSUMDB=""
GOOS="darwin"
GOPATH="/Users/admin/goTest"
GOPRIVATE=""
GOPROXY="https://goproxy.cn,direct"
GOROOT="/usr/local/go"
GOSUMDB="sum.golang.org"
GOTMPDIR=""
GOTOOLDIR="/usr/local/go/pkg/tool/darwin_amd64"
GCCGO="gccgo"
AR="ar"
CC="clang"
CXX="clang++"
CGO_ENABLED="1"
GOMOD=""
CGO_CFLAGS="-g -O2"
CGO_CPPFLAGS=""
CGO_CXXFLAGS="-g -O2"
CGO_FFLAGS="-g -O2"
CGO_LDFLAGS="-g -O2"
PKG_CONFIG="pkg-config"
GOGCCFLAGS="-fPIC -m64 -pthread -fno-caret-diagnostics -Qunused-arguments -fmessage-length=0 -fdebug-prefix-map=/var/folders/kp/3yqnp9cj4f3_9539b06q4yyc0000gn/T/go-build238604917=/tmp/go-build -gno-record-gcc-switches -fno-common"
```
下面详细解释下关于Go的环境变量中的各个参数的含义:

| 参数             | 含义                                                                   | 
| --------------- |------------------------------------------------------------------------|
|GO111MODULE      | 是一个环境变量, on 仍将强制使用Go模块,off 强制Go表现出GOPATH方式,auto 是默认模式。|
|GOARCH           | 程序构建环境的目标计算架构 |
|GOBIN            | 该环境变量的值为 Go 程序的可执行文件的目录 |
|GOCACHE          | 存储编译后信息的缓存目录 |
|GOENV            | 本地的go环境文件存储位置 |
|GOEXE            | 可执行文件名后缀(".exe" on Windows) |
|GOFLAGS          | 当给定标志被当前命令已知时，默认情况下以空格分隔的-flag = value设置列表将应用于go命令。 |
|GOHOSTARCH       | Go工具链二进制文件的体系结构（GOARCH）。|
|GOINSECURE       | 逗号分隔的模块路径前缀列表（按Go的path.Match语法），应始终以不安全的方式获取。仅适用于直接获取的依赖项。 |
|GOMODCACHE       | Go命令将存储下载的模块的目录。|
|GOOS             | 为其编译代码的操作系统。例如linux，darwin，windows，netbsd。|
|GOPATH           | Go 命令依赖一个重要的环境变量,GOPATH允许多个目录，当有多个目录时，请注意分隔符.|
|GOPRIVATE        | Go的私有模块仓库 |
|GOPROXY          | Go的mod代理 |
|GOROOT           | Go安装目录的绝对路径|
|GOSUMDB          | 要使用的校验和数据库的名称，以及可选的公用密钥和URL。 |
|GOTMPDIR         | Go命令将在其中写入临时源文件，程序包和二进制文件的目录。 |
|GOTOOLDIR        | Go tool的安装目录|
|GCCGO            | 为"go build -compiler = gccgo"运行的gccgo命令。 |
|AR               | 使用gccgo编译器进行构建时用于处理库归档文件的命令。 |
|CC               | 用于编译C代码 |
|CXX              | 用于编译C代码 |
|CGO_ENABLED      | 是否支持cgo命令 |
|GOMOD            | 主模块go.mod的绝对路径。如果启用了模块感知模式，但没有go.mod，则GOMOD将为os.DevNull |

如果你想查看更加详细的可以通过命令:
```bash 
> go help environment
```

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
