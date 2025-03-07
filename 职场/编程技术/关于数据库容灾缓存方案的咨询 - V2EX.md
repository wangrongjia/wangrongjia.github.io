---
link: https://www.v2ex.com/t/1098113
site: V2EX
date: 2024-12-17T10:36
excerpt: "程序员 - @seedhk - ## 数据库版本阿里云 RDS SQLSERVER## 需求需求是因为老项目的长 SQL
  实在是过于多了，几百行的 SQL 一找一个准，去优化 SQL 工作量非常大。导致生产环"
twitter: https://twitter.com/@V2EX
slurped: 2025-02-08T10:43
title: 关于数据库容灾缓存方案的咨询 - V2EX
---

这是一个创建于 53 天前的主题，其中的信息可能已经有所发展或是发生改变。

## 数据库版本

阿里云 RDS SQLSERVER

## 需求

需求是因为老项目的长 SQL 实在是过于多了，几百行的 SQL 一找一个准，去优化 SQL 工作量非常大。

导致生产环境数据库很不稳定，经常因为 SQL 引起数据库不可用导致被客户投诉罚钱，问了阿里云他们推荐高可用集群，但是阿里云高可用对于小企业来说实在是太贵了。迁移下云又需要比较专业的 DBA 来运维数据库，小企业老板估计也不会同意。

## 做了什么

已经做了这几步：

1. 使用了 DTS ，同步主库的数据到从库，基本上实现了读写分离；
    
2. 拆分了核心业务，但是核心业务仍然有访问数据库的需求，因此万一数据库不可用时，如何保证核心业务的正常运行，成为了一个大问题；
    

## 想做什么：

领导提了一个想法：能否通过在中间加一层缓存层的方式，比如 Redis ，核心业务的增删改查先走 Redis 。一段时间后落库，这样即使数据库挂了，只要能撑住 10 分钟数据库就能恢复。

## 其他方案：

将数据库和接口都进行拆分，拆成多服务，需要对应数据的，走接口进行查询调用

不知道有没有其他更好的方案，求大佬们指教，谢谢~

