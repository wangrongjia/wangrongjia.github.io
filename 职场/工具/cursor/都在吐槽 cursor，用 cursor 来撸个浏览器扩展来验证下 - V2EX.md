---
link: https://www.v2ex.com/t/1102994
site: V2EX
date: 2025-01-06T18:59
excerpt: 程序员 - @pizone - 本人产品狗一枚，趁着都在讨论 cursor ，也做个浏览器扩展来玩玩，顺便分享下 cursor
  使用心得。本人不能说对技术完全没了解，毕竟经常跟开发大佬打交道略有耳闻一些术语，本次使用了 cursor
twitter: https://twitter.com/@V2EX
slurped: 2025-02-05T17:07
title: 都在吐槽 cursor，用 cursor 来撸个浏览器扩展来验证下 - V2EX
---

本人产品狗一枚，趁着都在讨论 cursor ，也做个浏览器扩展来玩玩，顺便分享下 cursor 使用心得。本人不能说对技术完全没了解，毕竟经常跟开发大佬打交道略有耳闻一些术语，本次使用了 cursor 来生成了一 rss 订阅浏览器扩展 rssflow ，代码纯 cursor 生成、除了一些配置信息手动修改外,经过两次重构和性能优化，历时一个月 [rssflow](https://rssflow.oinchain.com/)最终完成了 Edge 和 Chrome 扩展的上架。[https://rssflow.oinchain.com/](https://rssflow.oinchain.com/)

### 开发初衷

项目启动其实挺随意。偶然在抖音上刷到用 Cursor 几分钟撸了个浏览器扩展的视频，而我本身是 RSS 订阅的拥趸，但不太喜欢安装对于的订阅 App 或桌面软件，我需要一个随手就用，用完就走的订阅工具。再加上 Google Gemini 有免费的 API ，国内的 Deepseek 和 Siliconflow 性价比也很高，所以就打算手搓一个具备 RSS 订阅和 AI 摘要功能的扩展的想法了：

一款 RSS 浏览器扩展，不需要账号登录、即装即用，把未读文章的消除以一种解压的方式来呈现, 具备 RSS 的阅读器的基本功能，同时具备 AI 摘要功能。

### 开发过程-万事开头难

把这个粗略的想法，问 chatgpt ，让他分析这个目标在浏览器扩展上技术可行性，让它结合最佳实践给出具体的技术方案，拷贝到 txt 文本上，然后所有的项目都基于这个 txt 文本开始。 让 cursor 先理解这个技术方案，让 cursor 把最简要的文件结构搭建起来，可以使用 composer 模式让他自动创建文件。 要求 cursor 以最简单能跑通流程方式来逐步迭代实现，比如：首先要求其验证 rss-parser.js 解析 rss 在扩展上的技术方案是否可行，要求跑通 RSS 订阅和显示订阅内容为目标，开始不要考虑各种边边角角的问题，只要这个最简单的流程能跑起来即可，万事开头难，只要项目能跑起来，慢慢就把积木搭起来了。整个 cursor 开发的过程接近 1 个月，最主要是 css 代码和某个文件超过 2000 行，导致代码经常抽风，再加上摸索使用 cursor 浪费大量时间。

### Cursor 使用心得

折腾完这个项目，简单分享一些个人经验：

1. **万事开头难，先从简单的跑通流程开始。**
    - 不要一开始就要求实现一个很完整的大功能。
    - Cursor 可能会抽风，出现大量错误，难以定位和修复，这对于不懂代码的人来说是灾难。
2. **只有初步想法，怎么开始。**
    - 可以问 ChatGPT 、Claude 或 Gemini ，汇总后得出大致的落地技术方案。
    - AI 阅读的代码量远超人类，要求它以最佳实践方案考虑设计，它给的会比你预想的多很多。
    - 这种场景下如果有款 AI 产品可以实现模型自动互提问题、互相回答、讨论确定最终技术方案，那就更好了。
3. **根据项目特点配置 Cursor 的 Rules for AI 。**
    - 直接描述你的项目和场景需求，让 AI 生成对应的提示词。
    - AI 比你更懂如何写 Prompt ，没必要花太多时间研究 Prompt 框架。
    - 也可以直接到 [cursor.directory](https://cursor.directory/) 上找适合项目的技术栈的提示词。
4. **解决 Cursor 上下文不足和不时抽风问题：**
    - **无法根治：** 只能及早发现，及时治疗（回滚代码）。
    - **单文件代码量：** Cursor 在单文件 1000 多行代码时处理起来还算游刃有余，超过 2000 行或接近时，抽风概率会很大，最好尽早拆分功能。
    - **拆分过细，解决抽风问题？** 上下文长度是硬伤，分拆太细，它后面可能会忘记，导致重复实现。
    - **善用 Git：** 如果一个小问题，改了一堆代码，同时错误没有减少反而增加，大概率在抽风。
    - **分支开发：** 在做复杂功能前，最好创建一个分支，通过 Git 更细粒度地控制版本，因为这个复杂功能有很大概率会失败，通过 git 来更细的控制版本，让代码变得可控，比如我做多语言适配模型回复语言和播客功能就改了很长时间，把原有代码都改乱了，就差问候 cursor 全家了，这个需要点耐心。
5. **防止 Cursor 修改正常代码逻辑：**
    - **提示词限制：** 在提示词中加入限定，如：`每次按指令执行代码建议，不能对与本次指令无关的代码逻辑和功能进行修改`。
    - **Composer 对话：** 对话太长，建议新开窗口。 一直在一个对话窗口的好处是有足够的上下文，不好的地方恰恰是知道太多了，历史对话中包含多个功能的改动，cursor 有时会不知所措。
    - **功能迭代：** 开始新功能或迭代时，建议新开窗口，先 `@codebase`，让 Cursor 熟悉代码，要求重点关注接下来要迭代的功能和代码逻辑，然后再开始提你的迭代需求。
6. **避免 Cursor 过度设计：**
    - AI 的优势是看过太多代码，知道各种最佳实践，但往往引入太多复杂设计，不利于实现和功能迭代。
    - 遇到这种情况，回到“万事开头难”的观点，先要求跑通流程，它出的方案先复制下来，等流程跑通了，再让他回过头评估可以做哪些优化，哪些是最要紧的。
7. **界面设计：**
    - 这的确是一个难题，我也在摸索，起初我是画了个简单的原型，上传图片让他来实现。后面我是直接上网找了一些设计稿，让他照着来，其实都不是太理想。
    - 后面实在没办法，直接一顿猛夸 cursor ，把所有在设计师方面的赞美词都用上，让他基于当前代码功能大胆放开设计，陆续设计了十几个版本的界面，以量取胜，选了一个可以接收的。

### 结论

实践完后整体体会是，把 cursor 吹上天也是可以的，虽然 Cursor 还没有到替代程序员的阶段，但是这波趋势会挤压程序员的生存空间，其实不单单是程序员，生产力提高太快的情况下，整个互联网链条上的岗位都会被挤压（ cursor 也可以用来写需求、做运营方案，各种你意想不到都可以在 cursor 上来实现）。Cursor 只是工具，具体如何使用取决于你，还是要尽快拥抱变化。它目前非常适合实现简单的逻辑和页面，所见即所得的开发方式的确是个最佳的选择。如果你略懂开发流程和功能迭代思路，即使是零代码基础的人也可以做出一些复杂功能的应用出来，关键看有没有产品意识。其实是利好有产品意识的开发的，或者有些开发常识的零代码基础的个人。

粗略观点，抛砖引玉了。现在 cursor 还可以免费试用，以个人经验来看，想要完全依靠 cursor 来生成中小规模的应用，每个月 250 次是远远不够用的，起码得消耗个六七个账号的额度。大家趁严格限制之前多玩一玩。

|   |   |   |
|---|---|---|
|![wuhunyu](https://cdn.v2ex.com/avatar/c2dc/24ad/710616_normal.png?m=1728192540)||1<br><br>**[wuhunyu](https://www.v2ex.com/member/wuhunyu)**      29 天前<br><br>我遇到一个问题是，我在发起一个堆的提问之后，发现之前的一个提问是我发出的指令有问题，这个时候如果我再发起一个撤回提问往往都是无法达到我想要的撤回效果的。也就是说，我以为的撤回是把之前的一个操作剔除掉，但 ai 的操作往往是通过增量动作去尝试到达我要的撤回效果|

|   |   |   |
|---|---|---|
|![mumbler](https://cdn.v2ex.com/gravatar/53e87c11a8aa9c21ad440f5b5eacdba9?s=48&d=retro)||2<br><br>**[mumbler](https://www.v2ex.com/member/mumbler)**      29 天前<br><br>@[wuhunyu](https://www.v2ex.com/member/wuhunyu) cursor 的每次交互之前都会存一个 checkpoint ，点击 restore ，可以回到任意一次交互之前的状态，别用嘴跟他说退回上一个版本，而是点 restore 回去更可靠|

|   |   |   |
|---|---|---|
|![pizone](https://cdn.v2ex.com/gravatar/28c456b150686e515cdf21cc273f7dab?s=48&d=retro)||3<br><br>**[pizone](https://www.v2ex.com/member/pizone)**      29 天前<br><br>@[wuhunyu](https://www.v2ex.com/member/wuhunyu) 每次更改，对应文件的变更记录都会在时间线上看到，找到你想要回到的版本，还原一下内容就可以了。 功能改完，验证没问题，就 git 保存一下，养成一下这个习惯，对于 cursor 来说比较重要。|

|   |   |   |
|---|---|---|
|![layxy](https://cdn.v2ex.com/gravatar/57b94f7f153f3745286c0b8db7131786?s=48&d=retro)||4<br><br>**[layxy](https://www.v2ex.com/member/layxy)**      29 天前<br><br>搁着吹 cursor 都是扯淡,实际体验写个逻辑反反复复纠错,问题也是反反复复,他只是个辅助工具,简单的通用逻辑写起来还算可以,但是一旦逻辑链路太长,啥都记不住|

|   |   |   |
|---|---|---|
|![pizone](https://cdn.v2ex.com/gravatar/28c456b150686e515cdf21cc273f7dab?s=48&d=retro)||6<br><br>**[pizone](https://www.v2ex.com/member/pizone)**      29 天前<br><br>@[layxy](https://www.v2ex.com/member/layxy) 提示词上增加些描述，让他加入思维链的方式思考。其实最好的方式是自己略微看得懂代码，如果逻辑很清晰的话，复杂逻辑也是可以执行的。也可以引导它一步步来实现，比如先让他输出数据流程，不要进行代码建议。  <br>想办法让他一步步严谨的思考。  <br>## Methodology  <br>1.**System 2 Thinking**: 用分析严谨性来解决问题。将需求分解成更小、更易于管理的部分，并在实施之前彻底考虑每个步骤。  <br>2.**Tree of Thoughts**: 评估多个可能的解决方案及其后果。使用结构化方法来探索不同的路径并选择最佳路径。  <br>3.**Iterative Refinement**: 在最终确定代码之前，考虑改进、边缘情况和优化。通过潜在的增强功能进行迭代，以确保最终解决方案是健壮的。  <br>**Process**:  <br>1)**Deep Dive Analysis**: 从对当前任务进行彻底分析开始，考虑技术要求和限制;  <br>2)**Planning**: 制定一个明确的计划，概述解决方案的架构结构和流程，必要时使用 <PLANNING> 标签;  <br>3)**Implementation**: 逐步实施解决方案，确保每个部分都符合指定的最佳实践;  <br>4)**Review and Optimize**: 对代码进行审查，寻找潜在的优化和改进领域;  <br>5)**Finalization**: 通过确保代码满足所有要求、安全且性能良好来最终确定代码;|

|   |   |   |
|---|---|---|
|![zzsqwq](https://cdn.v2ex.com/avatar/6546/e347/557640_normal.png?m=1736220767)||8<br><br>**[zzsqwq](https://www.v2ex.com/member/zzsqwq)**      29 天前<br><br>想问下 OP 的这个产品介绍的网页是怎么做的？|

|   |   |   |
|---|---|---|
|![pizone](https://cdn.v2ex.com/gravatar/28c456b150686e515cdf21cc273f7dab?s=48&d=retro)||9<br><br>**[pizone](https://www.v2ex.com/member/pizone)**      29 天前   ![❤️](https://www.v2ex.com/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>@[zzsqwq](https://www.v2ex.com/member/zzsqwq) 也是用 cursor 来实现啊，让 cursor 更新一下项目的 readme ，不满意的话，你可以在这个基础上修改一下描述。 再找一个类似的网站，让 cursor 照着结构实现一遍，文案从 readme 中抽取，然后你让设计个你喜欢的风格或主题色，最后优化下文案差不多就行了。|

|   |   |   |
|---|---|---|
|![27149](https://cdn.v2ex.com/gravatar/1effc6e6d7eff243eacbb1b8f81d325a?s=48&d=retro)||10<br><br>**[27149](https://www.v2ex.com/member/27149)**      29 天前<br><br>巧了，也是产品狗，上周知道了 cursor 之后，也是写了个 chrome 扩展。我的需求和你不一样，我是要挂课。我的需求是，在一个网页，实现自动播放、状态检查、播放下一个视频，但由于各种按钮、状态并不是在 HTML 元素里，而是多层 iframe 嵌套，而且还有 CSP 的问题，对于完全没有前端知识和代码知识的我，找解法非常费劲。<br><br>cursor 在用起来其实有非常几个致命的问题，除了你前面提到的乱改代码外，还容易丢上下文、0 帧起手上来就改代码，而不是在控制台调试，寻找可行性方案。<br><br>我用了 3 天，大概 400 次调用，连第一个需求实现自动播放都没有实现…<br><br>后来换了 windsurf ，这个 10 分钟就解决了自动播放的问题，又花了一个周末，实现了后面两个需求，今天完全堪用了（虽然调试信息报的乱七八糟）。<br><br>有点不理解，windsurf 和 cursor 调用的都是 claude3.5 ，怎么差距这么大…|

|   |   |   |
|---|---|---|
|![pizone](https://cdn.v2ex.com/gravatar/28c456b150686e515cdf21cc273f7dab?s=48&d=retro)||12<br><br>**[pizone](https://www.v2ex.com/member/pizone)**      29 天前<br><br>@[27149](https://www.v2ex.com/member/27149) windsurf 我也使用过，不过我是用来写一些 tradingview 的指标，也写了挺多个了，也觉得挺好的。我感觉没有很大的区别，可能一个是手动挡一个是自动挡吧。我个人觉得 cursor 用来实现复杂的逻辑回避 windsurf 好一些，windsurf 更不可控一些。  <br>针对很简单问题，cursor 直接用 chat 模式就可以了，不需要使用到 composer 。就比如这个扩展中有个 TTS 功能，接的是 azure 的服务，还有一个后端的激活码验证功能，这些都是用 chat 模式来迭代的。一个很简单的问题，其实如果五六轮都没有解决，就不用再问下去了，直接新开个窗口，重新把问题说清楚，先让他熟悉代码，然后然让他分析问题，不断问它细节问题，问的差不多了，再让他开始进行代码建议，完成修复。|

|   |   |   |
|---|---|---|
|![prettybot](https://cdn.v2ex.com/gravatar/b76cf69d31f512a28be6354a367132b5?s=48&d=retro)||13<br><br>**[prettybot](https://www.v2ex.com/member/prettybot)**      29 天前<br><br>@[27149](https://www.v2ex.com/member/27149)  <br>我举我的一个例子<br><br>我是后端，前端代码基本能看懂，写起来手生  <br>最近我用 cursor 写前端，本着偷懒目的，不 review code ，只看网页效果。  <br>我发现简单 CURD 页面还行，稍微复杂点的页面，使用纯自然语言和它交互就非常费劲。但是如果我在它的代码基础上，用程序员的思维和它交流，把问题细化，比如哪个 div ，哪里的 js 逻辑可疑，哪里的样式需要调整，它就非常好用。<br><br>大模型的 coding 能力是没问题的，难的是让模型理解你要做什么。之前我们在对着人讲需求，现在我们在对着 AI 讲需求，我想表达方式应该是有一些差异的。<br><br>于是我有一些感悟，目前来说，cursor 也只是副驾驶，助手。  <br>你需要懂一些基本的代码尝试，纯自然语言交流目前很困难，就如同你讲的  <br>> 400 次调用，连第一个需求实现自动播放都没有实现<br><br>windsurf 我还没用过，不过也是存疑的。  <br>> 调试信息报的乱七八糟|

|   |   |   |
|---|---|---|
|![Chuckle](https://cdn.v2ex.com/avatar/0b33/4c86/604103_normal.png?m=1721878010)||14<br><br>**[Chuckle](https://www.v2ex.com/member/Chuckle)**      29 天前   ![❤️](https://www.v2ex.com/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 2<br><br>[![](https://i.imgur.com/agAJ0Rd.png)](https://i.imgur.com/agAJ0Rd.png)让 ai 自己写项目，就是老蒋模拟器，刚开始指挥 ai ，优势在我，想好几句思路让 ai 实现就行，后面 ai 写的"优雅的"shi 山堆起来了，人不想看，ai 上下文记不住，自己描述“思路”也和写小作文一样，更别说生产项目各种魔改框架、特殊语法、封装包、多工程了，马上就变成踢一脚走一下的 ai ，微操的人不红温挑战。现在更多是让 ai 梳理一遍知识再给我用，比如某个 api 用法、原理之类的，这个确实省心，省得翻文档网页。但我不看好现在这种堆提示词的 ai 写代码服务，上限就在那，但它确实大大降低了指挥计算机干活的门槛。|

|   |   |   |
|---|---|---|
|![suke119](https://cdn.v2ex.com/avatar/e3c5/b261/606399_normal.png?m=1670897845)||15<br><br>**[suke119](https://www.v2ex.com/member/suke119)**      29 天前<br><br>现在的产品都这么牛的嘛？不懂代码 咋知道 Cursor 修改之前代码的正确性还有各种其他代码问题的，看这流程都比专业的程序员都专业了（懂代码的话当我没说）|

|   |   |   |
|---|---|---|
|![aikilan](https://cdn.v2ex.com/gravatar/4877b680fe44aba64b22c5c8bd136aca?s=48&d=retro)||16<br><br>**[aikilan](https://www.v2ex.com/member/aikilan)**      29 天前<br><br>看完描述，给我一种儿童拿着容易擦枪走火的自动步枪在森林里打猎的感觉，没啥贬义，就是一种感觉|

|   |   |   |
|---|---|---|
|![zhady009](https://cdn.v2ex.com/gravatar/d95f7fc49a312f6a2c2671f9a63f04ea?s=48&d=retro)||17<br><br>**[zhady009](https://www.v2ex.com/member/zhady009)**      29 天前<br><br>chrome 扩展一年前用 copilot 就写过了，只是没自动创建文件之类的交互，这类项目都比较简单|

|   |   |   |
|---|---|---|
|![pizone](https://cdn.v2ex.com/gravatar/28c456b150686e515cdf21cc273f7dab?s=48&d=retro)||18<br><br>**[pizone](https://www.v2ex.com/member/pizone)**      29 天前<br><br>@[suke119](https://www.v2ex.com/member/suke119) 真不懂代码，这东西用多了就差不多，多试错就能总结出来了。每段代码 cursor 写的代码都会有注释，看注释就行，执行完，让 cursor 检查自己写的代码是否完整和健壮，不能重复和冲突，并检查是否有冗余的代码和逻辑。|

|   |   |   |
|---|---|---|
|![pizone](https://cdn.v2ex.com/gravatar/28c456b150686e515cdf21cc273f7dab?s=48&d=retro)||19<br><br>**[pizone](https://www.v2ex.com/member/pizone)**      29 天前<br><br>@[aikilan](https://www.v2ex.com/member/aikilan) 哈哈，的确有点这个意思。好就好在 cursor 写的代码，提示词里都要求写注释，看看注释就知道大概的逻辑了（其实他的逻辑本来就是根据我的需求来实现的，看符不符合需求就行了）。比如想更进一步提高可控性，就让 cursor 每次建议完，自己审视自己的代码，告诉他要求就行了，比如：保证逻辑清晰、高效，不能跟其它方法冲突、不能有冗余的代码。|

|   |   |   |
|---|---|---|
|![pizone](https://cdn.v2ex.com/gravatar/28c456b150686e515cdf21cc273f7dab?s=48&d=retro)||20<br><br>**[pizone](https://www.v2ex.com/member/pizone)**      29 天前<br><br>@[zhady009](https://www.v2ex.com/member/zhady009) 扩展有简单有复杂的，我这个相对复杂些，也是想验证下实现一些相对复杂的功能，对于没有代码基础的人来说，cursor 能不能胜任，算是一个验证测试吧。|

|   |   |   |
|---|---|---|
|![Zzzz77](https://cdn.v2ex.com/avatar/5ae2/3685/528185_normal.png?m=1656335441)||21<br><br>**[Zzzz77](https://www.v2ex.com/member/Zzzz77)**      29 天前<br><br>> 功能改完，验证没问题，就 git 保存一下<br><br>事实上你别说是不懂代码，哪怕是水平较低，你都验证不了有没有问题。<br><br>这是典型非开发的思维，通过鼠标点一点看看是否符合预期，以此判断有没有 bug ，这完全是扯淡，很多边界条件不是普通人随便试试能试出来的。<br><br>当然这种现状在 AI 之前也有，见过很多刚入门的程序员写代码靠猜的，代码逻辑去网上东抄一点西抄一点，自己不理解逻辑，运行起来简单试几下符合预期就行。真遇到 bug 了再去针对 bug 打补丁，很多屎山就是这么来的....|

|   |   |   |
|---|---|---|
|![pizone](https://cdn.v2ex.com/gravatar/28c456b150686e515cdf21cc273f7dab?s=48&d=retro)||22<br><br>**[pizone](https://www.v2ex.com/member/pizone)**      29 天前<br><br>@[Zzzz77](https://www.v2ex.com/member/Zzzz77) 这东西限于篇幅也说不了太细。你告诉 cursor 我需要验证功能是否符合需求，他就会给出一些解决方案了，按照他的建议执行就行了，他会在关键节点加上日志，看看日志数据，再结合界面上点击点击，就差不多了验证完了。其实如果你还想更细验证也可以的，你让他输出某个功能完整的调用链路，要求说明清楚每个方法的作用和调用顺序，包括数据流程。 他立马就能输出出来了。|

|   |   |   |
|---|---|---|
|![suke119](https://cdn.v2ex.com/avatar/e3c5/b261/606399_normal.png?m=1670897845)||23<br><br>**[suke119](https://www.v2ex.com/member/suke119)**      29 天前<br><br>@[pizone](https://www.v2ex.com/member/pizone) 我从 23 年 5 月 用到至今，他们产品迭代了 n 个版本了，我可是一直用的，如图  <br>[![](app://i.v2ex.co/33w23AcK.jpeg)](https://www.v2ex.com/i/33w23AcK.jpeg "在新窗口打开图片 33w23AcK.jpeg") 从 23 年我就开始推荐给身边很多人了；对于不会编程的人 可不会了解这么多编程上的细节|

|   |   |   |
|---|---|---|
|![pizone](https://cdn.v2ex.com/gravatar/28c456b150686e515cdf21cc273f7dab?s=48&d=retro)||24<br><br>**[pizone](https://www.v2ex.com/member/pizone)**      29 天前<br><br>@[suke119](https://www.v2ex.com/member/suke119) 嗯，我也挺早就听说了，不过一直没用。只是看到老是在吹 cursor ，其实也挺烦的，但是又看不到这些人使用纯 cursor 搞个完整的有前后端的项目出来给大家看看，给大家打个样，老是说做了很多小工具，小脚本之类的这些简单，没啥参考价值，其实也证明不了 cursor 有多神。同时让一些没有代码基础，但是又想用实践下搞点小工具的大概有个概念，使用 cursor ，可以完成复杂度能到到什么程度的项目，如果你的复杂度在我这个之下，完全是可以满足的，可以大胆的付出行动，赶紧实践做出来，大概是这么个意思。|