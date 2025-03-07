---
link: https://www.v2ex.com/t/1111015
site: V2EX
date: 2025-02-12T18:13
excerpt: 程序员 - @mizuki9 - 后端语言从未统一，前端语言自从浏览器发展出来后 js 几乎就是唯一的选择。在此期间产生许多将后端语言转换为
  js 的各种库，各种尝试，直到 WebAssembly 出现，给出了一条将其他语言都编译
twitter: https://twitter.com/@V2EX
slurped: 2025-02-13T09:19
title: 个人猜想 WebAssembly 的未来 - V2EX
---
  
  [mizuki9](/member/mizuki9) · 15 小时 5 分钟前 · 1569 次点击

后端语言从未统一，前端语言自从浏览器发展出来后 js 几乎就是唯一的选择。  
在此期间产生许多将后端语言转换为 js 的各种库，各种尝试，直到 WebAssembly 出现，给出了一条将其他语言都编译为 wasm ，提供给 js 使用的一条路。  
由于前端语言是唯一的，并且我们可以看到历史上不断有需求将其他语言转换为 js ，所以 wasm 必然在这个目标(需求)上成功。  
但除此之外，  
替代 docker ？各语言没有这个动力（需求），目前的 docker 已经满足了，想要推动这个目标，只有 wasi 相关的几家公司自己发展，就算 wasi 发展完善了，各语言也是要适配的，感觉不太能行，似乎没有希望。  
docker 是自己去适应所有语言，其他程序跑在实体机(例如 Linux)与跑在 docker 对于程序自身感受来说，并没有什么明确的区别。  
wasi 除非把自己虚拟化成某个 Linux 的发行版，提供与这个系统相同的 api ，否则每种语言适配 wasi 就像适配一个新系统。


13 条回复  **•**  2025-02-12 23:42:22 +08:00

