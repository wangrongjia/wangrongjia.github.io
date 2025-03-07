---
link: https://www.v2ex.com/t/1102252
site: V2EX
date: 2025-01-03T11:40
excerpt: 奇思妙想 - @heirtheloong - 需求大概如此：投入文档后，AI 根据文档回答问题，尽量准确全面。随着 AI
  发展，出现很多知识库问答工具，但我试用后发现不如人意，拿来做客服或者公司的问答机器人还行，能糊弄一下，可真要投些需要
twitter: https://twitter.com/@V2EX
slurped: 2025-02-05T14:16
title: 求推荐一个可靠的 AI 知识库 - V2EX
---

需求大概如此：投入文档后，AI 根据文档回答问题，尽量准确全面。

随着 AI 发展，出现很多知识库问答工具，但我试用后发现不如人意，拿来做客服或者公司的问答机器人还行，能糊弄一下，可真要投些需要上下文关联回答的问题，不是找不到就是乱说。

我真的很希望有这么一款工具，哪怕付费，能根据我的知识库给出准确回答，可看做一个加强的搜索引擎，因为写的东西多了，收集的资料多了，后面只有一个印象时再找真的很费时间。如果能用 AI 解决，那会省很多时间。

再比如读书，很多书没必要细读，只是工具书一类，如果也能丢进去提问，让 AI 指出页面，那能省很多时间。

