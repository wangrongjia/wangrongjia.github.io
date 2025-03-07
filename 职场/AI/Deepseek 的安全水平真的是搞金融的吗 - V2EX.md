---
link: https://www.v2ex.com/t/1110074
site: V2EX
date: 2025-02-09T12:11
excerpt: 程序员 - @evilStart - 云安全公司 Wiz 报告，在 Deepseek 域名下发现了 clickhouse
  数据库接口，没有任何身份验证，暴露了大量后端日志，里面包含 API 密钥、用户对话记录等敏感数据。这样的操作
twitter: https://twitter.com/@V2EX
slurped: 2025-02-10T09:29
title: Deepseek 的安全水平真的是搞金融的吗 - V2EX
---

  [evilStart](/member/evilStart) · 21 小时 14 分钟前 · 2467 次点击

云安全公司 Wiz 报告，在 Deepseek 域名下发现了 clickhouse 数据库接口，没有任何身份验证，暴露了大量后端日志，里面包含 API 密钥、用户对话记录等敏感数据。

这样的操作很难想象出自一个搞金融的公司


14 条回复

|   |   |   |
|---|---|---|
|![Ocean810975](https://cdn.v2ex.com/gravatar/589d48e5930e57b8d275da827350d080?s=48&d=retro)||1<br><br>**[Ocean810975](/member/Ocean810975)**  <br><br>   21 小时 1 分钟前<br><br>因为极大概率不是一个团队的做的，而且一个项目快速迭代，肯定不可能像金融量化一样有着相同的安全标准。|

|   |   |   |
|---|---|---|
|![codehz](https://cdn.v2ex.com/avatar/815f/9fae/187268_normal.png?m=1694577816)||2<br><br>**[codehz](/member/codehz)**  <br><br>   20 小时 56 分钟前 via Android<br><br>量化也不需要直接对消费者提供服务啊，数据库，直接内网就好了|

|   |   |   |
|---|---|---|
|![GeekGao](https://cdn.v2ex.com/avatar/6540/f6ff/30946_normal.png?m=1731046133)||3<br><br>**[GeekGao](/member/GeekGao)**  <br><br>   20 小时 21 分钟前<br><br>首先的首先：他们是同一家公司吗？|

|   |   |   |
|---|---|---|
|![spike0100](https://cdn.v2ex.com/gravatar/fa0742ef900538e460ff51682022333d?s=48&d=retro)||4<br><br>**[spike0100](/member/spike0100)**  <br><br>   20 小时 2 分钟前 via iPhone<br><br>确实离谱。|

|   |   |   |
|---|---|---|
|![evilStart](https://cdn.v2ex.com/avatar/23c3/aec1/109689_normal.png?m=1739020171)||5<br><br>**[evilStart](/member/evilStart)**  <br><br>OP<br><br>   18 小时 46 分钟前<br><br>@[GeekGao](/member/GeekGao) 不是幻方旗下的公司吗？|

|   |   |   |
|---|---|---|
|![GeekGao](https://cdn.v2ex.com/avatar/6540/f6ff/30946_normal.png?m=1731046133)||6<br><br>**[GeekGao](/member/GeekGao)**  <br><br>   18 小时 45 分钟前<br><br>@[evilStart](/member/evilStart) 两家独立的公司啊，独立的团队|

|   |   |   |
|---|---|---|
|![evilStart](https://cdn.v2ex.com/avatar/23c3/aec1/109689_normal.png?m=1739020171)||7<br><br>**[evilStart](/member/evilStart)**  <br><br>OP<br><br>   18 小时 45 分钟前<br><br>@[Ocean810975](/member/Ocean810975) 这不需要金融标准吧，验证接口不是互联网的基础标准吗|

|   |   |   |
|---|---|---|
|![Jerry23333](https://cdn.v2ex.com/gravatar/f6f90aeafd07afc94c0788a92eede2dc?s=48&d=retro)||8<br><br>**[Jerry23333](/member/Jerry23333)**  <br><br>   18 小时 38 分钟前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>幻方是搞量化的，不 tob 也不 toc ，它们的模型啥的应该都是自己内部用，一切都在内网下，不对外提供服务。|

|   |   |   |
|---|---|---|
|![mingtdlb](https://cdn.v2ex.com/avatar/1067/fd49/525301_normal.png?m=1722739500)||9<br><br>**[mingtdlb](/member/mingtdlb)**  <br><br>   16 小时 51 分钟前<br><br>同一个公司不同部门之间协调都比较困难，有的组之间都困难。  <br>  <br>不要 ≈，或者只看品牌。人各有所长，你车开的好，饭并不一定做的美味。|

|   |   |   |
|---|---|---|
|![Feeli](https://cdn.v2ex.com/gravatar/871085c050c15b7d4c4ba4c451219190?s=48&d=retro)||10<br><br>**[Feeli](/member/Feeli)**  <br><br>   16 小时 36 分钟前<br><br>dev 库罢了，问题是大，但没那么大......|

|   |   |   |
|---|---|---|
|![paopjian](https://cdn.v2ex.com/gravatar/141f86b5cead0224ebc0365353521a26?s=48&d=retro)||11<br><br>**[paopjian](/member/paopjian)**  <br><br>   16 小时 28 分钟前<br><br>做量化是坑别人的钱,又不是保护自己的钱, 而且子母公司没有必要同步技术栈吧|

|   |   |   |
|---|---|---|
|![LeoJ](https://cdn.v2ex.com/avatar/6261/a979/439282_normal.png?m=1580963350)||12<br><br>**[LeoJ](/member/LeoJ)**  <br><br>   11 小时 25 分钟前<br><br>感觉幻方上线个 Deepseek 只是为了证明下确实做出来了，不是凭空做空英伟达而已，人家就没想靠卖这个赚钱 哈哈|

|   |   |   |
|---|---|---|
|![win8en](https://cdn.v2ex.com/gravatar/daa907248202cd5689f03714b382ddce?s=48&d=retro)||13<br><br>**[win8en](/member/win8en)**  <br><br>   10 小时 52 分钟前<br><br>@[LeoJ](/member/LeoJ) #12 不管怎样，最近用下来确实强，比 ChatGPT 给力，中国人真的能做出来好东西|

|   |   |   |
|---|---|---|
|![nishikinor](https://cdn.v2ex.com/gravatar/22144c3c56f9e5a662465a2da204c1b9?s=48&d=retro)||14<br><br>**[nishikinor](/member/nishikinor)**  <br><br>   7 小时 55 分钟前<br><br>不要觉得幻方的安全水平很低，一些工作可能比安全更重要，人力有限暂时没有投入罢了。  <br>至少我知道的，有 top2 的安研大佬在幻方的组里|
