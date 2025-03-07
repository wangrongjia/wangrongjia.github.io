---
link: https://www.v2ex.com/t/1106515
site: V2EX
date: 2025-01-20T16:02
excerpt: 程序员 - @fatDex - 需求大致如下：1. 网站用于上传一个大小至少为 1GB 的视频文件；2.
  上传成功后，需要能够在网站上逐帧回放这个视频，必须能精确到每一帧；3. 定位到某一帧后，可以在这一帧的画面里面绘制
twitter: https://twitter.com/@V2EX
slurped: 2025-02-13T18:07
title: 请教一个视频网站的设计方案 - V2EX
---
  
  [fatDex](/member/fatDex) · 24 天前 · 1113 次点击

需求大致如下：

1. 网站用于上传一个大小至少为 1GB 的视频文件；
2. 上传成功后，需要能够在网站上逐帧回放这个视频，必须能精确到每一帧；
3. 定位到某一帧后，可以在这一帧的画面里面绘制直线或者多边形用于标注；
4. 标注完成后，再把视频和标注的数据统一发给另外一个服务器的 API 用于进一步解析；
5. 解析后的结果返回到网站，提供在线查看与下载；
6. 用户量暂时不大，同一时间最多不到 10 个人访问。

这里面最大的难点可能就在前三项了，自己没有做过视频相关的产品，感觉有很多坑的样子。也问过 gpt ，但还是有些迷茫。想请教下各位，有没有什么比较推荐的解决方案呢，最好是成本低一些的，十分感谢！


21 条回复  **•**  2025-01-22 15:13:49 +08:00

