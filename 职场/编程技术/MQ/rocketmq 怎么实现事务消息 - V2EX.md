---
link: https://www.v2ex.com/t/1109287
site: V2EX
date: 2025-02-06T11:42
excerpt: 程序员 - @ljzxloaf - 之前一直用的 qmq ，自带本地消息表，事务消息会与本地消息一起提交，对业务基本零侵入。看了下
  rocketmq 的事务消息示例发送消息https://github.com
twitter: https://twitter.com/@V2EX
slurped: 2025-02-06T17:24
title: rocketmq 怎么实现事务消息 - V2EX
---

# rocketmq 怎么实现事务消息

  [ljzxloaf](/member/ljzxloaf) · 5 小时 41 分钟前 · 738 次点击

之前一直用的 qmq ，自带本地消息表，事务消息会与本地消息一起提交，对业务基本零侵入。  
  
  
看了下 rocketmq 的事务消息示例  
  
发送消息  
  
[https://github.com/apache/rocketmq-spring/blob/1be808da74764128e404ae33cbf5e97c248aa207/rocketmq-spring-boot-samples/rocketmq-produce-demo/src/main/java/org/apache/rocketmq/samples/springboot/ProducerApplication.java#L209](https://github.com/apache/rocketmq-spring/blob/1be808da74764128e404ae33cbf5e97c248aa207/rocketmq-spring-boot-samples/rocketmq-produce-demo/src/main/java/org/apache/rocketmq/samples/springboot/ProducerApplication.java#L209)  
  
本地事务、checkState  
  
[https://github.com/apache/rocketmq-spring/blob/1be808da74764128e404ae33cbf5e97c248aa207/rocketmq-spring-boot-samples/rocketmq-produce-demo/src/main/java/org/apache/rocketmq/samples/springboot/ProducerApplication.java#L246](https://github.com/apache/rocketmq-spring/blob/1be808da74764128e404ae33cbf5e97c248aa207/rocketmq-spring-boot-samples/rocketmq-produce-demo/src/main/java/org/apache/rocketmq/samples/springboot/ProducerApplication.java#L246)  
  
这也太别扭了吧，分割业务逻辑不说，也要多写很多代码，甚至还要改造业务表。  
  
不知道是不是我使用的姿势不对，rmq 有点盛名之下其实难副的感觉？

第 1 条附言  ·  1 小时 6 分钟前

大家使用 rocketmq 难道不用考虑消息发送失败的情况吗...

第 2 条附言  ·  53 分钟前

FIX: "事务消息会与本地消息一起提交" => "事务消息会与本地事务一起提交"


4 条回复  **•**  2025-02-06 15:17:29 +08:00

|   |   |   |
|---|---|---|
|![EMMMMMMMMM](https://cdn.v2ex.com/gravatar/c6fc9e55d8bd673afa7d91e22f969a16?s=48&d=retro)||1<br><br>**[EMMMMMMMMM](/member/EMMMMMMMMM)**  <br><br>   4 小时 56 分钟前 via Android<br><br>你是去哪儿的？|

|   |   |   |
|---|---|---|
|![mark2025](https://cdn.v2ex.com/gravatar/0d54045890432a48c1bd1f605224190d?s=48&d=retro)||2<br><br>**[mark2025](/member/mark2025)**  <br><br>   4 小时 9 分钟前<br><br>如果数据库是 pgsql 可以考虑 pgmq （ [https://tembo-io.github.io/pgmq/）](https://tembo-io.github.io/pgmq/）) ，这是 pg 的一个插件，用 pg 来实现的轻量级消息队列。  <br>业务操作和队列消息可以共用事务，确保业务操作与消息的一致性。|

|   |   |   |
|---|---|---|
|![jorneyr](https://cdn.v2ex.com/gravatar/984c8da4e70f0f5323c155c7d67c5ad7?s=48&d=retro)||3<br><br>**[jorneyr](/member/jorneyr)**  <br><br>   3 小时 20 分钟前<br><br>RocketMQ 的分布式事务需要写代码判断事务是否提交，事务里的每个业务操作是否完成都需要调用方向 RocketMQ 确认的。|

|   |   |   |
|---|---|---|
|![securityCoding](https://cdn.v2ex.com/gravatar/d525abe274d89c3277be2acaefbd0941?s=48&d=retro)||4<br><br>**[securityCoding](/member/securityCoding)**  <br><br>   2 小时 6 分钟前<br><br>没理解为啥别扭，异构系统你要的事务不就是业务本身？|

