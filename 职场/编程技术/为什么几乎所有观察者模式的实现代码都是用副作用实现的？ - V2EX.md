---
link: https://www.v2ex.com/t/1101064
site: V2EX
date: 2024-12-29T18:00
excerpt: 程序员 - @netabare - 感觉很难理解，因为几乎所有的教程/教材，样例代码或者实际代码里面，提到观察者模式的时候，都是清一色的用返回
  void 的方法来 visit 和 accept ，然后依赖副作用和全局变量来返回结果。
twitter: https://twitter.com/@V2EX
slurped: 2025-02-06T21:35
title: 为什么几乎所有观察者模式的实现代码都是用副作用实现的？ - V2EX
---
 

  [netabare](/member/netabare) · 39 天前 · 3488 次点击


感觉很难理解，因为几乎所有的教程/教材，样例代码或者实际代码里面，提到观察者模式的时候，都是清一色的用返回 void 的方法来 visit 和 accept ，然后依赖副作用和全局变量来返回结果。

感觉这样的代码很难懂而且很绕，也可能因为我比起命令式或 OOP 代码更容易理解纯函数式代码吧。

就，比如说我试图理解 visitor pattern 的话，我会把它当成一个「在命令式语言里通过动态分派实现模式匹配」的技巧。自然而然的就会想出这样的代码，比如说在 Java 里的话：

```java
public ISomeVisitor<T> {
  public T visit(DerivedDataTypeA data);
  public T visit(DerivedDataTypeB data);
    ...
}
public IDataType {
  public T accept(ISomeVisitor visitor);
}
```

然后在 visitor 的具体实现里面，就只需要去重写然后使用 DerivedDataType 里面的访问方法去处理它，然后返回一个转换后的?T 类型。同时，由于每个 visit 分支都返回相同的类型，它们可以被组合起来，看起来就跟比如 Scala 或者 ML 语言里的模式匹配是同样的方式。

嗯，这个是理想情况。

但我记得在大学里学习 OOP 然后第一次按照这个路子写 visitor 后，就被其他人纠正说我实现的方法不对，因为我在 visit 函数里实现了具体逻辑。嗯，我一直没能搞懂为什么我实现错了，其实现在我也没搞懂。

但是我其实对返回 void 的方法和没有参数化泛型的类感觉更难理解，大概有这么几个原因吧：

- 首先是这样实现的模式完全依赖于副作用，而不是显式的返回一个值。给人想起了 C 语言里的通过参数返回函数结果的代码风格，至少对我来说，感觉这样的代码更难懂，因为没有类型安全，而且靠副作用来操纵数据变换的时候，基本上算是做啥都行也没有任何机制可以保证返回结果能够被妥善的使用并且只使用一次。感觉像是典型的约定大于类型。
- 其次是这样的代码里基本上可以不管什么都往 visitor 的基类里面塞，感觉就很自然地倒向了 god class 的反模式。而且这也是经常在使用了 visitor 的工程代码里看到的，而且每次看到这样的几百行甚至上千行的 visitor 都特别头疼。
- 同样的道理，我可以有一个`public Result returnedResult;`在第 19 行，然后我的几十个分支里面都去 mutate 这个`Result`来返回一次访问的结果，就像刚才说的，没有任何机制可以让我不去随意修改这个`returnedResult`来破坏 visitor pattern 的模式。但同时，一个字段可以在第 19 行，第 199 行和第 1099 行被修改，这也破坏了「就近原则」吧？而且这里也可以看到一个潜在的 NPE 热点。

所以觉得这样的代码既难以理解又难以维护。

当然也许有人会说顺序很重要，但是一般来说 visitor 在业务代码例如 web 应用里面都是用在树状数据结构上，这种使用场景应该没差？

所以我感觉困惑的大概就是，我这个 visitor 的实现思路错在了哪里？为什么几乎清一色的所有 visitor 的代码实现都是返回 void 方法并且通过副作用修改全局变量来储存返回计算结果的？这样做是为了什么呢？

