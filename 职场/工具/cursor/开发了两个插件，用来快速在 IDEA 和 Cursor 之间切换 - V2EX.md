---
link: https://www.v2ex.com/t/1106449
site: V2EX
date: 2025-01-20T13:21
excerpt: 分享创造 - @qczone - Cursor 很好用，但是对于我这个 Java 开发来说还是太依赖 IDEA 了，现在我的开发流程是用
  Cursor 生成，用 IDEA 编译调试。然而两个软件之间来回切换找代码不太方便，于是
twitter: https://twitter.com/@V2EX
slurped: 2025-02-13T17:30
title: 开发了两个插件，用来快速在 IDEA 和 Cursor 之间切换 - V2EX
---
 

[qczone](https://github.com/qczone) · 24 天前 · 2933 次点击

Cursor 很好用，但是对于我这个 Java 开发来说还是太依赖 IDEA 了，现在我的开发流程是用 Cursor 生成，用 IDEA 编译调试。  
  
然而两个软件之间来回切换找代码不太方便，于是我开发了两个插件  
1. Switch2Cursor (IDEA 插件)  
2. Switch2IDEA (Cursor 插件)  
  
两个配合使用，通过快捷键可以很方便的在 IDEA 和 Cursor 之间来回切换，并保持光标的位置。  
  
核心功能：  
Alt+Shift+O：在另一 IDE 中打开当前文件  
Alt+Shift+P：在另一 IDE 中打开当前项目  
  
演示视频：

  
安装方式：  
IDEA 插件市场搜索：switch2cursor  
Cursor 插件市场搜索：switch2idea  
  
源码：  
[https://github.com/qczone/switch2cursor](https://github.com/qczone/switch2cursor)  
[https://github.com/qczone/switch2idea](https://github.com/qczone/switch2idea)  
  
如果使用过程中遇到问题，或者有改进建议，欢迎在 GitHub 上提交 Issue


39 条回复  **•**  2025-02-12 15:12:04 +08:00

|   |   |   |
|---|---|---|
|![AoEiuV020JP](https://cdn.v2ex.com/avatar/0ad7/2c6c/626874_normal.png?m=1716779343)||1<br><br>**[AoEiuV020JP](/member/AoEiuV020JP)**  <br><br>   24 天前<br><br>切换依据是“进程名”还是？  <br>windows 能用吗，android studio 能兼容吗，cursor 可执行文件改名了的情况能用吗，|

|   |   |   |
|---|---|---|
|![qczone](https://cdn.v2ex.com/avatar/9b47/7763/631853_normal.png?m=1737338990)||2<br><br>**[qczone](/member/qczone)**  <br><br>OP<br><br>   24 天前<br><br>@[AoEiuV020JP](/member/AoEiuV020JP) 切换依据是 IDEA 和 Cursor 的可执行文件的路径 + 文件参数，例如  <br>  <br>Mac: open -a /Applications/[Cursor.app](http://Cursor.app) cursor://file/Users/developer/project/main.kt:10:5  <br>Windows: cmd /c "C:\Program Files\Cursor\Cursor.exe" --goto "C:\Users\developer\project\main.kt:10:5"  <br>  <br>Windows 上可以用  <br>Android Studio 能兼容，需要在 Cursor 配置 Android Studio 的可执行文件的路径  <br>Cursor 可执行文件改名在 IDEA/Android Studio 里面配置 Cursor 的可执行文件的路径即可，只是窗口激活可能会有问题|

|   |   |   |
|---|---|---|
|![wanniwa](https://cdn.v2ex.com/avatar/b5bd/0c79/362568_normal.png?m=1691310579)||3<br><br>**[wanniwa](/member/wanniwa)**  <br><br>   24 天前<br><br>点赞，这是我想要的|

|   |   |   |
|---|---|---|
|![arischow](https://cdn.v2ex.com/gravatar/c4234d36f1c66464a630fc1bb14238d7?s=48&d=retro)||4<br><br>**[arischow](/member/arischow)**  <br><br>   24 天前<br><br>[https://manico.im/](https://manico.im/)|

|   |   |   |
|---|---|---|
|![Echoleung](https://cdn.v2ex.com/gravatar/0a4beda3f9c32a7df4bd4b2b10e7139b?s=48&d=retro)||5<br><br>**[Echoleung](/member/Echoleung)**  <br><br>   24 天前 via Android<br><br>甜菜|

|   |   |   |
|---|---|---|
|![qczone](https://cdn.v2ex.com/avatar/9b47/7763/631853_normal.png?m=1737338990)||6<br><br>**[qczone](/member/qczone)**  <br><br>OP<br><br>   24 天前<br><br>@[arischow](/member/arischow) 不太一样的兄弟，我这两个插件可以定位到具体的行和列进行跳转|

|   |   |   |
|---|---|---|
|![sakuno](https://cdn.v2ex.com/gravatar/30c47736d35edd7e9d2786495cc2fdd0?s=48&d=retro)||7<br><br>**[sakuno](/member/sakuno)**  <br><br>   24 天前<br><br>🐂🍺|

|   |   |   |
|---|---|---|
|![HaibaraDP](https://cdn.v2ex.com/gravatar/c23d7b81887316a9c8d66cc69a9e1071?s=48&d=retro)||8<br><br>**[HaibaraDP](/member/HaibaraDP)**  <br><br>   24 天前<br><br>🙏|

|   |   |   |
|---|---|---|
|![bitmin](https://cdn.v2ex.com/gravatar/bbe99da803152a49eda34d7f10ac64b9?s=48&d=retro)||9<br><br>**[bitmin](/member/bitmin)**  <br><br>   24 天前<br><br>装了，试试，点赞，感谢|

|   |   |   |
|---|---|---|
|![among](https://cdn.v2ex.com/avatar/4a56/94f4/417783_normal.png?m=1711429226)||10<br><br>**[among](/member/among)**  <br><br>   24 天前<br><br>pycharm 支持吗|

|   |   |   |
|---|---|---|
|![qczone](https://cdn.v2ex.com/avatar/9b47/7763/631853_normal.png?m=1737338990)||11<br><br>**[qczone](/member/qczone)**  <br><br>OP<br><br>   24 天前<br><br>@[among](/member/among) Jetbrains 系列都支持的，只不过需要在 Cursor 中配置 idea path 为 PyCharm 的可执行文件的路径|

|   |   |   |
|---|---|---|
|![xaltman30](https://cdn.v2ex.com/avatar/4f6e/054a/621787_normal.png?m=1719548296)||12<br><br>**[xaltman30](/member/xaltman30)**  <br><br>   23 天前<br><br>直接打开俩个环境，不就好了么...#24|

|   |   |   |
|---|---|---|
|![LevineChen](https://cdn.v2ex.com/avatar/0558/a5f4/159038_normal.png?m=1559111244)||13<br><br>**[LevineChen](/member/LevineChen)**  <br><br>   23 天前<br><br>🐮🍺|

|   |   |   |
|---|---|---|
|![nocmt](https://cdn.v2ex.com/gravatar/6640001960b888da54f3ea01bd2fcb2d?s=48&d=retro)||14<br><br>**[nocmt](/member/nocmt)**  <br><br>   23 天前<br><br>点赞|

|   |   |   |
|---|---|---|
|![wyjwork](https://cdn.v2ex.com/gravatar/389562f71d2172436344f6c6c1452194?s=48&d=retro)||15<br><br>**[wyjwork](/member/wyjwork)**  <br><br>   23 天前<br><br>[![](https://i.imgur.com/OZySWIG.png)](https://i.imgur.com/OZySWIG.png)|

|   |   |   |
|---|---|---|
|![paststrange](https://cdn.v2ex.com/gravatar/367c3ad8cc7111f04fed19176340e757?s=48&d=retro)||16<br><br>**[paststrange](/member/paststrange)**  <br><br>   23 天前<br><br>有点牛逼|

|   |   |   |
|---|---|---|
|![Xinu](https://cdn.v2ex.com/avatar/021e/4fbb/431658_normal.png?m=1724206977)||17<br><br>**[Xinu](/member/Xinu)**  <br><br>   23 天前<br><br>洞察需求，甜菜|

|   |   |   |
|---|---|---|
|![Xinu](https://cdn.v2ex.com/avatar/021e/4fbb/431658_normal.png?m=1724206977)||18<br><br>**[Xinu](/member/Xinu)**  <br><br>   23 天前<br><br>@[xaltman30](/member/xaltman30) 这就是同时打开两个环境，节省切换环境时间，简直是在救人|

|   |   |   |
|---|---|---|
|![Xinu](https://cdn.v2ex.com/avatar/021e/4fbb/431658_normal.png?m=1724206977)||19<br><br>**[Xinu](/member/Xinu)**  <br><br>   23 天前<br><br>好用，十分丝滑 👍 👍 👍|

|   |   |   |
|---|---|---|
|![yatoooon](https://cdn.v2ex.com/gravatar/5f4ec14ee56b43cfd4528c6720590360?s=48&d=retro)||20<br><br>**[yatoooon](/member/yatoooon)**  <br><br>   23 天前<br><br>厉害|

|   |   |   |
|---|---|---|
|![dust0522](https://cdn.v2ex.com/gravatar/5141c0f3d760d1e5d9515c0944bc120c?s=48&d=retro)||21<br><br>**[dust0522](/member/dust0522)**  <br><br>   23 天前<br><br>牛牛牛牛牛牛牛牛牛牛牛牛牛牛牛牛牛牛牛牛牛牛|

|   |   |   |
|---|---|---|
|![cccxu](https://cdn.v2ex.com/gravatar/e286d7190dbb0ca6736fba6885412a87?s=48&d=retro)||22<br><br>**[cccxu](/member/cccxu)**  <br><br>   23 天前<br><br>天才|

|   |   |   |
|---|---|---|
|![Moldav](https://cdn.v2ex.com/gravatar/e44114d3986a8e7a174e906ad0ed17a6?s=48&d=retro)||23<br><br>**[Moldav](/member/Moldav)**  <br><br>   23 天前<br><br>我 idea 、webstorm 、cursor 都开了，实际上只是想在 web 和 cursor 之间切换， 从 cursor 切换好像默认跳的是 IDEA ，怎么修改呢。|

|   |   |   |
|---|---|---|
|![qczone](https://cdn.v2ex.com/avatar/9b47/7763/631853_normal.png?m=1737338990)||24<br><br>**[qczone](/member/qczone)**  <br><br>OP<br><br>   23 天前<br><br>@[Moldav](/member/Moldav) 修改设置里面的 Extensions -> Switch2IDEA 的 idea path 为 WebStorm 的路径|

|   |   |   |
|---|---|---|
|![sumonian](https://cdn.v2ex.com/avatar/8470/9322/199643_normal.png?m=1509337729)||25<br><br>**[sumonian](/member/sumonian)**  <br><br>   23 天前<br><br>win 在 cursor 配置了 idea path ，无法跳转，然后在 idea2024.2 版本安装了，也无法跳转，如何排查|

|   |   |   |
|---|---|---|
|![meeop](https://cdn.v2ex.com/avatar/8f89/5180/450566_normal.png?m=1735874691)||26<br><br>**[meeop](/member/meeop)**  <br><br>   22 天前<br><br>非常好用，楼主伟大  <br>  <br>另外小建议，说明文档说一下 mac 怎么操作，我试了几次才找到正确的快捷键|

|   |   |   |
|---|---|---|
|![timedivision](https://cdn.v2ex.com/gravatar/11f796086ce788cebdf0900cf27c3d3d?s=48&d=retro)||27<br><br>**[timedivision](/member/timedivision)**  <br><br>   22 天前<br><br>牛的，这也算是 ide 使用 cursor 的曲线救国方案了，后面是否会支持自定义快捷键啊|

|   |   |   |
|---|---|---|
|![teddybun](https://cdn.v2ex.com/gravatar/62d6540b597b9ca3c9f0b2020205aae7?s=48&d=retro)||28<br><br>**[teddybun](/member/teddybun)**  <br><br>   22 天前<br><br>能直接跳 vscode 吗，我用是 vscode+Cline|

|   |   |   |
|---|---|---|
|![teddybun](https://cdn.v2ex.com/gravatar/62d6540b597b9ca3c9f0b2020205aae7?s=48&d=retro)||29<br><br>**[teddybun](/member/teddybun)**  <br><br>   22 天前<br><br>太牛逼了，直接修改为 Visual Studio Code ，就可以打开，🐂🍺|

|   |   |   |
|---|---|---|
|![madou](https://cdn.v2ex.com/avatar/df18/c852/711278_normal.png?m=1730266841)||30<br><br>**[madou](/member/madou)**  <br><br>   22 天前<br><br>好东西，太爽了，感谢分享插件，提升了不少效率。android studio 修改 idea 路径可用|

|   |   |   |
|---|---|---|
|![xiaocyidie](https://cdn.v2ex.com/avatar/3c8e/73f3/221008_normal.png?m=1656986760)||31<br><br>**[xiaocyidie](/member/xiaocyidie)**  <br><br>   22 天前<br><br>感谢楼主|

|   |   |   |
|---|---|---|
|![qczone](https://cdn.v2ex.com/avatar/9b47/7763/631853_normal.png?m=1737338990)||32<br><br>**[qczone](/member/qczone)**  <br><br>OP<br><br>   21 天前<br><br>@[sumonian](/member/sumonian) 是配置的 C:\Program Files\JetBrains\xxxx\bin\idea64.exe 这样的吗|

|   |   |   |
|---|---|---|
|![qczone](https://cdn.v2ex.com/avatar/9b47/7763/631853_normal.png?m=1737338990)||33<br><br>**[qczone](/member/qczone)**  <br><br>OP<br><br>   21 天前<br><br>@[meeop](/member/meeop) 感谢建议，我完善一下说明文档|

|   |   |   |
|---|---|---|
|![IceBay](https://cdn.v2ex.com/gravatar/1e35e8d818ce71d61a5de79990360f36?s=48&d=retro)||34<br><br>**[IceBay](/member/IceBay)**  <br><br>   20 天前<br><br>可以支持一下 PHPStorm 吗？|

|   |   |   |
|---|---|---|
|![IceBay](https://cdn.v2ex.com/gravatar/1e35e8d818ce71d61a5de79990360f36?s=48&d=retro)||35<br><br>**[IceBay](/member/IceBay)**  <br><br>   20 天前<br><br>是我不会用 cursor ，已经可以互相切换了，太棒了！|

|   |   |   |
|---|---|---|
|![sumonian](https://cdn.v2ex.com/avatar/8470/9322/199643_normal.png?m=1509337729)||36<br><br>**[sumonian](/member/sumonian)**  <br><br>   7 天前<br><br>@[qczone](/member/qczone) 不是 我安装的目录不是默认的 但是我已经按照教程在设置里面修改成我安装的目录了|

|   |   |   |
|---|---|---|
|![zerolist](https://cdn.v2ex.com/avatar/b5de/835d/672115_normal.png?m=1705498246)||37<br><br>**[zerolist](/member/zerolist)**  <br><br>   5 天前<br><br>牛逼 @@！！|

|   |   |   |
|---|---|---|
|![henjihenguanjian](https://cdn.v2ex.com/avatar/3da4/dbc2/385245_normal.png?m=1617931693)||38<br><br>**[henjihenguanjian](/member/henjihenguanjian)**  <br><br>   1 天前<br><br>安装试了下，厉害了|

|   |   |   |
|---|---|---|
|![Yukineko](https://cdn.v2ex.com/gravatar/04b0120d3fcd319d90208f972500668b?s=48&d=retro)||39<br><br>**[Yukineko](/member/Yukineko)**  <br><br>   1 天前<br><br>非常好用，感谢楼主～|
