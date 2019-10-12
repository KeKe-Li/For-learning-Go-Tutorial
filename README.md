### For-learning-Go-Tutorial
准备写一本Go的书针对初学者快速入门开发和使用go！
<p align="center">
<img width="100%" align="center" src="src/images/1.jpg" />
</p>

<p align='center'>
<img src="https://img.shields.io/badge/build-passing-brightgreen.svg">
<a href="https://twitter.com/perfactsen"><img src="https://img.shields.io/badge/twitter-keke-green.svg?style=flat&colorA=009df2"></a>
<a href="https://www.zhihu.com/people/sencoed.com/activities"><img src="https://img.shields.io/badge/%E7%9F%A5%E4%B9%8E-keke-green.svg?style=flat&colorA=009df2"></a>
</p>

学习Go语言需要去了解Go的特性，然后在深入的去实践，如果你想使用Go语言写出Go味道的程序，那么你就需要付出努力去实践了！
先来了解下Go语言为何创造出来的历史吧，Go 语言是由谷歌公司在 2007 年开始开发的一门语言，目的是能在多核心时代高效编写网络应用程序。Go 语言的创始人 Robert Griesemer、Rob Pike 和 Ken Thompson 都是在计算机发展过程中作出过重要贡献的人。
自从 2009 年 11 月正式公开发布后，Go 语言迅速席卷了整个互联网后端开发领域，其社区里不断涌现出类似 vitess、Docker、etcd、Consul 等重量级的开源项目。

Go是一种编译型语言，一种并发的、带垃圾回收的、快速编译的语言。它具有以下特点：

* 它可以在一台计算机上用几秒钟的时间编译一个大型的Go程序。
* Go为软件构造提供了一种模型，它使依赖分析更加容易，且避免了大部分C风格include文件与库的开头。
* Go是静态类型的语言，它的类型系统没有层级。因此用户不需要在定义类型之间的关系上花费时间，这样感觉起来比典型的面向对象语言更轻量级。
* Go完全是垃圾回收型的语言，并为并发执行与通信提供了基本的支持。

为了获得最佳的运行性能,GO语言被设计成一门静态编译型的语言，而不是动态解释型语言，这里我对静态编译型的语言和动态解释型语言做个简单的介绍，方便初学Go语言的新人理解。

1.静态编译型的语言

静态类型语言是指在编译时变量的数据类型即可确定的语言，多数静态类型语言要求在使用变量之前必须声明数据类型，某些具有类型推导能力的现代语言可能能够部分减轻这个要求. 并且通过编译器（compiler）将源代码编译成机器码，之后才能执行的语言。一般需经过编译（compile）、链接（linker）这两个步骤。编译是把源代码编译成机器码，链接是把各个模块的机器码和依赖库串连起来生成可执行文件。

代表语言：Java,Go,C

2.动态解释型语言

动态类型语言是在运行 时确定数据类型的语言。变量使用之前不需要类型声明，通常变量的类型是被赋值的那个值的类型。解释性语言的程序不需要编译，相比编译型语言省了道工序，解释性语言在运行程序的时候才逐行翻译。

代表语言：JavaScript、Python

Go语言的官方编译器被称为gc,包括编译工具5g,6g.8g，链接工具51,61和81以及文档查看工具godoc.
学习一门语言最好的方式就是去实践，那么我们就从go的例子开始实践吧！

* [例子入门](https://github.com/KeKe-Li/For-learning-Go-Tutorial/blob/master/src/example/EX.0.1.md)
* [基本结构](https://github.com/KeKe-Li/For-learning-Go-Tutorial/blob/master/src/chapter01/01.0.md)
* [基本数据类型](https://github.com/KeKe-Li/For-learning-Go-Tutorial/blob/master/src/chapter02/01.0.md)  
* [复合数据类型](https://github.com/KeKe-Li/For-learning-Go-Tutorial/blob/master/src/chapter03/01.0.md)
* [函数](https://github.com/KeKe-Li/For-learning-Go-Tutorial/blob/master/src/chapter04/01.0.md)
* [方法(method)](https://github.com/KeKe-Li/For-learning-Go-Tutorial/blob/master/src/chapter05/01.0.md)
* [接口(Interfaces)](https://github.com/KeKe-Li/For-learning-Go-Tutorial/blob/master/src/chapter06/01.0.md)
* [反射(reflection)](https://github.com/KeKe-Li/For-learning-Go-Tutorial/blob/master/src/chapter07/01.0.md)
* [通信协议解析](https://github.com/KeKe-Li/For-learning-Go-Tutorial/blob/master/src/chapter08/01.0.md)
* [Channel](https://github.com/KeKe-Li/For-learning-Go-Tutorial/blob/master/src/chapter09/01.0.md)
* [Goroutine并发处理](https://github.com/KeKe-Li/For-learning-Go-Tutorial/blob/master/src/chapter10/01.0.md)
* [Golang包详解](https://github.com/KeKe-Li/For-learning-Go-Tutorial/blob/master/src/chapter11/01.0.md)
* [Grpc与Protobuf](https://github.com/KeKe-Li/For-learning-Go-Tutorial/blob/master/src/chapter12/01.0.md)
* [Golang逃逸分析](https://github.com/KeKe-Li/For-learning-Go-Tutorial/blob/master/src/chapter13/01.0.md)
* [Etcd的使用](https://github.com/KeKe-Li/For-learning-Go-Tutorial/blob/master/src/chapter14/01.0.md)
* [TiDB的使用](https://github.com/KeKe-Li/For-learning-Go-Tutorial/blob/master/src/chapter15/01.0.md)
* [Go排序算法及其性能比较](https://github.com/KeKe-Li/For-learning-Go-Tutorial/blob/master/src/chapter16/01.0.md)
* [Go程序测试](https://github.com/KeKe-Li/For-learning-Go-Tutorial/blob/master/src/chapter17/01.0.md)
* [Go编程标准和规范](https://github.com/KeKe-Li/For-learning-Go-Tutorial/blob/master/src/spec/01.0.md)
* [Golang垃圾回收](https://github.com/KeKe-Li/For-learning-Go-Tutorial/blob/master/src/spec/02.0.md)
* [Go练习案例](https://github.com/KeKe-Li/For-learning-Go-Tutorial/blob/master/src/example/EX.0.2.md)
* [Sync.Map解析](https://github.com/KeKe-Li/For-learning-Go-Tutorial/blob/master/src/chapter18/01.0.md)
* [Sync.WaitGroup解析](https://github.com/KeKe-Li/For-learning-Go-Tutorial/blob/master/src/chapter19/01.0.md)

### golang编程

觉得此文章不错，支持我的话可以给我star ，:star:！如果有问题可以加我的微信,也可以加入我们的交流群一起交流golang技术！
<p align="center">
<img width="300" align="center" src="https://github.com/KeKe-Li/micro-Services-Tutorial/blob/master/src/images/12.jpg" />
<img width="300" align="center" src="https://github.com/KeKe-Li/micro-Services-Tutorial/blob/master/src/images/13.jpg" />
</p>

### License
This is free software distributed under the terms of the MIT license
