---
link: https://www.v2ex.com/t/1096283
site: V2EX
date: 2024-12-10T08:49
excerpt: "分享创造 - @zapll - # ChatMCP: 开源的 MCP 协议客户端 🚀大家好呀! 👋 我是 [ChatMCP](
  https://github.com/daodao97/chatmcp) 的作者。最近一直在关注"
twitter: https://twitter.com/@V2EX
slurped: 2025-02-08T15:25
title: "ChatMCP: 可能是第一个支持 MCP 协议的开源 AI 客户端 - V2EX"
---
  [zapll](/member/zapll) · 60 天前 · 2667 次点击

这是一个创建于 60 天前的主题，其中的信息可能已经有所发展或是发生改变。

# ChatMCP: 开源的 MCP 协议客户端 🚀

大家好呀! 👋 我是 [ChatMCP](https://github.com/daodao97/chatmcp) 的作者。最近一直在关注 Anthropic 的 MCP 协议, 这个协议真的太棒了, 让我忍不住想要动手实现一个开源版本。经过一段时间的开发, 很高兴跟大家分享我的作品 - [ChatMCP](https://github.com/daodao97/chatmcp), 这可是目前第一个开源的 MCP 客户端实现哦! 🎉

GithHub: [https://github.com/daodao97/chatmcp](https://github.com/daodao97/chatmcp) 求 Star⭐️

- Chat 中 访问本地 sqlite 数据库的样例

![ChatMCP Preview](https://raw.githubusercontent.com/daodao97/chatmcp/refs/heads/main/assets/preview/preview.png)

- 更方便的管理 MCP Server (建设中)

![ChatMCP Setting Preview](https://raw.githubusercontent.com/daodao97/chatmcp/refs/heads/main/assets/preview/preview-setting.png)

## MCP 能解决什么问题? 🤔

有了 MCP,AI 简直就像获得了超能力一样,可以轻松实现:

- 📊 查询分析本地数据库
- 🐙 管理 GitHub 仓库(创建 Issue 、PR 什么的都不在话下)
- 💬 总结微信聊天记录
- 📂 操作本地文件,得心应手
- 🥡 想吃外卖?一键搞定!(支持美团、饿了么)
- 🛒 变身智能购物助手(自动比价、帮你省钱)
- 🏠 智能家居随心控(灯光、空调、窗帘统统搞定)
- 💰 管理个人财务(分析账单、规划消费)
- 💪 健康数据分析(运动、睡眠质量都给你整明白)

有了 MCP 统统都能接入大模型, 是不是很有想象空间, 哈哈哈

以前要实现这些功能,每个数据源都需要单独开发接入。MCP 提供了统一的标准,大大降低了开发成本。

## 为什么需要开源客户端?

目前 MCP 只能在 Claude 官方客户端使用, 这带来一些局限:

1. Claude 账号经常被封, 泪目, 我的又被封了
2. 不能使用其他的 LLM 模型

ChatMCP 作为开源方案,提供了更多选择:

- 不依赖特定服务商
- 支持多种 LLM 模型
- 完全本地化, 保证隐私
- 支持自定义开发

## ChatMCP 主要功能

- 多模型支持(OpenAI 、Claude 、OLLama 等)
- MCP 服务器管理
- 本地聊天记录
- RAG 知识库集成
- 更漂亮的用户界面

## 快速开始 🚗

[点我下载](https://github.com/daodao97/chatmcp/releases)

1. ⬇️ 下载安装(目前只支持 MacOS 哦),
2. 🔑 配置你的 API Key
3. 🔧 装好需要的 MCP 服务
4. ✨ 开始体验神奇功能!

## 开发计划 🗓️

目前计划:

- 🪟 支持 Windows/Linux
- 🔌 接入更多 AI 模型
- 🌱 建设 MCP 服务生态, MCP Server 的自动安装

## 写在最后 💝

开发 ChatMCP 的过程中,我真的学到了很多。希望这个项目能帮助到对 MCP 感兴趣的小伙伴们。欢迎大家来 GitHub 上交流,一起让 ChatMCP 变得更好!

项目地址: [https://github.com/daodao97/chatmcp](https://github.com/daodao97/chatmcp) ⭐️

如果觉得有帮助的话,求个 star 呀~ 😘

第 1 条附言  ·  60 天前

macos 安装闪退的问题已经修复, 下载 fixed 版本 [https://github.com/daodao97/chatmcp/releases/tag/v0.0.1-alpha](https://github.com/daodao97/chatmcp/releases/tag/v0.0.1-alpha)


32 条回复  **•**  2024-12-19 11:13:58 +08:00

|   |   |   |
|---|---|---|
|![cowcomic](https://cdn.v2ex.com/avatar/4939/ffd8/73524_normal.png?m=1727658639)||1<br><br>**[cowcomic](/member/cowcomic)**  <br><br>   60 天前<br><br>点个赞，收藏一下，之前看到 MCP 的时候就觉得这个很有用  <br>能接入 ollama 这个太棒了|

|   |   |   |
|---|---|---|
|![tpcy](https://cdn.v2ex.com/avatar/e9f0/2793/212986_normal.png?m=1702431869)||2<br><br>**[tpcy](/member/tpcy)**  <br><br>   60 天前<br><br>支持！已 star|

|   |   |   |
|---|---|---|
|![clemente](https://cdn.v2ex.com/avatar/9a6c/b769/455659_normal.png?m=1735610803)||3<br><br>**[clemente](/member/clemente)**  <br><br>   60 天前<br><br>用 dart flutter 做客户端和 electron 有什么区别吗|

|   |   |   |
|---|---|---|
|![zapll](https://cdn.v2ex.com/avatar/ea4c/2176/590499_normal.png?m=1730366396)||4<br><br>**[zapll](/member/zapll)**  <br><br>OP<br><br>   60 天前<br><br>@[cowcomic](/member/cowcomic) 具体介入 ollama 的部分还没实现, todo 了  <br>  <br>@[clemente](/member/clemente) 只从使用层面的话, 实现了同样的功能, 是没有差别的, 开发层面就看开发者熟系那个了|

|   |   |   |
|---|---|---|
|![foufoufm](https://cdn.v2ex.com/avatar/0484/763b/499086_normal.png?m=1733884433)||5<br><br>**[foufoufm](/member/foufoufm)**  <br><br>   60 天前<br><br>@[zapll](/member/zapll) 下载了，但是我的 mbp 打开闪退，从 github 上添加好友了，但是没有通过|

|   |   |   |
|---|---|---|
|![shil949](https://cdn.v2ex.com/avatar/29b1/efff/597725_normal.png?m=1694493948)||6<br><br>**[shil949](/member/shil949)**  <br><br>   60 天前<br><br>mbp 打开闪退|

|   |   |   |
|---|---|---|
|![crokily](https://cdn.v2ex.com/gravatar/39e659a7e2c3b155536b83717776dfe2?s=48&d=retro)||7<br><br>**[crokily](/member/crokily)**  <br><br>   60 天前<br><br>居然还能支持不同的模型！想想也是毕竟 MCP 只是个协议，不过也是第一次见到把它用在其他模型上。  <br>早早就在推上关注了作者，因为感觉想法很领先，目前确实没见过有把 MCP 往这种平台式设计的想法， 大多数都还在尝试 MCP 的单独应用设计。一个好用的开放平台比单独的应用更有前景啊  <br>期待一下 Win 端|

|   |   |   |
|---|---|---|
|![zapll](https://cdn.v2ex.com/avatar/ea4c/2176/590499_normal.png?m=1730366396)||8<br><br>**[zapll](/member/zapll)**  <br><br>OP<br><br>   60 天前<br><br>@[foufoufm](/member/foufoufm) @[shil949](/member/shil949) 有没有日志可以提供, 我是 M3 下打包的|

|   |   |   |
|---|---|---|
|![foufoufm](https://cdn.v2ex.com/avatar/0484/763b/499086_normal.png?m=1733884433)||9<br><br>**[foufoufm](/member/foufoufm)**  <br><br>   60 天前<br><br>@[zapll](/member/zapll) 怀疑是环境问题，查看 readme 后发现没有预装环境，目前没时间验证，下午再看看，通过个微信好友呗～|

|   |   |   |
|---|---|---|
|![zapll](https://cdn.v2ex.com/avatar/ea4c/2176/590499_normal.png?m=1730366396)||10<br><br>**[zapll](/member/zapll)**  <br><br>OP<br><br>   60 天前<br><br>@[foufoufm](/member/foufoufm) 推上私信我一下 [https://x.com/daodao97_](https://x.com/daodao97_)|

|   |   |   |
|---|---|---|
|![swaggeek](https://cdn.v2ex.com/gravatar/0817cfc305c6209f25b92d698e39283d?s=48&d=retro)||11<br><br>**[swaggeek](/member/swaggeek)**  <br><br>   60 天前<br><br>目前支持接入除 Claude 之外的 provider 么？|

|   |   |   |
|---|---|---|
|![woorz](https://cdn.v2ex.com/avatar/c723/579a/39913_normal.png?m=1719626835)||12<br><br>**[woorz](/member/woorz)**  <br><br>   60 天前<br><br>这个不就是 rag 吗？ mcp 之前都可以实现这些的啊|

|   |   |   |
|---|---|---|
|![jimmy3780](https://cdn.v2ex.com/avatar/3e51/3517/372321_normal.png?m=1727681075)||13<br><br>**[jimmy3780](/member/jimmy3780)**  <br><br>   60 天前 via Android<br><br>@[woorz](/member/woorz) MCP 是一套标准，有点类似于微软的 LSP 。它想解决的事情应该是让开发者只需要开发一次基于 MCP 的插件，任何支持 MCP 的宿主软件都可以直接使用这些现有插件|

|   |   |   |
|---|---|---|
|![thetbw](https://cdn.v2ex.com/avatar/5086/bbd2/460473_normal.png?m=1709107492)||14<br><br>**[thetbw](/member/thetbw)**  <br><br>   60 天前<br><br>学到了|

|   |   |   |
|---|---|---|
|![swaggeek](https://cdn.v2ex.com/gravatar/0817cfc305c6209f25b92d698e39283d?s=48&d=retro)||15<br><br>**[swaggeek](/member/swaggeek)**  <br><br>   60 天前<br><br>目前支持接入除 Claude 之外的 provider 么？|

|   |   |   |
|---|---|---|
|![stonesirsir](https://cdn.v2ex.com/gravatar/f5dfb7e36a451c1c617fe583c2c0c29f?s=48&d=retro)||16<br><br>**[stonesirsir](/member/stonesirsir)**  <br><br>   60 天前<br><br>已经 star|

|   |   |   |
|---|---|---|
|![zapll](https://cdn.v2ex.com/avatar/ea4c/2176/590499_normal.png?m=1730366396)||17<br><br>**[zapll](/member/zapll)**  <br><br>OP<br><br>   60 天前<br><br>@[swaggeek](/member/swaggeek) 目前只实现了 openai 的模型接入, 其他的慢慢来|

|   |   |   |
|---|---|---|
|![swaggeek](https://cdn.v2ex.com/gravatar/0817cfc305c6209f25b92d698e39283d?s=48&d=retro)||18<br><br>**[swaggeek](/member/swaggeek)**  <br><br>   60 天前<br><br>可以，我看下代码实现。也想按 MCP 的协议去搞一些其他模型的|

|   |   |   |
|---|---|---|
|![san3](https://cdn.v2ex.com/gravatar/9410348c0999d029520b4d90b33531d4?s=48&d=retro)||19<br><br>**[san3](/member/san3)**  <br><br>   59 天前<br><br>已 star|

|   |   |   |
|---|---|---|
|![mortal](https://cdn.v2ex.com/avatar/d838/a873/59363_normal.png?m=1667466130)||20<br><br>**[mortal](/member/mortal)**  <br><br>   59 天前<br><br>为啥 brew 没有这两个包啊|

|   |   |   |
|---|---|---|
|![san3](https://cdn.v2ex.com/gravatar/9410348c0999d029520b4d90b33531d4?s=48&d=retro)||21<br><br>**[san3](/member/san3)**  <br><br>   59 天前<br><br>uvx npx 是什么命令？ brew 提示没有这俩命令|

|   |   |   |
|---|---|---|
|![marquina](https://cdn.v2ex.com/avatar/4841/3ba4/460333_normal.png?m=1723611611)||22<br><br>**[marquina](/member/marquina)**  <br><br>   59 天前<br><br>MCP 的协议大佬是在哪看的？我想用在自己的助手 bot 上，有啥推荐的文档吗|

|   |   |   |
|---|---|---|
|![zapll](https://cdn.v2ex.com/avatar/ea4c/2176/590499_normal.png?m=1730366396)||23<br><br>**[zapll](/member/zapll)**  <br><br>OP<br><br>   59 天前<br><br>@[san3](/member/san3)  <br>  <br># uvx  <br>brew install uv  <br>  <br># npx  <br>brew install node  <br>  <br>@[marquina](/member/marquina) 得有一个支持 mcp 的客户端 chatmcp 这种|

|   |   |   |
|---|---|---|
|![san3](https://cdn.v2ex.com/gravatar/9410348c0999d029520b4d90b33531d4?s=48&d=retro)||24<br><br>**[san3](/member/san3)**  <br><br>   59 天前<br><br>@[zapll](/member/zapll) 软件打开后，install 模块的时候提示 uvx 不存在。你这为什么叫 uvx ？ 这不就是一个 python 包管理器吗？本地别名？|

|   |   |   |
|---|---|---|
|![jimmy3780](https://cdn.v2ex.com/avatar/3e51/3517/372321_normal.png?m=1727681075)||25<br><br>**[jimmy3780](/member/jimmy3780)**  <br><br>   59 天前 via iPhone<br><br>@[san3](/member/san3) 因为用的是 uv 啊 🤔，不是因为 op 想叫这个|

|   |   |   |
|---|---|---|
|![san3](https://cdn.v2ex.com/gravatar/9410348c0999d029520b4d90b33531d4?s=48&d=retro)||26<br><br>**[san3](/member/san3)**  <br><br>   59 天前<br><br>@[jimmy3780](/member/jimmy3780) 了解。uv 和 uvx 是一起的。但是一个 app 应用依赖命令行，环境变量还是不能修改的：/usr/bin:/bin:/usr/sbin:/sbin ，是不是需要完善一下？|

|   |   |   |
|---|---|---|
|![zapll](https://cdn.v2ex.com/avatar/ea4c/2176/590499_normal.png?m=1730366396)||27<br><br>**[zapll](/member/zapll)**  <br><br>OP<br><br>   59 天前<br><br>@[san3](/member/san3) 目前内置了常见的 bin 目录, 后续增加一个自定义配置的功能|

|   |   |   |
|---|---|---|
|![has](https://cdn.v2ex.com/avatar/7f8b/4356/198349_normal.png?m=1489735393)||28<br><br>**[has](/member/has)**  <br><br>   58 天前<br><br>已 star|

|   |   |   |
|---|---|---|
|![GARLICTRUMP](https://cdn.v2ex.com/gravatar/c40901340e96129fd4dc287b19b9a1c1?s=48&d=retro)||29<br><br>**[GARLICTRUMP](/member/GARLICTRUMP)**  <br><br>   57 天前<br><br>claude 应该在 mcp 上微调过吧，换别的模型能达到类似效果吗|

|   |   |   |
|---|---|---|
|![284716337](https://cdn.v2ex.com/avatar/2929/913e/181458_normal.png?m=1696901329)||30<br><br>**[284716337](/member/284716337)**  <br><br>   51 天前 via Android<br><br>出 windows 了踢我下|

|   |   |   |
|---|---|---|
|![zapll](https://cdn.v2ex.com/avatar/ea4c/2176/590499_normal.png?m=1730366396)||31<br><br>**[zapll](/member/zapll)**  <br><br>OP<br><br>   51 天前<br><br>@[284716337](/member/284716337) 已经有了, 一个印度小哥 PR 的, 仓库 release 里下载|

|   |   |   |
|---|---|---|
|![284716337](https://cdn.v2ex.com/avatar/2929/913e/181458_normal.png?m=1696901329)||32<br><br>**[284716337](/member/284716337)**  <br><br>   51 天前<br><br>@[zapll](/member/zapll) 多谢多谢|
