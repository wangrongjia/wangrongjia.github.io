---
link: https://www.v2ex.com/t/1112098
site: V2EX
date: 2025-02-17T18:17
excerpt: 分享创造 - @damao2250 - 苦于无法顺畅地查看本站地历史数据（只能通过搜索引擎搜索关键字），于是利用 GitHub Actions
  定时拉去本站历史数据的每日评论 top 10 的帖子及帖子感谢数 top 10 的评论，目前每十
twitter: https://twitter.com/@V2EX
slurped: 2025-02-18T09:33
title: 利用 GitHub Actions 拉取 V2EX 的历史数据到 Issues - V2EX
---
                                                

[

](/ "way to explore")

[首页](/) [注册](/signup) [登录](/signin)

**V2EX = way to explore**

V2EX 是一个关于分享和探索的地方

[现在注册](/signup)

已注册用户请  [登录](/signin)

爱意满满的作品展示区。 

[广告](/advertise)

[![damao2250](https://cdn.v2ex.com/avatar/8b50/f50e/308765_xlarge.png?m=1739785731)](/member/damao2250)

[V2EX](/)  ›  [分享创造](/go/create)

# 利用 GitHub Actions 拉取 V2EX 的历史数据到 Issues

[

](javascript:) [

](javascript:)

  [damao2250](/member/damao2250) ·

[damao2250](https://github.com/damao2250) · 15 小时 15 分钟前 · 428 次点击

苦于无法顺畅地查看本站地历史数据（只能通过搜索引擎搜索关键字），于是利用 GitHub Actions 定时拉去本站历史数据的每日评论 top 10 的帖子及帖子感谢数 top 10 的评论，目前每十五分钟左右从 2010-04-25 按照日期顺序拉取一天的热门主题

为什么要查看历史主题数据？ 因为一直以来本站帖子的质量都很高，有些帖子即使已经过去很久了，但是大部分主题及评论的观点依然给我很大的影响

关于 GitHub Actions 频率 我设置了 8 分钟执行一次，但是执行的时间好像不太对，之前没研究过，目前观察大概十五分钟左右执行一次

GitHub 仓库地址： [https://github.com/Damao2250/v2ex_mofish_old_data](https://github.com/Damao2250/v2ex_mofish_old_data)

借鉴：

[https://github.com/jiacai2050/mofish](https://github.com/jiacai2050/mofish)

[https://github.com/coolpace/V2EX_Polish](https://github.com/coolpace/V2EX_Polish)

效果如下： ![](https://s3.bmp.ovh/imgs/2025/02/17/44bdbf01d257e151.png)

![](https://s3.bmp.ovh/imgs/2025/02/17/8e35673ad22d2c1e.png)

![](https://s3.bmp.ovh/imgs/2025/02/17/547572c908004838.png)

如有不对的地方望大家指出，感谢

[

GitHub Actions](/tag/GitHub Actions)[

V2EX](/tag/V2EX)[

历史数据](/tag/历史数据)

4 条回复  **•**  2025-02-17 19:01:04 +08:00

|   |   |   |
|---|---|---|
|![0x400](https://cdn.v2ex.com/gravatar/54e7b3f1505aff532d279426e7eb23e4?s=48&d=retro)||1<br><br>**[0x400](/member/0x400)**  <br><br>   15 小时 6 分钟前 via iPhone<br><br>issue 的搜索好用吗|

|   |   |   |
|---|---|---|
|![damao2250](https://cdn.v2ex.com/avatar/8b50/f50e/308765_normal.png?m=1739785731)||2<br><br>**[damao2250](/member/damao2250)**  <br><br>OP<br><br>   15 小时 3 分钟前 via iPhone<br><br>@[0x400](/member/0x400) 暂时没使用 issue 搜索功能的需求，只是想按天查看当天热门的主题|

|   |   |   |
|---|---|---|
|![Chaidu](https://cdn.v2ex.com/gravatar/e786c3126a2181205f32e51a093d3d0c?s=48&d=retro)||3<br><br>**[Chaidu](/member/Chaidu)**  <br><br>   14 小时 52 分钟前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>我之前也搞过，然后我 GitHub 账号就被封了|

|   |   |   |
|---|---|---|
|![damao2250](https://cdn.v2ex.com/avatar/8b50/f50e/308765_normal.png?m=1739785731)||4<br><br>**[damao2250](/member/damao2250)**  <br><br>OP<br><br>   14 小时 32 分钟前 via iPhone<br><br>@[Chaidu](/member/Chaidu) 啊🤣那我还是赶紧停了|

[

](https://www.digitalocean.com/?refcode=1b51f1a7651d)

**[关于](/about)   ·   [帮助文档](/help)   ·   [博客](https://blog.v2ex.com/)   ·   [API](/help/api)   ·   [FAQ](/faq)   ·   [实用小工具](/tools)   ·   5685 人在线**   最高记录 6679   ·     [![](/static/img/language.png?v=6a5cfa731dc71a3769f6daace6784739)   Select Language](/select/language)

创意工作者们的社区

World is powered by solitude

VERSION: 3.9.8.5 · 20ms · [UTC 01:33](/worldclock#utc) · [PVG 09:33](/worldclock#pvg) · [LAX 17:33](/worldclock#lax) · [JFK 20:33](/worldclock#jfk)  
Developed with [CodeLauncher](https://cl.v2ex.pro/)  
♥ Do have faith in what you're doing.