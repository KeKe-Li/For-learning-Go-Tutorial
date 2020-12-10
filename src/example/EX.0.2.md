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

#### Go语言案例总结

最近一直在写一部针对初入门Golang开发人员的书，我觉得最好的状态就是学习了基础之后，练习，然后做项目中不断的提高！

GO 例子目录：

* [Go 数组](#Go数组)
* [Go map](#map)
* [Go 函数定义](#Go函数定义)
* [Go 方法](#Go方法)
* [Go 结构体](#Go结构体)
* [Go Channel](#Channel)
* [Go 闭包函数](#Go闭包函数)
* [Go Defer函数]()
* [Go 接口]()
* [Go Base64编码]()
* [Go 状态协程]()
* [Go Panic]()
* [Go 散列函数]()
* [Go 工作池]()
* [Go 进程触发]()
* [Go 时间戳]()
* [Go 时间格式化和解析]()
* [Go 通道缓冲]()
* [Go IO]()
* [Go 压缩]()

#### Go数组
* 数组是一个具有相同数据类型的元素组成的固定长度的有序集合。
* 在Go语言中，数组是值类型，长度是类型的组成部分，也就是说"[10]int"和“[20]int”是完全不同的两种数组类型。
* 同类型的两个数组支持"=="和"!="比较，但是不能比较大小。
* 数组作为参数时，函数内部不改变数组内部的值，除非是传入数组的指针。
* 数组的指针：*[2,3,4]int
* 指针数组：[3]*int

```go
package main

import "fmt"

func main() {

	// 这里我们创建了一个具有5个元素的整型数组
	// 元素的数据类型和数组长度都是数组的一部分
	// 默认情况下，数组元素都是零值
	// 对于整数，零值就是0
	var a [5]int
	fmt.Println("emp:", a)

	// 我们可以使用索引来设置数组元素的值，就像这样
	// "array[index] = value"  或者使用索引来获取元素值，
	// 就像这样"array[index]"
	a[4] = 100
	fmt.Println("set:", a)
	fmt.Println("get:", a[4])

	// 内置的len函数返回数组的长度
	fmt.Println("len:", len(a))

	// 这种方法可以同时定义和初始化一个数组
	b := [5]int{1, 2, 3, 4, 5}
	fmt.Println("dcl:", b)

	// 数组都是一维的，但是你可以把数组的元素定义为一个数组
	// 来获取多维数组结构
	var twoD [2][3]int
	for i := 0; i < 2; i++ {
		for j := 0; j < 3; j++ {
			twoD[i][j] = i + j
		}
	}
	fmt.Println("2d: ", twoD)
}
```
输出结果为:
```go
emp: [0 0 0 0 0]
set: [0 0 0 0 100]
get: 100
len: 5
dcl: [1 2 3 4 5]
2d:  [[0 1 2] [1 2 3]]
```
拥有固定长度是数组的一个特点，但是这个特点有时候会带来很多不便，尤其在一个集合元素个数不固定的情况下。这个时候我们更多地使用切片。


#### map

map是Go语言内置的关联数据类型。因为数组是索引对应数组元素，而字典是键对应值。
```go
package main

import "fmt"

func main() {

	// 创建一个字典可以使用内置函数make
	// "make(map[键类型]值类型)"
	m := make(map[string]int)

	// 使用经典的"name[key]=value"来为键设置值
	m["k1"] = 9
	m["k2"] = 22

	// 用Println输出字典，会输出所有的键值对
	fmt.Println("map:", m)

	// 获取一个键的值 "name[key]".
	v1 := m["k1"]
	fmt.Println("v1: ", v1)

	// 内置函数返回字典的元素个数
	fmt.Println("len:", len(m))

	// 内置函数delete从字典删除一个键对应的值
	delete(m, "k2")
	fmt.Println("map:", m)

	// 根据键来获取值有一个可选的返回值，这个返回值表示字典中是否
	// 存在该键，如果存在为true，返回对应值，否则为false，返回零值
	// 有的时候需要根据这个返回值来区分返回结果到底是存在的值还是零值
	// 比如字典不存在键x对应的整型值，返回零值就是0，但是恰好字典中有
	// 键y对应的值为0，这个时候需要那个可选返回值来判断是否零值。
	_, ok := m["k2"]
	fmt.Println("ok:", ok)

	// 可以用 ":=" 同时定义和初始化一个字典
	n := map[string]int{"foo": 1, "bar": 2}
	fmt.Println("map:", n)
}
```
输出结果为:
```go
map: map[k1:9 k2:22]
v1:  9
len: 2
map: map[k1:9]
ok: false
map: map[foo:1 bar:2]
```
#### Go函数定义

函数是Go语言的重要内容。
```go
package main

import "fmt"

// 这个函数计算两个int型输入数据的和，并返回int型的和
func plus(a int, b int) int {
	// Go需要使用return语句显式地返回值
	return a + b
}

func main() {
	// 函数的调用方式很简单
	// "名称(参数列表)"
	res := plus(1, 2)
	fmt.Println("1+2 =", res)
}
```

输出结果为:
```go
1+2 = 3
```

#### Go方法

通常的函数定义叫做函数，定义在结构体上面的函数叫做该结构体的方法。
从某种意义上说，方法是函数的“语法糖”。当函数与某个特定的类型绑定，那么它就是一个方法。也证因为如此，我们可以将方法“还原”成函数。
```go
package main

import "fmt"

type rect struct {
	width, height int
}

// 这个area方法有一个限定类型*rect，
// 表示这个函数是定义在rect结构体上的方法
func (r *rect) area() int {
	return r.width * r.height
}

// 方法的定义限定类型可以为结构体类型
// 也可以是结构体指针类型
// 区别在于如果限定类型是结构体指针类型
// 那么在该方法内部可以修改结构体成员信息
func (r rect) perim() int {
	return 2*r.width + 2*r.height
}

func main() {
	r := rect{width: 10, height: 5}

	// 调用方法
	fmt.Println("area: ", r.area())
	fmt.Println("perim:", r.perim())

	// Go语言会自动识别方法调用的参数是结构体变量还是
	// 结构体指针，如果你要修改结构体内部成员值，那么使用
	// 结构体指针作为函数限定类型，也就是说参数若是结构体
	//变量，仅仅会发生值拷贝。
	rp := &r
	fmt.Println("area: ", rp.area())
	fmt.Println("perim:", rp.perim())
}
```

输出结果为:
```go
area:  50
perim: 30
area:  50
perim: 30
```
#### Go结构体

#### Channel

channel常用的10中操作:

1. 使用for range读channel

场景:当需要不断从channel读取数据时.

使用for-range读取channel，这样既安全又便利，当channel关闭时，for循环会自动退出，无需主动监测channel是否关闭，可以防止读取已经关闭的channel，造成读到数据为通道所存储的数据类型的零值。

```go
for x := range ch{
    fmt.Println(x)
}
```
2. 使用v,ok := <-ch + select操作判断channel是否关闭

场景:判断channel是否关闭.其中ok的含义是:
```markdown
true：读到通道数据，不确定是否关闭，可能channel还有保存的数据，但channel已关闭。
false：通道关闭，无数据读到。
```
从关闭的channel读值读到是channel所传递数据类型的零值，这个零值有可能是发送者发送的，也可能是channel关闭了。

情况1：当chanrecv返回(false,false)时，本质是select操作失败了，所以相关的case会阻塞，不会执行:

```go
func main() {
	ch := make(chan int)
	select {
	case v, ok := <-ch:
		fmt.Printf("v: %v, ok: %v\n", v, ok)
	default:
		fmt.Println("nothing")
	}
}
```
情况2：下面的结果会是零值和false：

```go 
func main() {
	ch := make(chan int)
	// 增加关闭
	close(ch)

	select {
	case v, ok := <-ch:
		fmt.Printf("v: %v, ok: %v\n", v, ok)
	}
}
```

向channel写数据然后关闭，依然可以从已关闭channel读到有效数据，但channel关闭且没有数据时，读不到有效数据，ok为false，可以确定当前channel已关闭。
```go 
func main() {
	ch := make(chan int, 1)

	// 发送1个数据关闭channel
	ch <- 1
	close(ch)
	print("close channel\n")

	// 不停读数据直到channel没有有效数据
	for {
		select {
		case v, ok := <-ch:
			print("v: ", v, ", ok:", ok, "\n")
			if !ok {
				print("channel is close\n")
				return
			}	
		default:
			print("nothing\n")
		}
	}
}

// 结果
// close channel
// v: 1, ok:true
// v: 0, ok:false
// channel is close
```

3. 使用select处理多个channel

场景:需要对多个通道进行同时处理，但只处理最先发生的channel时.

select可以同时监控多个通道的情况，只处理未阻塞的case。当通道为nil时，对应的case永远为阻塞，无论读写。

这里需要注意下特殊关注：普通情况下，对nil的通道写操作是要panic的。

```go
// 分配job时，如果收到关闭的通知则退出，不分配job
func (h *Handler) handle(job *Job) {
    select {
    case h.jobCh<-m:
        return 
    case <-h.stopCh:
        return
    }
}
```

4. 使用channel的声明控制读写权限

场景:协程对某个通道只读或只写时.

目的：

* 使代码更易读、更易维护，
* 防止只读协程对通道进行写数据，但通道已关闭，造成panic,

通常如果协程对某个channel只有写操作，则这个channel声明为只写。如果协程对某个channel只有读操作，则这个channe声明为只读。
```go
// 只有generator进行对outCh进行写操作，返回声明
// <-chan int，可以防止其他协程乱用此通道，造成隐藏bug
func generator(int n) <-chan int {
    outCh := make(chan int)
    go func(){
        for i:=0;i<n;i++{
            outCh<-i
        }
    }()
    return outCh
}

// consumer只读inCh的数据，声明为<-chan int
// 可以防止它向inCh写数据
func consumer(inCh <-chan int) {
    for x := range inCh {
        fmt.Println(x)
    }
}
```

5. 使用缓冲channel增强并发

场景:异步

有缓冲通道可供多个协程同时处理，在一定程度可提高并发性。

```go
// 无缓冲
ch1 := make(chan int)
ch2 := make(chan int, 0)
// 有缓冲
ch3 := make(chan int, 1)
```

```go 
// 使用5个start协程同时处理输入数据
func test() {
    inCh := generator(100)
    outCh := make(chan int, 10)

    for i := 0; i < 5; i++ {
        go start(inCh, outCh)
    }

    for r := range outCh {
        fmt.Println(r)
    }
}

func start(inCh <-chan int, outCh chan<- int) {
    for v := range inCh {
        outCh <- v * v
    }
}
```

6. 为操作加上超时

场景:需要超时控制的操作.

使用select和time.After，看操作和定时器哪个先返回，处理先完成的，就达到了超时控制的效果

```go 
func doWithTimeOut(timeout time.Duration) (int, error) {
	select {
	case ret := <-start():
		return ret, nil
	case <-time.After(timeout):
		return 0, errors.New("timeout")
	}
}

func start() <-chan int {
	outCh := make(chan int)
	go func() {
		// do work
	}()
	return outCh
}
```

7. 使用time实现channel无阻塞读写

场景:并不希望在channel的读写上浪费时间.

使用channel为操作加上超时的扩展，这里的操作是channel的读或写.
```go 
func unBlockRead(ch chan int) (x int, err error) {
	select {
	case x = <-ch:
		return x, nil
	case <-time.After(time.Microsecond):
		return 0, errors.New("read time out")
	}
}

func unBlockWrite(ch chan int, x int) (err error) {
	select {
	case ch <- x:
		return nil
	case <-time.After(time.Microsecond):
		return errors.New("read time out")
	}
}
```
这里的time.After等待可以替换为default，则是channel阻塞时，立即返回的效果.

8. 使用close(ch)关闭所有下游协程

场景:退出时，显示通知所有协程退出.

```go 
func (h *Handler) Stop() {
    close(h.stopCh)

    // 可以使用WaitGroup等待所有协程退出
}

// 收到停止后，不再处理请求
func (h *Handler) loop() error {
    for {
        select {
        case req := <-h.reqCh:
            go handle(req)
        case <-h.stopCh:
            return
        }
    }
}
```

9. 使用chan struct{}作为信号channel

场景:使用channel传递信号，而不是传递数据时.

没数据需要传递时，传递空struct.

```go 
// 如果channel不需要传递任何数据,只是要给所有协程发送退出的信号
type Handler struct {
    stopCh chan struct{}
    recevieCh chan *Request
}
```

10. 使用channel传递结构体的指针而非结构体

场景:使用channel传递结构体数据时.

channel本质上传递的是数据的拷贝，拷贝的数据越小传输效率越高，传递结构体指针，比传递结构体更高效.

```go
// 效率高
receiveCh chan *Request

// 效率低
receiveCh chan Request
```

11. 使用channel传递channel

场景:使用场景有点多，通常是用来获取结果.

channel可以用来传递变量，channel自身也是变量，可以传递自己。

```go
package main

import (
	"fmt"
	"math/rand"
	"sync"
	"time"
)

func main() {
	reqs := []int{1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
	// 存放结果的channel的channel
	outs := make(chan chan int, len(reqs))
	var wg sync.WaitGroup
	wg.Add(len(reqs))
	for _, x := range reqs {
		o := handle(&wg, x)
		outs <- o
	}

	go func() {
		wg.Wait()
		close(outs)
	}()

	// 读取结果，结果有序
	for o := range outs {
		fmt.Println(<-o)
	}
}

// handle 处理请求，耗时随机模拟
func handle(wg *sync.WaitGroup, a int) chan int {
	out := make(chan int)
	go func() {
		time.Sleep(time.Duration(rand.Intn(3)) * time.Second)
		out <- a
		wg.Done()
	}()
	return out
}
```







