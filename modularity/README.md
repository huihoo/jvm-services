## Modularity
Modular java，模块化Java，Jigsaw 和 OSGi。

Java模块化是构建大型应用和生态系统的关键。

### 规范
* [Java Platform Module System: Requirements DRAFT 2](http://openjdk.java.net/projects/jigsaw/spec/reqs/02)
* [JSR 376: Java Platform Module System](http://openjdk.java.net/projects/jigsaw/spec)
* [JEP 220: Modular Run-Time Images](http://openjdk.java.net/jeps/220)
* [JEP 201: Modular Source Code](http://openjdk.java.net/jeps/201)
* [JEP 200: The Modular JDK](http://openjdk.java.net/jeps/200)
* [JSR 277 and OSGi](http://www.osgi.org/blog/2006/10/jsr-277-review.html)

### 模块化模式
* 基本模式（Base Pattern）
* 管理关系（Manage Relationship）：设计模块关系。
* 模块重用（Module Reuse）：强调模块级别的重用。
* 模块内聚（Cohesive Module）：模块的行为应该只服务于一个目的。
* 依赖模式（Dependency Pattern）
* 非循环关系（Acyclic Relationship）：模块关系必须是非循环的。
* 等级化模块（Levelize Module）：模块关系应该是等级化的。
* 物理分层（Physical Layer）：模块关系不应该违反概念上的分层。
* 容器独立（Container Independence）：模块应该独立于运行时容器。
* 独立部署（Independent Deployment）：模块应该是独立的可部署单元。
* 可用性模式（Usability Pattern）
* 发布接口（Published Interface）：使模块的发布接口众所周知。
* 外部配置（External Configuration）：模块应该可以在外部进行配置。
* 默认实现（Default Implementation）：为模块提供一个默认实现。
* 模块门面（Module Facade）：为具有底层实现的细粒度模块创建一个门面，使其成为细粒度模块的一个粗粒度入口。
* 扩展性模式（Extensibility Pattern）
* 抽象化模块（Abstract Module）：依赖于模块的抽象元素。
* 实现工厂（Implementation Factory）：使用工厂来创建模块的实现类。
* 分离抽象（Separate Abstraction）：将抽象与实现它们的类放在各自独立的模块中。
* 通用模式（Utility Pattern）
* 就近异常（Colocate Exception）：异常应该接近抛出它们的类或接口。
* 等级化构建（Levelize Build:）：按照模块的等级执行构建。
* 测试模块（Test Module）：每个模块应该有一个对应的测试模块。
模块化模式来自：《Java应用架构设计：模块化模式与OSGi》

### OSGi
OSGi - The Dynamic Module System for Java

OSGi还是模块化领域中的一个工具，可用于模块化并在模块之间强制施加边界。随着项目规模的不断扩大，强有力的模块化系统所带来的价值已经超越了实现模块化的代价。

OSGi规范为网络服务定义了一个标准的、面向组件的计算环境。将OSGI服务平台添加到一个网络设备中，可以为其增加在网络的任何地方管理组件的生命周期的能力。软件组件可以从运行中被安装、升级或者移除而不需要中断设备的操作。软件组件可以动态的发现和使用其他库或者应用程序。通过这个平台，软件组件可以作为商品在柜台中出售以及在家里开发。OSGi联盟已经开发出很多标准组件接口，从普通的功能如：HTTP server、configuration、 logging、security、user administration、XML等等很多。一致的插件机制可以使这些组件满足不同买主的不同需求。

软件组件架构致力于一个软件开发中越来越大的问题：大量的基础配置需要开发和维护。标准化的OSGI组件架构显然可以简化这个配置过程。

OSGi的用途和目标：
* 降低复杂性：OSGi 由捆绑包组成。捆绑包（Bundles） 是完全模块化的，只通过服务接口相互通信。
* 重用：由于 OSGi 捆绑包是完全模块化的，因此它们支持更好的重用。有些开源项目将它们的 Java 类打包到与 OSGi 捆绑包兼容的 JARs 中。
* 易于部署：OSGi 框架提供一个标准化的 API，以支持 OSGi 实现使用一些工具来安装、启动和停止 OSGi 捆绑包。
* 动态更新：由于 OSGi 捆绑包是模块化的且易于部署，因此无需重新启动应用程序即可进行更新。
* 版本控制：捆绑包的动态更新和沙箱化特性支持轻松部署和使用捆绑包的不同版本，而不会在 JARs 之间遇到冲突。类加载被沙箱化到每个捆绑包，因此日志记录框架这样的依赖项在捆绑包之间即使不同也不会导致问题。

OSGi规范的核心组件是OSGi框架。该框架为应用程序（被成为bundles）提供一个标准化的环境。这个框架被分为以下几个层次：
* L0: 执行环境
* L1: 组件模块
* L2: 组件生命周期管理
* L3: 服务注册

### Karaf
Apache Karaf 是一个轻量的的 OSGi 运行时，被用于众多开源项目中，如：[ONOS (Open Network Operating System) ](http://onosproject.org/), [OpenDaylight](http://www.opendaylight.org/), [OpenHAB](http://www.openhab.org/), [Liferay](https://www.liferay.com/), [Nexus](http://www.sonatype.com/), [Talend](http://www.talend.com/)。

Apache Karaf提供了一个可升级、模块化的企业级应用平台，你可以专注于自己的业务和应用，Karaf帮助搞定其它部分，你也可通过Karaf开发基于OSGi架构的微服务。 

DevOps：OSGi - Dev 和 Karaf - Ops 
* Runtime: Karaf Runtime 
* Clustering: Karaf Cellar 
* Repository: Karaf Cave 
* Monitoring: Karaf Decanter

### 文档
* [Project Jigsaw: Under the Hood](http://docs.huihoo.com/javaone/2015/CON6823-Project-Jigsaw-Under-the-Hood.pdf)
* [Migrating Java UI Client Apps to the Modular JDK](http://docs.huihoo.com/javaone/2015/CON4384-Migrating-Java-UI-Client-Apps-to-the-Modular-JDK.pdf)
* [Java Components: Solving the Puzzle with Jigsaw and Gradle](http://docs.huihoo.com/javaone/2015/CON10063-Java-Components-Solving-the-Puzzle-with-Jigsaw-and-Gradle.pdf)
* [Packaging Java Applications](http://docs.huihoo.com/javaone/2015/CON3467-Packaging-Java-Applications.pdf)
* [Modular Java 幻灯片](http://docs.huihoo.com/apache/apachecon/us2011/11-Friday/A-Modular-Java/)
* [OSGi: Simplifying the IoT Gateway](http://docs.huihoo.com/eclipse/eclipsecon/europe2015/OSGi-Simplifying-the-IoT-Gateway.pdf)
* [Building Modular Cloud Applications with OSGi](http://docs.huihoo.com/javaone/2015/TUT2489-Building-Modular-Cloud-Applications-with-OSGi.pdf)
* [Using OSGi to Build Better Software](http://docs.huihoo.com/apache/apachecon/us2011/11-Friday/A-Modular-Java/A-1530-Using-OSGi-to-Build-Better-Software.ppt)
* [Microservices with OSGi](https://docs.huihoo.com/microservices/Microservices-with-OSGi.pdf)

### 图集
![JDK 9 Modules](https://wiki.huihoo.com/images/6/63/JDK-9-Modules.png)JDK 9 Modules

![JDK Modules](https://wiki.huihoo.com/images/a/ab/Jdk-module-graph.png)JDK Modules

![OSGi容器安全](https://wiki.huihoo.com/images/4/48/Osgi-container-security-architecture.gif)OSGi容器安全

![kafaf](https://wiki.huihoo.com/images/b/b8/Apache-kafaf.png)Apache Karaf

![microservices](https://wiki.huihoo.com/images/4/48/Microservices-with-osgi.png)Microservices with OSGi

### 链接
* [Awesome OSGi](https://github.com/rebaze/awesome-osgi) ![awesome](https://wiki.huihoo.com/images/1/13/Awesome.png)
* [OSGi官网](http://www.osgi.org/)
* [OSGi中文社区](http://www.osgi.com.cn/)
* [Apache Karaf](https://karaf.apache.org/)