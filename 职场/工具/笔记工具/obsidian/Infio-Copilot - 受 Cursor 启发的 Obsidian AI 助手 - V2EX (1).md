---
link: https://www.v2ex.com/t/1103030
site: V2EX
date: 2025-01-06T23:07
excerpt: 分享创造 - @finesixseven - https://github.com/infiolab/infio-copilot基本实现对
  cursor 1:1 复刻deepseek-v3 非常便宜, 适合笔记场景, 所有的 pr
twitter: https://twitter.com/@V2EX
slurped: 2025-02-06T09:09
title: "Infio-Copilot: 受 Cursor 启发的 Obsidian AI 助手，提供智能自动补全和与选定笔记的交互式聊天 - V2EX"
---

# Infio-Copilot: 受 Cursor 启发的 Obsidian AI 助手，提供智能自动补全和与选定笔记的交互式聊天


[duanfuxiang0](https://github.com/duanfuxiang0) · 30 天前 · 2060 次点击

[https://github.com/infiolab/infio-copilot](https://github.com/infiolab/infio-copilot)  
  
基本实现对 cursor 1:1 复刻  
  
deepseek-v3 非常便宜, 适合笔记场景, 所有的 prompt 都对它进行了优化  
  
有任何问题都欢迎直接站内联系, 或者 email 我  
  
聊天与编辑流程  
在 Obsidian 中一键获取 AI 帮助并应用建议改进, 例如: 改写/润色/翻译 ...  
[![](//i.v2ex.co/j8cJbfs1.gif)](/i/j8cJbfs1.gif "在新窗口打开图片 j8cJbfs1.gif")  
  
自动补全  
在输入时获取上下文感知的写作建议,  
使用 deepseek 的 FIM 功能, 对 代码块, 数学公式, mermaid 都有适配  
[![](//i.v2ex.co/Vg0s8c85l.gif)](/i/Vg0s8c85l.gif "在新窗口打开图片 Vg0s8c85l.gif")  
  
内联编辑  
在当前文件中直接编辑笔记, 类似于 cursor edit inline  
[![](//i.v2ex.co/bVkn62Adl.gif)](/i/bVkn62Adl.gif "在新窗口打开图片 bVkn62Adl.gif")  
  
与知识库聊天 使用 pglite, 所有数据存储在本地  
利用 AI 的强大功能与整个 Obsidian 知识库互动，获取笔记中的见解和联系  
[![](//i.v2ex.co/fC55G316.gif)](/i/fC55G316.gif "在新窗口打开图片 fC55G316.gif")  
  
你也可以直接 粘贴 web url 和 图片, 进行对话

第 1 条附言  ·  29 天前

还在等待审核, 目前可以手动下载  
[https://github.com/infiolab/infio-copilot/releases/download/0.0.2/obsidian-infio-copilot-0.0.2.zip](https://github.com/infiolab/infio-copilot/releases/download/0.0.2/obsidian-infio-copilot-0.0.2.zip)  
解压到 vault 插件目录下  
demo_vault/.obsidian/plugins  
  
  
或者可以使用 BRAT  
1. 安装 BRAT 插件  
2. 打开命令输入并选择 : BRAT: Plugin: Add a beta plugin for testing  
3. 输入 [https://github.com/infiolab/infio-copilot](https://github.com/infiolab/infio-copilot)  
[![](//i.v2ex.co/9Es9ew31.png)](/i/9Es9ew31.png "在新窗口打开图片 9Es9ew31.png")  
4. 点击 Add Plugin 搞定  
  
BRAT 其实就是帮你自动下载解压

第 2 条附言  ·  29 天前

我建了一个 telegram 群组  
如果有遇到任何 安装 / API 配置 / 使用问题, 可以直接询问, 在线支持  
[https://t.me/+VHXvdT_ncDA4Njdl](https://t.me/+VHXvdT_ncDA4Njdl)

第 3 条附言  ·  22 天前

doc:  
[https://infio.app/docs/guide/get-start](https://infio.app/docs/guide/get-start)

[

Obsidian](/tag/Obsidian)[

AI](/tag/AI)[

DeepSeek](/tag/DeepSeek)

26 条回复  **•**  2025-01-18 16:44:38 +08:00

|   |   |   |
|---|---|---|
|![yyrj](https://cdn.v2ex.com/avatar/a0ee/dbc2/66791_normal.png?m=1736170693)||1<br><br>**[yyrj](/member/yyrj)**  <br><br>   30 天前<br><br>在 OB 的社区插件搜不到呢？|

|   |   |   |
|---|---|---|
|![SenLief](https://cdn.v2ex.com/avatar/d6cf/28a8/195119_normal.png?m=1663686232)||2<br><br>**[SenLief](/member/SenLief)**  <br><br>   30 天前<br><br>deepseekv3 我怎么感觉在文字功底上比代码要强呢|

|   |   |   |
|---|---|---|
|![zwpaper](https://cdn.v2ex.com/avatar/90cb/3ed8/33440_normal.png?m=1359701662)||3<br><br>**[zwpaper](/member/zwpaper)**  <br><br>   30 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>厉害了，前一阵还在想类似的东西，这就有人做出来了|

|   |   |   |
|---|---|---|
|![zwpaper](https://cdn.v2ex.com/avatar/90cb/3ed8/33440_normal.png?m=1359701662)||4<br><br>**[zwpaper](/member/zwpaper)**  <br><br>   30 天前<br><br>能否支持配置 api endpoint ，这样就能用自定义的模型，例如本地模型|

|   |   |   |
|---|---|---|
|![4ark](https://cdn.v2ex.com/avatar/fa21/ec17/371833_normal.png?m=1637549287)||5<br><br>**[4ark](/member/4ark)**  <br><br>   30 天前 via iPhone   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>牛逼，明天试用一下|

|   |   |   |
|---|---|---|
|![qxmqh](https://cdn.v2ex.com/avatar/2a36/708f/643486_normal.png?m=1731111200)||6<br><br>**[qxmqh](/member/qxmqh)**  <br><br>   30 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>挺好的，希望 OP 产出更多优秀工具。|

|   |   |   |
|---|---|---|
|![finesixseven](https://cdn.v2ex.com/avatar/6635/be3c/345468_normal.png?m=1708761670)||7<br><br>**[finesixseven](/member/finesixseven)**  <br><br>OP<br><br>   30 天前<br><br>@[yyrj](/member/yyrj) 我昨天提交了审核, 还没有通过  <br>[https://github.com/obsidianmd/obsidian-releases/pull/5078](https://github.com/obsidianmd/obsidian-releases/pull/5078)  <br>  <br>不过 obsidian 插件十分简单, 只需要 clone 到 对应 plugin 目录下就能使用  <br>demo_vault/.obsidian/plugins|

|   |   |   |
|---|---|---|
|![shuxhan](https://cdn.v2ex.com/avatar/d737/3168/527303_normal.png?m=1737013945)||8<br><br>**[shuxhan](/member/shuxhan)**  <br><br>   30 天前<br><br>抱歉 我没有在市场找到这个插件 Infio-Copilot|

|   |   |   |
|---|---|---|
|![finesixseven](https://cdn.v2ex.com/avatar/6635/be3c/345468_normal.png?m=1708761670)||9<br><br>**[finesixseven](/member/finesixseven)**  <br><br>OP<br><br>   29 天前<br><br>@[SenLief](/member/SenLief) 我感觉它代码也挺强, 我现在 cline + deepseekv3 编写大部分的 代码整理重写任务, 体感跟 Claude 3.5 差不多, 主要是便宜 1/10 价格, 他的文字输出, 特别是长文本输出, 感觉有点机器味, 也可能是我 prompt 的原因|

|   |   |   |
|---|---|---|
|![finesixseven](https://cdn.v2ex.com/avatar/6635/be3c/345468_normal.png?m=1708761670)||10<br><br>**[finesixseven](/member/finesixseven)**  <br><br>OP<br><br>   29 天前<br><br>@[zwpaper](/member/zwpaper) 可以自定模型, 只要符合这几个访问协议就可以  <br>[![](//i.v2ex.co/8EqtT125.png)](/i/8EqtT125.png "在新窗口打开图片 8EqtT125.png")|

|   |   |   |
|---|---|---|
|![finesixseven](https://cdn.v2ex.com/avatar/6635/be3c/345468_normal.png?m=1708761670)||11<br><br>**[finesixseven](/member/finesixseven)**  <br><br>OP<br><br>   29 天前<br><br>@[shuxhan](/member/shuxhan) 抱歉 还在等待审核, 目前可使用 附言中的方式|

|   |   |   |
|---|---|---|
|![registered](https://cdn.v2ex.com/avatar/56f1/70a0/459888_normal.png?m=1576665164)||12<br><br>**[registered](/member/registered)**  <br><br>   29 天前<br><br>感谢，最近正好在找这类插件，试用了几个都不太满意。就是没找到哪里可以给楼主买咖啡~|

|   |   |   |
|---|---|---|
|![finesixseven](https://cdn.v2ex.com/avatar/6635/be3c/345468_normal.png?m=1708761670)||13<br><br>**[finesixseven](/member/finesixseven)**  <br><br>OP<br><br>   29 天前<br><br>@[registered](/member/registered) 暂时帮 start 支持一下就好, 有任何问题 都欢迎联系|

|   |   |   |
|---|---|---|
|![SenLief](https://cdn.v2ex.com/avatar/d6cf/28a8/195119_normal.png?m=1663686232)||14<br><br>**[SenLief](/member/SenLief)**  <br><br>   29 天前<br><br>@[finesixseven](/member/finesixseven) cline 消耗 token 太快了，我现在用 copilot 搭配 deepseek 使用，token 还能接受。|

|   |   |   |
|---|---|---|
|![yzld2002](https://cdn.v2ex.com/gravatar/918c0a2d518b8fd9b7ba4be810df0877?s=48&d=retro)||15<br><br>**[yzld2002](/member/yzld2002)**  <br><br>   29 天前<br><br>赞，已 star|

|   |   |   |
|---|---|---|
|![Vitta](https://cdn.v2ex.com/avatar/e69c/5c78/251210_normal.png?m=1689733357)||16<br><br>**[Vitta](/member/Vitta)**  <br><br>   29 天前<br><br>审核过了踢我下[让我看看]|

|   |   |   |
|---|---|---|
|![0x5c0f](https://cdn.v2ex.com/avatar/2e09/fbb1/663955_normal.png?m=1729668750)||17<br><br>**[0x5c0f](/member/0x5c0f)**  <br><br>   29 天前<br><br>已有插件 continue dev|

|   |   |   |
|---|---|---|
|![yuhangch](https://cdn.v2ex.com/avatar/0cc7/3790/467934_normal.png?m=1680072171)||18<br><br>**[yuhangch](/member/yuhangch)**  <br><br>   29 天前<br><br>不是哥们，完成度也太高了，像要付费才能用的东西👍|

|   |   |   |
|---|---|---|
|![stefwoo](https://cdn.v2ex.com/gravatar/3235f0cda8845c15590a7b5de5c89f10?s=48&d=retro)||19<br><br>**[stefwoo](/member/stefwoo)**  <br><br>   29 天前<br><br>我这两天正在想是不是开发个这样的就出来，棒|

|   |   |   |
|---|---|---|
|![Altairvelvet](https://cdn.v2ex.com/gravatar/daef507ab03f1ea7e8cb801357b13d9e?s=48&d=retro)||20<br><br>**[Altairvelvet](/member/Altairvelvet)**  <br><br>   29 天前<br><br>@[yuhangch](/member/yuhangch) 我也感觉想要付费才能用的东西。  <br>  <br>刚刚配置好，用上了，太牛逼了！  <br>  <br>这必须得在 Github 上给你点个 star 了！|

|   |   |   |
|---|---|---|
|![finesixseven](https://cdn.v2ex.com/avatar/6635/be3c/345468_normal.png?m=1708761670)||21<br><br>**[finesixseven](/member/finesixseven)**  <br><br>OP<br><br>   29 天前<br><br>@[Altairvelvet](/member/Altairvelvet)  <br>@[yuhangch](/member/yuhangch)  <br>保证 所有客户端的功能都永久免费、开源, 现在大家都是自带的 key, 真没必要使用客户端 还要再掏钱  <br>  <br>我也给 zetore 写一个插件, zetore 上面也没有一个好用的,  <br>这个专注于读书/paper, 主要的 context 是 当前阅读进度/highlight; 复用了目前大部分代码, 但是 zetore 插件 比 obsidian 麻烦的多, 进度缓慢,...  <br>  <br>  <br>我正在写一个 infio-service, 基本写完了, 正在部署/测试  <br>- 可以直接当做 key 接入 Obsidian / zetore 使用, 支持所有 LLM  <br>- 也可以在 webapp 直接使用, 目前主要给 pdf 阅读优化,  <br>[![](//i.v2ex.co/GTMTqW7o.jpeg)](/i/GTMTqW7o.jpeg "在新窗口打开图片 GTMTqW7o.jpeg")|

|   |   |   |
|---|---|---|
|![coolliuzw](https://cdn.v2ex.com/gravatar/91007c09c42c0455a2dba57c06038344?s=48&d=retro)||22<br><br>**[coolliuzw](/member/coolliuzw)**  <br><br>   24 天前<br><br>以下是应用了 JSON-RPC 格式的完整修改：  <br>  <br><!-- ... existing content ... -->  <br>  <br>### 设备上报属性  <br>  <br>请求：  <br>{  <br>"jsonrpc": "2.0",  <br>"id": "123456",  <br>"method": "[thing.event.property.post](http://thing.event.property.post)",  <br>"params": {  <br>"temperature": 25.5,  <br>"humidity": 60  <br>}  <br>}  <br>  <br><!-- ... existing content ... -->  <br>  <br>自定义模型，无法进行自动 apply 编辑笔记文件，请问这个怎么解决呢？|

|   |   |   |
|---|---|---|
|![finesixseven](https://cdn.v2ex.com/avatar/6635/be3c/345468_normal.png?m=1708761670)||23<br><br>**[finesixseven](/member/finesixseven)**  <br><br>OP<br><br>   23 天前<br><br>@[coolliuzw](/member/coolliuzw) 我记录一下, 最好能提供一下更具体的信息,  <br>例如 model 名称,  <br>  <br>如果是非常弱的模型, 代码能力很弱, 可能无法生成 apply|

|   |   |   |
|---|---|---|
|![karlakte](https://cdn.v2ex.com/avatar/a208/b894/66257_normal.png?m=1408692507)||24<br><br>**[karlakte](/member/karlakte)**  <br><br>   22 天前<br><br>好像还没有通过审核。|

|   |   |   |
|---|---|---|
|![finesixseven](https://cdn.v2ex.com/avatar/6635/be3c/345468_normal.png?m=1708761670)||25<br><br>**[finesixseven](/member/finesixseven)**  <br><br>OP<br><br>   22 天前<br><br>还没有, 可以通过文档中方式 尝试安装  <br>[https://infio.app/docs/guide/get-start](https://infio.app/docs/guide/get-start)|

|   |   |   |
|---|---|---|
|![coolliuzw](https://cdn.v2ex.com/gravatar/91007c09c42c0455a2dba57c06038344?s=48&d=retro)||26<br><br>**[coolliuzw](/member/coolliuzw)**  <br><br>   18 天前<br><br>@[finesixseven](/member/finesixseven) 配置是的 deepseek-chat 的模型|

