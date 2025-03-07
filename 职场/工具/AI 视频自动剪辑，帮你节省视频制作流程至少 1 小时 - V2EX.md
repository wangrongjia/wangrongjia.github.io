---
link: https://www.v2ex.com/t/1110719
site: V2EX
date: 2025-02-11T17:27
excerpt: 分享创造 - @EdsionRookie - 支持多平台视频链接上传产品主页https://bravoclip.com/AI
  自动剪辑https://bravoclip.com/ai-viral-clip自动加字幕
twitter: https://twitter.com/@V2EX
slurped: 2025-02-12T10:04
title: AI 视频自动剪辑，帮你节省视频制作流程至少 1 小时 - V2EX
---

  [EdsionRookie](/member/EdsionRookie) · 16 小时 37 分钟前 · 404 次点击

支持多平台视频链接上传  
  
产品主页  
[https://bravoclip.com/](https://bravoclip.com/)  
  
AI 自动剪辑  
[https://bravoclip.com/ai-viral-clip](https://bravoclip.com/ai-viral-clip)  
  
自动加字幕（免费）  
[https://bravoclip.com/ai-caption](https://bravoclip.com/ai-caption)  
  
自动翻译 40+语言字幕（免费）  
[https://bravoclip.com/ai-translate](https://bravoclip.com/ai-translate)  
  
转录视频成文本（免费）  
[https://bravoclip.com/video-to-text](https://bravoclip.com/video-to-text)  
  
AI 自动改写脚本（免费）  
[https://bravoclip.com/ai-script-writer](https://bravoclip.com/ai-script-writer)  
  
视频转 MP3 、GIF 等多种格式  
[https://bravoclip.com/youtube-video-to-mp3-converter](https://bravoclip.com/youtube-video-to-mp3-converter)


5 条回复  **•**  2025-02-11 17:51:10 +08:00

|   |   |   |
|---|---|---|
|![Yuesh1](https://cdn.v2ex.com/avatar/9231/75d6/502736_normal.png?m=1715335569)||1<br><br>**[Yuesh1](/member/Yuesh1)**  <br><br>   16 小时 30 分钟前<br><br>[https://imgur.com/a/1GESYsk](https://imgur.com/a/1GESYsk)  <br>  <br>  <br>我用的 arc 浏览器，为什么一直谈这个导致我的浏览器假死，需要退出才能使用？|

|   |   |   |
|---|---|---|
|![lolita89201](https://cdn.v2ex.com/gravatar/0fdd297563fae90f8429b7b508d0d5ed?s=48&d=retro)||2<br><br>**[lolita89201](/member/lolita89201)**  <br><br>   16 小时 27 分钟前<br><br>以后所有的内容创作都是 AI 输出的, 网络世界还有什么意思!|

|   |   |   |
|---|---|---|
|![EdsionRookie](https://cdn.v2ex.com/gravatar/aba393373a74048689fcb9197d993c89?s=48&d=retro)||3<br><br>**[EdsionRookie](/member/EdsionRookie)**  <br><br>OP<br><br>   16 小时 24 分钟前<br><br>@[Yuesh1](/member/Yuesh1) 最好用 Chrome|

|   |   |   |
|---|---|---|
|![EdsionRookie](https://cdn.v2ex.com/gravatar/aba393373a74048689fcb9197d993c89?s=48&d=retro)||4<br><br>**[EdsionRookie](/member/EdsionRookie)**  <br><br>OP<br><br>   16 小时 24 分钟前<br><br>@[lolita89201](/member/lolita89201) 加快流程的工具，不是代替真人|

|   |   |   |
|---|---|---|
|![LeslieLeung](https://cdn.v2ex.com/avatar/18ac/40b8/489265_normal.png?m=1706030470)||5<br><br>**[LeslieLeung](/member/LeslieLeung)**  <br><br>   16 小时 13 分钟前<br><br>看到一楼的回复好奇试了下。  <br>  <br>这个防控制台打开的方法也太拙劣了，检测逻辑就是两个：一个控制台高度阈值，一个开发者工具快捷键拦截。甚至因为 arc 本身的布局，一打开就会触发检测。  <br>  <br>绕过方法：Arc 浏览器全屏，把开发者工具弹出方式改为单独窗口。  <br>  <br>```  <br>checkConsoleOpen: function checkConsoleOpen() {  <br>var threshold = 160; // 自定义控制台高度阈值  <br>setInterval(function () {  <br>if (window.outerHeight - window.innerHeight > threshold \| window.outerWidth - window.innerWidth > threshold) {  <br>alert("控制台已打开，禁止查看源代码！");  <br>window.location.reload(); // 可选：刷新页面或隐藏内容  <br>}  <br>}, 1000);  <br>}  <br>  <br>if (true) {  <br>if (localStorage.getItem('allowopenf12') != true && localStorage.getItem('allowopenf12') != 'true') {  <br>this.checkConsoleOpen();  <br>// 禁用右键菜单  <br>document.addEventListener('contextmenu', function (event) {  <br>return event.preventDefault();  <br>});  <br>document.addEventListener('keydown', function (event) {  <br>if (event.key === 'F12' \|  <br>// F12  <br>event.ctrlKey && event.shiftKey && event.key === 'I' \|  <br>// Ctrl+Shift+I  <br>event.ctrlKey && event.shiftKey && event.key === 'J' \|  <br>// Ctrl+Shift+J  <br>event.ctrlKey && event.key === 'U' // Ctrl+U  <br>) {  <br>event.preventDefault();  <br>}  <br>});  <br>}  <br>}  <br>```  <br>  <br>说实话，开发者工具真没必要防吧，想看你接口我抓包也行，一万种方法。|
