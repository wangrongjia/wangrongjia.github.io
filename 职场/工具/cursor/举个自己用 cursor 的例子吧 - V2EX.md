---
link: https://www.v2ex.com/t/1110401
site: V2EX
date: 2025-02-10T17:31
excerpt: 程序员 - @idblife - 看到大家讨论 cursor
  那么激烈，说个自己的实际例子吧。有个自己看的小网站https://qingbuyaohaixiu.com/（ nsfw ）之前是用 django 写的，感觉
twitter: https://twitter.com/@V2EX
slurped: 2025-02-28T17:15
title: 举个自己用 cursor 的例子吧 - V2EX
---
   [idblife](/member/idblife) · 17 天前 · 8297 次点击

看到大家讨论 cursor 那么激烈，说个自己的实际例子吧。  
有个自己看的小网站  
[https://qingbuyaohaixiu.com/](https://qingbuyaohaixiu.com/)  
（ nsfw ）之前是用 django 写的，  
感觉部署不太方便，用 cursor 给改成了 gin 框架，背景信息给的够足再加上功能简单，用了半个多小时吧。  
感觉还是不错的。

第 1 条附言  ·  17 天前

哦，又用了半个小时加上了发帖自动同步推特&电报  
  
[https://x.com/qingbuyaohaixiu](https://x.com/qingbuyaohaixiu)  
  
[https://t.me/qingbuyaohaixiu](https://t.me/qingbuyaohaixiu)

第 2 条附言  ·  16 天前

@[freewind](/member/freewind) #80  
提出了需求“提个建议，点击放大后，加个上一个，下一个按钮. 最好是可以左，右箭头翻页”  
  
用 cursor 花了不到一分钟搞定，提示词就是直接复制的这句话。  
反正比我自己实现要快。

第 3 条附言  ·  1 天前

cursor + claude sonnet 3.7 thinking  
我觉得已经能对得起 copilot 这个称号了

[

Cursor](/tag/Cursor)[

gin](/tag/gin)[

热更新](/tag/热更新)

95 条回复  **•**  2025-02-12 18:59:22 +08:00

|   |   |   |
|---|---|---|
|![jisuowei](https://cdn.v2ex.com/gravatar/2a8041d98ce73145e52dedc652ae87df?s=48&d=retro)||1<br><br>**[jisuowei](/member/jisuowei)**  <br><br>   17 天前<br><br>mmp|

|   |   |   |
|---|---|---|
|![lepig](https://cdn.v2ex.com/avatar/1312/8f39/51948_normal.png?m=1736489725)||2<br><br>**[lepig](/member/lepig)**  <br><br>   17 天前<br><br>WC|

|   |   |   |
|---|---|---|
|![Kakarrot](https://cdn.v2ex.com/avatar/762f/c737/232500_normal.png?m=1718073317)||3<br><br>**[Kakarrot](/member/Kakarrot)**  <br><br>   17 天前<br><br>好活，当赏！|

|   |   |   |
|---|---|---|
|![ksedz](https://cdn.v2ex.com/avatar/3c52/05b5/189148_normal.png?m=1554198403)||4<br><br>**[ksedz](/member/ksedz)**  <br><br>   17 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 8<br><br>你那个 nsfw 能不能不要换行|

|   |   |   |
|---|---|---|
|![wei2629](https://cdn.v2ex.com/gravatar/471d7c689ca3aea31863ebcab4e6cab6?s=48&d=retro)||5<br><br>**[wei2629](/member/wei2629)**  <br><br>   17 天前<br><br>我擦 。这点开。|

|   |   |   |
|---|---|---|
|![idblife](https://cdn.v2ex.com/avatar/a95c/4050/14375_normal.png?m=1646796005)||6<br><br>**[idblife](/member/idblife)**  <br><br>OP<br><br>   17 天前<br><br>@[ksedz](/member/ksedz)  <br>哈哈|

|   |   |   |
|---|---|---|
|![idblife](https://cdn.v2ex.com/avatar/a95c/4050/14375_normal.png?m=1646796005)||7<br><br>**[idblife](/member/idblife)**  <br><br>OP<br><br>   17 天前<br><br>nsfw 换行专治看文不仔细|

|   |   |   |
|---|---|---|
|![fakecoder](https://cdn.v2ex.com/avatar/1775/f2cd/169307_normal.png?m=1674440985)||8<br><br>**[fakecoder](/member/fakecoder)**  <br><br>   17 天前<br><br>没看到 nsfw ，，，直接打开了。。|

|   |   |   |
|---|---|---|
|![SilentFlute](https://cdn.v2ex.com/gravatar/7462d73b15a1663b0a69f0af69405e50?s=48&d=retro)||9<br><br>**[SilentFlute](/member/SilentFlute)**  <br><br>   17 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>nsfw: not safe for work[![](https://i.imgur.com/agAJ0Rd.png)](https://i.imgur.com/agAJ0Rd.png)|

|   |   |   |
|---|---|---|
|![xuelang](https://cdn.v2ex.com/avatar/b568/e3db/35624_normal.png?m=1733280705)||10<br><br>**[xuelang](/member/xuelang)**  <br><br>   17 天前<br><br>[https://gallery.selfboot.cn/zh/games/sokoban](https://gallery.selfboot.cn/zh/games/sokoban)  <br>这个如何？  <br>  <br>其实我整个站点的所有页面都是 Cursor 和 Claude3,5 写的哈哈哈|

|   |   |   |
|---|---|---|
|![mMartin](https://cdn.v2ex.com/avatar/b391/300f/315881_normal.png?m=1737547653)||11<br><br>**[mMartin](/member/mMartin)**  <br><br>   17 天前<br><br>[https://github.com/mrtian2016/hass-panel](https://github.com/mrtian2016/hass-panel) 99%的代码都是 cursor 写的|

|   |   |   |
|---|---|---|
|![74123gzy](https://cdn.v2ex.com/avatar/b55a/34b8/178479_normal.png?m=1699634119)||12<br><br>**[74123gzy](/member/74123gzy)**  <br><br>   17 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 2<br><br>你那个 NSFW 能不能写在开头，用大写，再多打几个叹号|

|   |   |   |
|---|---|---|
|![imjiaoyuan](https://cdn.v2ex.com/avatar/b6d7/52af/713427_normal.png?m=1729754946)||13<br><br>**[imjiaoyuan](/member/imjiaoyuan)**  <br><br>   17 天前<br><br>当赏！|

|   |   |   |
|---|---|---|
|![vcbal](https://cdn.v2ex.com/avatar/1bc5/ab0d/460036_normal.png?m=1731292935)||14<br><br>**[vcbal](/member/vcbal)**  <br><br>   17 天前<br><br>我都直接跳过 nsfw 。。。你这故意的吧|

|   |   |   |
|---|---|---|
|![jackielllv7158](https://cdn.v2ex.com/gravatar/7f38f0890349b02470ab45b670df75ee?s=48&d=retro)||15<br><br>**[jackielllv7158](/member/jackielllv7158)**  <br><br>   17 天前<br><br>妈的，在公司打开了|

|   |   |   |
|---|---|---|
|![vincentWdp](https://cdn.v2ex.com/gravatar/e8f4a89b48b07934dd9196059a252ed2?s=48&d=retro)||16<br><br>**[vincentWdp](/member/vincentWdp)**  <br><br>   17 天前<br><br>很简单的代码, 监听苹果电脑, 用户复制事件, 用 rust 调的 oc 的包: [https://github.com/DejavuVin/copy_event_listener](https://github.com/DejavuVin/copy_event_listener)|

|   |   |   |
|---|---|---|
|![idblife](https://cdn.v2ex.com/avatar/a95c/4050/14375_normal.png?m=1646796005)||17<br><br>**[idblife](/member/idblife)**  <br><br>OP<br><br>   17 天前<br><br>@[jackielllv7158](/member/jackielllv7158)  <br>被美女同事看见了吗|

|   |   |   |
|---|---|---|
|![wtf12138](https://cdn.v2ex.com/avatar/bd3b/bb5e/373969_normal.png?m=1658826064)||18<br><br>**[wtf12138](/member/wtf12138)**  <br><br>   17 天前<br><br>我还以为多大尺度呢 我当着领导们看|

|   |   |   |
|---|---|---|
|![idblife](https://cdn.v2ex.com/avatar/a95c/4050/14375_normal.png?m=1646796005)||19<br><br>**[idblife](/member/idblife)**  <br><br>OP<br><br>   17 天前 via iPhone<br><br>@[wtf12138](/member/wtf12138)  <br>你就是领导吧|

|   |   |   |
|---|---|---|
|![aquarz](https://cdn.v2ex.com/gravatar/31254cbbcb779429fe30c51fda2b7a24?s=48&d=retro)||20<br><br>**[aquarz](/member/aquarz)**  <br><br>   17 天前<br><br>第一个我很喜欢|

|   |   |   |
|---|---|---|
|![JasperYanky](https://cdn.v2ex.com/gravatar/5c480629589fed43bd8780fe5f392341?s=48&d=retro)||21<br><br>**[JasperYanky](/member/JasperYanky)**  <br><br>   17 天前<br><br>哪里爬的|

|   |   |   |
|---|---|---|
|![Kruti](https://cdn.v2ex.com/gravatar/993a3d15da8c43b56b13c41a13fed791?s=48&d=retro)||22<br><br>**[Kruti](/member/Kruti)**  <br><br>   17 天前<br><br>好活！就是裁剪了，然后需要翻页。建议改瀑布流，像 Pinterest 那样。|

|   |   |   |
|---|---|---|
|![q1102389095](https://cdn.v2ex.com/avatar/ab84/9b11/722517_normal.png?m=1736650173)||23<br><br>**[q1102389095](/member/q1102389095)**  <br><br>   17 天前<br><br>c|

|   |   |   |
|---|---|---|
|![hnbcinfo](https://cdn.v2ex.com/avatar/7631/1c3a/209998_normal.png?m=1678714172)||24<br><br>**[hnbcinfo](/member/hnbcinfo)**  <br><br>   17 天前<br><br>能不能说下用 cursor 重构你这个站的使用流程。我最近也想用 cursor 搞搞，不知如何下手|

|   |   |   |
|---|---|---|
|![TimPeake](https://cdn.v2ex.com/avatar/9da1/d8ae/352325_normal.png?m=1708952363)||25<br><br>**[TimPeake](/member/TimPeake)**  <br><br>   17 天前<br><br>友情建议：可以去爬小红书、知乎的帖子 [![](https://i.imgur.com/agAJ0Rd.png)](https://i.imgur.com/agAJ0Rd.png)|

|   |   |   |
|---|---|---|
|![ncbdwss](https://cdn.v2ex.com/gravatar/fe73b0e6cf5940b1b26d67ffb74b4fc1?s=48&d=retro)||26<br><br>**[ncbdwss](/member/ncbdwss)**  <br><br>   17 天前<br><br>这域名，很熟悉。。从豆瓣小组那个时期过来的？|

|   |   |   |
|---|---|---|
|![Dlin](https://cdn.v2ex.com/avatar/f9f1/2a31/470824_normal.png?m=1697015553)||27<br><br>**[Dlin](/member/Dlin)**  <br><br>   17 天前<br><br>我，在公司！|

|   |   |   |
|---|---|---|
|![Dragonphy](https://cdn.v2ex.com/avatar/4dd8/adbe/473553_normal.png?m=1658504639)||28<br><br>**[Dragonphy](/member/Dragonphy)**  <br><br>   17 天前<br><br>NSFW ，可恶啊，在上班呢|

|   |   |   |
|---|---|---|
|![x2ve](https://cdn.v2ex.com/gravatar/4ab85a18083ab427704b1e0035547e94?s=48&d=retro)||29<br><br>**[x2ve](/member/x2ve)**  <br><br>   17 天前<br><br>自己看小说的网站|

|   |   |   |
|---|---|---|
|![pecsj](https://cdn.v2ex.com/gravatar/c2eea7a03df47013ccadd41227660046?s=48&d=retro)||30<br><br>**[pecsj](/member/pecsj)**  <br><br>   17 天前<br><br>吓我一跳，还好我是老 fps 玩家|

|   |   |   |
|---|---|---|
|![BeforeTooLate](https://cdn.v2ex.com/avatar/0dae/9391/455039_normal.png?m=1740358952)||31<br><br>**[BeforeTooLate](/member/BeforeTooLate)**  <br><br>   17 天前<br><br>可以详细展开说说怎么做到的，比如包括后端管理，数据库表也是 cursor 写的吗？|

|   |   |   |
|---|---|---|
|![fangxisama](https://cdn.v2ex.com/avatar/0918/86de/250976_normal.png?m=1733119195)||32<br><br>**[fangxisama](/member/fangxisama)**  <br><br>   17 天前<br><br>友情提醒：NSFW ！ NSFW ！ NSFW ！ NSFW ！ NSFW ！|

|   |   |   |
|---|---|---|
|![lwldcr](https://cdn.v2ex.com/avatar/239a/b3a7/250182_normal.png?m=1728368177)||33<br><br>**[lwldcr](/member/lwldcr)**  <br><br>   17 天前<br><br>你这是搬运以前豆瓣的请不要害羞小组吗 [![](https://i.imgur.com/agAJ0Rd.png)](https://i.imgur.com/agAJ0Rd.png) 感觉不是 尺度小了点|

|   |   |   |
|---|---|---|
|![ohoh](https://cdn.v2ex.com/gravatar/eebade5db3a4bc344a66749f387c1a6a?s=48&d=retro)||34<br><br>**[ohoh](/member/ohoh)**  <br><br>   17 天前<br><br>没点开，请问 NSFW 是什么|

|   |   |   |
|---|---|---|
|![wudalang0617](https://cdn.v2ex.com/avatar/c910/76e8/554854_normal.png?m=1734943141)||35<br><br>**[wudalang0617](/member/wudalang0617)**  <br><br>   17 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>@[ohoh](/member/ohoh) Not Safe For Work|

|   |   |   |
|---|---|---|
|![Daotin](https://cdn.v2ex.com/avatar/0053/93d4/468371_normal.png?m=1720236030)||36<br><br>**[Daotin](/member/Daotin)**  <br><br>   17 天前<br><br>做了一个微信读书网页版主题增强 Tampermonkey 脚本： [https://www.v2ex.com/t/1110349](https://www.v2ex.com/t/1110349)|

|   |   |   |
|---|---|---|
|![idblife](https://cdn.v2ex.com/avatar/a95c/4050/14375_normal.png?m=1646796005)||37<br><br>**[idblife](/member/idblife)**  <br><br>OP<br><br>   17 天前<br><br>@[lwldcr](/member/lwldcr)  <br>请不要害羞小组 太刺激了，可惜关闭了|

|   |   |   |
|---|---|---|
|![idblife](https://cdn.v2ex.com/avatar/a95c/4050/14375_normal.png?m=1646796005)||38<br><br>**[idblife](/member/idblife)**  <br><br>OP<br><br>   17 天前<br><br>@[BeforeTooLate](/member/BeforeTooLate)  <br>表结构是我自己设计的，cursor 很容易就生成了增删改查和对接 x ，电报|

|   |   |   |
|---|---|---|
|![BeforeTooLate](https://cdn.v2ex.com/avatar/0dae/9391/455039_normal.png?m=1740358952)||39<br><br>**[BeforeTooLate](/member/BeforeTooLate)**  <br><br>   17 天前<br><br>@[idblife](/member/idblife) 后台管理呢，如何对接前台，也可以吗？|

|   |   |   |
|---|---|---|
|![kristofer](https://cdn.v2ex.com/gravatar/80e4f89ea8f40ea11c123195f69a671d?s=48&d=retro)||40<br><br>**[kristofer](/member/kristofer)**  <br><br>   17 天前<br><br>我回复个不一样的，nsfw 有点名不副实，强度太低了啊，建议加大强度（ doge|

|   |   |   |
|---|---|---|
|![idblife](https://cdn.v2ex.com/avatar/a95c/4050/14375_normal.png?m=1646796005)||41<br><br>**[idblife](/member/idblife)**  <br><br>OP<br><br>   17 天前 via iPhone<br><br>@[BeforeTooLate](/member/BeforeTooLate)  <br>增删改查就包括了所有业务逻辑了  <br>增删改算后台管理功能  <br>查算前台应用|

|   |   |   |
|---|---|---|
|![hunterzhang86](https://cdn.v2ex.com/gravatar/28d9b3eb609bf89b3fbd5f0c8dd25dd4?s=48&d=retro)||42<br><br>**[hunterzhang86](/member/hunterzhang86)**  <br><br>   17 天前<br><br>[https://www.myaiexp.com/zh](https://www.myaiexp.com/zh)  <br>  <br>这个 AI 的导航站都是用 Cursor 写的。|

|   |   |   |
|---|---|---|
|![BeforeTooLate](https://cdn.v2ex.com/avatar/0dae/9391/455039_normal.png?m=1740358952)||43<br><br>**[BeforeTooLate](/member/BeforeTooLate)**  <br><br>   17 天前<br><br>@[idblife](/member/idblife) 哦，我可能一开始以为把后台 UI 框架都写好了，你这么说我明白了，相当于接口都给你写好了，具体后台自己套用现成框架模板就行了？|

|   |   |   |
|---|---|---|
|![unclejimao](https://cdn.v2ex.com/avatar/3a40/dd52/412579_normal.png?m=1557906472)||44<br><br>**[unclejimao](/member/unclejimao)**  <br><br>   17 天前<br><br>哥们，加个 FBI Warning 吧，我直接在办公室打开了，还好旁边同事在认真工作。。。|

|   |   |   |
|---|---|---|
|![CouleurVVEX](https://cdn.v2ex.com/avatar/4a65/f0a5/614443_normal.png?m=1726284949)||45<br><br>**[CouleurVVEX](/member/CouleurVVEX)**  <br><br>   17 天前<br><br>@[kristofer](/member/kristofer) +1 ，这强度太低了|

|   |   |   |
|---|---|---|
|![idblife](https://cdn.v2ex.com/avatar/a95c/4050/14375_normal.png?m=1646796005)||46<br><br>**[idblife](/member/idblife)**  <br><br>OP<br><br>   17 天前<br><br>@[BeforeTooLate](/member/BeforeTooLate)  <br>web 页面展示也是一起写好的|

|   |   |   |
|---|---|---|
|![zzping](https://cdn.v2ex.com/avatar/dc32/2f37/460179_normal.png?m=1682913327)||47<br><br>**[zzping](/member/zzping)**  <br><br>   17 天前<br><br>计划有变，打工暂停|

|   |   |   |
|---|---|---|
|![jhiiii](https://cdn.v2ex.com/gravatar/0f198fcdeec0ef149efa574b635d3b78?s=48&d=retro)||48<br><br>**[jhiiii](/member/jhiiii)**  <br><br>   17 天前<br><br>0 视频相关基础，ffmpeg 只限于知道名字和功能。  <br>依靠 cursor 写了一份自动、批量、合并、剪辑、字幕、绿幕等的工具  <br>全程提好需求，身份是懂产品的产品经理，全程 0 手写代码|

|   |   |   |
|---|---|---|
|![tomatocici2333](https://cdn.v2ex.com/avatar/1ea5/b0c8/495760_normal.png?m=1668689912)||49<br><br>**[tomatocici2333](/member/tomatocici2333)**  <br><br>   17 天前<br><br>@[unclejimao](/member/unclejimao) #44 [![](https://i.imgur.com/cPNPYD5.png)](https://i.imgur.com/cPNPYD5.png) 我也是还好我手快|

|   |   |   |
|---|---|---|
|![snitfk](https://cdn.v2ex.com/gravatar/fd1fa696e8ae56c3f1473a34922d5c2d?s=48&d=retro)||50<br><br>**[snitfk](/member/snitfk)**  <br><br>   17 天前<br><br>好活。|

|   |   |   |
|---|---|---|
|![beneo](https://cdn.v2ex.com/avatar/cd24/73ee/61206_normal.png?m=1708478806)||51<br><br>**[beneo](/member/beneo)**  <br><br>   17 天前<br><br>内容比技术好|

|   |   |   |
|---|---|---|
|![55wHD3PbDHiewGz1](https://cdn.v2ex.com/static/img/avatar_normal.png)||52<br><br>**[55wHD3PbDHiewGz1](/member/55wHD3PbDHiewGz1)**  <br><br>   17 天前<br><br>Django 换 Gin 都能做吗，Cursor 有点东西啊，有仓库吗观摩下|

|   |   |   |
|---|---|---|
|![hallomou](https://cdn.v2ex.com/gravatar/de1416246af093b870bf6a720f65d4d3?s=48&d=retro)||53<br><br>**[hallomou](/member/hallomou)**  <br><br>   17 天前<br><br>[https://github.com/bin64/Clash-Dash](https://github.com/bin64/Clash-Dash)|

|   |   |   |
|---|---|---|
|![idblife](https://cdn.v2ex.com/avatar/a95c/4050/14375_normal.png?m=1646796005)||54<br><br>**[idblife](/member/idblife)**  <br><br>OP<br><br>   17 天前<br><br>@[OrenZ](/member/OrenZ)  <br>主要是功能简单，单个函数转换基本都是一次成功|

|   |   |   |
|---|---|---|
|![bboring](https://cdn.v2ex.com/avatar/6a5e/3590/637277_normal.png?m=1740359634)||55<br><br>**[bboring](/member/bboring)**  <br><br>   17 天前<br><br>擦 同事看到了|

|   |   |   |
|---|---|---|
|![huolong](https://cdn.v2ex.com/gravatar/9e79fd45e2df2093e30cfa93d31b88c3?s=48&d=retro)||56<br><br>**[huolong](/member/huolong)**  <br><br>   17 天前<br><br>[https://chromewebstore.google.com/detail/tab-assistant/ggefhfojijgijhkhegnbhekgccbgmkjf](https://chromewebstore.google.com/detail/tab-assistant/ggefhfojijgijhkhegnbhekgccbgmkjf) 我用他写了个 Chrome 插件，可以吧要打开的网址放到一个列表里，一次性全部打开列表里的标签。|

|   |   |   |
|---|---|---|
|![dongdongdong](https://cdn.v2ex.com/avatar/6ff2/4ef6/391699_normal.png?m=1727572468)||57<br><br>**[dongdongdong](/member/dongdongdong)**  <br><br>   17 天前<br><br>图片数据哪里获取的|

|   |   |   |
|---|---|---|
|![levywang](https://cdn.v2ex.com/gravatar/28a0b6038d0ce68b7ce5fc659a0e00b1?s=48&d=retro)||58<br><br>**[levywang](/member/levywang)**  <br><br>   17 天前<br><br>前后端不分离的吗|

|   |   |   |
|---|---|---|
|![JRay](https://cdn.v2ex.com/avatar/b9b1/7c6a/261032_normal.png?m=1715413507)||59<br><br>**[JRay](/member/JRay)**  <br><br>   17 天前<br><br>牛批|

|   |   |   |
|---|---|---|
|![PeiXyJ](https://cdn.v2ex.com/avatar/cff1/3947/410199_normal.png?m=1605513396)||60<br><br>**[PeiXyJ](/member/PeiXyJ)**  <br><br>   17 天前<br><br>只能说精彩,准备离职了.|

|   |   |   |
|---|---|---|
|![superBearL](https://cdn.v2ex.com/avatar/dd87/776e/513088_normal.png?m=1616474490)||61<br><br>**[superBearL](/member/superBearL)**  <br><br>   17 天前<br><br>友情提示各位，不要在家里打开，在办公室摸鱼的时候看一下可以|

|   |   |   |
|---|---|---|
|![54xavier](https://cdn.v2ex.com/avatar/95d6/a971/446888_normal.png?m=1733565230)||62<br><br>**[54xavier](/member/54xavier)**  <br><br>   17 天前<br><br>不是，就这也配 nsfw ？就这？就这？  <br>  <br>好吧，后面几页确实有几张符合，但是第一页打开真的没觉得 nsfw|

|   |   |   |
|---|---|---|
|![Promtheus](https://cdn.v2ex.com/avatar/e4b7/c4b0/602067_normal.png?m=1678624705)||63<br><br>**[Promtheus](/member/Promtheus)**  <br><br>   17 天前<br><br>数据哪来的 技术不重要 重要的是数据啊|

|   |   |   |
|---|---|---|
|![hugozach](https://cdn.v2ex.com/avatar/4e55/2e82/590166_normal.png?m=1736767498)||64<br><br>**[hugozach](/member/hugozach)**  <br><br>   17 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 2<br><br>说实话啊，这 cursor 啊，没那么神。您要是想拿它糊弄糊弄自己，再糊弄糊弄领导，那还行，凑合能用。可您要是真打算用它干点复杂的活儿，那问题就来了——各种小毛病、报错接二连三地蹦出来，跟放鞭炮似的。  <br>  <br>这时候啊，您就得耐着性子慢慢调，一点一点去解决那些小问题。可是呢，这提示词写起来可不容易啊！您得描述一大堆场景，什么“如果用户点击这里”“当数据传过来的时候”，巴拉巴拉说个没完。结果呢？改了半天效果还是不咋地，气人不？  <br>  <br>更闹心的是，如果您对 cursor 生成的代码一窍不通，那恭喜您了，直接进入上述步骤的无限循环吧！一遍又一遍地试，一遍又一遍地错，最后把自己折腾得够呛，也没见多大成效。  <br>  <br>但如果您懂代码，情况也好不到哪儿去。为啥呢？因为您得从头到尾把 cursor 写的代码看明白，一行一行检查，生怕漏掉啥坑。这么一来二去，您是轻松了，懒了，不想动脑子了。长此以往啊，您的技术不仅没巩固住，反而可能退步了。这不是害了自己嘛！  <br>  <br>所以啊，咱得明白一个道理：工具终究是工具，它只能帮咱们省点力气，不能替咱们思考。就像我师父以前教我的，“学艺先学做人，练功还得靠勤”。您要是光指望这些智能工具，早晚有一天会发现自己成了无源之水、无本之木。  <br>  <br>我建议啊，用 cursor 可以，但别太依赖它。该琢磨的地方还得琢磨，该动手的时候还得动手。毕竟，真正的本事在脑子里，在手上，而不是在屏幕上那一串串自动生成的字符里头。|

|   |   |   |
|---|---|---|
|![IMZQZ](https://cdn.v2ex.com/gravatar/de7fbc461e509655c49de41775bfb807?s=48&d=retro)||65<br><br>**[IMZQZ](/member/IMZQZ)**  <br><br>   17 天前<br><br>@[54xavier](/member/54xavier) +1 满怀期待的打开 失落的离开 眼睛里的泪花在滚动|

|   |   |   |
|---|---|---|
|![dzdh](https://cdn.v2ex.com/avatar/1683/7ebf/226307_normal.png?m=1664637691)||66<br><br>**[dzdh](/member/dzdh)**  <br><br>   17 天前<br><br>没懂。哪里 nsfw 了。|

|   |   |   |
|---|---|---|
|![idblife](https://cdn.v2ex.com/avatar/a95c/4050/14375_normal.png?m=1646796005)||67<br><br>**[idblife](/member/idblife)**  <br><br>OP<br><br>   17 天前<br><br>@[levywang](/member/levywang)  <br>请问在这种类型这种规模的项目里，前后端分离的好处有哪些？|

|   |   |   |
|---|---|---|
|![bzj](https://cdn.v2ex.com/gravatar/268a4934d958d762bdfd741f2ee4c344?s=48&d=retro)||68<br><br>**[bzj](/member/bzj)**  <br><br>   17 天前<br><br>现在推广帖挺会蹭热度的|

|   |   |   |
|---|---|---|
|![xing7673](https://cdn.v2ex.com/gravatar/92699c48c8ccd17d47409bef8f1794be?s=48&d=retro)||69<br><br>**[xing7673](/member/xing7673)**  <br><br>   17 天前<br><br>不是，我还以为是啥呢  <br>这有啥 NSFW|

|   |   |   |
|---|---|---|
|![idblife](https://cdn.v2ex.com/avatar/a95c/4050/14375_normal.png?m=1646796005)||70<br><br>**[idblife](/member/idblife)**  <br><br>OP<br><br>   17 天前<br><br>@[bzj](/member/bzj)  <br>自己看的网站，推广个毛线啊。。。|

|   |   |   |
|---|---|---|
|![ZongjunLan](https://cdn.v2ex.com/avatar/2eb4/3319/331017_normal.png?m=1532320171)||71<br><br>**[ZongjunLan](/member/ZongjunLan)**  <br><br>   17 天前<br><br>rnidaye|

|   |   |   |
|---|---|---|
|![ciki](https://cdn.v2ex.com/gravatar/7a0c24f697ea1587001c36d00039b60f?s=48&d=retro)||72<br><br>**[ciki](/member/ciki)**  <br><br>   17 天前<br><br>幸好反应快|

|   |   |   |
|---|---|---|
|![zhangkui](https://cdn.v2ex.com/avatar/1bd1/cf40/440795_normal.png?m=1735625356)||73<br><br>**[zhangkui](/member/zhangkui)**  <br><br>   17 天前<br><br>浏览器插件：codebox-一键复制代码/下载文章 的这个网站 [https://www.code-box.fun/](https://www.code-box.fun/) 基本上都是的吧！|

|   |   |   |
|---|---|---|
|![fyxtc](https://cdn.v2ex.com/avatar/efd6/53c4/132693_normal.png?m=1733188514)||74<br><br>**[fyxtc](/member/fyxtc)**  <br><br>   17 天前<br><br>就这？各大跳舞区封面尺度都比你这大|

|   |   |   |
|---|---|---|
|![PaulSamuelson](https://cdn.v2ex.com/avatar/34e3/99df/595818_normal.png?m=1718186819)||75<br><br>**[PaulSamuelson](/member/PaulSamuelson)**  <br><br>   17 天前<br><br>果然瑟瑟是第一生产力|

|   |   |   |
|---|---|---|
|![ovtfkw](https://cdn.v2ex.com/gravatar/25efca467527b262608bc12f80387112?s=48&d=retro)||76<br><br>**[ovtfkw](/member/ovtfkw)**  <br><br>   17 天前 via iPhone<br><br>现在的软广都换着花样了|

|   |   |   |
|---|---|---|
|![shmilypeter](https://cdn.v2ex.com/gravatar/618607307eb0a82e539c89262378e771?s=48&d=retro)||77<br><br>**[shmilypeter](/member/shmilypeter)**  <br><br>   17 天前<br><br>没想到这个站现在还有生命力，瑟瑟永远都是第一生产力|

|   |   |   |
|---|---|---|
|![RealVic](https://cdn.v2ex.com/avatar/2475/6487/540455_normal.png?m=1739155453)||78<br><br>**[RealVic](/member/RealVic)**  <br><br>   17 天前<br><br>你那个 nsfw 能不能不要换行|

|   |   |   |
|---|---|---|
|![idblife](https://cdn.v2ex.com/avatar/a95c/4050/14375_normal.png?m=1646796005)||79<br><br>**[idblife](/member/idblife)**  <br><br>OP<br><br>   16 天前<br><br>@[shmilypeter](/member/shmilypeter)  <br>你之前访问过？|

|   |   |   |
|---|---|---|
|![freewind](https://cdn.v2ex.com/avatar/6051/a752/159396_normal.png?m=1711511840)||80<br><br>**[freewind](/member/freewind)**  <br><br>   16 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>提个建议，点击放大后，加个上一个，下一个按钮. 最好是可以左，右箭头翻页|

|   |   |   |
|---|---|---|
|![qloog](https://cdn.v2ex.com/avatar/9b94/b3d3/53261_normal.png?m=1713835571)||81<br><br>**[qloog](/member/qloog)**  <br><br>   16 天前<br><br>点开吓我一跳 Σ(⊙▽⊙"a|

|   |   |   |
|---|---|---|
|![idblife](https://cdn.v2ex.com/avatar/a95c/4050/14375_normal.png?m=1646796005)||82<br><br>**[idblife](/member/idblife)**  <br><br>OP<br><br>   16 天前<br><br>@[freewind](/member/freewind)  <br>晚上让 cursor 加一下这个功能，看看需要多久|

|   |   |   |
|---|---|---|
|![deali](https://cdn.v2ex.com/avatar/f914/e7aa/279572_normal.png?m=1595744033)||83<br><br>**[deali](/member/deali)**  <br><br>   16 天前<br><br>挺好的，我也有个 Django 开发的项目，想用其他语言重写，楼主可以把用 AI 重写的过程展开说说吗？|

|   |   |   |
|---|---|---|
|![idblife](https://cdn.v2ex.com/avatar/a95c/4050/14375_normal.png?m=1646796005)||84<br><br>**[idblife](/member/idblife)**  <br><br>OP<br><br>   16 天前 via iPhone<br><br>@[deali](/member/deali)  <br>先用 cursor 生成新语言的 web 框架基础代码，然后转换数据结构，最后挨个函数转换|

|   |   |   |
|---|---|---|
|![idblife](https://cdn.v2ex.com/avatar/a95c/4050/14375_normal.png?m=1646796005)||85<br><br>**[idblife](/member/idblife)**  <br><br>OP<br><br>   16 天前<br><br>@[freewind](/member/freewind) #80  <br>刚直接把你这段话复制给了 cursor ，没到 1 分钟就写好了，编译后功能满足需求。|

|   |   |   |
|---|---|---|
|![neochen13](https://cdn.v2ex.com/avatar/874d/5702/452997_normal.png?m=1739705170)||86<br><br>**[neochen13](/member/neochen13)**  <br><br>   16 天前<br><br>cursor 比通义灵码好用吗|

|   |   |   |
|---|---|---|
|![idblife](https://cdn.v2ex.com/avatar/a95c/4050/14375_normal.png?m=1646796005)||87<br><br>**[idblife](/member/idblife)**  <br><br>OP<br><br>   16 天前 via iPhone<br><br>@[neochen13](/member/neochen13)  <br>没用过通义灵码，不过 cursor 比 github copilot 好用。|

|   |   |   |
|---|---|---|
|![lazydao](https://cdn.v2ex.com/gravatar/cff28e08b377a6de74a96312eb7aefd6?s=48&d=retro)||88<br><br>**[lazydao](/member/lazydao)**  <br><br>   16 天前<br><br>最近刚用 Cursor 和 Trae 重构、优化了自己的一个脚手架。（ Cursor 比 Trae 强很多。）  <br>干活确实快（改动也很多/doge ）。生成的所有代码，我都 review 后才敢提交。但测试时，还是会发现一些 bug ，需要手动修复。  <br>整体评分能到 80/100 。  <br>不过，我之前的观点没变：**自己懂，才能用得好**。|

|   |   |   |
|---|---|---|
|![kaba](https://cdn.v2ex.com/avatar/e6b9/7c74/578383_normal.png?m=1678782532)||89<br><br>**[kaba](/member/kaba)**  <br><br>   16 天前<br><br>卧槽 公司打开吓我一跳|

|   |   |   |
|---|---|---|
|![KarmaWu](https://cdn.v2ex.com/avatar/6d13/2d1a/510691_normal.png?m=1608363073)||90<br><br>**[KarmaWu](/member/KarmaWu)**  <br><br>   16 天前<br><br>好活支持了|

|   |   |   |
|---|---|---|
|![luili](https://cdn.v2ex.com/avatar/c3fc/896b/84992_normal.png?m=1449470473)||91<br><br>**[luili](/member/luili)**  <br><br>   16 天前<br><br>妈的 在公司给打开了 女同事看着。。。|

|   |   |   |
|---|---|---|
|![messengers](https://cdn.v2ex.com/avatar/6a28/1ea3/629507_normal.png?m=1727070058)||92<br><br>**[messengers](/member/messengers)**  <br><br>   16 天前<br><br>nsfw 能不能醒目一点|

|   |   |   |
|---|---|---|
|![ccty](https://cdn.v2ex.com/avatar/b0e8/20e3/633945_normal.png?m=1702350530)||93<br><br>**[ccty](/member/ccty)**  <br><br>   16 天前<br><br>服务器是国外的，域名是国内的吗|

|   |   |   |
|---|---|---|
|![jettttt](https://cdn.v2ex.com/gravatar/6c6add1d7c4f2927102203f63474b493?s=48&d=retro)||94<br><br>**[jettttt](/member/jettttt)**  <br><br>   15 天前<br><br>卧槽，幸好手速快|

|   |   |   |
|---|---|---|
|![silenceeeee](https://cdn.v2ex.com/avatar/6b7d/d1ee/43937_normal.png?m=1394073924)||95<br><br>**[silenceeeee](/member/silenceeeee)**  <br><br>   15 天前<br><br>op 能说下这个图片源是哪里吗？|

[

](https://www.digitalocean.com/?refcode=1b51f1a7651d)

**[关于](/about)   ·   [帮助文档](/help)   ·   [博客](https://blog.v2ex.com/)   ·   [API](/help/api)   ·   [FAQ](/faq)   ·   [实用小工具](/tools)   ·   4979 人在线**   最高记录 6679   ·     [![](/static/img/language.png?v=6a5cfa731dc71a3769f6daace6784739)   Select Language](/select/language)

创意工作者们的社区

World is powered by solitude

VERSION: 3.9.8.5 · 25ms · [UTC 09:15](/worldclock#utc) · [PVG 17:15](/worldclock#pvg) · [LAX 01:15](/worldclock#lax) · [JFK 04:15](/worldclock#jfk)  
Developed with [CodeLauncher](https://cl.v2ex.pro/)  
♥ Do have faith in what you're doing.