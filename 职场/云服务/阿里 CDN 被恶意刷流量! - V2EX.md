---
link: https://www.v2ex.com/t/1101615
site: V2EX
date: 2024-12-31T16:38
excerpt: "程序员 - @lthero - ## 说明本人在 github 部署了静态网页博客，使用阿里云的 cdn 进行加速，最近发现 cdn
  流量异常异常表现：晚上 20 点到 2 点期间刷了 4GB 流量，访问 10w+次；并"
twitter: https://twitter.com/@V2EX
slurped: 2025-01-24T16:51
title: 阿里 CDN 被恶意刷流量! - V2EX
---
  

# 阿里 CDN 被恶意刷流量!

 [1](javascript:)  [

](javascript:)

  [lthero](/member/lthero) · 24 天前 · 3818 次点击

## 说明

本人在 github 部署了静态网页博客，使用阿里云的 cdn 进行加速，最近发现 cdn 流量异常

异常表现：晚上 20 点到 2 点期间刷了 4GB 流量，访问 10w+次；并不是每天都有，最近是隔一周左右发生一次

## 处理

好在阿里云提供了查询 ip 的接口（接口还被藏起来了）

[https://next.api.aliyun.com/api/Cdn/2018-05-10/DescribeDomainTopClientIpVisit](https://next.api.aliyun.com/api/Cdn/2018-05-10/DescribeDomainTopClientIpVisit)

返回结果如下

_仅一天内的访问情况_

```
  "ClientIpList": [
    {
      "Acc": 172871,
      "Traffic": 1932827800, #Byte,大概 2GB
      "Rank": 1,
      "ClientIp": "1.202.114.36"
    },
```

## 坏蛋 ip

**1.202.114.36**

**1.202.114.242**

北京电信的



48 条回复  **•**  2025-01-01 21:24:29 +08:00

|                                                                                   |     |                                                                                                                                                                               |
| --------------------------------------------------------------------------------- | --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ![summerwar](https://cdn.v2ex.com/avatar/0ed3/c59f/61831_normal.png?m=1545304008) |     | 1<br><br>**[summerwar](/member/summerwar)**  <br><br>   24 天前<br><br>前一段不是好多刷 cdn 流量的吗？尤其是组团刷下载的那些，这个问题无解。  <br>  <br>我个人是**把网站都扔 cloudflare pages** 了，国内随缘打开，但是可以睡个安稳觉，啥都不用管 |

|   |   |   |
|---|---|---|
|![TwilightCool](https://cdn.v2ex.com/avatar/df4c/6843/321406_normal.png?m=1538297106)||2<br><br>**[TwilightCool](/member/TwilightCool)**  <br><br>   24 天前<br><br>终于撞了一个头像了~|

|                                                                                        |     |                                                                                                                                                                 |
| -------------------------------------------------------------------------------------- | --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ![skallz](https://cdn.v2ex.com/gravatar/e2d66edb8b18a0aa97b9f7b21d6e1258?s=48&d=retro) |     | 3<br><br>**[skallz](/member/skallz)**  <br><br>   23 天前<br><br>查 ip 没用的，极大概率查不到是谁，首先云服务商自己就会刷流量，其次很多其他用途也会刷流量（只要你的域名暴露），**最稳妥的方式还是用服务器，大不了被刷到服务器带宽瘫痪**，好过被刷到欠费！ |

|   |   |   |
|---|---|---|
|![lucasdev](https://cdn.v2ex.com/avatar/d2be/d4e0/504225_normal.png?m=1723687429)||4<br><br>**[lucasdev](/member/lucasdev)**  <br><br>   23 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>[https://ping0.cc/ip/1.202.114.36](https://ping0.cc/ip/1.202.114.36)  <br>  <br>[![](https://i.imgur.com/xdq7UV3.png)](https://i.imgur.com/xdq7UV3.png)  <br>  <br>[![](https://i.imgur.com/KT1Z2Vi.png)](https://i.imgur.com/KT1Z2Vi.png)|

|   |   |   |
|---|---|---|
|![duzhuo](https://cdn.v2ex.com/avatar/49be/b5d0/487393_normal.png?m=1681874677)||5<br><br>**[duzhuo](/member/duzhuo)**  <br><br>   23 天前<br><br>刷的什么 图片吗|

|   |   |   |
|---|---|---|
|![lthero](https://cdn.v2ex.com/gravatar/77b27233e67963633225abbccf560168?s=48&d=retro)||6<br><br>**[lthero](/member/lthero)**  <br><br>OP<br><br>   23 天前<br><br>@[lucasdev](/member/lucasdev) #4 好工具，收藏了🥰|

|   |   |   |
|---|---|---|
|![lthero](https://cdn.v2ex.com/gravatar/77b27233e67963633225abbccf560168?s=48&d=retro)||7<br><br>**[lthero](/member/lthero)**  <br><br>OP<br><br>   23 天前<br><br>@[duzhuo](/member/duzhuo) #5 对，对着图片一直刷🤡|

|                                                                                 |     |                                                                                                                                                                                                                                                                                                                                                                                       |
| ------------------------------------------------------------------------------- | --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ![sggggy](https://cdn.v2ex.com/avatar/591a/ff29/341587_normal.png?m=1730443583) |     | 8<br><br>**[sggggy](/member/sggggy)**  <br><br>   23 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 2<br><br>可以切换到 **dcdn ，然后用边缘脚本自定义策略，尝试是否能判断指定 url 的请求来源**（请求头 referer ），  <br>用正则表达式匹配 URL 路径。  <br>  <br>策略：如果路径匹配，脚本会接着检查请求来源是否来自预期的域名地址，如果不是就拒绝请求。  <br>  <br>这个遇到过，之前被刷了 18 个 T ，用边缘脚本来做策略，彻底解决了，如果只用 dcdn 默认的规则不能彻底封杀，只要 对方 IP 足够多，还是能够一直刷流量。 |

|   |   |   |
|---|---|---|
|![gitdoit](https://cdn.v2ex.com/gravatar/0f9df604e7c6e3fdbc9e891a641b8ab6?s=48&d=retro)||9<br><br>**[gitdoit](/member/gitdoit)**  <br><br>   23 天前<br><br>哼~ 坏蛋|

|   |   |   |
|---|---|---|
|![lthero](https://cdn.v2ex.com/gravatar/77b27233e67963633225abbccf560168?s=48&d=retro)||10<br><br>**[lthero](/member/lthero)**  <br><br>OP<br><br>   23 天前<br><br>@[sggggy](/member/sggggy) #8 哇靠 18TB ，畜生啊；谢谢！我可以尝试下这方案|

|   |   |   |
|---|---|---|
|![proxychains](https://cdn.v2ex.com/avatar/19d0/007e/514234_normal.png?m=1678778024)||11<br><br>**[proxychains](/member/proxychains)**  <br><br>   23 天前<br><br>PCDN 刷下行量的|

|   |   |   |
|---|---|---|
|![duzhuo](https://cdn.v2ex.com/avatar/49be/b5d0/487393_normal.png?m=1681874677)||12<br><br>**[duzhuo](/member/duzhuo)**  <br><br>   23 天前<br><br>@[lthero](/member/lthero) [https://developers.cloudflare.com/r2/pricing/](https://developers.cloudflare.com/r2/pricing/) 直接跑了得了，惹不起哈哈|

|   |   |   |
|---|---|---|
|![moro](https://cdn.v2ex.com/avatar/84fd/bc3a/4702_normal.png?m=1432214209)||13<br><br>**[moro](/member/moro)**  <br><br>   23 天前<br><br>只有运营商才有这个动机。|

|   |   |   |
|---|---|---|
|![googlefans](https://cdn.v2ex.com/avatar/27b5/429c/28881_normal.png?m=1351474159)||14<br><br>**[googlefans](/member/googlefans)**  <br><br>   23 天前<br><br>@[skallz](/member/skallz) 我是把配置弄得很低，一访问就 down 机。|

|   |   |   |
|---|---|---|
|![lupus721](https://cdn.v2ex.com/avatar/2639/03fb/28823_normal.png?m=1371806895)||15<br><br>**[lupus721](/member/lupus721)**  <br><br>   23 天前<br><br>真是不明白，这些人图啥|

|                                                                                 |     |                                                                                                                                                                                                                                                                                                                             |
| ------------------------------------------------------------------------------- | --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ![yuzo555](https://cdn.v2ex.com/avatar/59c0/0e37/94227_normal.png?m=1731399453) |     | 16<br><br>**[yuzo555](/member/yuzo555)**  <br><br>   23 天前<br><br>[https://www.dogecloud.com/announcement/26](https://www.dogecloud.com/announcement/26)  <br>供参考。  <br>**建议设置好流量封顶**，设置到自己能接受的流量值，比如每天最多 10GB 、20GB 之类的，另外也可以定期查看访问 IP 排行进行封禁，高频率攻击的话可以设置 IP 访问频率 QPS 限制。  <br>异常流量时间段可以下载日志文件，查看攻击者的访问特征（比如 UA 特征等），精准屏蔽。 |

|   |   |   |
|---|---|---|
|![lthero](https://cdn.v2ex.com/gravatar/77b27233e67963633225abbccf560168?s=48&d=retro)||17<br><br>**[lthero](/member/lthero)**  <br><br>OP<br><br>   23 天前<br><br>@[yuzo555](/member/yuzo555) #16 谢谢！刚刚设置了流量封顶和带宽限制，过阵子看看效果|

|                                                                                        |     |                                                                                                                                                   |
| -------------------------------------------------------------------------------------- | --- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| ![lthero](https://cdn.v2ex.com/gravatar/77b27233e67963633225abbccf560168?s=48&d=retro) |     | 18<br><br>**[lthero](/member/lthero)**  <br><br>OP<br><br>   23 天前<br>**<br>@[lupus721](/member/lupus721) #15 听**说是 PCDN 刷下行流量的，和上行流量对冲，避免被运营商查水表 |

|                                                                                 |     |                                                                                                                 |
| ------------------------------------------------------------------------------- | --- | --------------------------------------------------------------------------------------------------------------- |
| ![lambdaq](https://cdn.v2ex.com/avatar/8553/adf9/10426_normal.png?m=1688377906) |     | 19<br><br>**[lambdaq](/member/lambdaq)**  <br><br>   23 天前<br><br>问题，cdn 如果缺收入了，业务员随机挑一个受害者扔给 pcdn 或者 ddos 组织吗？ |

|   |   |   |
|---|---|---|
|![liuidetmks](https://cdn.v2ex.com/avatar/e540/71e7/220603_normal.png?m=1732845678)||20<br><br>**[liuidetmks](/member/liuidetmks)**  <br><br>   23 天前<br><br>@[lambdaq](/member/lambdaq) 不是没可能。  <br>  <br>这环境，所有绑卡的都不搞|

|                                                                                     |     |                                                                                                                                                                                                        |
| ----------------------------------------------------------------------------------- | --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ![AEnjoyable](https://cdn.v2ex.com/avatar/af0b/0ec5/668228_normal.png?m=1716786434) |     | 21<br><br>**[AEnjoyable](/member/AEnjoyable)**  <br><br>   23 天前<br><br>我觉得北京电信 1.202/16 和 1.203/16 这两个 IP 段特别脏  <br>我们公司的电信出口在这里面，打开好些网站都是 403 一查 公司 IP 高风险  <br>  <br>然后就是这个网段里还有不少电信机房的机器，老是扫我的 vps |

|   |   |   |
|---|---|---|
|![xmumiffy](https://cdn.v2ex.com/avatar/17d3/d5c9/71891_normal.png?m=1422346356)||22<br><br>**[xmumiffy](/member/xmumiffy)**  <br><br>   23 天前 via Android<br><br>卖房 CDN 的日常😂|

|                                                                                   |     |                                                                                                                                                                |
| --------------------------------------------------------------------------------- | --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ![liuzimin](https://cdn.v2ex.com/avatar/ee48/0000/133755_normal.png?m=1735175970) |     | 23<br><br>**[liuzimin](/member/liuzimin)**  <br><br>   23 天前 via Android<br><br>@[sggggy](/member/sggggy) 我也是用 dcdn 的 waf 策略解决的。不过我是按流量阈值的。短时间内超过一定流量就把 ip 拉黑。 |

|                                                                                            |     |                                                                                                            |
| ------------------------------------------------------------------------------------------ | --- | ---------------------------------------------------------------------------------------------------------- |
| ![tjiaming99](https://cdn.v2ex.com/gravatar/a7946423064cfae1ff3a86d20dd27d66?s=48&d=retro) |     | 24<br><br>**[tjiaming99](/member/tjiaming99)**  <br><br>   23 天前<br><br>之前 VPS 被刷了一个 T 心疼的要死，你这赶上大出血了/haha |

|   |   |   |
|---|---|---|
|![Gilfoyle26](https://cdn.v2ex.com/avatar/f259/fba5/687708_normal.png?m=1716718653)||25<br><br>**[Gilfoyle26](/member/Gilfoyle26)**  <br><br>   23 天前<br><br>阿里云对这种情况也熟视无睹？？？这么做生意也能赚到钱，真是神奇。|

|                                                                                            |     |                                                                                                                                                                                                                                                                                                        |
| ------------------------------------------------------------------------------------------ | --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ![MagmaBlock](https://cdn.v2ex.com/gravatar/1204cb5fcf8de1205652f91467448f5f?s=48&d=retro) |     | 26<br><br>**[MagmaBlock](/member/MagmaBlock)**  <br><br>   23 天前 via Android<br><br>[https://www.dogecloud.com/announcement/26](https://www.dogecloud.com/announcement/26)  <br>  <br>今年我也遇到了，一个十八线不知名小博客都有被刷  <br>好在设置了流量上限，没造成啥损失  <br>  <br>对互联网提供服务，就要想好被恶意攻击的情况，前几年没 PCDN 的时候也遇见过恶意刷流量的。网线对面什么人都有 |

|                                                                                           |     |                                                                                                                   |
| ----------------------------------------------------------------------------------------- | --- | ----------------------------------------------------------------------------------------------------------------- |
| ![macaodoll](https://cdn.v2ex.com/gravatar/00305826ca0b60144a020c9775b6d1f6?s=48&d=retro) |     | 27<br><br>**[macaodoll](/member/macaodoll)**  <br><br>   23 天前<br><br>记得前几个月也有老哥说过这个事情，下面评论说是阿里自己用山西的 IP 批量刷的，参考下 |

|   |   |   |
|---|---|---|
|![mrzzoxo](https://cdn.v2ex.com/gravatar/f6e533c524d254ec536eb9008aa0eca7?s=48&d=retro)||28<br><br>**[mrzzoxo](/member/mrzzoxo)**  <br><br>   23 天前<br><br>博客？  <br>如果没涉及商业的话  <br>建议丢 cloud flare 好了，又不影响访问|

|   |   |   |
|---|---|---|
|![lthero](https://cdn.v2ex.com/gravatar/77b27233e67963633225abbccf560168?s=48&d=retro)||29<br><br>**[lthero](/member/lthero)**  <br><br>OP<br><br>   23 天前<br><br>@[macaodoll](/member/macaodoll) #27 对！也搜到了那篇帖子，我估计我的也是被拿去刷 pcdn 了|

|   |   |   |
|---|---|---|
|![lthero](https://cdn.v2ex.com/gravatar/77b27233e67963633225abbccf560168?s=48&d=retro)||30<br><br>**[lthero](/member/lthero)**  <br><br>OP<br><br>   23 天前<br><br>@[Gilfoyle26](/member/Gilfoyle26) #25 阿里云的 cdn 上倒是发了一条提醒，说最近有这种情况出现，警惕用户要处理|

|   |   |   |
|---|---|---|
|![lthero](https://cdn.v2ex.com/gravatar/77b27233e67963633225abbccf560168?s=48&d=retro)||31<br><br>**[lthero](/member/lthero)**  <br><br>OP<br><br>   23 天前<br><br>@[AEnjoyable](/member/AEnjoyable) #21 好！这网段全禁了先👀|

|   |   |   |
|---|---|---|
|![lthero](https://cdn.v2ex.com/gravatar/77b27233e67963633225abbccf560168?s=48&d=retro)||32<br><br>**[lthero](/member/lthero)**  <br><br>OP<br><br>   23 天前<br><br>@[MagmaBlock](/member/MagmaBlock) #26 哎，小博客都被抓着刷，挺难受的|

|   |   |   |
|---|---|---|
|![realpg](https://cdn.v2ex.com/avatar/71ee/202d/119683_normal.png?m=1675800870)||33<br><br>**[realpg](/member/realpg)**  <br><br>   23 天前<br><br>@[summerwar](/member/summerwar) #1  <br>所以有没有渠道介绍点这种需要刷下行流量的给我  <br>我有一些 cdn 需要别人帮我刷点下行流量做业绩|

|   |   |   |
|---|---|---|
|![lthero](https://cdn.v2ex.com/gravatar/77b27233e67963633225abbccf560168?s=48&d=retro)||34<br><br>**[lthero](/member/lthero)**  <br><br>OP<br><br>   23 天前<br><br>各位新年快乐|

|   |   |   |
|---|---|---|
|![AEnjoyable](https://cdn.v2ex.com/avatar/af0b/0ec5/668228_normal.png?m=1716786434)||35<br><br>**[AEnjoyable](/member/AEnjoyable)**  <br><br>   23 天前 via Android<br><br>@[lthero](/member/lthero) #31 这里面还有少量的北京电信移动网络...|

|   |   |   |
|---|---|---|
|![buildops](https://cdn.v2ex.com/avatar/af7b/9a7f/148306_normal.png?m=1448773167)||36<br><br>**[buildops](/member/buildops)**  <br><br>   23 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>建议可以收集好证据，然后到工信部平台投诉（ IP 对应的运营商）查处这些涉嫌违法的 IP： [https://ts.isc.org.cn](https://ts.isc.org.cn) 或 [https://yhssglxt.miit.gov.cn](https://yhssglxt.miit.gov.cn)|

|   |   |   |
|---|---|---|
|![buildops](https://cdn.v2ex.com/avatar/af7b/9a7f/148306_normal.png?m=1448773167)||37<br><br>**[buildops](/member/buildops)**  <br><br>   23 天前<br><br>有个向工信部投诉成功的 case： [https://www.idcbuy.net/talk/3242.html](https://www.idcbuy.net/talk/3242.html)|

|   |   |   |
|---|---|---|
|![summerwar](https://cdn.v2ex.com/avatar/0ed3/c59f/61831_normal.png?m=1545304008)||38<br><br>**[summerwar](/member/summerwar)**  <br><br>   23 天前<br><br>@[realpg](/member/realpg) 直接写个脚本一直循环请求大文件就是了，不需要别人，自己都能搞|

|   |   |   |
|---|---|---|
|![kele999](https://cdn.v2ex.com/gravatar/d6c5ba6b1d81e1238ddb00b2439f8210?s=48&d=retro)||39<br><br>**[kele999](/member/kele999)**  <br><br>   23 天前<br><br>开 refer 限制，开下行速率限制，开 IP 请求频率限制|

|   |   |   |
|---|---|---|
|![realpg](https://cdn.v2ex.com/avatar/71ee/202d/119683_normal.png?m=1675800870)||40<br><br>**[realpg](/member/realpg)**  <br><br>   23 天前<br><br>@[summerwar](/member/summerwar) #38  <br>自己的那点带宽远远不够|

|   |   |   |
|---|---|---|
|![iorilu](https://cdn.v2ex.com/avatar/7121/0eb9/222090_normal.png?m=1726796040)||41<br><br>**[iorilu](/member/iorilu)**  <br><br>   23 天前<br><br>我怎么记得国内 cdn 必须都要使用备案的域名|

|   |   |   |
|---|---|---|
|![summerwar](https://cdn.v2ex.com/avatar/0ed3/c59f/61831_normal.png?m=1545304008)||42<br><br>**[summerwar](/member/summerwar)**  <br><br>   23 天前<br><br>@[realpg](/member/realpg) #40 去人多的地方，发点很嚣张的帖子，挂上网址，一会就够了 [![](https://i.imgur.com/agAJ0Rd.png)](https://i.imgur.com/agAJ0Rd.png)|

|   |   |   |
|---|---|---|
|![lthero](https://cdn.v2ex.com/gravatar/77b27233e67963633225abbccf560168?s=48&d=retro)||43<br><br>**[lthero](/member/lthero)**  <br><br>OP<br><br>   23 天前<br><br>@[iorilu](/member/iorilu) #41 域名已经备案了的|

|   |   |   |
|---|---|---|
|![realpg](https://cdn.v2ex.com/avatar/71ee/202d/119683_normal.png?m=1675800870)||44<br><br>**[realpg](/member/realpg)**  <br><br>   23 天前<br><br>@[summerwar](/member/summerwar) #42  <br>如果我是想整别人，那这样是可以的  <br>问题是我并不是想整别人 是纯纯的业务需要 我甚至可以付点钱|

|   |   |   |
|---|---|---|
|![summerwar](https://cdn.v2ex.com/avatar/0ed3/c59f/61831_normal.png?m=1545304008)||45<br><br>**[summerwar](/member/summerwar)**  <br><br>   22 天前<br><br>@[realpg](/member/realpg) #44 不了解这方便的业务，帮不上忙|

|   |   |   |
|---|---|---|
|![iorilu](https://cdn.v2ex.com/avatar/7121/0eb9/222090_normal.png?m=1726796040)||46<br><br>**[iorilu](/member/iorilu)**  <br><br>   22 天前<br><br>国内几个 cdn 都有很详细的设置的  <br>  <br>比如你设置每天 5G 流量封顶, 预防被刷钱|

|   |   |   |
|---|---|---|
|![Emma24](https://cdn.v2ex.com/avatar/9d20/7629/647343_normal.png?m=1696397739)||47<br><br>**[Emma24](/member/Emma24)**  <br><br>   22 天前<br><br>好家伙这么大网站部设置封顶的吗|

|   |   |   |
|---|---|---|
|![misty8873](https://cdn.v2ex.com/avatar/29b9/4fc3/165198_normal.png?m=1730879636)||48<br><br>**[misty8873](/member/misty8873)**  <br><br>   22 天前<br><br>@[lucasdev](/member/lucasdev) 这个网站怎么和 ipip 那么像。。。。|

