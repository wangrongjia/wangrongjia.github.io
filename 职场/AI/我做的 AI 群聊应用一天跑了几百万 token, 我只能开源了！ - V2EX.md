---
link: https://www.v2ex.com/t/1112776
site: V2EX
date: 2025-02-19T23:00
excerpt: 分享创造 - @hobbyliu - 前天在 V2 发了一个帖子介绍 AI 群聊应用：
  https://www.v2ex.com/t/1112394本打算陆续完善下再开源，中午陆续收到阿里云、火山引擎、腾讯云大模型余额欠费通知几百
twitter: https://twitter.com/@V2EX
slurped: 2025-03-07T16:14
title: 我做的 AI 群聊应用一天跑了几百万 token, 我只能开源了！ - V2EX
---
   [hobbyliu](/member/hobbyliu) · 15 天前 · 2994 次点击

前天在 V2 发了一个帖子介绍 AI 群聊应用： [https://www.v2ex.com/t/1112394](https://www.v2ex.com/t/1112394)

本打算陆续完善下再开源，中午陆续收到阿里云、火山引擎、腾讯云大模型余额欠费通知几百万 token 完全耗尽，

为了更好的让大家体验，今天加速把它开源出来，大家可以用 cloudflare 免费部署托管，用几个平台免费大模型一个人完全够用一阵子。

- github 项目地址： [https://github.com/maojindao55/botgroup.chat](https://github.com/maojindao55/botgroup.chat)
- 体验地址：[https://botgroup.chat](https://botgroup.chat)

本次更新了新功能点：

- 🤖 支持多个 AI 角色同时对话
- 💬 实时流式响应
- 🎭 可自定义 AI 角色和个性
- 🔇 AI 角色禁言功能
- 📝 支持 Markdown 格式
- ➗ 支持数学公式显示（ KaTeX ）
- 📱 响应式设计，支持移动端

## 演示截图

![Image](https://github.com/user-attachments/assets/f88a6432-e80c-4f31-bbb6-21caac5a1ccf) ![文字游戏](https://i.v2ex.co/tu4a5mv9.png)

[

AI](/tag/AI)[

开源](/tag/开源)[

token](/tag/token)

16 条回复  **•**  2025-02-23 19:57:11 +08:00

|   |   |   |
|---|---|---|
|![rekulas](https://cdn.v2ex.com/avatar/ff00/e7ff/173283_normal.png?m=1726814747)||1<br><br>**[rekulas](/member/rekulas)**  <br><br>   15 天前<br><br>有点意思, 不过我觉得没必要接入多个模型,直接接入一个不错的模型然后拟定多种不同的身份(方便从多种维度来看待回复)接话就行了, 维护也容易点|

|   |   |   |
|---|---|---|
|![hobbyliu](https://cdn.v2ex.com/avatar/4a5d/0346/111151_normal.png?m=1739868215)||2<br><br>**[hobbyliu](/member/hobbyliu)**  <br><br>OP<br><br>   15 天前<br><br>@[rekulas](/member/rekulas) 嗯呢，看场景了，纯娱乐的没问题。|

|   |   |   |
|---|---|---|
|![snow0](https://cdn.v2ex.com/gravatar/300caec57ca5681b97d467d40f06ce7f?s=48&d=retro)||3<br><br>**[snow0](/member/snow0)**  <br><br>   15 天前<br><br>这个群聊有意思，实现思路是什么呢|

|   |   |   |
|---|---|---|
|![serviceootdshare](https://cdn.v2ex.com/gravatar/350b23db810bf803ec972af089f43073?s=48&d=retro)||4<br><br>**[serviceootdshare](/member/serviceootdshare)**  <br><br>   15 天前 via iPhone<br><br>你的 ApI key 是用什么信用卡买的？  <br>我看香港的信用卡也不行|

|   |   |   |
|---|---|---|
|![guguexxx](https://cdn.v2ex.com/gravatar/d3035219b28a02ffcb898e4c8be1e219?s=48&d=retro)||5<br><br>**[guguexxx](/member/guguexxx)**  <br><br>   15 天前<br><br>可以狼人杀吗？很想和 ai 来一场酣畅淋漓的杀|

|   |   |   |
|---|---|---|
|![aTA1Dw1MG127wgPb](https://cdn.v2ex.com/static/img/avatar_normal.png)||6<br><br>**[aTA1Dw1MG127wgPb](/member/aTA1Dw1MG127wgPb)**  <br><br>   15 天前 via iPhone<br><br>哇！真的好佩服你的这个 idea ！|

|   |   |   |
|---|---|---|
|![lanrete](https://cdn.v2ex.com/gravatar/2d27e1f2af5267b66f517ff6dcd186f8?s=48&d=retro)||7<br><br>**[lanrete](/member/lanrete)**  <br><br>   15 天前<br><br>@[guguexxx](/member/guguexxx) 之前自己写了个和 deepseek 玩谁是卧底的小 demo ，效果贼差，感觉要花功夫研究下 prompt 怎么写|

|   |   |   |
|---|---|---|
|![hobbyliu](https://cdn.v2ex.com/avatar/4a5d/0346/111151_normal.png?m=1739868215)||8<br><br>**[hobbyliu](/member/hobbyliu)**  <br><br>OP<br><br>   15 天前<br><br>@[snow0](/member/snow0) 就让 AI 理解上下文，类似于角色扮演。  <br>  <br>@[serviceootdshare](/member/serviceootdshare) 都是国产的 api key 呢，没有用国外的模型。  <br>  <br>@[guguexxx](/member/guguexxx) 理论上可以，你可以试试，告诉好规则就行。  <br>  <br>@[unilehalil](/member/unilehalil) 感谢褒奖|

|   |   |   |
|---|---|---|
|![8355](https://cdn.v2ex.com/avatar/dbd3/6c22/210254_normal.png?m=1715407255)||9<br><br>**[8355](/member/8355)**  <br><br>   15 天前<br><br>还拉上群了是吧 [![](https://i.imgur.com/agAJ0Rd.png)](https://i.imgur.com/agAJ0Rd.png)|

|   |   |   |
|---|---|---|
|![zhw2590582](https://cdn.v2ex.com/avatar/ba8a/ba0f/66538_normal.png?m=1556897544)||10<br><br>**[zhw2590582](/member/zhw2590582)**  <br><br>   14 天前<br><br>之前也有过这个想法，但后来想想应用场景并不多|

|   |   |   |
|---|---|---|
|![Peiiii](https://cdn.v2ex.com/gravatar/25b646fe7cbf4ac6851de05fb188704b?s=48&d=retro)||11<br><br>**[Peiiii](/member/Peiiii)**  <br><br>   14 天前 via Android<br><br>俺也有个类似的，[https://agent.dimstack.com/](https://agent.dimstack.com/)  <br>github: [https://github.com/Peiiii/AgentVerse](https://github.com/Peiiii/AgentVerse)|

|   |   |   |
|---|---|---|
|![Jack66](https://cdn.v2ex.com/avatar/dc82/74dc/544930_normal.png?m=1720229954)||12<br><br>**[Jack66](/member/Jack66)**  <br><br>   14 天前<br><br>有趣啊这个|

|   |   |   |
|---|---|---|
|![dvbs2000](https://cdn.v2ex.com/avatar/89fb/52e6/28162_normal.png?m=1733058874)||13<br><br>**[dvbs2000](/member/dvbs2000)**  <br><br>   13 天前<br><br>挺有意思的。不过不太完美，是不是提示词没有写足够清晰还是有些 AI 太笨。|

|   |   |   |
|---|---|---|
|![dvbs2000](https://cdn.v2ex.com/avatar/89fb/52e6/28162_normal.png?m=1733058874)||14<br><br>**[dvbs2000](/member/dvbs2000)**  <br><br>   13 天前<br><br>@[Peiiii](/member/Peiiii) 你这个界面太复杂了 不好用|

|   |   |   |
|---|---|---|
|![huasheng22](https://cdn.v2ex.com/gravatar/297ee5650d5e6a1c0a16e0cf258df83e?s=48&d=retro)||15<br><br>**[huasheng22](/member/huasheng22)**  <br><br>   13 天前<br><br>目前看起来是排队回答，如果可以在每次成员发言之后，所有成员都进行一次判断选择是否需要插嘴，或许会更拟真一些|

|   |   |   |
|---|---|---|
|![hobbyliu](https://cdn.v2ex.com/avatar/4a5d/0346/111151_normal.png?m=1739868215)||16<br><br>**[hobbyliu](/member/hobbyliu)**  <br><br>OP<br><br>   11 天前<br><br>@[huasheng22](/member/huasheng22) 怎么正在考虑做智能调度系统，不过需要慢慢调试|

[

](https://www.digitalocean.com/?refcode=1b51f1a7651d)

**[关于](/about)   ·   [帮助文档](/help)   ·   [博客](https://blog.v2ex.com/)   ·   [API](/help/api)   ·   [FAQ](/faq)   ·   [实用小工具](/tools)   ·   5220 人在线**   最高记录 6679   ·     [![](/static/img/language.png?v=6a5cfa731dc71a3769f6daace6784739)   Select Language](/select/language)

创意工作者们的社区

World is powered by solitude

VERSION: 3.9.8.5 · 102ms · [UTC 08:13](/worldclock#utc) · [PVG 16:13](/worldclock#pvg) · [LAX 00:13](/worldclock#lax) · [JFK 03:13](/worldclock#jfk)  
Developed with [CodeLauncher](https://cl.v2ex.pro/)  
♥ Do have faith in what you're doing.