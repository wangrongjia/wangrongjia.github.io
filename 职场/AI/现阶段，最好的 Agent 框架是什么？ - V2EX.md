---
link: https://www.v2ex.com/t/1102516
site: V2EX
date: 2025-01-04T17:02
excerpt: 程序员 - @galileo1214 - 目前在看 coze ，dify 或者 langchain
twitter: https://twitter.com/@V2EX
slurped: 2025-02-05T14:20
title: 现阶段，最好的 Agent 框架是什么？ - V2EX
---


# 现阶段，最好的 Agent 框架是什么？



  [galileo1214](/member/galileo1214) · 31 天前 · 2475 次点击

目前在看 coze ，dify 或者 langchain


14 条回复

|   |   |   |
|---|---|---|
|![INCerry](https://cdn.v2ex.com/gravatar/8ef2ea2725ee123c4b6969dab2d7e492?s=48&d=retro)||1<br><br>**[INCerry](/member/INCerry)**  <br><br>   31 天前<br><br>我们用 Semantic Kernel 比较多，做应用很方便|

|   |   |   |
|---|---|---|
|![dwu8555](https://cdn.v2ex.com/avatar/80ef/3e1b/293789_normal.png?m=1734394843)||2<br><br>**[dwu8555](/member/dwu8555)**  <br><br>   31 天前<br><br>eliza?|

|   |   |   |
|---|---|---|
|![galileo1214](https://cdn.v2ex.com/gravatar/b097371b4d4bb1e7c9c67ba8199223ed?s=48&d=retro)||3<br><br>**[galileo1214](/member/galileo1214)**  <br><br>OP<br><br>   31 天前<br><br>@[INCerry](/member/INCerry) 我研究下，多谢|

|   |   |   |
|---|---|---|
|![crackidz](https://cdn.v2ex.com/gravatar/e5311b443d279d0bce5f7e7606af6c41?s=48&d=retro)||4<br><br>**[crackidz](/member/crackidz)**  <br><br>   31 天前<br><br>langgraph 正在用  <br>phidata 正在看|

|   |   |   |
|---|---|---|
|![galileo1214](https://cdn.v2ex.com/gravatar/b097371b4d4bb1e7c9c67ba8199223ed?s=48&d=retro)||5<br><br>**[galileo1214](/member/galileo1214)**  <br><br>OP<br><br>   31 天前<br><br>@[crackidz](/member/crackidz) langgraph 好用吗？|

|   |   |   |
|---|---|---|
|![crackidz](https://cdn.v2ex.com/gravatar/e5311b443d279d0bce5f7e7606af6c41?s=48&d=retro)||6<br><br>**[crackidz](/member/crackidz)**  <br><br>   31 天前<br><br>@[galileo1214](/member/galileo1214) 吐槽网上搜索一下就是啦|

|   |   |   |
|---|---|---|
|![wellCh4n](https://cdn.v2ex.com/avatar/243c/b4ea/249469_normal.png?m=1726886513)||7<br><br>**[wellCh4n](/member/wellCh4n)**  <br><br>   31 天前<br><br>我理解 langchain 才是框架，coze 和 dify 都是有大模型节点的低代码流程编排平台。|

|   |   |   |
|---|---|---|
|![riceball](https://cdn.v2ex.com/gravatar/f7b81e783188e376c9f046ae1285d47f?s=48&d=retro)||8<br><br>**[riceball](/member/riceball)**  <br><br>   31 天前<br><br>取决于你想干啥，比如,🙆‍♀️也许想这么干：  <br>  <br>翻译家.ai.yaml  <br>  <br>---  <br>input: ['lang', 'text']  <br>output: {type: 'object', properties: {target_text: {type: string}}}  <br>parameters:  <br>temperature: 0  <br>---  <br>system: 你是全球最棒的多语言翻译家。  <br>user: 请直接把接下来的文字翻译为{{lang}}："{{text}}"  <br>assistant: [[AI]]  <br>-> json(output)  <br>  <br>  <br>nodejs 调用：  <br>  <br>import {AIScript} from '@...'  <br>const result = await AIScript.execFile('翻译家.ai.yaml', {text: 'here is text', lang: '中文'})  <br>// result: {target_text: '这是文本'}|

|   |   |   |
|---|---|---|
|![nl101531](https://cdn.v2ex.com/avatar/2f7a/7169/217390_normal.png?m=1653443695)||9<br><br>**[nl101531](/member/nl101531)**  <br><br>   31 天前 via iPhone<br><br>agent 看起来更像是应用范式，没太理解框架在这里到底有啥用|

|   |   |   |
|---|---|---|
|![aijam](https://cdn.v2ex.com/avatar/3302/5eb2/202695_normal.png?m=1479937197)||10<br><br>**[aijam](/member/aijam)**  <br><br>   31 天前<br><br>@[nl101531](/member/nl101531) 你提出了一个好问题。其实没必要套用他们的框架，但是了解框架里面的一些范式可以给自己更多解决问题的思路。|

|   |   |   |
|---|---|---|
|![wicsp](https://cdn.v2ex.com/gravatar/ec24cc7263458525c16b733af29e0204?s=48&d=retro)||11<br><br>**[wicsp](/member/wicsp)**  <br><br>   30 天前<br><br>我最近也在考虑这个问题，HuggingFace 刚出了一个 smolagents, 好像很易用，打算先从这个入手|

|                                                                               |     |                                                                                                                                                                                                                   |
| ----------------------------------------------------------------------------- | --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ![highkay](https://cdn.v2ex.com/avatar/82ce/c960/355_normal.png?m=1314460625) |     | 12<br><br>**[highkay](/member/highkay)**  <br><br>   30 天前<br><br>**两大类，一类是可视化编排的 coze ，dify 的，一类是开发框架的，langchain ，langgraph ，autogen ，crew ，smolagents 等等，后者还分对话式和代码组装，抽象级别啥的，其实最近 anthopic 发的文章是建议用更轻而非更重的框架**。 |

|                                                                                        |     |                                                                                                                          |
| -------------------------------------------------------------------------------------- | --- | ------------------------------------------------------------------------------------------------------------------------ |
| ![kerb15](https://cdn.v2ex.com/gravatar/fe8954f4768ae6a30f36ec5028c68484?s=48&d=retro) |     | 13<br><br>**[kerb15](/member/kerb15)**  <br><br>   30 天前<br><br>框架的使用成本都不低，而 functioncall 的 api 的学习成本很低，了解之后自己实现一个框架可能更快 |

|   |   |   |
|---|---|---|
|![cryptonym](https://cdn.v2ex.com/gravatar/92f2d87a9a0d13b71820924ba8e116a9?s=48&d=retro)||14<br><br>**[cryptonym](/member/cryptonym)**  <br><br>   30 天前<br><br>原来 ai agent 这么火，还停留在 web3 炒作的印象，信息茧房了。|

