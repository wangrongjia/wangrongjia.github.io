---
link: https://www.v2ex.com/t/1097019
site: V2EX
date: 2024-12-12T15:15
excerpt: 程序员 - @OneLiteCore -
  最近在鼓捣国内的付费系统，但是觉得传统的用户注册流程过于繁琐，对于小体量的小项目来说开发和维护一套这样的系统得不偿失。因此构想了一个基于邮箱的用户注册付费流程，大家帮忙看看有什么问题没有。#
twitter: https://twitter.com/@V2EX
slurped: 2025-02-08T09:37
title: 一种基于邮箱的用户付费系统构想 - V2EX
---

这是一个创建于 57 天前的主题，其中的信息可能已经有所发展或是发生改变。

最近在鼓捣国内的付费系统，但是觉得传统的用户注册流程过于繁琐，对于小体量的小项目来说开发和维护一套这样的系统得不偿失。因此构想了一个基于邮箱的用户注册付费流程，大家帮忙看看有什么问题没有。

## 流程

1. APP 用户本地生成 UUID 并填写他的邮箱地址
    
2. 后台用邮箱地址和 UUID 计算出 MD5 ，并用后台私钥签名 MD5 ，然后发送给用户邮箱
    
3. 用户从邮箱中复制数据并回填到 APP 中
    
4. APP 本地计算出 MD5 然后和用户从邮箱复制过来的数据验签
    
5. 如果验证通过则说明用户确实持有这个邮箱地址，并将这个邮箱地址加密保存到 APP 本地，否则让用户重复上面的流程。
    
6. 后台检查数据库是否已存在邮箱对应的购买记录，不存在则生成订单信息并标记邮箱地址
    
7. APP 收到订单信息发起支付
    
8. 支付成功后，后台收到回调，将该邮箱的购买记录存入数据库
    
9. 后台以邮箱、UUID 、时间戳和设备等信息记录已付费邮箱的激活记录
    
10. 用户用本地认证的邮箱和 UUID 询问后台，如果激活记录小于 2 条则记录并允许激活
    
11. 如果激活记录 >= 2 则阻止激活，除非让旧设备注销，如果旧设备丢失可以以邮箱发送邮件申请人工注销。
    

## 可能存在的问题

- UUID 生成规则
    - 可以考虑别的生成算法比如雪花算法之类的
- MD5 不够可靠
    - 可以用 SHA3 或者 SHA256 摘要算法
- 发送到用户邮箱的数据可能太长
    - 可以考虑只将摘要算法计算出的散列的中间部分进行签名以缩短签名
- 用户本地 Hack 已认证邮箱
    - 用 AES 加密了扔进 MMKV 里面来增大难度
    - 用户难以知道其他已购买用户的邮箱
    - 保留用户从邮箱复制回填的签名数据并用作后续的认证
- 旧设备的注销可能繁琐
    - 丢失设备的情况下人工注销会比较麻烦，但是这个量级应该很少

第 1 条附言  ·  57 天前

看了下楼下的评论，目前发现这套构想似乎并没有决定性的创新或者突破。总结下有效的结论或者改进：

1.使用邮箱的话虽然可以规避发短信的成本问题，但是也同时存在被刷接口的问题导致邮件被 ban 拉高后续开发和维护的成本。

2.直接使用微信登录，然后以微信的开放 ID 作为购买凭证。优点是反正用户进行微信支付肯定有微信号，而且同样不需要手机号收发验证码的成本问题，而且还不用操心用户二次交易的情况。

3.直接使用激活码，用户如果忘记激活码可以使用付款方式的订单号来重新获取激活码，这样连登录都省略了，之后的限制登录的方式就是一样的。

