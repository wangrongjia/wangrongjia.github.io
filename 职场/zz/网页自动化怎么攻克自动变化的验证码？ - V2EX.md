---
link: https://www.v2ex.com/t/1097616
site: V2EX
date: 2024-12-14T23:53
excerpt: 程序员 - @wty95 -
  这个网站：https://www.jszwfw.gov.cn/jsjis/front/login.do?uuid=qvCwgZCSeRbz&gotoUrl=aHR0cDovL3h6endmdy5q
twitter: https://twitter.com/@V2EX
slurped: 2025-02-08T10:12
title: 网页自动化怎么攻克自动变化的验证码？ - V2EX
---

  [wty95](/member/wty95) · 55 天前 · 4773 次点击

这是一个创建于 55 天前的主题，其中的信息可能已经有所发展或是发生改变。

这个网站： [https://www.jszwfw.gov.cn/jsjis/front/login.do?uuid=qvCwgZCSeRbz&gotoUrl=aHR0cDovL3h6endmdy5qc3p3ZncuZ292LmNuL3h6empjc21od3ovZXBvaW50empjcy9wYWdlcy9hZ2VudFNwYWNlX3NlcnZpY2Uvd2FpdEJpZGRpbmc%2FendkdHV1aWQ9ZGI4NmIzNzUtYjU4NS00MmY5LWE0MjktODI4NjUyMzE2MjA2](https://www.jszwfw.gov.cn/jsjis/front/login.do?uuid=qvCwgZCSeRbz&gotoUrl=aHR0cDovL3h6endmdy5qc3p3ZncuZ292LmNuL3h6empjc21od3ovZXBvaW50empjcy9wYWdlcy9hZ2VudFNwYWNlX3NlcnZpY2Uvd2FpdEJpZGRpbmc%2FendkdHV1aWQ9ZGI4NmIzNzUtYjU4NS00MmY5LWE0MjktODI4NjUyMzE2MjA2)

验证码 url 是固定的，但返回结果每次都变： [https://www.jszwfw.gov.cn/jsjis/component/verifyCode.do?code=4&var=rand&width=162&height=55&random=0.34837298861771937](https://www.jszwfw.gov.cn/jsjis/component/verifyCode.do?code=4&var=rand&width=162&height=55&random=0.34837298861771937)

我目前是用自动化用 selenium ，识别 ocr 是腾讯云，请问怎么样才能实现 自动化填验证码？


51 条回复  **•**  2024-12-22 22:54:20 +08:00

|   |   |   |
|---|---|---|
|![seansong](https://cdn.v2ex.com/gravatar/13b01d3f97cd23d88c602a486ccbc63c?s=48&d=retro)||1<br><br>**[seansong](/member/seansong)**  <br><br>   55 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 10<br><br>很刑|

|   |   |   |
|---|---|---|
|![Abbeyok](https://cdn.v2ex.com/static/img/avatar_normal.png)||2<br><br>**[Abbeyok](/member/Abbeyok)**  <br><br>   55 天前<br><br>ddddocr|

|   |   |   |
|---|---|---|
|![nyxsonsleep](https://cdn.v2ex.com/gravatar/062fe34b18cfc2655220a1e8dc71c723?s=48&d=retro)||3<br><br>**[nyxsonsleep](/member/nyxsonsleep)**  <br><br>   55 天前<br><br>直接买服务，根据难度，会比较贵。  <br>破解验证码本身就能赚钱，技术含量也比爬虫高，甚至可能是里面技术含量最高的内容。|

|   |   |   |
|---|---|---|
|![NoOneNoBody](https://cdn.v2ex.com/gravatar/ade866d803c393db42301082488695d2?s=48&d=retro)||4<br><br>**[NoOneNoBody](/member/NoOneNoBody)**  <br><br>   55 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>[gov.cn](http://gov.cn) ……这个不敢碰|

|   |   |   |
|---|---|---|
|![z1829909](https://cdn.v2ex.com/gravatar/347d6ba181bf07a512c0542c5fb57c56?s=48&d=retro)||5<br><br>**[z1829909](/member/z1829909)**  <br><br>   55 天前 via Android<br><br>既然都 selenium 了，直接拿到页面图片文件送进 ocr 就行了，不用关心他怎么获取的。  <br>顺便，[gov.cn](http://gov.cn) 域名，你最好别搞。|

|   |   |   |
|---|---|---|
|![xuanbg](https://cdn.v2ex.com/avatar/5fdf/eb12/342464_normal.png?m=1534639613)||6<br><br>**[xuanbg](/member/xuanbg)**  <br><br>   55 天前<br><br>V2 真是什么样的人才都有|

|   |   |   |
|---|---|---|
|![dji38838c](https://cdn.v2ex.com/gravatar/ad3c86fa6513571ed8df21f728c42a67?s=48&d=retro)||7<br><br>**[dji38838c](/member/dji38838c)**  <br><br>   55 天前<br><br>水平越初，胆子越大|

|   |   |   |
|---|---|---|
|![klxyy](https://cdn.v2ex.com/avatar/e8e0/6883/615495_normal.png?m=1677050452)||8<br><br>**[klxyy](/member/klxyy)**  <br><br>   55 天前<br><br>[GOV.CN](http://GOV.CN) 你也敢弄，果然很刑|

|   |   |   |
|---|---|---|
|![Leofits](https://cdn.v2ex.com/avatar/1064/cb27/234950_normal.png?m=1689222560)||9<br><br>**[Leofits](/member/Leofits)**  <br><br>   55 天前 via Android<br><br>很刑很可拷|

|   |   |   |
|---|---|---|
|![hanssx](https://cdn.v2ex.com/avatar/5912/4ca0/350569_normal.png?m=1734523135)||10<br><br>**[hanssx](/member/hanssx)**  <br><br>   55 天前<br><br>兄弟，这个 uuid 要是根据客户端生成的，你有点自我暴露了就|

|   |   |   |
|---|---|---|
|![csulyb](https://cdn.v2ex.com/gravatar/d257b6523bc3a5fd7b71c9549c5d5b97?s=48&d=retro)||11<br><br>**[csulyb](/member/csulyb)**  <br><br>   55 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>你想想为啥人家要弄一下验证码？ 本来可以不用弄验证码的，就是因为楼主这样的憨憨 进去太多了|

|   |   |   |
|---|---|---|
|![shadowyue](https://cdn.v2ex.com/avatar/f6ae/0e20/124931_normal.png?m=1732504409)||12<br><br>**[shadowyue](/member/shadowyue)**  <br><br>   55 天前<br><br>很刑，出来了给大家讲讲里边的生活|

|   |   |   |
|---|---|---|
|![vevlins](https://cdn.v2ex.com/avatar/677c/39d0/274232_normal.png?m=1711777186)||13<br><br>**[vevlins](/member/vevlins)**  <br><br>   55 天前<br><br>爬虫把政务网站搞挂被判刑的事你是没听说过？|

|   |   |   |
|---|---|---|
|![huage](https://cdn.v2ex.com/avatar/162a/2584/69678_normal.png?m=1700057630)||14<br><br>**[huage](/member/huage)**  <br><br>   55 天前<br><br>肉身在国外随便搞，在国内老老实实。|

|   |   |   |
|---|---|---|
|![fanhaipeng0403](https://cdn.v2ex.com/gravatar/8f90d52093ca3504dd196f57826778e1?s=48&d=retro)||15<br><br>**[fanhaipeng0403](/member/fanhaipeng0403)**  <br><br>   54 天前<br><br>疯了吧你。|

|   |   |   |
|---|---|---|
|![sir283](https://cdn.v2ex.com/gravatar/c4a8c2c0e54b9af6e5f39404479d1c26?s=48&d=retro)||16<br><br>**[sir283](/member/sir283)**  <br><br>   54 天前<br><br>一、找打码平台，租接口。  <br>二、逆向网页 js ，尝试绕过对应逻辑，使其拿到对应的算法与出入参数，模拟 success 请求。类似中间人。  <br>三、黑掉对方服务器，直接提取数据。  <br>四、自己训练 ocr 模型。  <br>五、放弃。|

|   |   |   |
|---|---|---|
|![TArysiyehua](https://cdn.v2ex.com/gravatar/ba193a88bd6889dcf504d38e8bca792f?s=48&d=retro)||17<br><br>**[TArysiyehua](/member/TArysiyehua)**  <br><br>   54 天前<br><br>提供技术咨询，有意联系|

|   |   |   |
|---|---|---|
|![paopjian](https://cdn.v2ex.com/gravatar/141f86b5cead0224ebc0365353521a26?s=48&d=retro)||18<br><br>**[paopjian](/member/paopjian)**  <br><br>   54 天前<br><br>爬政府网?你在想什么呢|

|   |   |   |
|---|---|---|
|![sampeng](https://cdn.v2ex.com/gravatar/3b198446b72d1e5a3b0090f106a75f3c?s=48&d=retro)||19<br><br>**[sampeng](/member/sampeng)**  <br><br>   54 天前 via iPhone<br><br>刚看完新闻，年底了进去一堆爬虫小子…我还想哪来二的猛人爬个网站把自己送进去。这不就看到，有哥们急着进去吃年夜饭。|

|   |   |   |
|---|---|---|
|![gjw8u8](https://cdn.v2ex.com/gravatar/bd9541589378363b7d6f9f0abe1124a7?s=48&d=retro)||20<br><br>**[gjw8u8](/member/gjw8u8)**  <br><br>   54 天前 via Android<br><br>这个牛逼|

|   |   |   |
|---|---|---|
|![Lukedis](https://cdn.v2ex.com/avatar/6304/a0ce/532512_normal.png?m=1733319904)||21<br><br>**[Lukedis](/member/Lukedis)**  <br><br>   54 天前<br><br>狠人大帝都没你狠，怼着政府网站爬|

|   |   |   |
|---|---|---|
|![ggabc](https://cdn.v2ex.com/avatar/c3f2/4a23/464387_normal.png?m=1620223268)||22<br><br>**[ggabc](/member/ggabc)**  <br><br>   54 天前 via Android<br><br>注意原则|

|   |   |   |
|---|---|---|
|![kele999](https://cdn.v2ex.com/gravatar/d6c5ba6b1d81e1238ddb00b2439f8210?s=48&d=retro)||23<br><br>**[kele999](/member/kele999)**  <br><br>   54 天前<br><br>不要犯罪|

|   |   |   |
|---|---|---|
|![Liftman](https://cdn.v2ex.com/avatar/ee4a/3666/493197_normal.png?m=1737432778)||24<br><br>**[Liftman](/member/Liftman)**  <br><br>   54 天前<br><br>你好，已将您的行为投递到对应网信办。|

|   |   |   |
|---|---|---|
|![opengps](https://cdn.v2ex.com/avatar/1e8a/4d9b/250842_normal.png?m=1722219513)||25<br><br>**[opengps](/member/opengps)**  <br><br>   54 天前<br><br>爬虫不爬 gov 这是底线|

|   |   |   |
|---|---|---|
|![suhu](https://cdn.v2ex.com/avatar/1aaa/be7d/84747_normal.png?m=1734252323)||26<br><br>**[suhu](/member/suhu)**  <br><br>   54 天前<br><br>@[opengps](/member/opengps) robtos.txt 没有禁止的呢，一天只读一次的呢，这种大家没有接触过吗|

|   |   |   |
|---|---|---|
|![raycool](https://cdn.v2ex.com/gravatar/3535e890dad8960697c4f90990c8dca7?s=48&d=retro)||27<br><br>**[raycool](/member/raycool)**  <br><br>   54 天前<br><br>这种验证码没难度，但是这类网站很刑|

|   |   |   |
|---|---|---|
|![opengps](https://cdn.v2ex.com/avatar/1e8a/4d9b/250842_normal.png?m=1722219513)||28<br><br>**[opengps](/member/opengps)**  <br><br>   54 天前<br><br>@[suhu](/member/suhu) gov 级别比 robtos.txt 制定者的级别要高，所以在 gov 眼前一切更低标准都不适用|

|   |   |   |
|---|---|---|
|![Y25tIGxpdmlk](https://cdn.v2ex.com/gravatar/2f59b786fd9cd2ec2b95720531ebbe83?s=48&d=retro)||29<br><br>**[Y25tIGxpdmlk](/member/Y25tIGxpdmlk)**  <br><br>   54 天前<br><br>目测这个验证码没什么难度，用 10 年前的打码技术都能轻松搞定，更何况现在有些 AI 识别和人工打码了。  <br>  <br>还有，验证码哪个不是随机变化的，我还以为是那种 GIF 的动态验证码呢|

|   |   |   |
|---|---|---|
|![et5494](https://cdn.v2ex.com/avatar/b258/2ca0/116902_normal.png?m=1715188164)||30<br><br>**[et5494](/member/et5494)**  <br><br>   54 天前<br><br>0 难度，但是不敢|

|   |   |   |
|---|---|---|
|![guanhui07](https://cdn.v2ex.com/avatar/437f/2914/164143_normal.png?m=1736667690)||31<br><br>**[guanhui07](/member/guanhui07)**  <br><br>   54 天前<br><br>果然很刑|

|   |   |   |
|---|---|---|
|![TophTab](https://cdn.v2ex.com/avatar/5885/11f1/522511_normal.png?m=1609168752)||32<br><br>**[TophTab](/member/TophTab)**  <br><br>   54 天前<br><br>GOV ？老哥干的是体制内的活？  <br>我只知道以前大学老师会去干这个|

|   |   |   |
|---|---|---|
|![EndlessMemory](https://cdn.v2ex.com/avatar/694d/0934/655828_normal.png?m=1717637009)||33<br><br>**[EndlessMemory](/member/EndlessMemory)**  <br><br>   54 天前<br><br>截图识别啊|

|   |   |   |
|---|---|---|
|![wzblog](https://cdn.v2ex.com/avatar/6ac3/c992/358278_normal.png?m=1540790857)||34<br><br>**[wzblog](/member/wzblog)**  <br><br>   54 天前<br><br>放过自己吧，你看他验证码连基本的干扰都不做，随便识别的。搞 gov 很容易吃国家饭的。|

|   |   |   |
|---|---|---|
|![42V0CdLjCU494ogF](https://cdn.v2ex.com/static/img/avatar_normal.png)||35<br><br>**[42V0CdLjCU494ogF](/member/42V0CdLjCU494ogF)**  <br><br>   54 天前<br><br>大把这样的服务商，比如 [https://www.jfbym.com/](https://www.jfbym.com/)  <br>非要自己写的话用 OCR+AI 自己调教一下也够了|

|   |   |   |
|---|---|---|
|![dbow](https://cdn.v2ex.com/gravatar/3cd35089e110d90483a47b85241b85e4?s=48&d=retro)||36<br><br>**[dbow](/member/dbow)**  <br><br>   54 天前<br><br>建议不搞，政府的网站，你也知道的，性能不可能很好，万一被你刷崩了，估计要吃牢饭。|

|   |   |   |
|---|---|---|
|![Ackvincent](https://cdn.v2ex.com/gravatar/bb9d416880e29c4102646717fa5671c9?s=48&d=retro)||37<br><br>**[Ackvincent](/member/Ackvincent)**  <br><br>   54 天前<br><br>直接买服务，不要再验证码上折腾，掉服务商的 API 就行了。|

|   |   |   |
|---|---|---|
|![angryfish](https://cdn.v2ex.com/gravatar/f8c9d67d4c9c784b8ef637ec2d217f5c?s=48&d=retro)||38<br><br>**[angryfish](/member/angryfish)**  <br><br>   54 天前<br><br>即使你可能是某个地市或者啥的供应商，但是你用爬虫把省数据局的网站搞崩了，作为维护系统的乙方，为了能继续拿到这个项目，他们肯定想方设法甩锅，然后你一定会揪出来。然后恭喜你，你可能得进去了。|

|   |   |   |
|---|---|---|
|![isSamle](https://cdn.v2ex.com/avatar/9846/15bf/527523_normal.png?m=1610411826)||39<br><br>**[isSamle](/member/isSamle)**  <br><br>   54 天前<br><br>[https://www.jszwfw.gov.cn/jsjis/component/verifyCode.do?code=4&random=0.41377034550816183](https://www.jszwfw.gov.cn/jsjis/component/verifyCode.do?code=4&random=0.41377034550816183)  <br>通过随机数后端计算返回验证码图片，上 OCR 吧|

|   |   |   |
|---|---|---|
|![chenzi0103](https://cdn.v2ex.com/gravatar/15e86055e7edae5c36e9a75c2c81c68f?s=48&d=retro)||40<br><br>**[chenzi0103](/member/chenzi0103)**  <br><br>   54 天前<br><br>给到 llm 识别就好了 用个好的 llm 模型|

|   |   |   |
|---|---|---|
|![shangfabao](https://cdn.v2ex.com/avatar/4e41/6ad6/228892_normal.png?m=1549954423)||41<br><br>**[shangfabao](/member/shangfabao)**  <br><br>   54 天前<br><br>selenium +ocr,ocr 用的第三方库 搞过|

|   |   |   |
|---|---|---|
|![wty95](https://cdn.v2ex.com/gravatar/7857bc714acf7d348f5c0f74acf7412d?s=48&d=retro)||42<br><br>**[wty95](/member/wty95)**  <br><br>OP<br><br>   54 天前<br><br>@[seansong](/member/seansong) 各位老哥 我不是爬数据的，这个是政府公开中介超市，每天有项目可以报名，摇号中了就做业务，每天一堆报名，根本没精力手动填，所以想自动化报名。  <br>  <br>请问这个也违法么？|

|   |   |   |
|---|---|---|
|![zengxs](https://cdn.v2ex.com/avatar/aacc/d2f0/487121_normal.png?m=1733230152)||43<br><br>**[zengxs](/member/zengxs)**  <br><br>   54 天前<br><br>@[wty95](/member/wty95) 重点不是爬数据，而是你这种行为很容易把网站搞挂  <br>gov 网站大多数本身就做的很垃圾，手动刷刷都有可能挂了，但是你手动刷的他也不能甩锅给你  <br>如果是被你程序刷挂了，恭喜你喜提破坏计算机系统罪|

|   |   |   |
|---|---|---|
|![xuhuanzy](https://cdn.v2ex.com/gravatar/8468578dc697a2adb1f2516922f9862f?s=48&d=retro)||44<br><br>**[xuhuanzy](/member/xuhuanzy)**  <br><br>   54 天前 via Android<br><br>@[wty95](/member/wty95) 他崩了只要查到是你的流量异常，你就百分百入狱。|

|   |   |   |
|---|---|---|
|![lanten](https://cdn.v2ex.com/avatar/9cd9/1022/293805_normal.png?m=1589870628)||45<br><br>**[lanten](/member/lanten)**  <br><br>   54 天前<br><br>有趣的，看到 gov 就吓到腿软|

|   |   |   |
|---|---|---|
|![angryfish](https://cdn.v2ex.com/gravatar/f8c9d67d4c9c784b8ef637ec2d217f5c?s=48&d=retro)||46<br><br>**[angryfish](/member/angryfish)**  <br><br>   53 天前<br><br>@[lanten](/member/lanten) 有时候是百口难辨的。比如前几年的美国一位安全教授通过查看 html 页面获得几位老师的社保号码，被认为是黑客攻击。|

|   |   |   |
|---|---|---|
|![securityCoding](https://cdn.v2ex.com/gravatar/d525abe274d89c3277be2acaefbd0941?s=48&d=retro)||47<br><br>**[securityCoding](/member/securityCoding)**  <br><br>   53 天前<br><br>兄弟，有些内部的爬虫自动识别 [gov.cn](http://gov.cn) 关键词 return 掉。。。|

|   |   |   |
|---|---|---|
|![yuchen198](https://cdn.v2ex.com/gravatar/0fb3f8fde6359665f185a37539a748b9?s=48&d=retro)||48<br><br>**[yuchen198](/member/yuchen198)**  <br><br>   53 天前<br><br>[gov.cn](http://gov.cn) 确实那啥最好别碰，我当时爬了药品监督局几万条数据，不过我那是一次性的，不是每天都要|

|   |   |   |
|---|---|---|
|![seansong](https://cdn.v2ex.com/gravatar/13b01d3f97cd23d88c602a486ccbc63c?s=48&d=retro)||49<br><br>**[seansong](/member/seansong)**  <br><br>   53 天前<br><br>@[wty95](/member/wty95) 你这个自动化报名，不就是典型的非法破坏和入侵计算机系统么，非常刑|

|   |   |   |
|---|---|---|
|![akura](https://cdn.v2ex.com/gravatar/27ac91d138177bc90a628c35a8b44cc9?s=48&d=retro)||50<br><br>**[akura](/member/akura)**  <br><br>   52 天前<br><br>先生大才|

|   |   |   |
|---|---|---|
|![BBBOND](https://cdn.v2ex.com/gravatar/19efda891d7f62eb6cb155cdb5a433b0?s=48&d=retro)||51<br><br>**[BBBOND](/member/BBBOND)**  <br><br>   47 天前<br><br>[https://www.gov.cn/zhengce/content/202409/content_6977766.htm](https://www.gov.cn/zhengce/content/202409/content_6977766.htm)  <br>自 2025 年 1 月 1 日起施行  <br>  <br>第十八条　网络数据处理者使用自动化工具访问、收集网络数据，应当评估对网络服务带来的影响，不得非法侵入他人网络，不得干扰网络服务正常运行。  <br>  <br>第五十五条　违反本条例第十二条、第十六条至第二十条、第二十二条、第四十条第一款和第二款、第四十一条、第四十二条规定的，由网信、电信、公安等主管部门依据各自职责责令改正，给予警告，没收违法所得；拒不改正或者情节严重的，处 100 万元以下罚款，并可以责令暂停相关业务、停业整顿、吊销相关业务许可证或者吊销营业执照，对直接负责的主管人员和其他直接责任人员可以处 1 万元以上 10 万元以下罚款。  <br>  <br>先生请自重|
