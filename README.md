# mymuduo
基于c++11重写的部分muduo库的网络库
### 简介
***
* 用Channel和Poller实现了non-blocking + IO-multiplexing为核心的EventLoop。并通过runInLoop和queueInLoop接口提高线程安全
* 用TcpServer和TcpConnection等类实现了Multiple Reactors 模型。在开启服务器监听时设置了原子类，防止一个TcpServer对象被start多次请求
* 在EventLoopThread类中设置threadFunc方法做到“one loop perthread”；并用getNextLoop在EventLoopThreadPool中轮询获取下一个处理事件的loop
### 核心代码模块
***
* Channel
* Poller和EPollPoller
* EventLoop
* Thread和EventLoopThread
* EventLoopThreadPool
* Socket
* Acceptor
* Buffer
* TcpConnection
* TcpServer
