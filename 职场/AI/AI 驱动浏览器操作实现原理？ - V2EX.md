---
link: https://www.v2ex.com/t/1099418
site: V2EX
date: 2024-12-22T17:44
excerpt: 程序员 - @molvqingtai - 最近看到 google 的一个 AI 插件，可以让 AI 操作浏览器收集信息，对 AI prompt
  了解甚少，对它的实现原理很感兴趣插件视频： https://www.youtube.com
twitter: https://twitter.com/@V2EX
slurped: 2025-02-08T16:54
title: AI 驱动浏览器操作实现原理？ - V2EX
---

**V2EX = way to explore**

V2EX 是一个关于分享和探索的地方

• 请不要在回答技术问题时复制粘贴 AI 生成的内容

这是一个创建于 47 天前的主题，其中的信息可能已经有所发展或是发生改变。

[](https://www.v2ex.com/tag/AI)

[AI](https://www.v2ex.com/tag/AI)[

浏览器](https://www.v2ex.com/tag/%E6%B5%8F%E8%A7%88%E5%99%A8)[

操作](https://www.v2ex.com/tag/%E6%93%8D%E4%BD%9C)

7 条回复  **•**  2024-12-23 08:59:27 +08:00

|   |   |   |
|---|---|---|
|![herich](https://cdn.v2ex.com/avatar/9c4d/531e/333158_normal.png?m=1579598887)||2<br><br>**[herich](https://www.v2ex.com/member/herich)**      47 天前<br><br>比较关注的是 AI 驱动的浏览器能否高正确率的通过各种网站的 anti bot 机制|

|   |   |   |
|---|---|---|
|![kulove](https://cdn.v2ex.com/avatar/0fe8/6033/154072_normal.png?m=1678763404)||4<br><br>**[kulove](https://www.v2ex.com/member/kulove)**      47 天前<br><br>之前做过类似的 Demo ，读取 HTML 网页+截图来做的（单一的不准确），因为插件不能注入代码，所以封装了诸如点击、滚动、输入的各种事件，效果么还行，就是成本爆炸，所以没有上线。|

|   |   |   |
|---|---|---|
|![lizhenda](https://cdn.v2ex.com/avatar/45df/c74b/128487_normal.png?m=1444477674)||5<br><br>**[lizhenda](https://www.v2ex.com/member/lizhenda)**      47 天前<br><br>一般是基于视觉，感觉成本很高啊。并且获得的数据准确性存疑。|

|   |   |   |
|---|---|---|
|![YuanJiwei](https://cdn.v2ex.com/avatar/d151/b996/441391_normal.png?m=1737038349)||6<br><br>**[YuanJiwei](https://www.v2ex.com/member/YuanJiwei)**      47 天前<br><br>哈哈，巧了，我现在正在探索利用 pupputeer 实现 Google Mariner 的各种方案|

|   |   |   |
|---|---|---|
|![macaodoll](https://cdn.v2ex.com/gravatar/00305826ca0b60144a020c9775b6d1f6?s=48&d=retro)||7<br><br>**[macaodoll](https://www.v2ex.com/member/macaodoll)**      47 天前 via Android<br><br>程序驱动浏览器有成熟的方案，只是难的是让模型读懂页面|