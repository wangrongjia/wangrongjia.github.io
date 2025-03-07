---
link: https://www.v2ex.com/t/1109311
site: V2EX
date: 2025-02-06T13:17
excerpt: 程序员 - @CodingNameless - 关于本地部署 DeepSeek-r1
  模型进行定制化训练的问题，想请教一些技术细节。我们公司计划开发一套智能问答系统，主要用于内部业务指南的自动化处理。考虑到数据安全性和定制化需求，我们希望在本地环境
twitter: https://twitter.com/@V2EX
slurped: 2025-02-06T17:30
title: 如何本地部署 DeepSeek-r1 模型训练自己的大模型 - V2EX
---

# 如何本地部署 DeepSeek-r1 模型训练自己的大模型


  [CodingNameless](/member/CodingNameless) · 4 小时 11 分钟前 · 584 次点击

关于本地部署 DeepSeek-r1 模型进行定制化训练的问题，想请教一些技术细节。我们公司计划开发一套智能问答系统，主要用于内部业务指南的自动化处理。考虑到数据安全性和定制化需求，我们希望在本地环境部署 DeepSeek-r1 模型。

具体而言，我们有以下疑问：

通过向模型提供高质量的领域特定数据，是否能够有效训练出符合公司业务需求的定制化模型？ 在训练过程中所使用的技术是什么？ 我们计划使用公司积累的高质量业务文档和知识库作为训练数据，期望最终模型能够准确理解和回答与公司业务相关的问题。

感谢各位大佬的宝贵时间和建议！


9 条回复

|   |   |   |
|---|---|---|
|![Kite6](https://cdn.v2ex.com/gravatar/c53b0d09e248afaf64ed4f6259063537?s=48&d=retro)||1<br><br>**[Kite6](/member/Kite6)**  <br><br>   3 小时 50 分钟前 via Android<br><br>671b ，成本爆炸|

|   |   |   |
|---|---|---|
|![CodingNameless](https://cdn.v2ex.com/gravatar/5316642f050bbfe16a436665a8acd1d8?s=48&d=retro)||2<br><br>**[CodingNameless](/member/CodingNameless)**  <br><br>OP<br><br>   3 小时 48 分钟前<br><br>不会用到 671b ，只是 14b 或者 32b 这种能回答一些基本问题的，然后也能结合我们公司的业务知识|

|   |   |   |
|---|---|---|
|![CodingNameless](https://cdn.v2ex.com/gravatar/5316642f050bbfe16a436665a8acd1d8?s=48&d=retro)||3<br><br>**[CodingNameless](/member/CodingNameless)**  <br><br>OP<br><br>   3 小时 48 分钟前<br><br>@[Kite6](/member/Kite6) #1 不会用到 671b ，只是 14b 或者 32b 这种能回答一些基本问题的，然后也能结合我们公司的业务知识|

|   |   |   |
|---|---|---|
|![qxmqh](https://cdn.v2ex.com/avatar/2a36/708f/643486_normal.png?m=1731111200)||4<br><br>**[qxmqh](/member/qxmqh)**  <br><br>   3 小时 14 分钟前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>你去 github 上搜一个叫 LLaMA-Factory 的东西。你会发现有惊喜。|

|                                                                                          |     |                                                                                                                     |
| ---------------------------------------------------------------------------------------- | --- | ------------------------------------------------------------------------------------------------------------------- |
| ![Mianmiss](https://cdn.v2ex.com/gravatar/97c80e39692a9a1858f9e709e2e3e69a?s=48&d=retro) |     | 5<br><br>**[Mianmiss](/member/Mianmiss)**  <br><br>   2 小时 18 分钟前<br><br>**推荐你用 DIFY 建立公司知识库，微调就算有框架，没点技术 也很难训练成。** |

|   |   |   |
|---|---|---|
|![Dw521](https://cdn.v2ex.com/avatar/6170/a8d0/488214_normal.png?m=1672302552)||6<br><br>**[Dw521](/member/Dw521)**  <br><br>   2 小时 1 分钟前<br><br>ollama 搜索一下这个也会有惊喜|

|                                                                                        |     |                                                                                            |
| -------------------------------------------------------------------------------------- | --- | ------------------------------------------------------------------------------------------ |
| ![visper](https://cdn.v2ex.com/gravatar/838db077a2334ed6bcbc29c29ab41a6e?s=48&d=retro) |     | 7<br><br>**[visper](/member/visper)**  <br><br>   1 小时 43 分钟前<br><br>**直接 ollama 一个命令...** |

|                                                                                     |     |                                                                                                                                          |
| ----------------------------------------------------------------------------------- | --- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| ![newaccount](https://cdn.v2ex.com/avatar/12cb/9729/528250_normal.png?m=1713948986) |     | 8<br><br>**[newaccount](/member/newaccount)**  <br><br>   46 分钟前<br><br>**14b 和 32b 就是被 deepseek-r1 提拔了两句的阿里通义千问，它跟 deepseek 的关系就是没啥关系** |

|                                                                                |     |                                                                                                            |     |
| ------------------------------------------------------------------------------ | --- | ---------------------------------------------------------------------------------------------------------- | --- |
| ![heliar](https://cdn.v2ex.com/avatar/1e66/31e1/66189_normal.png?m=1438665687) |     | 9<br><br>**[heliar](/member/heliar)**  <br><br>   25 分钟前<br><br>先别一开始就想着训练，**用 RAG 试试**。  训练的话你知识库经常更新成本不低 |     |
|                                                                                |     | _RAG（Retrieval Augmented Generation_）是一种使用大型语言模型的方法_检索增强生成（RAG_）将LLMs与外部知识库相结合，以提高其输出。                     |     |
