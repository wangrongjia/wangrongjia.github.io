---
link: https://www.v2ex.com/t/1098421
site: V2EX
date: 2024-12-18T11:09
excerpt: 奇思妙想 - @hekmon - 大家好！ MCP 出来之后，打通了 AI 与设备之间的联系。最近在玩 Home Assistant
  的时候就在想：要是能让 AI 来帮我控制家里的智能设备该多好。于是就有了这个项目 - Hom
twitter: https://twitter.com/@V2EX
slurped: 2025-02-08T10:48
title: AI➕MCP➕Homeassistant，感觉有点搞头？！ - V2EX
---
  
  [hekmon](/member/hekmon) · 51 天前 via iPhone · 1819 次点击

这是一个创建于 51 天前的主题，其中的信息可能已经有所发展或是发生改变。

大家好！ MCP 出来之后，打通了 AI 与设备之间的联系。

最近在玩 Home Assistant 的时候就在想：要是能让 AI 来帮我控制家里的智能设备该多好。于是就有了这个项目 - Home Assistant MCP Server 。

项目地址： [https://github.com/hekmon8/Homeassistant-server-mcp](https://github.com/hekmon8/Homeassistant-server-mcp)

## 这个项目是干啥的？

简单来说，这是一个让 AI 能够理解和控制你的智能家居设备的工具。比如：

想知道家里某个设备开着还是关着？ 要远程控制设备？ 需要触发自动化场景？ 查看所有可用设备？ 都可以通过 AI 来完成！不需要再记那么多命令和操作步骤了。

## 开发过程中和 AI 搭伙打工是什么体验？

说实话，和 Claude AI 一起开发简直太爽了！

举个例子，在写设备状态查询功能时，我是这么和 Claude 聊的： "我想获取设备状态，但要考虑各种异常情况，你觉得怎么写比较好？"

然后它就给出了完整的代码建议，包括错误处理、日志记录等细节。真的是事半功倍！

## 还能玩出什么花样？

我觉得这个项目还有很多有趣的玩法：

### 智能助手进阶版

1. AI 帮你分析用电量，主动提醒你哪些设备可以关掉省电
2. 学习你的作息习惯，自动调整空调温度、灯光亮度
3. 发现异常情况（比如忘关灯、设备离线）自动提醒

### 懒人福音

1. 直接用自然语言控制设备："帮我把客厅的灯调暗一点"
2. AI 根据你的日常习惯自动创建自动化场景
3. 多个设备智能联动，比如回家自动开灯开空调

### 安全管家

1. 检测到异常活动自动报警
2. 定期生成设备健康报告
3. 智能防盗模式

### 想试试看？

具体配置方法看 README

## 写在最后

如果你也在用 Home Assistant ，欢迎来试试这个项目！有什么想法或建议都可以在评论区聊聊。

项目正在持续优化中，欢迎 star 、fork ，也特别欢迎提 PR ！


10 条回复  **•**  2024-12-21 10:08:40 +08:00

|   |   |   |
|---|---|---|
|![SantinoSong](https://cdn.v2ex.com/gravatar/fb3070fbfc1930ddd4c46cc0d0a28a54?s=48&d=retro)||1<br><br>**[SantinoSong](/member/SantinoSong)**  <br><br>   51 天前<br><br>看出来你的 readme 是 ai 写的, 用的还是 yourusername 占位符🧐|

|   |   |   |
|---|---|---|
|![hekmon](https://cdn.v2ex.com/gravatar/4c90022e62784a51031da922421abb70?s=48&d=retro)||2<br><br>**[hekmon](/member/hekmon)**  <br><br>OP<br><br>   51 天前 via iPhone<br><br>@[SantinoSong](/member/SantinoSong) 对 ai 写的大概，我再手动改了下😂|

|   |   |   |
|---|---|---|
|![tsja](https://cdn.v2ex.com/avatar/b58f/4505/570178_normal.png?m=1730252403)||3<br><br>**[tsja](/member/tsja)**  <br><br>   51 天前<br><br>有意思, 已 start|

|   |   |   |
|---|---|---|
|![hekmon](https://cdn.v2ex.com/gravatar/4c90022e62784a51031da922421abb70?s=48&d=retro)||4<br><br>**[hekmon](/member/hekmon)**  <br><br>OP<br><br>   51 天前 via iPhone<br><br>@[tsja](/member/tsja) 捕获 HA 选手|

|   |   |   |
|---|---|---|
|![NGGTI](https://cdn.v2ex.com/avatar/0ed5/cb9a/434155_normal.png?m=1709800738)||5<br><br>**[NGGTI](/member/NGGTI)**  <br><br>   51 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>感觉小爱同学团队已经在做了。  <br>我拓展一下思路，把人体的各种数据都接入 Ai ，让 AI 来分析健康，生活作息，给出各种建议。|

|   |   |   |
|---|---|---|
|![gehui302](https://cdn.v2ex.com/gravatar/b48800da2c1eb52929bdbc299f7865bc?s=48&d=retro)||6<br><br>**[gehui302](/member/gehui302)**  <br><br>   51 天前<br><br>涉及家电安全。。。|

|   |   |   |
|---|---|---|
|![hekmon](https://cdn.v2ex.com/gravatar/4c90022e62784a51031da922421abb70?s=48&d=retro)||7<br><br>**[hekmon](/member/hekmon)**  <br><br>OP<br><br>   51 天前 via iPhone<br><br>@[NGGTI](/member/NGGTI) 嗯 澎拜 OS 有类似的策略，不过毕竟数据是别人的😂|

|   |   |   |
|---|---|---|
|![hekmon](https://cdn.v2ex.com/gravatar/4c90022e62784a51031da922421abb70?s=48&d=retro)||8<br><br>**[hekmon](/member/hekmon)**  <br><br>OP<br><br>   51 天前 via iPhone<br><br>@[gehui302](/member/gehui302) 考虑一下本地部署和必要的 webhook 通知|

|   |   |   |
|---|---|---|
|![hongjic93](https://cdn.v2ex.com/gravatar/81497d2c52419d0f948e1bfe82991bdb?s=48&d=retro)||9<br><br>**[hongjic93](/member/hongjic93)**  <br><br>   49 天前<br><br>mcp 和以前的 function calling 有什么本质上的不同吗？怎么理解呢？|

|   |   |   |
|---|---|---|
|![musi](https://cdn.v2ex.com/avatar/3c30/8c17/303588_normal.png?m=1691313864)||10<br><br>**[musi](/member/musi)**  <br><br>   49 天前 via iPhone<br><br>@[hongjic93](/member/hongjic93) #9 底层还是 fc 和提示词，基于 fc 扩展了一套数据交互协议，便于社区生态发展|
