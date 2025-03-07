---
link: https://www.v2ex.com/t/1106467
site: V2EX
date: 2025-01-20T14:16
excerpt: 程序员 - @llej - 突然想明白了为什么要有依赖注入了：这里只讨论在组合优于继承的这种情况下
  一定会有许多的函数组合情况，而且还会有函数组合的组合，这样实质上形成了一个函数之间的依赖链路。如果是直接在代码中硬编码对
twitter: https://twitter.com/@V2EX
slurped: 2025-02-13T17:28
title: 对于依赖注入的思考 - V2EX
---
 
  [llej](/member/llej) · 24 天前 · 2673 次点击

突然想明白了为什么要有依赖注入了：这里只讨论在组合优于继承的这种情况下 一定会有许多的函数组合情况，而且还会有函数组合的组合，这样实质上形成了一个函数之间的依赖链路。

如果是直接在代码中硬编码对应的函数组合的话，我要实现一个新的高阶组合他和原来的高阶组合的唯一区别只是一个基础函数的实现不一致，那我基本需要重新复制一遍原来的组合代码，然后修改其中一个调用

如果要想复用原来的高阶组合，而只是修改其中对于该基础函数的替换的话，要么将该函数作为参数传递（这个传递链路可能很长），而依赖注入就是为了解决这个问题而存在的。

有了依赖注入，只需要在编写代码的时候就通过依赖注入来调用函数，后续的替换就十分的方便了。

```js
function baseFn_A(){}
function baseFn_B(){}
function higherFn_B(){
	baseFn_A()
	//other baseFn ...
}

function higherFn_C(){
	higherFn_B()
	//other baseFn / higherFn ...
}
// 这中间还可能有更多层次的这样的套娃

// 上面存在一个依赖链路 higherFn_C>higherFn_B>baseFn_A
// 如果我要实现一个新的函数 higherFn_C2 ，它和 higherFn_C 唯一的区别就是调用的是 baseFn_B 而非 baseFn_A
// 我认为依赖注入就是为了更方便的创建 higherFn_C2 而不需要改动特别多的代码
```

## 如何实现依赖注入

> 依赖注入可以使用链表来理解。js 的原型链就可以认为是一种依赖注入

只要实现 `inject` 和 `provide` 这两个函数就可以了

`provide` 实现 ：接受一个 key 和 value ， 将这两个参数和当前节点相绑定

`inject` 实现 ：接受一个 key ， 在任意一个节点，沿父级一直向上通过 key 查询对应的注入的值，找到了就返回，没有就找父级的父级。

`inject` 的实现基本和 js 对象基于原型链查找属性值的实现方式是一样的。所以我说 <u>js 的原型链就可以认为是一种依赖注入</u>

如何使用链表来理解呢：

比如 vue 中的依赖注入系统，这里的链表是组件树中，将组件理解为节点，然后一直查找上一层组件，一直到顶层，其中经过的所有节点就是一个链表，基于这个链表，最末端的节点，可以获取他的任意一个父级节点 `provide` 的值，并且在 key 相同的情况下 `inject` 的是离他最近的一个节点 `provide` 的值

但如果我们要以函数为节点，以函数调用栈作为链表来实现一个依赖注入系统可行吗？

