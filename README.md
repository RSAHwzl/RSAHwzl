# grpc
## 1.grpc简介
    gRPC  是一个高性能、开源和通用的 RPC 框架，面向移动和 HTTP/2设计。目前提供 C、Java 和 Go 语言版本，分别是：grpc, grpc-java, grpc-go。
    其中 C 版本支持 C, C++, Node.js, Python, Ruby, Objective-C, PHP 和 C# 支持。
    gRPC 基于 HTTP/2 标准设计，带来诸如双向流、流控、头部压缩、单 TCP 连接上的多复用请求等特性。
    HTTP1 文本传输数据    每个请求都需建立tcp连接（等待请求返回再执行下一个请求） 头部数据无处理
    HTTP2 二进制传输数据  同一地方的多次请求只需建立一次tcp连接（多路复用）头部数据压缩（内容相同二次请求复用）服务端可主动推送数据至客户端
## 1.go环境搭建