|   |   |   |
|---|---|---|
|![murmur](https://cdn.v2ex.com/avatar/5141/1e1f/161642_normal.png?m=1462262183)||1<br><br>**[murmur](/member/murmur)**  <br><br>   14 小时 32 分钟前<br><br>webasm 现在最多的需求还是做代码加密，毕竟反编译和调试的工具没有 js 那么牛逼  <br>  <br>以前 b 站软解 h265 卡的一笔，webasm 再牛逼也比不上显卡的编解码器，而这玩意对于 native 就是洒洒水  <br>  <br>很早以前就侧重 app 了，既然是 app 我干嘛不用 native 直接做呢，除去大量的编解码需求，就那点 js 运算，瓶颈不全在 dom 渲染上，网页精简 50%，你想不流畅都难|

|   |   |   |
|---|---|---|
|![Rorysky](https://cdn.v2ex.com/avatar/7e19/69c8/77850_normal.png?m=1705629254)||2<br><br>**[Rorysky](/member/Rorysky)**  <br><br>   12 小时 55 分钟前<br><br>没有杀手应用，主要还是用来提升性能|

|   |   |   |
|---|---|---|
|![Linho1219](https://cdn.v2ex.com/avatar/158d/22c6/531255_normal.png?m=1698641538)||3<br><br>**[Linho1219](/member/Linho1219)**  <br><br>   12 小时 46 分钟前 via Android<br><br>感觉 wasm 还是突出一个方便吧，让 PWA 能做更多的事情，看看能不能早点把 Electron 干掉（|

|   |   |   |
|---|---|---|
|![w568w](https://cdn.v2ex.com/gravatar/a07da489e1f63eaa83cded683786df23?s=48&d=retro)||4<br><br>**[w568w](/member/w568w)**  <br><br>   12 小时 44 分钟前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>WebAssembly 的另一个雄心壮志是脱离 Web ，就像 WebGPU 、WebRTC 一样，成为可以独立存在的技术。  <br>  <br>WebGPU 现在已经发展成一个桌面图形技术栈，有自己的 Shader 语言； WebRTC 也成为 P2P 协议的一种了。这个意义上来说，WebAssembly 其实有替代 JVM 、成为原生应用虚拟机的目标。  <br>  <br>像 [https://wasmtime.dev/](https://wasmtime.dev/) 这样的独立 WebAssembly 运行时，已经比较成熟了。只是「一次编译，到处运行」的需求究竟存不存在，还真不好说。|

|   |   |   |
|---|---|---|
|![sagaxu](https://cdn.v2ex.com/avatar/a4b7/3b82/200123_normal.png?m=1735644881)||5<br><br>**[sagaxu](/member/sagaxu)**  <br><br>   12 小时 42 分钟前<br><br>WebAssembly ，大概率绑死在 Web 领域，脱离 Web 意义不大，其它语言拿 wasm 重写一个 runtime ，或者编译到 wasm 意义何在？恐怕还不如 CLR/JVM 或者 llvm/graalvm 靠谱。|

|   |   |   |
|---|---|---|
|![shui14](https://cdn.v2ex.com/gravatar/3b4876f071130eddc1b5cb25533f4897?s=48&d=retro)||6<br><br>**[shui14](/member/shui14)**  <br><br>   12 小时 31 分钟前<br><br>楼上提到的，webgpu 。很多人被这个 web 骗了，不管 dawn 还是 wgpu ，都是 native 优先，在 web 上只是一个最小子集  <br>wasm 同样，wasi 在于没有里程碑的应用，各大平台壁垒没那么容易突破，flash 是特例，技术上人家 as 没毛病。vercel 的 serverless function 提供了多语言架构的可能，就是一个项目里多个模块选不同的方案  <br>我做过一个测试，不过有点久了  <br>[https://www.v2ex.com/t/963777](https://www.v2ex.com/t/963777)  <br>它的 rust 实现就是 wasm 方案，其他语言好像也有这种方式|

|   |   |   |
|---|---|---|
|![tool2dx](https://cdn.v2ex.com/avatar/c810/399e/684488_normal.png?m=1736062402)||7<br><br>**[tool2dx](/member/tool2dx)**  <br><br>   12 小时 8 分钟前 via Android<br><br>专业前端谁用 wasm 啊，都是框架。这就是设计给后端用的。  <br>但是后端有那么多语言可选，也未必选 wasm 。|

|   |   |   |
|---|---|---|
|![nagisaushio](https://cdn.v2ex.com/avatar/cc0a/2c9a/661506_normal.png?m=1703076362)||8<br><br>**[nagisaushio](/member/nagisaushio)**  <br><br>   12 小时 7 分钟前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>wasm 在 web 外最有力的应用应该是助力插件系统|

|   |   |   |
|---|---|---|
|![yplam](https://cdn.v2ex.com/avatar/0e54/04e0/178523_normal.png?m=1548727748)||9<br><br>**[yplam](/member/yplam)**  <br><br>   12 小时 4 分钟前 via Android<br><br>用 WebAssembly 仅仅是因为有些库已经用其他语言实现了，封装一下给 JS 调用|

|   |   |   |
|---|---|---|
|![TimPeake](https://cdn.v2ex.com/avatar/9da1/d8ae/352325_normal.png?m=1708952363)||10<br><br>**[TimPeake](/member/TimPeake)**  <br><br>   11 小时 30 分钟前<br><br>没啥大的出路。js 那么容易上手， 在加上现在 ai 的辅助， 实在想不出用 wasm 的场景。|

|                                                                                     |     |                                                                                             |
| ----------------------------------------------------------------------------------- | --- | ------------------------------------------------------------------------------------------- |
| ![importmeta](https://cdn.v2ex.com/avatar/2018/6513/562972_normal.png?m=1733475592) |     | 11<br><br>**[importmeta](/member/importmeta)**  <br><br>   9 小时 44 分钟前<br><br>没人说 Blazor 吗? |

|   |   |   |
|---|---|---|
|![moonheart](https://cdn.v2ex.com/avatar/b82f/3b6f/397965_normal.png?m=1719254602)||12<br><br>**[moonheart](/member/moonheart)**  <br><br>   9 小时 41 分钟前<br><br>envoy 使用 wasm 做热拔插的插件系统 [https://github.com/proxy-wasm/spec/blob/main/docs/WebAssembly-in-Envoy.md](https://github.com/proxy-wasm/spec/blob/main/docs/WebAssembly-in-Envoy.md)|

|                                                                                         |     |                                                                                                                  |
| --------------------------------------------------------------------------------------- | --- | ---------------------------------------------------------------------------------------------------------------- |
| ![wanghoi](https://cdn.v2ex.com/gravatar/bdada60af0164d1623bbe46638bbcd20?s=48&d=retro) |     | 13<br><br>**[wanghoi](/member/wanghoi)**  <br><br>   9 小时 36 分钟前<br><br>wasm 有 simd 支持，计算密集部分速率 2~10x ，像 IDCT 计算 |
|                                                                                         |     |                                                                                                                  |
