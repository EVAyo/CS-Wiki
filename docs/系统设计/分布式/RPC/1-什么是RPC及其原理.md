# 📞 什么是 RPC 及其原理

---

## 1. 什么是 RPC

`RPC（Remote Procedure Call）远程过程调用`，它是一种通过网络从远程计算机程序上请求服务，而不需要了解底层网络技术的协议。比如两个不同的服务 A、B 部署在两台不同的机器上，那么服务 A 如果想要调用服务 B 中的某个方法该怎么办呢？使用 HTTP 请求当然可以，但是可能会比较麻烦。 **RPC 的出现就是为了让你调用远程方法像调用本地方法一样简单**。

## 2. RPC 原理

![](https://gitee.com/veal98/images/raw/master/img/20201126202743.png)

1. 服务消费方（client）以本地调用方式调用服务；
2. client stub 接收到调用后负责将方法、参数等组装成能够进行网络传输的消息体；
3. client stub 找到服务地址，并将消息发送到服务端；
4. server stub 收到消息后进行解码；
5. server stub 根据解码结果调用本地的服务；
6. 本地服务执行并将结果返回给 server stub；
7. server stub 将返回结果打包成消息并发送至消费方；
8. client stub 接收到消息，并进行解码；
9. 服务消费方得到最终结果。

时序图如下：

![](https://gitee.com/veal98/images/raw/master/img/20201126202849.png)





## 📚 References

- [Github - Advanced Java](https://doocs.gitee.io/advanced-java/#/./docs/distributed-system/distributed-system-interview)
- [Github - JavaGuide](https://snailclimb.gitee.io/javaguide/#/docs/system-design/distributed-system/分布式?id=二-分布式事务)