[](https://www.v2ex.com/tag/%E9%82%AE%E7%AE%B1)

[邮箱](https://www.v2ex.com/tag/%E9%82%AE%E7%AE%B1)[

uuid](https://www.v2ex.com/tag/uuid)[

md5](https://www.v2ex.com/tag/md5)

36 条回复  **•**  2024-12-13 19:49:38 +08:00

|   |   |   |
|---|---|---|
|![ltaoo1o](https://cdn.v2ex.com/avatar/dfd1/c96b/410043_normal.png?m=1734877140)||2<br><br>**[ltaoo1o](https://www.v2ex.com/member/ltaoo1o)**      57 天前<br><br>难评，看之前以为是通过邮箱来进行支付的方案，看完发现是基于邮箱的用户认证。<br><br>你把邮箱视为手机号，发邮件看作发验证码。而且邮箱认证已经有完善的方案，开源的有 next-auth ，不过它们都是基于 web 的，逻辑应该能复用到 APP 吧。|

|   |   |   |
|---|---|---|
|![importmeta](https://cdn.v2ex.com/avatar/2018/6513/562972_normal.png?m=1733475592)||3<br><br>**[importmeta](https://www.v2ex.com/member/importmeta)**      57 天前<br><br>国内注册必须使用能实名标识用户的方式, 方便监管, 手机号只是其一.  <br>但是邮箱不一定, 除非只让 139 邮箱这种实名的手机号办的邮箱.  <br>不然, 别人一举报一个准.|

|   |   |   |
|---|---|---|
|![OneLiteCore](https://cdn.v2ex.com/gravatar/601adb72b7cc3c075af1de6ef8f935ec?s=48&d=retro)||6<br><br>**[OneLiteCore](https://www.v2ex.com/member/OneLiteCore)**      57 天前<br><br>@[ltaoo1o](https://www.v2ex.com/member/ltaoo1o) 标题确实不太贴合内容，不好意思。主要还是想要了解下这套逻辑是否可行，是否存在着明显的漏洞问题之类的，如果熟悉这方面知识还望赐教。|

|   |   |   |
|---|---|---|
|![monkeyk](https://cdn.v2ex.com/avatar/c085/8dd1/180311_normal.png?m=1557900609)||7<br><br>**[monkeyk](https://www.v2ex.com/member/monkeyk)**      57 天前<br><br>推荐看看最新的 物联网协议 FIDO 中的 passkeys 机制； 直接用设备上已有的认证方式（如指纹，扫脸），会是更好的解决办法，安全性更高。<br><br>github 上也开始提供这种认证方式。|

|   |   |   |
|---|---|---|
|![ysy950803](https://cdn.v2ex.com/avatar/406d/72a9/303249_normal.png?m=1713870055)||8<br><br>**[ysy950803](https://www.v2ex.com/member/ysy950803)**      57 天前<br><br>感觉就是用邮箱（视为唯一 ID ）收验证码来证明是本人？然后服务器存邮箱对应的激活次数？是这个意思吗？  <br>其实国内的话，还有个办法是接入微信登录，就能免去传统的注册流程了，那样最简单，服务器存微信的开放 UID 就行。|

|   |   |   |
|---|---|---|
|![ysy950803](https://cdn.v2ex.com/avatar/406d/72a9/303249_normal.png?m=1713870055)||9<br><br>**[ysy950803](https://www.v2ex.com/member/ysy950803)**      57 天前<br><br>补充一下：既然你都接入国内的支付系统了，说明你有开发者和收款资质，那直接把微信登录一起接了算了。|

|   |   |   |
|---|---|---|
|![geelaw](https://cdn.v2ex.com/avatar/1f0b/a007/202505_normal.png?m=1720483156)||10<br><br>**[geelaw](https://www.v2ex.com/member/geelaw)**      57 天前 via iPhone<br><br>单从密码学的角度考虑，不太理解 UUID 的作用是啥，是要绑定第一段邮箱验证，还是要绑定第二段激活？为什么要把 hash 算法（签名的实现细节）暴露在抽象的协议描述上？<br><br>从安全与易用性的角度考虑，UUID 需要保存吗？如何教育用户让他们保存？|

|   |   |   |
|---|---|---|
|![SenLief](https://cdn.v2ex.com/avatar/d6cf/28a8/195119_normal.png?m=1663686232)||11<br><br>**[SenLief](https://www.v2ex.com/member/SenLief)**      57 天前<br><br>没必要吧，直接每次给 email 发验证码登录不就好了。你甚至可以不用发验证码，而是直接发登录链接的方式来登录。|

|   |   |   |
|---|---|---|
|![cJ8SxGOWRH0LSelC](https://cdn.v2ex.com/gravatar/e7dffdc7a7a00db89464c7bae1a36bc5?s=48&d=retro)||12<br><br>**[cJ8SxGOWRH0LSelC](https://www.v2ex.com/member/cJ8SxGOWRH0LSelC)**      57 天前<br><br>你这个方案根本没有什么优势。  <br>1. 邮箱不是必选项，就是一个邮箱接收验证码的流程， 换成手机号也完全可行。  <br>2. 设备唯一性完全靠本地生成的 UUID ， 我只要拿到 UUID ， 并 HOOK 掉 UUID 的取值函数， 就完全可以无限复制设备， 你的设备数量激活限制也就无用了。|

|   |   |   |
|---|---|---|
|![yuhaofe](https://cdn.v2ex.com/avatar/7262/7407/692127_normal.png?m=1717952241)||13<br><br>**[yuhaofe](https://www.v2ex.com/member/yuhaofe)**      57 天前<br><br>不需要用户系统的话那连邮箱都没必要，购买成功直接后台返回一个唯一的激活码得了，用户什么都不用填付完款直接就能用，需要迁移设备就去 app 设置里复制激活码，要是丢了就直接用付款记录里的订单号查就行了  <br>工具类 app 本来就很容易被破解，绕这么一圈没必要，也没增加任何破解难度|

|   |   |   |
|---|---|---|
|![sampeng](https://cdn.v2ex.com/gravatar/3b198446b72d1e5a3b0090f106a75f3c?s=48&d=retro)||14<br><br>**[sampeng](https://www.v2ex.com/member/sampeng)**      57 天前<br><br>为什么都用手机号？除掉监管还有一个很大的原因。  <br>邮箱地址是假的。刷你接口，你的邮箱 smtp 就会“一不小心”的被当发垃圾邮件给 ban 了。。我上一个项目。隔三差五被 ban 一次。拆东墙补西墙。头疼得不行。。。因为不是国内项目，一些原因，没办法用手机验证。痛苦得 1b 。国内项目就没这个事了。。当然。。手机是要花钱的。还挺贵。。这确实也是一个考虑因素。。如何验证其实很多方法了。倒无所谓。。|

|   |   |   |
|---|---|---|
|![OneLiteCore](https://cdn.v2ex.com/gravatar/601adb72b7cc3c075af1de6ef8f935ec?s=48&d=retro)||15<br><br>**[OneLiteCore](https://www.v2ex.com/member/OneLiteCore)**      57 天前<br><br>@[monkeyk](https://www.v2ex.com/member/monkeyk) 指纹和扫脸只能认证用户是这个设备的主人的吧，用户换设备激活的话没办法迁移。本质上这个就是生成一个用户唯一凭证以此来代替账户系统而已，邮箱恰巧是个人拥有并且可以作为数据交换的方式。|

|   |   |   |
|---|---|---|
|![OneLiteCore](https://cdn.v2ex.com/gravatar/601adb72b7cc3c075af1de6ef8f935ec?s=48&d=retro)||16<br><br>**[OneLiteCore](https://www.v2ex.com/member/OneLiteCore)**      57 天前<br><br>@[ysy950803](https://www.v2ex.com/member/ysy950803) 用微信登录来做唯一凭证是一个不错的想法，毕竟都用微信支付了肯定有微信号，感谢提点！最开始设想用邮箱的话有一个目的就是将用户的购买凭证和付款方式分离开来，这样比如类似俄罗斯这种用不了 Google 支付以及微信支付的地区也能够通过手动转账，然后人工将邮箱写进数据库的方法来完成流程。|

|   |   |   |
|---|---|---|
|![OneLiteCore](https://cdn.v2ex.com/gravatar/601adb72b7cc3c075af1de6ef8f935ec?s=48&d=retro)||17<br><br>**[OneLiteCore](https://www.v2ex.com/member/OneLiteCore)**      57 天前<br><br>@[geelaw](https://www.v2ex.com/member/geelaw)<br><br>UUID 的作用是唯一标识，因为获取 IMEI 之类的设备表示不太符合隐私政策。其实只要是随机的没有碰撞问题的 ID 都行，UUID 只不过是在 Android 原生开发里面最容易获取罢了。这样和邮箱关联在一起，可以知道 UUID 和邮箱的持有人是对应关系，同时也可以用来限制登录设备数量。<br><br>UUID 是要保存在客户端本地的，用 MMKV 框架做持久化就行了最多本地再加密一下，不需要用户手动操作。<br><br>发送到邮箱里面的数据也可以不用用户复制，而是使用 DeepLink 之类的方式拉起应用，以减少用户的操作。|

|   |   |   |
|---|---|---|
|![OneLiteCore](https://cdn.v2ex.com/gravatar/601adb72b7cc3c075af1de6ef8f935ec?s=48&d=retro)||18<br><br>**[OneLiteCore](https://www.v2ex.com/member/OneLiteCore)**      57 天前<br><br>@[SenLief](https://www.v2ex.com/member/SenLief) 那也要确保用户填写的邮箱是他本人的邮箱，如果用户随便填写一个邮箱然后付费激活了的话，还是需要人工联系提交交易 ID ，然后开发者手动去退款之类的。|

|   |   |   |
|---|---|---|
|![OneLiteCore](https://cdn.v2ex.com/gravatar/601adb72b7cc3c075af1de6ef8f935ec?s=48&d=retro)||19<br><br>**[OneLiteCore](https://www.v2ex.com/member/OneLiteCore)**      57 天前<br><br>@[StinkyTofus](https://www.v2ex.com/member/StinkyTofus)<br><br>1. 邮箱确实不是必选项，但是比起用手机号和验证码来说更省钱，短信验证码可不是免费的。<br><br>2. 如果你都能 HOOK 掉 UUID 的话，直接本地激活就行了，或者有这个能力直接破解 APK 都更容易些。|

|   |   |   |
|---|---|---|
|![yuhaofe](https://cdn.v2ex.com/avatar/7262/7407/692127_normal.png?m=1717952241)||23<br><br>**[yuhaofe](https://www.v2ex.com/member/yuhaofe)**      57 天前<br><br>另外 1~5 的流程是验证邮箱所有权，类似忘记密码，主要逻辑就是发送一封邮件，只有持有邮箱的人能够知道邮件内容  <br>目前绝大部分 app 应该都是发送短的随机验证码或者带着随机码的链接，不太确定 lz 这样做的目的在哪里，无状态不占缓存吗，还是会更安全|

|   |   |   |
|---|---|---|
|![OneLiteCore](https://cdn.v2ex.com/gravatar/601adb72b7cc3c075af1de6ef8f935ec?s=48&d=retro)||24<br><br>**[OneLiteCore](https://www.v2ex.com/member/OneLiteCore)**      57 天前   ![❤️](https://www.v2ex.com/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>@[yuhaofe](https://www.v2ex.com/member/yuhaofe) 为了规避发送短信所需要的成本，短信显然不是免费的，同时也为了规避自己搭建一套账号系统，是出于运行和开发成本的考量。但是按照上面的讨论得出的结果就是，直接上微信登录似乎是一个更好的选择，或者不在乎用户二次交易的话直接用激活码更合适一些。|

|   |   |   |
|---|---|---|
|![yueji](https://cdn.v2ex.com/avatar/1a39/f5a5/246372_normal.png?m=1729165359)||25<br><br>**[yueji](https://www.v2ex.com/member/yueji)**      57 天前<br><br>在本地抓包可以把 smtp server / 账号 / 密码 明文抓包出来。|

|   |   |   |
|---|---|---|
|![yuhaofe](https://cdn.v2ex.com/avatar/7262/7407/692127_normal.png?m=1717952241)||26<br><br>**[yuhaofe](https://www.v2ex.com/member/yuhaofe)**      57 天前<br><br>@[OneLiteCore](https://www.v2ex.com/member/OneLiteCore) 哦哦，这个我明白，主要不清楚的还是为什么用邮箱地址和 UUID 算 MD5 再签名而不是直接后端生成临时随机码放缓存里，邮件里发随机码不是用户输入更方便吗|

|   |   |   |
|---|---|---|
|![OneLiteCore](https://cdn.v2ex.com/gravatar/601adb72b7cc3c075af1de6ef8f935ec?s=48&d=retro)||27<br><br>**[OneLiteCore](https://www.v2ex.com/member/OneLiteCore)**      57 天前<br><br>@[yueji](https://www.v2ex.com/member/yueji) 是后台通过 smtp 发送邮件到用户的邮箱，抓包没办法抓服务器的包的吧，用户在这个过程中能够看到的是后台用私钥签名的值。这样客户端本地也持有邮箱和 UUID 可以直接算 MD5 并验证签名。|

|   |   |   |
|---|---|---|
|![OneLiteCore](https://cdn.v2ex.com/gravatar/601adb72b7cc3c075af1de6ef8f935ec?s=48&d=retro)||28<br><br>**[OneLiteCore](https://www.v2ex.com/member/OneLiteCore)**      57 天前   ![❤️](https://www.v2ex.com/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>@[yuhaofe](https://www.v2ex.com/member/yuhaofe) 发送随机验证码的话，客户端拿到验证码还是需要去询问后台是不是这个验证码，直接用在客户端用后台的公钥去验证签名可以省略一步。不过看了上面老哥的讨论，觉得要么直接用微信登录，要么就直接激活码更合适点。|

|   |   |   |
|---|---|---|
|![baobao1270](https://cdn.v2ex.com/avatar/d18d/28b5/114915_normal.png?m=1736950860)||29<br><br>**[baobao1270](https://www.v2ex.com/member/baobao1270)**      57 天前 via Android<br><br>1. 传统方式过于繁琐：用户需要的是步骤少，步骤越少心智负担越少，大部分人不在乎隐私，输手机号就 2. 能注册是大部分人的认知，如果能一键登录更好  <br>小体量项目开发系统麻烦：推荐一下 logto  <br>3. 怎么避免用户逆向改 asm  <br>4. 怎么避免用户 mitm 改请求  <br>5. 国内用户有没有使用邮箱的习惯？|

|   |   |   |
|---|---|---|
|![OneLiteCore](https://cdn.v2ex.com/gravatar/601adb72b7cc3c075af1de6ef8f935ec?s=48&d=retro)||31<br><br>**[OneLiteCore](https://www.v2ex.com/member/OneLiteCore)**      56 天前 via Android<br><br>@[baobao1270](https://www.v2ex.com/member/baobao1270)  <br>1. 这个没毛病，赞同。  <br>2. 小工具品类东西都在客户端上，后台也不提供服务的情况下登录了也没有更多功能，所以才考虑简化的。看了眼 logto 似乎能解决部分问题不过还是感觉略复杂，打算接微信登录算了。  <br>3. Android 开发里面没听说过 ASM ，这个是前端的东西吗？  <br>4. Mitm 也没听说过。  <br>5. 国内基本是微信当邮箱用的，所以直接接入微信生态似乎是一个更好的选择|

|   |   |   |
|---|---|---|
|![OneLiteCore](https://cdn.v2ex.com/gravatar/601adb72b7cc3c075af1de6ef8f935ec?s=48&d=retro)||34<br><br>**[OneLiteCore](https://www.v2ex.com/member/OneLiteCore)**      56 天前<br><br>@[baobao1270](https://www.v2ex.com/member/baobao1270)<br><br>1. 小工具基本没办法防止反编译啊，而且用户有这个能力的话那此时也就不是操心账号和付费系统的时候了  <br>2. 抓包的话用 https 里面套了一层 RSA 加密，客户端和服务端互相持有对方的公钥的那种  <br>3. 综合下来就是用微信登录和订单号作为记录最靠谱，还能预防二次转卖的问题|

|   |   |   |
|---|---|---|
|![louzhichen](https://cdn.v2ex.com/avatar/5dde/a97f/579959_normal.png?m=1737994199)||36<br><br>**[louzhichen](https://www.v2ex.com/member/louzhichen)**      56 天前<br><br>银行 app 的验证码都只是六位数字，我感觉前五步不需要这么复杂，就是正常走生成随机验证码就行了。如果担心碰撞，设置一个有效期即可。|