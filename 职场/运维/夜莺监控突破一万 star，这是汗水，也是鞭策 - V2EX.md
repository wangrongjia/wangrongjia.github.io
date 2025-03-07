---
link: https://www.v2ex.com/t/1101588
site: V2EX
date: 2024-12-31T15:33
excerpt: 程序员 - @GoRuby - 夜莺监控项目在上周突破了一万 star ，算是一个小小的里程碑。在开源领域，通常把 star
  数量看作项目的繁荣指标，star 数量越多，说明愿意关注你的人越多。这个数字的背后，是一群人对你的鼓励、认
twitter: https://twitter.com/@V2EX
slurped: 2025-01-24T17:00
title: 夜莺监控突破一万 star，这是汗水，也是鞭策 - V2EX
---

夜莺监控项目在上周突破了一万 star ，算是一个小小的里程碑。在开源领域，通常把 star 数量看作项目的繁荣指标，star 数量越多，说明愿意关注你的人越多。这个数字的背后，是一群人对你的鼓励、认可和支持，当然，还有鞭策。夜莺项目最早发起于 2020 年初，发展到现在接近四年时间，本文想借此机会聊聊我们做开源的初心，这四年的感悟，以及多方共赢的商业模式设计。

## 项目简介

![](https://i.imgur.com/vB2nRi6.png)

夜莺项目最初是我们在滴滴的时候开源的，后来捐赠给中国计算机学会开源发展委员会进行托管，以基金会的方式运作。其 github 地址是 [https://github.com/ccfos/nightingale](https://github.com/ccfos/nightingale)，其中 ccfos 就是 CCF OpenSource ，即中国计算机学会开源项目的统一地址。

项目至今，有 130 位 contributor 参与，共提交了 2600 多次 commit ，发版了 170 多次，fork 数 1400 ，docker pull 228k ，虽说我们还有很多不足，但这些数字让我们看到了持续进步的汗水。如果一个开源项目可以坚持投入 4 年，甚至 10 年，20 年，我们坚信它的社会价值会越来越大。

## 项目发起初心

如果聊到项目开源的初心，那得追溯到 10 年前我们开源 open-falcon 那会了，当时确实啥都不懂，就是凭一腔热血为爱发电，当时觉得吧，我们搞了一个自认为还不错的项目，独乐乐不如众乐乐，放出来大家一起完善，项目会越发牛逼。当时的我们，也没有想过什么商业模式，只是想把这个项目做好，让更多人用，让更多人参与。

实际遇到了如下一些问题，如果你也做过开源项目，估计会很有同感：

- 维护者的心理压力大
    - 经常碰到不看文档的小白用户，问各种基础问题。就像一个二年级的小学生经常被问 1+1 等于多少，时间久了，会很厌倦
    - 偶尔会碰到颐指气使的人，用了你的项目，觉得你欠他的的一样，但凡遇到问题，不管是不是自己的问题就恶语相向

![开源项目维护者秒懂的痛苦](https://i.imgur.com/hHzSTFM.png)

- 维护者时间精力有限
    - 大部分开源项目都是维护者兼职在搞，时间精力有限，毕竟养家糊口才是第一位的，搞开源是上层精神层面的追求了
    - 这会导致有些问题处理不够及时，显然，这会导致用户不满。周末照顾家人时收到陌生人提问那也是家常便饭，我不开心，用户也不开心
    - 当维护者调岗跳槽之后，基本就不会继续参与了，这对项目而言是致命的
- 项目功能发展设计其实还是靠你自己
    - 会有水平很高且愿意和你探讨项目设计发展的人，但确实数量不多，毕竟大部分开源项目影响力有限
    - 也会有参与者，通常是小修小改，偶尔还会碰到巨型 PR ，是要改你的命名规范，因为他觉得现有的命名规范不符合他的审美

后来发起夜莺项目，我们就在思考如下这个关键问题：

> 如何才能让一些人才持续全情投入？只要有人持续投入，项目一定会越来越好，不管是功能层面、性能层面，还是文档、社区支持，只要有人持续参与，一切都会越来越好。但是人家得养家糊口啊，除非给人发工资。工资从哪里来？靠项目自身去赚不就行了。于是，，，我们创业了，做了一家公司叫快猫星云。

但是，事情远没有这么简单。

## 开源和商业的天然悖论

我们想到的第一个模式是靠技术 Support ，因为 RedHat 就是这么干的。普通用户提供社区支持，商业用户提供商业支持，如果客户在生产环境部署了你的软件，为了防止紧急生产故障，买个 Support 以防万一，这理所当然，看起来是个好模式。但也仅仅是看起来，实操中会发现如下问题：

- 监控、可观测性系统，我们觉得是 P0 级服务，但是很多客户觉得不影响核心系统所以没关系，重视程度不高，如果是核心 DB 或 OS ，那就不一样了
- 开源做的越好，比如功能越稳定、丰富，文档越完备，用户遇到的问题越少，越不需要 Support ，如果开源做的不好，用户量起不来，也不会有商业用户
- 边界不好界定。如果只是夜莺软件本身出问题我们来提供支持理所当然，那客户问这个 promql 怎么写？达梦数据库怎么监控？这些问题就很难界定了

所以，技术 Support 根本没有大规模商业化的底层逻辑支撑。如果你只是个人项目，养活自己就行，或者只是想赚点外快，这个模式或许还行，如果只是想养活几个人，这个模式我都觉得很难。

另外，开源监控、可观测性项目，可选择的项目还比较多，你如果收费，别家免费，即便你做的更好，也很难有人买单。你有养家糊口的压力，但是其他有些项目的研发人员人家已经财务自由了，人家就是可以全职不拿钱做开源，你怎么办？

## 多方共赢的商业模式设计

其他领域不敢讲，监控、可观测性这个领域，如何设计一个多方共赢的商业模式？我的个人观点（注意，只是个人观点）如下：

- 开源的部分，需要是功能闭环的，即，不依赖商业功能也能用的起来。而且这部分功能要足够好，让用户觉得用的很爽，这样才能吸引用户。这部分承接了我们的精神层面的诉求以及商业营销层面的诉求。这部分功能，我们可以把它叫做社区版。我们要在社区版这块投入全职人力，给他们发工资做开源。
- 没有预算的开源用户，可以免费使用社区版，有社区提供的技术支持，虽然响应速度没有商业版快，总还会有人响应，比那些动不动就撂挑子的开源项目会强很多。
- 有预算的用户，可以购买商业版，商业版的功能要比社区版更强大，技术支持也更及时。比如开源版会重点做告警引擎功能，而商业版会做大一统的可观测性平台。其定位不能相同，定位相同了就没法取舍，比如一个功能是放社区版还是商业版，就很难界定了。

其他一些 ToB 商业公司同行可能会觉得我们这种做法就是毒瘤。因为我们开源的部分抢了他们的生意，但实际上，我们开源的是基础监控告警能力，即便没有我们，还是会有 Prometheus ，会有 Zabbix 这些前辈在，如果 ToB 公司的生意能够被开源项目抢走，说明你的产品能力可能还需要加强。而社区版也承载了我们的精神层面的诉求，我们希望为社会提供一个好用的监控系统，让更多人受益，这是初心，我们不可能放弃。

## 活下去是责任，留下点什么才是关键价值

有些创业导师说，如果你只是为了钱，那不应该创业。实际上，创业的原因哪能是单一的。肯定是既要又要还要啊。

- 既要赚到钱，养家糊口，发得起工资，这是责任
- 又要部分员工可以全职做开源，满足一下精神层面的需求
- 还要让飞轮转起来，越做越好越做越大，让各方受益

如果，我是说如果，我们站在生命的尽头，回首往事，什么会相对更有价值？我想，可能是过程中一起经历的风雨，以及我们生命留下的痕迹，我们在开源项目上的付出，可能会是我这碌碌无为的一生中最深的那个痕迹了吧。

|   |   |   |
|---|---|---|
|![akin520](https://cdn.v2ex.com/avatar/ef95/b846/38097_normal.png?m=1658454100)||1<br><br>**[akin520](https://www.v2ex.com/member/akin520)**      24 天前<br><br>项目是好项目，主要是根不上你更新的速度|

|   |   |   |
|---|---|---|
|![wonderfulcxm](https://cdn.v2ex.com/avatar/06b8/e0c9/104939_normal.png?m=1708680914)||2<br><br>**[wonderfulcxm](https://www.v2ex.com/member/wonderfulcxm)**      24 天前 via iPhone<br><br>我是第一次看到这个项目，请问支持监控多台服务器吗？我想替换掉哪咤面板。|

|   |   |   |
|---|---|---|
|![southwolf](https://cdn.v2ex.com/avatar/8d31/7bdc/747_normal.png?m=1454115578)||4<br><br>**[southwolf](https://www.v2ex.com/member/southwolf)**      24 天前 via Android<br><br>open-falcon 时代就关注了。。。加油！|

|   |   |   |
|---|---|---|
|![arfa](https://cdn.v2ex.com/gravatar/07ec8d098203ee9d1d75241a3a44f6a3?s=48&d=retro)||5<br><br>**[arfa](https://www.v2ex.com/member/arfa)**      24 天前<br><br>项目是好项目， 建议你们别把大版本更新这么快|

|   |   |   |
|---|---|---|
|![GoRuby](https://cdn.v2ex.com/avatar/4914/047d/59895_normal.png?m=1735688836)||9<br><br>**[GoRuby](https://www.v2ex.com/member/GoRuby)**      24 天前<br><br>@[arfa](https://www.v2ex.com/member/arfa) 收到。正式大版本一般是每年 7 月底夜莺大会上发版。小版本其实可以不用更新，不过很多人希望尽快拿到小版本的 feature 所以我们只要开发完了一点功能就会放出去|

|   |   |   |
|---|---|---|
|![GoRuby](https://cdn.v2ex.com/avatar/4914/047d/59895_normal.png?m=1735688836)||11<br><br>**[GoRuby](https://www.v2ex.com/member/GoRuby)**      24 天前<br><br>@[wonderfulcxm](https://www.v2ex.com/member/wonderfulcxm) 支持。在服务器上部署一个 agent ，就可以监控了。我们一般建议安装 categraf 作为 agent ，也可以使用 telegraf 、datadog-agent 、grafana-agent 等其他 agent|

|   |   |   |
|---|---|---|
|![GoRuby](https://cdn.v2ex.com/avatar/4914/047d/59895_normal.png?m=1735688836)||12<br><br>**[GoRuby](https://www.v2ex.com/member/GoRuby)**      24 天前<br><br>@[akin520](https://www.v2ex.com/member/akin520) 收到。正式版一般是每年 7 月底夜莺大会上发版。小版本其实可以不用更新，不过很多人希望尽快拿到小版本的 feature 所以我们只要开发完了一点功能就会放出去|

|   |   |   |
|---|---|---|
|![swulling](https://cdn.v2ex.com/avatar/1ed3/f6c5/22404_normal.png?m=1340101995)||13<br><br>**[swulling](https://www.v2ex.com/member/swulling)**      24 天前 via iPhone<br><br>目前业界的模式是社区版提供的都是适合小规模个人、小团队、开发者使用的。其他的走商业版。<br><br>有几个收费的点：<br><br>1.UI ，社区版不提供或者只提供最简单的 UI  <br>2. 多租户。  <br>3. 分布式。社区版提供一个单点应用。  <br>4. 高级功能。社区版只提供最核心的功能。|

|   |   |   |
|---|---|---|
|![GoRuby](https://cdn.v2ex.com/avatar/4914/047d/59895_normal.png?m=1735688836)||14<br><br>**[GoRuby](https://www.v2ex.com/member/GoRuby)**      24 天前<br><br>@[swulling](https://www.v2ex.com/member/swulling) 补充一个点。国外赚钱感觉主要靠的是 Cloud 版本。而国内对 SaaS 模式不感冒，导致国内的模式和国外相比，有些差异。|

|   |   |   |
|---|---|---|
|![arfa](https://cdn.v2ex.com/gravatar/07ec8d098203ee9d1d75241a3a44f6a3?s=48&d=retro)||16<br><br>**[arfa](https://www.v2ex.com/member/arfa)**      24 天前<br><br>我觉得可以学一下禅道，虽然有点反感，但是人家这个赚钱的模式真心不错|

|   |   |   |
|---|---|---|
|![arfa](https://cdn.v2ex.com/gravatar/07ec8d098203ee9d1d75241a3a44f6a3?s=48&d=retro)||17<br><br>**[arfa](https://www.v2ex.com/member/arfa)**      24 天前<br><br>open-falcon 时，我也试玩过，但是当时觉得还不如 zabbix 方便，但是 nightingale 不一样了，使用起来就方便多了！|

|   |   |   |
|---|---|---|
|![accfcx](https://cdn.v2ex.com/avatar/d344/546a/221045_normal.png?m=1664765459)||18<br><br>**[accfcx](https://www.v2ex.com/member/accfcx)**      24 天前<br><br>支持。20 年时有同学在弹性云组下面，当时给我说夜莺是云那边的几个老板一起开源的，在这里又一次看见，感慨|

|   |   |   |
|---|---|---|
|![GoRuby](https://cdn.v2ex.com/avatar/4914/047d/59895_normal.png?m=1735688836)||19<br><br>**[GoRuby](https://www.v2ex.com/member/GoRuby)**      24 天前<br><br>@[arfa](https://www.v2ex.com/member/arfa) 能否稍微点拨两句禅道的商业模式？我们也好有针对性的学习下:)|

|   |   |   |
|---|---|---|
|![GoRuby](https://cdn.v2ex.com/avatar/4914/047d/59895_normal.png?m=1735688836)||24<br><br>**[GoRuby](https://www.v2ex.com/member/GoRuby)**      23 天前<br><br>@[PROJECT](https://www.v2ex.com/member/PROJECT) 夜莺自身实际就是一个二进制，直接启动就行了，只是有其他依赖，依赖 mysql 、redis ，如果要一键启动，可以使用默认提供的 docker compose 方式启动。如果只是临时测试，可以使用 v8.beta2 之后的版本，这个版本之后的版本，可以选择不依赖 mysql 、redis ，直接只使用二进制启动~|

|   |   |   |
|---|---|---|
|![matrix1010](https://cdn.v2ex.com/avatar/1eb9/c2c7/264857_normal.png?m=1733286302)||28<br><br>**[matrix1010](https://www.v2ex.com/member/matrix1010)**      23 天前   ![❤️](https://www.v2ex.com/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 2<br><br>其实我只要项目 star 过 100 就基本不怎么看这个了，而是看 CI ，看文档，看 issue 活跃度和质量这些。比如对比你的 CI 和 Grafana 的 CI 差别就十分巨大，你的项目 CI 里连测试这一步都没有。问基础问题的小白用户一般也不会是公司技术专家之类的，不太可能带来生意，最多也就能提供 star+1 的价值。不卑不亢回复就行|

|   |   |   |
|---|---|---|
|![Steaven](https://cdn.v2ex.com/avatar/d910/4bdb/550187_normal.png?m=1711454731)||30<br><br>**[Steaven](https://www.v2ex.com/member/Steaven)**      23 天前<br><br>open-falcon 时，就在使用了，这么些年还一直是，我被离职了，还一直是，没有升级过😓|

|   |   |   |
|---|---|---|
|![GoRuby](https://cdn.v2ex.com/avatar/4914/047d/59895_normal.png?m=1735688836)||31<br><br>**[GoRuby](https://www.v2ex.com/member/GoRuby)**      23 天前<br><br>@[matrix1010](https://www.v2ex.com/member/matrix1010) 项目后期其实我已经很少写代码了，项目前期我写的比较多。测试与否这块倒是可以聊聊。可能跟我的经历有关，我刚毕业那会，在一个大厂，我们组有个大牛从来不写单测，也不要 QA 同事协助，但是他的代码质量很高，极少听到用户反馈他负责的部分哪哪有 bug ，而组里那些配备了 QA 同时还声称 TDD 开发模式的同事，从质量结果来看，却不尽人意。<br><br>不写单测不代表不测，我现在的习惯是，一般很重视功能测试，一个功能跑通了，N 多个方法的正常路径就都跑通了，我个人觉得效率很高。监控系统，不像底层的 OS 、DB ，如果是 OS 、DB ，我觉得得有非常非常完备的 CI ，但是监控系统，作为一个上层系统，功能迭代较快，我感觉把功能测好就挺好了。<br><br>以上，纯探讨，纯个人观点。|

|   |   |   |
|---|---|---|
|![matrix1010](https://cdn.v2ex.com/avatar/1eb9/c2c7/264857_normal.png?m=1733286302)||35<br><br>**[matrix1010](https://www.v2ex.com/member/matrix1010)**      23 天前   ![❤️](https://www.v2ex.com/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>@[GoRuby](https://www.v2ex.com/member/GoRuby) 你这个无法考证的个例我不评论。但做开源并且想赚钱，一定要想清楚谁会为你付钱，仅靠国内这样的风气/环境能不能赚钱。如果面向世界，那些可能付费的程序员/公司看重的是什么。star 其实是各种指标里最没用的一个，给你点 star 的人和深度使用的人很有可能重叠很小|

|   |   |   |
|---|---|---|
|![Dxxxxs](https://cdn.v2ex.com/avatar/c1f6/bfd2/390146_normal.png?m=1715870197)||37<br><br>**[Dxxxxs](https://www.v2ex.com/member/Dxxxxs)**      23 天前<br><br>看来当年在滴滴云实习的时候的时候和大佬同组过，支持一下|

|   |   |   |
|---|---|---|
|![huangliu](https://cdn.v2ex.com/avatar/cd29/2a17/354479_normal.png?m=1713092890)||41<br><br>**[huangliu](https://www.v2ex.com/member/huangliu)**      22 天前<br><br>好项目，年初的时候有个同学还给我说他们公司也是基于夜莺进行二开的。开源项目要盈利或者说养活一个公司实在太难了，楼主已经做得很好了😂|

|   |   |   |
|---|---|---|
|![dfdd1811](https://cdn.v2ex.com/gravatar/f5123102c1a325f0f22c81c7d36f67d7?s=48&d=retro)||42<br><br>**[dfdd1811](https://www.v2ex.com/member/dfdd1811)**      22 天前<br><br>看着不错，但我的 1h1g 轻量实在是承受不了 mysql 和 redis…|

|   |   |   |
|---|---|---|
|![codingmiao](https://cdn.v2ex.com/avatar/fd6b/5bbe/582929_normal.png?m=1715870282)||45<br><br>**[codingmiao](https://www.v2ex.com/member/codingmiao)**      21 天前<br><br>不错，正好最近在找把 Prometheus 这个笨重的家伙换掉的方案。  <br>话说顺便看了下 ccfos 这个组织，唯一一个项目就是夜莺，就有点唏嘘，开源要走的路还很长很艰难呀。。|

|   |   |   |
|---|---|---|
|![supersu](https://cdn.v2ex.com/avatar/581e/8e6b/73962_normal.png?m=1456397246)||47<br><br>**[supersu](https://www.v2ex.com/member/supersu)**      17 天前 via Android<br><br>十年前关注过 open falcon ，稀里糊涂的倒腾 zabbix ，grafana 也快断断续续十年了，不知道有 telegram 群主不|

https://github.com/ccfos/nightingale

夜莺 Nightingale 是什么，解决什么问题？以大家都很熟悉的 Grafana 做个类比，**Grafana 擅长对接各种各样的数据源，然后提供灵活、强大、好看的可视化面板**。夜莺则擅长对接各种多样的数据源，提供灵活、强大、高效的监控告警管理能力。从发展路径和定位来说，夜莺和 Grafana 很像，可以总结为一句话：**可视化就用 Grafana，监控告警就找夜莺。**

在可视化领域，Grafana 是毫无争议的领导者，Grafana 在影响力、装机量、用户群、开发者数量等各个维度的数字上，相比夜莺都是追赶的榜样。巨无霸往往都是从一个切入点打开局面的，**Grafana Labs 有了在可视化领域 Grafana 这个王牌，逐步扩展到整个可观测性方向，比如 Logging 维度有 Loki，Tracing 维度有 Tempo，Profiling 维度有收购来的 Pyroscope，On-call 维度有同样是收购来的 Grafana-OnCall 项目，还有时序数据库 Mimir、eBPF 采集器 Beyla、OpenTelemetry 采集器 Alloy、前端监控 SDK Faro，最终构成了一个完整的可观测性工具矩阵，但整个飞轮都是从 Grafana 项目开始转动起来的。**

夜莺，则是从监控告警这个切入点打开局面，也逐步横向做了相应扩展，比如夜莺也自研了可视化面板，如果你想有一个 all-in-one 的监控告警+可视化的工具，那么用夜莺也是正确的选择；比如 OnCall 方向，夜莺可以和 [Flashduty SaaS](https://flashcat.cloud/product/flashcat-duty/) 服务无缝的集成；在采集器方向，夜莺有配套的 [Categraf](https://flashcat.cloud/product/categraf)，可以一个采集器中管理所有的 exporter，并同时支持指标和日志的采集，极大减轻工程师维护的采集器数量和工作量（这个点太痛了，你可能也遇到过业务团队吐槽采集器数量比业务应用进程数量还多的窘况吧）。