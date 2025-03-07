---
link: https://www.v2ex.com/t/1097140
site: V2EX
date: 2024-12-12T22:27
excerpt: 程序员 - @mawen0726 - 应对业务扩张，将服务拆分并支持横向扩展，现在拆了共 a,b,c
  三个服务出来，然后这三个服务要设计成可以随时横向扩展。其中有如下调用链路* a -> b -> c* a -> c然
twitter: https://twitter.com/@V2EX
slurped: 2025-02-08T09:56
title: 求教，有状态的分布式系统应该如何设计 - V2EX
---

这是一个创建于 57 天前的主题，其中的信息可能已经有所发展或是发生改变。

应对业务扩张，将服务拆分并支持横向扩展，现在拆了共 a,b,c 三个服务出来，然后这三个服务要设计成可以随时横向扩展。其中有如下调用链路

- a -> b -> c
- a -> c

然后 `c` 是主要处理业务的服务，会上分布式锁，加上处理时间长，会后台执行并执行完通知上游来做其他业务操作，业务操作之后才能解锁。

因为一个业务只能在一个 `c` 中执行，所以解锁要找到对应的 c 。比如 `a` 执行业务分配到`节点 1 的 c`，后续交互都要找`节点 1 的 c`。`b`是批量执行业务，这一批都要到同一个`c`中执行完。

目前设计方案是将 `c`的 IP 和业务 id 写到 redis ，然后通过 redis 确定业务在哪个 c 节点上面跑着。然后要在业务处理过程中，查看状态都通过 redis 查对应 ip 再去调用服务。

比如批量任务中，a 要确定哪个 b 节点承接了这个业务，b 节点确定哪个 c 节点正在处理这批次业务。

感觉这种设计不是很好，想请教下还有没有更优雅的做法

可能描述的有点复杂，大概意思是

### 怎么记录在多个节点时，知道这个任务在哪个节点上，并且应用之间相对不耦合

第 1 条附言  ·  44 天前

