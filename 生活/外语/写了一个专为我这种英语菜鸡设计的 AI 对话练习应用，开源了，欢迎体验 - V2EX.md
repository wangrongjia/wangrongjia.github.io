---
link: https://www.v2ex.com/t/1096005
site: V2EX
date: 2024-12-09T09:54
excerpt: 分享创造 - @Orenoid - GitHub 仓库： https://github.com/Orenoid/BabelDuck  在线
  Demo：[BabelDuck]( https://duck.orenoid.com)
twitter: https://twitter.com/@V2EX
slurped: 2025-02-08T14:22
title: 写了一个专为我这种英语菜鸡设计的 AI 对话练习应用，开源了，欢迎体验 - V2EX
---
 
[Orenoid](https://github.com/Orenoid) · 61 天前 · 3006 次点击

这是一个创建于 61 天前的主题，其中的信息可能已经有所发展或是发生改变。

GitHub 仓库： [https://github.com/Orenoid/BabelDuck](https://github.com/Orenoid/BabelDuck)  
在线 Demo：[BabelDuck](https://duck.orenoid.com)

嫌太长不看的朋友可以直接体验下，应用内置了一个简单的教程，来说明为什么更合适刚入门英语口语练习的人。  
（ P.S. 目前还是 MVP 版本，易用性方面后续会继续打磨，有问题可以提 issue ）

### 一些截图

![overall](https://i.v2ex.co/2Ru6h7JWl.png) ![follow-up](https://i.v2ex.co/70ug293pl.png)

### 这个应用尝试解决什么痛点？

虽然 GitHub 上已经有不少开源的对话练习应用了，但我之前在尝试用它们练习的时候，遇到了一个问题：  
我口语太菜了，很多时候上来就直接卡壳，嘴巴一张半天嘣不出几个词，或者磕磕巴巴地说完了但也不知道这么表达对不对，尝试过在 prompt 里让 AI 帮忙分析和纠正我的问题，但很多时候对话一长，AI 就老忘了这事儿，或者开始说车轱辘话，不好使。  
结果就是练习过程特别不流畅，还经常得停下来切出去查东西，体验非常糟糕。

所以我决定开发一个功能定位略有不同的 AI 口语应用，在 BabelDuck 引入了快捷指令的功能，由另外一个 AI 专门负责协助你的口语表达，直接翻译、语法纠正、表达润色之类的都能做，而且如果对它提供的结果有疑问的话，还可以开启子对话，进一步讨论语法表达问题，并且不影响当前对话。  
更重要的是，你可以完全根据自身需求自定义指令，比如：

- 模拟面试中遇到不会或者不知道英语咋回答的，直接让 AI 示范回答一遍
- 假如你的英文水平还行，但偶尔有些术语想不起来，可以夹杂一两个中文单词，然后让 AI 替换成英文
- 让 AI 为你提供一组等效的表达，扩充词汇、短语积累
- ……

### 应用还有哪些功能

除了上面介绍的，常规的 AI ChatBot 应用的功能也是有的，例如对话管理、语音输入、语音输出、LLM 服务切换等等。 目前尚处于 MVP 阶段，有些功能还需要打磨，后续会继续完善。

### 未来规划

接下来打算更新的功能（不一定按这个顺序）：

- 对话模板  
    类似于其他 ChatBot 的 Copilot ，但是可配置程度更高，除了 system prompt ，可以预设一段前置对话，可以给每个模板设置使用不同的模型、语音、音色、快捷指令等等。
- 接入更多 LLM/TTS/STT 服务  
    因为是 MVP 版，目前其实只内置支持了一小部分平台，后面继续接入更多服务，比如 Azure STT, Google Gemini 等等
- 复述练习模式  
    让用户可以在 AI 给出修改后的回复后，练习复述，增强记忆效果
- 语音回放  
    现在只是单纯地把语音转成文本，后续会把音频存起来，支持回放自己的语音（如果有合适的模型，没准还可以做发音分析和纠正）
- 支持多模态语音  
    目前的对话实现都是基于 TTS 和 STT ，目前已经陆续有一些开源或闭源模型支持端到端语音消息了，会尝试接入这类模型。
- 实时语音模式  
    就是 OpenAI 推出的那个 Realtime API ，这个优先级不高的原因是：1.太贵了，目前估计没太多人会用； 2.口语能流畅到跟 AI 实时对话的大佬，可能看不上我这个产品。所以，会接入这个模式，但优先级暂时靠后，视用户反馈而定。
- 更多指令类型
- 插件系统

### 其他

这里得道个歉，标题里的“开源”其实是不太严谨的说法，这个项目的 License 其实是限制商业用途的（所以不符合严格意义上的开源定义），但个人可以免费使用和修改，99% 的人应该都不受影响。  
总的来讲源代码是开放的，只是不符合狭义上的开源定义，为了挑选这个 License 还花了一些时间去调研，回头另外开贴讲下，之前在站内搜索也有看到有人在找这种 License 。


21 条回复  **•**  2024-12-12 14:45:54 +08:00

|   |   |   |
|---|---|---|
|![Maxbee](https://cdn.v2ex.com/avatar/a8e9/4d83/131125_normal.png?m=1730090243)||1<br><br>**[Maxbee](/member/Maxbee)**  <br><br>   61 天前<br><br>有 app 版就好了|

|   |   |   |
|---|---|---|
|![Orenoid](https://cdn.v2ex.com/avatar/b124/3b35/225606_normal.png?m=1733717729)||2<br><br>**[Orenoid](/member/Orenoid)**  <br><br>OP<br><br>   61 天前<br><br>@[Maxbee](/member/Maxbee) 后续会做移动端适配|

|   |   |   |
|---|---|---|
|![vsitebon](https://cdn.v2ex.com/avatar/f358/8cc3/363007_normal.png?m=1556063713)||3<br><br>**[vsitebon](/member/vsitebon)**  <br><br>   61 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>看着很不错|

|   |   |   |
|---|---|---|
|![ala2008](https://cdn.v2ex.com/gravatar/1180dc5117a3cdead26c10fed41ce710?s=48&d=retro)||4<br><br>**[ala2008](/member/ala2008)**  <br><br>   61 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>网站做的不错|

|   |   |   |
|---|---|---|
|![cookii](https://cdn.v2ex.com/gravatar/bd8eeaeedf8cbaa34943b72060b0f932?s=48&d=retro)||5<br><br>**[cookii](/member/cookii)**  <br><br>   61 天前<br><br>目前正在学习英语，回去试用一下 [![](https://i.imgur.com/xr1UOz1.png)](https://i.imgur.com/xr1UOz1.png)|

|   |   |   |
|---|---|---|
|![zjh7890](https://cdn.v2ex.com/gravatar/e61560cf4431281269d0a5fc6811ee62?s=48&d=retro)||6<br><br>**[zjh7890](/member/zjh7890)**  <br><br>   61 天前<br><br>ChatGPT 的语音模式不是已经很好用了吗？跟他说学啥场景，语速也可以调节。|

|   |   |   |
|---|---|---|
|![Orenoid](https://cdn.v2ex.com/avatar/b124/3b35/225606_normal.png?m=1733717729)||7<br><br>**[Orenoid](/member/Orenoid)**  <br><br>OP<br><br>   61 天前<br><br>@[zjh7890](/member/zjh7890) 功能定位不一样，这个主打的差异点在于辅助对话，提供很多对话之外的即时反馈，例如语法、表达等等，很多人的口语水平不足以跟 AI 形成有效的对话（比如我）|

|   |   |   |
|---|---|---|
|![Orenoid](https://cdn.v2ex.com/avatar/b124/3b35/225606_normal.png?m=1733717729)||8<br><br>**[Orenoid](/member/Orenoid)**  <br><br>OP<br><br>   61 天前<br><br>@[zjh7890](/member/zjh7890) 当然你说的这个场景练习 BabelDuck 也是能覆盖的|

|   |   |   |
|---|---|---|
|![luckycoding](https://cdn.v2ex.com/avatar/d51b/c9af/396792_normal.png?m=1712061781)||9<br><br>**[luckycoding](/member/luckycoding)**  <br><br>   61 天前<br><br>👍对于本菜鸡非常友好哈哈哈|

|   |   |   |
|---|---|---|
|![Orenoid](https://cdn.v2ex.com/avatar/b124/3b35/225606_normal.png?m=1733717729)||10<br><br>**[Orenoid](/member/Orenoid)**  <br><br>OP<br><br>   61 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>@[luckycoding](/member/luckycoding) 主要是我是真的在练习时，发现有这些痛点才开发的 😂 所以我猜应该有人有同样的需求|

|   |   |   |
|---|---|---|
|![lrh3321](https://cdn.v2ex.com/avatar/4be5/3cd1/144075_normal.png?m=1731230902)||11<br><br>**[lrh3321](/member/lrh3321)**  <br><br>   60 天前<br><br>👍有想法|

|   |   |   |
|---|---|---|
|![m502002313](https://cdn.v2ex.com/gravatar/92bbef49301043f9737c3524cde82aaf?s=48&d=retro)||12<br><br>**[m502002313](/member/m502002313)**  <br><br>   60 天前<br><br>@[zjh7890](/member/zjh7890) 是的 我平时都用 高级语音练习|

|   |   |   |
|---|---|---|
|![zzgo88](https://cdn.v2ex.com/gravatar/a07c4e1dc0d294d0765d01b1f4252ff7?s=48&d=retro)||13<br><br>**[zzgo88](/member/zzgo88)**  <br><br>   60 天前<br><br>非常棒，现在能用 Ollama 吧？|

|   |   |   |
|---|---|---|
|![Orenoid](https://cdn.v2ex.com/avatar/b124/3b35/225606_normal.png?m=1733717729)||14<br><br>**[Orenoid](/member/Orenoid)**  <br><br>OP<br><br>   60 天前<br><br>@[zzgo88](/member/zzgo88) 可以在 "设置 -> 模型" 里选择添加服务，可以添加兼容 OpenAI APi 格式的服务，然后在对话设置里切换对话模型服务，我记得 Ollama 是兼容 OpenAI API 的。|

|   |   |   |
|---|---|---|
|![zzzlll](https://cdn.v2ex.com/avatar/54dd/4e3b/372213_normal.png?m=1729822365)||15<br><br>**[zzzlll](/member/zzzlll)**  <br><br>   60 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>口语差的人很能明白 OP 的想法，狠狠点赞|

|   |   |   |
|---|---|---|
|![yuxian](https://cdn.v2ex.com/avatar/de4f/7ef0/464595_normal.png?m=1597214371)||16<br><br>**[yuxian](/member/yuxian)**  <br><br>   59 天前<br><br>目前还没有接入实时语音？|

|   |   |   |
|---|---|---|
|![coreki](https://cdn.v2ex.com/gravatar/950d490140eb13fd8579b8fb95470b73?s=48&d=retro)||17<br><br>**[coreki](/member/coreki)**  <br><br>   59 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>试用了一下,还不错|

|   |   |   |
|---|---|---|
|![Orenoid](https://cdn.v2ex.com/avatar/b124/3b35/225606_normal.png?m=1733717729)||18<br><br>**[Orenoid](/member/Orenoid)**  <br><br>OP<br><br>   59 天前<br><br>@[yuxian](/member/yuxian) 后续会接入，已经在路线图里了|

|   |   |   |
|---|---|---|
|![gorgeousGeorge](https://cdn.v2ex.com/gravatar/3b5fb6d86fa70880fd3e526e45a67c43?s=48&d=retro)||19<br><br>**[gorgeousGeorge](/member/gorgeousGeorge)**  <br><br>   59 天前<br><br>你好，我用了一下，很不错。但是有个奇怪的 bug ，我还以为是我键盘的问题——在输入 have 这个单词的时候，输入框里面老是打出 haev ，基本是必现的。  <br>@[Orenoid](/member/Orenoid)|

|   |   |   |
|---|---|---|
|![Orenoid](https://cdn.v2ex.com/avatar/b124/3b35/225606_normal.png?m=1733717729)||20<br><br>**[Orenoid](/member/Orenoid)**  <br><br>OP<br><br>   59 天前<br><br>@[gorgeousGeorge](/member/gorgeousGeorge) 感谢反馈，已修复。|

|   |   |   |
|---|---|---|
|![NeedforV2](https://cdn.v2ex.com/gravatar/96e1b7ecba71413584d53fa6df735c6a?s=48&d=retro)||21<br><br>**[NeedforV2](/member/NeedforV2)**  <br><br>   58 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>挺不错的，支持一下|