然后这个草稿写完之后又读了一本叫 A little Java, A few Patterns 的书，就感觉更困惑了。因为这本书里的 visitor 不但也是不依赖副作用而是返回值的，它的 visit 函数甚至还可以接受多个参数，看起来更不符合 visitor 的一般定义。

所以我该怎么理解这个 visitor pattern 呢？



23 条回复  **•**  2025-01-08 16:59:08 +08:00

|   |   |   |
|---|---|---|
|![donaldturinglee](https://cdn.v2ex.com/avatar/3a3f/543e/660751_normal.png?m=1699538555)||1<br><br>**[donaldturinglee](/member/donaldturinglee)**  <br><br>   39 天前<br><br>https://refactoring.guru/design-patterns/visitor 你可以参考一下这个，或者读一下 C++那本设计模式的书（很经典，但很难读）|

|   |   |   |
|---|---|---|
|![netabare](https://cdn.v2ex.com/avatar/6bf8/3d7c/125600_normal.png?m=1703247518)||2<br><br>**[netabare](/member/netabare)**  <br><br>OP<br><br>   39 天前<br><br>@[donaldturinglee](/member/donaldturinglee) 我了解这个网站，而且这个网站也属于我提到的「用副作用实现观察者模式」的例子。|

|   |   |   |
|---|---|---|
|![w568w](https://cdn.v2ex.com/gravatar/a07da489e1f63eaa83cded683786df23?s=48&d=retro)||3<br><br>**[w568w](/member/w568w)**  <br><br>   39 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>> 当然也许有人会说顺序很重要，但是一般来说 visitor 在业务代码例如 web 应用里面都是用在树状数据结构上，这种使用场景应该没差？  <br>  <br>你也想到了，如果 visitor 的结果依赖于访问状态（例如访问的顺序或访问的次数），你提出的这种设计就失效了。换句话说，你的设计要求 visitor 必须是无状态的（或者通俗地说，纯的），这就限制了使用场景。  <br>  <br>因此，不如在设计上退一步。无论是否需要访问状态，都要求访问者自己维护。|

|   |   |   |
|---|---|---|
|![nightwitch](https://cdn.v2ex.com/gravatar/77243c335d62c63de4032362b413f451?s=48&d=retro)||4<br><br>**[nightwitch](/member/nightwitch)**  <br><br>   39 天前<br><br>不带状态的 visitor 反而比较少见..  <br>visitor 经常有根据一些条件停止继续遍历或者记录一下是否碰见过某种节点以执行不同逻辑的需求吧|

|   |   |   |
|---|---|---|
|![netabare](https://cdn.v2ex.com/avatar/6bf8/3d7c/125600_normal.png?m=1703247518)||5<br><br>**[netabare](/member/netabare)**  <br><br>OP<br><br>   39 天前<br><br>@[w568w](/member/w568w)  <br>@[nightwitch](/member/nightwitch)  <br>  <br>  <br>我能想到的一个「针对依赖访问状态」的解决办法就是加一个中间层来表达顺序访问或者访问次数等信息，最简单的实现可以是这样的：  <br>  <br>```java  <br>interface IResult<T> { ... }  <br>class Skip<T> implements IResult<T> { ... }  <br>class Ok<T> implements IResult<T> { ... }  <br>```  <br>  <br>这只是个例子，不代表说一定要这么做。当然实际业务代码几乎没人这么做就是，但我想说的是这个「依赖访问状态」并不是无解的。  <br>  <br>而且换过来说，业务代码里增加不同的层级和抽象不也是很经常的手法嘛？ Stream 或者第三方库里面这样的工具也很多，为什么在 visitor 模式上反而不能够通过增加一层来解决问题了呢？引入可变状态和副作用的代价就不需要考虑一下吗？  <br>  <br>而且很多场景，例如我自己参与维护的一些代码项目里，经常在重构的时候需要花大量时间理解修改状态和副作用到底怎么桥接起来，最后发现很多代码实际上压根不依赖于访问状态，也对访问顺序没有任何前提要求，看起来更像是单纯的惯性所致，而且这样的 visitor 见一两个也就算了，项目里到处都是而且平均 LOC 几百上千行的时候，连重构都难下手。这也是我提出这个帖子的问题的原因——以前我是默认「 visitor 模式需要有状态，只是我不懂，可能工程代码里有最佳实践」，但在工作一两年接触了更多工程代码后，现在我对这个定论更多持有怀疑态度。  <br>  <br>反过来说，以教育和入门为目的的代码样例，例如大学 OOP 课上的代码，也是出于「 visitor 需要依赖可变状态」的前提来设计代码实现的吗？  <br>  <br>这里的问题在于，副作用、修改全局变量这些本质上都是不可推理并且无法用类型等东西来建模的，固然可以用单元测试来「告诉使用者这个 API 怎么使用」，但作为一个同时维护和使用 API 的开发者，我对这样的代码有极大的不适感。|

|   |   |   |
|---|---|---|
|![mahaoqu](https://cdn.v2ex.com/gravatar/4b1915880604a79838181f4f53c47dc5?s=48&d=retro)||6<br><br>**[mahaoqu](/member/mahaoqu)**  <br><br>   38 天前<br><br>观察者模式只是一种（面向对象语言用子类型模拟和类型时）模拟模式匹配的方法，又不是真正的模式匹配，当然不是一定得无副作用。我觉得这只是风格不同，没有对错之分。  <br>  <br>不过他们的理由可能是因为面向对象强调的内聚性：操作 DerivedDataTypeA 的方法当然应该在这个类里，不应该在 visitor 里，visitor 就应该只调用 data.opeartionXX() 就返回，这样也说得通。  <br>  <br>Visitor Pattern 其实出现的原因很简单，就是一个抽象父类一大堆子类，但是想要为一部分子类加一个方法的时候不想重新分别修改每个子类来实现它。按照命令式语言的逻辑，当然不需要关心这个操作有没有副作用——当然把返回值塞到父类的成员里就是严重的设计错误了。  <br>  <br>返回值的 Visitor Pattern 我感觉做个解释器之类的比较适合吧，其他情况下也用不太上。知乎上有很多讨论 Expression Problem 的文章，OP 可以看看。|

|   |   |   |
|---|---|---|
|![minami](https://cdn.v2ex.com/avatar/e4fb/44aa/174924_normal.png?m=1702609067)||7<br><br>**[minami](/member/minami)**  <br><br>   38 天前 via Android<br><br>别的语言不敢说，C++这边，观察者模式就是乐色，一用一个不吱声，建议用信号槽替代|

|   |   |   |
|---|---|---|
|![sagaxu](https://cdn.v2ex.com/avatar/a4b7/3b82/200123_normal.png?m=1735644881)||8<br><br>**[sagaxu](/member/sagaxu)**  <br><br>   38 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>visitor 是观察者，那 observer 又是什么？|

|   |   |   |
|---|---|---|
|![netabare](https://cdn.v2ex.com/avatar/6bf8/3d7c/125600_normal.png?m=1703247518)||9<br><br>**[netabare](/member/netabare)**  <br><br>OP<br><br>   38 天前 via Android<br><br>@[sagaxu](/member/sagaxu) 没必要抠字眼，我人在国外平时用的都是 visitor ，没那么熟悉中文定义。再说我这篇贴子里有提到一个 observer ？|

|   |   |   |
|---|---|---|
|![lesismal](https://cdn.v2ex.com/avatar/a296/b6c2/497905_normal.png?m=1731414322)||10<br><br>**[lesismal](/member/lesismal)**  <br><br>   38 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>设计模式的糟粕害人挺多的, 观察者是少数实用的之一, 和发布订阅本质上是类似的.  <br>没必要把自己陷在某个语言的实现方式上, 理解它的用途, 融会贯通的实际运用就可以了. 我当年写 C 为了模块之间解耦自己就搞了个出来, 当时都不知道这玩意是个设计模式, 后来看设计模式的书才知道原来这叫做观察者.  <br>  <br>BTW, 至今设计模式我也没记住几个, 反倒让自己代码通常比多数人更简洁一点.|

|   |   |   |
|---|---|---|
|![visper](https://cdn.v2ex.com/gravatar/838db077a2334ed6bcbc29c29ab41a6e?s=48&d=retro)||11<br><br>**[visper](/member/visper)**  <br><br>   38 天前<br><br>visitor 只是为了把一类相同功能的方法，本来都需要写成各种不同的实现类里面的，抽取到一个公共的地方。这样的话不需要每次加一类功能方法的时候所有的实现类都改一次然后都要重新编译。所以那个方法怎么实现都可以吧。 感觉很多设计模式都是为了少改些类不用重新都编译设计的。|

|   |   |   |
|---|---|---|
|![zhuisui](https://cdn.v2ex.com/avatar/3773/9b2a/274978_normal.png?m=1573811904)||12<br><br>**[zhuisui](/member/zhuisui)**  <br><br>   38 天前<br><br>我想说，大概就是因为你搞错了翻译，使得你理解错了这个模式。  <br>visitor 不是观察者，visitor 是访问者。  <br>visitor 模式用来解决的业务问题是——将访问图等各类对象数据结构的算法和其具体的业务逻辑分离，这里面 visitor 指的是 visit objects 。  <br>  <br>至于该模式的具体实现，是否 accept 有返回值，不是首要重点，但也很重要，符合了最广泛的一种业务模式。  <br>像 https://refactoring.guru/design-patterns/visitor 中的实现，无返回值。试想，如果 client 调用各类 ele 的 accept 返回各种 node 的处理结果，那么这些结果就需要由 client 自己集合为最终结果，但这部分是具体业务逻辑，应该由具体的 visitor 实现来负责。|

|   |   |   |
|---|---|---|
|![GiantHard](https://cdn.v2ex.com/avatar/a1bc/a77b/280209_normal.png?m=1690705146)||13<br><br>**[GiantHard](/member/GiantHard)**  <br><br>   38 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>> 所以我感觉困惑的大概就是，我这个 visitor 的实现思路错在了哪里？  <br>  <br>我认为你的实现没错，在实践中也存在类似的设计 [https://learn.microsoft.com/en-us/dotnet/api/microsoft.codeanalysis.csharp.csharpsyntaxvisitor-1?view=roslyn-dotnet-4.9.0](https://learn.microsoft.com/en-us/dotnet/api/microsoft.codeanalysis.csharp.csharpsyntaxvisitor-1?view=roslyn-dotnet-4.9.0)  <br>  <br>> 为什么几乎清一色的所有 visitor 的代码实现都是返回 void 方法并且通过副作用修改全局变量来储存返回计算结果的？这样做是为了什么呢？  <br>  <br>我认为是否使用「副作用」属于开发者的个人习惯甚至是编程语言的风格，比如 [https://refactoringguru.cn/design-patterns/visitor/rust/example](https://refactoringguru.cn/design-patterns/visitor/rust/example) 中 Rust 实现的 Visitor 中，visit 函数有返回值，但是用 C++ 实现 [https://refactoringguru.cn/design-patterns/visitor/cpp/example](https://refactoringguru.cn/design-patterns/visitor/cpp/example) 的 Visitor 就没有返回值。  <br>  <br>如果开发者经常使用的编程语言鼓励可变状态，那么他大概率就会用副作用实现 Visitor 模式中的计算；如果开发者更认同不可变状态并且使用的编程语言也鼓励不可变状态，那么他大概率会采用使用返回值的 Visitor 模式。|

|   |   |   |
|---|---|---|
|![Belmode](https://cdn.v2ex.com/avatar/58c3/16c0/312499_normal.png?m=1730809702)||14<br><br>**[Belmode](/member/Belmode)**  <br><br>   38 天前<br><br>@[zhuisui](/member/zhuisui) #12 这是不是就是传说中的鸡同鸭讲成语的由来？😂😂😂|

|   |   |   |
|---|---|---|
|![netabare](https://cdn.v2ex.com/avatar/6bf8/3d7c/125600_normal.png?m=1703247518)||15<br><br>**[netabare](/member/netabare)**  <br><br>OP<br><br>   38 天前<br><br>@[mahaoqu](/member/mahaoqu) 话说 Expression Problem 有什么具体的文章或者讨论可以指一下路吗？我想看看。  <br>  <br>@[lesismal](/member/lesismal) 我倒是对设计模式并没有怎么太去学，但是造自己语言思考语义和语法的时候，再结合平时的日常工作，就不免会回过头想这些问题。  <br>  <br>@[zhuisui](/member/zhuisui) 换句话说就是 visitor 从设计模式的角度讲只追求分离，并不在乎 dynamic dispatch 和子类型的运行时自动求解，对吗？如果从这个角度讲，那么似乎说得过去……但这么一来这个设计模式对我的兴趣可能也就剩不下多少了。  <br>  <br>@[GiantHard](/member/GiantHard) 我觉得你说的有道理。感谢。|

|   |   |   |
|---|---|---|
|![netabare](https://cdn.v2ex.com/avatar/6bf8/3d7c/125600_normal.png?m=1703247518)||16<br><br>**[netabare](/member/netabare)**  <br><br>OP<br><br>   38 天前<br><br>另外关于返回值，我给出的`ISomeVisitor`本身是用 T 去参数化限定它的返回类型。但是在业务代码里面返回类型受限应该不是什么问题？考虑一个复杂数据类型树的话，那么用泛型和返回值可以让 visitor 的职责更清晰吧？  <br>  <br>比如说一个订单和用户还有交易构成的数据类型的话，定义三个 visitor ，比如说  <br>  <br>```java  <br>class OrderVisitor extends ISomeVisitor<IOrder>  <br>class TxVisitor extends ISomeVisitor<ITx>  <br>class UserVisitor extends ISomeVisitor<IUser>  <br>```  <br>  <br>然后自然而然每个 visitor 的 visit 和 accept 分支都会遵守「这个 visitor 只处理和基类相关的职责」，最后再把 visitor 互相组合起来，不会比一个巨型的，什么都可以做的 visitor 更加清晰可维护吗？  <br>  <br>A little Java, A few Patterns 里面也有提到 visitor 之间可以组合嵌套的例子。  <br>  <br>我在实际代码里面就遇到过那种「一个巨型 visitor 同时承担很多职责」的例子，比如一个 ColorScheme 相关的 visitor 里面不光处理颜色，还要处理字体、排版，甚至把 cache 相关的函数都塞进去的情况。我不觉得哪怕在业务工程的考虑上这样的代码也比使用返回值和泛型参数的代码更好维护。|

|   |   |   |
|---|---|---|
|![snylonue](https://cdn.v2ex.com/avatar/006f/d79d/635353_normal.png?m=1729659971)||17<br><br>**[snylonue](/member/snylonue)**  <br><br>   38 天前<br><br>之前用 tracing 的 visitor pattern 的时候是这样的，一个 visitor 会被调用很多次，最终是要聚合这些结果，当然可以类似 fold 一样做成纯的，但是就性能和易用性而言这样就挺好了  <br>  <br>[https://github.com/ProjectAnni/tracing-subscriber-sqlite/blob/master/src/lib.rs#L177](https://github.com/ProjectAnni/tracing-subscriber-sqlite/blob/master/src/lib.rs#L177)|

|   |   |   |
|---|---|---|
|![mahaoqu](https://cdn.v2ex.com/gravatar/4b1915880604a79838181f4f53c47dc5?s=48&d=retro)||18<br><br>**[mahaoqu](/member/mahaoqu)**  <br><br>   38 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 2<br><br>啊，OP 我觉得我终于懂你在说什么了。  <br>  <br>首先要强调的是 Visitor 是一个行为设计模式，这意味着 Visitor 表达的是一个动作。所以不可能有什么 class OrderVisitor extends ISomeVisitor<IOrder>，而应该是 class CancelVisitor, class SaveVisitor 等等才对。  <br>  <br>面向对象把一个类的多个方法放在一起，而 Visitor 模式恰好反过来了。那 visitor 方法里该怎么做呢？如果数据类是传统的属性封装，那就只能转发给类内部的函数。如果暴露了实现细节，那就可以直接编写实现。Visitor 本身自然不应该包含任何状态（这点你是对的）。  <br>  <br>那么 visit-accept 应该是泛型，或者说该有返回值吗？实际上 Visitor 里的 visit 函数（或者可以把它重命名为和 Visitor 一样的名字）就相当于一个普通的方法，所以它的写法等同于为所有的 DataType 实现，那参数和返回值都是可以任意设计的。  <br>  <br>visitor 模式都可以用一个很简单的转化把方法都塞回原本的数据类里。即：data.accept(evalVisitor) 和 data.eval() 是等价的写法。  <br>  <br>但是如果现在只有一个大而全的万能 visitor 呢？实际上让它的职责更清晰的办法是通过不同操作拆分，而非通过操作的数据类型拆分。这时候，组合 visitor 相当于组合方法。这也是函数式编程的一大特色。  <br>  <br>实际上设计模式只是当时的权宜之计，Java 21 中引入了 Switch 模式匹配。配合 sealed class 后 visitor 的意义就不大了。  <br>  <br>关于 expression problem 可以看这一篇，我觉得非常有水平：  <br>  <br>[https://zhuanlan.zhihu.com/p/53810286](https://zhuanlan.zhihu.com/p/53810286)  <br>  <br>@[netabare](/member/netabare)|

|   |   |   |
|---|---|---|
|![zhuisui](https://cdn.v2ex.com/avatar/3773/9b2a/274978_normal.png?m=1573811904)||19<br><br>**[zhuisui](/member/zhuisui)**  <br><br>   37 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 2<br><br>@[netabare](/member/netabare) 我这样整体地描述该模式，看看是否命中了你的疑惑，因为我觉得可能你对这个模式的运转方式理解错了。  <br>  <br>首先有一组固定类型的 object ，每个 object 内有多种类型的 element ，然后有多个 visitor 可以处理这组 object 。  <br>每个 visitor 定义了一种将这组 object 输出为一种形式的业务逻辑，那么多个 visitor 分别代表可以输出不同形式的业务逻辑，visitor 之间是互相独立的。每种 element 需要对应一个 visitor 的 visitXXXElement 方法的实现。该方法的调用通过 element.accept 来做 dispatch ，这样就避免了业务侧用 switch case 做模式匹配，仅需 iterate elements 的 accept 方法即可完成调用。  <br>其中关于 accept 的返回值，如果对这组 object 进行 visit 的结果是顺序的列表，自然可以直接将返回值简单地 map 为顺序列表。但如果 visit 的结果是其他复杂的类型，这部分业务逻辑必须由 visitor 在内部暂留状态，在整体 visit 结束后通过注入 end 的方法返回。这完全取决于要处理的业务，这部分不是该模式的核心。  <br>其中关于 iterate elements ，这部分甚至也可以做到 visitor 的基类中，取决于 elements 的顺序如何产生，是统一的还是无关的。这部分不是该模式的核心。  <br>  <br>举个例子，把一种 tree 输出为 json 、xml 、table 不同格式的业务。这里 tree 就是 object ，各种 tree node 就是 element ，json xml table 各需要一种 visitor. 其中对于 xml 如果选择用 element 嵌套的格式来表示输出形式，那么自然不可能直接由 accept 返回，因为整体结果是个 xml root element.|

|                                                                                          |     |                                                                                                                                                                                |
| ---------------------------------------------------------------------------------------- | --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ![YuuuuuuH](https://cdn.v2ex.com/gravatar/aa031d11c3cb9e32c9d1227868e836bc?s=48&d=retro) |     | 20<br><br>**[YuuuuuuH](/member/YuuuuuuH)**  <br><br>   37 天前<br><br>@[netabare](/member/netabare) #9 因为 observer 也是个 pattern ，主楼里就有些人跟你说的 [观察者模式] 的看法实际上指的是 observer pattern 。 |

|   |   |   |
|---|---|---|
|![netabare](https://cdn.v2ex.com/avatar/6bf8/3d7c/125600_normal.png?m=1703247518)||21<br><br>**[netabare](/member/netabare)**  <br><br>OP<br><br>   33 天前<br><br>@[zhuisui](/member/zhuisui)  <br>@[mahaoqu](/member/mahaoqu)  <br>  <br>感谢讲解！  <br>  <br>所以这里我想我可能陷入了一个很大的误区，就是把 visitor 机械地等同于 pattern matching ，然后把 pattern matching 在 subtyping 下面的作用（也就是 dynamic dispatch ）给搬运到了 visitor pattern 下，但是这个 dynamic dispatch 只是 visitor 的其中一个「稍微显著但不是主要的作用」，而 visitor pattern 的主要作用，就像 @[mahaoqu](/member/mahaoqu) 说的，「面向对象把一个类的多个方法放在一起，而 Visitor 模式恰好反过来了」，或者 @[zhuisui](/member/zhuisui) 所说的「多个 visitor 分别代表可以输出不同形式的业务逻辑，visitor 之间是互相独立的」这样的作用。  <br>  <br>我的理解是你说的「避免了业务侧用 switch case 做模式匹配，仅需 iterate elements 的 accept 方法即可完成调用」用我前面的表达其实就是「 dynamic dispatch 」对吧。比如用户解析 Tree 的时候，它不关心 Tree 具体长啥样或者具体怎么解析，它只希望能够正确的拿到 XML/JSON 或者 Table 。那么 visitor pattern 就充当了这个解析的作用吧。  <br>  <br>这么说来倒是很多东西都说得清了。  <br>  <br>至于副作用的问题，主要是我对这样的代码有很大的意见：  <br>  <br>```java  <br>class ... {  <br>/* L.18 */ResultType result;  <br>  <br>public void visitSomeArm(...) {  <br>  <br>/* L.259 */ ResultType oldResult = result;  <br>  <br>/* L.343 */ ... = visitAnotherArm(...);  <br>  <br>/* L.569 */ result = ...;  <br>}  <br>  <br>public void VisitAnotherArm(...) {  <br>/* L.1982 */ result = ...  <br>}  <br>}  <br>```  <br>  <br>当然这个其实并不是 effectful visitor 的问题而更像是某种 structural 的 code smell 了，如果一个 visitor 的实现能够把副作用清晰的表达出来，让我能够人肉去建模出 Effect 大概长啥样，我对这样的代码并没有太大的意见。  <br>  <br>顺祝新年快乐！|

|   |   |   |
|---|---|---|
|![zhuisui](https://cdn.v2ex.com/avatar/3773/9b2a/274978_normal.png?m=1573811904)||22<br><br>**[zhuisui](/member/zhuisui)**  <br><br>   31 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>倾向于用一组特别命名的私有方法去处理副作用，甚至单独封装成一个内部类，把状态对象的修改都放到里面，visitor 像调用纯函数一样调用这组方法。|

|   |   |   |
|---|---|---|
|![netabare](https://cdn.v2ex.com/avatar/6bf8/3d7c/125600_normal.png?m=1703247518)||23<br><br>**[netabare](/member/netabare)**  <br><br>OP<br><br>   29 天前 via iPhone<br><br>@[zhuisui](/member/zhuisui) 这个也是我的想法倒是…如果非要使用副作用的话|

