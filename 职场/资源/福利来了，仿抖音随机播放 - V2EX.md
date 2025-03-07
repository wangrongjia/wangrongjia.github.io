---
link: https://www.v2ex.com/t/1101154
site: V2EX
date: 2024-12-30T09:36
excerpt: 分享创造 - @levywang - Random Web Player配合接口实现类似抖音效果的随机在线播放器，内置接口提供了 50W+
  随机地址播放。该项目只是一个简单的 html 页面，需要配合项目中的爬虫或者接口使
twitter: https://twitter.com/@V2EX
slurped: 2025-02-08T09:17
title: 福利来了，仿抖音随机播放 - V2EX
---


  [levywang](/member/levywang) · 39 天前 · 6946 次点击

这是一个创建于 39 天前的主题，其中的信息可能已经有所发展或是发生改变。

Random Web Player

配合接口实现类似抖音效果的随机在线播放器，内置接口提供了 50W+ 随机地址播放。

该项目只是一个简单的 html 页面，需要配合项目中的爬虫或者接口使用

项目地址： [https://github.com/levywang/random_web_player](https://github.com/levywang/random_web_player)

起因是刷到了某个帖子，发现一些 h 站开启了 nginx autoindex ，内置了非常多的播放源地址，经过一番摸鱼，成功写好了 pa 虫和 api ，配合项目中的 index.html 食用，在哪都能无缝刷小姐姐了~~~

预览地址： [http://43.154.146.172/](http://43.154.146.172/)

**预览地址&本项目 不宜在工作场合和旁边有人的情况下打开**

第 1 条附言  ·  39 天前

感谢各位的提醒，预览地址改为：  
Cloudflare Page: [https://random-web-player.pages.dev/](https://random-web-player.pages.dev/)  
  
原来的地址取消了，GitHub 中增加了自建 api 文档和播放源 txt 文件


74 条回复  **•**  2025-01-02 17:02:19 +08:00

|   |   |   |
|---|---|---|
|![zhaom](https://cdn.v2ex.com/avatar/3325/5afa/70531_normal.png?m=1737014907)||1<br><br>**[zhaom](/member/zhaom)**  <br><br>   39 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>太牛逼了 哥们 你从哪里找的那么多视频|

|   |   |   |
|---|---|---|
|![levywang](https://cdn.v2ex.com/gravatar/28a0b6038d0ce68b7ce5fc659a0e00b1?s=48&d=retro)||2<br><br>**[levywang](/member/levywang)**  <br><br>OP<br><br>   39 天前<br><br>@[zhaom](/member/zhaom) 项目中有方法，都是 h 站的源地址，爬过来的|

|   |   |   |
|---|---|---|
|![x86](https://cdn.v2ex.com/avatar/04c7/f37f/12555_normal.png?m=1647752403)||3<br><br>**[x86](/member/x86)**  <br><br>   39 天前<br><br>可以点🩷后，根据片的 tag 推荐相同类型的片吗|

|   |   |   |
|---|---|---|
|![levywang](https://cdn.v2ex.com/gravatar/28a0b6038d0ce68b7ce5fc659a0e00b1?s=48&d=retro)||4<br><br>**[levywang](/member/levywang)**  <br><br>OP<br><br>   39 天前<br><br>@[x86](/member/x86) 不会那么复杂的，源地址没有其他信息，这个又不是真的抖音系统 哈哈🤣|

|   |   |   |
|---|---|---|
|![x86](https://cdn.v2ex.com/avatar/04c7/f37f/12555_normal.png?m=1647752403)||5<br><br>**[x86](/member/x86)**  <br><br>   39 天前<br><br>@[levywang](/member/levywang) #4 下次可以抓 jable 的，那边的页面带片子 tag 的🐶|

|   |   |   |
|---|---|---|
|![forty](https://cdn.v2ex.com/avatar/b93d/57f6/177983_normal.png?m=1467965927)||6<br><br>**[forty](/member/forty)**  <br><br>   39 天前<br><br>有随机直播的吗？|

|   |   |   |
|---|---|---|
|![bkmi](https://cdn.v2ex.com/avatar/9d67/8e20/84263_normal.png?m=1735309349)||7<br><br>**[bkmi](/member/bkmi)**  <br><br>   39 天前<br><br>很刑啊 少年|

|   |   |   |
|---|---|---|
|![yuwangG](https://cdn.v2ex.com/avatar/9854/55e0/414646_normal.png?m=1629969132)||8<br><br>**[yuwangG](/member/yuwangG)**  <br><br>   39 天前<br><br>少年你这技术可以啊🐶|

|   |   |   |
|---|---|---|
|![l6241425](https://cdn.v2ex.com/avatar/30af/a518/353242_normal.png?m=1703571740)||9<br><br>**[l6241425](/member/l6241425)**  <br><br>   39 天前<br><br>牛批|

|   |   |   |
|---|---|---|
|![levywang](https://cdn.v2ex.com/gravatar/28a0b6038d0ce68b7ce5fc659a0e00b1?s=48&d=retro)||10<br><br>**[levywang](/member/levywang)**  <br><br>OP<br><br>   39 天前<br><br>@[forty](/member/forty) 你自己找到直播源也是可以的|

|   |   |   |
|---|---|---|
|![levywang](https://cdn.v2ex.com/gravatar/28a0b6038d0ce68b7ce5fc659a0e00b1?s=48&d=retro)||11<br><br>**[levywang](/member/levywang)**  <br><br>OP<br><br>   39 天前<br><br>@[x86](/member/x86) 这个就涉及到前后端交互了，现在的项目只是一个纯粹的播放器，由于一些你懂得原因，加上交互和推荐就不太适合了|

|   |   |   |
|---|---|---|
|![yypro](https://cdn.v2ex.com/avatar/195a/b6f5/596835_normal.png?m=1668073523)||12<br><br>**[yypro](/member/yypro)**  <br><br>   39 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 3<br><br>看到了预览地址，没注意底下的一行字，这办公室我是呆不下去了😡|

|   |   |   |
|---|---|---|
|![lpf0309](https://cdn.v2ex.com/gravatar/05afcae7ad9c0d40b7dc9318355d74de?s=48&d=retro)||13<br><br>**[lpf0309](/member/lpf0309)**  <br><br>   39 天前<br><br>牛逼|

|   |   |   |
|---|---|---|
|![sam7ikoma](https://cdn.v2ex.com/gravatar/e32a1d4d79ef3a8cead1e5b8306cc0c9?s=48&d=retro)||14<br><br>**[sam7ikoma](/member/sam7ikoma)**  <br><br>   39 天前<br><br>牛批...|

|   |   |   |
|---|---|---|
|![levywang](https://cdn.v2ex.com/gravatar/28a0b6038d0ce68b7ce5fc659a0e00b1?s=48&d=retro)||15<br><br>**[levywang](/member/levywang)**  <br><br>OP<br><br>   39 天前<br><br>@[yypro](/member/yypro) 这个不能怪我哈|

|   |   |   |
|---|---|---|
|![lynth](https://cdn.v2ex.com/avatar/9962/b91b/202807_normal.png?m=1680569617)||16<br><br>**[lynth](/member/lynth)**  <br><br>   39 天前<br><br>清晰度堪忧呀，感觉源片不至于这么糊吧。|

|   |   |   |
|---|---|---|
|![levywang](https://cdn.v2ex.com/gravatar/28a0b6038d0ce68b7ce5fc659a0e00b1?s=48&d=retro)||17<br><br>**[levywang](/member/levywang)**  <br><br>OP<br><br>   39 天前<br><br>@[lynth](/member/lynth) 源站的质量就那样啊，有些视频点击全屏会好些|

|   |   |   |
|---|---|---|
|![lynth](https://cdn.v2ex.com/avatar/9962/b91b/202807_normal.png?m=1680569617)||18<br><br>**[lynth](/member/lynth)**  <br><br>   39 天前<br><br>@[levywang](/member/levywang) #17 确实，播放器填充模式有问题，全屏才是源片的画质。|

|   |   |   |
|---|---|---|
|![Xinu](https://cdn.v2ex.com/avatar/021e/4fbb/431658_normal.png?m=1724206977)||19<br><br>**[Xinu](/member/Xinu)**  <br><br>   39 天前<br><br>祝楼主长生不死|

|   |   |   |
|---|---|---|
|![Xinu](https://cdn.v2ex.com/avatar/021e/4fbb/431658_normal.png?m=1724206977)||20<br><br>**[Xinu](/member/Xinu)**  <br><br>   39 天前<br><br>我擦啊 还有暴力血腥的视频，能不能干掉，有点吓人|

|   |   |   |
|---|---|---|
|![lucybenz](https://cdn.v2ex.com/avatar/692f/4a79/31293_normal.png?m=1733279610)||21<br><br>**[lucybenz](/member/lucybenz)**  <br><br>   39 天前<br><br>@[yypro](/member/yypro) 我差一点儿点开|

|   |   |   |
|---|---|---|
|![GiggleSmile](https://cdn.v2ex.com/gravatar/7e0f01fba0ea722311684c86a41fc1da?s=48&d=retro)||22<br><br>**[GiggleSmile](/member/GiggleSmile)**  <br><br>   39 天前<br><br>幸好手速快|

|   |   |   |
|---|---|---|
|![izsm](https://cdn.v2ex.com/avatar/f0d5/4d44/600048_normal.png?m=1731487554)||23<br><br>**[izsm](/member/izsm)**  <br><br>   39 天前<br><br>日，坑人啊，还好手速快|

|   |   |   |
|---|---|---|
|![yangxiaopeipei](https://cdn.v2ex.com/avatar/2164/d6a6/302144_normal.png?m=1689566540)||24<br><br>**[yangxiaopeipei](/member/yangxiaopeipei)**  <br><br>   39 天前<br><br>第一个就是🐢头？|

|   |   |   |
|---|---|---|
|![nevermoreluo](https://cdn.v2ex.com/gravatar/a08a48aa178c972f91958b604a35f5e3?s=48&d=retro)||25<br><br>**[nevermoreluo](/member/nevermoreluo)**  <br><br>   39 天前<br><br>emmm 哥们该说不说的，还是小心点吧。  <br>你这 ip 腾讯云的吧，对叔叔来说相当于实名上网了。  <br>咱说实话，防人之心不可无啊|

|   |   |   |
|---|---|---|
|![mumbler](https://cdn.v2ex.com/gravatar/53e87c11a8aa9c21ad440f5b5eacdba9?s=48&d=retro)||26<br><br>**[mumbler](/member/mumbler)**  <br><br>   39 天前<br><br>都不能上滑下滑|

|   |   |   |
|---|---|---|
|![Tink](https://cdn.v2ex.com/avatar/64d6/6ac2/51170_normal.png?m=1684830587)||27<br><br>**[Tink](/member/Tink)**  <br><br>   39 天前<br><br>打不开呀|

|   |   |   |
|---|---|---|
|![spacebound](https://cdn.v2ex.com/avatar/d5a6/ae01/429976_normal.png?m=1715391893)||28<br><br>**[spacebound](/member/spacebound)**  <br><br>   39 天前<br><br>思路很强啊兄弟|

|   |   |   |
|---|---|---|
|![levywang](https://cdn.v2ex.com/gravatar/28a0b6038d0ce68b7ce5fc659a0e00b1?s=48&d=retro)||29<br><br>**[levywang](/member/levywang)**  <br><br>OP<br><br>   39 天前<br><br>@[nevermoreluo](/member/nevermoreluo) 嗯 Demo 站马上关掉，有需要的下载源码自己构建吧|

|   |   |   |
|---|---|---|
|![lbbdefy](https://cdn.v2ex.com/avatar/d97b/4583/192025_normal.png?m=1478614187)||30<br><br>**[lbbdefy](/member/lbbdefy)**  <br><br>   39 天前<br><br>牛的|

|   |   |   |
|---|---|---|
|![albert0326](https://cdn.v2ex.com/gravatar/653b4fcfc2e3f8d624220cb09422e1fb?s=48&d=retro)||31<br><br>**[albert0326](/member/albert0326)**  <br><br>   39 天前<br><br>牛逼 太强了。搞个群吹水吧|

|   |   |   |
|---|---|---|
|![youngkingdom](https://cdn.v2ex.com/gravatar/7288e73141181568e9124a6842b3c642?s=48&d=retro)||32<br><br>**[youngkingdom](/member/youngkingdom)**  <br><br>   39 天前<br><br>api 源站有吗|

|   |   |   |
|---|---|---|
|![levywang](https://cdn.v2ex.com/gravatar/28a0b6038d0ce68b7ce5fc659a0e00b1?s=48&d=retro)||33<br><br>**[levywang](/member/levywang)**  <br><br>OP<br><br>   39 天前<br><br>@[youngkingdom](/member/youngkingdom) 有的，看文档，python fastapi|

|   |   |   |
|---|---|---|
|![youngkingdom](https://cdn.v2ex.com/gravatar/7288e73141181568e9124a6842b3c642?s=48&d=retro)||34<br><br>**[youngkingdom](/member/youngkingdom)**  <br><br>   39 天前<br><br>@[levywang](/member/levywang) #33 谢谢，刚刚没仔细看以为是公开的 api|

|   |   |   |
|---|---|---|
|![moxiaonai](https://cdn.v2ex.com/avatar/e6dd/5516/139726_normal.png?m=1478691934)||35<br><br>**[moxiaonai](/member/moxiaonai)**  <br><br>   39 天前<br><br>我擦，上班呢，打开吓我一跳|

|   |   |   |
|---|---|---|
|![dyyhobby](https://cdn.v2ex.com/gravatar/574370dfe11b537e76209253dd5a4287?s=48&d=retro)||36<br><br>**[dyyhobby](/member/dyyhobby)**  <br><br>   39 天前<br><br>来来来，交代一下你的犯罪事实|

|   |   |   |
|---|---|---|
|![dododada](https://cdn.v2ex.com/avatar/2def/a0c9/58056_normal.png?m=1713160096)||37<br><br>**[dododada](/member/dododada)**  <br><br>   39 天前<br><br>擦，吓我一跳|

|   |   |   |
|---|---|---|
|![frozenway](https://cdn.v2ex.com/avatar/c684/ffbb/226009_normal.png?m=1644474092)||38<br><br>**[frozenway](/member/frozenway)**  <br><br>   39 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>我擦，上班呢，打开吓我一跳|

|   |   |   |
|---|---|---|
|![braveLeon](https://cdn.v2ex.com/avatar/f9d5/f367/255021_normal.png?m=1738831285)||39<br><br>**[braveLeon](/member/braveLeon)**  <br><br>   39 天前<br><br>被女同事看到了，丢，社死了|

|   |   |   |
|---|---|---|
|![opengps](https://cdn.v2ex.com/avatar/1e8a/4d9b/250842_normal.png?m=1722219513)||40<br><br>**[opengps](/member/opengps)**  <br><br>   39 天前<br><br>靠|

|   |   |   |
|---|---|---|
|![Aindy](https://cdn.v2ex.com/avatar/8166/90ed/564750_normal.png?m=1726033057)||41<br><br>**[Aindy](/member/Aindy)**  <br><br>   39 天前<br><br>神经病|

|   |   |   |
|---|---|---|
|![GeekGao](https://cdn.v2ex.com/avatar/6540/f6ff/30946_normal.png?m=1731046133)||42<br><br>**[GeekGao](/member/GeekGao)**  <br><br>   39 天前<br><br>刑啊，牢玩家了|

|   |   |   |
|---|---|---|
|![slowmist](https://cdn.v2ex.com/avatar/3cc1/6b4a/646602_normal.png?m=1704500903)||43<br><br>**[slowmist](/member/slowmist)**  <br><br>   39 天前<br><br>ts m3u8 是自动切割生成的吗|

|   |   |   |
|---|---|---|
|![systemsettings](https://cdn.v2ex.com/avatar/e8c1/cd1a/688146_normal.png?m=1716697227)||44<br><br>**[systemsettings](/member/systemsettings)**  <br><br>   39 天前<br><br>我还以为是福利呢，原来真的是福利|

|   |   |   |
|---|---|---|
|![Ne](https://cdn.v2ex.com/avatar/4179/7f18/70823_normal.png?m=1715426855)||45<br><br>**[Ne](/member/Ne)**  <br><br>   39 天前 via Android<br><br>真福利不是吹牛，打开看了差点赶不上车😂|

|   |   |   |
|---|---|---|
|![kokerkov](https://cdn.v2ex.com/gravatar/394276fe32a121c5c21b4af110058c98?s=48&d=retro)||46<br><br>**[kokerkov](/member/kokerkov)**  <br><br>   39 天前<br><br>地址失效了还是要挂梯子了？ rand-web-player 那个地址|

|   |   |   |
|---|---|---|
|![AbysmalSorrow](https://cdn.v2ex.com/avatar/e01b/0920/524395_normal.png?m=1728721072)||47<br><br>**[AbysmalSorrow](/member/AbysmalSorrow)**  <br><br>   39 天前<br><br>1024 投币上车 [![](https://i.imgur.com/Cvl7dyN.png)](https://i.imgur.com/Cvl7dyN.png)|

|   |   |   |
|---|---|---|
|![levywang](https://cdn.v2ex.com/gravatar/28a0b6038d0ce68b7ce5fc659a0e00b1?s=48&d=retro)||48<br><br>**[levywang](/member/levywang)**  <br><br>OP<br><br>   39 天前<br><br>@[slowmist](/member/slowmist) 看教程，网络空间测绘获取 h 站的特征，爬的他们的数据源|

|   |   |   |
|---|---|---|
|![levywang](https://cdn.v2ex.com/gravatar/28a0b6038d0ce68b7ce5fc659a0e00b1?s=48&d=retro)||49<br><br>**[levywang](/member/levywang)**  <br><br>OP<br><br>   39 天前<br><br>@[kokerkov](/member/kokerkov) 这个是 cloudflare page ，有的地区应该是被墙了|

|   |   |   |
|---|---|---|
|![pol](https://cdn.v2ex.com/gravatar/0d4f712558090208cd0386048b1bb766?s=48&d=retro)||50<br><br>**[pol](/member/pol)**  <br><br>   38 天前<br><br>op op ，我看到你是通过那个什么网站搜索 包含 index of 的 ip ，但你是如何知道他是 h 站呢，这个没看明白|

|   |   |   |
|---|---|---|
|![levywang](https://cdn.v2ex.com/gravatar/28a0b6038d0ce68b7ce5fc659a0e00b1?s=48&d=retro)||51<br><br>**[levywang](/member/levywang)**  <br><br>OP<br><br>   38 天前<br><br>@[pol](/member/pol) h 站开启了 nginx autoindex ，里面的目录特征都是差不多的，应该是用同一种程序生成的。|

|   |   |   |
|---|---|---|
|![lisxour](https://cdn.v2ex.com/avatar/580f/70c0/600882_normal.png?m=1717041609)||52<br><br>**[lisxour](/member/lisxour)**  <br><br>   38 天前<br><br>不是哥们，你搞个 demo 站啊，我一打开直接零帧起手，差点社死 [![](https://i.imgur.com/c1Q76Cd.png)](https://i.imgur.com/c1Q76Cd.png)|

|   |   |   |
|---|---|---|
|![guoziq09](https://cdn.v2ex.com/gravatar/40d40f2689168164ec7ea1a6fe41229c?s=48&d=retro)||53<br><br>**[guoziq09](/member/guoziq09)**  <br><br>   38 天前<br><br>卧槽你的 OP..........友情提示,别在公司打开....|

|   |   |   |
|---|---|---|
|![wangxinpier](https://cdn.v2ex.com/avatar/cd11/ec55/136174_normal.png?m=1719383419)||54<br><br>**[wangxinpier](/member/wangxinpier)**  <br><br>   38 天前<br><br>服了，什么东西，差点社死一万年。。。。。|

|   |   |   |
|---|---|---|
|![fukusan](https://cdn.v2ex.com/gravatar/b7673703766658d9d2d9558497c33ff6?s=48&d=retro)||55<br><br>**[fukusan](/member/fukusan)**  <br><br>   38 天前 via Android<br><br>🐮🐮🐮服了|

|   |   |   |
|---|---|---|
|![PamelaKevein](https://cdn.v2ex.com/avatar/7b2e/1d26/466244_normal.png?m=1581517201)||56<br><br>**[PamelaKevein](/member/PamelaKevein)**  <br><br>   38 天前 via iPhone<br><br>💯|

|   |   |   |
|---|---|---|
|![makry](https://cdn.v2ex.com/avatar/1c0a/7798/89131_normal.png?m=1737627889)||57<br><br>**[makry](/member/makry)**  <br><br>   38 天前<br><br>上去第一个就 TM 刷到个光头尼姑！！！|

|   |   |   |
|---|---|---|
|![diglife](https://cdn.v2ex.com/gravatar/c47bb442cb8309bcc8062ff658a6e500?s=48&d=retro)||58<br><br>**[diglife](/member/diglife)**  <br><br>   38 天前<br><br>差点~~~|

|   |   |   |
|---|---|---|
|![zarvin](https://cdn.v2ex.com/gravatar/15867de4ca10ad44672d427bcc0d5908?s=48&d=retro)||59<br><br>**[zarvin](/member/zarvin)**  <br><br>   38 天前<br><br>18++++++，请写在第一行|

|   |   |   |
|---|---|---|
|![channlong](https://cdn.v2ex.com/gravatar/c0acb1df4816942186128a0c843ec802?s=48&d=retro)||60<br><br>**[channlong](/member/channlong)**  <br><br>   38 天前<br><br>太好了， 是雷锋， 弟弟们有救了|

|   |   |   |
|---|---|---|
|![Num6](https://cdn.v2ex.com/gravatar/e87cf00db3fac1e431a3f92dc80426df?s=48&d=retro)||61<br><br>**[Num6](/member/Num6)**  <br><br>   38 天前<br><br>。。。NSFW|

|   |   |   |
|---|---|---|
|![Jinyang7](https://cdn.v2ex.com/avatar/a363/71cc/471483_normal.png?m=1702004716)||62<br><br>**[Jinyang7](/member/Jinyang7)**  <br><br>   38 天前<br><br>我超，上班呢 吓我一跳|

|   |   |   |
|---|---|---|
|![PrinceofInj](https://cdn.v2ex.com/gravatar/a8e5a873829e265b793a9ef8e7811300?s=48&d=retro)||63<br><br>**[PrinceofInj](/member/PrinceofInj)**  <br><br>   38 天前<br><br>我艹，开屏暴击，还好旁边没人。|

|   |   |   |
|---|---|---|
|![lizhenda](https://cdn.v2ex.com/avatar/45df/c74b/128487_normal.png?m=1444477674)||64<br><br>**[lizhenda](/member/lizhenda)**  <br><br>   38 天前<br><br>有点厉害啊，不过就是质量太糊了吧|

|   |   |   |
|---|---|---|
|![levywang](https://cdn.v2ex.com/gravatar/28a0b6038d0ce68b7ce5fc659a0e00b1?s=48&d=retro)||65<br><br>**[levywang](/member/levywang)**  <br><br>OP<br><br>   38 天前<br><br>@[lizhenda](/member/lizhenda) 点全屏播放，原视频格式大小分辨率都不一样，前端水平不行，全屏播放就是原质量|

|   |   |   |
|---|---|---|
|![sobev](https://cdn.v2ex.com/avatar/caac/0be5/580026_normal.png?m=1711434436)||66<br><br>**[sobev](/member/sobev)**  <br><br>   38 天前 via Android<br><br>爬到的地址刚好给 tvbox 用😏😏|

|   |   |   |
|---|---|---|
|![zfyStars](https://cdn.v2ex.com/avatar/b5f7/589b/682416_normal.png?m=1717464001)||67<br><br>**[zfyStars](/member/zfyStars)**  <br><br>   38 天前<br><br>卧槽 上班不小心打开了|

|   |   |   |
|---|---|---|
|![levywang](https://cdn.v2ex.com/gravatar/28a0b6038d0ce68b7ce5fc659a0e00b1?s=48&d=retro)||68<br><br>**[levywang](/member/levywang)**  <br><br>OP<br><br>   38 天前<br><br>@[sobev](/member/sobev) 是的，你这个也是个好方法|

|   |   |   |
|---|---|---|
|![sunrain](https://cdn.v2ex.com/avatar/3761/fc95/24503_normal.png?m=1626694484)||69<br><br>**[sunrain](/member/sunrain)**  <br><br>   38 天前<br><br>FUCK ，名誉扫地。|

|   |   |   |
|---|---|---|
|![monkeyWie](https://cdn.v2ex.com/avatar/9a27/720a/461501_normal.png?m=1725355575)||70<br><br>**[monkeyWie](/member/monkeyWie)**  <br><br>   38 天前 via Android<br><br>有点东西啊|

|   |   |   |
|---|---|---|
|![bigtear](https://cdn.v2ex.com/gravatar/42bbedaf61395a9fb73e397bab3c6d5d?s=48&d=retro)||71<br><br>**[bigtear](/member/bigtear)**  <br><br>   37 天前<br><br>点开 tmd 是南桐|

|   |   |   |
|---|---|---|
|![pacino](https://cdn.v2ex.com/avatar/1faa/cc3a/40201_normal.png?m=1423449039)||72<br><br>**[pacino](/member/pacino)**  <br><br>   36 天前<br><br>厉害了👍|

|   |   |   |
|---|---|---|
|![lanweizhujiao](https://cdn.v2ex.com/avatar/1c4b/2e0d/630454_normal.png?m=1737447490)||73<br><br>**[lanweizhujiao](/member/lanweizhujiao)**  <br><br>   36 天前<br><br>现在已经黑屏了 没有视频输出了|

|   |   |   |
|---|---|---|
|![levywang](https://cdn.v2ex.com/gravatar/28a0b6038d0ce68b7ce5fc659a0e00b1?s=48&d=retro)||74<br><br>**[levywang](/member/levywang)**  <br><br>OP<br><br>   36 天前<br><br>@[lanweizhujiao](/member/lanweizhujiao) 版本更新了，现在好了|