可我试用了[ChatDOC](https://chatdoc.com/)、[ChatPDF](https://www.chatpdf.com/)、[Humata](https://www.humata.ai/)这些工具，都不如人意，AI 的水平还只是机械的找关键词，稍微要些上下文的就不行。一些国内的服务则更差，开源的几个工具也相差无几。还是停留在淘宝 AI 客服类型人的那种水平。

上面三个服务中最好的是 ChatDOC ，我丢了一篇《风云・惊世少年》第一章，然后提问，一些问题确实能给出答案，但一些问题找不到，还有些根本就是错的。这种提问不像拿 AI 编程，编程可以反复试，一点点调试，这确实省了时间，可提问得到的答案如果错了，写进文章是要被人骂的。如果用于更严谨的领域显然也不可靠。

我想知道，是我没找到正确的工具，还是我没用用好已有的工具，还是说 AI 的水平根本就这样。

ChatDOC 测试如下：

**聂人王用的是什么武器？**

聂人王使用的武器是名为“雪饮”的宝刀。这把刀被描绘得华丽而沉重，是他昔日的骄傲与象征，但在故事中，它却被遗弃在暗室中，暗示着聂人王的衰落和他所经历的种种变故。

**简单介绍一下雪饮**

雪饮是一柄不平凡的宝刀，刀长三尺七寸，锋刃无瑕，其外观曾显赫一时，能够斩下无数高手的头颅。然而，如今的雪饮却积满了尘垢，被随意挂于阴暗的一角，周围则是一些普通的农具，展现出其昔日光辉的消逝[1]。这柄刀不仅是武器，更承载着聂人王家族的荣光与困扰，象征着曾经的辉煌与现今的落魄[6]。对于聂风来说，尽管他还小，但对这把刀的力量充满了好奇，渴望能够像父亲一样掌握它[1]。

**聂大嫂是谁？**

聂大嫂是聂风的母亲，名叫颜盈。她是一位美丽的女性，文中描述她有着令人惊艳的外貌，并且在家庭生活中承受着对过去辉煌时光的怀念与对现状的不满。在文章中，她表现出对丈夫聂人王的失望，并通过做家务来抒发内心的怨恨和不满。

**断帅用的是什么武器？**

根据文档内容，断帅所用的武器是剑。文中提到他是“南麟剑首”，这表明他精通剑术，并且在多个段落中提到了他的剑术修为及对对手的挑战。

**火麟剑是谁的武器？**

火麟剑是聂人王的武器。在文中提到，聂人王是曾经叱诧一时的天下第一刀客，火麟剑作为他的武器，象征着他曾经的辉煌和武林地位。

**那你为什么之前说聂人王用的是雪饮刀？**

文中提到聂人王是“北饮狂刀”，而雪饮是他的宝刀。雪饮刀在文中被描绘为一柄绝世的宝刀，与聂人王的身份和过去的辉煌密切相关[1]。同时，雪饮除了是聂人王的武器，也是其家族荣光的象征，承载着过往的辉煌和现状的困扰。因此，提到聂人王时，自然会提到他使用的雪饮刀。

**火麟剑到底是谁的武器？**

在文中并没有直接提到“火麟剑”的具体信息和归属，然而提到了一个名叫“断帅”的角色，他是南麟剑首，修为极高，对聂人王的到来感到喜悦。不管是“火麟剑”还是“南麟剑”，文中并没有解释其具体的关联或归属。因此，无法根据当前文档内容回答火麟剑是谁的武器。

其中关于火麟剑的归属，其实文中已有，只是 AI 没能提取出来：

![|500](https://raw.githubusercontent.com/Lawrence-of-AnKing/imgBank/main/imgMD/2025/01/03/20250103-113748.png)

这里有个简单推理：拿火麟剑的人是南麟剑首⭢断帅外号“南麟剑首”⭢断帅的武器是火麟剑。可 AI 没完成，偏机械了。我也试着用 Obsidian 结合 AI 插件，在本地完成向量，提问 CHATGPT ，得到的答案也有类似问题，甚至更差。

如上，希望有有大佬能解答一下这些困惑。                                                


20 条回复  **•**  2025-01-31 20:09:13 +08:00

|   |   |   |
|---|---|---|
|![KcKXpykSg2777f5I](https://cdn.v2ex.com/gravatar/47751674a5f2786990767d0321c07d71?s=48&d=retro)||1<br><br>**[KcKXpykSg2777f5I](/member/KcKXpykSg2777f5I)**  <br><br>   33 天前<br><br>现在的水平就这样，其实向量化的数据库也会丢失很多上下文，相关性的信息，你的需求更适合跟超长上下文的模型对话。不过还是推荐一下 CherryStudio ，最新的版本支持自己选择向量化模型和对话模型，可以多尝试一些组合，说不定能找到适合你的。|

|   |   |   |
|---|---|---|
|![lointo](https://cdn.v2ex.com/avatar/b4d1/b83d/94021_normal.png?m=1426171967)||2<br><br>**[lointo](/member/lointo)**  <br><br>   33 天前 via Android<br><br>试试 notebooklm google 出品的在线知识库  <br>还有本地的 cursor.把小说切分成章节加载进去 再试下|

|   |   |   |
|---|---|---|
|![bingordinary188](https://cdn.v2ex.com/gravatar/bbee2dadbc407881c0364ca88f50dbd6?s=48&d=retro)||3<br><br>**[bingordinary188](/member/bingordinary188)**  <br><br>   33 天前 via iPhone<br><br>试下 graphed|

|   |   |   |
|---|---|---|
|![bingordinary188](https://cdn.v2ex.com/gravatar/bbee2dadbc407881c0364ca88f50dbd6?s=48&d=retro)||4<br><br>**[bingordinary188](/member/bingordinary188)**  <br><br>   33 天前 via iPhone<br><br>@[bingordinary188](/member/bingordinary188) graphrag|

|   |   |   |
|---|---|---|
|![heirtheloong](https://cdn.v2ex.com/avatar/513c/08bf/607976_normal.png?m=1672053037)||5<br><br>**[heirtheloong](/member/heirtheloong)**  <br><br>OP<br><br>   33 天前<br><br>@[lointo](/member/lointo) 稍微试了下，回答比 ChatDOC 强很多，比如上面提到的火麟剑主人的回答，他就找到了：“断帅用的是火麟剑。 袁氏兄弟看到断帅的剑，认出那是火麟剑，非常吃惊。 断帅也承认自己是南麟剑首。”  <br>  <br>但仍有不全面的问题，比如我问他聂风掌握了哪些武功，他只找到“冰心决、点穴法（其实就是兽穴法）、风神腿”，但其实还有一门鬼虎所传的“急转步法”。进一步追问下倒是得到了这套步法，可又开始胡说八道：  <br>  <br>> 除了您提到的武功之外，聂风还掌握以下武功：  <br>> ●鬼虎所授轻功步法: 在鬼虎的洞穴中，鬼虎传授给聂风一套独特的轻功步法。 这套步法非常精妙，能够帮助聂风在与巨熊搏斗中躲避攻击。 后来在与独孤鸣比试时，聂风也是用这套步法躲避了独孤鸣的“亢龙有悔”。  <br>因此，聂风所掌握的武功招式可以总结为以下几点:  <br>> ●内功心法: 冰心诀  <br>> ●轻功: 鬼虎所授轻功步法  <br>> ●腿法: 风神腿  <br>> ●剑法: 霍家剑法  <br>> ●点穴: 点穴法  <br>> 值得一提的是，虽然聂风精通霍家剑法，但他更倾向于使用腿法和轻功，这可能与他性格中善良温和的一面有关。  <br>  <br>其中“霍家剑法”显然是步惊云的武功。  <br>  <br>我会再用出版书籍试试，看面对纯知识类文本的效果如何。|

|   |   |   |
|---|---|---|
|![xieqiqiang00](https://cdn.v2ex.com/avatar/2a2a/ed0f/431158_normal.png?m=1676974734)||6<br><br>**[xieqiqiang00](/member/xieqiqiang00)**  <br><br>   33 天前 via Android<br><br>我也想要，有没有本地就能跑的，工作用数据不能外泄|

|   |   |   |
|---|---|---|
|![wangweiggsn](https://cdn.v2ex.com/avatar/3071/bd3c/303765_normal.png?m=1543539434)||7<br><br>**[wangweiggsn](/member/wangweiggsn)**  <br><br>   32 天前<br><br>我测了 kimi 算是相对还好的了，但也有上面说的问题。|

|   |   |   |
|---|---|---|
|![heirtheloong](https://cdn.v2ex.com/avatar/513c/08bf/607976_normal.png?m=1672053037)||8<br><br>**[heirtheloong](/member/heirtheloong)**  <br><br>OP<br><br>   32 天前<br><br>@[wangweiggsn](/member/wangweiggsn) 刚试了下 KIMI ，确实结果较好，但也确实和谷歌的 notebooklm 一样，当文本一长，就不能准确回答，特别是相关信息一散，就不能总结。我丢了《中国古代史教程》进去，KIMI 虽说只能读前 60%，可一让他介绍某个人物，有时还是说没有，可直接搜都能搜到名字。我截下该人物对应的章节，就能较好总结。  <br>  <br>可如果是小说这类，一个人物散见于全书各处，你再让他总结，就经常张冠李戴、不全面、胡说八道。|

|   |   |   |
|---|---|---|
|![lointo](https://cdn.v2ex.com/avatar/b4d1/b83d/94021_normal.png?m=1426171967)||9<br><br>**[lointo](/member/lointo)**  <br><br>   32 天前 via Android<br><br>@[xieqiqiang00](/member/xieqiqiang00) 那就用 cursor 然后自己用本地模型 ollama 这样子的|

|   |   |   |
|---|---|---|
|![lointo](https://cdn.v2ex.com/avatar/b4d1/b83d/94021_normal.png?m=1426171967)||10<br><br>**[lointo](/member/lointo)**  <br><br>   32 天前 via Android<br><br>@[heirtheloong](/member/heirtheloong) 试试 cursor 么|

|   |   |   |
|---|---|---|
|![emonber](https://cdn.v2ex.com/gravatar/dab6bd875fbc75dfb829188f11e7d58a?s=48&d=retro)||11<br><br>**[emonber](/member/emonber)**  <br><br>   32 天前<br><br>试试 ima.copilot ？|

|   |   |   |
|---|---|---|
|![zhaoyi1234](https://cdn.v2ex.com/gravatar/53c5d3f1c2fe11dc4adc85490d6ad64d?s=48&d=retro)||12<br><br>**[zhaoyi1234](/member/zhaoyi1234)**  <br><br>   31 天前 via Android<br><br>你这种情况适合用 图向量工具，例如 lightrag 等，不过需要一些开发量|

|                                                                                  |     |                                                                                                                     |
| -------------------------------------------------------------------------------- | --- | ------------------------------------------------------------------------------------------------------------------- |
| ![lucybenz](https://cdn.v2ex.com/avatar/692f/4a79/31293_normal.png?m=1733279610) |     | 13<br><br>**[lucybenz](/member/lucybenz)**  <br><br>   31 天前<br><br>在线的 百川 AI  <br>离线的 MaxKB  <br>这俩楼主测试过没有，我目前在用这俩 |

|   |   |   |
|---|---|---|
|![heirtheloong](https://cdn.v2ex.com/avatar/513c/08bf/607976_normal.png?m=1672053037)||14<br><br>**[heirtheloong](/member/heirtheloong)**  <br><br>OP<br><br>   29 天前<br><br>@[lucybenz](/member/lucybenz) MaxKB 之前用过，我移动端 3070 本地向量+Gemini 提问，效果很差，基本也就是原句才能找到这种，拿来做客服问答或者企业对外机器人还行，自己正经用不行，百川没试过|

|   |   |   |
|---|---|---|
|![heirtheloong](https://cdn.v2ex.com/avatar/513c/08bf/607976_normal.png?m=1672053037)||15<br><br>**[heirtheloong](/member/heirtheloong)**  <br><br>OP<br><br>   29 天前<br><br>@[lointo](/member/lointo) 试过了，同样是《中国古代史教程》和《风云 3_倾城之恋》，跟谷歌的 notebooklm 差不多，在一个水平上。比如前者，叫他总结下某某特征，能说得有模有样，但一问细一点的东西，就全不知道。对于后者，效果更差。要他“介绍下梦这个角色”，他说没有这个角色。再叫他介绍下聂风相关人物，他又能找到“梦”，可是又缺个步惊云这种重要角色。还是那个问题：你让他找全面，他就胡说、张冠李戴。你让他准确，他就找不到、找不全。  <br>  <br>如果拿来水论文，其实谷歌那个就很好了，毕竟免费额度也不少。这个我看官网只有 14 天试用，然后又基于 VS Code ，对于程序员可能很方便？能直接查找自己的代码库，并直接插入代码。但对一般用户就不甚好用了。  <br>  <br>还是看你的文本，如果是那种特别机械的文本，可能效果会不错。也看你的要求，如果只是泛读，写点综述，那也可以。但指望他帮你模糊搜索，还指出位置，那真的做不到。|

|   |   |   |
|---|---|---|
|![heirtheloong](https://cdn.v2ex.com/avatar/513c/08bf/607976_normal.png?m=1672053037)||16<br><br>**[heirtheloong](/member/heirtheloong)**  <br><br>OP<br><br>   29 天前<br><br>@[lucybenz](/member/lucybenz) 百度的刚用过了，除了其他 AI 通用的问题外（出错、漏答、张冠李戴），还有一个新问题：即使你要求他基于文本，他还是会引用网络资料。比如我问他聂风的人际关系，要求他不要引用网络资料，他本该基于小说第三部，可结果还是出现了小说中没有的角色（怀空、第二梦），即使如此，也不全面。|

|   |   |   |
|---|---|---|
|![heirtheloong](https://cdn.v2ex.com/avatar/513c/08bf/607976_normal.png?m=1672053037)||17<br><br>**[heirtheloong](/member/heirtheloong)**  <br><br>OP<br><br>   29 天前<br><br>@[zhaoyi1234](/member/zhaoyi1234) 我能力最多也就配置下别人开发好的，你整些 python 代码我还能给你跑起来，再往上我就不行了|

|   |   |   |
|---|---|---|
|![lucybenz](https://cdn.v2ex.com/avatar/692f/4a79/31293_normal.png?m=1733279610)||18<br><br>**[lucybenz](/member/lucybenz)**  <br><br>   29 天前<br><br>@[heirtheloong](/member/heirtheloong) 百川？ 谢谢你的测评，回头我也体验下你前边提到的那些方案； 我是做的数字人对话系统，目前场景要求每那么严苛；|

|   |   |   |
|---|---|---|
|![forestrs](https://cdn.v2ex.com/avatar/224b/ac56/346015_normal.png?m=1535700703)||19<br><br>**[forestrs](/member/forestrs)**  <br><br>   29 天前<br><br>可以试试秘塔搜索，支持自己传文件上去问，众多 AI 搜索的工具里面我使用体验最好的一个了|

|   |   |   |
|---|---|---|
|![sloppysop](https://cdn.v2ex.com/avatar/db81/7217/13888_normal.png?m=1715355689)||20<br><br>**[sloppysop](/member/sloppysop)**  <br><br>   4 天前 via Android<br><br>希望有一个可以本地运行的 gpt 来消化自己存的书，写的日志，消化收藏夹，可以随时提问。前几天看有 AnythingLLM 加 Deepseek ，还没配置成功|