补充个最终设计的大概原型图 ![foo.png](https://s1.locimg.com/2024/12/25/83b3093fea83d.png)

|   |   |   |
|---|---|---|
|![k9982874](https://cdn.v2ex.com/avatar/5c2f/5bb4/94888_normal.png?m=1737012444)||1<br><br>**[k9982874](https://www.v2ex.com/member/k9982874)**      57 天前 via Android<br><br>为什么要把问题搞这么复杂，为什么不用消息队列|

|   |   |   |
|---|---|---|
|![tairan2006](https://cdn.v2ex.com/gravatar/a8107cfefeeb689b9039dc6658d7427f?s=48&d=retro)||2<br><br>**[tairan2006](https://www.v2ex.com/member/tairan2006)**      57 天前 via Android<br><br>这很简单，你改成 pub/sub ，比如 mqtt 。接到任务的节点会自己订阅相关 topic ，其他的节点不会订阅。你发布任务的时候也无需关心到底目的地在哪。|

|   |   |   |
|---|---|---|
|![JasonGrass](https://cdn.v2ex.com/avatar/afe0/1e2f/647891_normal.png?m=1711551625)||3<br><br>**[JasonGrass](https://www.v2ex.com/member/JasonGrass)**      57 天前<br><br>我的理解：a 执行业务分配到节点 1 的 c ，执行完成之后，C1 就把中间结果保存到数据库或者 Redis ，得到一个 key,  <br>后面 a 要继续处理这个业务，随便找一个 c 的节点，把 key 给 c ，然后继续处理。<br><br>感觉是业务拆得还不够彻底？理想情况是，把业务拆成一步一步执行的，  <br>执行完第一步，丢到消息队列，中间结果（如果有比较大的中间结果）保存到 redis 或者数据库，下一个服务从消息队列中拿到任务，然后继续跑，这样才好真正的横向扩展。|

|   |   |   |
|---|---|---|
|![k9982874](https://cdn.v2ex.com/avatar/5c2f/5bb4/94888_normal.png?m=1737012444)||6<br><br>**[k9982874](https://www.v2ex.com/member/k9982874)**      57 天前 via Android<br><br>不是，你为什么关心认为在哪个节点  <br>a 有任务扔进队列，c 去捡了执行，执行完了再扔个消息，a 受到走完后面流程，就这么简单的事|

|   |   |   |
|---|---|---|
|![mawen0726](https://cdn.v2ex.com/gravatar/304b9be6481d465463f53e97c8043564?s=48&d=retro)||7<br><br>**[mawen0726](https://www.v2ex.com/member/mawen0726)**      57 天前<br><br>@[k9982874](https://www.v2ex.com/member/k9982874)  <br>因为 c 在执行任务的时候，上了锁，锁定了某个资源，因为处理时间长，锁定时间久  <br>代码在写的时候，不是常规的写法....  <br>lock.lock  <br>try{  <br>dosomething()  <br>}  <br>finally{  <br>lock.unlock  <br>}<br><br>而是起了个线程来上锁，等 a 确定完业务执行完，再去通知持锁的 c 解锁。因为用的 redisson 的 lock ，所以要找回对应的节点 c 才能解锁...|

|   |   |   |
|---|---|---|
|![1402851639](https://cdn.v2ex.com/gravatar/a29b97b4b28b95bff4258df36ccff409?s=48&d=retro)||10<br><br>**[1402851639](https://www.v2ex.com/member/1402851639)**      57 天前 via Android<br><br>感觉你这个耦合这么重是不是拆的就有问题呢。。|

|   |   |   |
|---|---|---|
|![1402851639](https://cdn.v2ex.com/gravatar/a29b97b4b28b95bff4258df36ccff409?s=48&d=retro)||11<br><br>**[1402851639](https://www.v2ex.com/member/1402851639)**      57 天前 via Android   ![❤️](https://www.v2ex.com/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>我觉得你更应该解释一下是什么条件限制了必须在同一个实例上，去考虑能否在请求中将关键信息传递过去，又或者 redis 暂时存一下，而不是 b 服务去循环将请求打到同一个 c 上面？|

|   |   |   |
|---|---|---|
|![cowcomic](https://cdn.v2ex.com/avatar/4939/ffd8/73524_normal.png?m=1727658639)||14<br><br>**[cowcomic](https://www.v2ex.com/member/cowcomic)**      57 天前<br><br>1 ，当时为什么要拆，从描述看 abc 的耦合很严重，而且是双向依赖，这不拆更合理  <br>2 ，如果一定要拆，那我理解可以把 C 看成一些工作节点，把 C 向上依赖的部分再拆出来变成 C 的下游，首先保证链条是单向的，AB 变成纯上游，C 变成总业务入口，这样看能不能消除 C 的状态变成无状态的  <br>3 ，如果消除不了，那就 C 前面架消息队列，由 C 决定要哪些请求，如果并发不是很大的话，就直接表记录，如果并发很大，那这个整体的系统功能就很有问题，重新梳理吧|

|   |   |   |
|---|---|---|
|![czsas](https://cdn.v2ex.com/gravatar/833f5b5319ea44a54f880c03b020b43b?s=48&d=retro)||15<br><br>**[czsas](https://www.v2ex.com/member/czsas)**      57 天前<br><br>可以借鉴一下 temporal/Cadence 这种 workflow 框架|

|   |   |   |
|---|---|---|
|![nuk](https://cdn.v2ex.com/avatar/2745/97e1/285805_normal.png?m=1713722833)||16<br><br>**[nuk](https://www.v2ex.com/member/nuk)**      57 天前<br><br>给每个任务加一个路径栈|

|   |   |   |
|---|---|---|
|![Plutooo](https://cdn.v2ex.com/gravatar/266c45ffd42b4b256a34461299dc017e?s=48&d=retro)||19<br><br>**[Plutooo](https://www.v2ex.com/member/Plutooo)**      57 天前<br><br>@[mawen0726](https://www.v2ex.com/member/mawen0726) #7 redisson 的 lock 不是基于线程的吗，当你的 a 通知 c 可以解锁以后相当于一个新的请求，新的请求怎么去解锁之前那个线程的锁|

|   |   |   |
|---|---|---|
|![RightHand](https://cdn.v2ex.com/gravatar/7378fe3ab0f9395a7fb6774621b0b609?s=48&d=retro)||20<br><br>**[RightHand](https://www.v2ex.com/member/RightHand)**      56 天前 via Android<br><br>有状态的，去做复杂均衡啊。干嘛非要上无状态的微服务|

|   |   |   |
|---|---|---|
|![THESDZ](https://cdn.v2ex.com/gravatar/4477bb3cd951bd10dc081c72dd608de3?s=48&d=retro)||21<br><br>**[THESDZ](https://www.v2ex.com/member/THESDZ)**      56 天前<br><br>1.状态带着走；  <br>2.更进一步，状态单独存，状态唯一 id 带着走。|

|   |   |   |
|---|---|---|
|![cheng6563](https://cdn.v2ex.com/avatar/382f/1f51/414567_normal.png?m=1691026308)||25<br><br>**[cheng6563](https://www.v2ex.com/member/cheng6563)**      56 天前<br><br>“会后台执行并执行完通知上游来做其他业务操作，业务操作之后才能解锁。”<br><br>所以你的实际调用链应该是 a->b->c->b->a|

|   |   |   |
|---|---|---|
|![pangzipp](https://cdn.v2ex.com/avatar/1025/7392/108352_normal.png?m=1734326509)||27<br><br>**[pangzipp](https://www.v2ex.com/member/pangzipp)**      56 天前<br><br>上一个分布式调度框架例如  <br>例如 airflow  <br>阿里云的 SchedulerX|

|   |   |   |
|---|---|---|
|![sujin190](https://cdn.v2ex.com/avatar/e66f/964a/36127_normal.png?m=1732868751)||28<br><br>**[sujin190](https://www.v2ex.com/member/sujin190)**      56 天前<br><br>@[Plutooo](https://www.v2ex.com/member/Plutooo) #19 分布式锁底层都是加锁方生成一个只有自己指定的 ID 来防止他人异常解锁，那换句话说你加锁后主动把这个 ID 告诉别人，或者提前生成一个 ID 要求加锁方使用这个 ID ，，那别人就能解锁了啊，和线程啥的无关<br><br>而且从实现来看，如果执行时间很长，那这个执行中的状态应该保存在数据库中，不应该单纯加锁，加锁范围只到查询修改这个数据库中状态的过程，否则直接在入口加锁同步调用就好了啊，没必要异步吧<br><br>有状态逻辑可比把这个状态写入数据库需要的地方读取判断复杂多了，存入数据库需要的地方读取判断，那整个系统还是无状态的，简单多了，想要性能好一点那存入 redis 也不是不行啊，干嘛非要纠结使用加锁的方式|

|   |   |   |
|---|---|---|
|![ychost](https://cdn.v2ex.com/avatar/2f62/955a/456296_normal.png?m=1587696818)||29<br><br>**[ychost](https://www.v2ex.com/member/ychost)**      56 天前<br><br>每个任务 ID 创建一个 topic ，后续只需要往这个 Topic 推数据就行了，处理的那台机器拿到任务之后去监听它，后续都是此机器来处理任务|

|   |   |   |
|---|---|---|
|![Plutooo](https://cdn.v2ex.com/gravatar/266c45ffd42b4b256a34461299dc017e?s=48&d=retro)||31<br><br>**[Plutooo](https://www.v2ex.com/member/Plutooo)**      56 天前<br><br>@[sujin190](https://www.v2ex.com/member/sujin190) #28 对啊拥有线程 id 是可以解锁，那还跟请求到哪个 c 的节点有什么关系呢，既然 a 需要再次请求解锁，那么这个重新发送的请求必然跟先前的请求大概率不同线程，那些跟请求到了其他 c 节点有什么不同吗|

|   |   |   |
|---|---|---|
|![aarontian](https://cdn.v2ex.com/gravatar/8ed3e93701b2cc69253e5be59d9edd18?s=48&d=retro)||33<br><br>**[aarontian](https://www.v2ex.com/member/aarontian)**      55 天前<br><br>我不认为有必要查询到具体是在哪个实例上执行。把服务实现为有状态的，并假定它在释放资源前不会挂是个很糟糕的设计，你记录了 c1 的 IP ，c1 挂了呢？你是不是又要有更多复杂的“业务逻辑”去处理实例状态变更导致的问题。<br><br>你这里 c 锁定资源的正确姿势或许是把锁定的凭证存放到某个分布式存储（比如 redis ）中，等解锁时任意一个本服务的实例都应该能拿到凭证去解锁。（但我甚至怀疑这个设计有根本性的问题，或许不需要加这种资源锁，或者可能可以有一个统一的调度器负责一个流程的资源上锁与解锁）|

|   |   |   |
|---|---|---|
|![mawen0726](https://cdn.v2ex.com/gravatar/304b9be6481d465463f53e97c8043564?s=48&d=retro)||34<br><br>**[mawen0726](https://www.v2ex.com/member/mawen0726)**      45 天前<br><br>@[1402851639](https://www.v2ex.com/member/1402851639)  <br>这几天忙忘记回了，后面重新拆了下。  <br>将所有要执行的东西都提交到消息队列中，让下游去抢。如果执行的要中断，上游也是发消息队列，下游监听自己有没有在处理这个业务，没有就忽略。  <br>将所有相关场景都改成这样了，不知道这样的设计好不好...|

|   |   |   |
|---|---|---|
|![mawen0726](https://cdn.v2ex.com/gravatar/304b9be6481d465463f53e97c8043564?s=48&d=retro)||35<br><br>**[mawen0726](https://www.v2ex.com/member/mawen0726)**      45 天前<br><br>@[cowcomic](https://www.v2ex.com/member/cowcomic)  <br>这里的最底层的资源其实是 jupyter ，用来运行一些大型算法得出结果。然后印个 jupyter 同时只能跑一个算法，所以需要资源锁定。c 服务就是干这个事的。然后 a 和 b 其实就是一个算法只跑单次和按时间纬度跑多次的区别，因为跑多次且结果有上下关联，所需内存大，所以也抽两个了（原本放一块）<br><br>然后之前 c 跟业务耦合了，最初拆的就来回解锁了。后面把 c 拆得只跟 jupyter 交互，是个无状态的。a 、b 服务发算法任务让 c 自己去抢，中断执行 ab 也是发消息队列，c 监听到检查自己有没有正在运行对应的业务（算法 id 唯一），没有则忽略。<br><br>我之前纠结要维护 ip 是因为觉得中断，暂停等操作要通知对应的 c 服务。但是后面捋了下，一个业务只会在一个 c 里面执行，要做什么操作直接广播所有 c （通过消息队列），c 来判断有没有在运行这个就可以了。<br><br>然后上锁放在上游（ a 、b 服务）里面，在让 c 运行前上锁，c 运行完通知后解锁。|

|   |   |   |
|---|---|---|
|![mawen0726](https://cdn.v2ex.com/gravatar/304b9be6481d465463f53e97c8043564?s=48&d=retro)||36<br><br>**[mawen0726](https://www.v2ex.com/member/mawen0726)**      45 天前<br><br>@[czsas](https://www.v2ex.com/member/czsas)  <br>@[server](https://www.v2ex.com/member/server)  <br>感谢感谢，现在回头看看这些框架。  <br>之前纠结要维护 ip 是因为觉得中断，暂停等操作要通知对应的 c 服务。但是后面捋了下，一个业务只会在一个 c 里面执行，要做什么操作直接广播所有 c （通过消息队列），c 来判断有没有在运行这个就可以了。没有运行则不做任何操作|

|   |   |   |
|---|---|---|
|![mawen0726](https://cdn.v2ex.com/gravatar/304b9be6481d465463f53e97c8043564?s=48&d=retro)||37<br><br>**[mawen0726](https://www.v2ex.com/member/mawen0726)**      44 天前<br><br>@[mark2025](https://www.v2ex.com/member/mark2025)  <br>因为业务场景锁有业务在生命周期内固定使用某个资源的场景，感觉自己写一套去维护资源的状态，还不如用分布式锁来的直接...|

|   |   |   |
|---|---|---|
|![mawen0726](https://cdn.v2ex.com/gravatar/304b9be6481d465463f53e97c8043564?s=48&d=retro)||38<br><br>**[mawen0726](https://www.v2ex.com/member/mawen0726)**      44 天前<br><br>@[mark2025](https://www.v2ex.com/member/mark2025)  <br>当时没设计好，后面重新捋了下，将上锁和解锁都放在同一端了  <br>当时不想大动代码（屎山），就想着 c 上锁，a 、c 解锁|

|   |   |   |
|---|---|---|
|![mawen0726](https://cdn.v2ex.com/gravatar/304b9be6481d465463f53e97c8043564?s=48&d=retro)||39<br><br>**[mawen0726](https://www.v2ex.com/member/mawen0726)**      44 天前<br><br>@[huzhizhao](https://www.v2ex.com/member/huzhizhao)  <br>现在的设计是消息队列中：  <br>主题 1 关于任务发布（ a 、c 发布的任务，类型字段区分开）  <br>主题 2 关于任务接收成功的响应，让 a 、c 知道任务在执行了  <br>主题 3 关于执行中的数据  <br>主题 4 关于任务的中断、取消<br><br>所有的 c 实例对于主题都属于同一个消费组，共同监听主题 1 抢任务执行，发布到主题 2 响应上游正在执行，同时将结果发布到主题 3 。主题 4 则是不同消费组，收到取消的消息判断自身有没有在执行对应业务，没有则忽略<br><br>所有的 a 、b 实例都是一个单独的消费组，监听主题 2 确定任务发布成功（没响应则重试 5 次），监听主题 3 获取结果（结果实体包含消费组信息，消费组不一致忽略消息）<br><br>感觉这样设计强依赖了消息队列，但是可以不管下游的 ip 了，也不知道好不好，但是也没机会再改了 - -|

|   |   |   |
|---|---|---|
|![mawen0726](https://cdn.v2ex.com/gravatar/304b9be6481d465463f53e97c8043564?s=48&d=retro)||41<br><br>**[mawen0726](https://www.v2ex.com/member/mawen0726)**      44 天前<br><br>@[Plutooo](https://www.v2ex.com/member/Plutooo)  <br>其实正是这个线程的问题，才让我发帖问的，原本我以为 redisson 只是简单的 key 相同解锁...  <br>后面稍微深入了一下，其实就是分了两个类型  <br>1. 线程 id 必须一样  <br>2. lockasync ，指定一个 id ，使用相同 id 上锁解锁即可（可以联想场景 reactor java ，每个场景都可能是不同的线程执行的）<br><br>但是抛开这个不谈，原本要维护下游 ip 还是很垃圾的设计...|

|   |   |   |
|---|---|---|
|![mawen0726](https://cdn.v2ex.com/gravatar/304b9be6481d465463f53e97c8043564?s=48&d=retro)||42<br><br>**[mawen0726](https://www.v2ex.com/member/mawen0726)**      44 天前<br><br>@[aarontian](https://www.v2ex.com/member/aarontian)  <br>当时认为 c 去锁定资源，就认为 c 去上锁了，其实还说漏了一些，c 和资源会建立 ws 连接，所以当时就更认为要在 c 上锁...  <br>希望可以看看我新的回复，看看这种设计怎么样，算是第一次做种比较复杂的设计|

|   |   |   |
|---|---|---|
|![mark2025](https://cdn.v2ex.com/gravatar/0d54045890432a48c1bd1f605224190d?s=48&d=retro)||45<br><br>**[mark2025](https://www.v2ex.com/member/mark2025)**      43 天前<br><br>@[mawen0726](https://www.v2ex.com/member/mawen0726) 你这个场景使用任务队列来做应该还算简单了：  <br>1. 发布任务消息到消息队列（带执行）  <br>2. 收到任务消息，上锁，发布任务状态消息（已上锁）  <br>3. 收到已上锁的行任务消息，开始执行任务。根据任务执行结果（成功、失败），发布任务状态消息（执行状态，可以包含任务结果数据）  <br>4. 收到包含执行状态的任务消息，解锁<br><br>抽象为 4 个步骤，使用任务状态值在消息队列中来流转，可以忽略 a 、b 、c 具体服务。|

|   |   |   |
|---|---|---|
|![mark2025](https://cdn.v2ex.com/gravatar/0d54045890432a48c1bd1f605224190d?s=48&d=retro)||46<br><br>**[mark2025](https://www.v2ex.com/member/mark2025)**      43 天前<br><br>a -> b -> c  <br>a -> c  <br>两种调用链路可以设计为两个队列 topic ，以上面 4 步为基础对 步骤 3 进行扩展就行了|