答案是可以但又不可以，因���在浏览器中是受限的，只能基于 [zone.js](https://shenzilong.cn/other/zone.js.html#20210409090637-h0drlqf) 来实现（存在缺陷）

[在 node.js 的环境下可以选择使用 Async hooks 来达成同样的目的](https://shenzilong.cn/other/zone.js.html#20210608231606-cw5th69)


21 条回复  **•**  2025-02-02 18:50:46 +08:00

|   |   |   |
|---|---|---|
|![sapjax](https://cdn.v2ex.com/avatar/1d3b/7f1f/4786_normal.png?m=1715995247)||1<br><br>**[sapjax](/member/sapjax)**  <br><br>   24 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>首先要区分依赖倒置和依赖注入  <br>依赖注入是实现依赖倒置的一个环节  <br>依赖倒置的目的不是为了方便，而是管理依赖的方向，避免环形依赖  <br>让具体的外部实现依赖一个内部的 Interface ，避免内部依赖具体的外部实现，这样就把依赖的方向倒转过来了  <br>那么外部实现是如何生效的呢，这就涉及到依赖注入，通过自动注入让内部实现调用 Interface 的时候，可以找到正确的实现|

|   |   |   |
|---|---|---|
|![importmeta](https://cdn.v2ex.com/avatar/2018/6513/562972_normal.png?m=1733475592)||2<br><br>**[importmeta](/member/importmeta)**  <br><br>   24 天前<br><br>之前研究过依赖注入.  <br>  <br>推荐两个  <br>[https://github.com/microsoft/tsyringe](https://github.com/microsoft/tsyringe)  <br>[https://github.com/inversify/InversifyJS](https://github.com/inversify/InversifyJS)|

|   |   |   |
|---|---|---|
|![icode1688](https://cdn.v2ex.com/gravatar/53cbb62174abf97818e229f016653fd6?s=48&d=retro)||3<br><br>**[icode1688](/member/icode1688)**  <br><br>   24 天前<br><br>inversify/InversifyJS 竟然不支持 typescript 5.x|

|   |   |   |
|---|---|---|
|![Orangeee](https://cdn.v2ex.com/gravatar/0e522bb6f9e9b9fab7b47c3f138b3cba?s=48&d=retro)||4<br><br>**[Orangeee](/member/Orangeee)**  <br><br>   24 天前<br><br>JS 原型链 和 DI 没有关系，相似点可能是都复用了代码|

|   |   |   |
|---|---|---|
|![llej](https://cdn.v2ex.com/avatar/b4e7/fabc/451595_normal.png?m=1596437487)||5<br><br>**[llej](/member/llej)**  <br><br>OP<br><br>   24 天前<br><br>@[icode1688](/member/icode1688) 但这些都是基于类的，我最想要的是基于函数调用的。|

|   |   |   |
|---|---|---|
|![llej](https://cdn.v2ex.com/avatar/b4e7/fabc/451595_normal.png?m=1596437487)||6<br><br>**[llej](/member/llej)**  <br><br>OP<br><br>   24 天前<br><br>@[importmeta](/member/importmeta) 但这些都是基于类的，我最想要的是基于函数调用的。|

|   |   |   |
|---|---|---|
|![runlongyao2](https://cdn.v2ex.com/gravatar/5cb4d4c0051e8affe31fa798d57d7f58?s=48&d=retro)||7<br><br>**[runlongyao2](/member/runlongyao2)**  <br><br>   24 天前<br><br>对于类是第一公民的语言，比如 JAVA,C#，依赖注入能降低复杂度。但是对于 JS ，GO 这类语言就大可不必。原因也很简单，JAVA 的表达方式基于类，灵活性是很差的，所以需要所谓的设计模式去弥补|

|   |   |   |
|---|---|---|
|![importmeta](https://cdn.v2ex.com/avatar/2018/6513/562972_normal.png?m=1733475592)||8<br><br>**[importmeta](/member/importmeta)**  <br><br>   24 天前<br><br>@[llej](/member/llej) 函数用组合模式的多吧, 比如 React 的 Hooks.|

|   |   |   |
|---|---|---|
|![mcfog](https://cdn.v2ex.com/avatar/442b/548e/7379_normal.png?m=1721639123)||9<br><br>**[mcfog](/member/mcfog)**  <br><br>   24 天前<br><br>虽然都是 js ，原型链和组件-父组件构成的链完全不是一回事儿  <br>  <br>用链表理解依赖注入怎么想都是歪的  <br>  <br>OP 后面描述的一些行为，比起依赖注入，似乎更像职责链模式|

|   |   |   |
|---|---|---|
|![newaccount](https://cdn.v2ex.com/avatar/12cb/9729/528250_normal.png?m=1713948986)||10<br><br>**[newaccount](/member/newaccount)**  <br><br>   24 天前<br><br>DI 是用来处理 OOP 的，不管 FP 这一摊子|

|   |   |   |
|---|---|---|
|![3085570450tt](https://cdn.v2ex.com/gravatar/938969e2ac0a93f3f780e82c2ab2f1dc?s=48&d=retro)||11<br><br>**[3085570450tt](/member/3085570450tt)**  <br><br>   24 天前<br><br>@[importmeta](/member/importmeta) 也推荐用 inversifyJS 的一个项目，Theia [https://theia-ide.org/](https://theia-ide.org/)|

|   |   |   |
|---|---|---|
|![cybernty](https://cdn.v2ex.com/gravatar/bda48af70c455b84d784c22c81dd1cab?s=48&d=retro)||12<br><br>**[cybernty](/member/cybernty)**  <br><br>   23 天前<br><br>[https://quii.gitbook.io/learn-go-with-tests/go-fundamentals/dependency-injection](https://quii.gitbook.io/learn-go-with-tests/go-fundamentals/dependency-injection)|

|   |   |   |
|---|---|---|
|![lixiaolin123](https://cdn.v2ex.com/gravatar/23fcf6bdc8cf7b897c930b91fc1bad17?s=48&d=retro)||13<br><br>**[lixiaolin123](/member/lixiaolin123)**  <br><br>   23 天前<br><br>@[runlongyao2](/member/runlongyao2) 想知道 go 是如何使用回调的。java 我知道有个 Obcsrver 设计模式来实现回调，go 是否在实现回调上比 java 简单？|

|   |   |   |
|---|---|---|
|![GeekGao](https://cdn.v2ex.com/avatar/6540/f6ff/30946_normal.png?m=1731046133)||14<br><br>**[GeekGao](/member/GeekGao)**  <br><br>   23 天前<br><br>认同 1 楼观点。  <br>  <br>不过补充一下：  <br>依赖倒置原则：是一种设计思想，它告诉我们应该依赖抽象，而不是具体实现。  <br>依赖注入：是一种实现方式，它通过外部注入依赖，帮助我们实现依赖倒置原则。  <br>  <br>  <br>依赖倒置原则就像是一个“万能遥控器” 它不直接依赖具体的电器，而是依赖一个通用的接口。这样，无论电器如何变化，遥控器都能正常工作，系统也更易于维护和扩展。  <br>  <br>依赖注入过程就像电器独立实现自己的核心控制逻辑。然后通过蓝牙协议与“万能遥控器” 进行连接，这个过程，不会对万能遥控器进行任何代码更改。  <br>  <br>核心思想就是：高层模块（遥控器）不应该依赖低层模块（电器），而是两者都应该依赖抽象（电源开关接口）。|

|   |   |   |
|---|---|---|
|![charlie21](https://cdn.v2ex.com/gravatar/5765a702fda4ba24599890b4c40cc2de?s=48&d=retro)||15<br><br>**[charlie21](/member/charlie21)**  <br><br>   23 天前<br><br>@[icode1688](/member/icode1688) inversify 6.2.1 和 typescript 5.7.3 在项目里同时使用是没发现问题的|

|   |   |   |
|---|---|---|
|![AEnjoyable](https://cdn.v2ex.com/avatar/af0b/0ec5/668228_normal.png?m=1716786434)||16<br><br>**[AEnjoyable](/member/AEnjoyable)**  <br><br>   23 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>@[lixiaolin123](/member/lixiaolin123) go 的函数参数可以传递函数，然后还支持匿名函数 那想做回调就很好办|

|   |   |   |
|---|---|---|
|![runlongyao2](https://cdn.v2ex.com/gravatar/5cb4d4c0051e8affe31fa798d57d7f58?s=48&d=retro)||17<br><br>**[runlongyao2](/member/runlongyao2)**  <br><br>   23 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>@[lixiaolin123](/member/lixiaolin123)  <br>package main  <br>  <br>import "fmt"  <br>  <br>// 定义一个回调函数类型  <br>type Callback func(int) int  <br>  <br>// 处理函数，接受一个回调函数作为参数  <br>func process(value int, callback Callback) {  <br>result := callback(value)  <br>fmt.Println("Callback result:", result)  <br>}  <br>  <br>// 一个示例回调函数  <br>func double(x int) int {  <br>return x * 2  <br>}  <br>  <br>// 另一个示例回调函数  <br>func square(x int) int {  <br>return x * x  <br>}  <br>  <br>func main() {  <br>value := 5  <br>  <br>// 使用 double 作为回调函数  <br>process(value, double)  <br>  <br>// 使用 square 作为回调函数  <br>process(value, square)  <br>}  <br>  <br>GPT 生成的和 JS 很类似|

|   |   |   |
|---|---|---|
|![runlongyao2](https://cdn.v2ex.com/gravatar/5cb4d4c0051e8affe31fa798d57d7f58?s=48&d=retro)||18<br><br>**[runlongyao2](/member/runlongyao2)**  <br><br>   23 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>@[lixiaolin123](/member/lixiaolin123) OOP 的年代已经过去了，那会儿 OOP 大行其道，所以 JAVA 和 C#都是基于这套东西设计的，之后设计的语言可能都不存在类这个概念比如 GO|

|   |   |   |
|---|---|---|
|![icode1688](https://cdn.v2ex.com/gravatar/53cbb62174abf97818e229f016653fd6?s=48&d=retro)||19<br><br>**[icode1688](/member/icode1688)**  <br><br>   23 天前<br><br>@[charlie21](/member/charlie21) 喔不好意思，我表达有误，是不支持 stage 3 阶段的注解，也就是 tsconfig.json 中不需要配置 experimentalDecorators: true  <br>emitDecoratorMetadata: true  <br>  <br>TypeScript 5.0 版本，支持 stage3 阶段的装饰器写法。  <br>  <br>[https://www.typescriptlang.org/docs/handbook/release-notes/typescript-5-0.html#decorators](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-5-0.html#decorators)|

|   |   |   |
|---|---|---|
|![johnhom](https://cdn.v2ex.com/avatar/43e0/2245/577941_normal.png?m=1681781015)||20<br><br>**[johnhom](/member/johnhom)**  <br><br>   22 天前<br><br>@[llej](/member/llej) #6 其实都上了依赖注入，最好就是跟着用类去写，同时继承接口的写法也更易懂，而且这样符合依赖倒置原则（高层模块不应依赖于低层模块，二者应依赖于抽象）方便代码的解耦。  <br>给你看示例代码感受一下：  <br>[![](https://i.imgur.com/Q22LH9g.png)](https://i.imgur.com/Q22LH9g.png)  <br>[![](https://i.imgur.com/zxD5oWB.png)](https://i.imgur.com/zxD5oWB.png)  <br>  <br>而且我可以通过继承 LocalStorageService 这个类，来增加更多额外的功能。当然也可以控制继承的嵌套，我觉得用函数来写的话有点没有那么容易理解|

|   |   |   |
|---|---|---|
|![zhuangzhuang1988](https://cdn.v2ex.com/avatar/c6af/9dc4/121655_normal.png?m=1434286696)||21<br><br>**[zhuangzhuang1988](/member/zhuangzhuang1988)**  <br><br>   10 天前<br><br>@[runlongyao2](/member/runlongyao2) 真复杂的项目还是要的 比如说 vscode  <br>[https://github.com/microsoft/vscode/tree/main/src/vs/platform/instantiation/common](https://github.com/microsoft/vscode/tree/main/src/vs/platform/instantiation/common)  <br>这是 vscode 的 IOC 实现，整个 vscode 都依赖  <br>[https://github.com/microsoft/vscode/blob/main/src/vs/workbench/browser/web.main.ts#L271](https://github.com/microsoft/vscode/blob/main/src/vs/workbench/browser/web.main.ts#L271) 各种服务注册|
