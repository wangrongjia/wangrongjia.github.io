---
link: https://www.v2ex.com/t/1111791
site: V2EX
date: 2025-02-16T16:54
excerpt: 程序员 - @BuGoooo - 目前大概有 10 亿条数据(陆续还会继续增加)，就两个字段一个用户编码（随机的）
  一个姓名。我现在想做模糊匹配查询手机号做毫秒级的返回，比如输入编码后 3 位置后 4 位这些条件来输出所有编码一样
twitter: https://twitter.com/@V2EX
slurped: 2025-03-07T15:37
title: 我这个需求 适合用 clickhouse 吗 - V2EX
---
 
  [BuGoooo](/member/BuGoooo) · 18 天前 · 2879 次点击

目前大概有 10 亿条数据(陆续还会继续增加)，就两个字段一个用户编码（随机的） 一个姓名。 我现在想做模糊匹配查询手机号做毫秒级的返回，比如输入编码后 3 位置后 4 位这些条件来输出所有编码一样的用户出来，用 clickhouse 合适吗

[

clickhouse](/tag/clickhouse)[

模糊匹配](/tag/模糊匹配)[

数据量](/tag/数据量)

33 条回复  **•**  2025-02-21 10:07:29 +08:00

|   |   |   |
|---|---|---|
|![raycool](https://cdn.v2ex.com/gravatar/3535e890dad8960697c4f90990c8dca7?s=48&d=retro)||1<br><br>**[raycool](/member/raycool)**  <br><br>   18 天前<br><br>用 ES 合适吧？|

|   |   |   |
|---|---|---|
|![xausky](https://cdn.v2ex.com/avatar/100d/f2fd/623168_normal.png?m=1739685666)||2<br><br>**[xausky](/member/xausky)**  <br><br>   18 天前<br><br>如果都是后 N 位的话直接数据库索引就可以优化，如果是任意 N 位 PGSQL 的话可以用 pg_trgm|

|   |   |   |
|---|---|---|
|![yudoo](https://cdn.v2ex.com/avatar/adb8/e677/540602_normal.png?m=1689518455)||3<br><br>**[yudoo](/member/yudoo)**  <br><br>   18 天前<br><br>非常合适啊 也好部署，数据压缩比较好对内存要求比较低|

|   |   |   |
|---|---|---|
|![silentsky](https://cdn.v2ex.com/avatar/b06b/e628/563714_normal.png?m=1711037497)||4<br><br>**[silentsky](/member/silentsky)**  <br><br>   18 天前 via Android<br><br>合适|

|   |   |   |
|---|---|---|
|![8355](https://cdn.v2ex.com/avatar/dbd3/6c22/210254_normal.png?m=1715407255)||5<br><br>**[8355](/member/8355)**  <br><br>   18 天前<br><br>es 成本更低|

|   |   |   |
|---|---|---|
|![gazi](https://cdn.v2ex.com/avatar/cef2/64a3/592916_normal.png?m=1662795826)||6<br><br>**[gazi](/member/gazi)**  <br><br>   18 天前<br><br>es 更合适。  <br>clickhouse 的任意位置模糊匹配查询很费劲|

|   |   |   |
|---|---|---|
|![bronyakaka](https://cdn.v2ex.com/avatar/4bc4/38c9/676530_normal.png?m=1735389040)||7<br><br>**[bronyakaka](/member/bronyakaka)**  <br><br>   18 天前<br><br>搜索需求 毫无疑问是 es|

|   |   |   |
|---|---|---|
|![root71370](https://cdn.v2ex.com/gravatar/8b41b5aba0f2dd6060ec75a9e1073ebd?s=48&d=retro)||8<br><br>**[root71370](/member/root71370)**  <br><br>   18 天前 via Android<br><br>@[8355](/member/8355) 大家不都说 clickhouse 的成本要比 es 低吗？|

|   |   |   |
|---|---|---|
|![mark2025](https://cdn.v2ex.com/gravatar/0d54045890432a48c1bd1f605224190d?s=48&d=retro)||9<br><br>**[mark2025](/member/mark2025)**  <br><br>   18 天前<br><br>pgsql 的 FTS 搜索可以满足需求|

|   |   |   |
|---|---|---|
|![NotLongNil](https://cdn.v2ex.com/gravatar/1afa6987d13718a197fade1f6f8e656c?s=48&d=retro)||10<br><br>**[NotLongNil](/member/NotLongNil)**  <br><br>   18 天前 via iPhone<br><br>需要你再具体描述下你的搜索场景，是固定按后 3 位搜索？还是后 4 位？还是随机长度？|

|   |   |   |
|---|---|---|
|![cobbage](https://cdn.v2ex.com/gravatar/78cb72e2bd01326d19a49efee32ba076?s=48&d=retro)||11<br><br>**[cobbage](/member/cobbage)**  <br><br>   18 天前<br><br>Pika|

|   |   |   |
|---|---|---|
|![me1onsoda](https://cdn.v2ex.com/avatar/ae5b/6713/636446_normal.png?m=1688972240)||12<br><br>**[me1onsoda](/member/me1onsoda)**  <br><br>   18 天前 via Android<br><br>这么简单的需求 pg 其实就可以，支持表达式索引|

|   |   |   |
|---|---|---|
|![levelworm](https://cdn.v2ex.com/avatar/3f06/6f8f/401678_normal.png?m=1733594936)||13<br><br>**[levelworm](/member/levelworm)**  <br><br>   18 天前 via Android<br><br>好奇一把，十个亿存储量多大？|

|   |   |   |
|---|---|---|
|![spritecn](https://cdn.v2ex.com/gravatar/5bd942c8bc4a90af9ffa7f3576428154?s=48&d=retro)||14<br><br>**[spritecn](/member/spritecn)**  <br><br>   18 天前<br><br>感觉,这个活普通 mysql 就能搞定啊,不要被各种教程说 2000 万以上 mysql 撑不住说法给忽悠|

|   |   |   |
|---|---|---|
|![13240284671](https://cdn.v2ex.com/avatar/129c/5f01/639318_normal.png?m=1709524023)||15<br><br>**[13240284671](/member/13240284671)**  <br><br>   18 天前<br><br>@[spritecn](/member/spritecn) 模糊搜索呢，你用 mysql 搜试下，搜一次几分钟|

|   |   |   |
|---|---|---|
|![silentsky](https://cdn.v2ex.com/avatar/b06b/e628/563714_normal.png?m=1711037497)||16<br><br>**[silentsky](/member/silentsky)**  <br><br>   18 天前<br><br>@[spritecn](/member/spritecn) 怎么想的 这个得看业务需要 如果数据分析那肯定不用 mysql 存储成本也高|

|   |   |   |
|---|---|---|
|![lasuar](https://cdn.v2ex.com/avatar/0a94/3887/328850_normal.png?m=1709527453)||17<br><br>**[lasuar](/member/lasuar)**  <br><br>   18 天前<br><br>@[spritecn](/member/spritecn) #14 亿级模糊搜索超出 mysql 的能力范畴了，早点上专业的更合适。|

|   |   |   |
|---|---|---|
|![homewORK](https://cdn.v2ex.com/gravatar/2b90f8e8787898dc6882795df80fa135?s=48&d=retro)||18<br><br>**[homewORK](/member/homewORK)**  <br><br>   18 天前<br><br>不适合  <br>clickhouse 更适合的是时序 + 数据处理任务的数据  <br>很明显你这个不是，只是查找。es 可能更合适，或者折腾一下 mysql 等|

|   |   |   |
|---|---|---|
|![cosen](https://cdn.v2ex.com/gravatar/fab9dac963b95a9227ba858ea070dc1d?s=48&d=retro)||19<br><br>**[cosen](/member/cosen)**  <br><br>   18 天前<br><br>应该问题不大，把后 3 位或后 4 位设计成分区，最多也就 1w 个分区，这样查数据也不会全表扫，可以试试|

|   |   |   |
|---|---|---|
|![telemsg](https://cdn.v2ex.com/gravatar/9f4ad43069f8812fd67d6294b96bba65?s=48&d=retro)||20<br><br>**[telemsg](/member/telemsg)**  <br><br>   18 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>各位需求都没明白吧（我反正是没有看懂） 就开始说技术了？|

|   |   |   |
|---|---|---|
|![8355](https://cdn.v2ex.com/avatar/dbd3/6c22/210254_normal.png?m=1715407255)||21<br><br>**[8355](/member/8355)**  <br><br>   18 天前<br><br>@[root71370](/member/root71370) 简单来说看看阿里云的价格  <br>Elasticsearch 有 Serverless 版本，可以按照 cu 收费，如果计划任务批量写库实际使用的 cu 很少，系统不是高并发持续访问的话一年不到 1 万就够了。clickhouse 单机起步就是 1 万|

|   |   |   |
|---|---|---|
|![dilu](https://cdn.v2ex.com/gravatar/c633afbd75edf0f0c9473ebd0866d659?s=48&d=retro)||22<br><br>**[dilu](/member/dilu)**  <br><br>   18 天前<br><br>“就两个字段一个用户编码（随机的） 一个姓名”  <br>  <br>“模糊匹配查询手机号做毫秒级的返回”  <br>  <br>从哪又蹦出来一个手机号字段？不就两个字段吗？一个用户编码，一个姓名  <br>  <br>而且从实际出发，你已经有 10 亿条记录，还是手机号这种数据，先不说你从哪来的  <br>  <br>如果只搜后 4 位，重复的概率得多大啊，你一下子就能搜出上万条记录，请问你怎么把这上万甚至几十万的数据展示给用户？|

|                                                                                      |     |                                                                                                                                                                                                                                                                       |
| ------------------------------------------------------------------------------------ | --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ![rays](https://cdn.v2ex.com/gravatar/ca845cb48e2da6f0e7ecbfdb5c5402de?s=48&d=retro) |     | 23<br><br>**[rays](/member/rays)**  <br><br>   18 天前<br><br>**你的需求是模糊匹配且是后缀匹配，是要用到 LIKE 和 position 函数，跳数索引是前缀匹配，无法满足你的需求，起不到加速查询的作用。position 是 ClickHouse 自带的字符串查询算法，性能会比 like 要好。但是 ClickHouse 数据库还是更适合列式聚合场景的，你的这种需求，还是不是很推荐使用 ClickHouse ，因为引入一项新技术后并没有带来突破性的提升**。 |

|                                                                                    |     |                                                                                         |
| ---------------------------------------------------------------------------------- | --- | --------------------------------------------------------------------------------------- |
| ![guanhui07](https://cdn.v2ex.com/avatar/437f/2914/164143_normal.png?m=1736667690) |     | 24<br><br>**[guanhui07](/member/guanhui07)**  <br><br>   18 天前<br><br>**搜索需求 最合适还是 es** |

|   |   |   |
|---|---|---|
|![blessingsi](https://cdn.v2ex.com/gravatar/c4cc094b4aa389cf85b88a2526a3b2dd?s=48&d=retro)||25<br><br>**[blessingsi](/member/blessingsi)**  <br><br>   17 天前<br><br>查询流量是多少？|

|                                                                                         |     |                                                                                                                                                                                                                        |
| --------------------------------------------------------------------------------------- | --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ![BuGoooo](https://cdn.v2ex.com/gravatar/e3b6412d155596a7aa3cf46ff36dd910?s=48&d=retro) |     | 26<br><br>**[BuGoooo](/member/BuGoooo)**  <br><br>OP<br><br>   17 天前<br><br>@[NotLongNil](/member/NotLongNil)  <br>编码长度是固定的，32 位的。但是编码是随机的，每次查询的话就是查询开头和结尾是否有匹配的，比如  <br>ABCD****123456 我就查询前面 2 位 AB 和后面 4 位是否有相匹配的编码 |

|   |   |   |
|---|---|---|
|![BuGoooo](https://cdn.v2ex.com/gravatar/e3b6412d155596a7aa3cf46ff36dd910?s=48&d=retro)||27<br><br>**[BuGoooo](/member/BuGoooo)**  <br><br>OP<br><br>   17 天前<br><br>@[homewORK](/member/homewORK) es 我也倒腾了下，总感觉没对 查起来速度有点慢 不知道是不是我倒腾的没对|

|   |   |   |
|---|---|---|
|![BuGoooo](https://cdn.v2ex.com/gravatar/e3b6412d155596a7aa3cf46ff36dd910?s=48&d=retro)||28<br><br>**[BuGoooo](/member/BuGoooo)**  <br><br>OP<br><br>   17 天前<br><br>@[dilu](/member/dilu) 打错了，就是编码+姓名， 主要是通过匹配编码来找数据|

|   |   |   |
|---|---|---|
|![NotLongNil](https://cdn.v2ex.com/gravatar/1afa6987d13718a197fade1f6f8e656c?s=48&d=retro)||29<br><br>**[NotLongNil](/member/NotLongNil)**  <br><br>   17 天前<br><br>@[BuGoooo](/member/BuGoooo) #26 clickhouse 不适合做这个。上面看到你试验后，发现查询慢。这是正常的，因为 CH 做了全表扫描。CH 的索引跟 mysql 多索引不一样。如果是固定前两位和固定后四位查询，你使用 mysql ，把这两个单独提出来，作为分表键，加索引，查询速度比 ch es 还快，还节省资源|

|   |   |   |
|---|---|---|
|![silentsky](https://cdn.v2ex.com/avatar/b06b/e628/563714_normal.png?m=1711037497)||30<br><br>**[silentsky](/member/silentsky)**  <br><br>   17 天前 via Android<br><br>@[NotLongNil](/member/NotLongNil) clickhouse 物化视图就能做|

|   |   |   |
|---|---|---|
|![unclejimao](https://cdn.v2ex.com/avatar/3a40/dd52/412579_normal.png?m=1557906472)||31<br><br>**[unclejimao](/member/unclejimao)**  <br><br>   17 天前<br><br>多存两列，prefix 存前两位，做分区字段，不区分大小写的话 1000 多个分区； suffix 存后 4 位，做排序字段；  <br>查询的时候直接 WHERE prefix=? AND suffix=?|

|                                                                                            |     |                                                                                                                                                                                                                                                                                                              |
| ------------------------------------------------------------------------------------------ | --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ![NotLongNil](https://cdn.v2ex.com/gravatar/1afa6987d13718a197fade1f6f8e656c?s=48&d=retro) |     | 32<br><br>**[NotLongNil](/member/NotLongNil)**  <br><br>   17 天前<br><br>@[silentsky](/member/silentsky) #30 **CH 的 MergeTree 索引结构，只能判断到数据在哪个段，然后将整个段加载到内存，在内存中进行遍历过滤。一个段默认大小有 8000 多行。在这个场景下，做好分表，设置好索引，B+ 树段查询速度反而会比 CH 更可观，还节省资源，并发更大。楼主这个搜索场景还需要考虑并发数，CH 的并发成本比 mysql 高了几个量级。物化视图只是 MergeTree 套了一层，底层没变** |

|   |   |   |
|---|---|---|
|![oneisall8955](https://cdn.v2ex.com/avatar/60dc/c401/355824_normal.png?m=1711427173)||33<br><br>**[oneisall8955](/member/oneisall8955)**  <br><br>   14 天前<br><br>es 前缀匹配完美符合切合你的需求|
#### 什么是列式存储数据库？

列式存储数据库是一种数据库管理系统（DBMS），它将数据按列（而不是传统数据库的按行）存储。也就是说，每一列的数据单独存储并连续排列，而不是将整行数据放在一起。这种设计特别适合在线分析处理（OLAP），比如数据仓库和商业智能场景，因为分析查询通常只涉及少量列但需要扫描大量记录。

例如，ClickHouse、Vertica 和 Snowflake 都是列式存储数据库的代表。
#### 优点

1. **查询速度快**：只读取需要的列，减少 I/O 操作，尤其适合聚合查询（如 SUM、AVG）。
2. **压缩率高**：同一列数据类型相似，压缩效率更高，节省存储空间。
3. **适合分析**：在大规模数据集上执行复杂分析时性能优越。

#### 缺点

1. **写入性能差**：频繁插入或更新数据时效率低，因为需要调整多列。
2. **不适合事务**：不支持复杂的 OLTP（在线事务处理）需求，如高并发写入。
3. **实现复杂**：设计和维护比行式数据库更复杂，开发成本可能更高。
#### 定义与技术原理

列式存储数据库将表中的数据按列存储，而不是按行存储。传统行式数据库（如 MySQL）会将一行数据的所有字段连续存储，而列式数据库则将每一列的数据单独存储并优化。例如，对于一个包含“姓名”、“年龄”和“薪资”的表：

- **行式存储**：存储为 [张三, 30, 5000], [李四, 25, 6000]，每行连续存放。
- **列式存储**：存储为 [张三, 李四], [30, 25], [5000, 6000]，每列独立存放。

这种设计的核心在于，分析查询通常只涉及少数列（如“计算平均薪资”只需读取“薪资”列），列式存储可以跳过无关列，显著提高效率