# high_io
# 目前的常用的IO复用模型有三种：select，poll，epoll，我们主要分析select和epoll；
一、select模型
  说的通俗一点就是各个客户端连接的文件描述符也就是套接字，都被放到了一个集合中，
调用select函数之后会一直监视这些文件描述符中有哪些可读，如果有可读的描述符那
么我们的工作进程就去读取资源。
二、epoll模型
epoll是基于内核的反射机制，在有活跃的 socket 时，系统会调用我们提前设置的回调函数,
epoll 也分为边沿处罚和水平触发，在文档中分别为 epoll 和 epoll_et.
