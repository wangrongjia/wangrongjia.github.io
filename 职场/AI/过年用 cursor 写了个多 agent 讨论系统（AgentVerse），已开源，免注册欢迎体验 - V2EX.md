---
link: https://www.v2ex.com/t/1109694
site: V2EX
date: 2025-02-07T17:39
excerpt: "分享创造 - @Peiiii - 网址： [https://agent.dimstack.com/](
  https://agent.dimstack.com/)github: [https://github.com/Peiiii/"
twitter: https://twitter.com/@V2EX
slurped: 2025-02-28T15:33
title: 过年用 cursor 写了个多 agent 讨论系统（AgentVerse），已开源，免注册欢迎体验 - V2EX
---
 
  [Peiiii](/member/Peiiii) ·

[Peiiii](https://github.com/Peiiii) · 20 天前 · 1989 次点击

网址： [https://agent.dimstack.com/](https://agent.dimstack.com/) github: [https://github.com/Peiiii/AgentVerse](https://github.com/Peiiii/AgentVerse) ![](https://pic1.imgdb.cn/item/67a5cdd0d0e0a243d4fc8bf0.png) 目前只是个非常基础的 demo ，支持用一个 moderator agent 去创建管理其它 agent 。 有很多拓展想法但还不完善，例如支持 mcp ，给每个 agent 配置记忆，更灵活的响应机制、让每个 agent 可以通过命令行等其它形式访问等。希望最终真的能做成 A Universe of Agents

目前接的 qwen2.5-max,估计很快就会没钱，等没钱了就打算暂时下掉了

[

AgentVerse](/tag/AgentVerse)[

multi-agent](/tag/multi-agent)[

开源](/tag/开源)

30 条回复  **•**  2025-02-14 02:08:04 +08:00

|   |   |   |
|---|---|---|
|![lanrete](https://cdn.v2ex.com/gravatar/2d27e1f2af5267b66f517ff6dcd186f8?s=48&d=retro)||1<br><br>**[lanrete](/member/lanrete)**  <br><br>   20 天前<br><br>挺有意思的欸，不过一旦开始讨论几个 agent 就不停输出了，去上了个厕所回来就跟不上讨论了，感觉 token 消耗得也挺快的|

|   |   |   |
|---|---|---|
|![superlaomao](https://cdn.v2ex.com/gravatar/d84921f344942c90a24d026d900badf6?s=48&d=retro)||2<br><br>**[superlaomao](/member/superlaomao)**  <br><br>   20 天前<br><br>能不能使用离线的模型啊？|

|   |   |   |
|---|---|---|
|![Peiiii](https://cdn.v2ex.com/gravatar/25b646fe7cbf4ac6851de05fb188704b?s=48&d=retro)||3<br><br>**[Peiiii](/member/Peiiii)**  <br><br>OP<br><br>   20 天前<br><br>@[lanrete](/member/lanrete) 对的，这个需要优化，现在废话太多了不够简洁，像 cursor 的 chat 那样就很好，另外目前没有停止机制，会无限发送。估计我充的钱很快就会用光光|

|   |   |   |
|---|---|---|
|![Peiiii](https://cdn.v2ex.com/gravatar/25b646fe7cbf4ac6851de05fb188704b?s=48&d=retro)||4<br><br>**[Peiiii](/member/Peiiii)**  <br><br>OP<br><br>   20 天前<br><br>@[superlaomao](/member/superlaomao) 这个是调用 api 的，离线的模型可以加个后端 server 包起来也是一样的。|

|   |   |   |
|---|---|---|
|![kitmyfaceplease2](https://cdn.v2ex.com/avatar/fafb/8ce6/579332_normal.png?m=1698992374)||5<br><br>**[kitmyfaceplease2](/member/kitmyfaceplease2)**  <br><br>   20 天前<br><br>非常有趣，感谢分享！|

|   |   |   |
|---|---|---|
|![luckyrayyy](https://cdn.v2ex.com/avatar/47f9/a4b5/216117_normal.png?m=1728905688)||6<br><br>**[luckyrayyy](/member/luckyrayyy)**  <br><br>   20 天前<br><br>有意思|

|   |   |   |
|---|---|---|
|![Asyncway](https://cdn.v2ex.com/avatar/99d3/d0a8/357534_normal.png?m=1737013029)||7<br><br>**[Asyncway](/member/Asyncway)**  <br><br>   20 天前<br><br>有点意思|

|   |   |   |
|---|---|---|
|![devdes](https://cdn.v2ex.com/avatar/5df1/e77f/117431_normal.png?m=1736691721)||8<br><br>**[devdes](/member/devdes)**  <br><br>   20 天前<br><br>很棒啊，一顿头脑风暴下来收获不少👍|

|   |   |   |
|---|---|---|
|![senghoo](https://cdn.v2ex.com/avatar/76c0/0cef/45511_normal.png?m=1395319902)||9<br><br>**[senghoo](/member/senghoo)**  <br><br>   20 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>很棒的 idea 。建议加个功能，就是用户来触发每一轮讨论或者指定谁发言。有种 leader 指挥头脑风暴的感觉。用来控制 token 消耗以及控制节奏。|

|   |   |   |
|---|---|---|
|![GeekGao](https://cdn.v2ex.com/avatar/6540/f6ff/30946_normal.png?m=1731046133)||10<br><br>**[GeekGao](/member/GeekGao)**  <br><br>   20 天前<br><br>有点意思|

|   |   |   |
|---|---|---|
|![GeekGao](https://cdn.v2ex.com/avatar/6540/f6ff/30946_normal.png?m=1731046133)||11<br><br>**[GeekGao](/member/GeekGao)**  <br><br>   20 天前<br><br>不过讨论到最后跑题了、也不停止，是怎个情况？|

|   |   |   |
|---|---|---|
|![yushi17](https://cdn.v2ex.com/avatar/1bf3/d3d6/406260_normal.png?m=1715792508)||12<br><br>**[yushi17](/member/yushi17)**  <br><br>   20 天前<br><br>不是大哥你咋还 copy 别人的名字呢？|

|   |   |   |
|---|---|---|
|![ksc010](https://cdn.v2ex.com/avatar/e420/4b5b/37397_normal.png?m=1739689237)||13<br><br>**[ksc010](/member/ksc010)**  <br><br>   20 天前<br><br>主持人创建的专家 需要用户手动添加到讨论里面吗？|

|   |   |   |
|---|---|---|
|![javaluo](https://cdn.v2ex.com/avatar/7500/bbe7/29316_normal.png?m=1656820103)||14<br><br>**[javaluo](/member/javaluo)**  <br><br>   20 天前<br><br>挺不错|

|   |   |   |
|---|---|---|
|![Peiiii](https://cdn.v2ex.com/gravatar/25b646fe7cbf4ac6851de05fb188704b?s=48&d=retro)||15<br><br>**[Peiiii](/member/Peiiii)**  <br><br>OP<br><br>   20 天前<br><br>@[ksc010](/member/ksc010) 不需要，正常主持人会邀请专家进讨论，但是目前效果还不稳定。如果它没有邀请你也可以提升它|

|   |   |   |
|---|---|---|
|![Peiiii](https://cdn.v2ex.com/gravatar/25b646fe7cbf4ac6851de05fb188704b?s=48&d=retro)||16<br><br>**[Peiiii](/member/Peiiii)**  <br><br>OP<br><br>   20 天前<br><br>@[yushi17](/member/yushi17) 自己想的时候想到了这个名字，github 上一搜发现的确另外有一个项目（是一篇论文 [https://github.com/OpenBMB/AgentVerse](https://github.com/OpenBMB/AgentVerse) ）也叫 AgentVerse ，但还是取了这个名字的原因是：我目前的愿景就是最终能做成 The Universe of Agents ，希望能有“世界感”。|

|   |   |   |
|---|---|---|
|![136178128](https://cdn.v2ex.com/avatar/ebc0/fb1f/272387_normal.png?m=1740389484)||17<br><br>**[136178128](/member/136178128)**  <br><br>   20 天前<br><br>非常有意思的项目 [![](https://i.imgur.com/pmNOo2w.png)](https://i.imgur.com/pmNOo2w.png)  <br>我把以前开发的的软件需求文档发过去（只是粗略的写了写）  <br>ai 提出了很多质疑大概是有一半多都是我在开发中遇到的问题，还有些我确实没考虑到，剩下的就是一些废话。  <br>但即使是这样也是收获不少。  <br>  <br>能否提供自定义模型的功能？|

|   |   |   |
|---|---|---|
|![Peiiii](https://cdn.v2ex.com/gravatar/25b646fe7cbf4ac6851de05fb188704b?s=48&d=retro)||18<br><br>**[Peiiii](/member/Peiiii)**  <br><br>OP<br><br>   20 天前 via Android<br><br>@[136178128](/member/136178128) 自定义模型是指？现在其实可以在设置里换其它模型，比如 deepseek, openai|

|   |   |   |
|---|---|---|
|![136178128](https://cdn.v2ex.com/avatar/ebc0/fb1f/272387_normal.png?m=1740389484)||19<br><br>**[136178128](/member/136178128)**  <br><br>   20 天前<br><br>@[Peiiii](/member/Peiiii) #18 刷新后有了。|

|   |   |   |
|---|---|---|
|![xiliang](https://cdn.v2ex.com/avatar/b129/902e/427269_normal.png?m=1689564377)||20<br><br>**[xiliang](/member/xiliang)**  <br><br>   20 天前<br><br>非常有意思的项目|

|   |   |   |
|---|---|---|
|![coldcode](https://cdn.v2ex.com/avatar/2d9c/fffe/260180_normal.png?m=1508208473)||21<br><br>**[coldcode](/member/coldcode)**  <br><br>   20 天前<br><br>太棒了，头脑风暴很有启发，要是支持聊天记录导出就好了|

|   |   |   |
|---|---|---|
|![kloseWu](https://cdn.v2ex.com/gravatar/e8ffbe0c166089d4ba18ee28bb46d836?s=48&d=retro)||22<br><br>**[kloseWu](/member/kloseWu)**  <br><br>   20 天前<br><br>太棒了，这个做头脑风暴非常有用！！|

|   |   |   |
|---|---|---|
|![freesoul](https://cdn.v2ex.com/avatar/784c/d35d/148257_normal.png?m=1448345089)||23<br><br>**[freesoul](/member/freesoul)**  <br><br>   19 天前<br><br>good job|

|   |   |   |
|---|---|---|
|![knight0zh](https://cdn.v2ex.com/avatar/492b/5764/342072_normal.png?m=1704246637)||24<br><br>**[knight0zh](/member/knight0zh)**  <br><br>   19 天前<br><br>请问项目是 cursor 写的吗还是自己写的|

|   |   |   |
|---|---|---|
|![Peiiii](https://cdn.v2ex.com/gravatar/25b646fe7cbf4ac6851de05fb188704b?s=48&d=retro)||25<br><br>**[Peiiii](/member/Peiiii)**  <br><br>OP<br><br>   19 天前 via Android<br><br>@[knight0zh](/member/knight0zh) 基本都是 cursor 写的。但是自己要有判断力，要保证整体架构的健康度|

|   |   |   |
|---|---|---|
|![shangguanshaofu](https://cdn.v2ex.com/gravatar/80e74a233f90bd5caacfdec7d7e87d88?s=48&d=retro)||26<br><br>**[shangguanshaofu](/member/shangguanshaofu)**  <br><br>   19 天前<br><br>这个界面很好看，想知道这也是 cursor 设计的吗？还是说整体布局样式是自己的想法，只是用 cursor 将想法实现了|

|   |   |   |
|---|---|---|
|![Peiiii](https://cdn.v2ex.com/gravatar/25b646fe7cbf4ac6851de05fb188704b?s=48&d=retro)||27<br><br>**[Peiiii](/member/Peiiii)**  <br><br>OP<br><br>   19 天前 via Android<br><br>@[shangguanshaofu](/member/shangguanshaofu) 协同优化吧，一步步迭代出来的。cursor 是主要干活的，很多时候它写出来的界面就很好看了，我主要是挑刺的。我觉得两者的角色就像皇帝和宰相，我有时候就是这么提示 cursor 的，让它负责高层涉及到底层实现，开发者主要是挑刺和鉴别它的设计实现质量怎么样。|

|   |   |   |
|---|---|---|
|![wanniwa](https://cdn.v2ex.com/avatar/b5bd/0c79/362568_normal.png?m=1691310579)||28<br><br>**[wanniwa](/member/wanniwa)**  <br><br>   18 天前<br><br>蛮好的，有一键分享功能吗，比如生成一个长截图啥的，我想把讨论过程结果分享给别人|

|   |   |   |
|---|---|---|
|![kaminic](https://cdn.v2ex.com/gravatar/e5ce167fd258a8eb7a6b07ee80884797?s=48&d=retro)||29<br><br>**[kaminic](/member/kaminic)**  <br><br>   18 天前<br><br>体验了下非常震惊|

|   |   |   |
|---|---|---|
|![Peiiii](https://cdn.v2ex.com/gravatar/25b646fe7cbf4ac6851de05fb188704b?s=48&d=retro)||30<br><br>**[Peiiii](/member/Peiiii)**  <br><br>OP<br><br>   14 天前<br><br>@[wanniwa](/member/wanniwa) 现在支持了！|

[

](https://www.digitalocean.com/?refcode=1b51f1a7651d)

**[关于](/about)   ·   [帮助文档](/help)   ·   [博客](https://blog.v2ex.com/)   ·   [API](/help/api)   ·   [FAQ](/faq)   ·   [实用小工具](/tools)   ·   4992 人在线**   最高记录 6679   ·     [![](/static/img/language.png?v=6a5cfa731dc71a3769f6daace6784739)   Select Language](/select/language)

创意工作者们的社区

World is powered by solitude

VERSION: 3.9.8.5 · 24ms · [UTC 07:33](/worldclock#utc) · [PVG 15:33](/worldclock#pvg) · [LAX 23:33](/worldclock#lax) · [JFK 02:33](/worldclock#jfk)  
Developed with [CodeLauncher](https://cl.v2ex.pro/)  
♥ Do have faith in what you're doing.