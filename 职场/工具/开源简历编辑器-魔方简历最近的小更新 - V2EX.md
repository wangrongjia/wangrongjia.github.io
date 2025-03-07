---
link: https://www.v2ex.com/t/1111987
site: V2EX
date: 2025-02-17T13:40
excerpt: 程序员 - @haishangrain - 魔方简历最近的一版小更新：1. 支持了 docker 部署2. AI
  设置模块抽离成了单独的菜单，更加清爽![img]( https://github.com/JOYCEQL/pi
twitter: https://twitter.com/@V2EX
slurped: 2025-03-07T15:50
title: 开源简历编辑器-魔方简历最近的小更新 - V2EX
---
 
  [haishangrain](/member/haishangrain) · 18 天前 · 1297 次点击

魔方简历最近的一版小更新：

1. 支持了 docker 部署
2. AI 设置模块抽离成了单独的菜单，更加清爽

![img](https://github.com/JOYCEQL/picx-images-hosting/raw/master/507shots_so.5fkpr1tba0.webp)

![img](https://github.com/JOYCEQL/picx-images-hosting/raw/master/339shots_so.esmzhlluq.webp)

# 体验地址

[http://magicv.art/](http://magicv.art/)

如果这个小工具对你有所帮助，请动动小手给予一个 star ，不胜感激～

[

魔方简历](/tag/魔方简历)[

Docker](/tag/Docker)[

AI](/tag/AI)

17 条回复  **•**  2025-02-20 10:26:18 +08:00

|   |   |   |
|---|---|---|
|![wxyrrcj](https://cdn.v2ex.com/avatar/a15b/2215/569167_normal.png?m=1646525179)||1<br><br>**[wxyrrcj](/member/wxyrrcj)**  <br><br>   18 天前<br><br>期待在线简历托管|

|   |   |   |
|---|---|---|
|![kile](https://cdn.v2ex.com/gravatar/70dd89b3de772b7d638bdd16d92e4419?s=48&d=retro)||2<br><br>**[kile](/member/kile)**  <br><br>   18 天前<br><br>有一说一,效果比很多同类产品好  <br>  <br>只支持 PDF,靠 json 配置一下思路就打开了  <br>  <br>md 格式出来真的代码又不好写,又不好看|

|   |   |   |
|---|---|---|
|![musi](https://cdn.v2ex.com/avatar/3c30/8c17/303588_normal.png?m=1691313864)||3<br><br>**[musi](/member/musi)**  <br><br>   17 天前<br><br>@[kile](/member/kile) 确实，用 md 写还不如用 html+tailwindcss 写，还更容易控制一些，还能直接复用前端生态|

|   |   |   |
|---|---|---|
|![bzj](https://cdn.v2ex.com/gravatar/268a4934d958d762bdfd741f2ee4c344?s=48&d=retro)||4<br><br>**[bzj](/member/bzj)**  <br><br>   17 天前<br><br>@[musi](/member/musi) 连 md 是什么都不知道了吗|

|   |   |   |
|---|---|---|
|![musi](https://cdn.v2ex.com/avatar/3c30/8c17/303588_normal.png?m=1691313864)||5<br><br>**[musi](/member/musi)**  <br><br>   17 天前<br><br>@[bzj](/member/bzj) #4 逗，md 能安装 npm 依赖吗？|

|   |   |   |
|---|---|---|
|![0xCAFEF00D](https://cdn.v2ex.com/gravatar/3d336d13b603a2b133845316a31c6ea7?s=48&d=retro)||6<br><br>**[0xCAFEF00D](/member/0xCAFEF00D)**  <br><br>   17 天前<br><br>不错，star|

|   |   |   |
|---|---|---|
|![hausen](https://cdn.v2ex.com/gravatar/f98af4acf9714d5ab15101910107a9e6?s=48&d=retro)||7<br><br>**[hausen](/member/hausen)**  <br><br>   17 天前<br><br>期待官方能自动构建 docker 镜像到 dockerhub ，不然有更新还得自己构建镜像|

|   |   |   |
|---|---|---|
|![haishangrain](https://cdn.v2ex.com/avatar/d0f9/988e/596934_normal.png?m=1739770287)||8<br><br>**[haishangrain](/member/haishangrain)**  <br><br>OP<br><br>   17 天前<br><br>@[hausen](/member/hausen) 已经 ok 了，官方镜像： [https://hub.docker.com/r/siyueqingchen/magic-resume](https://hub.docker.com/r/siyueqingchen/magic-resume)|

|   |   |   |
|---|---|---|
|![hausen](https://cdn.v2ex.com/gravatar/f98af4acf9714d5ab15101910107a9e6?s=48&d=retro)||9<br><br>**[hausen](/member/hausen)**  <br><br>   17 天前<br><br>@[haishangrain](/member/haishangrain) 感谢|

|   |   |   |
|---|---|---|
|![THESDZ](https://cdn.v2ex.com/gravatar/4477bb3cd951bd10dc081c72dd608de3?s=48&d=retro)||10<br><br>**[THESDZ](/member/THESDZ)**  <br><br>   17 天前<br><br>docker 的持久化目录是怎样的?  <br>运行用户的 id 可以映射吗?|

|   |   |   |
|---|---|---|
|![haishangrain](https://cdn.v2ex.com/avatar/d0f9/988e/596934_normal.png?m=1739770287)||11<br><br>**[haishangrain](/member/haishangrain)**  <br><br>OP<br><br>   16 天前<br><br>@[THESDZ](/member/THESDZ) 没有设计持久化目录，id 是固定映射的，详细可以看 github 仓库的 dockerfile|

|   |   |   |
|---|---|---|
|![qtxxm](https://cdn.v2ex.com/gravatar/0ff395c144b1e701d19179c679d92494?s=48&d=retro)||12<br><br>**[qtxxm](/member/qtxxm)**  <br><br>   16 天前<br><br>本地 docker 启动后, 点击简历模板好像报异常  <br>```javascript  <br>Uncaught TypeError: crypto.randomUUID is not a function  <br>NextJS 14  <br>createResume  <br>s  <br>onClick  <br>a_  <br>aR  <br>sF  <br>sF  <br>sM  <br>sU  <br>o4  <br>iV  <br>sU  <br>uR  <br>uM  <br>```|

|   |   |   |
|---|---|---|
|![haishangrain](https://cdn.v2ex.com/avatar/d0f9/988e/596934_normal.png?m=1739770287)||13<br><br>**[haishangrain](/member/haishangrain)**  <br><br>OP<br><br>   16 天前<br><br>@[qtxxm](/member/qtxxm) 你在 win 还是 mac 或者是服务器上的 docker ，我用 mac 没复现出来|

|   |   |   |
|---|---|---|
|![haishangrain](https://cdn.v2ex.com/avatar/d0f9/988e/596934_normal.png?m=1739770287)||14<br><br>**[haishangrain](/member/haishangrain)**  <br><br>OP<br><br>   16 天前<br><br>@[qtxxm](/member/qtxxm) 猜测是你 node 的环境有点旧，请使用 node.20 版本尝试|

|   |   |   |
|---|---|---|
|![haishangrain](https://cdn.v2ex.com/avatar/d0f9/988e/596934_normal.png?m=1739770287)||15<br><br>**[haishangrain](/member/haishangrain)**  <br><br>OP<br><br>   16 天前<br><br>@[qtxxm](/member/qtxxm) 现在再试试，应该可以了|

|   |   |   |
|---|---|---|
|![qtxxm](https://cdn.v2ex.com/gravatar/0ff395c144b1e701d19179c679d92494?s=48&d=retro)||16<br><br>**[qtxxm](/member/qtxxm)**  <br><br>   15 天前<br><br>@[haishangrain](/member/haishangrain) 正常打开了，请问是 node 版本问题么？|

|   |   |   |
|---|---|---|
|![haishangrain](https://cdn.v2ex.com/avatar/d0f9/988e/596934_normal.png?m=1739770287)||17<br><br>**[haishangrain](/member/haishangrain)**  <br><br>OP<br><br>   15 天前<br><br>@[qtxxm](/member/qtxxm) 我没复现，就直接换了个库实现|

[

](https://www.digitalocean.com/?refcode=1b51f1a7651d)

**[关于](/about)   ·   [帮助文档](/help)   ·   [博客](https://blog.v2ex.com/)   ·   [API](/help/api)   ·   [FAQ](/faq)   ·   [实用小工具](/tools)   ·   5204 人在线**   最高记录 6679   ·     [![](/static/img/language.png?v=6a5cfa731dc71a3769f6daace6784739)   Select Language](/select/language)

创意工作者们的社区

World is powered by solitude

VERSION: 3.9.8.5 · 31ms · [UTC 07:47](/worldclock#utc) · [PVG 15:47](/worldclock#pvg) · [LAX 23:47](/worldclock#lax) · [JFK 02:47](/worldclock#jfk)  
Developed with [CodeLauncher](https://cl.v2ex.pro/)  
♥ Do have faith in what you're doing.