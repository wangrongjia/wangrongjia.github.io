---
link: https://www.v2ex.com/t/1097978
site: V2EX
date: 2024-12-16T18:14
excerpt: 程序员 - @LeeReamond - 如题，用途是文档自动化分析，需要使用 chatgpt4o 或者能力更强的模型（或者 claude
  都行）调研了一下 chatgpt.com ，调用 API 需要账号绑定国外手机号才行，感觉比较
twitter: https://twitter.com/@V2EX
slurped: 2025-02-08T10:23
title: 问一下国内获得大模型 API 调用有哪些渠道？ - V2EX
---

这是一个创建于 53 天前的主题，其中的信息可能已经有所发展或是发生改变。

如题，用途是文档自动化分析，需要使用 chatgpt4o 或者能力更强的模型（或者 claude 都行）

调研了一下 [chatgpt.com](http://chatgpt.com/) ，调用 API 需要账号绑定国外手机号才行，感觉比较难搞，就算搞定了安全性和便利性都很成问题。

有没有类似需求的老哥分享一下路径

[](https://www.v2ex.com/tag/API)

[API](https://www.v2ex.com/tag/API)[

调用](https://www.v2ex.com/tag/%E8%B0%83%E7%94%A8)[

渠道](https://www.v2ex.com/tag/%E6%B8%A0%E9%81%93)

26 条回复  **•**  2024-12-17 09:52:28 +08:00

|   |   |   |
|---|---|---|
|![Ariake265](https://cdn.v2ex.com/avatar/ceca/819a/511388_normal.png?m=1671499844)||3<br><br>**[Ariake265](https://www.v2ex.com/member/Ariake265)**      53 天前<br><br>Gemini 有免费的 API ，直接买来的 Google 账号也能用，一天有免费的 1500 次调用，来回轮着用都可以。gemini-2.0-flash-exp 在 livebench 上面的 benchmark 还挺强的，并且速度非常非常快|

|   |   |   |
|---|---|---|
|![jettttt](https://cdn.v2ex.com/gravatar/6c6add1d7c4f2927102203f63474b493?s=48&d=retro)||6<br><br>**[jettttt](https://www.v2ex.com/member/jettttt)**      53 天前<br><br>我用的代理商，不过 token 计费会贵一点，个人用倒还好。另外文档自动化用外部的 api 会不会不太安全，可以尝试部署开源模型？|

|   |   |   |
|---|---|---|
|![iyaozhen](https://cdn.v2ex.com/avatar/6406/09f6/68154_normal.png?m=1735210344)||7<br><br>**[iyaozhen](https://www.v2ex.com/member/iyaozhen)**      53 天前<br><br>生产环境就是 Azure openai ，没别的选择|

|   |   |   |
|---|---|---|
|![mumbler](https://cdn.v2ex.com/gravatar/53e87c11a8aa9c21ad440f5b5eacdba9?s=48&d=retro)||8<br><br>**[mumbler](https://www.v2ex.com/member/mumbler)**      53 天前<br><br>gemini-exp-1206 ，有个 google 账号就能用，免费每天 1500 次，每分钟 10 次，付费需要美国信用卡|

|   |   |   |
|---|---|---|
|![winterpotato](https://cdn.v2ex.com/avatar/b08f/d972/473461_normal.png?m=1735717886)||9<br><br>**[winterpotato](https://www.v2ex.com/member/winterpotato)**      53 天前<br><br>Azure OpenAI ，或者 GCP 和 AWS 上（可能要企业协议），groq 上也有一些模型，再不行只能各种中转商了。|

|   |   |   |
|---|---|---|
|![LeeReamond](https://cdn.v2ex.com/avatar/f481/5f03/469082_normal.png?m=1713801588)||10<br><br>**[LeeReamond](https://www.v2ex.com/member/LeeReamond)**      53 天前<br><br>@[mumbler](https://www.v2ex.com/member/mumbler) 不知道国内 visa 或者 mastercard 行不行。这个模型是个什么水平的模型，和 chatgpt4o ，4 这个基准的比较如何？|

|   |   |   |
|---|---|---|
|![mumbler](https://cdn.v2ex.com/gravatar/53e87c11a8aa9c21ad440f5b5eacdba9?s=48&d=retro)||12<br><br>**[mumbler](https://www.v2ex.com/member/mumbler)**      53 天前<br><br>@[LeeReamond](https://www.v2ex.com/member/LeeReamond) #10 国内所有卡都不行，我的 visa 试过了，只能用虚拟卡支付，其实如果分析文档要求不高，国内 deepseek 也可以用，或者多注册几个 google 账号，一个 ip 一个 key 来调|

|   |   |   |
|---|---|---|
|![Alexf4](https://cdn.v2ex.com/avatar/6582/8ba9/196828_normal.png?m=1496900646)||13<br><br>**[Alexf4](https://www.v2ex.com/member/Alexf4)**      53 天前   ![❤️](https://www.v2ex.com/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>非利益相关。  <br>用了 wildcard 的 api 转发，跟官网原价一样。支持 OpenAI 跟 Claude 的。可以看看  <br>gemini-exp-1206 这个也用了免费的 API 。  <br>结合着用，嘎嘎的|

|   |   |   |
|---|---|---|
|![ruoxie](https://cdn.v2ex.com/avatar/29ca/be40/322280_normal.png?m=1705590144)||14<br><br>**[ruoxie](https://www.v2ex.com/member/ruoxie)**      53 天前<br><br>非利益相关，用了一年多了，所有模型都比官方便宜，也挺稳定  <br>aHR0cHM6Ly9wZWlxaXNob3AubWUv|

|   |   |   |
|---|---|---|
|![meeop](https://cdn.v2ex.com/avatar/8f89/5180/450566_normal.png?m=1735874691)||18<br><br>**[meeop](https://www.v2ex.com/member/meeop)**      53 天前<br><br>国内使用不要用模型原厂 api ，不确定什么时候就封了（以及按照用户协议你确实违规使用，封也没毛病）<br><br>只有两类：  <br>1 云服务厂商提供的，各个云服务厂商都有  <br>2api 代理服务，比如 openrouter|

|   |   |   |
|---|---|---|
|![meeop](https://cdn.v2ex.com/avatar/8f89/5180/450566_normal.png?m=1735874691)||19<br><br>**[meeop](https://www.v2ex.com/member/meeop)**      53 天前<br><br>同时多接几个，不要只接一家|

|   |   |   |
|---|---|---|
|![southwolf](https://cdn.v2ex.com/avatar/8d31/7bdc/747_normal.png?m=1454115578)||21<br><br>**[southwolf](https://www.v2ex.com/member/southwolf)**      53 天前 via Android<br><br>GPT 就是 Azure,  <br>Claude 可以 GCP|

|   |   |   |
|---|---|---|
|![channlong](https://cdn.v2ex.com/gravatar/c0acb1df4816942186128a0c843ec802?s=48&d=retro)||23<br><br>**[channlong](https://www.v2ex.com/member/channlong)**      53 天前<br><br>目前使用的是腾讯的， 甚至腾讯还可以帮你转发 openai 的 api ，哈哈 [![](https://i.imgur.com/L62ZP7V.png)](https://i.imgur.com/L62ZP7V.png)|

|   |   |   |
|---|---|---|
|![z7356995](https://cdn.v2ex.com/gravatar/244ff0bb7793a0c2725c298c77d71e27?s=48&d=retro)||24<br><br>**[z7356995](https://www.v2ex.com/member/z7356995)**      53 天前<br><br>李开复的 01 模型，或者自己查一下大模型竞技场各排名得分|