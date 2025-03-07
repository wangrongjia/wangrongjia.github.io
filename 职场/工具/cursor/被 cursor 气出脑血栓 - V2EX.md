---
link: https://www.v2ex.com/t/1102687
site: V2EX
date: 2025-01-05T16:44
excerpt: 程序员 - @wryyyyyyyyyyyy - 究竟是谁在说 2 、3 天就能写一个网站出来，之前都是自己写，不懂就 chat
  ；最近总看到不懂程序的小白啊，产品经理啊，没有基础靠 cursor 就能写出一个网站来 ，就用了一下 composer
twitter: https://twitter.com/@V2EX
slurped: 2025-02-05T14:33
title: 被 cursor 气出脑血栓 - V2EX
---

究竟是谁在说 2 、3 天就能写一个网站出来，之前都是自己写，不懂就 chat ；最近总看到不懂程序的小白啊，产品经理啊，没有基础靠 cursor 就能写出一个网站来 ，就用了一下 composer ，确实速度很快生成了一大堆代码，但 python 库一多，就骨头不顾屁股，bug 一大堆。

举个例子：

我用 fastapi 些项目 ，需要迁移，迁移是不支持用异步驱动的，但 fastapi 生成的时候用的异步，cursor 就像用异步的库来配置 alembic ，发现不支持，就把异步删了换同步，顺便把 fastapi 的异步库删了，但前面的代码都是用的异步代码，他有自己给加回来，然后又把同步的库删掉， 开始循环。

是 fastapi 有什么难度吗？还是我的操作有问题？

