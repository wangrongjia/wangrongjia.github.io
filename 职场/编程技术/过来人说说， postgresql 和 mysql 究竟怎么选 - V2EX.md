---
link: https://www.v2ex.com/t/1109357
site: V2EX
date: 2025-02-06T15:40
excerpt: 数据库 - @unt - 从客户要求，系统架构，公司内部技术栈，领导偏好，个人使用体验等多方面聊聊
twitter: https://twitter.com/@V2EX
slurped: 2025-02-06T21:24
title: 过来人说说， postgresql 和 mysql 究竟怎么选 - V2EX
---

从客户要求，系统架构，公司内部技术栈，领导偏好，个人使用体验等多方面聊聊

|   |   |   |
|---|---|---|
|![Seanfuck](https://cdn.v2ex.com/gravatar/7d59c05dc2dc29dc93bb77784f09694e?s=48&d=retro)||1<br><br>**[Seanfuck](https://www.v2ex.com/member/Seanfuck)**      5 小时 40 分钟前<br><br>没有硬性要求就无脑 mysql ，简单省事。|

|   |   |   |
|---|---|---|
|![whevether](https://cdn.v2ex.com/gravatar/c12eceadb99256aef415e66496c4398a?s=48&d=retro)||2<br><br>**[whevether](https://www.v2ex.com/member/whevether)**      5 小时 39 分钟前<br><br>sql 玩的不好的还是 mysql 吧。简单。高手可以玩 pg|

|   |   |   |
|---|---|---|
|![rekulas](https://cdn.v2ex.com/avatar/ff00/e7ff/173283_normal.png?m=1726814747)||3<br><br>**[rekulas](https://www.v2ex.com/member/rekulas)**      5 小时 33 分钟前<br><br>看业务，如果未来业务对 json 需求高的可以上 pg ，如果不高就 mysql 又成熟又稳  <br>以基础框架为例，优先适配、测试用例覆盖更全的也是 mysql ，找库也好找些|

|   |   |   |
|---|---|---|
|![laikick](https://cdn.v2ex.com/avatar/7d70/1b2f/553821_normal.png?m=1731246240)||4<br><br>**[laikick](https://www.v2ex.com/member/laikick)**      5 小时 28 分钟前<br><br>必须使用独立自主的 mysql|

|   |   |   |
|---|---|---|
|![defunct9](https://cdn.v2ex.com/avatar/5cf8/faa5/97884_normal.png?m=1631865166)||5<br><br>**[defunct9](https://www.v2ex.com/member/defunct9)**      5 小时 27 分钟前<br><br>mysql ，pg 的模式很麻烦的。|

|   |   |   |
|---|---|---|
|![hefish](https://cdn.v2ex.com/gravatar/32ee5257ae9360eb881ec3628319cef3?s=48&d=retro)||6<br><br>**[hefish](https://www.v2ex.com/member/hefish)**      5 小时 27 分钟前<br><br>哈哈哈， 我选 sql2000 。咳咳。。。|

|   |   |   |
|---|---|---|
|![8355](https://cdn.v2ex.com/avatar/dbd3/6c22/210254_normal.png?m=1715407255)||7<br><br>**[8355](https://www.v2ex.com/member/8355)**      5 小时 25 分钟前<br><br>mysql 已经不是以前的 mysql 了，支持 mysql 协议的数据库很多，性能也有很好的，扩展和迁移方案也很多。|

|   |   |   |
|---|---|---|
|![iFerrari860](https://cdn.v2ex.com/gravatar/e92725d52e705b071602088eb5adb5bb?s=48&d=retro)||8<br><br>**[iFerrari860](https://www.v2ex.com/member/iFerrari860)**      5 小时 24 分钟前<br><br>之前业务系统从 mysql 转 pg ，改到冒烟。。想轻松就无脑选 mysql.|

|   |   |   |
|---|---|---|
|![beneo](https://cdn.v2ex.com/avatar/cd24/73ee/61206_normal.png?m=1708478806)||9<br><br>**[beneo](https://www.v2ex.com/member/beneo)**      5 小时 23 分钟前<br><br>pg ，真的，从 0 到 1000 都可以，云，本地，包括信创过渡都没问题|

|   |   |   |
|---|---|---|
|![qqjt](https://cdn.v2ex.com/avatar/8465/c966/65237_normal.png?m=1713941227)||10<br><br>**[qqjt](https://www.v2ex.com/member/qqjt)**      5 小时 21 分钟前<br><br>……哥们你来收集话术的吗？这类讨论网上多的是啊|

|   |   |   |
|---|---|---|
|![chendy](https://cdn.v2ex.com/avatar/0515/645c/264467_normal.png?m=1730183207)||12<br><br>**[chendy](https://www.v2ex.com/member/chendy)**      5 小时 18 分钟前<br><br>政策法规 > 领导喜好 > 使用成本 >> 其他|

|   |   |   |
|---|---|---|
|![gimp](https://cdn.v2ex.com/avatar/d03f/fbc5/136804_normal.png?m=1444699066)||13<br><br>**[gimp](https://www.v2ex.com/member/gimp)**      5 小时 17 分钟前<br><br>没啥理由，我投 PG 一票|

|   |   |   |
|---|---|---|
|![fffq](https://cdn.v2ex.com/gravatar/c532ce725b10d767f990b74d8780eb9a?s=48&d=retro)||17<br><br>**[fffq](https://www.v2ex.com/member/fffq)**      4 小时 49 分钟前<br><br>团队对哪个熟悉选哪个|

|   |   |   |
|---|---|---|
|![encro](https://cdn.v2ex.com/avatar/436f/d60a/267961_normal.png?m=1711446400)||18<br><br>**[encro](https://www.v2ex.com/member/encro)**      4 小时 47 分钟前<br><br>那么必须是扩展有几百个的 pg 啊。<br><br>装一个扩展，就变身了！！！|

|   |   |   |
|---|---|---|
|![shiny](https://cdn.v2ex.com/avatar/8909/a6e3/5670_normal.png?m=1700478994)||19<br><br>**[shiny](https://www.v2ex.com/member/shiny)**      4 小时 46 分钟前<br><br>postgresql ，运维更容易点|

|   |   |   |
|---|---|---|
|![ymmud](https://cdn.v2ex.com/gravatar/421bcae8843e5c706437ccf09e1f7fed?s=48&d=retro)||20<br><br>**[ymmud](https://www.v2ex.com/member/ymmud)**      4 小时 44 分钟前<br><br>pg,如果哪天要转国产化，会少一些痛苦|

|   |   |   |
|---|---|---|
|![wangtian2020](https://cdn.v2ex.com/avatar/5f94/b385/510746_normal.png?m=1731907010)||23<br><br>**[wangtian2020](https://www.v2ex.com/member/wangtian2020)**      4 小时 4 分钟前<br><br>mysql 的时序支持度不如 pgsql ，所以 pgsql 完爆 mysql|

|   |   |   |
|---|---|---|
|![dbskcnc](https://cdn.v2ex.com/avatar/144c/f058/230943_normal.png?m=1659945817)||25<br><br>**[dbskcnc](https://www.v2ex.com/member/dbskcnc)**      3 小时 58 分钟前<br><br>sql server 2000 转 pg 8 后从没用过其它数据库，pg 实在太省心了|

|   |   |   |
|---|---|---|
|![hingle](https://cdn.v2ex.com/gravatar/f9f88ca495ac9e2ec23304fe4f3478a2?s=48&d=retro)||26<br><br>**[hingle](https://www.v2ex.com/member/hingle)**      3 小时 57 分钟前<br><br>一般问这种问题的，大多数都是两者都不熟。<br><br>建议选 mysql ，出问题搜搜问问都好解决，等熟悉了想换 pg 也不迟。|

|   |   |   |
|---|---|---|
|![murmur](https://cdn.v2ex.com/avatar/5141/1e1f/161642_normal.png?m=1462262183)||28<br><br>**[murmur](https://www.v2ex.com/member/murmur)**      3 小时 53 分钟前<br><br>秒选 postgres ，信创的东西都是 postgres 翻版|

|   |   |   |
|---|---|---|
|![billbob](https://cdn.v2ex.com/avatar/069b/b573/661574_normal.png?m=1735009578)||30<br><br>**[billbob](https://www.v2ex.com/member/billbob)**      3 小时 49 分钟前<br><br>PG 原生支持 全文搜索, 数据统计物化视图洗数据, AI 支持空间数据'向量数据,中文分词,免费,大量的开源扩展.|

|   |   |   |
|---|---|---|
|![Leviathann](https://cdn.v2ex.com/gravatar/d3b22910a49ecf620ab67790d7f594eb?s=48&d=retro)||32<br><br>**[Leviathann](https://www.v2ex.com/member/Leviathann)**      3 小时 45 分钟前<br><br>用 pg 的大部分项目可以只用 pg  <br>用 mysql 还得另外加一堆东西|

|   |   |   |
|---|---|---|
|![Geon97](https://cdn.v2ex.com/avatar/2527/c5bc/583897_normal.png?m=1736668779)||34<br><br>**[Geon97](https://www.v2ex.com/member/Geon97)**      3 小时 34 分钟前<br><br>工作还是 MySQL 省心，虽然还是 pg 好，但我工作的话还是选 mysql ，自己用就选 pg|

|   |   |   |
|---|---|---|
|![AdamMing](https://cdn.v2ex.com/avatar/abb2/e9f9/197428_normal.png?m=1652841479)||35<br><br>**[AdamMing](https://www.v2ex.com/member/AdamMing)**      3 小时 33 分钟前<br><br>以后可能因为信创转库的话，推荐用 pg 。|

|   |   |   |
|---|---|---|
|![zoharSoul](https://cdn.v2ex.com/avatar/e8f4/7f9a/486945_normal.png?m=1639325273)||36<br><br>**[zoharSoul](https://www.v2ex.com/member/zoharSoul)**      3 小时 31 分钟前<br><br>mysql  <br>postgre 那个设置自动更新 update_time 非要设个触发器, 简直服了|

|   |   |   |
|---|---|---|
|![iminto](https://cdn.v2ex.com/avatar/2555/b8e9/26143_normal.png?m=1711523900)||37<br><br>**[iminto](https://www.v2ex.com/member/iminto)**      1 小时 59 分钟前 via Android<br><br>菜就 mysql  <br>水平高就 pg|

|   |   |   |
|---|---|---|
|![momo2789](https://cdn.v2ex.com/gravatar/2cbbfea22c30c65427c8cff91d74fc2e?s=48&d=retro)||38<br><br>**[momo2789](https://www.v2ex.com/member/momo2789)**      1 小时 35 分钟前<br><br>当然无脑 postgresql ，mysql 可以丢进历史的垃圾桶了。|

|   |   |   |
|---|---|---|
|![mmmhhhddd](https://cdn.v2ex.com/gravatar/68427e9a2640c9aa076a56ddba6cd639?s=48&d=retro)||39<br><br>**[mmmhhhddd](https://www.v2ex.com/member/mmmhhhddd)**      1 小时 26 分钟前<br><br>如果没啥人用的简单的数据库就 mysql,如果奔着要发展起来就 postgresql ，本人项目 pg 集群 16c32g * 50 台|

|   |   |   |
|---|---|---|
|![bjfane](https://cdn.v2ex.com/gravatar/f09dfe4a71eb5922469f844fb8b37816?s=48&d=retro)||40<br><br>**[bjfane](https://www.v2ex.com/member/bjfane)**      1 小时 17 分钟前<br><br>@[murmur](https://www.v2ex.com/member/murmur) 也不全是，oceanbase 不是吧，虽然是分布式， 但是符合信创，且兼容 mysql 的程序 ：）|

|   |   |   |
|---|---|---|
|![seansong](https://cdn.v2ex.com/gravatar/13b01d3f97cd23d88c602a486ccbc63c?s=48&d=retro)||41<br><br>**[seansong](https://www.v2ex.com/member/seansong)**      27 分钟前<br><br>熟悉哪个用哪个，客户要求哪个用哪个，领导要求哪个用哪个|

|   |   |   |
|---|---|---|
|![wencan](https://cdn.v2ex.com/avatar/0690/9014/5813_normal.png?m=1738839319)||42<br><br>**[wencan](https://www.v2ex.com/member/wencan)**      20 分钟前<br><br>之前都是 mysql ，现在 pg ，一样的，sql 稍有不同而已|