|   |   |   |
|---|---|---|
|![humbass](https://cdn.v2ex.com/gravatar/167e7101a0d1f1af92baf53ad32ee4f4?s=48&d=retro)||1<br><br>**[humbass](/member/humbass)**  <br><br>   24 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>没啥难度，但是工作量还是有的  <br>  <br>帧操作肯定有一个定制版的滑动条，用来定位帧啥的；  <br>其次是多边形标注；  <br>至于说第 1 条，做个分片的断点续传|

|   |   |   |
|---|---|---|
|![linshuizhaoying](https://cdn.v2ex.com/gravatar/fc3d99ea1d60a416202e932d928b1b1f?s=48&d=retro)||2<br><br>**[linshuizhaoying](/member/linshuizhaoying)**  <br><br>   24 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>标注简单 canvas 定位 画图|

|   |   |   |
|---|---|---|
|![gaobh](https://cdn.v2ex.com/avatar/4a85/8bdd/205723_normal.png?m=1738847557)||3<br><br>**[gaobh](/member/gaobh)**  <br><br>   24 天前 via iPhone   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>你应该找视频解析编辑框架，比如这个 [https://juejin.cn/post/7380702373570494490](https://juejin.cn/post/7380702373570494490)|

|   |   |   |
|---|---|---|
|![dejavuwind](https://cdn.v2ex.com/avatar/5fd1/f2bb/189194_normal.png?m=1722561640)||4<br><br>**[dejavuwind](/member/dejavuwind)**  <br><br>   24 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>第一条要考虑实际使用者的网络环境吧  <br>内网速度够快的话应该问题不大 公网的话是不是要考虑下断点续传？  <br>2 服务器拿到视频之后做切分转格式按需给前端  <br>  <br>标记数据看起来跟单个帧是绑定的 这块触及到知识盲区了 等下大佬们的回答|

|   |   |   |
|---|---|---|
|![fatDex](https://cdn.v2ex.com/gravatar/b20aaed786bd13bc162149cb83eb707f?s=48&d=retro)||5<br><br>**[fatDex](/member/fatDex)**  <br><br>OP<br><br>   24 天前<br><br>@[dejavuwind](/member/dejavuwind) 是公网环境，所以目前看下来肯定得做断点续传了。标记的话我觉得只需要记录下帧号以及在这个帧下的几个标记的位置就行了，这块并不需要对原始的视频数据做任何修改，所以应该相对容易实现。视频逐帧解析这块工作我目前打算放在前端，类似于用 ffmpeg.js 这种东西，但不知道前端做起来效率怎么样。|

|   |   |   |
|---|---|---|
|![fatDex](https://cdn.v2ex.com/gravatar/b20aaed786bd13bc162149cb83eb707f?s=48&d=retro)||6<br><br>**[fatDex](/member/fatDex)**  <br><br>OP<br><br>   24 天前<br><br>@[gaobh](/member/gaobh) 啊，这个看起来挺有启发的，我研究一下，感谢～|

|   |   |   |
|---|---|---|
|![fatDex](https://cdn.v2ex.com/gravatar/b20aaed786bd13bc162149cb83eb707f?s=48&d=retro)||7<br><br>**[fatDex](/member/fatDex)**  <br><br>OP<br><br>   24 天前<br><br>@[linshuizhaoying](/member/linshuizhaoying) 对，我目前也是这么想。|

|   |   |   |
|---|---|---|
|![fatDex](https://cdn.v2ex.com/gravatar/b20aaed786bd13bc162149cb83eb707f?s=48&d=retro)||8<br><br>**[fatDex](/member/fatDex)**  <br><br>OP<br><br>   24 天前<br><br>@[humbass](/member/humbass) 没错，得有一个专门的进度条。|

|   |   |   |
|---|---|---|
|![iamzuoxinyu](https://cdn.v2ex.com/gravatar/92bc6e749bdb9f70f7be8ae071e08870?s=48&d=retro)||9<br><br>**[iamzuoxinyu](/member/iamzuoxinyu)**  <br><br>   24 天前<br><br>前端用 ffmpeg+wasm 挺合适的。wasm 虽然性能有点捉急，但你的场景似乎不用考虑 25+的帧率；其它的就是做好解码缓存就行，有 B 帧处理起来稍微麻烦一些。|

|   |   |   |
|---|---|---|
|![iamzuoxinyu](https://cdn.v2ex.com/gravatar/92bc6e749bdb9f70f7be8ae071e08870?s=48&d=retro)||10<br><br>**[iamzuoxinyu](/member/iamzuoxinyu)**  <br><br>   24 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>另外 webcodecs 看主流版本浏览器也支持了，可以优先考虑这个。|

|   |   |   |
|---|---|---|
|![fatDex](https://cdn.v2ex.com/gravatar/b20aaed786bd13bc162149cb83eb707f?s=48&d=retro)||11<br><br>**[fatDex](/member/fatDex)**  <br><br>OP<br><br>   23 天前<br><br>@[iamzuoxinyu](/member/iamzuoxinyu) 好的，我研究下，感谢～|

|   |   |   |
|---|---|---|
|![fatDex](https://cdn.v2ex.com/gravatar/b20aaed786bd13bc162149cb83eb707f?s=48&d=retro)||12<br><br>**[fatDex](/member/fatDex)**  <br><br>OP<br><br>   23 天前<br><br>@[iamzuoxinyu](/member/iamzuoxinyu) 感觉思路一下子打开了|

|   |   |   |
|---|---|---|
|![wnpllrzodiac](https://cdn.v2ex.com/gravatar/84e41a23f65477d2c3c398dc13c8e053?s=48&d=retro)||13<br><br>**[wnpllrzodiac](/member/wnpllrzodiac)**  <br><br>   23 天前 via Android<br><br>有个本地编辑视频的开源项目。electron 做的，逐桢编辑|

|   |   |   |
|---|---|---|
|![netnr](https://cdn.v2ex.com/avatar/9bfd/9fda/426497_normal.png?m=1737784936)||14<br><br>**[netnr](/member/netnr)**  <br><br>   23 天前 via Android   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>用 Uppy.js TUS 协议上传  <br>  <br>前端处理视频要考虑超大视频文件是否支持，  <br>稳妥还是后台处理，拿到总帧数，然后弄个类似分页的组件，动态加载对应帧画面|

|   |   |   |
|---|---|---|
|![fatDex](https://cdn.v2ex.com/gravatar/b20aaed786bd13bc162149cb83eb707f?s=48&d=retro)||15<br><br>**[fatDex](/member/fatDex)**  <br><br>OP<br><br>   23 天前<br><br>@[netnr](/member/netnr) 收到～ 关于前端处理的问题，昨天收到大家的建议之后我发现也可以考虑用 webcodecs 这样子的前端方案去先在本地处理好视频，再做后续调用 API 的工作，这样子的好处是可以少上传一次视频，并且也不需要专门用来存视频的服务器了，不过我自己试了下一些基于 webcodecs 的几个开源项目，包括 B 站的 WebAV 以及 3 楼兄弟推荐的 fly-cut ，都遇到了一个问题，就是如果视频有几百兆的话，处理起来都很慢，甚至看起来页面跟完全没反应一样，要等好久，我现在还不确定究竟是什么问题，但这可能就是你提到的超大视频文件支持的问题？考虑到我这边的需求，视频普通都是大于 1 GB 甚至几十 GB 的，或许真的不用考虑前端处理了。|

|   |   |   |
|---|---|---|
|![skallz](https://cdn.v2ex.com/gravatar/e2d66edb8b18a0aa97b9f7b21d6e1258?s=48&d=retro)||16<br><br>**[skallz](/member/skallz)**  <br><br>   23 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>前端处理的话，web 的话大视频基本不太可能，内存捉急，electron 可以考虑下  <br>@[fatDex](/member/fatDex)|

|   |   |   |
|---|---|---|
|![zzzyyysss](https://cdn.v2ex.com/avatar/317c/0739/575441_normal.png?m=1737598947)||17<br><br>**[zzzyyysss](/member/zzzyyysss)**  <br><br>   23 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>@[fatDex](/member/fatDex) 视频这么大的话 只能分片传到后端 然后再处理，不过前端有个读取文件的 api `File System Access API` 是不是可以拿到目录权限 然后每次读取视频文件的一部分来处理。|

|   |   |   |
|---|---|---|
|![zzzyyysss](https://cdn.v2ex.com/avatar/317c/0739/575441_normal.png?m=1737598947)||18<br><br>**[zzzyyysss](/member/zzzyyysss)**  <br><br>   23 天前<br><br>不过这种需求感觉打包个 electron 更适合，直接处理完数据发送给指定的 API 。|

|   |   |   |
|---|---|---|
|![fatDex](https://cdn.v2ex.com/gravatar/b20aaed786bd13bc162149cb83eb707f?s=48&d=retro)||19<br><br>**[fatDex](/member/fatDex)**  <br><br>OP<br><br>   23 天前<br><br>@[wnpllrzodiac](/member/wnpllrzodiac) 请问下知道这个项目叫什么名字么？|

|   |   |   |
|---|---|---|
|![fatDex](https://cdn.v2ex.com/gravatar/b20aaed786bd13bc162149cb83eb707f?s=48&d=retro)||20<br><br>**[fatDex](/member/fatDex)**  <br><br>OP<br><br>   23 天前<br><br>@[zzzyyysss](/member/zzzyyysss) 嗯，看很多人都提到 electron ，我研究下看看。|

|   |   |   |
|---|---|---|
|![wnpllrzodiac](https://cdn.v2ex.com/gravatar/84e41a23f65477d2c3c398dc13c8e053?s=48&d=retro)||21<br><br>**[wnpllrzodiac](/member/wnpllrzodiac)**  <br><br>   22 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>@[fatDex](/member/fatDex) [https://github.com/mifi/lossless-cut](https://github.com/mifi/lossless-cut)|