|   |   |   |
|---|---|---|
|![ck19920702](https://cdn.v2ex.com/avatar/6bb5/3d38/220502_normal.png?m=1711446128)||2<br><br>**[ck19920702](https://www.v2ex.com/member/ck19920702)**      30 天前 via Android   ![❤️](https://www.v2ex.com/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 44<br><br>懂得太多了，不是 0 基础，不符合要求🤣|

|   |   |   |
|---|---|---|
|![drymonfidelia](https://cdn.v2ex.com/gravatar/017bcef6e642dbf067e17838a9cd447a?s=48&d=retro)||3<br><br>**[drymonfidelia](https://www.v2ex.com/member/drymonfidelia)**      30 天前 via iPhone   ![❤️](https://www.v2ex.com/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>写前后端已经算好了，你拿它写点冷门一点的技术栈，绝对卸载不用了|

|   |   |   |
|---|---|---|
|![mumbler](https://cdn.v2ex.com/gravatar/53e87c11a8aa9c21ad440f5b5eacdba9?s=48&d=retro)||4<br><br>**[mumbler](https://www.v2ex.com/member/mumbler)**      30 天前   ![❤️](https://www.v2ex.com/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 2<br><br>现在还是 L2 自动驾驶，这种路况不好的时候，还是得人来接管，composer 每一步都有一个备份，切换到最后一次正常的版本，到关键位置，借助 ctrl+K 和自动完成手工处理|

|   |   |   |
|---|---|---|
|![ChrisFreeMan](https://cdn.v2ex.com/avatar/f6c2/fb66/539019_normal.png?m=1731040901)||5<br><br>**[ChrisFreeMan](https://www.v2ex.com/member/ChrisFreeMan)**      30 天前 via iPhone   ![❤️](https://www.v2ex.com/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 15<br><br>主要是唬一唬那些既不懂 AI 又不懂技术的人，让他们快速生成一个网上随处可见的模板网站，给他们一种处理掉了大量技术细节的幻觉，以及安抚了对技术未知的恐惧感，给他们一种不过如此的假象。<br><br>我自己也用 AI ，但只是辅助而已，把控整个软件技术细节和理解每一处发生了什么可见的未来内还得人来做。|

|                                                                                 |     |                                                                                                                                                                                                                                                                             |
| ------------------------------------------------------------------------------- | --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ![ixcode](https://cdn.v2ex.com/avatar/ef0b/a6b9/561937_normal.png?m=1704250050) |     | 6<br><br>**[ixcode](https://www.v2ex.com/member/ixcode)**      30 天前   ![❤️](https://www.v2ex.com/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 2<br><br>**多用 git commit 存档，每跑通一个功能就存档一次，当成打过关游戏那样。如果 cursor 傻逼了，就新开一个会话。一个会话中上下文太长了，cursor 的回答质量就会下降** |

|                                                                                      |     |                                                                                                                                                                                                                                |
| ------------------------------------------------------------------------------------ | --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ![q1102389095](https://cdn.v2ex.com/avatar/ab84/9b11/722517_normal.png?m=1736650173) |     | 8<br><br>**[q1102389095](https://www.v2ex.com/member/q1102389095)**      30 天前<br><br>windsurf 也是这样的，我懂后端不懂前端经常一下回到解放前。他特么有时候把我辛辛苦苦堆得样式都删了，我现在生成之前都得备份。而且有问题不考虑相互影响看完就说我看到问题了，然后库库一顿改，结果报错更多了，甚至有时候告诉他注意相互影响多看分析原因然后再执行，就是不管不顾 |

|   |   |   |
|---|---|---|
|![zhwguest](https://cdn.v2ex.com/avatar/b633/f688/433522_normal.png?m=1685067457)||10<br><br>**[zhwguest](https://www.v2ex.com/member/zhwguest)**      30 天前<br><br>关于这个问题，其实大家看看 chatgpt 自己的对话网页做得怎么样，就最有说服力了。|

|   |   |   |
|---|---|---|
|![xing7673](https://cdn.v2ex.com/gravatar/92699c48c8ccd17d47409bef8f1794be?s=48&d=retro)||11<br><br>**[xing7673](https://www.v2ex.com/member/xing7673)**      30 天前<br><br>对 auto coder 类的人工介入是必要的  <br>但是对问题的可解性判断是区别专业非专业人的点|

|   |   |   |
|---|---|---|
|![james122333](https://cdn.v2ex.com/gravatar/c31bcf9f1085a2105a3824e90c219a9f?s=48&d=retro)||12<br><br>**[james122333](https://www.v2ex.com/member/james122333)**      30 天前 via Android<br><br>不用这种东西 现在顶多用于知识了解 剩下自己弄生成|

|   |   |   |
|---|---|---|
|![csys](https://cdn.v2ex.com/gravatar/fd37e15e292183dbfe2052f41c06d10d?s=48&d=retro)||13<br><br>**[csys](https://www.v2ex.com/member/csys)**      30 天前   ![❤️](https://www.v2ex.com/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 3<br><br>你知道最恐怖的是什么吗<br><br>最恐怖的是，你的老板某天看到别人 0 基础用 cursor3 小时写个 app 出来，然后看了看 cursor 的定价，又看了看你的工资...|

|   |   |   |
|---|---|---|
|![Hans999632](https://cdn.v2ex.com/gravatar/c5d5e35df393f85bb83c31f456e789df?s=48&d=retro)||14<br><br>**[Hans999632](https://www.v2ex.com/member/Hans999632)**      30 天前<br><br>不要相信这种东西😂用它写写工具类还挺好，项目级别它最多就能写出一堆不能直接用的垃圾|

|                                                                                             |     |                                                                                                                                                                                                               |
| ------------------------------------------------------------------------------------------- | --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ![sunny352787](https://cdn.v2ex.com/gravatar/90a5a461f39a0070fa05d261cc75834d?s=48&d=retro) |     | 15<br><br>**[sunny352787](https://www.v2ex.com/member/sunny352787)**      30 天前<br><br>哈哈哈哈哈，老弟，**加个.cursorrules 文件说明一下项目基本情况试试**，写清楚用异步啥啥啥的，这破玩意欠调教，别当它是自动驾驶，得当它是个驴车，大部分路能自己走，偶尔倔脾气起来了要么抽它要么**重开个 composer** |

|   |   |   |
|---|---|---|
|![z1829909](https://cdn.v2ex.com/gravatar/347d6ba181bf07a512c0542c5fb57c56?s=48&d=retro)||16<br><br>**[z1829909](https://www.v2ex.com/member/z1829909)**      30 天前<br><br>大模型目前的局限, 上下文不能太长.  <br>想要替代码农, 需要技术和硬件的重大进步. 前者提高准确性, 后者把成本降下去.  <br>不要看现在的大模型 api 没多贵, 是因为都在不计成本卷, 寻找应用的方向.|

|   |   |   |
|---|---|---|
|![chocotan](https://cdn.v2ex.com/avatar/91e0/91be/66457_normal.png?m=1479967571)||17<br><br>**[chocotan](https://www.v2ex.com/member/chocotan)**      30 天前   ![❤️](https://www.v2ex.com/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 2<br><br>是这样的，我至少 60%的时间是在跟 ai 战斗，它总是把对的东西改错，让他改回去过一会儿又改错。  <br>我现在只能让它写最简单的增删改查|

|   |   |   |
|---|---|---|
|![Norie](https://cdn.v2ex.com/avatar/9709/0177/226070_normal.png?m=1513127863)||18<br><br>**[Norie](https://www.v2ex.com/member/Norie)**      30 天前 via Android<br><br>一个网页也网站啊。嘿嘿|

|   |   |   |
|---|---|---|
|![myluke](https://cdn.v2ex.com/avatar/af50/a6c8/293649_normal.png?m=1735781643)||19<br><br>**[myluke](https://www.v2ex.com/member/myluke)**      30 天前<br><br>还得靠自己，具体问题具体分析解决，让它给你整个大的，它弄不出来。|

|   |   |   |
|---|---|---|
|![zhengfan2016](https://cdn.v2ex.com/gravatar/df526f138d10cac8c95b274c720a6f55?s=48&d=retro)||21<br><br>**[zhengfan2016](https://www.v2ex.com/member/zhengfan2016)**      30 天前   ![❤️](https://www.v2ex.com/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 5<br><br>哈哈，最近我们老板不知道从何听说 cursor 能 5 分钟写一个网站，让我们用 cursor 把公司官网移动端 5 分钟适配了了，于是我专门给它们演示了下，它们两眼放光的期望终于放下了。<br><br>cursor 确实有进步，但是它没有视觉，根本没法理解稍微复杂的前端展示页为什么要在这里要写出这样的 css ，它只能凭借大部分人的写法去猜测。我感觉 cursor 反而更适合写后端的 curd ，一个是后端没有 ui ，不需要 cursor 有视觉，并且大部分 curd 的代码重合性很高，cursor 适合干不需要视觉或者重合性很高的代码编写。|

|   |   |   |
|---|---|---|
|![SiLenceControL](https://cdn.v2ex.com/avatar/d796/4342/575357_normal.png?m=1654591159)||22<br><br>**[SiLenceControL](https://www.v2ex.com/member/SiLenceControL)**      30 天前<br><br>我这种只用 python 进行图像处理和科学计算的人用 cursor 真的合适， 不适合真程序员|

|   |   |   |
|---|---|---|
|![quantum00549](https://cdn.v2ex.com/gravatar/414d06c01a4defe58af4539227be20c1?s=48&d=retro)||23<br><br>**[quantum00549](https://www.v2ex.com/member/quantum00549)**      30 天前 via iPhone   ![❤️](https://www.v2ex.com/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 4<br><br>我觉得用这类工具首先要把自己当作架构师，做好任务分解，让他一个模块一个模块写，把自己当老板，那现在 AI 还差太多了|

|   |   |   |
|---|---|---|
|![crackidz](https://cdn.v2ex.com/gravatar/e5311b443d279d0bce5f7e7606af6c41?s=48&d=retro)||24<br><br>**[crackidz](https://www.v2ex.com/member/crackidz)**      30 天前<br><br>很正常的，什么东西你遇到无脑吹的，都应该小心。起码作为你自己而言，要知道模型的能力边界在哪里。<br><br>当然，对我而言，AI 还是提供了不错的生产力加成|

|   |   |   |
|---|---|---|
|![Damn](https://cdn.v2ex.com/gravatar/11c75c59eda7e91d605308d0664053bb?s=48&d=retro)||25<br><br>**[Damn](https://www.v2ex.com/member/Damn)**      30 天前 via iPhone<br><br>但是气应该气不出脑血栓的。  <br>脑血栓的成因一般是血流缓慢血压低什么的。  <br>你可以气出脑溢血的。  <br>狗头.jpg|

|   |   |   |
|---|---|---|
|![XTTX](https://cdn.v2ex.com/avatar/1d7d/8905/477613_normal.png?m=1586326604)||26<br><br>**[XTTX](https://www.v2ex.com/member/XTTX)**      30 天前<br><br>最近经常碰到 AI 写出来的大便。 有萌新自以为懂了，要倒反天罡，用 AI 画的 demo 取代成熟 UI 的。我也碰到过程序员用 cursor 弄出一坨坨屎山还不自知的。  <br>@[mumbler](https://www.v2ex.com/member/mumbler) 从今以后这都是常态，我基本是 Ai 主力的写了。但是我有成熟的代码 context 和 hook pattern 让它照着输出。|

|   |   |   |
|---|---|---|
|![daimaosix](https://cdn.v2ex.com/avatar/dad4/9f17/377923_normal.png?m=1736750104)||27<br><br>**[daimaosix](https://www.v2ex.com/member/daimaosix)**      30 天前 via Android<br><br>很正常，我写点东西都要写好多文档才行，真羡慕别人轻轻松松就写出来个东西，我可以肯定并没有注重代码是否优雅，技术的更多细节|

|   |   |   |
|---|---|---|
|![ThomasKim](https://cdn.v2ex.com/avatar/fce5/6add/555279_normal.png?m=1699682747)||28<br><br>**[ThomasKim](https://www.v2ex.com/member/ThomasKim)**      30 天前<br><br>挺好奇发起《大模型人工智能是不是马上就要代替程序员了》帖子的 V 友要是看到你的帖子会有如何感想|

|   |   |   |
|---|---|---|
|![exiaduck](https://cdn.v2ex.com/gravatar/d9945d9f3d0d31231d8e68dff6047b85?s=48&d=retro)||29<br><br>**[exiaduck](https://www.v2ex.com/member/exiaduck)**      30 天前   ![❤️](https://www.v2ex.com/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>因为那种号称 x 小时做出成品的营销视频，背后编排、彩排了 N 次，看一乐得了。|

|   |   |   |
|---|---|---|
|![estk](https://cdn.v2ex.com/avatar/12f5/d602/576589_normal.png?m=1704726369)||30<br><br>**[estk](https://www.v2ex.com/member/estk)**      30 天前 via iPhone<br><br>cursor 唯一用处是代码补全，但是 vscode 也免费了，cursor 我就不用了|

|   |   |   |
|---|---|---|
|![glcolof](https://cdn.v2ex.com/avatar/8fa3/d99c/461811_normal.png?m=1724812917)||33<br><br>**[glcolof](https://www.v2ex.com/member/glcolof)**      30 天前<br><br>Cursor 使用的大模型，上下文长度应该也就 128K ，换算成代码不到 2000 行，也就是说，代码行数超过 2000 行之后，AI 性能会开始下降，代码量越大，性能下降越多。|

|   |   |   |
|---|---|---|
|![Rehtt](https://cdn.v2ex.com/avatar/b059/4b34/340262_normal.png?m=1679377084)||34<br><br>**[Rehtt](https://www.v2ex.com/member/Rehtt)**      30 天前 via Android<br><br>感觉唯一好用的地方是可以按规律生成一些“笨代码”，比如 a=1; b=2; c=3 这种有明显规律的|

|   |   |   |
|---|---|---|
|![wangtian2020](https://cdn.v2ex.com/avatar/5f94/b385/510746_normal.png?m=1731907010)||36<br><br>**[wangtian2020](https://www.v2ex.com/member/wangtian2020)**      30 天前<br><br>整天重复的页面逻辑写不完的人可以用，对写创意性代码的人一点儿用都没有。2000 行的 threejs 单页面，试过，他帮不了我|

|   |   |   |
|---|---|---|
|![assassing](https://cdn.v2ex.com/avatar/50a6/fac6/78369_normal.png?m=1724825959)||37<br><br>**[assassing](https://www.v2ex.com/member/assassing)**      30 天前<br><br>应该多吹吹 AI 编程，让不懂技术的老板们多吃点苦头|

|   |   |   |
|---|---|---|
|![AlexHsu](https://cdn.v2ex.com/avatar/0af6/2754/13706_normal.png?m=1677143930)||38<br><br>**[AlexHsu](https://www.v2ex.com/member/AlexHsu)**      30 天前<br><br>一群大傻子狂欢罢了 用 cursor 的前提是你用他生成的代码你得每一行都看得懂  <br>你这个谢谢 rules 就行了 不是啥大问题 大问题是一些性能的问题 cluade 总是想当然|

|   |   |   |
|---|---|---|
|![konakona](https://cdn.v2ex.com/avatar/15c0/8959/38523_normal.png?m=1710480337)||39<br><br>**[konakona](https://www.v2ex.com/member/konakona)**      30 天前<br><br>没错，在使用 cursor 也遇到过无论怎么提点它，它都在来回 2 份代码里重复，骂也骂了，让它重新总结，它还能再继续错。<br><br>明知故犯的那种，这个时候我会换 GPT o1|

|   |   |   |
|---|---|---|
|![iyiluo](https://cdn.v2ex.com/gravatar/a6259a1cf7368bed8dfbab87b4a32600?s=48&d=retro)||40<br><br>**[iyiluo](https://www.v2ex.com/member/iyiluo)**      30 天前<br><br>我自己使用的经验不能给它复杂逻辑的东西，得拆成一个个逻辑简单的单元方法，然后自己组合起来。太复杂的容易抽风|

|   |   |   |
|---|---|---|
|![sampeng](https://cdn.v2ex.com/gravatar/3b198446b72d1e5a3b0090f106a75f3c?s=48&d=retro)||41<br><br>**[sampeng](https://www.v2ex.com/member/sampeng)**      30 天前 via iPhone<br><br>我的经验是代码模块设计本身有问题，当我发现 cursor 开始循环或者犯傻就停下来，快速指挥 cursor 重构：不变的封装，变的抽象。然后再继续前面的任务，cursor 就知道怎么处理了。也没幻觉也没死循环，也不去乱改已经正确的代码了|

|   |   |   |
|---|---|---|
|![visper](https://cdn.v2ex.com/gravatar/838db077a2334ed6bcbc29c29ab41a6e?s=48&d=retro)||42<br><br>**[visper](https://www.v2ex.com/member/visper)**      30 天前<br><br>说实话，当一下项目做大了在用了然后要加功能或者维护修改的时候，你们放心用 cursor 这样的 ai 让他同时修改多个文件吗？等下不知道改了哪里全部乱了。我好像只敢在开始的时候让它做个初始版本出来，然后自己开始在里面改，后面只敢 ctrl+k 让它改单个文件了。|

|   |   |   |
|---|---|---|
|![Bluecoda](https://cdn.v2ex.com/avatar/d7ea/d549/11809_normal.png?m=1590386952)||43<br><br>**[Bluecoda](https://www.v2ex.com/member/Bluecoda)**      30 天前<br><br>应该是你的 prompt 写得不够好，不能简单来。prompt 要非常的细化，需要把 reason 和你的预期写得非常清楚，如果它生成的不对，需要限定好它输出的 scope|

|   |   |   |
|---|---|---|
|![keakon](https://cdn.v2ex.com/avatar/81c2/f886/2704_normal.png?m=1723105389)||44<br><br>**[keakon](https://www.v2ex.com/member/keakon)**      30 天前<br><br>给它一个方案，告诉它需要异步，用什么库实现。不明确的需求它就随便写。|

|   |   |   |
|---|---|---|
|![devilte](https://cdn.v2ex.com/avatar/e5ef/96d1/527498_normal.png?m=1640245187)||45<br><br>**[devilte](https://www.v2ex.com/member/devilte)**      30 天前<br><br>@[csys](https://www.v2ex.com/member/csys) 有被说到 -_-，老板整天发各种 cursor 、windsurf 、bolt 、devin 的文章过来，让对比哪个适合我们。顺便再 PUA 一下，再不努力 都要被这些取代了...|

|   |   |   |
|---|---|---|
|![sss393](https://cdn.v2ex.com/avatar/8966/fef2/306920_normal.png?m=1694573888)||47<br><br>**[sss393](https://www.v2ex.com/member/sss393)**      30 天前<br><br>cursor 适合项目起步阶段：打草稿、画 UI 布局、写单元测试。完全依靠 cursor 不现实。|

|   |   |   |
|---|---|---|
|![hi2hi](https://cdn.v2ex.com/gravatar/57850c996ab1b8a93ee3fe8862392b06?s=48&d=retro)||49<br><br>**[hi2hi](https://www.v2ex.com/member/hi2hi)**      30 天前<br><br>体验了免费的 15 天，写简单的、重复的就让它写，写复杂的，，，，算了，我自己写|

|   |   |   |
|---|---|---|
|![mumbler](https://cdn.v2ex.com/gravatar/53e87c11a8aa9c21ad440f5b5eacdba9?s=48&d=retro)||51<br><br>**[mumbler](https://www.v2ex.com/member/mumbler)**      30 天前<br><br>@[sss393](https://www.v2ex.com/member/sss393) #47 你对新东西还是有偏见，我们已经完全依赖 cursor 两个月了，肯定会遇到问题，但坚决不退让，想办法解决，掌握 cursor 使用方法也是一种技能，比花时间在传统方式上更有价值|

|   |   |   |
|---|---|---|
|![vipfts](https://cdn.v2ex.com/avatar/03a0/4432/223857_normal.png?m=1709193364)||52<br><br>**[vipfts](https://www.v2ex.com/member/vipfts)**      30 天前<br><br>请出示病例, 否则举报你造谣, 拘留 15 天🤡|

|   |   |   |
|---|---|---|
|![yh7gdiaYW](https://cdn.v2ex.com/avatar/5e37/b76a/119748_normal.png?m=1710228712)||53<br><br>**[yh7gdiaYW](https://www.v2ex.com/member/yh7gdiaYW)**      30 天前<br><br>同气，用 cursor 做了一个需求，10 个 sql 写出 8 个 bug ，我 tm 之前两个月都写不出这么多 bug （认真自测.jpg ）。  <br>问题出要出在 cursor 一次补全的代码太多了，看起来又很像那么回事儿，执行起来也能跑，但修 bug 时复盘发现细节就是错的...之前用 copilot 一行一行来就不会有这种问题，开发时的效率也不会比 cursor 这种一次补全一堆低多少|

|   |   |   |
|---|---|---|
|![migu](https://cdn.v2ex.com/gravatar/494b347636cc382e240b57a8b6a3d029?s=48&d=retro)||54<br><br>**[migu](https://www.v2ex.com/member/migu)**      30 天前<br><br>终于有人说了，也就初始化和写写常规的模板配置有点用，其他就是一坨屎，除非你 prompt 写的足够完整，但是那点精力，代码都改完一半了|

|   |   |   |
|---|---|---|
|![tlerbao](https://cdn.v2ex.com/avatar/9deb/c5d9/421999_normal.png?m=1691047818)||55<br><br>**[tlerbao](https://www.v2ex.com/member/tlerbao)**      30 天前   ![❤️](https://www.v2ex.com/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>所以强如微软 强如 github copilot 自家的 vscode ，自家的 copilot 一直都没出 cursor 这些功能，最近出了也是被逼的，<br><br>还得是 copilot 的代码质量，但是大部分时候还就是 tab tab 最常用罢了|

|   |   |   |
|---|---|---|
|![mandex](https://cdn.v2ex.com/avatar/39b6/ba49/155064_normal.png?m=1730884794)||56<br><br>**[mandex](https://www.v2ex.com/member/mandex)**      30 天前<br><br>就当玩具玩一玩，真当生产力工具还差点意思。[![](https://i.imgur.com/NIvxivj.png)](https://i.imgur.com/NIvxivj.png)|

|   |   |   |
|---|---|---|
|![lekai63](https://cdn.v2ex.com/avatar/8813/03a4/69052_normal.png?m=1418357036)||57<br><br>**[lekai63](https://www.v2ex.com/member/lekai63)**      30 天前<br><br>所以我用 Zed 。 代码还是得自己控制，但是 AI 可以帮我生成一个小模块、小组件。跟我聊一聊|

|   |   |   |
|---|---|---|
|![Zzzz77](https://cdn.v2ex.com/avatar/5ae2/3685/528185_normal.png?m=1656335441)||58<br><br>**[Zzzz77](https://www.v2ex.com/member/Zzzz77)**      30 天前   ![❤️](https://www.v2ex.com/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 2<br><br>很简单，大多数觉得 AI 可以代替自己的人，你不能说他们是吹牛，或许他们的水平（工作）真的能被 AI 代替掉。  <br>换个说法，没接触过代码的人，看着刚入门的小白程序员写了个百度首页的前端页面，也会直呼大神，觉得百度不过如此。|

|   |   |   |
|---|---|---|
|![Zzzz77](https://cdn.v2ex.com/avatar/5ae2/3685/528185_normal.png?m=1656335441)||60<br><br>**[Zzzz77](https://www.v2ex.com/member/Zzzz77)**      30 天前   ![❤️](https://www.v2ex.com/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>@[Zzzz77](https://www.v2ex.com/member/Zzzz77) 补充一句，这类人通常有一种自我 PUA 的精神：这个生成的不对，肯定是我的问题，我的提示词写的不好。|

|   |   |   |
|---|---|---|
|![wangyzj](https://cdn.v2ex.com/avatar/c2e5/7e77/204533_normal.png?m=1480955939)||61<br><br>**[wangyzj](https://www.v2ex.com/member/wangyzj)**      30 天前<br><br>都说 cursor 这种代码辅助可以替代程序员  <br>但我觉得只有高端程序员才会使用 cursor|

|   |   |   |
|---|---|---|
|![mht](https://cdn.v2ex.com/avatar/8e3e/1bff/185360_normal.png?m=1677822183)||62<br><br>**[mht](https://www.v2ex.com/member/mht)**      30 天前<br><br>我拿来把蓝湖里的设计图自动生成的代码 html+css 复制进去，然后按我引用代码的风格生成同样风格的切图后的代码，很省事很舒服。。。<br><br>能省掉很多不需要什么脑子又繁琐的工作，假如你想让他做一些复杂的，非通用业务的东西，那他肯定不如自己写的好，后端代码我一般不让他碰。|

|   |   |   |
|---|---|---|
|![sss393](https://cdn.v2ex.com/avatar/8966/fef2/306920_normal.png?m=1694573888)||63<br><br>**[sss393](https://www.v2ex.com/member/sss393)**      30 天前<br><br>@[mumbler](https://www.v2ex.com/member/mumbler) #51 兄弟，不是只有你天天在用，我也买了俩月了。用来写 nestjs+前端。好不好用我能不清楚么。cursor 最好用的阶段就是打草稿、ui 布局、单测。业务复杂之后只能给我打辅助。|

|   |   |   |
|---|---|---|
|![keychain](https://cdn.v2ex.com/avatar/3810/ea0a/80643_normal.png?m=1441601507)||66<br><br>**[keychain](https://www.v2ex.com/member/keychain)**      30 天前   ![❤️](https://www.v2ex.com/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>基本就是说，你脑海中已经有一个差不多知道怎么做的框架了，然后让它帮你做：  <br>1. 每次让它尽量做小一点的变更，减少出错概率。  <br>2. 每次修改后功能测试没问题的话，最好手动 commit 一下，方便后续在此基础上修改。  <br>3. 一点发现 AI 的修改开始不对劲，怎么改都改不对，最好重新开个对话，原来的上下文已经造成污染了。|

|   |   |   |
|---|---|---|
|![JackyYang](https://cdn.v2ex.com/avatar/5ce0/f52d/365219_normal.png?m=1736132074)||69<br><br>**[JackyYang](https://www.v2ex.com/member/JackyYang)**      30 天前<br><br>@[keychain](https://www.v2ex.com/member/keychain) 同感，  <br>1. 业务理解，项目整体框架需要开发者自己设计。  <br>2. AI 当前阶段更适合给它某单一功能，描述清楚，完成起来更高效  <br>3. 如果结果不符合预期，切记不要持续陷入到一个对话：开新对话，完善 Prompt, 补充必要的上下文|

|   |   |   |
|---|---|---|
|![sampeng](https://cdn.v2ex.com/gravatar/3b198446b72d1e5a3b0090f106a75f3c?s=48&d=retro)||70<br><br>**[sampeng](https://www.v2ex.com/member/sampeng)**      30 天前<br><br>我其实很奇怪。难道你不给他直接指定上下文文件的么？全靠它自己 search ？  <br>直接给上下文文件，很准确啊|

|   |   |   |
|---|---|---|
|![chanChristin](https://cdn.v2ex.com/avatar/b0c6/6f54/415795_normal.png?m=1728630548)||71<br><br>**[chanChristin](https://www.v2ex.com/member/chanChristin)**      30 天前<br><br>同感，我在项目里面做个需求，根本搞不定，因为项目太久了，里面有很多历史工具和包袱，用这玩意还不够闹心的。|

|   |   |   |
|---|---|---|
|![snitfk](https://cdn.v2ex.com/gravatar/fd1fa696e8ae56c3f1473a34922d5c2d?s=48&d=retro)||72<br><br>**[snitfk](https://www.v2ex.com/member/snitfk)**      30 天前<br><br>不要光看现在做什么，要看这块的发展增速。从现在看 AI 在代码这块做出来的东西完整度是越来越高了，以前只能写写小东西，一跑起来还一堆 BUG 。现在写出来的东西直接能跑，你还能告诉他你要加什么，他给你加上去。肯定和人还没办法比，但看这增速。估计也就二三年时间，初级开发人员能做的速度 AI 这边也就都能做了。|

|   |   |   |
|---|---|---|
|![jesseZhang](https://cdn.v2ex.com/avatar/a9fa/7d66/248409_normal.png?m=1502615496)||74<br><br>**[jesseZhang](https://www.v2ex.com/member/jesseZhang)**      30 天前<br><br>还是得本身有开发基础，开始得磕开发啊，说的太抽象，它就乱搞。|

|   |   |   |
|---|---|---|
|![mightybruce](https://cdn.v2ex.com/avatar/0eed/e14d/567660_normal.png?m=1711593178)||75<br><br>**[mightybruce](https://www.v2ex.com/member/mightybruce)**      30 天前<br><br>来来来，你先贴出你的 .cursorrules ， 让我对你会使用 AI 的能力消除疑问。|

|                                                                                                |     |                                                                                                                                                                                                                                               |
| ---------------------------------------------------------------------------------------------- | --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ![wryyyyyyyyyyyy](https://cdn.v2ex.com/gravatar/b74d7ceb779ec6c28adf8788d7f4cf0d?s=48&d=retro) |     | 77<br><br>**[wryyyyyyyyyyyy](https://www.v2ex.com/member/wryyyyyyyyyyyy)**      30 天前<br><br>@[mightybruce](https://www.v2ex.com/member/mightybruce) 抱歉，由于是第一次使用 composer ，我并不知道有这个东西，之前都是单文件 ctrl+l/k ，今晚我将使用 .cursorrules 再次尝试。同时感谢让我学到新知识。 |

|   |   |   |
|---|---|---|
|![wryyyyyyyyyyyy](https://cdn.v2ex.com/gravatar/b74d7ceb779ec6c28adf8788d7f4cf0d?s=48&d=retro)||79<br><br>**[wryyyyyyyyyyyy](https://www.v2ex.com/member/wryyyyyyyyyyyy)**      30 天前<br><br>@[sampeng](https://www.v2ex.com/member/sampeng) 之前我也是这么干的，但不是想起来看到好多无经验快速开发项目的，我也想试试，刚好有新项目，就只描述不修改代码，发现让 cursor 做主力不太行，打打辅助还可以。|

|   |   |   |
|---|---|---|
|![shm7](https://cdn.v2ex.com/avatar/ba72/3d07/182027_normal.png?m=1713778624)||80<br><br>**[shm7](https://www.v2ex.com/member/shm7)**      30 天前<br><br>怎么样？救回来没？|

|   |   |   |
|---|---|---|
|![angryfish](https://cdn.v2ex.com/gravatar/f8c9d67d4c9c784b8ef637ec2d217f5c?s=48&d=retro)||81<br><br>**[angryfish](https://www.v2ex.com/member/angryfish)**      30 天前<br><br>我现在用 ai 都是实现一些常用的功能，把他当做 ai 模块搬运工，比如实现常见的功能，像轮播图管理，文章管理这些，生成基本的功能，然后 ctrl+K ，让他修改一些函数，逻辑。  <br>太复杂了 ai 现在搞不定的，而且描述也很费劲，这部分自己写都可以。|

|   |   |   |
|---|---|---|
|![seenthewind](https://cdn.v2ex.com/avatar/2d1d/a0d0/42654_normal.png?m=1374808697)||83<br><br>**[seenthewind](https://www.v2ex.com/member/seenthewind)**      30 天前<br><br>你用 ai 来写 fastapi 基本上是自寻死路。<br><br>要用它来写这两年的热点语言/框架，越看不懂、越时髦、越被人吹的牛逼越大越要用这个。<br><br>比如吧，你上来就说用 go 的协程给我来一段 xxxx ，直接秒出秒编译运行。<br><br>就好比要打儿子，你得先认识他爹是什么人。|

|   |   |   |
|---|---|---|
|![Jius7u](https://cdn.v2ex.com/gravatar/da46458a09389742bbdff93d4f65ec06?s=48&d=retro)||84<br><br>**[Jius7u](https://www.v2ex.com/member/Jius7u)**      29 天前<br><br>我废了 2 个号了 才写了 2 个基础的功能😒|

|   |   |   |
|---|---|---|
|![sampeng](https://cdn.v2ex.com/gravatar/3b198446b72d1e5a3b0090f106a75f3c?s=48&d=retro)||85<br><br>**[sampeng](https://www.v2ex.com/member/sampeng)**      29 天前<br><br>@[wryyyyyyyyyyyy](https://www.v2ex.com/member/wryyyyyyyyyyyy) 我觉得那是不可能的，AI 天然就会有幻觉。尤其内容特别多的时候，他的注意力无法集中在正好你需要的模块上。我已经实验过。如果一个函数或者一块代码包含了多种不相关的代码逻辑和分支，他越会莫名其妙去把好的改成坏的。如果一个代码块越聚焦，他基本不会去乱动。目前我的 cursor 乱改代码基本是因为我有一大段代码做了 n 件事。当然，也是他自个儿写的。。我还得给他擦屁股，告诉他不要这样写，给我把功能拆分开。其实也是一个不错的过程。cursor 辅助的情况下重构代码非常香，以前不想干的事，现在干起来毫无心理负担|

|   |   |   |
|---|---|---|
|![sampeng](https://cdn.v2ex.com/gravatar/3b198446b72d1e5a3b0090f106a75f3c?s=48&d=retro)||86<br><br>**[sampeng](https://www.v2ex.com/member/sampeng)**      29 天前<br><br>我觉得很大的一个问题是他的代码全文搜索，依靠的是向量查找。向量相似度查找本身就会错误的概率，而且非常大。所以我现在基本是写了一对的 notepad 。把一些功能模块聚焦好。直接告诉他看这几个文件改哪些内容。这样才能保证他不会搞错。。。  <br>新东西，就是要摸索怎么用才最舒服。没有十全十美的工具|

|   |   |   |
|---|---|---|
|![fresco](https://cdn.v2ex.com/gravatar/e6680262abd3902034ca18b51734cd70?s=48&d=retro)||87<br><br>**[fresco](https://www.v2ex.com/member/fresco)**      29 天前<br><br>目前不到一周，写完了一个 flutter 的 APP ，感觉 50%以上的时间都在做无用功，来来回回的改，还是需要一些基础，配合着用会舒服很多。|

|   |   |   |
|---|---|---|
|![iyaozhen](https://cdn.v2ex.com/avatar/6406/09f6/68154_normal.png?m=1735210344)||88<br><br>**[iyaozhen](https://www.v2ex.com/member/iyaozhen)**      29 天前<br><br>说实话，这个问题得 python 背锅。人写异步的都有点坑 各种库兼容性问题 不支持|

|   |   |   |
|---|---|---|
|![wtdd](https://cdn.v2ex.com/gravatar/225342b8261e28f00a28f3bcfd24134c?s=48&d=retro)||89<br><br>**[wtdd](https://www.v2ex.com/member/wtdd)**      29 天前<br><br>即便一个小功能，prompt 写的详细程度，基本要脑子里程序同步写好了，最多差点算法，  <br>目前 AI 替代的是程序员，不是架构师，2 ，3 天能写出一个网站，说明自身就有这个水平|

|   |   |   |
|---|---|---|
|![meteora0tkvo](https://cdn.v2ex.com/gravatar/7de15ad4a50e967054101a207082176f?s=48&d=retro)||93<br><br>**[meteora0tkvo](https://www.v2ex.com/member/meteora0tkvo)**      29 天前<br><br>ai 生成的代码得人工 code review 和跑一遍白盒测试，不可能一个不懂程序的人能直接用的😂|

|   |   |   |
|---|---|---|
|![Bluecoda](https://cdn.v2ex.com/avatar/d7ea/d549/11809_normal.png?m=1590386952)||94<br><br>**[Bluecoda](https://www.v2ex.com/member/Bluecoda)**      29 天前<br><br>@[hongye](https://www.v2ex.com/member/hongye) 其实还是挺容易的<br><br>第一点，不要把它认为是 AI ，其实只是一个比较聪明一点点的代码生成器，自身有很多缺陷，要输出好的代码，需要一些技巧。  <br>第二点，去看看一些提示词的编写技巧，其实都差不多的，来来去去都是那一些。主要是给的指令要非常清楚和细化，能多打一点字就多打一点，不要省。要限定好生成的代码的框框，比如你要一段代码，最好说明你的代码是要在 fastapi 中使用，这样生成代码出错的可能性就会降低。|

|   |   |   |
|---|---|---|
|![pengfei0916](https://cdn.v2ex.com/gravatar/504954a277509f8cd7e7ac2da287bcb7?s=48&d=retro)||95<br><br>**[pengfei0916](https://www.v2ex.com/member/pengfei0916)**      28 天前<br><br>这几天利用碎片,用 cursor 写一个后台管理系统,fastapi+vue(未完成),使用感觉:  <br>1. 项目大的时候很卡,反应超级慢  <br>2. 解决控制台启动的 bug,直接扔给他,解决速度很快  <br>3. 产品思维很重要,先规划好做什么,然后可以先生成产品文档,在搭建项目框架目录,最后拆分细节,一点点告诉他怎么做,比如使用 fastapi 实现登录接口,他写的很快  <br>4. 解决一个问题,调试好以后一定要提交 git,因为有时候回复和修改的很差,所以要先存档<br><br>作为写代码过程的辅助是非常棒的,具体的等用的多了,可能会有更多的想法吧|

|   |   |   |
|---|---|---|
|![mogutouer](https://cdn.v2ex.com/avatar/2140/3c8d/97149_normal.png?m=1723465965)||96<br><br>**[mogutouer](https://www.v2ex.com/member/mogutouer)**      25 天前<br><br>很多人觉得 cursor 不好用是还停留在程序员思维，你如果站在产品经理的角度去思考产品和每个步骤，一个星期干完一个月的活儿轻轻松松好不啦。要用 cursor ，你首先要能表达清楚你要他做什么具体的事情，这件事情跟其他事情有什么关联，跟哪个目录的文件有关系，就算是 chatgpt 你也不可能在自己表达不清楚的情况下让他给你非常精准的东西。<br><br>一周五天，用了一千多个对话，完成了三个前后端大项目的功能增加和一个 python 项目，这些工作量在以前起码要干一个月。把重点放在逻辑思维上，码代码这种重复又累的工作交给 AI 。  <br>[![](https://i.imgur.com/aE7WYjJ.png)](https://i.imgur.com/aE7WYjJ.png)|

|   |   |   |
|---|---|---|
|![wryyyyyyyyyyyy](https://cdn.v2ex.com/gravatar/b74d7ceb779ec6c28adf8788d7f4cf0d?s=48&d=retro)||97<br><br>**[wryyyyyyyyyyyy](https://www.v2ex.com/member/wryyyyyyyyyyyy)**      25 天前<br><br>5 天，一天问 200 次，不提效率会降低，算你工作 10 个 h ，一 h 20 次，3 分钟一次， 你这是什么实力啊，ai 产生的代码眼睛不过一遍吗？里面没看懂的接着查，理解+debug 可能都不止 3min ， 而且哪有这么多的重复代码给你生成啊。|
