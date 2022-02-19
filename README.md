# grpc
## grpc简介
    1.gRPC  是一个高性能、开源和通用的 RPC 框架，面向移动和 HTTP/2设计
    2.目前提供 C、Java 和 Go 语言版本，分别是：grpc, grpc-java, grpc-go
    3.其中 C 版本支持 C, C++, Node.js, Python, Ruby, Objective-C, PHP 和 C# 支持
    4.gRPC 基于 HTTP/2 标准设计，带来诸如双向流、流控、头部压缩、单 TCP 连接上的多复用请求等特性
    5.HTTP1,文本传输数据,每个请求都需建立tcp连接(等待请求返回才顺序执行下一个请求)
    6.HTTP2,二进制传输数据,同一地方的多次请求只需建立一次tcp连接(多路复用),头部数据压缩(内容相同二次请求复用),服务端可主动推送数据至客户端
   ###### 为什么使用 gRPC?
    我们的例子是一个简单的路由映射的应用，它允许客户端获取路由特性的信息，生成路由的总结，以及交互路由信息，如服务器和其他客户端的流量更新。
    有了 gRPC， 我们可以一次性的在一个 .proto 文件中定义服务并使用任何支持它的语言去实现客户端和服务器，反过来，它们可以在各种环境中，
    从Google的服务器到你自己的平板电脑—— gRPC 帮你解决了不同语言及环境间通信的复杂性.使用 protocol buffers 还能获得其他好处，
    包括高效的序列号，简单的 IDL 以及容易进行接口更新。
    个人理解：可以写一套service，通过proto文件生成不同语言的代码执行。微服务中，可以分为几个模块执行，各个模块间异常情况互不干扰，
    各个模块可以使用不同的语言执行（可以利用不同语言的特点进行service最大化利用）
## goland的grpc环境搭建
    1.先安装Protobuf 编译器 protoc,下载地址：https://github.com/google/protobuf/releases,解压缩得到protoc.exe(可以把proto编译成其他语言)
    2.获取protobuf编解码支持库，go get -u github.com/golang/protobuf/proto
    3.编辑成go的插件，go get -u github.com/golang/protobuf/protoc-gen-go
    4.引入grpc支持，go get google.golang.org/grpc
