---
link: https://www.v2ex.com/t/1108788
site: V2EX
date: 2025-02-04T01:22
excerpt: 程序员 - @CureDovahkiin - 在页面加载前拦截 xhr 和 fetch
  对象加个响应拦截器，屏蔽放在用户信息流里面的广告，返回处理后的数据，还能顺便屏蔽 up 主发的广告屏蔽一些跟踪脚本的请求，然后不会像 ublo
twitter: https://twitter.com/@V2EX
slurped: 2025-02-14T09:03
title: 有没有基于拦截浏览器请求来达成一些事情的浏览器扩展 - V2EX
---
  
  [CureDovahkiin](/member/CureDovahkiin) · 10 天前 · 2383 次点击

在页面加载前拦截 xhr 和 fetch 对象

加个响应拦截器，屏蔽放在用户信息流里面的广告，返回处理后的数据，还能顺便屏蔽 up 主发的广告

屏蔽一些跟踪脚本的请求，然后不会像 ublock 之类的疯狂在控制台报错，直接把请求吞了。

[之前写了一个](https://github.com/shadowdreamer/jioben/blob/master/bilibili/bilibili-fetch-hijack.user.js) 但是感觉会重复造轮子就凑合用没继续写。

如果是一个扩展，感觉可以订阅一些请求和响应拦截器的脚本和规则，不过做起来好麻烦还是算了🤓


19 条回复  **•**  2025-02-05 09:22:15 +08:00

|   |   |   |
|---|---|---|
|![kk2syc](https://cdn.v2ex.com/avatar/7eac/ff4c/655410_normal.png?m=1734018023)||1<br><br>**[kk2syc](/member/kk2syc)**  <br><br>   10 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>这么多年了，还有不知道 tampermonkey 的？|

|   |   |   |
|---|---|---|
|![lijiangang886](https://cdn.v2ex.com/gravatar/52ef5f4954cf1b0778a5694c7a8e4669?s=48&d=retro)||2<br><br>**[lijiangang886](/member/lijiangang886)**  <br><br>   10 天前<br><br>没去纠细节，不是说 Chrome manifest V3 把这个功能干废了吗？|

|   |   |   |
|---|---|---|
|![foufoufm](https://cdn.v2ex.com/avatar/0484/763b/499086_normal.png?m=1733884433)||3<br><br>**[foufoufm](/member/foufoufm)**  <br><br>   9 天前<br><br>@[kk2syc](/member/kk2syc) 下载了很久，但是，没啥好用的脚本。。。|

|   |   |   |
|---|---|---|
|![whjlinyi](https://cdn.v2ex.com/gravatar/e8fadb9cdbb70525348272f204878d5d?s=48&d=retro)||4<br><br>**[whjlinyi](/member/whjlinyi)**  <br><br>   9 天前 via iPhone<br><br>AdGuard|

|   |   |   |
|---|---|---|
|![CureDovahkiin](https://cdn.v2ex.com/gravatar/2ea98c6fd91d8a655144e37613586017?s=48&d=retro)||5<br><br>**[CureDovahkiin](/member/CureDovahkiin)**  <br><br>OP<br><br>   9 天前<br><br>@[kk2syc](/member/kk2syc) 我寻思里面链接就是我写的用户脚本啊，就是问有没有优化一下做成扩展的|

|   |   |   |
|---|---|---|
|![klesh](https://cdn.v2ex.com/gravatar/43ab30c8f8abc821ccc4d89504a47935?s=48&d=retro)||6<br><br>**[klesh](/member/klesh)**  <br><br>   9 天前<br><br>@[kk2syc](/member/kk2syc) tampermonkey 能拦截 xhr 和 fetch 对象吗？有没有例子分享一下呀？谢谢。|

|   |   |   |
|---|---|---|
|![Archeb](https://cdn.v2ex.com/gravatar/93f5d0e297fe1c30eb4cf540e214523a?s=48&d=retro)||7<br><br>**[Archeb](/member/Archeb)**  <br><br>   9 天前<br><br>大部分情况下是没办法直接注入页面才需要的请求重写，tampermonkey 能直接注入页面还费那劲重写干嘛|

|   |   |   |
|---|---|---|
|![abccccabc](https://cdn.v2ex.com/avatar/8ddd/6828/240733_normal.png?m=1519953523)||8<br><br>**[abccccabc](/member/abccccabc)**  <br><br>   9 天前<br><br>借这个主题问一下：tampermonkey 如何拦截页面的 audio/video 这些请求呢？一直没有找到这种插件。  <br>  <br>不知那位高手 show 一下代码。|

|   |   |   |
|---|---|---|
|![loginv2](https://cdn.v2ex.com/avatar/e492/a12a/38849_normal.png?m=1678049930)||9<br><br>**[loginv2](/member/loginv2)**  <br><br>   9 天前<br><br>@[abccccabc](/member/abccccabc) [https://segmentfault.com/a/1190000025182822](https://segmentfault.com/a/1190000025182822)|

|   |   |   |
|---|---|---|
|![fuzzsh](https://cdn.v2ex.com/gravatar/80a77afb1761c378e3255001241a6f8b?s=48&d=retro)||10<br><br>**[fuzzsh](/member/fuzzsh)**  <br><br>   9 天前 via Android<br><br>fiddler 可以拦截改返回内容|

|   |   |   |
|---|---|---|
|![CureDovahkiin](https://cdn.v2ex.com/gravatar/2ea98c6fd91d8a655144e37613586017?s=48&d=retro)||11<br><br>**[CureDovahkiin](/member/CureDovahkiin)**  <br><br>OP<br><br>   9 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>@[klesh](/member/klesh) 直接问 deepseek 就行了  <br>[https://gist.github.com/shadowdreamer/4687f0fe1da96bec64db68feccbb09d1](https://gist.github.com/shadowdreamer/4687f0fe1da96bec64db68feccbb09d1)  <br>看了下应该没毛病（  <br>因为大部分逻辑都通用，所以才想会不会有扩展包装一下，有个修改请求头的扩展叫 Header Editor ，那修改参数和响应体也感觉也可以有|

|   |   |   |
|---|---|---|
|![NoOneNoBody](https://cdn.v2ex.com/gravatar/ade866d803c393db42301082488695d2?s=48&d=retro)||12<br><br>**[NoOneNoBody](/member/NoOneNoBody)**  <br><br>   9 天前<br><br>@[abccccabc](/member/abccccabc) #8  <br>umatrix 之类可以拦截 media 类型，不过可能把 font 之类也拦截了  <br>或者搜 request block (关键词，不是名字)之类的扩展  <br>  <br>油猴脚本拦截需要设置更早的加载时间，因为默认是页面加载完成，这样大部分已经加载了，拦截没意义  <br>具体让 AI 写一个就行，绰绰有余|

|   |   |   |
|---|---|---|
|![abccccabc](https://cdn.v2ex.com/avatar/8ddd/6828/240733_normal.png?m=1519953523)||13<br><br>**[abccccabc](/member/abccccabc)**  <br><br>   9 天前<br><br>@[NoOneNoBody](/member/NoOneNoBody) @[loginv2](/member/loginv2) 多谢两位分享。找到 http request block 和 custome block 挨个试用下，看看效果。|

|   |   |   |
|---|---|---|
|![leokun](https://cdn.v2ex.com/avatar/12ab/702a/625066_normal.png?m=1712507728)||14<br><br>**[leokun](/member/leokun)**  <br><br>   9 天前<br><br>Hoppscotch 的插件实现了类似功能，不过并不是传统的拦截 xhr 和 fetch|

|   |   |   |
|---|---|---|
|![kk2syc](https://cdn.v2ex.com/avatar/7eac/ff4c/655410_normal.png?m=1734018023)||15<br><br>**[kk2syc](/member/kk2syc)**  <br><br>   9 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>@[CureDovahkiin](/member/CureDovahkiin) @[klesh](/member/klesh) 注入点选好都可以重写啊，fetch 参考下，xhr 类似  <br>  <br>(function () {  <br>   const originFetch = fetch;  <br>   // console.log(originFetch)  <br>   window.unsafeWindow.fetch = (url, options) => {  <br>       return originFetch(url, options).then(async (response) => {  <br>           console.log(url)  <br>           if(url === 'https://domain/something'){  <br>               const responseClone = response.clone()  <br>               let res = await responseClone.json()  <br>               res.data.push('处理数据')  <br>               const responseNew = new Response(JSON.stringify(res), response);  <br>               return responseNew  <br>          }else{  <br>               return response  <br>          }  <br>      })  <br>  }  <br>})()|

|   |   |   |
|---|---|---|
|![kk2syc](https://cdn.v2ex.com/avatar/7eac/ff4c/655410_normal.png?m=1734018023)||16<br><br>**[kk2syc](/member/kk2syc)**  <br><br>   9 天前<br><br>@[foufoufm](/member/foufoufm) 大部分是自己日积月累写下来的针对性脚本，也有一些分享的，比如百度盘 vip 解析啊（虽然从免费变成赞助可用，几块钱也比 svip 便宜）|

|   |   |   |
|---|---|---|
|![foufoufm](https://cdn.v2ex.com/avatar/0484/763b/499086_normal.png?m=1733884433)||17<br><br>**[foufoufm](/member/foufoufm)**  <br><br>   9 天前<br><br>@[kk2syc](/member/kk2syc) 有没有传送门指指北 求求|

|   |   |   |
|---|---|---|
|![lijiangang886](https://cdn.v2ex.com/gravatar/52ef5f4954cf1b0778a5694c7a8e4669?s=48&d=retro)||18<br><br>**[lijiangang886](/member/lijiangang886)**  <br><br>   9 天前<br><br>浏览器为扩展提供了 API 可以拦截请求： [webRequest] （已在 manifest V3 中被 Chrome 废止）和 [declarativeNetRequest]|

|   |   |   |
|---|---|---|
|![EdwardWong](https://cdn.v2ex.com/gravatar/ad8ab334baecba498eb1214c1e198dec?s=48&d=retro)||19<br><br>**[EdwardWong](/member/EdwardWong)**  <br><br>   8 天前<br><br>如果是 Bilibili 可以用 [https://github.com/the1812/Bilibili-Evolved](https://github.com/the1812/Bilibili-Evolved) ，也是用 user.js 实现的，里面有组件可以过滤首页的流。|
