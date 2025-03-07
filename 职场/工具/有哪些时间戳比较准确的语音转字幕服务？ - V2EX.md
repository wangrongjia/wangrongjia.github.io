---
link: https://www.v2ex.com/t/1109990
site: V2EX
date: 2025-02-08T19:10
excerpt: 程序员 - @henix -
  场景：做视频加字幕（中文，不需要翻译），希望先自动出个字幕，然后人工校对可接受付费，最好付给不会跑路的大厂尝试过：1\. 本地跑
  openai-whipser  * 本
twitter: https://twitter.com/@V2EX
slurped: 2025-02-10T09:16
title: 有哪些时间戳比较准确的语音转字幕服务？ - V2EX
---
   
[henix](https://github.com/henix) · 1 天前 · 975 次点击

场景：做视频加字幕（中文，不需要翻译），希望先自动出个字幕，然后人工校对

可接受付费，最好付给不会跑路的大厂

尝试过：

1. 本地跑 openai-whipser

- 本地跑 Python ，比较慢
- 识别中文的时候，时间戳只能精确到 1 秒，而不是 0.1 秒（明明识别日语的时候都可以精确到 0.1 秒），导致字幕展示时间不精确，不能用

2. 剪映字幕识别

- 需要剪映 SVIP ，每月有免费额度
- 断开的位置经常在一句话的中间，但我希望一个完整的意思作为一条字幕，需要后期人工修正时间轴

1. 腾讯云录音文件识别 [https://cloud.tencent.com/document/product/1093/37823](https://cloud.tencent.com/document/product/1093/37823)

- 单句太长，20 多秒中间没有任何断句，作为字幕不可行


10 条回复  **•**  2025-02-09 16:57:47 +08:00

|   |   |   |
|---|---|---|
|![JensenQian](https://cdn.v2ex.com/avatar/e503/54ce/486663_normal.png?m=1716974467)||1<br><br>**[JensenQian](/member/JensenQian)**  <br><br>   1 天前<br><br>飞书以前有免费额度的  <br>最近不知道是不是限制了我记得|

|   |   |   |
|---|---|---|
|![timerring](https://cdn.v2ex.com/avatar/a1e8/ee40/693273_normal.png?m=1735282380)||2<br><br>**[timerring](/member/timerring)**  <br><br>   1 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>我在去年下半年做过一个直播录制识别字幕并压制的项目 [https://github.com/timerring/bilive](https://github.com/timerring/bilive)  <br>  <br>我基本上试遍了市面上的字幕识别项目以及 api ，效果很难达到你说的既能精确到 0.1 秒（实际上精确到 0.1 秒作用也不大，除非你做的是某类型的说唱字幕，1 秒能输出若干字），又能准确识别断句，还能合理地将句子划分刚好合适，最后还是选择本地跑 openai 的 whisper ，其实很多时候没有 silver bullet ，但就 asr 任务来说，要方便就选剪映，要实惠就选本地跑 whisper ，至于其他云服务商例如腾讯云，讯飞，谷歌等等，则是既不实惠也不方便，效果也没差别。|

|   |   |   |
|---|---|---|
|![mumbler](https://cdn.v2ex.com/gravatar/53e87c11a8aa9c21ad440f5b5eacdba9?s=48&d=retro)||3<br><br>**[mumbler](/member/mumbler)**  <br><br>   1 天前<br><br>groq 刚刚开放了付费，whisper 飞一样的速度，还很便宜|

|   |   |   |
|---|---|---|
|![rekulas](https://cdn.v2ex.com/avatar/ff00/e7ff/173283_normal.png?m=1726814747)||4<br><br>**[rekulas](/member/rekulas)**  <br><br>   1 天前<br><br>我之前搞过,基于开源语音识别+分词进行字幕生成, 纯中文下误差可以控制在 200ms 内, 用于视频生产服务, 后面空了整理个开源出来|

|   |   |   |
|---|---|---|
|![yeqizhang](https://cdn.v2ex.com/gravatar/1a3226bf91c6372840ed0c76742a2941?s=48&d=retro)||5<br><br>**[yeqizhang](/member/yeqizhang)**  <br><br>   1 天前 via Android<br><br>用 faster-whipser ，显卡好点就会快点|

|                                                                                        |     |                                                                                                                                                         |
| -------------------------------------------------------------------------------------- | --- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ![coreJK](https://cdn.v2ex.com/gravatar/51f9f89af340304c3d4fe9dbcfd91ebf?s=48&d=retro) |     | 6<br><br>**[coreJK](/member/coreJK)**  <br><br>   1 天前 via Android<br><br>**可以试试 potplayer 的，有声字幕功能，满足你的场景，带字幕浏览器功能，可人工编辑导出（封装的 faster-whipser ），挺好用的** |

|                                                                                |     |                                                                                                                                                                                                                                                   |
| ------------------------------------------------------------------------------ | --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ![Nosub](https://cdn.v2ex.com/avatar/4427/a61e/645252_normal.png?m=1717479623) |     | 7<br><br>**[Nosub](/member/Nosub)**  <br><br>   1 天前 via iPhone   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>看到熟悉的话题，说两句，无论腾讯云还是阿里云，都可以精确到词的 api 参数，如果你是程序员，写一个分词并不难，另外如果你是自己制作视频，不是做软件，用剪映旧版本，语音识别没有次数限制。 |

|   |   |   |
|---|---|---|
|![henix](https://cdn.v2ex.com/gravatar/41ecaf675f9a963ac47aec132fd468a6?s=48&d=retro)||8<br><br>**[henix](/member/henix)**  <br><br>OP<br><br>   1 天前<br><br>@[Nosub](/member/Nosub) 确实，我今天又看了下，有精确到词的 api 参数，之前只是在控制台网页上试了一下|

|   |   |   |
|---|---|---|
|![shellus](https://cdn.v2ex.com/avatar/b78b/ca36/95868_normal.png?m=1704536677)||9<br><br>**[shellus](/member/shellus)**  <br><br>   22 小时 2 分钟前<br><br>相对来说，剪映识别效果最好，人工修正必不可少的。|

|                                                                                      |     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| ------------------------------------------------------------------------------------ | --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ![heimoshuiyu](https://cdn.v2ex.com/avatar/3d31/8385/456629_normal.png?m=1725589093) |     | 10<br><br>**[heimoshuiyu](/member/heimoshuiyu)**  <br><br>   16 小时 16 分钟前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>> 本地跑 Python ，比较慢  <br>  <br>**使用 faster-whisper + 显卡**  <br>  <br>> 识别中文的时候，时间戳只能精确到 1 秒，而不是 0.1 秒（明明识别日语的时候都可以精确到 0.1 秒），导致字幕展示时间不精确，不能用  <br>  <br>**开启 word level timestamp ，默认是不开的**  <br>  <br>> 翻译  <br>  <br>**使用 [https://heimoshuiyu.github.io/whisper-web/](https://heimoshuiyu.github.io/whisper-web/) 转录同时利用 GPT 翻译字幕** |
