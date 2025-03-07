---
link: https://www.v2ex.com/t/1101255
site: V2EX
date: 2024-12-30T14:18
excerpt: 程序员 - @iamtuzi3333 - 小弟负责是后端内容的编写，现在系统有一批传感器，数据格式都是 json
  ，每个传感器每秒都有数据发送过来。我接收，然后写入文件，每天一个.json ，例如：传感器编号-日期-文件，这样的格式。文件中每
twitter: https://twitter.com/@V2EX
slurped: 2025-02-10T11:10
title: 大佬们，请教一下数据读取 - V2EX
---

这是一个创建于 41 天前的主题，其中的信息可能已经有所发展或是发生改变。

小弟负责是后端内容的编写，现在系统有一批传感器，数据格式都是 json ，每个传感器每秒都有数据发送过来。我接收，然后写入文件，每天一个.json ，例如：传感器编号-日期-文件，这样的格式。文件中每行都是{}的数据，里面有时间戳，data ，例如{"time":12346574,"data":[1,2,3,4,5]}，每一行都是这样的形式。文件夹目录有分层，每天都有一个日期对应的目录，里面就是当天的数据文件。数据同时存入到数据库 Mongo 中，单个节点，建了 time 字段的索引。现在查询历史数据量多的话感觉速度还是有点慢，依靠 time 字段找出时间范围的数据，取出每条数据的 data 元素；现在小弟想数据库只存储当前 3 天的数据，就是额外写一个脚本定时删除三天以前的数据，然后历史数据改为读取对应文件及日期的文件数据，这样读取历史数据是否可行，速度是否更快呢，后端用的 node ，他读取数据量量一大就容易内存栈，这个 data 字段元素有 200 个浮点数，一天能存 86400*200 多个数字，所以读取历史数据有时候读的时间范围大就容易崩，想请教大佬们怎么处理好一点。

