---
link: https://www.v2ex.com/t/1108803
site: V2EX
date: 2025-02-04T10:06
excerpt: "分享创造 - @ihehe - ## OHY 介绍`GITHUB` 地址:
  https://github.com/ohyfun/ohy无需打包：一行命令就直接把 WEB 启动成桌面应用。自动设置好桌面 ICON 。"
twitter: https://twitter.com/@V2EX
slurped: 2025-02-28T13:14
title: OHY 又一款 WEB 打包成桌面应用的 CLI 工具 - V2EX
---
  
  [ihehe](/member/ihehe) · 24 天前 · 1612 次点击

## OHY 介绍

`GITHUB` 地址: [https://github.com/ohyfun/ohy](https://github.com/ohyfun/ohy)

无需打包：一行命令就直接把 WEB 启动成桌面应用。自动设置好桌面 ICON 。 隐私优先：所有应用的 WEB 缓存数据统一目录存放，不在系统里到处创建文件。 性能保障： 纯 `RUST` 性能应该没问题，实现代码超精简，有利于高级用户二开。 支持应用多开： 每个应用的 WEB 缓存单独存放，相互隔离

## Usage

```bash
Usage: ohy --url <url> [-n <name>] [-w <width>] [-h <height>] [-a <user-agent>]

Options:
  --url             url example https://www.github.com
  -n, --name        name
  -w, --width       width default 1200
  -h, --height      height default 780
  -a, --user-agent  user agent
  --help, help      display usage information
```

## 安装简单（ linux 用户需要安装`libwebkit2gtk-4.1`的系统依赖）

```bash
cargo install ohy
```

## 开发这个工具的心路历程：

OP 是 LINUX 桌面用户，平时蛮重视隐私保护的。浏览器用的全隐私模式，不同网址都用 firefox-container 隔离在不同的 SESSION 中（ OP 是 FIREFOX 全平台用户）， 平时一开 Tab 就是几十个，隔三岔五的 Tab 一键全删除, 这时候就有个问题了， 一些需要登陆的网站就得重新登陆了，AI 兴起之前时间还好，也就两三个必须登陆使用， 自从 AI 平台百团大战以来，需要登陆的平台多到十多个。作为一个 Linux 桌面用户，官方能提供桌面应用的少得可怜，所以就寻找解决方案。 一开始发现 PAKE 这个 WEB 打包工具，试用了一下发现有点不合适我，PAKE 中每个应用需要提前打包，然后还要 APT 安装。 PAKE 好像没在 LINUX 上测试过，LINUX 安装多个应用好像有些问题。 PAKE 是个很好的工具，提供的功能也更丰富，只是不适合我的使用习惯； OHY 的底层依赖，跟 PAKE 一样都是 WRY 这个 RUST 的 WEBVIEW 库，所以性能差别不大。

## OHY 状态

OHY 目前只在 LINUX 跟 WINDODOWS 上测试过，因为没有 MAC 设备，所以没有测试过， 底层依赖是支持 MAC 的，作为 RUST 新手对交叉编译还不太会，所以 MAC 上可能会有 BUG ， 欢迎大家试用，star 跟 issues ， 欢迎 MAC 用户来帮忙测试一下。 可怜的 `CARGO CLIPPY` 竟然对 #[cfg]指定的其他平台下的代码不闻不问？

放一张应用截图![qwen](https://github.com/user-attachments/assets/eec15bdd-f1fa-4364-bd5c-e6229b70a46b)

8 条回复  **•**  2025-02-05 10:10:54 +08:00

|   |   |   |
|---|---|---|
|![SayHelloHi](https://cdn.v2ex.com/avatar/d961/3cd9/563553_normal.png?m=1739072847)||1<br><br>**[SayHelloHi](/member/SayHelloHi)**  <br><br>   24 天前<br><br>感谢分享 非常棒的工具 👍|

|   |   |   |
|---|---|---|
|![gorira](https://cdn.v2ex.com/avatar/af64/43c4/637633_normal.png?m=1688805105)||2<br><br>**[gorira](/member/gorira)**  <br><br>   24 天前<br><br>这应用截图大黑体字还以为在骂人……|

|                                                                                       |     |                                                                                                          |
| ------------------------------------------------------------------------------------- | --- | -------------------------------------------------------------------------------------------------------- |
| ![w568w](https://cdn.v2ex.com/gravatar/a07da489e1f63eaa83cded683786df23?s=48&d=retro) |     | 3<br><br>**[w568w](/member/w568w)**  <br><br>   23 天前<br><br>请问楼主知道**现代浏览器支持叫 PWA 的**技术吗？这个相比 PWA 有什么优势？ |

|   |   |   |
|---|---|---|
|![ihehe](https://cdn.v2ex.com/avatar/699d/92be/520833_normal.png?m=1738634679)||4<br><br>**[ihehe](/member/ihehe)**  <br><br>OP<br><br>   23 天前 via iPhone<br><br>@[SayHelloHi](/member/SayHelloHi) 谢谢  <br>@[gorrira](/member/gorrira) 这个还真没注意，每个平台都要取名字就简单取一个  <br>@[w568w](/member/w568w) PWA 听过很久了，刚才拿 chrome 试了一下 PWA ，（ firefox 好像是放弃了 PWA ，安排给第三方插件了），chrome 里手动开启 10 来个 PWA 的配置选项，然后点安装就可以使用了，打开 APP 体验不错，好像是跟 chrome 共用配置，APP 支持 chrome 里的插件，这个看起来不错。  <br>ohy 的有优势的地方是可以多开，各自隔离，内存占用少，进程也少。  <br>chrome pwa 优势就是插件系统，chrome 自带，窗口 banner 也小一些。  <br>![deskpng]( [https://github.com/user-attachments/assets/d6d0f03b-9039-4eec-9aed-bcdd9595d32f](https://github.com/user-attachments/assets/d6d0f03b-9039-4eec-9aed-bcdd9595d32f))  <br>![psef]( [https://github.com/user-attachments/assets/bfe34136-826d-4872-87ba-72a34e48c3cf](https://github.com/user-attachments/assets/bfe34136-826d-4872-87ba-72a34e48c3cf))|

|                                                                               |     |                                                                                                                                                                                                                                                    |
| ----------------------------------------------------------------------------- | --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ![musi](https://cdn.v2ex.com/avatar/3c30/8c17/303588_normal.png?m=1691313864) |     | 5<br><br>**[musi](/member/musi)**  <br><br>   23 天前<br><br>chrome **pwa 优势可不只是插件系统，目前市面上的大部分网站基本都是以 chrome 作为标准进行开发的，也就是说 chrome 拥有一流的网站支持能力，另外像 web usb web bluetooth 这些 api 也是 chrome 最早支持的  <br>况且根据 pwa 的标准离线缓存、用户通知都可以实现**，这些方面不是知道 ohy 做的怎么样 |

|   |   |   |
|---|---|---|
|![ihehe](https://cdn.v2ex.com/avatar/699d/92be/520833_normal.png?m=1738634679)||6<br><br>**[ihehe](/member/ihehe)**  <br><br>OP<br><br>   23 天前 via iPhone<br><br>@[musi](/member/musi) 其实 ohy 啥也没干，就是调用当前系统的 webview 启动一个桌面程序，隔离一下数据缓存，最后设一个 icon 而已。所有功能都来自于系统自带。  <br>总共 100 来行代码，换成 py 大概就 10 行？|

|   |   |   |
|---|---|---|
|![subframe75361](https://cdn.v2ex.com/avatar/b115/3d02/587457_normal.png?m=1673837359)||7<br><br>**[subframe75361](/member/subframe75361)**  <br><br>   23 天前 via Android<br><br>和这个类似 [https://github.com/tw93/Pake](https://github.com/tw93/Pake)|

|   |   |   |
|---|---|---|
|![ihehe](https://cdn.v2ex.com/avatar/699d/92be/520833_normal.png?m=1738634679)||8<br><br>**[ihehe](/member/ihehe)**  <br><br>OP<br><br>   23 天前 via iPhone<br><br>@[7subframe75361](/member/7subframe75361) 是的，跟 Pake 类似，就连底层的 webview 库都是同一个库：Wry ( [https://github.com/tauri-apps/wry)。](https://github.com/tauri-apps/wry\)。)  <br>Pake 使用的是 wry 上层的 Tauri 库，需要打包成对应平台的系统包，然后安装，打包需要 JS/NPM 生态的依赖。  <br>ohy 是直接使用 wry 的，无需打包，没有 JS 依赖，直接启动。  <br>Pake 提供的功能更丰富（页面美化，JS 注入等等）|
