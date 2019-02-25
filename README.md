# 概述
这个一个基础的消息通信架构，只在解决服务端与客户端消息通信，可应用于消息推送，即时通信以及由此衍生出来的消息通信业务。本项目基于其他开源项目的基础上，
希望通过合理的分布式架构，解决大规模并发链接的问题，从而适应互联网用户不断增长的需求，本项目将会采用微服务的开发与设计模式进行架构设计，尽量保持各个业务的单一性和高可用性。
这样的目的也是基于业务扩展的方式，方便以后能够在基于此通信架构基础上衍生其他相关业务，从而保持业务的独立性，增加项目的可维护性。

# 基础架构

![image](attachment/push-universe.png)

## Push-connector
### 基本功能
* 提供集群链接管理的能力
* 提供消息群发的功能
* 提供消息单发的功能
* 客户端管理服务


## Push-gate
### 基本功能
所有推送到客户端的请求都必须经过此网关，确保推送出口一致，此网关仅仅提供RPC调用接口，以提高接口调用效率
* 提供单推功能
* 提供群组推送功能

## Push-Cache
### 基本功能
提供消息缓存服务
* 消息缓存
* 消息过期

## Push-api
### 基本功能
提供推送Http接口服务，调用推送网关发送推送消息，此接口采用springboot开发web服务


# 扩展服务
## 聊天服务
* 单聊服务
* 群组服务



# 部署

**NOTE:** 部署connector要同时更新，防止出现redisson发布订阅数据解析问题

# 参考资料
## 参考项目
* [T-io](https://github.com/tywo45/t-io)
* [蚂蚁通信框架实践](https://mp.weixin.qq.com/s/JRsbK1Un2av9GKmJ8DK7IQ)

