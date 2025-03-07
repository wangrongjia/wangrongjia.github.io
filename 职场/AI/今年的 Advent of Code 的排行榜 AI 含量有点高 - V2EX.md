---
link: https://www.v2ex.com/t/1095887
site: V2EX
date: 2024-12-08T14:28
excerpt: 程序员 - @wlh233 - [Advent of Code]( https://adventofcode.com/)
  是个每年一次的活动，主办者每天定时放出一道编程题，前 100 名做出来的可以进当天的排行榜并获得分数，根据总分
twitter: https://twitter.com/@V2EX
slurped: 2025-02-08T14:14
title: 今年的 Advent of Code 的排行榜 AI 含量有点高 - V2EX
---
  
[wlh320](https://github.com/wlh320) · 61 天前 · 2283 次点击

这是一个创建于 61 天前的主题，其中的信息可能已经有所发展或是发生改变。

[Advent of Code](https://adventofcode.com/) 是个每年一次的活动，主办者每天定时放出一道编程题，前 100 名做出来的可以进当天的排行榜并获得分数，根据总分还有个总排行榜。

题目难度总体上不算太大，基本上是随着日期每天变难一点。有时会有特别复杂的模拟题，比如前两年有道题需要把一个立方体的平面展开图组装起来，模拟在立方体表面移动。

从去年开始，有人开始尝试用 AI 自动化解题了，但随着每天题目的难度增加基本坚持不了几天。

今年情况有点不一样。这是第 8 天，AI 选手还是可以做到 **14 秒** 从读题到提交答案拿到榜一。怎么确定是 AI 呢，有很多用户点进 GitHub 一看都明说了自己是做 LLM 的。值得注意的是网站有提交限制，答错两次后在一段时间内不能提交。14 秒的时间基本意味着现在的 AI 模型可以**一次性把题做对**。

实际上，主办者去年开始已经在网站上表达了他的态度，明令禁止这种行为，然而没有什么效果。

> > > Can I use AI to get on the global leaderboard? Please don't use AI / LLMs (like GPT) to automatically solve a day's puzzles until that day's global leaderboards are full. By "automatically", I mean using AI to do most or all of the puzzle solving, like handing the puzzle text directly to an LLM. The leaderboards are for human competitors; if you want to compare the speed of your AI solver with others, please do so elsewhere. (If you want to use AI to help you solve puzzles, I can't really stop you, but I feel like it's harder to get better at programming if you ask an AI to do the programming for you.)

先不管用 AI 刷榜的行为如何（_因为我的水平还上不了榜所以我不太关心位置被抢了_），我比较感��趣的是这件事反映出的 AI 编程能力的提升极大地超出了我的预期。我之前对大语言模型的态度还是比较悲观的，认为只能写写文字不算真正的智能，从现在开始我想法有点转变了，很难想象过几年我的编程水平还能不能有班上。

过几天如果复杂模拟题还是能被 AI 轻松做出来的话，我要开始计划认真学一学准备转行了。我的 NLP 知识水平还停留在 word2vec 呢，现在开始学还来得及吗？

第 1 条附言  ·  56 天前

今天（第 14 天）的第二问比较绝，我认为几年内 AI 还不具备**独立**解出这种题的能力，感觉这是作者有意的反击。


5 条回复  **•**  2024-12-09 11:52:54 +08:00

|   |   |   |
|---|---|---|
|![Kauruus](https://cdn.v2ex.com/avatar/1c6c/41b9/328201_normal.png?m=1531401751)||1<br><br>**[Kauruus](/member/Kauruus)**  <br><br>   61 天前<br><br>转行做套壳还是来得及的，感觉连不知道 NLP 和 word2vec 都没问题。  <br>  <br>转行做模型，没钱没卡没数据，怕是来不及了。|

|   |   |   |
|---|---|---|
|![majula](https://cdn.v2ex.com/gravatar/5a6cbf049c81ff590baf25190606cda1?s=48&d=retro)||2<br><br>**[majula](/member/majula)**  <br><br>   61 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 4<br><br>我本来也是对 AI 解决问题的能力持怀疑态度的，总觉得它目前只适合做简单重复工作。不过近一年来 AI 显然变强了许多，让我对其有所改观。  <br>  <br>上周我们部门里有个实习生小伙子，只花了不到一小时，拿 AI 解决了整个算法团队折腾了两周都没有头绪的性能优化相关 case 。而且不是动动嘴皮子，而是生成了可以跑通 benchmark 用例，有实打实的 10%~15% 稳定性能提升的代码  <br>  <br>当时我们工作群就炸锅了，一整天都无心工作在那里吃瓜。算法团队应该是破防最严重的，他们那边一堆上世纪就开始写代码的老工程师，技术氛围守旧，对 AI 持激进的排斥态度。这下子自己的工作专长被 AI 轻易地威胁到了，不知道接下来该何去何从，整片工位一直阴霾不散|

|   |   |   |
|---|---|---|
|![levelworm](https://cdn.v2ex.com/avatar/3f06/6f8f/401678_normal.png?m=1733594936)||3<br><br>**[levelworm](/member/levelworm)**  <br><br>   61 天前 via Android<br><br>没办法了，估计这就是趋势，咱们程序员孜孜不倦的把自己的工作迅速搞没。还好四十多了，就研究研究自己感兴趣的底层代码，混到六十岁就行了。|

|   |   |   |
|---|---|---|
|![shylockhg](https://cdn.v2ex.com/gravatar/1bea0d89d2b7688a434dd3d0aa7d343c?s=48&d=retro)||4<br><br>**[shylockhg](/member/shylockhg)**  <br><br>   61 天前<br><br>做 API boy 还行，LLM 不管训练还是微调个人成本都挺高|

|   |   |   |
|---|---|---|
|![ninjashixuan](https://cdn.v2ex.com/gravatar/b0a9dd66406d51c7c0a5ef35f3e56c37?s=48&d=retro)||5<br><br>**[ninjashixuan](/member/ninjashixuan)**  <br><br>   61 天前<br><br>这种兴趣比赛 puzzle 用 AI 不是很无聊么。|