|   |   |   |
|---|---|---|
|![duuu](https://cdn.v2ex.com/gravatar/41a4613627e84bfe1fc1e5e1b78ce47a?s=48&d=retro)||1<br><br>**[duuu](https://www.v2ex.com/member/duuu)**      53 天前<br><br>那 Redis 挂了呢|

|   |   |   |
|---|---|---|
|![evan1](https://cdn.v2ex.com/gravatar/f24dff322fba89717868f9dd9bbb3e41?s=48&d=retro)||3<br><br>**[evan1](https://www.v2ex.com/member/evan1)**      53 天前   ![❤️](https://www.v2ex.com/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>我遇到的项目都是先加监控，定位慢 SQL 然后进行针对性的优化，比如加索引，分库分表之类的。<br><br>没有遇到过用 redis 做这种中间库的。|

|   |   |   |
|---|---|---|
|![bg7lgb](https://cdn.v2ex.com/gravatar/6bb03ff54ba18b49cb072d1521b78f57?s=48&d=retro)||4<br><br>**[bg7lgb](https://www.v2ex.com/member/bg7lgb)**      52 天前<br><br>数据库优化，从应用开始，而不是从数据库层面入手。<br><br>老老实实查日志，找慢 SQL 优化。|

|   |   |   |
|---|---|---|
|![bg7lgb](https://cdn.v2ex.com/gravatar/6bb03ff54ba18b49cb072d1521b78f57?s=48&d=retro)||5<br><br>**[bg7lgb](https://www.v2ex.com/member/bg7lgb)**      52 天前<br><br>Redis 做缓存，增加了技术的复杂性，故障节点也多了。<br><br>而且目前这个问题也不是用高可用版本就可以解决的。|

|   |   |   |
|---|---|---|
|![seedhk](https://cdn.v2ex.com/avatar/e2b1/4142/483358_normal.png?m=1734402939)||7<br><br>**[seedhk](https://www.v2ex.com/member/seedhk)**      52 天前<br><br>@[bg7lgb](https://www.v2ex.com/member/bg7lgb) 大佬说的是，这样加东西，只会增加复杂性和排查问题的难度，最根本还是得优化 SQL 。<br><br>有没有什么其他好一些的方案？ 因为 SQL 优化是一个很漫长的过程，其中还牵涉到很多老的业务逻辑，那些 SQL 和表我看过，给我的感觉是一天能改好一个都已经不错了。|

|   |   |   |
|---|---|---|
|![Varobjs](https://cdn.v2ex.com/avatar/3364/3773/388906_normal.png?m=1714096458)||8<br><br>**[Varobjs](https://www.v2ex.com/member/Varobjs)**      52 天前<br><br>redis 缓存有个项目叫 readyset ，可以兼容 mysql 协议，数据库连接可以直接改为 readyset 端口，默认 sql 都会直连数据库，可以在控制台指定 sql ，走内存|

|   |   |   |
|---|---|---|
|![SoulSleep](https://cdn.v2ex.com/avatar/758d/e329/139248_normal.png?m=1732668908)||9<br><br>**[SoulSleep](https://www.v2ex.com/member/SoulSleep)**      52 天前<br><br>@[evan1](https://www.v2ex.com/member/evan1) +1<br><br>不解决问题，要靠堆配置是最后的选择，又不舍得花钱，这不是既要又要吗？  <br>阿里云的 dts 使用场景主要是异构数据库，相同数据库直接开主从就好了....<br><br>再就是如果分析型 sql 过多可以考虑用列存数据库、可以考虑加读写分离。。。但是归根结底<br><br>必须要做的：  <br>精简在线业务库的单表大小（做做历史归档？）  <br>做慢 SQL 优化（加索引、改写法、做限流...)  <br>优化业务逻辑（如同步改异步）|

|   |   |   |
|---|---|---|
|![seedhk](https://cdn.v2ex.com/avatar/e2b1/4142/483358_normal.png?m=1734402939)||10<br><br>**[seedhk](https://www.v2ex.com/member/seedhk)**      52 天前<br><br>@[SoulSleep](https://www.v2ex.com/member/SoulSleep) 谢谢大佬的指导<br><br>1.公司买的是阿里云的 RDS sqlserver ，除了 DTS ，不支持其他方式做主从或者读写分离；  <br>2.精简在线业务库的单表大小、做慢 SQL 优化、优化业务逻辑 这些都有在做，也在拆分核心业务，但是数据库这一层始终没有非常好的办法解决。<br><br>列存数据库您具体指的是哪些？|

|   |   |   |
|---|---|---|
|![bg7lgb](https://cdn.v2ex.com/gravatar/6bb03ff54ba18b49cb072d1521b78f57?s=48&d=retro)||12<br><br>**[bg7lgb](https://www.v2ex.com/member/bg7lgb)**      52 天前<br><br>挂的时候是什么情况？系统响应慢导致服务不可用？还是直接崩掉了？<br><br>最直接的方法就是升级配置，先缓解一下，争取点时间来优化。|

|   |   |   |
|---|---|---|
|![goodryb](https://cdn.v2ex.com/avatar/5a60/ef6c/110971_normal.png?m=1711524398)||14<br><br>**[goodryb](https://www.v2ex.com/member/goodryb)**      52 天前<br><br>redis 本质是做缓存的（不乏一些开了持久化当数据库用），提升查询效率，正常写逻辑都是要直接写库<br><br>而且加缓存业务也得改，不如好好投入精力，优化 SQL ，短期来不及就先升级配置，后续改好了再奖降回去|

|   |   |   |
|---|---|---|
|![fatyoung](https://cdn.v2ex.com/gravatar/f4b019dbc49ce159e281baa44bc9f912?s=48&d=retro)||15<br><br>**[fatyoung](https://www.v2ex.com/member/fatyoung)**      52 天前<br><br>用 redis 做只读缓存应该可以分担很多数据库压力吧？看描述应该是数据量不大，只是 sql 执行时间长吧？|

|   |   |   |
|---|---|---|
|![adoal](https://cdn.v2ex.com/avatar/69c6/27fd/54059_normal.png?m=1389512292)||16<br><br>**[adoal](https://www.v2ex.com/member/adoal)**      52 天前<br><br>这种典型的传统信息化型应用的性能瓶颈问题，就不要指望能直接套互联网基础设施来速成了。|

|   |   |   |
|---|---|---|
|![seedhk](https://cdn.v2ex.com/avatar/e2b1/4142/483358_normal.png?m=1734402939)||17<br><br>**[seedhk](https://www.v2ex.com/member/seedhk)**      52 天前<br><br>@[bg7lgb](https://www.v2ex.com/member/bg7lgb) 最常见的情况就是因为 SQL 太复杂，表数据量又太大，引起数据库 CPU 过高导致数据库服务不可用，一般重启就能解决，但是也要将近 10 分钟时间。配置目前是 16C 32G 次高，在网上就是顶配 16C 64G 。业务压力点是夏天，时间大概有 2-4 个月。|

|   |   |   |
|---|---|---|
|![seedhk](https://cdn.v2ex.com/avatar/e2b1/4142/483358_normal.png?m=1734402939)||18<br><br>**[seedhk](https://www.v2ex.com/member/seedhk)**      52 天前<br><br>@[cccb](https://www.v2ex.com/member/cccb) 谢谢，我看一下  <br>@[goodryb](https://www.v2ex.com/member/goodryb) #14 正常流程肯定是当做读的缓存来用，就是考虑数据库挂的了情况下，如何解决的问题  <br>@[fatyoung](https://www.v2ex.com/member/fatyoung) #15 最大的几张表已经过亿了，做了数据库拆分，在太复杂 SQL 的情况下，一张表即使只有 1 2KW 的数据，查询也是有风险的  <br>@[adoal](https://www.v2ex.com/member/adoal) #16 请问有什么好的方案吗？ 谢谢|

|   |   |   |
|---|---|---|
|![gostair](https://cdn.v2ex.com/avatar/cd20/39de/500411_normal.png?m=1651130376)||19<br><br>**[gostair](https://www.v2ex.com/member/gostair)**      52 天前<br><br>redis 增删改查,定期同步到 db,在游戏业务服务器上,是比较常见的方案.  <br>但这种方案,仅针对单条记录的线性的增删改查.<br><br>但如果复杂业务复杂 sql,比如涉及跨表查询,比如 事务性的多表修改,加缓存层 实现起来也比较麻烦吧? 何况还得考虑并发等情况.  <br>具体还得结合你的业务场景,看起来是复杂 sql,目测不适合.|

|   |   |   |
|---|---|---|
|![blackeeper](https://cdn.v2ex.com/avatar/c0e6/6e73/60003_normal.png?m=1728975544)||21<br><br>**[blackeeper](https://www.v2ex.com/member/blackeeper)**      52 天前<br><br>感觉你需要的是一个网关，对流量进行拦截，限流，限频。从而服务降级，来保证数据库不崩溃。  <br>当你数据库慢的时候，前端不断的重试，刷新，加重数据库的卡死。|

|   |   |   |
|---|---|---|
|![mangodai](https://cdn.v2ex.com/avatar/f7c5/3f16/378325_normal.png?m=1547819570)||22<br><br>**[mangodai](https://www.v2ex.com/member/mangodai)**      52 天前<br><br>要看业务规模 和 架构。  <br>redis 确实做过库存扣件最后落 db 。  <br>infoq 写过快手等电商系统， 对于直播超大秒杀百万 qps 直接走 redis 。  <br>你们有这个业务场景，和维护 redis 库存的技术能力吗？|

|   |   |   |
|---|---|---|
|![0x663](https://cdn.v2ex.com/avatar/d479/e3ff/436405_normal.png?m=1680923774)||23<br><br>**[0x663](https://www.v2ex.com/member/0x663)**      52 天前<br><br>感觉和数据库容灾没啥关系，和你们项目的脏 SQL 关系更大。  <br>即使做了容灾，运行这些 SQL 还是会出现问题。|

|   |   |   |
|---|---|---|
|![bellx](https://cdn.v2ex.com/gravatar/9e175947eb3f3d411b73db991d6cc8be?s=48&d=retro)||24<br><br>**[bellx](https://www.v2ex.com/member/bellx)**      52 天前 via iPhone<br><br>如果核心业务也涉及复杂的查询，那怎么堆配置都是没用的，根本问题解决不了，还是得老老实实优化查询。|

|   |   |   |
|---|---|---|
|![ala2008](https://cdn.v2ex.com/gravatar/1180dc5117a3cdead26c10fed41ce710?s=48&d=retro)||25<br><br>**[ala2008](https://www.v2ex.com/member/ala2008)**      52 天前<br><br>1 、缓存肯定要加的，你说的 sql 复杂，估计查询也慢  <br>2 、阿里云应该直接支持配置从库啊，不用自己搞  <br>3 、sql 优化吧|

|   |   |   |
|---|---|---|
|![seedhk](https://cdn.v2ex.com/avatar/e2b1/4142/483358_normal.png?m=1734402939)||26<br><br>**[seedhk](https://www.v2ex.com/member/seedhk)**      52 天前<br><br>@[blackeeper](https://www.v2ex.com/member/blackeeper) #21 是这样的，越是不可用的时候，用户越会不断重试刷新，因为解决这类问题，不是一套工具或者一个方案能解决的。相关的熔断限流都有，现在想解决的是数据库挂了的问题；  <br>@[mangodai](https://www.v2ex.com/member/mangodai) #22 有这个能力就不会问这个问题了 哈哈哈  <br>@[0x663](https://www.v2ex.com/member/0x663) #23 根本问题就在大 SQL ，但是远水解不了近渴，得先想数据库挂了如何处理的问题  <br>@[bellx](https://www.v2ex.com/member/bellx) #24 核心业务少，SQL 优化耗费的时间和精力都能接受  <br>@[ala2008](https://www.v2ex.com/member/ala2008) #25 好像 sqlserver 不支持从库|

|   |   |   |
|---|---|---|
|![heiya](https://cdn.v2ex.com/gravatar/2aad244ded1ccba436ae4bceb62744ee?s=48&d=retro)||28<br><br>**[heiya](https://www.v2ex.com/member/heiya)**      52 天前<br><br>SQL 太复杂，一查几百行，表数据量又太大 导致大量的慢 sql ，是不是瓶颈在于查询而不是新增和修改？这样的话我感觉用 Redis 替代 Mysql 查询不合适，原因是即使前台没有显式的调用这些复杂 sql ，在相关业务进行新增和修改时也调用复杂 sql 同步到 Redis ；如果说不调用 sql 直接将数据存到 Redis ，那能不能确定由复杂 sql 组成的数据可以通过简单的 Redis 命令重新组成，我感觉挺困难的；还有数据量太多的话假设 Redis 挂掉，AOF 恢复是需要时间的，在这段时间内服务不可用；综上，我感觉 Redis 不合适。 解决办法根据描述我感觉：1.针对那些很复杂、数据量又特别多导致慢 sql 的表，将这数据同步到 ES 的一个索引中，组成一个大宽表，所有有关的复杂查询全走 ES 2.每次新增或修改时使用消息队列同步到 ES ，不能直接同步（或者现在有一些同步组件可以用） 3.如果有很多复杂查询但彼此不相关就需要多个索引了 4. 如果条件允许的话针对这些复杂的查询单独拆出来组成查询服务 5.分库分表还是有必要搞的，不过根据我的经验用过 Sharding 和 Mycat ，复杂的 sql 还是歇菜 6. 优化还得继续，慢 sql 报警不知道有没有 7.业务上能不能限制一下查询条件，比如起始时间什么的 8.有没有数据冷热分离的可能性？ 9.据说 PG 很强，但我没有用过，得试试|

|   |   |   |
|---|---|---|
|![z1829909](https://cdn.v2ex.com/gravatar/347d6ba181bf07a512c0542c5fb57c56?s=48&d=retro)||29<br><br>**[z1829909](https://www.v2ex.com/member/z1829909)**      52 天前 via Android<br><br>定期捞慢 sql ，然后拆分优化或者跳过。既然你们钱不够，那就靠人力解决。  <br>不是很赞同直接引入 redis ，可以分析出慢的地方，sql 优化成本很高的时候，针对这一部分做一些缓存。sql 虽然几百行，但是多花一些时间，逐步分析，测试到位问题不大。|

|   |   |   |
|---|---|---|
|![seedhk](https://cdn.v2ex.com/avatar/e2b1/4142/483358_normal.png?m=1734402939)||30<br><br>**[seedhk](https://www.v2ex.com/member/seedhk)**      52 天前<br><br>@[ala2008](https://www.v2ex.com/member/ala2008) 这个真迁不了 哈哈哈 工作量太大了  <br>@[heiya](https://www.v2ex.com/member/heiya) #28 谢谢大佬的回复，原先的方案确实不合适，我已经否了，现在在考虑新的方案，主要是解决如何避免数据库挂了，以及如果数据库挂了如何保证业务可用的问题，针对您说的这几点我概括一下，您看我说的对不对<br><br>1. 如果是将大数据量的表同步到 ES ，那如何解决关联查询的问题？ 还是说将关联查询的结果直接同步到 ES ？<br><br>2.阿里云的 rds sqserver 好像不支持从库，只能通过 DTS 同步。<br><br>3.索引是肯定有的，但是数据量太大，优化的工作量也不小，目前同步在做；<br><br>4.将核心业务迁出来，包括代码和数据库，避免影响到核心业务。<br><br>5. 分库分表暂时没有<br><br>6. 慢 SQL ，大 SQL 的报警都有，但是优化难度很大<br><br>7. 业务上的限制条件也是有的<br><br>8. 问了阿里云客服，除了买高可用和 DTS ，没有其他方案，自己做了部分冷数据的备份，但也仅仅是备份<br><br>9. 更换数据库成本太高了，而且领导层不一定支持，我综合一下方案往上提|

|   |   |   |
|---|---|---|
|![seedhk](https://cdn.v2ex.com/avatar/e2b1/4142/483358_normal.png?m=1734402939)||31<br><br>**[seedhk](https://www.v2ex.com/member/seedhk)**      52 天前<br><br>@[z1829909](https://www.v2ex.com/member/z1829909) 人力更不够(笑哭)，而且 SQL 强关联业务，又不可能扔了业务需求完全不做来改 SQL 。|

|   |   |   |
|---|---|---|
|![z1829909](https://cdn.v2ex.com/gravatar/347d6ba181bf07a512c0542c5fb57c56?s=48&d=retro)||32<br><br>**[z1829909](https://www.v2ex.com/member/z1829909)**      52 天前 via Android<br><br>@[seedhk](https://www.v2ex.com/member/seedhk) 或者组里安排一个人专职优化 sql ，或者轮岗，每人定期来一波精神折磨 233|

|   |   |   |
|---|---|---|
|![opengps](https://cdn.v2ex.com/avatar/1e8a/4d9b/250842_normal.png?m=1722219513)||33<br><br>**[opengps](https://www.v2ex.com/member/opengps)**      52 天前<br><br>复杂 sql 本身就是业务设计时候应该避免的|

|   |   |   |
|---|---|---|
|![Atoony](https://cdn.v2ex.com/avatar/e370/fb62/499558_normal.png?m=1676453708)||34<br><br>**[Atoony](https://www.v2ex.com/member/Atoony)**      52 天前<br><br>可以试试让 AI 优化 SQL ，说不定有奇效|

|   |   |   |
|---|---|---|
|![blackeeper](https://cdn.v2ex.com/avatar/c0e6/6e73/60003_normal.png?m=1728975544)||36<br><br>**[blackeeper](https://www.v2ex.com/member/blackeeper)**      52 天前<br><br>都已经确定是数据库的问题了，那就从数据库优化着手。  <br>1,买几个虚拟机，整多个只读实例，卡死一个，不影响全局  <br>2,优化数据库服务器的性能，换 SSD ，32G 内存太小，建议加大内存，配置数据库 cache 大小  <br>3,排查优化慢 sql ，增加相关索引  <br>4,把旧的数据归档，很多 sql 每次几亿的全表扫描是很消耗资源的。|

|   |   |   |
|---|---|---|
|![heiya](https://cdn.v2ex.com/gravatar/2aad244ded1ccba436ae4bceb62744ee?s=48&d=retro)||39<br><br>**[heiya](https://www.v2ex.com/member/heiya)**      52 天前<br><br>@[seedhk](https://www.v2ex.com/member/seedhk)<br><br>1.这个需要你们去分析。可以将关联查询出来的数据结果集作为一个大宽表同步到 ES 的索引中，这个大宽表可能有很多字段；也可以在后端业务逻辑中将需要的条件提前准备好了直接传递给 ES （如果被 jion 的表查询很快的话）；还有一种是 ES 的索引间关联查询也可以。  <br>2.有一个数据同步中间件 datax ，可以将 Mysql 的表数据同步到各种其他数据库。  <br>4.我感觉是哪个工作量相对小就将哪一个迁出，目标就是避免影响到核心业务。  <br>10.还有一种查询是各种聚合查询，针对于各种大数据量下的 count 语句，那 ClickHouse 特别合适，不过使用他是有条件的，只有写入和查询的话可以使用。  <br>11.前端页面上点击查询一时半会返回不了就不要再发送相同请求了<br><br>整体上我感觉就是现在的 Mysql 满足不了复杂的查询业务，把整个服务拖垮了，并发量其实并不高。最要紧的是把 1 和 4 搞定，其他的 6,11 同步做。不过，这么一搞就把技术复杂度提上去了，新增了 ES 和消息。|

|   |   |   |
|---|---|---|
|![seedhk](https://cdn.v2ex.com/avatar/e2b1/4142/483358_normal.png?m=1734402939)||40<br><br>**[seedhk](https://www.v2ex.com/member/seedhk)**      52 天前<br><br>@[heiya](https://www.v2ex.com/member/heiya) #39 谢谢回复<br><br>1 、ES 关联查询不如数据库那么方便，如果将查询后的数据汇总到 ES ，又涉及到数据变动更新的问题，不管怎么做都很复杂  <br>2. 我是 RDS SQLSERVER WEB 版，目前来看只支持 DTS ，其他都不支持。|

|   |   |   |
|---|---|---|
|![LoNeZ](https://cdn.v2ex.com/gravatar/a02778e6eda9c91fa75b33f17c545962?s=48&d=retro)||42<br><br>**[LoNeZ](https://www.v2ex.com/member/LoNeZ)**      52 天前<br><br>要么改代码, 要么加机器...|

|   |   |   |
|---|---|---|
|![adoal](https://cdn.v2ex.com/avatar/69c6/27fd/54059_normal.png?m=1389512292)||44<br><br>**[adoal](https://www.v2ex.com/member/adoal)**      52 天前<br><br>你那些大 SQL 是什么类型的，事务型还是分析型，如果是前者，没啥好办法，只能硬着头皮一点一点改了。后者的话，可以考虑同步到数仓里做分析，但是结果可能不会跟事务库完全实时一致。|

|   |   |   |
|---|---|---|
|![adoal](https://cdn.v2ex.com/avatar/69c6/27fd/54059_normal.png?m=1389512292)||46<br><br>**[adoal](https://www.v2ex.com/member/adoal)**      52 天前<br><br>至于换数据库，千万不要幻想 PG 比 MSSQL 性能好……至于 MySQL 想都别想了。|

|   |   |   |
|---|---|---|
|![adoal](https://cdn.v2ex.com/avatar/69c6/27fd/54059_normal.png?m=1389512292)||47<br><br>**[adoal](https://www.v2ex.com/member/adoal)**      52 天前<br><br>@[heiya](https://www.v2ex.com/member/heiya) 人家用的 MSSQL 你讲 MySQL 满足不了复杂的查询业务……|

|   |   |   |
|---|---|---|
|![wxw752](https://cdn.v2ex.com/avatar/85cf/7db0/514601_normal.png?m=1731378287)||48<br><br>**[wxw752](https://www.v2ex.com/member/wxw752)**      52 天前<br><br>你这题我会，我们公司用到了大量各类阿里的云服务。<br><br>对于你们来说，不要动 SQL ，最好的解决方案确实是读写分离，但读不要再用 RDS 了，用 DTS 将主库的数据同步到 AnalyticDB 中，这个阿里云的数仓和 mysql 的语法完全一样，SQL 查询效率直接拉满，一行代码不改，JDBC 直接连 ADB 读就完事了。|

|   |   |   |
|---|---|---|
|![lvlongxiang199](https://cdn.v2ex.com/gravatar/996c63b8796b3153c859ac2625880c7e?s=48&d=retro)||49<br><br>**[lvlongxiang199](https://www.v2ex.com/member/lvlongxiang199)**      52 天前<br><br>复杂查询估计是 AP 类型的, 建议上 clickhouse/Doris<br><br>救急的话, 与其上 redis 不如考虑拆分实例, 核心服务读/写单独的实例, 通过 DTS 把数据同步到复杂 sql 读的实例, 这样开发的工作量小些|

|   |   |   |
|---|---|---|
|![wxw752](https://cdn.v2ex.com/avatar/85cf/7db0/514601_normal.png?m=1731378287)||50<br><br>**[wxw752](https://www.v2ex.com/member/wxw752)**      52 天前<br><br>@[wxw752](https://www.v2ex.com/member/wxw752) #48 至于 ES ，只有在需要全文检索这种特定场景的表才会存 ES 。<br><br>所有数据全部存入 ES ，对于你们现阶段绝对绝对不是一个可选项。|

|   |   |   |
|---|---|---|
|![mark2025](https://cdn.v2ex.com/gravatar/0d54045890432a48c1bd1f605224190d?s=48&d=retro)||52<br><br>**[mark2025](https://www.v2ex.com/member/mark2025)**      52 天前<br><br>自己购买服务器，存储上固态，放 IDC 机房。性能会比云高得多。|

|   |   |   |
|---|---|---|
|![seedhk](https://cdn.v2ex.com/avatar/e2b1/4142/483358_normal.png?m=1734402939)||53<br><br>**[seedhk](https://www.v2ex.com/member/seedhk)**      52 天前<br><br>@[adoal](https://www.v2ex.com/member/adoal) #44 是后者 @[lvlongxiang199](https://www.v2ex.com/member/lvlongxiang199) #49 。同时请问下二位大佬，clickhouse 我不太熟。翻了下文档好像 ck 对 join 的支持不太好？ 那我如果将部分大 SQL 涉及到的表 以关系型数据库的原表数据导入到 ck ，并在 ck 中进行 join 关联查询等是否可行？ 谢谢|

|   |   |   |
|---|---|---|
|![heiya](https://cdn.v2ex.com/gravatar/2aad244ded1ccba436ae4bceb62744ee?s=48&d=retro)||55<br><br>**[heiya](https://www.v2ex.com/member/heiya)**      52 天前<br><br>@[adoal](https://www.v2ex.com/member/adoal) 别盯着笔误挑毛病，我写成 abc 他那不还是不行？最烦你这种人，啥方案提供不了就知道挑别人毛病。你觉得你行就给人家一个方案，觉得我说的方案不行就指出哪里不行。逼逼赖赖显你有嘴了。|

|   |   |   |
|---|---|---|
|![adoal](https://cdn.v2ex.com/avatar/69c6/27fd/54059_normal.png?m=1389512292)||58<br><br>**[adoal](https://www.v2ex.com/member/adoal)**      52 天前<br><br>@[seedhk](https://www.v2ex.com/member/seedhk) Clickhouse 之类数仓的玩法是把复杂查询“预处理”生成宽表，这样查起来在宽表上就快了，所以，结果可能不会跟事务库完全实时一致，你要先想明白这是不是你要的目标。|

|   |   |   |
|---|---|---|
|![bitfly](https://cdn.v2ex.com/gravatar/60b3f5502957c45bfe539d50de7d3a4e?s=48&d=retro)||59<br><br>**[bitfly](https://www.v2ex.com/member/bitfly)**      52 天前 via Android   ![❤️](https://www.v2ex.com/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>我也遇到過這種問題  <br>用用了一个简单有效的极速无脑一把鑠的办法  <br>就是监控出最吃 CPU 的语句 可能查询超时那种<br><br>提前把他查出来存一表里 等用户来查询的时候 直接 select *from 就好了  <br>然后后台在不定期看数据时效性来自动跟新这个表就行了  <br>是不是很无脑|

|   |   |   |
|---|---|---|
|![seedhk](https://cdn.v2ex.com/avatar/e2b1/4142/483358_normal.png?m=1734402939)||60<br><br>**[seedhk](https://www.v2ex.com/member/seedhk)**      52 天前<br><br>@[adoal](https://www.v2ex.com/member/adoal) #58 这样也没 OK ，唯一的问题是如果数据发生变动了，那宽表的数据不是得跟着变|

|   |   |   |
|---|---|---|
|![heiya](https://cdn.v2ex.com/gravatar/2aad244ded1ccba436ae4bceb62744ee?s=48&d=retro)||62<br><br>**[heiya](https://www.v2ex.com/member/heiya)**      52 天前<br><br>@[seedhk](https://www.v2ex.com/member/seedhk)  <br>1.数据修改只能是通过待更新标记再重新同步。  <br>2.但假如你使用 OLAP 数据库，比如 ClickHouse ，就像我之前说过的要注意是否有时不时的数据更新操作，如果有则不推荐。因为更新操作会引起索引重建，严重影响性能。非要更新的话也得是批量更新，数据更新及时性会受影响。我们之前的业务比如广告埋点，发送短信等这些数据插入/查询的业务每天几个亿数据，做数据分析连表查询性能很高，美滋滋。|

|   |   |   |
|---|---|---|
|![lvlongxiang199](https://cdn.v2ex.com/gravatar/996c63b8796b3153c859ac2625880c7e?s=48&d=retro)||63<br><br>**[lvlongxiang199](https://www.v2ex.com/member/lvlongxiang199)**      52 天前<br><br>@[seedhk](https://www.v2ex.com/member/seedhk) 可行. 但 ck 没有 join reorder, 写 join sql 的时候得是大表在左, 小表在右, 否则性能比较差. Doris 优化器做的还可以, 也可以考虑 Doris|

|   |   |   |
|---|---|---|
|![bg7lgb](https://cdn.v2ex.com/gravatar/6bb03ff54ba18b49cb072d1521b78f57?s=48&d=retro)||64<br><br>**[bg7lgb](https://www.v2ex.com/member/bg7lgb)**      52 天前<br><br>没专职的 DBA ，难为 OP 了。<br><br>从最简单的做起：  <br>1 、升级服务器配置，加内存，提升数据块缓冲区大小；不知 MSSQL 这个怎么做。Oracle 这样做有奇效。硬盘搞 SSD ，阿里云用本地 SSD ，IOPS 提升不小。  <br>2 、分析慢 SQL ，慢 SQL 一般是多表 JOIN ，查询没利用到索引，导致全表扫描。先识别出来，加索引来提升效率，有奇效。  <br>3 、分表，计算结果缓存，读写分离。  <br>优化顺序 ：应用 -- 》数据库 --》系统架构<br><br>我的认知就这么多了|

|   |   |   |
|---|---|---|
|![bg7lgb](https://cdn.v2ex.com/gravatar/6bb03ff54ba18b49cb072d1521b78f57?s=48&d=retro)||65<br><br>**[bg7lgb](https://www.v2ex.com/member/bg7lgb)**      52 天前<br><br>大 SQL ，见过几千行的 SQL ，真佩服那哥们能写得出来，反正我是不行。<br><br>后来重写，几十行搞定，运行效率还高。|

|   |   |   |
|---|---|---|
|![mark2025](https://cdn.v2ex.com/gravatar/0d54045890432a48c1bd1f605224190d?s=48&d=retro)||66<br><br>**[mark2025](https://www.v2ex.com/member/mark2025)**      52 天前<br><br>没人没钱就让哥们你来解决？ 可以准备跑路了。|

|   |   |   |
|---|---|---|
|![rockyliang](https://cdn.v2ex.com/avatar/4494/fcd3/538191_normal.png?m=1728892759)||67<br><br>**[rockyliang](https://www.v2ex.com/member/rockyliang)**      52 天前<br><br>@[seedhk](https://www.v2ex.com/member/seedhk) #2 ，有个疑问，按照你们领导“先写 redis ，再落地数据库”的想法，怎么知道 redis 里的哪些数据需要落地数据库？通过读取 AOF 日志文件吗|

|   |   |   |
|---|---|---|
|![mark2025](https://cdn.v2ex.com/gravatar/0d54045890432a48c1bd1f605224190d?s=48&d=retro)||71<br><br>**[mark2025](https://www.v2ex.com/member/mark2025)**      52 天前<br><br>@[seedhk](https://www.v2ex.com/member/seedhk) 不建议 ES：  <br>1. ES 需要同步。如果数据源修改增加了字段，ES 还得折腾一番  <br>2. ES 运维成本相当高|

|   |   |   |
|---|---|---|
|![seedhk](https://cdn.v2ex.com/avatar/e2b1/4142/483358_normal.png?m=1734402939)||73<br><br>**[seedhk](https://www.v2ex.com/member/seedhk)**      52 天前<br><br>@[heiya](https://www.v2ex.com/member/heiya) #62 ，@lvlongxiang199 #63 明白了，谢谢大佬们  <br>@[bg7lgb](https://www.v2ex.com/member/bg7lgb) #64 谢谢，数据库这块我也不精通，优化 SQL 什么的没问题，再深入点就两眼一抹黑了，应用和架构层面我能做的都做了，现在就差数据库  <br>@[mark2025](https://www.v2ex.com/member/mark2025) #66 是的，Redis 这方案已经否了，最多拿 Redis 做个缓存，ES 做不了太复杂的聚合查询，也不适用  <br>@[rockyliang](https://www.v2ex.com/member/rockyliang) #67 原先项目是指定几个接口或者几张表的数据，都走 Redis<br><br>目前来看最适合的还是 OLAP 型数据库|

|   |   |   |
|---|---|---|
|![v2orz](https://cdn.v2ex.com/gravatar/0d1d0e728e7236e7e3778088541bba3e?s=48&d=retro)||75<br><br>**[v2orz](https://www.v2ex.com/member/v2orz)**      52 天前<br><br>加 redis 不太行，改动大工作量大，见效慢，经典的面试问题：缓存和数据库一致性<br><br>把 TOP3 or TOP5 的复杂查询针对性优化一下先缓解，然后通过 DTS 到 ck 或者 doris ，建成一个单独的 OLAP 库感觉比较合适（不太适合高并发场景，看你业务）|

|   |   |   |
|---|---|---|
|![dengtongcai](https://cdn.v2ex.com/avatar/e188/a689/203082_normal.png?m=1550727840)||76<br><br>**[dengtongcai](https://www.v2ex.com/member/dengtongcai)**      52 天前<br><br>短期：先加 RDS 配置，解决紧急投诉问题。  <br>长期：还得慢慢把 SQL 、业务逻辑优化了。  <br>不到万不得已不建议引入新的中间件，引入新的环节也是一种不可控和增加成本。|

|   |   |   |
|---|---|---|
|![Meld](https://cdn.v2ex.com/avatar/09b6/b5c7/668533_normal.png?m=1730968070)||77<br><br>**[Meld](https://www.v2ex.com/member/Meld)**      52 天前<br><br>一堆 Join 还是 doris 吧，CH 需要你对各个引擎以及业务数据库具体设计都要有很深的理解|

|   |   |   |
|---|---|---|
|![Meld](https://cdn.v2ex.com/avatar/09b6/b5c7/668533_normal.png?m=1730968070)||78<br><br>**[Meld](https://www.v2ex.com/member/Meld)**      52 天前<br><br>业务瓶颈在读，肯定要从读这侧下手吧，既然读写分离了，就把读的数据导入到适合业务场景的数据库里呗？|

|   |   |   |
|---|---|---|
|![zhoujinjing09](https://cdn.v2ex.com/gravatar/221979cf82b35d9e78f14679e374f742?s=48&d=retro)||79<br><br>**[zhoujinjing09](https://www.v2ex.com/member/zhoujinjing09)**      52 天前<br><br>据说 doris/starrocks 对 join 支持比较好，建议试一下。这东西都要试了才知道，建议先从简单的开始，AnalyticDB + 弹性扩容，如果不能满足你们需求再看看别的方案。复杂的 SQL 很多时候避免不了全表扫描，唯一解决方案就是用一个弹性的方案|

|   |   |   |
|---|---|---|
|![isSamle](https://cdn.v2ex.com/avatar/9846/15bf/527523_normal.png?m=1610411826)||81<br><br>**[isSamle](https://www.v2ex.com/member/isSamle)**      52 天前<br><br>目前的方案是读从 redis ，低频写的话正常写，高频写的话用消息队列慢慢消费|

|   |   |   |
|---|---|---|
|![fengpan567](https://cdn.v2ex.com/gravatar/1317aa48a9ab0f096fc00da732594817?s=48&d=retro)||82<br><br>**[fengpan567](https://www.v2ex.com/member/fengpan567)**      52 天前<br><br>扯犊子呢，缓存到 redis 碰到大 key 怎么办，为啥不优化 sql|

|   |   |   |
|---|---|---|
|![huBane](https://cdn.v2ex.com/avatar/3c43/a595/564493_normal.png?m=1681284627)||83<br><br>**[huBane](https://www.v2ex.com/member/huBane)**      52 天前<br><br>Redis 确实可行，老项目 sql 优化已经十分困难，我做过一个老项目优化就是中间做了一层 redis ，低频操作正常写库，高频查的走 redis 系统性能提升非常明显。|

|   |   |   |
|---|---|---|
|![datoujiejie221](https://cdn.v2ex.com/gravatar/f01dc0ad03e236002c50a98240a2bb14?s=48&d=retro)||85<br><br>**[datoujiejie221](https://www.v2ex.com/member/datoujiejie221)**      52 天前<br><br>我们用的 mysql ，开始也有这个问题，说一下我们的方案  <br>1 写了个监听 binlog 的服务，数据发生变化刷新 redis 。  <br>2 写了个脚本统计慢查询日志，针对频繁出现的 sql 进行优化，用了一个开源的工具 archery 去做可视化分析和 sql 优化。  <br>3 统计类的查询放到 doris 去做，效果提升明显，并且大部分 sql 都不用改。  <br>1 和 3 都用了 flink-cdc 的方案去做数据同步。|

|   |   |   |
|---|---|---|
|![netnr](https://cdn.v2ex.com/avatar/9bfd/9fda/426497_normal.png?m=1737784936)||87<br><br>**[netnr](https://www.v2ex.com/member/netnr)**      52 天前<br><br>OP 但凡搜一下也不会说 好像不支持从库  <br>感觉搞个从库是目前最优方案了|

|   |   |   |
|---|---|---|
|![wxw752](https://cdn.v2ex.com/avatar/85cf/7db0/514601_normal.png?m=1731378287)||88<br><br>**[wxw752](https://www.v2ex.com/member/wxw752)**      52 天前<br><br>@[mark2025](https://www.v2ex.com/member/mark2025) #84 肯定不能你百分之多少我百分之多少，然后 op 以此作为依据是否采用，这不成了小马过河了嘛。<br><br>在这里几十层楼都是集思广益，提供给 op 思路，让 op 去逐个尝试。|

|   |   |   |
|---|---|---|
|![spritecn](https://cdn.v2ex.com/gravatar/5bd942c8bc4a90af9ffa7f3576428154?s=48&d=retro)||89<br><br>**[spritecn](https://www.v2ex.com/member/spritecn)**      52 天前<br><br>阿里的集群,好像不贵..2*4 双节点版和 4*8 机器差不多一个价,并且现在送代理..并且读写分离完后,CPU 点用比之前还低,别问我怎么知道,还有上读写分离还是要看看代码怎么写,有些 save 马上就查的业务代码可能得改改|

|   |   |   |
|---|---|---|
|![lambdaq](https://cdn.v2ex.com/avatar/8553/adf9/10426_normal.png?m=1688377906)||91<br><br>**[lambdaq](https://www.v2ex.com/member/lambdaq)**      52 天前<br><br>读写分离为啥还会卡啊？前面推荐 clickhouse 的只能解决 olap 导致卡的问题，也就是只读的 sql 。<br><br>如果你又读又写，还锁表导致的卡，业务还复杂的一批，那没救了。混吃等死吧。谁碰谁倒霉|

|   |   |   |
|---|---|---|
|![dd102](https://cdn.v2ex.com/gravatar/8ecefddd6be5a6cbc54db060963276f4?s=48&d=retro)||92<br><br>**[dd102](https://www.v2ex.com/member/dd102)**      52 天前<br><br>@[seedhk](https://www.v2ex.com/member/seedhk) 阿里云 顶配 16C 64G 为啥配置这么低?阿里云没有解决方案嘛|

|   |   |   |
|---|---|---|
|![BadAngel](https://cdn.v2ex.com/avatar/f140/c5cc/476231_normal.png?m=1590304677)||93<br><br>**[BadAngel](https://www.v2ex.com/member/BadAngel)**      52 天前<br><br>阿里云没有分布式数据库中间件么？  <br>华为云 DDM 直接把数据库导进去，自动分库分表，搞定|

|   |   |   |
|---|---|---|
|![ZiLong](https://cdn.v2ex.com/avatar/6ed9/77ec/159848_normal.png?m=1474816668)||95<br><br>**[ZiLong](https://www.v2ex.com/member/ZiLong)**      52 天前<br><br>我有一个疑问，升级 sql 配置的钱出不起，能有钱上 OLAP ，印象中 OLAP 比关系型的更贵的多，而且 OLAP 基本底层架构基本都是分布式的，运维也非常复杂。  <br>我的想法还是把耗时的，拖垮数据库的 sql 结果查询出来，可以放在一张预存结果表或者 redis ，尽量不要让查询打到数据库，然后慢慢梳理优化 sql 、表结构、表数据，感觉这才是最经济，见效最快的。|

|   |   |   |
|---|---|---|
|![laminux29](https://cdn.v2ex.com/gravatar/f5dac702f2936e95d543670f76649f23?s=48&d=retro)||96<br><br>**[laminux29](https://www.v2ex.com/member/laminux29)**      52 天前<br><br>思路错了。<br><br>SQL 有 bug 属于重大缺陷，应该立即下成本去修复或重写，而不是去找什么 HA 方案。不然最后一堆脏数据写到库里，系统没办法运行了。<br><br>微软这类大公司，都有过这种黑历史时期。就像 Intel 之前自家晶圆厂存在工艺问题，不好好修复，而是选择强行冲，最后搞成这个鬼样子。虽然 15 代 Ultra 倒吸牙膏，但选择台积电，至少方向掰回来了。另外就是暴雪，早期暴雪，宁愿拖延跳票，也不愿意把不成熟的游戏放出来，所以暴雪早期口碑一直很好。|

|   |   |   |
|---|---|---|
|![seedhk](https://cdn.v2ex.com/avatar/e2b1/4142/483358_normal.png?m=1734402939)||97<br><br>**[seedhk](https://www.v2ex.com/member/seedhk)**      52 天前<br><br>@[mark2025](https://www.v2ex.com/member/mark2025) #74 是的，ES 的方案不太适合我目前的业务场景，IDC 没有 DBA 也没法做，加钱？ 难啊 哈哈哈  <br>@[v2orz](https://www.v2ex.com/member/v2orz) #75 目前可能考虑这个方案，在看优缺点  <br>@[dengtongcai](https://www.v2ex.com/member/dengtongcai) #76 双刃剑把算是，又好吃也有坏处，配置基本上拉满了，SQL 也在一直优化中  <br>@[Meld](https://www.v2ex.com/member/Meld) #77 谢谢，昨天咨询了一个大数据的前同事，也说 doris 比较适合  <br>@[zhoujinjing09](https://www.v2ex.com/member/zhoujinjing09) #78 我是 mssql ，AnalyticDB 是 mysql 的，不适用 谢谢|

|   |   |   |
|---|---|---|
|![seedhk](https://cdn.v2ex.com/avatar/e2b1/4142/483358_normal.png?m=1734402939)||98<br><br>**[seedhk](https://www.v2ex.com/member/seedhk)**      52 天前<br><br>@[datoujiejie221](https://www.v2ex.com/member/datoujiejie221) #85 这个思路也是不错的，谢谢您提的想法。我去看看我们的数据库是否能实现这个  <br>@[netnr](https://www.v2ex.com/member/netnr) #87 我去问了阿里云的客服，我们是 web 版本，而且是基础版，要从库要升级到集群版，中间还夹了个 HA 版  <br>@[spritecn](https://www.v2ex.com/member/spritecn) #89 我这边看到一年要 2 30W ，也不算低了，没办法是小公司，属于是既要又要还要了  <br>@[lambdaq](https://www.v2ex.com/member/lambdaq) #91 目前基本上的大 SQL 和都迁移到 DTS 同步的从库去了，但还是担心主库会挂，所以想找个方案  <br>@[dd102](https://www.v2ex.com/member/dd102) #92 问了就说升级到高版本，花更多的钱  <br>@[ZiLong](https://www.v2ex.com/member/ZiLong) #95 是的，就是您说的这个思路  <br>@[laminux29](https://www.v2ex.com/member/laminux29) #96 谢谢您的建议，SQL 优化一直有在做，但是工作量太大了，远水解不了近渴|

|   |   |   |
|---|---|---|
|![ttkanni](https://cdn.v2ex.com/avatar/b1c9/deca/602847_normal.png?m=1733797042)||99<br><br>**[ttkanni](https://www.v2ex.com/member/ttkanni)**      52 天前<br><br>@[seedhk](https://www.v2ex.com/member/seedhk)  <br>按照 OP 的描述，最优的方案就是从库+Redis ，读写分离，从库承担读压力，Redis 做读缓存（视业务情况）。  <br>如果是单纯保障 RDS 稳定，可以考虑把 SQL 限流打开，免费版也能用个基础的，开高级版能针对 SQL 限流。一个月好像就百来块，针对 SQL 限流能缓解慢 SQL 堆集耗尽 RDS 资源的问题，但业务那边的沟通得做好。<br><br>领导提的方案有很大的场景缺陷，延迟落库并不会显著环节数据库的压力，同时延迟落库存在数据差异，万一缓存穿透，业务直接读库，数据不一致完蛋。|

|   |   |   |
|---|---|---|
|![npe](https://cdn.v2ex.com/avatar/0219/1437/402730_normal.png?m=1555553934)||100<br><br>**[npe](https://www.v2ex.com/member/npe)**      52 天前<br><br>短期增加配置、长期优化 SQL 和业务逻辑，以及考虑使用 OLAP 数据库来处理复杂查询，如 ClickHouse 或 Doris 。|