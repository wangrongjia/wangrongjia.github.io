---
link: https://www.v2ex.com/t/1103038
site: V2EX
date: 2025-01-07T00:42
excerpt: 程序员 - @Gorvery - 前段时间，我的 Android 手机坏了，找了个 iPhone
  过渡一段时间。因为我的个人号和工作号是分开的，所以对微信双开是强需求。我没有企业证书，altserver 这种局域网自签的方式也让我比较
twitter: https://twitter.com/@V2EX
slurped: 2025-02-06T09:16
title: 分享一个关于购买的双开微信包有异常风险行为的事情 - V2EX
---
前段时间，我的 Android 手机坏了，找了个 iPhone 过渡一段时间。因为我的个人号和工作号是分开的，所以对微信双开是强需求。我没有企业证书，altserver 这种局域网自签的方式也让我比较焦虑（担心出去玩，超过 7 天没开电脑），所以我直接从淘宝上买了个包，想着过渡几个月凑活用，也比较省心。安装完后用了几天，微信号没被封，而且这个包通过常驻后台的方式实现了新消息实时接收，虽然耗电比较大，但也还能接受。

周日那天出门，我觉得手机比较重，就把手机壳摘掉了。结果在一天的使用过程中，我发觉得手机永远是温热的，于是产生了警觉。咨询了淘宝客服，客服说因为后台常驻，10 秒刷新一次比较频繁，功耗比较高。于是在客服的指导下，我将刷新时间修改成了 30 秒。

今天上班我依旧不带壳，发现手机还是一直温热的。突然联想到之前在站内看到过一个帖子的回复里说，这种购买的微信包，有可能会被利用来挖矿的，于是我就用 Charles 抓包看了下有没有可疑流量，结果还真发现了几个无域名的可疑 http 流量请求，看接口名，有判断 wifi 环境的，有 putImage 上传图片的等等。

其中 putImage 的请求，在 app 退到后台后，每隔 5 、6 秒，就会发送一个 PUT 请求，每次 PUT 一个大概几百 KB 的数据文件，文件似乎被加密了，每个请求都不一样，而且只在连接 wifi 后 PUT 数据，实在是可疑。因为本人也在做 iOS 开发，根据自己有限的知识，觉得 iOS 后台保活应该不需要这么频繁的请求任务来保活，而且如果只是单纯保活，也没必要搞个这么大的数据请求。所以我总觉得这个请求怪怪的，心里越想越发毛，赶紧退了微信，更换了密码。

后来我拿着抓包信息，找淘宝商家质问这个请求是做什么的，上传了什么数据。结果淘宝商家拒绝回答，反而嘲讽我，说有本事让我自己开发一个，还说“没有十全十美的东西”、“如果感觉别人的不好用就自己去开发一个，如果开发不出来就老老实实接受别人的”。气得我本来想在评论里追评下，提醒下购买的人注意风险，但又想到可能在使用他们这个微信的过程中，一些敏感信息已经被收集了，断人财路会遭到报复，所以最后还是怂了，只申请了退款，没有去给他们打差评。

