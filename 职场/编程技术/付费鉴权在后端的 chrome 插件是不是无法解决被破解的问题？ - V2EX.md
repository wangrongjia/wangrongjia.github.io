---
link: https://www.v2ex.com/t/1103143
site: V2EX
date: 2025-01-07T11:44
excerpt: Chrome - @Cellinlab -
  之前看中一个付费插件，准备付费，然后联系不上客服付款，刚刚不小心发现，居然没加密，被我看到了源码！Chrome
  插件源码查看，具体步骤：https://x.com/cellinlab/st
twitter: https://twitter.com/@V2EX
slurped: 2025-02-06T09:17
title: 付费鉴权在后端的 chrome 插件是不是无法解决被破解的问题？ - V2EX
---


[Cellinlab](https://www.v2ex.com/member/Cellinlab) · 29 天前 · 965 次点击

之前看中一个付费插件，准备付费，然后联系不上客服付款，刚刚不小心发现，居然没加密，被我看到了源码！

Chrome 插件源码查看，具体步骤： [https://x.com/cellinlab/status/1876315256307556554](https://x.com/cellinlab/status/1876315256307556554)

![](https://pbs.twimg.com/media/GgoCd71boAU23hB?format=jpg&name=large) ![](https://pbs.twimg.com/media/GgoCkwTboAIfQrd?format=jpg&name=large) （ PS：做付费插件的弟兄们，一定要混淆和加密源码！

那如果要做这种付费插件如何最大程度保护被破解呢？

[](https://www.v2ex.com/tag/%E7%A0%B4%E8%A7%A3)

[破解](https://www.v2ex.com/tag/%E7%A0%B4%E8%A7%A3)[

付费](https://www.v2ex.com/tag/%E4%BB%98%E8%B4%B9)[

加密](https://www.v2ex.com/tag/%E5%8A%A0%E5%AF%86)

3 条回复  **•**  2025-01-07 14:25:52 +08:00

|   |   |   |
|---|---|---|
|![SayHelloHi](https://cdn.v2ex.com/avatar/d961/3cd9/563553_normal.png?m=1728892808)||1<br><br>**[SayHelloHi](https://www.v2ex.com/member/SayHelloHi)**      29 天前   ![❤️](https://www.v2ex.com/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>如果代码混淆<br><br>Chrome Web Store 审核团队会拒绝开发者提交的插件<br><br>并提出修改意见让开发者修改<br><br>直到符合平台政策才审核通过|

|   |   |   |
|---|---|---|
|![musi](https://cdn.v2ex.com/avatar/3c30/8c17/303588_normal.png?m=1691313864)||2<br><br>**[musi](https://www.v2ex.com/member/musi)**      29 天前<br><br>除非主要功能在云端，否则就没有破解不了的  <br>IDEA photoshop 他们被破解是因为代码没混淆吗？|

|   |   |   |
|---|---|---|
|![weixind](https://cdn.v2ex.com/avatar/83d2/802a/354938_normal.png?m=1733128054)||3<br><br>**[weixind](https://www.v2ex.com/member/weixind)**      29 天前<br><br>前端混淆和加密就是图一乐。|