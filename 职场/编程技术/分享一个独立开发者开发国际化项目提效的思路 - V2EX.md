---
link: https://www.v2ex.com/t/1109204
site: V2EX
date: 2025-02-05T22:53
excerpt: 分享创造 - @hamsterbase - 分享一下我所有项目都在用的工作流1. 以源码作为唯一的 i18n 配置源代码里所有的文案都是
  localize('key','Default Message') 这种格式key
twitter: https://twitter.com/@V2EX
slurped: 2025-02-06T10:16
title: 分享一个独立开发者开发国际化项目提效的思路 - V2EX
---
  

# 分享一个独立开发者开发国际化项目提效的思路


[carytrivett](https://github.com/carytrivett) · 11 小时 19 分钟前 · 395 次点击

分享一下我所有项目都在用的工作流  
  
1. 以源码作为唯一的 i18n 配置源  
  
代码里所有的文案都是 localize('key','Default Message') 这种格式  
  
key 没有专门规范，想到什么用什么  
  
  
2. 使用脚本解析 ast ，自动生成默认的 en-US.json 和 (zh-CN.json ....)  
  
"highlight.action.EditNote": {  
"defaultMessage": "Edit Note",  
"content": "Edit Note"  
},  
  
  
"highlight.action.EditNote": {  
"defaultMessage": "Edit Note",  
"content": ""  
},  
  
  
未翻译的为空白字符串。  
  
  
3. 编写脚本，把所有未翻译的 json 都拆出来。 提交给 ai ，把所有 content :'' 为空的都翻译好  
  
  
  
  
按照这个思路，在开发的时候完全不需要管翻译，只需要无脑写代码就行了。  
在发布之前，跑一下脚本，就可以自动翻译好整个项目。  
  
  
  
  
我写了一个 vscode 插件给自己用，感兴趣的可以下载  
  
[https://marketplace.visualstudio.com/items?itemName=hamsterbase.i18nease](https://marketplace.visualstudio.com/items?itemName=hamsterbase.i18nease)  
  
  
插件本书完全离线，自行配置 openai 的 key 就可以使用。  
  
  
  
如果是希望参考脚本， 我之前给一个 10000 多 star 多项目提了 PR 。 感兴趣可以参考  
  
[https://github.com/caprover/caprover-frontend/blob/master/scripts/generate-locales.mjs](https://github.com/caprover/caprover-frontend/blob/master/scripts/generate-locales.mjs)


1 条回复  **•**  2025-02-06 09:22:14 +08:00

|   |   |   |
|---|---|---|
|![rm0gang0rf](https://cdn.v2ex.com/avatar/27a4/eabd/520160_normal.png?m=1711422486)||1<br><br>**[rm0gang0rf](/member/rm0gang0rf)**  <br><br>   50 分钟前<br><br>最近有这个需求, 最好是可以定义格式|
