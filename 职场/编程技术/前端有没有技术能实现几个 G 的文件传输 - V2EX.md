---
link: https://www.v2ex.com/t/1097693
site: V2EX
date: 2024-12-15T17:14
excerpt: 程序员 - @mascteen - 目前的实现方式是用 NAS, 但是我觉得应该还有更好的实现方式，希望能得到一些思路。
twitter: https://twitter.com/@V2EX
slurped: 2025-02-08T10:15
title: 前端有没有技术能实现几个 G 的文件传输 - V2EX
---

[![mascteen](https://cdn.v2ex.com/avatar/b3ed/8ca6/495701_xlarge.png?m=1677199064)](https://www.v2ex.com/member/mascteen)

[V2EX](https://www.v2ex.com/)  ›  [程序员](https://www.v2ex.com/go/programmer)

 

[mascteen](https://www.v2ex.com/member/mascteen) · [janegwaww](https://github.com/janegwaww) · 54 天前 · 2268 次点击

这是一个创建于 54 天前的主题，其中的信息可能已经有所发展或是发生改变。

目前的实现方式是用 NAS, 但是我觉得应该还有更好的实现方式，希望能得到一些思路。

[](https://www.v2ex.com/tag/%E6%96%87%E4%BB%B6%E4%BC%A0%E8%BE%93)

[文件传输](https://www.v2ex.com/tag/%E6%96%87%E4%BB%B6%E4%BC%A0%E8%BE%93)[

高效](https://www.v2ex.com/tag/%E9%AB%98%E6%95%88)[

NAS](https://www.v2ex.com/tag/NAS)

7 条回复

|   |   |   |
|---|---|---|
|![ns09005264](https://cdn.v2ex.com/avatar/2373/6f4a/156949_normal.png?m=1464097249)||1<br><br>**[ns09005264](https://www.v2ex.com/member/ns09005264)**      54 天前<br><br>你能不能描述地更详细点，  <br>你是想让其他设备下载本机的文件的话，最简单的方式是通过 miniserve 这个工具起一个简单的服务器，它自带前端，可以浏览目录以及下载文件。[https://github.com/svenstaro/miniserve](https://github.com/svenstaro/miniserve) 。  <br>你是想通过纯前端进行文件点对点传输的话，[https://github.com/ShareDropio/sharedrop](https://github.com/ShareDropio/sharedrop) [https://sharedrop.io/](https://sharedrop.io/)|

|   |   |   |
|---|---|---|
|![SHF](https://cdn.v2ex.com/avatar/97c3/d714/304956_normal.png?m=1694707218)||2<br><br>**[SHF](https://www.v2ex.com/member/SHF)**      54 天前<br><br>下载很简单，http range header 就可以由浏览器自动分块下载。上传的话用 websocket 分块传输，server 端建立一个大文件，然后分块写入  <br>我自己写了一个，你可以传大文件试试  <br>[https://shenhongfei.com:9443/files/](https://shenhongfei.com:9443/files/)|

|   |   |   |
|---|---|---|
|![mascteen](https://cdn.v2ex.com/avatar/b3ed/8ca6/495701_normal.png?m=1677199064)||3<br><br>**[mascteen](https://www.v2ex.com/member/mascteen)**  <br><br>OP<br><br>   54 天前<br><br>@[SHF](https://www.v2ex.com/member/SHF) 我理解是主要的实现方式就是把文件分块处理？|

|   |   |   |
|---|---|---|
|![huangqihong](https://cdn.v2ex.com/avatar/8ecf/562a/460296_normal.png?m=1735616282)||4<br><br>**[huangqihong](https://www.v2ex.com/member/huangqihong)**      54 天前<br><br>@[mascteen](https://www.v2ex.com/member/mascteen) 断点续传？|

|                                                                              |     |                                                                                                                                                                                                                                                                 |
| ---------------------------------------------------------------------------- | --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ![SHF](https://cdn.v2ex.com/avatar/97c3/d714/304956_normal.png?m=1694707218) |     | 5<br><br>**[SHF](https://www.v2ex.com/member/SHF)**      53 天前<br><br>@[mascteen](https://www.v2ex.com/member/mascteen) 是的，在浏览器端可以分块 [https://developer.mozilla.org/zh-CN/docs/Web/API/Blob/slice](https://developer.mozilla.org/zh-CN/docs/Web/API/Blob/slice) |

|   |   |   |
|---|---|---|
|![SHF](https://cdn.v2ex.com/avatar/97c3/d714/304956_normal.png?m=1694707218)||6<br><br>**[SHF](https://www.v2ex.com/member/SHF)**      53 天前<br><br>@[huangqihong](https://www.v2ex.com/member/huangqihong) 不能断点续传，页面关掉之后需要重新传|

|   |   |   |
|---|---|---|
|![Yanlongli](https://cdn.v2ex.com/avatar/e284/9e62/466417_normal.png?m=1735622028)||7<br><br>**[Yanlongli](https://www.v2ex.com/member/Yanlongli)**      53 天前<br><br>按固定长度分，并计算每个分片的 哈希值，请求服务端是否存在相同哈希的分配，有则跳过没有则上传，最后服务端组合所有分片。断点续传同理。|