[](https://www.v2ex.com/tag/%E5%BE%AE%E4%BF%A1%E5%8F%8C%E5%BC%80)

[微信双开](https://www.v2ex.com/tag/%E5%BE%AE%E4%BF%A1%E5%8F%8C%E5%BC%80)[

风险](https://www.v2ex.com/tag/%E9%A3%8E%E9%99%A9)[

挖矿](https://www.v2ex.com/tag/%E6%8C%96%E7%9F%BF)

24 条回复  **•**  2025-01-11 10:22:25 +08:00

|   |   |   |
|---|---|---|
|![czhu](https://cdn.v2ex.com/avatar/c4bb/c69c/36810_normal.png?m=1654541837)||3<br><br>**[czhu](https://www.v2ex.com/member/czhu)**      30 天前<br><br>两个手机完美解决？|

|   |   |   |
|---|---|---|
|![Lucups](https://cdn.v2ex.com/avatar/1925/4180/41582_normal.png?m=1556244764)||4<br><br>**[Lucups](https://www.v2ex.com/member/Lucups)**      30 天前<br><br>看起来感觉楼主花钱买了个木马...<br><br>我之前好奇这种花钱买的破解类软件是否还会有问题，看了楼主的分析，看来哪怕是花钱了还是有问题。  <br>这类软件花钱还是买不了安心，还是小心为上。|

|   |   |   |
|---|---|---|
|![12101111](https://cdn.v2ex.com/avatar/0805/86ef/196009_normal.png?m=1561111286)||5<br><br>**[12101111](https://www.v2ex.com/member/12101111)**      30 天前<br><br>根据我的了解，一般是破解软件自带的 DRM ，防止同行抄过去二次出售|

|   |   |   |
|---|---|---|
|![xing7673](https://cdn.v2ex.com/gravatar/92699c48c8ccd17d47409bef8f1794be?s=48&d=retro)||7<br><br>**[xing7673](https://www.v2ex.com/member/xing7673)**      30 天前 via iPhone<br><br>你是 ios 开发的直接去下一个官方包自签不就行了  <br>我现在就是这样，这玩意淘宝就是链子罢了|

|   |   |   |
|---|---|---|
|![ETiV](https://cdn.v2ex.com/avatar/0e09/5e05/1183_normal.png?m=1708966496)||8<br><br>**[ETiV](https://www.v2ex.com/member/ETiV)**      30 天前 via iPhone   ![❤️](https://www.v2ex.com/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 6<br><br>你虽然不能自己开发微信，但是可以把上传数据的 URL 地址、IP 发出来，让有才的 v 友们去练习一下|

|   |   |   |
|---|---|---|
|![kokutou](https://cdn.v2ex.com/avatar/171b/5976/95780_normal.png?m=1684391405)||9<br><br>**[kokutou](https://www.v2ex.com/member/kokutou)**      30 天前 via Android<br><br>再买个手机，电信开个 0 元副卡。。。|

|   |   |   |
|---|---|---|
|![jiangziheng](https://cdn.v2ex.com/avatar/fb9a/55e3/463334_normal.png?m=1717743075)||10<br><br>**[jiangziheng](https://www.v2ex.com/member/jiangziheng)**      30 天前<br><br>有需要局域网电脑自签的，也有只需要局域网不需要电脑自签的，还有就是买个开发者自签个，还有就是用巨魔安装的。1,2,4 三种方式加起来用了好几年了。|

|   |   |   |
|---|---|---|
|![lisxour](https://cdn.v2ex.com/avatar/580f/70c0/600882_normal.png?m=1717041609)||11<br><br>**[lisxour](https://www.v2ex.com/member/lisxour)**      29 天前   ![❤️](https://www.v2ex.com/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>为啥你愿意买一台 iphone ，又搞这搞那的，都不愿意再买一台安卓|

|   |   |   |
|---|---|---|
|![Gorvery](https://cdn.v2ex.com/avatar/e279/cb65/463095_normal.png?m=1730697198)||13<br><br>**[Gorvery](https://www.v2ex.com/member/Gorvery)**      29 天前<br><br>@[czhu](https://www.v2ex.com/member/czhu) @[kokutou](https://www.v2ex.com/member/kokutou) @[lisxour](https://www.v2ex.com/member/lisxour) 出门带两个手机觉得有点重。iPhone 不是买的，是我的测试机，想先过渡一段时间，然后买小米 16 pro 。我还有一台测试机是三星的，实在太难用了，用了一周还是用苹果吧|

|   |   |   |
|---|---|---|
|![Gorvery](https://cdn.v2ex.com/avatar/e279/cb65/463095_normal.png?m=1730697198)||16<br><br>**[Gorvery](https://www.v2ex.com/member/Gorvery)**      29 天前<br><br>@[eairjhioaegnh](https://www.v2ex.com/member/eairjhioaegnh) @[ETiV](https://www.v2ex.com/member/ETiV) 请求是这个请求，http://23.249.29.78:8080/api/putImages 但数据包没有保留下来……  <br>但说实话，如果不考虑被微信识别的因素，做个后台常驻也没有什么特别难的|

|   |   |   |
|---|---|---|
|![Cheez](https://cdn.v2ex.com/gravatar/d0d039018b81ff8d509f70864e39fddf?s=48&d=retro)||19<br><br>**[Cheez](https://www.v2ex.com/member/Cheez)**      29 天前<br><br>那你就把相关的证据都发出来呗，这没头没脑的，你要我们怎么做？|

|   |   |   |
|---|---|---|
|![LeoLYF](https://cdn.v2ex.com/gravatar/f42cb1483981427251502caec1434bdb?s=48&d=retro)||20<br><br>**[LeoLYF](https://www.v2ex.com/member/LeoLYF)**      29 天前<br><br>sidestore 开源免费，个人证书 7 天，能自动自签，搞巨魔前的最佳替代|

|   |   |   |
|---|---|---|
|![shenyuzhi](https://cdn.v2ex.com/avatar/d626/dd0e/35980_normal.png?m=1698065493)||22<br><br>**[shenyuzhi](https://www.v2ex.com/member/shenyuzhi)**      29 天前 via iPhone<br><br>花钱购买这种东西，不如买个低端安卓机，专门工作用|

|   |   |   |
|---|---|---|
|![Gorvery](https://cdn.v2ex.com/avatar/e279/cb65/463095_normal.png?m=1730697198)||23<br><br>**[Gorvery](https://www.v2ex.com/member/Gorvery)**      27 天前 via iPhone<br><br>@[Cheez](https://www.v2ex.com/member/Cheez) 不是求助帖，不需要大家帮忙做什么，看标题，只是分享一个经历罢了，让大家买这种多开微信的时候长个心眼|

|   |   |   |
|---|---|---|
|![moefishtang](https://cdn.v2ex.com/gravatar/938e8fdf307775a55065bd974354604a?s=48&d=retro)||24<br><br>**[moefishtang](https://www.v2ex.com/member/moefishtang)**      25 天前<br><br>挖矿应该不至于吧，之前用 iPhone 装 iSH 跑 xmrig ，效果并不好<br><br>倒是泄露微信资料很有可能，我一般不敢用第三方改版的微信客户端|