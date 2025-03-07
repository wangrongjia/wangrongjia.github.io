---
link: https://github.com/cdk8s/cdk8s-team-style/blob/master/full-stack/4-backend.md
site: GitHub
excerpt: 寻找志同道合的人，引发自身的思考. Contribute to cdk8s/cdk8s-team-style development by
  creating an account on GitHub.
twitter: https://twitter.com/@github
slurped: 2025-02-08T13:08
title: cdk8s-team-style/full-stack/4-backend.md at master · cdk8s/cdk8s-team-style
---

## 【从开公司到开发全平台产品】4.后端开发的思考、实践-UPUPMO

[](https://github.com/cdk8s/cdk8s-team-style/blob/master/full-stack/4-backend.md#%E4%BB%8E%E5%BC%80%E5%85%AC%E5%8F%B8%E5%88%B0%E5%BC%80%E5%8F%91%E5%85%A8%E5%B9%B3%E5%8F%B0%E4%BA%A7%E5%93%814%E5%90%8E%E7%AB%AF%E5%BC%80%E5%8F%91%E7%9A%84%E6%80%9D%E8%80%83%E5%AE%9E%E8%B7%B5-upupmo)

- 本文视频版已发到 Bilibili：[https://www.bilibili.com/video/BV1Qa411L72z/](https://www.bilibili.com/video/BV1Qa411L72z/)
- 大家好，我是 UPUPMO.com 的作者 Meek，欢迎观看《从开公司到开发全平台产品》系列。
- 希望通过该系列可以帮助新手，快速了解全栈软件产品的一些思路、应用。
- 如果你心中有创意，也想独立开发产品，可以在视频或文章的最后，查看联系信息加我好友。
- 本期我们讲解第四章：《后端开发的思考、实践》
- 我们将会从以下4个小节进行探讨：

```
1. 后端行业中常见争议
2. 后端企业级架构标准
3. 各类数据库应用场景
4. 如何挑选技术、框架
```

- 本期文字版已发布到 GitHub，欢迎观看：
- [https://github.com/cdk8s/cdk8s-team-style/blob/master/full-stack/4-backend.md](https://github.com/cdk8s/cdk8s-team-style/blob/master/full-stack/4-backend.md)

---

## 1. 后端行业中常见争议

[](https://github.com/cdk8s/cdk8s-team-style/blob/master/full-stack/4-backend.md#1-%E5%90%8E%E7%AB%AF%E8%A1%8C%E4%B8%9A%E4%B8%AD%E5%B8%B8%E8%A7%81%E4%BA%89%E8%AE%AE)

#### 1.1 行业中的普遍争议

[](https://github.com/cdk8s/cdk8s-team-style/blob/master/full-stack/4-backend.md#11-%E8%A1%8C%E4%B8%9A%E4%B8%AD%E7%9A%84%E6%99%AE%E9%81%8D%E4%BA%89%E8%AE%AE)

[![img](https://camo.githubusercontent.com/9677130d79824d66f227adfee9ba3e9f0f12cf04603322291e8e1f09b31f7e69/68747470733a2f2f63646e2e7570746d722e636f6d2f757075706d6f2d61727469636c652f323032322f332d73797374656d2d6f732e6a706567)](https://camo.githubusercontent.com/9677130d79824d66f227adfee9ba3e9f0f12cf04603322291e8e1f09b31f7e69/68747470733a2f2f63646e2e7570746d722e636f6d2f757075706d6f2d61727469636c652f323032322f332d73797374656d2d6f732e6a706567)

1. Windows、macOS、Linux 哪个更适合程序员日常?（暂停 3 秒，大家想一下自己心中的答案）

```
其实这个问题是不够严谨的，理论上应该说哪种程序员? 是嵌入式? 后端? 安全? 驱动? 等等，但是如果这样的问，该争议就没意思了。
这里我们先假设是可以用 TNT 软件，不讨论道德洁癖，并且假设的是国内环境，因为国内 Windows 流氓软件确实很多。
我说下我个人答案：我喜欢 macOS。综合看 macOS 和 Windows + WSL 可以干的事情都差不多，但是 macOS 是一个生态，没有割裂性，整体沉浸感更强，系统也更加稳定，真的是稳如狗的稳。
我还喜欢 macOS 大量的收费软件，它们都是有人维护、更新，我们可以经常跟进
缺点就是性价比不高，白苹果很贵。
至于 Linux，该是会用服务器的人终归把它当服务器，做桌面的话只能妥协国内那些必备软件体验，或者使用网页版、手机，割裂感太强。
同时 Linux 下的生活软件也是被更新最慢，所以只适合做服务器或者单纯只开发。
```

2. 程序员应该用哪个 IDE 或编辑器?

[![img](https://camo.githubusercontent.com/0fa8dbe06bdb7c494fb532f76024b20c19f77e45e2fbff215a792190dd4fde78/68747470733a2f2f63646e2e7570746d722e636f6d2f757075706d6f2d61727469636c652f323032322f4a6574427261696e732e706e67)](https://camo.githubusercontent.com/0fa8dbe06bdb7c494fb532f76024b20c19f77e45e2fbff215a792190dd4fde78/68747470733a2f2f63646e2e7570746d722e636f6d2f757075706d6f2d61727469636c652f323032322f4a6574427261696e732e706e67)

```
我的答案是：
这个问题也是不严谨的，应该是具体到哪种程序员
我主要是前后端开发，所以我是 JetBrains 的坚定支持者，它缺点是收费，并且需要大内存的电脑。
```

3. IDE 应该用浅色主题还是深色主题?

```
我的答案是：
这个我倒是有自己的一套健康理论
首先大多数程序员都是整天对着电脑的，需要一个防蓝光眼镜，一个屏幕挂灯，并且把系统改为夜览模式，此时看到系统会是偏黄色
在这种条件下对你的眼镜保护是最好的，此时屏幕亮度不会很高，用深色主题看起来不清晰，所以我觉得应该是浅色主题
```

4. 缩进是用 Tab 还是空格?

```
我的答案是：
一开始用 Java 习惯用 Tab，但是从开始写前端后，我偏向于应该让所有语言都是用空格。
```

5. 最好的注释就是代码本身?

```
我的答案是：
理想状态下应该是，但是实际情况下，需求各种各样，有的细节没有流程图、时序图根本说不清楚，所以我倾向于有注释，只是简单方法、简单单词的注释可以少写
```

#### 1.2 开发语言相关争议

[](https://github.com/cdk8s/cdk8s-team-style/blob/master/full-stack/4-backend.md#12-%E5%BC%80%E5%8F%91%E8%AF%AD%E8%A8%80%E7%9B%B8%E5%85%B3%E4%BA%89%E8%AE%AE)

6. 谁是世界上最好的开发语言?

```
我的答案是：
不存在的，没有哪种语言可以干任何场景的需求。
但是我喜欢静态语言，最好是类似 Rust 这种，可以在编译期就暴露出大多数错误的这种语言
```

7. Go 要取代 Java 吗?

```
在回答这个问题之前得先介绍 Pivotal：

2003 年，Rod Johnson 和同伴创建了 Interface 21
2008 年，改名为大家熟知的 SpringSource 并收购 Covalent 得到 Tomcat、Geronimo、Apache Axis
2008 年，SpringSource 收购 G2One 得到 Groovy、Grails
2009 年，SpringSource 收购 Hyperic
但是 2009 年 8 月，VMware 收购了 SpringSource
2009 年，SpringSource 收购 Cloud Foundry 平台
2010 年，SpringSource 收购 RabbitMQ、Redis、GemStone Data
2012 年，Rod Johnson 离开 
2012 年，EMC 又收购了 Pivotal Labs 公司；
2013 年，EMC、VMware、通用电气和收购来的 Pivotal Labs 公司重新组建了新的公司 Pivotal，此时 EMC 是控股股东
2015 年，戴尔又并购了 EMC，所以严格算此时是戴尔当家
2018 年，Pivotal 上市，但是后续股票不理想
2019 年，VMware 收购 Pivotal 变成的控股股东，然后把它从纽交所摘牌，开始主推 VMware Tanzu 生态（是 K8S 生态）
更多信息可以看：https://wikipedia.org/wiki/SpringSource

从 2003 年到 2019 年来，Spring 所代表的企业经历了好几次收购、被收购，所以我们可以看出来 Spring 所代表开源是需要大量钱、优秀的人才能堆出来。
还是我上一章节那句话：写代码就是写 Bug 过程，一定要有金主支撑不然很难维持。
Java 单体、大数据、以及过去十几年的旧体系，目前还是会继续存活，但是 Go 带来的云原生趋势越来越明显，而且也有大金主支撑。至于 Rust 还要再熬一下生态。
目前的世界因为 K8S 变了，所以我的结论就是：Go 会在未来代替 Java 成为最大主流，但是需要继续熬一下。

```

8. MySQL、PostgreSQL 之争

```
从性能和插件扩展性上看 PostgreSQL 更优秀。
但是，PostgreSQL 国内流行度不高，所以学习成本、维护成本就无法把控。
并且国内云厂商自研的分布式云数据库引擎协议，都是优先 MySQL，所以从长远看，用 MySQL 更有助于后续上云。
```

9. Java ORM 框架之争

```
Java ORM 框架主流是 JPA 和 MyBatis
我个人不反感 API 方式，但是对于复杂业务，我喜欢先在 Navicat 中进行书写、测试，
确定没问题之后，直接把 SQL 复制到 XML 中，所以我偏向 MyBatis
```

10. JDK 版本争论

```
从类型上可以分为：
OraceJDK
OpenJDK
Amazon Corretto
Alibaba Dragonwell
Tencent Kona
HUAWEI 毕昇
等等其他

从版本号上分主流有：
JDK 6
JDK 8
JDK 11
JDK 17

我个人试过：OraceJDK、OpenJDK、Amazon Corretto 的 JDK 8、JDK 11
都是对同一个后台多模块项目进行编译、接口压测 QPS，得到结果还是以 OraceJDK 8 为最佳或者说差异不大。
大家可以根据自己的需求做下压测，选择自己最适合的。
```

---

## 2. 后端企业级架构标准

[](https://github.com/cdk8s/cdk8s-team-style/blob/master/full-stack/4-backend.md#2-%E5%90%8E%E7%AB%AF%E4%BC%81%E4%B8%9A%E7%BA%A7%E6%9E%B6%E6%9E%84%E6%A0%87%E5%87%86)

[![img](https://camo.githubusercontent.com/33c750ddc0fce7215e02e24123d2550836e3a9af871c8845806c15b501984c06/68747470733a2f2f63646e2e7570746d722e636f6d2f757075706d6f2d61727469636c652f323032322f636e63662e706e67)](https://camo.githubusercontent.com/33c750ddc0fce7215e02e24123d2550836e3a9af871c8845806c15b501984c06/68747470733a2f2f63646e2e7570746d722e636f6d2f757075706d6f2d61727469636c652f323032322f636e63662e706e67)

- 立这个标准主要目的是：每当我学习一个新的后端语言、后端框架，我都会按照此功能需求进行调研
- 我主要是以业务驱动去思考使用的语言、框架
- 其中微服务需要的组件较多，放在第二部分

#### 2.1 基础标准

[](https://github.com/cdk8s/cdk8s-team-style/blob/master/full-stack/4-backend.md#21-%E5%9F%BA%E7%A1%80%E6%A0%87%E5%87%86)

```
IDE 代码补全、纠错支持
IDE 调试、重构支持
公网包管理、私服包管理
单元测试
文件上传、下载
多环境配置
性能分析工具
调试工具
事务管理
日志工具
Web 安全：SQL 注入、XSS、CSRF、SSRF、上传漏洞
缓存库：Redis、KeyDB
传统数据库：MySQL、PostgreSQL 等


调度工具
参数校验框架
持续集成、容器化
度量指标实时上报
静态资源配置
Excel、PDF 等文档工具
WebSocket、gRPC、MQ、MQTT
事件监听
拦截器、过滤器、监听器思维
参数解析器
返回值处理器
统一异常管理
国际化多语言



AOP 切面思维
单点登录
远程调试
流程引擎
规则引擎
异常分析：SQL异常、框架异常
搜索引擎：Elasticsearch、Solr、OpenSearch 等
列数据库：ClickHouse、HBase 等
时序库：Prometheus、M3DB、InfluxDB 等
图数据库：Neo4j、Dgraph 等
```

#### 2.2 微服务标准

[](https://github.com/cdk8s/cdk8s-team-style/blob/master/full-stack/4-backend.md#22-%E5%BE%AE%E6%9C%8D%E5%8A%A1%E6%A0%87%E5%87%86)

```
分布式 ID
分布式缓存
分布式锁
分布式事务
分布式调度
分布式日志
分布式消息

熔断、限流
注册中心
API 网关
配置管理（路由、限流动态配置）
链路追踪
gRPC
系统监控
度量指标监控
单点登录、认证、鉴权
A/B测试、灰度发布
```

---

## 3. 各类数据库应用场景

[](https://github.com/cdk8s/cdk8s-team-style/blob/master/full-stack/4-backend.md#3-%E5%90%84%E7%B1%BB%E6%95%B0%E6%8D%AE%E5%BA%93%E5%BA%94%E7%94%A8%E5%9C%BA%E6%99%AF)

[![img](https://camo.githubusercontent.com/55d62e2938e4960180febc1d9f90b4be39bbcedbca4ffc454351b72d49c48aaa/68747470733a2f2f63646e2e7570746d722e636f6d2f757075706d6f2d61727469636c652f323032322f6461746162617365732e706e67)](https://camo.githubusercontent.com/55d62e2938e4960180febc1d9f90b4be39bbcedbca4ffc454351b72d49c48aaa/68747470733a2f2f63646e2e7570746d722e636f6d2f757075706d6f2d61727469636c652f323032322f6461746162617365732e706e67)

```
传统数据库的范式要求既是缺点也是优点。
缺点就是大家都怪它不灵活，但是这同样是它优点，毕竟死板的东西跟容易被维护、控制。
我个人喜欢做事死板，但是也排斥不灵活的，主要还是看应用场景的合适原则
```

1. MySQL：传统数据库思维场景
2. Redis：内存存储场景
3. RabbitMQ：消息队列场景
4. Elasticsearch：全文检索、复杂搜索、可视化分析
5. ClickHouse：数据量大、批量写入，查询条件简单、列与列之间联系不大的场景
6. MongoDB：结构不确定，聚合查询，查询多
7. Neo4j：图类结构的场景，比如：社交关系、企业关系、多维关联分析、交通物流、推荐系统
8. Prometheus：物联网设备采集、各类监控数据采集等基于时间线的连续数据

---

```
可以从下面看出来，我基本都是围着 GitHub 转，可以说我最大老师就是 GitHub 本身，也推荐大家养成这个习惯
```

1. 查看官网文档编写情况
2. 查看 GitHub 的 star 数量，越高表示越流行
3. 查看 GitHub 的 Contributors 数量，以及主要参与者活跃
4. 查看 GitHub 的发布记录
5. 查看 GitHub 是否有资金赞助者否属于某些大企业
6. 针对某些你认为常用 API 在 GitHub 进行全文检索，查看使用它搜索到的项目数量
7. 在掘金、博客园、InfoQ、CSDN、51CTO 等社区搜索，查看活跃度
8. 对基础项目进行性能测试
9. 查看其框架搭建起来是否能尽可能多地满足我们前面的标准
10. 其他资料，比如：各大云厂商支持的架构、ThoughtWorks 的技术雷达、GitHub Octoverse、已出版书籍等等

---

## 下期预告

[](https://github.com/cdk8s/cdk8s-team-style/blob/master/full-stack/4-backend.md#%E4%B8%8B%E6%9C%9F%E9%A2%84%E5%91%8A)

- 下期我们将介绍《前端开发的思考、实践》，分别从以下 4 个方面进行讲解：

```
1. 前端企业级架构标准
2. 主流前端框架对比
3. 正在发展的云开发介绍
4. 我常用的前端框架介绍
```

## 最后

[](https://github.com/cdk8s/cdk8s-team-style/blob/master/full-stack/4-backend.md#%E6%9C%80%E5%90%8E)

- 如果你心中有创意，想自己开发产品，可以微信联系我。
- 如果你觉得视频、文章对你有帮助，欢迎点赞、收藏、转发。我们下期见。