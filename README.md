# 前言

偶然在网上看到一张咕泡学院的架构师成长路线图，觉得很适合作为自己准备找工作时的复习路线，为了方便操作，自己利用Xmind手敲了一幅脑图出来(侵权的话请联系我删除)。希望自己能够持之以恒，一砖一瓦地盖起这座高楼。

![awesome-architect]([https://github.com/raymond-zhao/awesome-architect/blob/master/08-%E5%8F%82%E8%80%83%E8%B5%84%E6%96%99/awesome-architect.png](https://github.com/raymond-zhao/awesome-architect/blob/master/08-参考资料/awesome-architect.png))

# 架构师学习路线

## 1 架构师必备工具

### 1.1 Git

- 0）什么是Git？
- 1）Git的工作原理？
- 2）Git常用命令
- 3）Git冲突的原因以及解决方式
- 4）架构师职责：Git Flow规范团队Git使用规程。

### 1.2 Maven

- 0）什么是Maven？
- 1）与Gradle的对比
- 2）生成可执行jar、理解scope生成最精确的jar
- 3）解决类冲突、包依赖、NoClassDefFoundError问题定位及解决
- 4）全面理解Maven的LifeCycle/Phase/Goal
- 5）架构师必备之Maven生成Archetype
- 6）Maven流行插件
- 7）Nexus环境搭建、上传、配置

### 1.3 Jenkins

- 0）什么是Jenkins
- 1）Jenkins持续集成基本思路
- 2）Jenkins避坑指南

### 1.4 SonarQube

- 0）什么是SonarQube
- 1）安装及环境搭建
- 2）代码检查规则配置
- 3）单元测试报表

### 1.5 Docker

- 0）什么是Docker？
- 1）了解Docker的镜像、仓库、容器
- 2）Docker基础支持简介
- 3）Kubernates入门到进阶
- 4）基于Kubernetes治理微服务

### 1.6 敏捷开发

- 0）什么是敏捷开发？
- 1）敏捷的由来

  - （1）传统模式的问题
  - （2）当前行业面临的问题
  - （3）微服务与敏捷

- 2）敏捷开发模式

  - （1）敏捷文化
  - （2）敏捷组织开发
  - （3）敏捷最佳实践

    - <1>TDD
    - <2>结对编程
    - <3>C1

  - （4）敏捷与DevOps

## 2 架构师内在心法

### 2.1 软件架构设计原则

- 1）Open Closed Principle：开闭原则
- 2）Dependency Inversion Principle：依赖倒转原则
- 3）Simple Responsibility Principle：单一职责原则原则
- 4）Interface Segregation Principle：接口隔离原则
- 5）Law of Demeter：迪米特法则
- 6）Liskov Substitution Principle：里氏代换原则
- 7）Composite/Aggregate Reuse Principle：合成复用原则

### 2.2 创建型模式

- 1）Simple Factory Pattern：简单工厂模式
- 2）Factory Method Pattern：工厂方法模式
- 3）Abstract Factory Pattern：抽象工厂模式
- 4）Builder Pattern：建造者模式
- 5）Singleton Pattern：单例模式
- 6）Prototype Pattern：原型模式

### 2.3 结构型模式

- 1）Flyweight Pattern：享元模式
- 2）Component Pattern：组合模式
- 3）Bridge Pattern：桥接模式
- 4）Adapter Pattern：：适配器模式
- 5）Facade Pattern：门面模式
- 6）Decorator Pattern：装饰器模式
- 7）Proxy Pattern：代理模式

### 2.4 行为型模式

- 1）Strategy Pattern：策略模式
- 2）Template Pattern：模板方法模式
- 3）Iterator Pattern：迭代器模式
- 4）Delegate Pattern：委派模式
- 5）Observer Pattern：观察者模式
- 6）Chain Responsibility Pattern：责任链模式
- 7）Command Pattern：命令模式
- 8）Memento Pattern：备忘录模式
- 9）State Pattern：状态模式
- 10）Visitor Pattern：访问者模式
- 11）Mediator Pattern：中介者模式
- 12）Interpreter Pattern：解释器模式

### 2.5 各设计模式对比总结及应用场景分析

### 2.6  主流框架中的设计模式剖析

## 3 分布式与高并发

### 3.1 并发编程

- 1）并发编程与原理

  - （1）从西安城的生命周期分析对线程的控制
  - （2）Synchronized的底层实现原理
  - （3）volatile的本质

- 2）J.U.C

  - （1）深入分析AbstractQueuedSynchronizer底层原理
  - （2）ConcurrentHaspMap源码分析
  - （3）阻塞队列原理及源码
  - （4）CountDownLatch、CyclicBarrier源码分析及实际应用
  - （5）线程池的实现原理及手写线程池

### 3.2 漫读分布式架构

- 1）分布式架构的发展与演进
- 2）如何把应用从单机扩展到分布式？
- 3）大型分布式架构演进过程
- 4）构建分布式架构的最重要因素

  - （1）CDN加速静态文件访问
  - （2）分布式存储
  - （3）分布式搜索引擎
  - （4）应用发布与监控
  - （5）系统动态规划

- 5）分布式架构设计原则

  - （1）主流架构模型-SOA架构和微服务架构
  - （2）领域驱动设计及业务驱动划分
  - （3）分布式架构的基础理论CAP、BASE以及其应用
  - （4）什么是分布式架构下的高可用设计？
  - （5）分布式架构下的可伸缩设计
  - （6）构建高性能的分布式架构

### 3.3 分布式架构基础

- 1）由简入繁，从网络通信探究分布式通信的原理
- 2）基于消息方式的系统间通信
- 3）理解通信协议传输过程中的序列化和反序列化机制

### 3.4 分布式通信框架

- 1）IO基础篇

  - （1）JavaIO演进之路

- 2）RPC通信技术

  - （1）传统RPC技术在大型分布式架构下面临的问题
  - （2）分布式架构下的RPC解决方案
  - （3）手写一个分布式RPC通信框架

- 3）高性能NIO框架Netty

  - （1）Netty初体验

    - <1> Netty与NIO之前世今生
    - <2> 基于Netty手写Tomcat
    - <3> 基于Netty重构RPC框架

  - （2）Netty实战

## 4 分布式与微服务

### 4.1 漫谈微服务架构

- 0）微服务的由来
- 1）SOA架构和微服务架构之间的区别和联系
- 2）如何设计微服务及其设计原则
- 3）Spring Boot流行的原因及解决的问题
- 4）什么是Spring Cloud以及为什么选择Spring Cloud
- 5）基于全局分析Spring Cloud各个组件所解决的问题

### 4.2 Spring Boot

- 1）Spring Boot与微服务之间的关系
- 2）Spring Boot热部署实战
- 3）核心组件之Starter、Actuator、Auto-Configuration、CLI
- 4）Spring Boot集成MyBatis实现多数据源
- 5）Spring Boot集成Dubbo
- 6）Spring Boot集成Redis
- 7）Spring Boot集成Swagger构建API管理及测试体系
- 8）Spring Boot实现多环境配置动态解析

### 4.3 Spring Cloud Netflix

- 1）Eureka注册中心
- 2）Ribbon集成REST实现负载均衡
- 3）Feign声明式服务调用
- 4）Hystrix服务熔断降级方式
- 5）Zuul实现微服务网关
- 6）Config分布式统一配置中心
- 7）Sleuth调用链路跟踪
- 8）基于Hystrix实现接口降级
- 9）Spring Boot集成Spring Cloud实现统一整合方案

### 4.4 Spring Cloud Alibaba

- 1）NACOS

  - （1）动态配置服务
  - （2）服务发现及管理
  - （3）动态DNS服务

- 2）Sentinel服务熔断及限流

  - （1）限流及熔断的场景
  - （2）Sentinel对于限流及熔断的支持及与原理分析
  - （3）Spring Boot集成Sentinel

- 3）Seata高性能微服务分布式事务解决方案

  - （1）分布式事务的产生背景及理论指导
  - （2）Seata如何实现分布式事务及实现与原理分析
  - （3）Dubbo如何集成Seata实现分布式事务

- 4）Spring Boot + Dubbo实现微服务

  - （1）Dubbo管理中心及监控平台安装部署
  - （2）Dubbo分布式服务模块划分(领域驱动)
  - （3）基于Dubbo的分布式系统架构
  - （4）Dubbo负载均衡策略分析
  - （5）Dubbo服务调试之服务只订阅及只订阅注册配置
  - （6）Dubbo服务接口的设计原则
  - （7）基于Dubbo构建大型分布式电商平台
  - （8）Dubbo容错机制及高扩展性分析

- 5）Zookeeper分布式协调服务

  - （1）从0开始搭建3个节点的Zookeeper集群
  - （2）深入分析Zookeeper在disconf配置中心的应用
  - （3）基于Zookeeper的分布式锁解决方案
  - （4）Zookeeper Watcher核心机制深入源码分析
  - （5）Zookeeper集群升级、迁移
  - （6）基于Zookeeper实现分布式服务器动态上下线感知
  - （7）深入分析Zookeeper Zab协议及选举机制源码
  - （8）手写实现带注册中心的RPC框架

- 6）RocketMQ

  - （1）RocketMQ整体认知、概念模型
  - （2）核心配置参数讲解、主从同步机制分析
  - （3）消息同步发送机制分析、Netty通信机制分析
  - （4）消息的延迟投递，自定义投递
  - （5）核心配置参数优化、消费端集群、广播模式
  - （6）消息的同步刷盘与异步刷盘机制、同步复制与异步复制机制

### 4.5 微服务监控及分布式架构下的应用实战

- 1）分布式实战解决方案

  - （1）分布式全局ID生成方案
  - （2）Session跨域共享及SSO解决方案
  - （3）分布式事务解决方案
  - （4）高并发下的服务降级、限流
  - （5）基于分布式架构下分布式锁的解决方案
  - （6）分布式架构下实现分布式定时调度

- 2）ElasticSearch分布式搜索引擎

  - （1）分布式搜索引擎背景
  - （2）ElasticSearch中的基本概念
  - （3）ElasticSearch Java API常用操作
  - （4）ElasticSearch高级查询
  - （5）ElasticSearch与Spring Boot整合

- 3）ELK分布式日志监控

  - （1）ELK应用背景、基本思路及原理
  - （2）Logstash原理
  - （3）Kibana原理
  - （4）ELK的常用部署方案

### 4.6 ServiceMesh

- 1）ServiceMesh功能原理
- 2）ServiceMesh开源工具
- 3）ServiceMesh服务应用

## 5 分布式与中间件

### 5.1 分布式缓存技术

- 1）Redis

  - （1）Redis的数据结构分析
  - （2）Redis主从复制原理及无磁盘复制分析
  - （3）Redis管道模式详解
  - （4）Redis缓存与数据库一致性问题解决方案
  - （5）基于Redis实现分布式锁
  - （6）Redis中AOF和RDB持久化策略的原理
  - （7）Redis读写分离架构
  - （8）Redis哨兵架构及数据丢失问题
  - （9）Redis Cluster数据分布算法之Hash Slot
  - （10）Redis使用常见问题及性能优化思路
  - （11）Redis高可用及可伸缩架构
  - （12）缓存击穿、缓存雪崩预防策略
  - （13）Redis批量查询优化
  - （14）Redis高性能集群之Twemproxy or codis

- 2）MongoDB

  - （1）MongoDB应用场景及实现原理
  - （2）MongoDB常用命令及配置
  - （3）基于MongoDB手写ORM框架
  - （4）基于MongoDB GirdFS实现一个分布式网盘
  - （5）MongoDB高可用实战及V4.0新特性

### 5.2 分布式消息中间件

- 1）ActiveMQ

  - （1）消息中间件在分布式架构中的应用
  - （2）ActiveMQ高可用集群企业级部署方案
  - （3）ActiveMQ P2P及PUB/SUB模型
  - （4）ActiveMQ消息确认及重发策略
  - （5）ActiveMQ基于Spring完成分布式消息队列

- 2）RabbitMQ

  - （1）初步认识RabbitMQ及高可用集群部署
  - （2）详解RabbitMQ消息机制及主题消息分发
  - （3）RabbitMQ消息路由机制分析
  - （4）RabbitMQ消息确认机制

- 3）Kafka

  - （1）Kafka基于Zookeeper搭建高可用集群
  - （2）Kafka消息处理过程剖析
  - （3）Java客户端实现Kafka生产者与消费者实例
  - （4）Kafka的副本机制及选举原理剖析
  - （5）基于Kafka实现应用日志实时上报统计分析

### 5.3 数据库分库分表

- 1）MySQL主从复制及读写分离
- 2）MySQL+KeepAlived实现双主高可用方案时间
- 3）MySQL高兴能解决方案之分库分表
- 4）数据库中间件初识MyCat
- 5）基于MyCat实现MySQL数据库读写分离
- 6）基于MyCat实战之数据库切分策略剖析
- 7）MyCat全局表、ER表、分片策略分析

### 5.4 ShardingSphere

- 1）Sharding-JDBC与MyCat对比
- 2）Sharding-JDBC架构与核心概念
- 3）Spring Boot集成Sharding-JDBC实战
- 4）Sharding-JDBC分库分表策略解析
- 5）Sharding-JDBC原理分析

### 5.5 Elastic Job

- 1）Quartz体系结构及API
- 2）Quartz与Spring Boot集成
- 3）Quartz源码解析及工作原理
- 4）Quartz集群及协调原理
- 5）Elastic-Job架构及核心概念
- 6）Elastic-Job配置使用
- 7）Elastic-Job运行原理
- 8）Elastic-Job运维监控

### 5.6 Nginx

- 1）基于OpenResty部署应用层Nginx以及Nginx+Lua实践
- 2）Nginx反向代理服务器及负载均衡服务配置
- 3）利用Nginx+KeepAlived实践Nginx高可用方案
- 4）基于Nginx实现访问控制、连接限制
- 5）Nginx动静分离实战
- 6）Nginx Location、Rewrite等语法配置及原理分析
- 7）Nginx提供HTTPS服务
- 8）基于Nginx+Lua完成访问流量实时上报Kafka实战

## 6 架构师审美观

### 6.1 Spring 源码分析

- 1）Spring核心原理篇

  - 1）Spring框架的前世今生与系统架构
  - 2）Spring源码版本升级命名规则
  - 3）基于Gradle的Spring源码构建技巧
  - 4）一步一步手绘Spring IOC运行时序图
  - 5）一步一步手绘Spring DI运行时序图
  - 6）一步一步手绘Spring AOP运行时序图
  - 7）一步一步手绘Spring MVC运行时序图

- 2）Spring手写实战篇

  - 1）用300行代码手写提炼Spring的核心原理
  - 2）用30个类高仿真浓缩手写Spring框架V2.0

- 3）Spring数据访问篇

  - 1）Spring事务传播原理及数据库事务操作原理
  - 2）基于Spring JDBC手写定制自己的ORM框架

- 4）Spring案例分享篇

  - 1）Spring5新特性
  - 2）BAT经典高频面试题

### 6.2 My Batis源码分析

- 1）MyBatis原理篇

  - （1）MyBatis应用分析与最佳实践
  - （2）MyBatis体系结构与工作原理
  - （3）MyBatis源码解析

- 2）MyBatis实用篇

  - （1）Spring集成MyBatis
  - （2）手写MyBatis

### 6.3 Dubbo源码分析

- 1）Dubbo内核剖析
- 2）Dubbo的SPI机制及adaptive原理
- 3）Dubbo服务发布原理剖析
- 4）Dubbo如何基于Zookeeper实现服务注册
- 5）Dubbo集群容错设计
- 6）Dubbo LoadBalance负载均衡原理
- 7）Dubbo服务降级原理剖析

### 6.4 Netty源码分析

- 1）Netty高性能之道
- 2）解开Bootstrap的神秘面纱
- 3）大名鼎鼎的EventLoop
- 4）Netty大动脉Pipeline
- 5）Promise与Future双子星的秘密
- 6）Netty内存分配与ByteBuf
- 7）Netty编解码的艺术
- 8）Netty中的设计模式

### 6.5 Zookeeper源码分析

- 1）Leader选举源码分析
- 2）Watcher机制源码分析

### 6.6 Active MQ源码分析

## 7 架构师修养与软技能

### 7.1 性能调优

- 1）Tomcat调优篇

  - （1）How it works？探查Tomcat的运行机制及框架
  - （2）分析Tomcat线程模型
  - （3）Tomcat系统参数认识及调优
  - （4）基准测试技巧

- 2）MySQL调优篇

  - （1）深度剖析MySQL的B+树索引机制
  - （2）了解存储引擎、从SQL执行学习执行计划
  - （3）深入学习InnoDB引擎特性之锁、MVCC机制
  - （4）MySQL集群搭建、高可用方案
  - （5）数据拯救、数据库表设计、参数配置

- 3）JVM调优篇

  - （1）知其然、知其所以然
  - （2）什么是JVM内存模型JMM？
  - （3）各垃圾回收期使用场景
  - （4）理解GC日志、从日志看端倪
  - （5）实战MAT分析dump文件

- 4）理解性能优化

  - （1）性能基准
  - （2）性能优化到底是什么
  - （3）衡量维度

### 7.2 数据结构篇

- （1）线性表
- （2）栈与队列
- （3）树
- （4）图
- （5）散列表

### 7.3 算法分析与设计

- （1）算法复杂度
- （2）贪心算法
- （3）分治算法
- （4）动态规划算法
- （5）回溯法
- （6）分支定界法
- （7）字符串匹配算法
- （8）排序算法

### 7.3 UML建模

- 1）常用建模工具
- 2）用例建模
- 3）类建模
- 4）系统交互建模

### 7.4 技术文档编写

- 1）需求文档编写技巧
- 2）Java开发规范文档编写技巧
- 3）数据库设计文档编写技巧

### 7.5 面试技巧

- 1）如何写出一份漂亮的简历
- 2）如何高效准备面试
- 3）如何优雅谈薪资
- 4）如何精准跳槽
- 5）辞职的正确姿势
- 6）如何规划自己的职业发展

### 7.6 中英文档阅读能力

