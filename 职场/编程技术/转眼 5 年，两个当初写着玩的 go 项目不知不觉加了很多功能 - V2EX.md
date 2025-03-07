---
link: https://www.v2ex.com/t/1106238
site: V2EX
date: 2025-01-19T17:00
excerpt: 程序员 - @lesismal -
  两个项目分别是：https://github.com/lesismal/arpchttps://github.com/lesismal/nbio2024
  年到现在的主要变化：
twitter: https://twitter.com/@V2EX
slurped: 2025-02-11T16:14
title: 转眼 5 年，两个当初写着玩的 go 项目不知不觉加了很多功能，合计也有 3000 多 star 了，开心又疲惫，当作是职业生涯的纪念 - V2EX
---
[lesismal](https://github.com/lesismal) · 22 天前 · 2029 次点击

两个项目分别是： [https://github.com/lesismal/arpc](https://github.com/lesismal/arpc)

[https://github.com/lesismal/nbio](https://github.com/lesismal/nbio)

2024 年到现在的主要变化：

arpc

1. 一点缝缝补补
2. 顺便支持了 stream 。我个人觉得 stream 比较鸡肋，因为原本已经支持双向 Call/Notify 在绝大多数场景都比 stream 还方便，需要 stream 的场景并不多。

nbio

1. 优化 http/websocket 解析相关的逻辑和对象，降低了内存使用和 gc 压力，配合 SetMemoryLimit 让，在 4c 的 ubuntu 虚拟机上，百万连接 websocket 1k payload 压力测试，内存占用能控制在 1G 以内、tps 10w 。
2. 优化了 bufferpool ，[]byte 变为 *[]byte ，减少小对象频繁分配，降低 gc 压力，这是首次 sub package interface 定义变更、与之前版本不兼容，但 nbio 主 package 仍然保持兼容性，除非自定义了 mempool 否则用户因该也不需要对代码做改变。
3. 改掉了一些 buffer 相关的低概率脏内存 bug

当初这两个项目都是写着玩的

两年多前，把 arpc 也拿去 rpc benchmark 仓库去跟其他知名项目对比了下，也算是跑出了个不错的成绩，比较公平的三方测试可以请看鸟窝老师这里： [https://colobu.com/2021/08/01/benchmark-of-rpc-frameworks/](https://colobu.com/2021/08/01/benchmark-of-rpc-frameworks/) [https://colobu.com/2022/07/31/2022-rpc-frameworks-benchmarks/](https://colobu.com/2022/07/31/2022-rpc-frameworks-benchmarks/)

nbio 是为了解决 golang 海量连接场景的内存与 GC 压力、以及对应的 OOM 和 STW 问题，暂时算是 golang 社区里功能比较齐全的独一份。

arpc 实现很简单、没费太多精力，但 nbio 花费了太多精力，这几年身体都有点垮了。还想给 nbio 支持 HTTP2.0/QUIC ，但业余时间用爱发电，目前是没精力了，因为实在是太耗精力了。

5 年，40+的年纪，也算是程序员职业生涯末期，秋后的蚂蚱了，给自己留个纪念。

感谢所有我仓库的用户的支持, 感谢所有 issue pr 以及经常交流讨论的朋友们, 我个人精力有限, 大家的关注支持和交流让我的仓库完善了很多!

提前祝大家新年快乐，身体健康，诸事顺遂！


16 条回复  **•**  2025-01-23 22:34:39 +08:00

|   |   |   |
|---|---|---|
|![mysunshinedreams](https://cdn.v2ex.com/gravatar/61024f7cc3772e88729593bb55010944?s=48&d=retro)||1<br><br>**[mysunshinedreams](/member/mysunshinedreams)**  <br><br>   22 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>很棒，加油，蛇年快乐，万事如意！|

|   |   |   |
|---|---|---|
|![gongquanlin](https://cdn.v2ex.com/avatar/3e37/eb2d/278470_normal.png?m=1694084194)||2<br><br>**[gongquanlin](/member/gongquanlin)**  <br><br>   22 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>大佬大佬，很久之前就 star 了 nbio ，拜读|

|   |   |   |
|---|---|---|
|![lesismal](https://cdn.v2ex.com/avatar/a296/b6c2/497905_normal.png?m=1731414322)||3<br><br>**[lesismal](/member/lesismal)**  <br><br>OP<br><br>   22 天前<br><br>@[gongquanlin](/member/gongquanlin) #2 感谢支持! 欢迎多来交流!|

|   |   |   |
|---|---|---|
|![prosgtsr](https://cdn.v2ex.com/gravatar/127c01c2f36cd4ce3ca9afc2502f9198?s=48&d=retro)||4<br><br>**[prosgtsr](/member/prosgtsr)**  <br><br>   22 天前 via iPhone   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>nbio ，确实 nb👍|

|   |   |   |
|---|---|---|
|![arphone](https://cdn.v2ex.com/gravatar/338a8e0c82d3e2831fddf1f818302223?s=48&d=retro)||5<br><br>**[arphone](/member/arphone)**  <br><br>   22 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>很棒，加油！|

|   |   |   |
|---|---|---|
|![spritecn](https://cdn.v2ex.com/gravatar/5bd942c8bc4a90af9ffa7f3576428154?s=48&d=retro)||6<br><br>**[spritecn](/member/spritecn)**  <br><br>   22 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>afk 帖啊...同快 4 张,读的心酸|

|   |   |   |
|---|---|---|
|![wkong](https://cdn.v2ex.com/avatar/5d93/cdb1/638625_normal.png?m=1732582509)||7<br><br>**[wkong](/member/wkong)**  <br><br>   22 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>大佬加油！|

|   |   |   |
|---|---|---|
|![pangzipp](https://cdn.v2ex.com/avatar/1025/7392/108352_normal.png?m=1734326509)||8<br><br>**[pangzipp](/member/pangzipp)**  <br><br>   22 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>大佬加油！|

|   |   |   |
|---|---|---|
|![abcde123456789](https://cdn.v2ex.com/gravatar/cf2e35e035a417fb8b925392c060ce40?s=48&d=retro)||9<br><br>**[abcde123456789](/member/abcde123456789)**  <br><br>   22 天前 via Android   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>这是大佬|

|   |   |   |
|---|---|---|
|![kingcanfish](https://cdn.v2ex.com/gravatar/bdb0e1be36d026bab9c0017db1065706?s=48&d=retro)||10<br><br>**[kingcanfish](/member/kingcanfish)**  <br><br>   22 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>新年快乐 每次都能在大佬和 v 友的“激情探讨” 中学到很多新知识～|

|   |   |   |
|---|---|---|
|![huig](https://cdn.v2ex.com/avatar/b521/6d40/358636_normal.png?m=1721989758)||11<br><br>**[huig](/member/huig)**  <br><br>   21 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>后续干嘛去 我不想打工了|

|   |   |   |
|---|---|---|
|![icode1688](https://cdn.v2ex.com/gravatar/53cbb62174abf97818e229f016653fd6?s=48&d=retro)||12<br><br>**[icode1688](/member/icode1688)**  <br><br>   21 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>牛逼|

|   |   |   |
|---|---|---|
|![ziyue002](https://cdn.v2ex.com/gravatar/73039eb0e4a91760a80bb9adfd566140?s=48&d=retro)||13<br><br>**[ziyue002](/member/ziyue002)**  <br><br>   21 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>很棒，加油！|

|   |   |   |
|---|---|---|
|![lesismal](https://cdn.v2ex.com/avatar/a296/b6c2/497905_normal.png?m=1731414322)||14<br><br>**[lesismal](/member/lesismal)**  <br><br>OP<br><br>   21 天前<br><br>@[prosgtsr](/member/prosgtsr) 这算是我职业生涯里的最佳命名了  <br>  <br>@[spritecn](/member/spritecn) 末期末期, 还没全退, 但是准备中...  <br>  <br>@[kingcanfish](/member/kingcanfish) "激情探讨", 做清醒的自己~  <br>  <br>@[huig](/member/huig) 来来来, 兄弟一起干 BA|

|   |   |   |
|---|---|---|
|![stabc](https://cdn.v2ex.com/gravatar/fb5e1d9d5745f01c46d72087b6f48e57?s=48&d=retro)||15<br><br>**[stabc](/member/stabc)**  <br><br>   20 天前<br><br>为什么两个加起来一个 issue 都没有？|

|   |   |   |
|---|---|---|
|![lesismal](https://cdn.v2ex.com/avatar/a296/b6c2/497905_normal.png?m=1731414322)||16<br><br>**[lesismal](/member/lesismal)**  <br><br>OP<br><br>   18 天前<br><br>> 为什么两个加起来一个 issue 都没有？  <br>  <br>@[stabc](/member/stabc)  <br>不是一个 issue 都没有, 而是一个 Open 状态的都没有. 兄弟你查 Closed 状态的, 到目前 arpc 有 47 个, nbio 有 242 个.  <br>一个 Open 状态的都没有有两个原因:  <br>1. 作者个人形单影只, 宣传力度不够, 吹个牛说, 虽然功能性能个方面都算是同领域 Top 级的, 但知名度太低, 知道的人少, 来 issue 的人也就少. 看看其他一些同领域的, 功能比这个少, 性能不比这个强, 但是 star 比这多的多, issue 不解决比这多的多  <br>2. 每次有 issue, 作者都尽量迅速答复和解决, 所以除了极个别迷案无果而终, 绝大多数都已经解决了然后就关闭了|
