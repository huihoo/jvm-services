## Apache Usergrid

### 简介

Apache Usergrid 是一个面向web和移动应用的多租户 Backend-as-a-Service 堆栈，基于 RESTful APIs，使用 Apache Cassandra 做后端存储。

可以把Usergrid看成在Cassandra上进行以用户为中心设计的最佳开源实践 :)

### 以用户为中心的设计

提供了一组用户核心应用实体对象(Data Entity Types)包括：

* 用户(user)
* 用户组(group)
* 角色(role)
* 应用(application)
* 行为(activity)
* 设备(device)
* 资源(asset)
* 目录(folder)
* 事件(event)
* 通知(notifier)
* 通告(notification)
* 收到(receipt)

每个对象都被保存在其各自的集合中(/users，/groups……)。Usergrid也允许创建用户想要的任何类型的动态(自定义的)实体。动态实体会被自动保存在以实体类型复数为名称的集合中。

所提及的消息(message)概念是以notifier、notification、receipt数据实体类型体现。

我们可以在此基础上开发一个以用户为基础开放平台。

### App基础设施

Mobile Backend as a Services(MBaaS)

提供开放API和多语言SDK。

![MBaaS](https://wiki.huihoo.com/images/c/c5/Multi-tenancy-at-scale.png)

### Cassandra

Cassandra带来分布式存储基础设施，为Usergrid带来高可用的水平扩展。

![usergrid core](https://wiki.huihoo.com/images/a/a4/Apache-usergrid-core.png)Usergrid核心架构

![usergrid usergroup](https://wiki.huihoo.com/images/8/81/Apache-usergrid-groups.png)Usergrid用户组

![usergrid keyspace](https://wiki.huihoo.com/images/0/00/Apache-usergrid-cassandra.png)Usergrid  Keyspace

### 文档

* [Building Your Own BaaS With Apache Usergrid & Docker: Lessons Learned At Scale](http://docs.huihoo.com/apache/apachecon/eu2014/Building-your-own-BaaS-with-Apache-Usergrid-and-Docker.pdf)
* [How to Contribute to Apache Usergrid](http://docs.huihoo.com/apache/usergrid/How-to-Contribute-to-Apache-Usergrid.pdf)
* [Apache Usergrid Internals](http://docs.huihoo.com/apache/usergrid/Apache-Usergrid-Internals.pdf)
* [Open Source Mobile Backend on Cassandra](http://docs.huihoo.com/apache/usergrid/Open-Source-Mobile-Backend-on-Cassandra.pdf)

### 链接

* [Apache Usergrid官网](https://usergrid.apache.org/)
* [Apache Usergrid @ GitHub](https://github.com/apache/usergrid)
