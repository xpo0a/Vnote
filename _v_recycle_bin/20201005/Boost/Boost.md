Boost.Asio C++ 网络编程
# 0.Socket简介
IP+port+协议



# 0.Boost 是什么
    什么是 Boost.Asio？
    历史
    依赖
    编译 Boost.Asio
    重要的宏
    同步 VS 异步
    异常 VS 错误代码
    Boost.Asio 中的多线程
    不仅仅是网络请求
    计时器
    io_service 类
    总结
# 1.基本原理
    网络 API
    Boost.Asio 命名空间
    IP 地址
    端点
    Sockets
    同步错误代码
    Socket 成员函数
    其他注意事项
    read/write/connect 自由函数
    connect 函数
    read/write 函数
    异步编程
    为什么要异步？
    异步 run()，run_one()，poll()，poll_one()
    持续运行
    run_one()，poll()，poll_one() 函数
    异步工作
    异步 post() VS dispatch() VS wrap()
    保持运行
    总结
# 2.如何实现一个小客户端应用
    TCP 回显服务端/客户端
    TCP 同步客户端
    TCP 同步服务端
    TCP 异步客户端
    TCP 同步服务端
    代码
    UDP回显服务端/客户端
    UDP 同步回显客户端
    UDP 同步回显服务端
    总结
# 3.创建一个客户端/服务端应用
    同步客户端/服务端
    同步客户端
    同步服务端
    异步客户端/服务端
    异步客户端
    异步服务端
    总结
# 4.同步、异步方式
    同步异步混合编程
    客户端和服务端之间消息的互相传递
    客户端软件中的同步 I/O
    服务端软件中的同步 I/O
    同步服务端中的线程
    客户端软件中的异步 I/O
    服务端软件中的异步 I/O
    异步服务端中的线程
    异步操作
    代理实现
# 5.进阶