[](https://www.v2ex.com/tag/%E6%95%B0%E6%8D%AE)

[数据](https://www.v2ex.com/tag/%E6%95%B0%E6%8D%AE)[

读取](https://www.v2ex.com/tag/%E8%AF%BB%E5%8F%96)[

优化](https://www.v2ex.com/tag/%E4%BC%98%E5%8C%96)

26 条回复  **•**  2025-01-02 09:06:52 +08:00

|   |   |   |
|---|---|---|
|![skallz](https://cdn.v2ex.com/gravatar/e2d66edb8b18a0aa97b9f7b21d6e1258?s=48&d=retro)||1<br><br>**[skallz](https://www.v2ex.com/member/skallz)**      41 天前<br><br>如果查询范围不大的话，可以考虑直接让前端拿对应文件的内容前端处理，让客户端分担服务端的性能压力，哈哈哈哈，前提是你的文件服务器和业务服务器不是同一个服务器，比如用的云服务商 oss 之类的|

|   |   |   |
|---|---|---|
|![chihiro2014](https://cdn.v2ex.com/gravatar/a101f4a233d8c1a4c9d37f8b5aafb595?s=48&d=retro)||2<br><br>**[chihiro2014](https://www.v2ex.com/member/chihiro2014)**      41 天前<br><br>为什么感觉应该是使用 influxdb 之类的产品，而不是 mongo|

|   |   |   |
|---|---|---|
|![daxin945](https://cdn.v2ex.com/avatar/c156/114a/506253_normal.png?m=1721982261)||4<br><br>**[daxin945](https://www.v2ex.com/member/daxin945)**      41 天前<br><br>如果是我的话可能会用 clickhouse 替换 mongo|

|   |   |   |
|---|---|---|
|![MoYi123](https://cdn.v2ex.com/avatar/2a62/8338/469223_normal.png?m=1649665753)||5<br><br>**[MoYi123](https://www.v2ex.com/member/MoYi123)**      41 天前<br><br>没必要, 数据库一般会用一些压缩算法, 肯定比你支持存 json 文件要省的.  <br>数据库里用 partition table, 按日期分  <br>内存溢出肯定是你代码有错, 86400*200 个 float 应该还不到 100MB.|

|   |   |   |
|---|---|---|
|![sagaxu](https://cdn.v2ex.com/avatar/a4b7/3b82/200123_normal.png?m=1735644881)||7<br><br>**[sagaxu](https://www.v2ex.com/member/sagaxu)**      41 天前<br><br>数据总量是多少，每次查询返回多少，有点儿慢是多慢，查询是怎么写的，这些都没讲清楚，不大好分析。|

|   |   |   |
|---|---|---|
|![Oldletter](https://cdn.v2ex.com/gravatar/b7a7811c5d44ba485e08a96cc834ff54?s=48&d=retro)||8<br><br>**[Oldletter](https://www.v2ex.com/member/Oldletter)**      41 天前<br><br>MongoDB 支持 TTL 索引，允许自动删除超过指定时间的数据。你可以为 time 字段创建一个 TTL 索引来确保数据库中只保留 3 天的数据，这样就不需要手动写脚本来删除过期数据。<br><br>你的数据感觉不是特别大,所以建议你看看代码问题吧|

|   |   |   |
|---|---|---|
|![iamtuzi3333](https://cdn.v2ex.com/gravatar/84ffc0a186f96fb0dfea0ca5fb100d3e?s=48&d=retro)||10<br><br>**[iamtuzi3333](https://www.v2ex.com/member/iamtuzi3333)**      41 天前<br><br>@[MoYi123](https://www.v2ex.com/member/MoYi123) 内存溢出是 node 的问题好像，我试过查询去年某一段时间的数据，他就查询内存栈溢出了。  <br>@[sagaxu](https://www.v2ex.com/member/sagaxu) 数据总量很多，每天 86400 条 json 存入，每次查询返回不定期，就是得根据前端传回的时间范围作为查询条件，有时候会查询去年某一段时间的数据，慢的时候主要是等待很久，数据库的每个集合的 timestamp 字段有做索引。查询代码如下：  <br>// 获取 MongoDB 原生数据库连接  <br>const db = mongoose.connection.db;  <br>// 获取指定的集合  <br>const collection = db.collection(collectionName);  <br>// 构建查询条件  <br>const query = {};  <br>const timestampInt = parseInt(timestamp, 10);  <br>query.timestamp = timestampInt;  <br>// 查询数据  <br>const result = await collection.find(query).toArray();  <br>if (result.length <= 0) {  <br>ctx.status = 200;  <br>ctx.body = { message: 'no data', data: [] };  <br>return;  <br>}<br><br>@[Oldletter](https://www.v2ex.com/member/Oldletter) 代码相对来说比较简单，就是传入集合名字，时间范围，就去对应的结合查询，查询代码如上，后端用的 node ，koa 框架，但是我发现 Mongo 的数据迁移不太方便，比如说我要把 a 服务器的某一个库的所有数据转移到 b 服务器的 Mongo 实例中，就不太方便了。|

|   |   |   |
|---|---|---|
|![sagaxu](https://cdn.v2ex.com/avatar/a4b7/3b82/200123_normal.png?m=1735644881)||12<br><br>**[sagaxu](https://www.v2ex.com/member/sagaxu)**      41 天前<br><br>前端查一个月的数据干嘛用？浏览器根本无法展示。显然要做好聚合，缩小数据规模。|

|   |   |   |
|---|---|---|
|![aloxaf](https://cdn.v2ex.com/gravatar/4ea6081ef8d855cb90225438daf0de63?s=48&d=retro)||13<br><br>**[aloxaf](https://www.v2ex.com/member/aloxaf)**      41 天前   ![❤️](https://www.v2ex.com/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>没用过 MongoDB ，不过这类时间序列数据查询的优化方向都是差不多的：  <br>1. 提前按天、按小时聚合数据，根据查询范围来调整返回数据的精度。就像楼上说的，一个月的数据得上百万条了，前端要这么多数据干嘛。  <br>2. 原始数据可以存的时候就按小时打包来存，没必要每秒生成一条记录。  <br>3. 你这数据量也不大，但不知道 MongoDB 存这些数据效率如何，如果太占空间可能要考虑对旧数据降采样（你真的需要查询三年前某分钟内每秒的数据？）或者转冷存储。<br><br>不过还是推荐直接用数序数据库，不仅速度更快还节省空间，而且「优化花费的时间」未必比「迁移花费的时间」更少，除了 influxdb 外也可以看看 timescaledb ，对于有 sql 经验的人来说迁移真的方便）|

|   |   |   |
|---|---|---|
|![iamtuzi3333](https://cdn.v2ex.com/gravatar/84ffc0a186f96fb0dfea0ca5fb100d3e?s=48&d=retro)||14<br><br>**[iamtuzi3333](https://www.v2ex.com/member/iamtuzi3333)**      41 天前<br><br>@[sagaxu](https://www.v2ex.com/member/sagaxu) 查询画图展示，长时间的我会额外查询宿友再处理，比如每十分钟提取一个最大值，汇聚所有的值返回。但是归根到底我还是要查询这些时间范围的数据。  <br>@[aloxaf](https://www.v2ex.com/member/aloxaf) 前端查询数据主要是展示，会有额外的需求，不过我还是要单独查询出这些范围的数据做进一步的加工。原始数据是传感器就固定每秒会有数据，传感器一多，每小时打包就不方便了，有时需要上半段，有时候需要下半段，每秒是最好的处理方法。数据会查询很久之前的，需要保持。时序数据库我还在找，发现挺多不怎么合适，总有一两项让我退步🤣|

|   |   |   |
|---|---|---|
|![nivalxer](https://cdn.v2ex.com/gravatar/59ca2c914722d2989442a86da5240a87?s=48&d=retro)||15<br><br>**[nivalxer](https://www.v2ex.com/member/nivalxer)**      41 天前<br><br>场景比较类似，只不过我们这边传感器数据没有到每秒，一般大概 10 几秒到几分钟不等。  <br>目前也是 Mongodb 的方案，按每个站点（一个站会有多个参数）一张表方式存储，每个小时会抽一条数据放小时表，统计报表再根据公司配置进行公司表级的存储。  <br>Mongodb 需要考虑查出来的文档返回不能超过 16M ，虽然有一些配置可以绕过限制。目前感觉在数据量比较多，也根据查询条件（时间等）加了索引情况下，响应速度一般。  <br>如果数据比较频繁并且需要偶尔查出来比较多的历史数据（多天、月、季度）还是看看其他的方案，目前我也想看看有没有除 MongoDb 外的其他更好的方案。|

|   |   |   |
|---|---|---|
|![hd10180](https://cdn.v2ex.com/gravatar/8c401efdd3e655d8c0029455669e57df?s=48&d=retro)||16<br><br>**[hd10180](https://www.v2ex.com/member/hd10180)**      41 天前<br><br>虽然我很菜，但我也做过类似的数据处理。  <br>我的看法是要分析的数据不要存成数组，后期可能不方便做查询，data 的每个数值应该有个属性名。  <br>假设[26, 80, ..]代表的是 [温度, 湿度, ...] 转成 temp: value, hum: value 的方式存储。可能你的情况跟我的不太一样，就当我没说。[![](https://i.imgur.com/OVQjxIr.png)](https://i.imgur.com/OVQjxIr.png)  <br>另外每个传感器应该有 uuid 的吧，索引做成 uuid+time 不知道会不会好些？还可以考虑写个额外的程序对数据做分析，比如做小时维度的数据统计、月维度的统计等。|

|   |   |   |
|---|---|---|
|![yyt6801](https://cdn.v2ex.com/avatar/c2ac/894c/393681_normal.png?m=1562671598)||18<br><br>**[yyt6801](https://www.v2ex.com/member/yyt6801)**      41 天前<br><br>楼上都提到的时序数据库就是为了解决这种问题， 首先你要知道 每秒的那个 data:[]里面都代表什么东西；知道结构其他都好办了， 剩下的交给时序数据库解决|

|   |   |   |
|---|---|---|
|![sagaxu](https://cdn.v2ex.com/avatar/a4b7/3b82/200123_normal.png?m=1735644881)||19<br><br>**[sagaxu](https://www.v2ex.com/member/sagaxu)**      41 天前   ![❤️](https://www.v2ex.com/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>@[iamtuzi3333](https://www.v2ex.com/member/iamtuzi3333) “比如每十分钟提取一个最大值”，这个事情可以提前做好。我之前做过一个数据结构类似的项目，有分钟汇总，小时汇总，天汇总，都是提前生成缓存好，当日数据还会存一份在内存里加速访问。一般查询都有个特点，时间段跨度越大，越不关心局部数据，缓存好的汇总表能极大提高查询速度。<br><br>一次查大量数据，只能在后台定时任务里跑，不能由前端触发查询，否则任何数据库都无法满足。数据量量一大，即使 nodejs 直接读文件解析，不经过 db ，也会消耗很大资源。|

|   |   |   |
|---|---|---|
|![kivmi](https://cdn.v2ex.com/avatar/f035/930d/599386_normal.png?m=1710077859)||21<br><br>**[kivmi](https://www.v2ex.com/member/kivmi)**      41 天前<br><br>从大数据处理基本都是 map-reduce ，所以，这么直接查询原始数据，总感觉有些不妥|

|   |   |   |
|---|---|---|
|![iamtuzi3333](https://cdn.v2ex.com/gravatar/84ffc0a186f96fb0dfea0ca5fb100d3e?s=48&d=retro)||22<br><br>**[iamtuzi3333](https://www.v2ex.com/member/iamtuzi3333)**      41 天前<br><br>@[nivalxer](https://www.v2ex.com/member/nivalxer) 我是每个传感器一个表，返回的文档长度不超过 16M 吗，有更好的方案可以分享一下。  <br>@[hd10180](https://www.v2ex.com/member/hd10180) 他格式没有这么多，就是固定的 data 数组，要么 50,100,200 ，是根据采样率来定的。传感器也没有 uuid 全靠自己编。  <br>@[yyt6801](https://www.v2ex.com/member/yyt6801) data 数组就是 50 或者 100 或者 200 个浮点数，每秒的数据都是这样。  <br>@[sagaxu](https://www.v2ex.com/member/sagaxu) 是的，我现在只统计了每秒的最大值，最小值，平均值，读取起来还不算太费劲。正常来说我们只关注十分钟这个节点，还有每分钟数据，这个都还算好用处理。文件确实，主要是读取文件比较麻烦，文件目录不固定，没有很好的索引方式。  <br>@[kivmi](https://www.v2ex.com/member/kivmi) 是的，但是我们的数据也不算大，就是多，频繁，每秒都有，直接查询原始数据出来也是为了做进一步处理，比如取出每一分钟的最大值，最小值，均值，方差这一些。|

|   |   |   |
|---|---|---|
|![nivalxer](https://cdn.v2ex.com/gravatar/59ca2c914722d2989442a86da5240a87?s=48&d=retro)||23<br><br>**[nivalxer](https://www.v2ex.com/member/nivalxer)**      41 天前<br><br>我们这边行业比较特殊，对接 PLC 走场站这块，虽然 PLC 站控那边数据是实时的，我们采集远传还是以间隔来走的，所以数据量不会太多，在 10 秒频率下，按天走也不会超过 16M 。这个 16M 是输出文档大小，如果采用分页查询等，输出文档不超过 16M 也没啥问题。  <br>数据库我们暂时还是 mongodb 还没改，计划后面改，还没测试其他方案。  <br>我们行业场景，其实客户不会关注每秒的数据情况，所以大部分时间客户查的小时表（每小时一条取样）和统计表（小时、日、月）这两种，压力就还好。少量在出报警、统计到处等场景才会查完整历史数据。  <br>可以按客户场景来处理。如果客户有每条数据必须存和频繁的查询需求，在不过多改动现有技术架构情况下，可能看看其他数据库比较合适。|

|   |   |   |
|---|---|---|
|![fishman231](https://cdn.v2ex.com/gravatar/a40fc932d781b6279f759a0e6eaa4143?s=48&d=retro)||24<br><br>**[fishman231](https://www.v2ex.com/member/fishman231)**      40 天前<br><br>MongoDB 也是有时序集合,可以使用 TTL 索引自动删除过期文件.另外时序集合可压缩数据,这样是否可以所有数据都存数据库呢|

|   |   |   |
|---|---|---|
|![pangzipp](https://cdn.v2ex.com/avatar/1025/7392/108352_normal.png?m=1734326509)||25<br><br>**[pangzipp](https://www.v2ex.com/member/pangzipp)**      40 天前<br><br>mongodb 本身有数据压缩  <br>你能够实现 3 天以前数据读本地文件文件， 那也可以在 mongodb 里分表。<br><br>可以评估下计划投入的资源，成本多少?  <br>用自己熟悉的技术栈|

|   |   |   |
|---|---|---|
|![iamtuzi3333](https://cdn.v2ex.com/gravatar/84ffc0a186f96fb0dfea0ca5fb100d3e?s=48&d=retro)||26<br><br>**[iamtuzi3333](https://www.v2ex.com/member/iamtuzi3333)**      39 天前<br><br>@[nivalxer](https://www.v2ex.com/member/nivalxer) 挺好，后者历史数据我们很像，不过我就是还有一个实时数据的波形展示。  <br>@[fishman231](https://www.v2ex.com/member/fishman231) 我查询看看。  <br>@[pangzipp](https://www.v2ex.com/member/pangzipp) 目前还没有实现三天以前读取本地文件，就是想这么做，看到一个方案就是只存储最近几天的数据，然后历史数据都存储到文件，查询历史数据通过读文件的形式去完成。MongoDB 分表我还不熟悉；技术栈都是啥好用简单方便就上啥了。|