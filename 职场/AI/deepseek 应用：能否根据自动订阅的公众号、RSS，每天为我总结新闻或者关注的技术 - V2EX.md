---
link: https://www.v2ex.com/t/1111374
site: V2EX
date: 2025-02-14T10:11
excerpt: 程序员 - @mianhk - 目前看能让 deepseek 直接阅读单篇文章，但是好像没有应用能自动拉取新的文章，或者 Follow
  的输出能用吗？有啥好的思路没呀
twitter: https://twitter.com/@V2EX
slurped: 2025-02-14T17:16
title: deepseek 应用：能否根据自动订阅的公众号、RSS，每天为我总结新闻或者关注的技术 - V2EX
---
                                                

[

](/ "way to explore")

[首页](/) [注册](/signup) [登录](/signin)

**V2EX = way to explore**

V2EX 是一个关于分享和探索的地方

[现在注册](/signup)

已注册用户请  [登录](/signin)

• 请不要在回答技术问题时复制粘贴 AI 生成的内容 

[![mianhk](https://cdn.v2ex.com/gravatar/23f6b6edf117b94992fbd04dc6a31ceb?s=73&d=retro)](/member/mianhk)

[V2EX](/)  ›  [程序员](/go/programmer)

# deepseek 应用：能否根据自动订阅的公众号、RSS，每天为我总结新闻或者关注的技术

[

](javascript:) [

](javascript:)

  [mianhk](/member/mianhk) · 7 小时 2 分钟前 · 6136 次点击

目前看能让 deepseek 直接阅读单篇文章，但是好像没有应用能自动拉取新的文章，或者 Follow 的输出能用吗？有啥好的思路没呀

[

DeepSeek](/tag/DeepSeek)[

公众号](/tag/公众号)[

RSS](/tag/RSS)

23 条回复

|   |   |   |
|---|---|---|
|![AEDaydreamer](https://cdn.v2ex.com/avatar/dbf0/f1ab/504831_normal.png?m=1674896537)||1<br><br>**[AEDaydreamer](/member/AEDaydreamer)**  <br><br>   6 小时 48 分钟前<br><br>那不就是简单的基于 llm api 开发吗？ 直接喂文章和 prompt 拿输出就行了|

|   |   |   |
|---|---|---|
|![huyujievip](https://cdn.v2ex.com/gravatar/d107c04304dceffdbf9f03b128d2463d?s=48&d=retro)||2<br><br>**[huyujievip](/member/huyujievip)**  <br><br>   6 小时 43 分钟前<br><br>![image]( https://i.111666.best/image/VfJWUSqrj9enyFmZIDP4Yq.png)  <br>  <br>你是不是想要这个|

|   |   |   |
|---|---|---|
|![huyujievip](https://cdn.v2ex.com/gravatar/d107c04304dceffdbf9f03b128d2463d?s=48&d=retro)||3<br><br>**[huyujievip](/member/huyujievip)**  <br><br>   6 小时 43 分钟前<br><br>https://i.111666.best/image/VfJWUSqrj9enyFmZIDP4Yq.png|

|   |   |   |
|---|---|---|
|![meeop](https://cdn.v2ex.com/avatar/8f89/5180/450566_normal.png?m=1735874691)||4<br><br>**[meeop](/member/meeop)**  <br><br>   6 小时 37 分钟前<br><br>技术没问题，成本是个问题  <br>  <br>因为提供这个服务的话，就需要对每日新增数量 m 进行用户量 n=m*n 那么多次 ai 请求，至少不是一个经济高性能的方法  <br>而其他高性能推荐算法就是线上各个 app 正在使用的|

|   |   |   |
|---|---|---|
|![gudao](https://cdn.v2ex.com/gravatar/ea33d6241e865b70c33dc33a3009798b?s=48&d=retro)||5<br><br>**[gudao](/member/gudao)**  <br><br>   6 小时 29 分钟前<br><br>@[huyujievip](/member/huyujievip) 这个是如何实现的呢？|

|   |   |   |
|---|---|---|
|![skadi](https://cdn.v2ex.com/avatar/c88b/4496/206369_normal.png?m=1493682869)||6<br><br>**[skadi](/member/skadi)**  <br><br>   6 小时 22 分钟前<br><br>我也有这个需求,rss 有点多,挨个看太花时间了.|

|   |   |   |
|---|---|---|
|![korvin](https://cdn.v2ex.com/avatar/099e/54d3/81317_normal.png?m=1739501644)||7<br><br>**[korvin](/member/korvin)**  <br><br>   6 小时 16 分钟前<br><br>@[meeop](/member/meeop) #4 是不是可以考虑用自己部署的模型，就总结个文章，应该不用太大的模型参数。|

|   |   |   |
|---|---|---|
|![mapleshadowxda](https://cdn.v2ex.com/avatar/3c0d/6082/63526_normal.png?m=1497773182)||8<br><br>**[mapleshadowxda](/member/mapleshadowxda)**  <br><br>   5 小时 46 分钟前 via Android<br><br>自己部署的不消耗 api 吗？|

|   |   |   |
|---|---|---|
|![mapleshadowxda](https://cdn.v2ex.com/avatar/3c0d/6082/63526_normal.png?m=1497773182)||9<br><br>**[mapleshadowxda](/member/mapleshadowxda)**  <br><br>   5 小时 46 分钟前 via Android<br><br>如此那确实有用啊|

|   |   |   |
|---|---|---|
|![JiJJA](https://cdn.v2ex.com/gravatar/ef4543b44572f27c77bf35aa8c089672?s=48&d=retro)||10<br><br>**[JiJJA](/member/JiJJA)**  <br><br>   5 小时 32 分钟前<br><br>@[huyujievip](/member/huyujievip) 大佬,求几个关键词 我也想整一个 orz|

|   |   |   |
|---|---|---|
|![huyujievip](https://cdn.v2ex.com/gravatar/d107c04304dceffdbf9f03b128d2463d?s=48&d=retro)||11<br><br>**[huyujievip](/member/huyujievip)**  <br><br>   5 小时 19 分钟前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 6<br><br>![1739505196269.png]( [https://image.dooo.ng/c/2025/02/14/67aebe362bb21.webp](https://image.dooo.ng/c/2025/02/14/67aebe362bb21.webp))  <br>![SCR-20250214-jpqb-2.png]( [https://image.dooo.ng/c/2025/02/14/67aebd3ec20cf.webp](https://image.dooo.ng/c/2025/02/14/67aebd3ec20cf.webp))  <br>  <br>统一回复一下楼上  <br>  <br>我使用 FreshRSS 管理分组订阅链接  <br>  <br>然后写了一个每天定时运行的程序，通过 FreshRSS API 获取各个分类下的文章，一般可以顺带拿到文章的前几十个内容字符  <br>  <br>再 by 分类总结，再汇总总结，最后通过邮件发送到自己的邮箱  <br>  <br>用 Gemini 2.0 Flash 每天花不了一分钱（当然文章数量比较少）  <br>  <br>后面大家需要的话，可以整理整理代码开源出来|

|   |   |   |
|---|---|---|
|![huyujievip](https://cdn.v2ex.com/gravatar/d107c04304dceffdbf9f03b128d2463d?s=48&d=retro)||12<br><br>**[huyujievip](/member/huyujievip)**  <br><br>   5 小时 18 分钟前<br><br>@[JiJJA](/member/JiJJA) @[gudao](/member/gudao)|

|   |   |   |
|---|---|---|
|![tinyzilan123](https://cdn.v2ex.com/avatar/1003/1392/651310_normal.png?m=1717464740)||13<br><br>**[tinyzilan123](/member/tinyzilan123)**  <br><br>   5 小时 7 分钟前<br><br>@[huyujievip](/member/huyujievip) #11 这个项目不错啊，期待开源|

|   |   |   |
|---|---|---|
|![mianhk](https://cdn.v2ex.com/gravatar/23f6b6edf117b94992fbd04dc6a31ceb?s=48&d=retro)||14<br><br>**[mianhk](/member/mianhk)**  <br><br>OP<br><br>   4 小时 17 分钟前<br><br>@[AEDaydreamer](/member/AEDaydreamer) 还是不一样的，相当于要自动把新的文章或新闻获取到  <br>@[meeop](/member/meeop) 嗯，自己部署的是不是可能也够用  <br>@[huyujievip](/member/huyujievip) +1 期待开源|

|   |   |   |
|---|---|---|
|![huzhizhao](https://cdn.v2ex.com/avatar/5c4d/6294/292300_normal.png?m=1734317120)||15<br><br>**[huzhizhao](/member/huzhizhao)**  <br><br>   3 小时 7 分钟前<br><br>@[huyujievip](/member/huyujievip) #11  <br>真不错，期待开源|

|   |   |   |
|---|---|---|
|![sampeng](https://cdn.v2ex.com/gravatar/3b198446b72d1e5a3b0090f106a75f3c?s=48&d=retro)||16<br><br>**[sampeng](/member/sampeng)**  <br><br>   2 小时 40 分钟前<br><br>其实问题不是整个技术。。而是 RSS 本身就不稳定。|

|   |   |   |
|---|---|---|
|![jeepc](https://cdn.v2ex.com/gravatar/a660302c80fa864ca7823a3027fd4239?s=48&d=retro)||17<br><br>**[jeepc](/member/jeepc)**  <br><br>   2 小时 9 分钟前<br><br>[https://github.com/RSSNext/follow](https://github.com/RSSNext/follow) 这个有人用过吗|

|   |   |   |
|---|---|---|
|![Foxii](https://cdn.v2ex.com/gravatar/5dd4fd4fe74cdc2f59662d84e0ebe1a8?s=48&d=retro)||18<br><br>**[Foxii](/member/Foxii)**  <br><br>   2 小时 5 分钟前<br><br>@[huyujievip](/member/huyujievip) [https://image.dooo.ng/c/2025/02/14/67aebe362bb21.webp](https://image.dooo.ng/c/2025/02/14/67aebe362bb21.webp) 这张图是哪个平台？是可以调用多个模型的 API 吗|

|   |   |   |
|---|---|---|
|![huyujievip](https://cdn.v2ex.com/gravatar/d107c04304dceffdbf9f03b128d2463d?s=48&d=retro)||19<br><br>**[huyujievip](/member/huyujievip)**  <br><br>   2 小时 2 分钟前<br><br>@[Foxii](/member/Foxii) openrouter|

|   |   |   |
|---|---|---|
|![pizone](https://cdn.v2ex.com/gravatar/28c456b150686e515cdf21cc273f7dab?s=48&d=retro)||20<br><br>**[pizone](/member/pizone)**  <br><br>   1 小时 58 分钟前<br><br>你可以选择你要订阅的微信公众号，配置一下规则，找个服务生成 RSS 订阅源，你统一以 RSS 来订阅就可以了。  <br>  <br>至于生成摘要之类的，现在的订阅源信息都太杂乱了，最好还是自己快速标记一下，节省一下 token 消耗。  <br>  <br>我自己的解决方案是，之前有写过一个 rss 的帖子，可以翻阅一下，看下有没有灵感。  <br>  <br>其实最好自己写一个浏览器扩展根据自己需求实现一些个性化功能。实现 RSS 订阅和标记的工作，然后根据全文内容生成对应的摘要，并在此基础上自定义一些 prompt 来实现一些个性化的功能，比如分析某个标签的文章（我之前是让他分析美联储相关的报道，分析各种可能情况和市场影响），或者选择一下某个主题，写篇文章。  <br>  <br>类似这样，用来做什么，主要还是看你的 prompt 怎么写了，比如用推理模型来分析，把过去一个月或 2 周内所有某个标签的内容，拿出来分析和推理，也是挺有意思的：  <br>  <br>[https://ibb.co/WNFckr7p](https://ibb.co/WNFckr7p)  <br>[https://ibb.co/pr3Qm3mr](https://ibb.co/pr3Qm3mr)  <br>[https://ibb.co/23wwb6tw](https://ibb.co/23wwb6tw)  <br>[https://ibb.co/DH1Xff5C](https://ibb.co/DH1Xff5C)|

|   |   |   |
|---|---|---|
|![blessyou](https://cdn.v2ex.com/avatar/7833/d0ea/198402_normal.png?m=1477464707)||21<br><br>**[blessyou](/member/blessyou)**  <br><br>   1 小时 32 分钟前<br><br>自己用 n8n 写一个就是了。|

|   |   |   |
|---|---|---|
|![prime2015](https://cdn.v2ex.com/gravatar/c4aad50dd9340fcbb2a19d70dcb84f36?s=48&d=retro)||22<br><br>**[prime2015](/member/prime2015)**  <br><br>   46 分钟前<br><br>这个难点在反爬上而不在于 AI 处理，rsshub 之类的我都试过，没有可用性|

|   |   |   |
|---|---|---|
|![prime2015](https://cdn.v2ex.com/gravatar/c4aad50dd9340fcbb2a19d70dcb84f36?s=48&d=retro)||23<br><br>**[prime2015](/member/prime2015)**  <br><br>   44 分钟前<br><br>@[prime2015](/member/prime2015) Follow 和 rsshub 是同一个作者开发的，依然没有解决反爬问题，基本上这个产品就没有可用性|

[

](https://www.digitalocean.com/?refcode=1b51f1a7651d)

**[关于](/about)   ·   [帮助文档](/help)   ·   [博客](https://blog.v2ex.com/)   ·   [API](/help/api)   ·   [FAQ](/faq)   ·   [实用小工具](/tools)   ·   5554 人在线**   最高记录 6679   ·     [![](/static/img/language.png?v=6a5cfa731dc71a3769f6daace6784739)   Select Language](/select/language)

创意工作者们的社区

World is powered by solitude

VERSION: 3.9.8.5 · 43ms · [UTC 09:14](/worldclock#utc) · [PVG 17:14](/worldclock#pvg) · [LAX 01:14](/worldclock#lax) · [JFK 04:14](/worldclock#jfk)  
Developed with [CodeLauncher](https://cl.v2ex.pro/)  
♥ Do have faith in what you're doing.