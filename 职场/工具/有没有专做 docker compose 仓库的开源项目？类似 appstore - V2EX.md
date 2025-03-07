---
link: https://www.v2ex.com/t/1105365
site: V2EX
date: 2025-01-15T20:05
excerpt: 程序员 - @GoRuby - 有没有类似这样的开源项目。项目就是一堆配置文件。分成很多目录，每个目录就是一个开源软件，比如
  `zabbix`、`mysql`、`mongo_cluster`，不同的目录下面是 docker-comp
twitter: https://twitter.com/@V2EX
slurped: 2025-02-11T14:42
title: 有没有专做 docker compose 仓库的开源项目？类似 appstore - V2EX
---
  
[UlricQin](https://github.com/UlricQin) · 26 天前 · 1790 次点击

有没有类似这样的开源项目。项目就是一堆配置文件。分成很多目录，每个目录就是一个开源软件，比如 `zabbix`、`mysql`、`mongo_cluster`，不同的目录下面是 docker-compose.yaml 以及相关配置文件。想使用啥组件的时候直接进去 `docker compose up -d` 即可。

省得我去到处找 docker compose 文件的时间了，如果文档比较完善就更好了。


14 条回复  **•**  2025-01-16 15:58:31 +08:00

|   |   |   |
|---|---|---|
|![263](https://cdn.v2ex.com/gravatar/6e7188d9e16887307be08e556fcc902a?s=48&d=retro)||1<br><br>**[263](/member/263)**  <br><br>   26 天前<br><br>1Panel|

|   |   |   |
|---|---|---|
|![chase196](https://cdn.v2ex.com/avatar/d1a8/10a1/669222_normal.png?m=1729403253)||2<br><br>**[chase196](/member/chase196)**  <br><br>   26 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 2<br><br>dockge ，跟你说的一模一样的|

|   |   |   |
|---|---|---|
|![ysicing](https://cdn.v2ex.com/avatar/cba2/dc20/87080_normal.png?m=1732087768)||3<br><br>**[ysicing](/member/ysicing)**  <br><br>   26 天前<br><br>bitnami/containers|

|   |   |   |
|---|---|---|
|![hanxiV2EX](https://cdn.v2ex.com/avatar/2d5f/b1ec/172691_normal.png?m=1667609808)||4<br><br>**[hanxiV2EX](/member/hanxiV2EX)**  <br><br>   26 天前 via Android<br><br>需要的时候自己配，都不复杂。|

|   |   |   |
|---|---|---|
|![wogogoing](https://cdn.v2ex.com/avatar/9a10/fb3d/705949_normal.png?m=1725864984)||5<br><br>**[wogogoing](/member/wogogoing)**  <br><br>   26 天前 via iPhone<br><br>欢迎一起贡献代码/配置  <br>  <br>[https://github.com/keepchen/docker-compose](https://github.com/keepchen/docker-compose)|

|   |   |   |
|---|---|---|
|![HE1HE](https://cdn.v2ex.com/gravatar/c889339bcb2f3061055d973f4b9f5b5b?s=48&d=retro)||6<br><br>**[HE1HE](/member/HE1HE)**  <br><br>   26 天前<br><br>dockge +1 ，简单好用|

|   |   |   |
|---|---|---|
|![sch1111878](https://cdn.v2ex.com/gravatar/6048868197a340513ec6fcf85a5b47cc?s=48&d=retro)||7<br><br>**[sch1111878](/member/sch1111878)**  <br><br>   26 天前<br><br>dockge 看了, image 如果支持搜索就更棒了|

|   |   |   |
|---|---|---|
|![GoRuby](https://cdn.v2ex.com/avatar/4914/047d/59895_normal.png?m=1735688836)||8<br><br>**[GoRuby](/member/GoRuby)**  <br><br>OP<br><br>   26 天前<br><br>以上收到，感谢各位|

|   |   |   |
|---|---|---|
|![zzerd](https://cdn.v2ex.com/avatar/5288/c60e/390555_normal.png?m=1732204101)||9<br><br>**[zzerd](/member/zzerd)**  <br><br>   26 天前<br><br>我都是用 ai 生成配置文件|

|   |   |   |
|---|---|---|
|![Ayanokouji](https://cdn.v2ex.com/gravatar/a3330a6a823a9945c860c7aa2cb1c29f?s=48&d=retro)||10<br><br>**[Ayanokouji](/member/Ayanokouji)**  <br><br>   26 天前<br><br>[https://github.com/bitnami/containers](https://github.com/bitnami/containers)|

|   |   |   |
|---|---|---|
|![wdv2ly](https://cdn.v2ex.com/avatar/870d/a5a0/95308_normal.png?m=1541413811)||11<br><br>**[wdv2ly](/member/wdv2ly)**  <br><br>   26 天前 via Android<br><br>@[chase196](/member/chase196) 我特意去试了下 dockge ，怎么感觉跟楼主要的不是一个东西呢。这个看起来是一个 docker compose 配置的图形化编辑器和管理器，我想启动一个镜像，还是需要手工配置各个字段。而楼主想要的是一个预定义的配置集，省去自己写的时间？|

|   |   |   |
|---|---|---|
|![buffzty](https://cdn.v2ex.com/gravatar/b7307d566c500a00fbbd3439296350bf?s=48&d=retro)||12<br><br>**[buffzty](/member/buffzty)**  <br><br>   25 天前<br><br>是不是想找这种仓库 [仓库]( [https://imgur.com/a/y7RSTGP](https://imgur.com/a/y7RSTGP))|

|   |   |   |
|---|---|---|
|![RayJiang9](https://cdn.v2ex.com/avatar/8382/545b/424826_normal.png?m=1686800220)||13<br><br>**[RayJiang9](/member/RayJiang9)**  <br><br>   25 天前<br><br>[https://github.com/FrozenGEE/compose](https://github.com/FrozenGEE/compose)|

|   |   |   |
|---|---|---|
|![chase196](https://cdn.v2ex.com/avatar/d1a8/10a1/669222_normal.png?m=1729403253)||14<br><br>**[chase196](/member/chase196)**  <br><br>   25 天前<br><br>@[wdv2ly](/member/wdv2ly) 初理解 dockge 是满足楼主说的每一句了  <br>项目多目录，每个目录就是一个开源软件 docker-compose.yaml +配置文件  <br>除了这句”想使用啥组件的时候直接进去 docker compose up -d 即可“，dockge 是直接网页图像启动  <br>  <br>目前俺是这样使用的，开发正式不同环境，使用$APP_PATH 环境变量定义区分|
