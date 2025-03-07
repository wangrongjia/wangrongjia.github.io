---
link: https://www.v2ex.com/t/1095862
site: V2EX
date: 2024-12-08T11:45
excerpt: 程序员 - @BaymaxK - 像他们这种公益站点是怎么弄的呢，我看他好像用的是 token ，并非 API
  。https://chatgptplus.cn/ https://aicnn.cn/oaifree htt
twitter: https://twitter.com/@V2EX
slurped: 2025-02-08T14:16
title: 比较好奇这 gpt 的镜像站是怎么搭建的？ - V2EX
---

  [BaymaxK](/member/BaymaxK) · 62 天前 · 3494 次点击

这是一个创建于 62 天前的主题，其中的信息可能已经有所发展或是发生改变。

像他们这种公益站点是怎么弄的呢，我看他好像用的是 token ，并非 API 。

[https://chatgptplus.cn/](https://chatgptplus.cn/) [https://aicnn.cn/oaifree](https://aicnn.cn/oaifree) [https://chatgpt.dairoot.cn](https://chatgpt.dairoot.cn) [https://free.share-ai.top/](https://free.share-ai.top/)

![image-20241208114427989](https://resource.kaisir.cn/uploads/MarkDownImg/20241208/KDgi7a.png) [https://chatgptplus.cn/](https://chatgptplus.cn/) 111 、 [https://aicnn.cn/oaifree](https://aicnn.cn/oaifree) 74 、 [https://chatgpt.dairoot.cn](https://chatgpt.dairoot.cn) 74 、 [https://free.share-ai.top/](https://free.share-ai.top/) 83 、

第 1 条附言  ·  61 天前

感谢大家的回复，我找到了一个项目：

- [ChatGPT-Mirror](https://github.com/dairoot/ChatGPT-Mirror)

已经部署成功，用上了。


10 条回复  **•**  2024-12-09 08:59:40 +08:00

|   |   |   |
|---|---|---|
|![GrayXu](https://cdn.v2ex.com/gravatar/aacc01606f4653e3ba1a14bf35ea3e8a?s=48&d=retro)||1<br><br>**[GrayXu](/member/GrayXu)**  <br><br>   62 天前<br><br>就是和 chat2api 一样的原理|

|   |   |   |
|---|---|---|
|![xiaokuonai](https://cdn.v2ex.com/avatar/5dbd/3418/438030_normal.png?m=1729769561)||2<br><br>**[xiaokuonai](/member/xiaokuonai)**  <br><br>   62 天前<br><br>同问|

|   |   |   |
|---|---|---|
|![mmdsun](https://cdn.v2ex.com/avatar/c476/56f5/269732_normal.png?m=1672555848)||3<br><br>**[mmdsun](/member/mmdsun)**  <br><br>   62 天前 via iPhone<br><br>反代别人的网站，把自己的脚本加进去。  <br>别说写 token 了，改样式都可以。  <br>  <br>你也可以把网站下载到本地来搞，好像之前 chatgpt 共享站的 pandora 是这么搞的。|

|   |   |   |
|---|---|---|
|![ply](https://cdn.v2ex.com/gravatar/e9dfbe81953b8c8235cff8f8574efc76?s=48&d=retro)||4<br><br>**[ply](/member/ply)**  <br><br>   62 天前<br><br>有没有那种私下小范围分享的方案，只求不封号不求其他功能，想共用 pro 了|

|   |   |   |
|---|---|---|
|![zhangjiashu2023](https://cdn.v2ex.com/avatar/f3dd/765e/640627_normal.png?m=1737801579)||5<br><br>**[zhangjiashu2023](/member/zhangjiashu2023)**  <br><br>   62 天前<br><br>@[ply](/member/ply) 1. 开源的没有。你要是有需求可以找我|

|   |   |   |
|---|---|---|
|![baidishenjian](https://cdn.v2ex.com/gravatar/79f2a83f81a4f7ee6b2a7054f0b70008?s=48&d=retro)||6<br><br>**[baidishenjian](/member/baidishenjian)**  <br><br>   61 天前<br><br>感觉比如用户->我的服务器->gpt  <br>我的服务器上加个 nginx 做代理，然后做一些控制比如改写 token 之类的，不知道可不可行。  <br>我想到的是类似这样的方法|

|   |   |   |
|---|---|---|
|![burtnonald2](https://cdn.v2ex.com/gravatar/257c90fe299073b2879cf6f4508481b7?s=48&d=retro)||7<br><br>**[burtnonald2](/member/burtnonald2)**  <br><br>   61 天前<br><br>我这儿多的是  <br>全是自己部署的  <br>[[https://home.opaoai.com/](https://home.opaoai.com/)]( [https://home.opaoai.com/](https://home.opaoai.com/))  <br>![img]( [https://img.opaoai.com/i/2024/12/08/6755614c8c040.webp](https://img.opaoai.com/i/2024/12/08/6755614c8c040.webp))|

|   |   |   |
|---|---|---|
|![liyafe1997](https://cdn.v2ex.com/avatar/524e/7d08/32249_normal.png?m=1711747440)||8<br><br>**[liyafe1997](/member/liyafe1997)**  <br><br>   61 天前<br><br>@[ply](/member/ply) 我之前给我的朋友们用这种方法分享过：虚拟机开个 Windows server ，安装终端服务器然后破解，建立几个账户，然后在上面登好我的 ChatGPT 帐号。组策略做一些限制，比如只能开 edge 浏览器，然后 edge 浏览器只能开 [chatgpt.com](http://chatgpt.com) 。然后用那个 RemoteApp Tool 生成一个打开 Edge 浏览器 & ChatGPT 的.rdp ，给他们一键使用。|

|   |   |   |
|---|---|---|
|![liyafe1997](https://cdn.v2ex.com/avatar/524e/7d08/32249_normal.png?m=1711747440)||9<br><br>**[liyafe1997](/member/liyafe1997)**  <br><br>   61 天前<br><br>@[ply](/member/ply) 噢对了还塞了个油猴脚本，屏蔽了边栏历史记录，并且强制?temporary-chat=true|

|                                                                                        |     |                                                                                             |
| -------------------------------------------------------------------------------------- | --- | ------------------------------------------------------------------------------------------- |
| ![cslive](https://cdn.v2ex.com/gravatar/1b016fe0fb76c0cee96842649cbff8d8?s=48&d=retro) |     | 10<br><br>**[cslive](/member/cslive)**  <br><br>   61 天前<br><br>there is no way  <br>封的差不多了 |
|                                                                                        |     |                                                                                             |
