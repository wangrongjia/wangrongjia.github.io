---
link: https://www.v2ex.com/t/1101162
site: V2EX
date: 2024-12-30T09:52
excerpt: 程序员 - @Ashe007 - 手上仅用一台 2 核 8g 的 Centos 服务器。个人是练习 Java 两年半的 bug creator
  。最近刚练习完 Gitlab 的 CI/CD ，想搞一搞 kubernetes
twitter: https://twitter.com/@V2EX
slurped: 2025-02-08T09:18
title: 学习研究搭建 Kubernetes 的问题 - V2EX
---
  
  [Ashe007](/member/Ashe007) · 39 天前 · 3689 次点击

这是一个创建于 39 天前的主题，其中的信息可能已经有所发展或是发生改变。

手上仅用一台 2 核 8g 的 Centos 服务器。 个人是练习 Java 两年半的 bug creator 。

最近刚练习完 Gitlab 的 CI/CD ，想搞一搞 kubernetes ，然而感觉官网的 get started 页面有些过于简陋（只有命令没有对行为的相关入门级别解释），其他页面则是过于繁琐冗杂。

问了下智谱清言，也是给出了一堆 command ，有没有好心的大佬给小白我讲一讲 kubernetes 的整体架构，运作流程（有相关博客更佳），以及为什么它需要 docker 容器，而后最新版本又不需要 docker 容器呢？


57 条回复

|   |   |   |
|---|---|---|
|![log4j](https://cdn.v2ex.com/gravatar/7dc574de6d1e76fd02dc9e77088579a6?s=48&d=retro)||1<br><br>**[log4j](/member/log4j)**  <br><br>   39 天前<br><br>参考官网文档吧，比任何人讲的都要权威准确|

|   |   |   |
|---|---|---|
|![defunct9](https://cdn.v2ex.com/avatar/5cf8/faa5/97884_normal.png?m=1631865166)||2<br><br>**[defunct9](/member/defunct9)**  <br><br>   39 天前<br><br>这个问题太复杂了，估计你还得用两年半搞清楚。|

|   |   |   |
|---|---|---|
|![Ashe007](https://cdn.v2ex.com/avatar/cdb3/c329/683571_normal.png?m=1717585814)||3<br><br>**[Ashe007](/member/Ashe007)**  <br><br>OP<br><br>   39 天前<br><br>@[log4j](/member/log4j) 额，主要是想走走捷径，想有人帮我捋一捋架构思路再研究&#129315;|

|   |   |   |
|---|---|---|
|![Ashe007](https://cdn.v2ex.com/avatar/cdb3/c329/683571_normal.png?m=1717585814)||4<br><br>**[Ashe007](/member/Ashe007)**  <br><br>OP<br><br>   39 天前<br><br>@[defunct9](/member/defunct9) 我看完官方文档也用不了两年半吧……|

|   |   |   |
|---|---|---|
|![Ayanokouji](https://cdn.v2ex.com/gravatar/a3330a6a823a9945c860c7aa2cb1c29f?s=48&d=retro)||5<br><br>**[Ayanokouji](/member/Ayanokouji)**  <br><br>   39 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>[/go/k8s](/go/k8s) 到这个节点看看，有发教程的|

|   |   |   |
|---|---|---|
|![Flourite](https://cdn.v2ex.com/gravatar/49d74281539e6709e74554961e173b64?s=48&d=retro)||6<br><br>**[Flourite](/member/Flourite)**  <br><br>   39 天前 via iPhone   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>本质上是高级版的 docker ，管理计算机 CPU 、内存、磁盘等资源。到时候还的加各种入 gateway 、分布式文件系统、告警链路等一堆东西|

|   |   |   |
|---|---|---|
|![Ashe007](https://cdn.v2ex.com/avatar/cdb3/c329/683571_normal.png?m=1717585814)||7<br><br>**[Ashe007](/member/Ashe007)**  <br><br>OP<br><br>   39 天前<br><br>@[Flourite](/member/Flourite) 真大佬，有没有博客？|

|   |   |   |
|---|---|---|
|![kursk](https://cdn.v2ex.com/gravatar/60b283fe6f2a85b3e620d1d0ed3045b8?s=48&d=retro)||8<br><br>**[kursk](/member/kursk)**  <br><br>   39 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 2<br><br>kubernetes 的整体架构，运作流程  <br>  <br>我的理解，K8S 整体是一个分布式的高可用架构，运行这个架构之上的应用不需要应用本身具有高可用的特点(降低应用开发者的门槛)，而可以借助架构的能力让应用高可用。详细的理解建议看周志明的《凤凰架构》 [https://icyfenix.cn/](https://icyfenix.cn/) 建议看电子版，因为链接也是需要看的，不要急，书的知识量很大，我花了 9 个月才读完，很多内容都需要实践。当然读后为了感谢作者买了纸质版。  <br>  <br>为什么它需要 docker 容器，而后最新版本又不需要 docker 容器呢  <br>  <br>当多个应用程序在操作系统上运行时，操作系统有两个基本问题要解决，共享和隔离，共享是为了降低成本、解决应用之间的通信等问题，隔离是安全、避免干扰和解决雪花崩溃问题，容器这种技术很好地解决了这两个问题，docker 生逢其实，刚好撞上了微服务的大风口，但是输掉了与 google 的容器编排战争，输给了 K8S 容器编排技术，然后 Google 所在 CNCF 又搞了一系列标准，包括容器运行时接口 CNI 标准，而 docker 嘴硬不遵从该标准，所以有 cri-o\containerd runc 其它遵循 CRI 的容器运行时技术更普遍受欢迎。其实 docker 配合 cri-docker 也可以用 [https://github.com/Mirantis/cri-dockerd](https://github.com/Mirantis/cri-dockerd)|

|   |   |   |
|---|---|---|
|![kursk](https://cdn.v2ex.com/gravatar/60b283fe6f2a85b3e620d1d0ed3045b8?s=48&d=retro)||9<br><br>**[kursk](/member/kursk)**  <br><br>   39 天前<br><br>包括容器运行时接口 CNI 标准 此处应该是 CRI 标准|

|   |   |   |
|---|---|---|
|![Ashe007](https://cdn.v2ex.com/avatar/cdb3/c329/683571_normal.png?m=1717585814)||10<br><br>**[Ashe007](/member/Ashe007)**  <br><br>OP<br><br>   39 天前<br><br>@[kursk](/member/kursk) 瑞思拜，致敬开源精神|

|   |   |   |
|---|---|---|
|![SuperDaFu](https://cdn.v2ex.com/avatar/fcf2/b7ed/296521_normal.png?m=1715079206)||11<br><br>**[SuperDaFu](/member/SuperDaFu)**  <br><br>   39 天前<br><br>[https://kuboard.cn/](https://kuboard.cn/) 看这个，我感觉适合新手。  <br>Kuboard 把集群搭起来，然后配合文档组件的定义。  <br>自己搭 k8s,主要网络问题太麻烦了，镜像都拉不下来。|

|   |   |   |
|---|---|---|
|![datehoer](https://cdn.v2ex.com/gravatar/06b5cb9dd95bb0f00a42e56faa73cfd2?s=48&d=retro)||12<br><br>**[datehoer](/member/datehoer)**  <br><br>   39 天前<br><br>现在搭建 k8s 啥的，直接用 Kubekey 就完了，然后加个 kubesphere 。  <br>离线在线都能装，麒麟也可以。  <br>参考：  <br>[https://kubesphere.io/zh/docs/v4.1/03-installation-and-upgrade/02-install-kubesphere/02-install-kubernetes-and-kubesphere/](https://kubesphere.io/zh/docs/v4.1/03-installation-and-upgrade/02-install-kubesphere/02-install-kubernetes-and-kubesphere/)  <br>[https://www.datehoer.com/blogs/other/kylinv10installk8s.html](https://www.datehoer.com/blogs/other/kylinv10installk8s.html)|

|   |   |   |
|---|---|---|
|![zjno996](https://cdn.v2ex.com/avatar/d386/96d8/651320_normal.png?m=1697956766)||13<br><br>**[zjno996](/member/zjno996)**  <br><br>   39 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>可以参考下 Kubernetes in Action 这本书，简要讲了 k8s 的架构和实践|

|   |   |   |
|---|---|---|
|![Ashe007](https://cdn.v2ex.com/avatar/cdb3/c329/683571_normal.png?m=1717585814)||14<br><br>**[Ashe007](/member/Ashe007)**  <br><br>OP<br><br>   39 天前<br><br>@[SuperDaFu](/member/SuperDaFu) 确实，网络问题是个麻烦|

|   |   |   |
|---|---|---|
|![Ashe007](https://cdn.v2ex.com/avatar/cdb3/c329/683571_normal.png?m=1717585814)||15<br><br>**[Ashe007](/member/Ashe007)**  <br><br>OP<br><br>   39 天前<br><br>@[datehoer](/member/datehoer) 你确定不是在发广告……|

|   |   |   |
|---|---|---|
|![datehoer](https://cdn.v2ex.com/gravatar/06b5cb9dd95bb0f00a42e56faa73cfd2?s=48&d=retro)||16<br><br>**[datehoer](/member/datehoer)**  <br><br>   39 天前<br><br>@[Ashe007](/member/Ashe007) kubekey 还是广告？|

|   |   |   |
|---|---|---|
|![dolphintwo](https://cdn.v2ex.com/avatar/b601/6c31/267745_normal.png?m=1711435971)||17<br><br>**[dolphintwo](/member/dolphintwo)**  <br><br>   39 天前<br><br>看官方文档，非常详细，而且实时更新  <br>你要找的博客文章约等于 “200 字概述西游记讲了啥”，看完约等于没看|

|   |   |   |
|---|---|---|
|![miscnote](https://cdn.v2ex.com/gravatar/fa3a0431ee232cdeeccd0608eb5aed21?s=48&d=retro)||18<br><br>**[miscnote](/member/miscnote)**  <br><br>   39 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>试试 minikube 。照着我这个文档操作一遍，基本你就理解了 k8s 概念。  <br>  <br>[https://unix2go.com/deploy-k8s-from-scratch/](https://unix2go.com/deploy-k8s-from-scratch/)|

|   |   |   |
|---|---|---|
|![Ashe007](https://cdn.v2ex.com/avatar/cdb3/c329/683571_normal.png?m=1717585814)||19<br><br>**[Ashe007](/member/Ashe007)**  <br><br>OP<br><br>   39 天前<br><br>@[dolphintwo](/member/dolphintwo) 是的，不过评论区还是有一些有价值的回答|

|   |   |   |
|---|---|---|
|![Flourite](https://cdn.v2ex.com/gravatar/49d74281539e6709e74554961e173b64?s=48&d=retro)||20<br><br>**[Flourite](/member/Flourite)**  <br><br>   39 天前 via iPhone<br><br>非运维，没有深入研究 k8s 架构，官网文档不喜欢，啰嗦找不到重点，有兴趣可以看下笔记  <br>[https://y2k38.github.io/use-kubeadm-to-deploy-k8s-cluster/](https://y2k38.github.io/use-kubeadm-to-deploy-k8s-cluster/)|

|   |   |   |
|---|---|---|
|![Maca](https://cdn.v2ex.com/avatar/a9a1/0b4c/685961_normal.png?m=1715388045)||21<br><br>**[Maca](/member/Maca)**  <br><br>   39 天前<br><br>官方的 quick start 没记错是分 master/worker 部署的吧。  <br>只有一台机器的话，可以参考 18 楼用 minikube 或者 k3s 。  <br>（其实 docker desktop 也内置了 k8s 的可选功能）|

|   |   |   |
|---|---|---|
|![Ackvincent](https://cdn.v2ex.com/gravatar/bb9d416880e29c4102646717fa5671c9?s=48&d=retro)||22<br><br>**[Ackvincent](/member/Ackvincent)**  <br><br>   39 天前<br><br>简单入门可以看看这个 [https://www.kuboard.cn/learning/](https://www.kuboard.cn/learning/)|

|   |   |   |
|---|---|---|
|![Maca](https://cdn.v2ex.com/avatar/a9a1/0b4c/685961_normal.png?m=1715388045)||23<br><br>**[Maca](/member/Maca)**  <br><br>   39 天前<br><br>然后关于 k8s 的架构，8 楼推荐的 凤凰架构 那本书（网站）确实讲得挺不错的，值得慢慢啃。  <br>  <br>至于问了 AI 得到一堆 command （应该还有一堆 yaml ）是这样的 ಥ_ಥ 玩这玩意就是一堆配置和命令，反而图形化的管理页面用了几个都觉得不好用，很别扭。  <br>还有 docker 容器的问题，不是不需要 docker ，而是有更多的 CNI 可以选择。在没有完善这块之前，kubernetes 通过内置了 shim 去兼容 docker ，之后”时机成熟“就把这个兼容层移除了（当然还是可以通过手动安装 shim 来兼容 docker ）。  <br>不过 8 楼说 docker 嘴硬这点，跟我的认知不太一样，很多 CNCF 的规范和工具，包括 containerd ，都是出自 docker 之手。|

|   |   |   |
|---|---|---|
|![clf](https://cdn.v2ex.com/avatar/75a1/81e9/349567_normal.png?m=1653470554)||24<br><br>**[clf](/member/clf)**  <br><br>   39 天前<br><br>先理解每个东西是干嘛的，然后就大概知道了。比如 Service 、Pod 、pvc 之类的……|

|   |   |   |
|---|---|---|
|![gimp](https://cdn.v2ex.com/avatar/d03f/fbc5/136804_normal.png?m=1444699066)||25<br><br>**[gimp](/member/gimp)**  <br><br>   39 天前<br><br>我之前整理了篇博客，可能对你了解容器方面的知识有些许帮助  <br>  <br><了解容器运行时的演进与标准化之路> [https://blog.yasking.org/a/container-containerd-cri-o-runc.html](https://blog.yasking.org/a/container-containerd-cri-o-runc.html)|

|   |   |   |
|---|---|---|
|![n43635](https://cdn.v2ex.com/gravatar/b68ecd97d6f7db455e28ab3d53c75cd3?s=48&d=retro)||26<br><br>**[n43635](/member/n43635)**  <br><br>   39 天前<br><br>快速上手的话可以用 sealos 快速搭建起 K8S 集群，然后再启动一个 dashboard 比如 kuboard ，这样有图形界面可以更好容易理解 k8s 的整体架构，kuboard 的文档做的也很好，很多可以一步一步跟着做，最后拓展深入理解可以参考 k8s 的官方文档，官方文档比较全面|

|   |   |   |
|---|---|---|
|![lasuar](https://cdn.v2ex.com/avatar/0a94/3887/328850_normal.png?m=1709527453)||27<br><br>**[lasuar](/member/lasuar)**  <br><br>   39 天前<br><br>[https://github.com/chaseSpace/k8s-tutorial-cn/blob/main/doc_tutorial.md#11-架构设计](https://github.com/chaseSpace/k8s-tutorial-cn/blob/main/doc_tutorial.md#11-架构设计)|

|   |   |   |
|---|---|---|
|![kursk](https://cdn.v2ex.com/gravatar/60b283fe6f2a85b3e620d1d0ed3045b8?s=48&d=retro)||28<br><br>**[kursk](/member/kursk)**  <br><br>   39 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 2<br><br>关于学习 K8S ，我还是认为通过官方文档学习比较靠谱，因为这个东西还在发展，附着在它身上的其它工具可能活不了那么久，或者慢慢就不兼容了，所以泼一下楼上很多人的凉水，知识应该从源头学习，不要学习被别人转换或理解过的笔记或者 blog ，因为有些内容可能被扭曲或丢失  <br>  <br>搭建环境也是，还是推荐用 kubeadm ，其它工具会更方便，但是只有 hard 模式才能让你理解更多，计算机就是实践性科学，你初学时不栽跟头，以后栽跟头成本更高  <br>  <br>至于 K3S 我不了解，但线下与人讨论时别人说这个 bug 很多，我自己在搭建 K8S 集群发现也存在很多文档上没有写，自己实践做时才出现的问题，所以虽然我搭建 K8S 的环境是 ARM 的，但我也没有研究 K3S  <br>  <br>我是自己在类似树莓派的国产开发板上搭建 K8S 集群，可以看看我这个帖子  <br>  <br>草根云，每个云原生工程师都值得拥有 [https://www.v2ex.com/t/1003629](https://www.v2ex.com/t/1003629)  <br>  <br>不过 orangepi 3B 在运行 2 年后，10 个板子有 9 个的有线网口都坏了，所以这个质量不怎么样，我现在用了其它开发板，运行时也从 docker 换成了 runc ，操作系统还要自己编译，等我用一段时间后再写篇实践过程文档|

|   |   |   |
|---|---|---|
|![Suaxi](https://cdn.v2ex.com/avatar/d626/2d2a/447356_normal.png?m=1725241916)||29<br><br>**[Suaxi](/member/Suaxi)**  <br><br>   39 天前 via Android<br><br>v 站之前有位大佬做一小时精讲专题的，K8s 这一块他用的是官网文档 demo 里的 MiniKube ，推荐先看看这个了解个大概，再整体深入学习|

|   |   |   |
|---|---|---|
|![kursk](https://cdn.v2ex.com/gravatar/60b283fe6f2a85b3e620d1d0ed3045b8?s=48&d=retro)||30<br><br>**[kursk](/member/kursk)**  <br><br>   39 天前<br><br>还有楼上说的网络问题的确很重要，但是如果你要是没有能力在路由器上实现透明代理，那就也不用研究 K8S 了，因为 service 这种资源的本质就是一堆 rule ，你搞不定透明代理和科学上网，就肯定懂不了 K8S 的 servce 是咋回事|

|   |   |   |
|---|---|---|
|![Ashe007](https://cdn.v2ex.com/avatar/cdb3/c329/683571_normal.png?m=1717585814)||31<br><br>**[Ashe007](/member/Ashe007)**  <br><br>OP<br><br>   39 天前<br><br>@[kursk](/member/kursk) 不能通过一些镜像网站规避网络问题吗？意思是先必须在服务器上实现科学上网，才能进而着手 k8s 吗|

|   |   |   |
|---|---|---|
|![gdw1986](https://cdn.v2ex.com/avatar/0d34/713e/304279_normal.png?m=1723516886)||32<br><br>**[gdw1986](/member/gdw1986)**  <br><br>   39 天前 via Android<br><br>研究下 CKA 认证吧，分分钟给你催熟|

|   |   |   |
|---|---|---|
|![isno](https://cdn.v2ex.com/avatar/466a/ccba/2368_normal.png?m=1710135553)||33<br><br>**[isno](/member/isno)**  <br><br>   39 天前<br><br>[https://www.thebyte.com.cn/container/summary.html](https://www.thebyte.com.cn/container/summary.html)|

|   |   |   |
|---|---|---|
|![c8c](https://cdn.v2ex.com/gravatar/efb64837a4b39bd599254921df3f11be?s=48&d=retro)||34<br><br>**[c8c](/member/c8c)**  <br><br>   39 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>官网网站就可以了  <br>先看 [https://kubernetes.io/zh-cn/docs/tasks/tools/](https://kubernetes.io/zh-cn/docs/tasks/tools/) 这个安装环境  <br>然后看 [https://kubernetes.io/zh-cn/docs/tutorials/hello-minikube/](https://kubernetes.io/zh-cn/docs/tutorials/hello-minikube/) 这个搭建 minikube  <br>之后 看 [https://kubernetes.io/zh-cn/docs/tutorials/kubernetes-basics/](https://kubernetes.io/zh-cn/docs/tutorials/kubernetes-basics/) 这个把基础跟着做一遍  <br>  <br>基础的概念就都有了。|

|   |   |   |
|---|---|---|
|![datasheet](https://cdn.v2ex.com/gravatar/3a0ecc41e87ecae762f00d00a7aa7fc1?s=48&d=retro)||35<br><br>**[datasheet](/member/datasheet)**  <br><br>   39 天前<br><br>[https://kubernetes.io/zh-cn/docs/setup/production-environment/tools/kubeadm/install-kubeadm/](https://kubernetes.io/zh-cn/docs/setup/production-environment/tools/kubeadm/install-kubeadm/) 按照步骤走完就可以搞一个单机版的，你这个服务器配置也只能搞一个节点，不要考虑集群了|

|   |   |   |
|---|---|---|
|![darkgeek](https://cdn.v2ex.com/avatar/b36a/ecc9/99164_normal.png?m=1665032945)||36<br><br>**[darkgeek](/member/darkgeek)**  <br><br>   39 天前 via Android<br><br>@[kursk](/member/kursk) 问个题外话，你的香橙派坏得这么厉害，是超负荷运转导致的，还是它本身质量问题？😂|

|   |   |   |
|---|---|---|
|![kursk](https://cdn.v2ex.com/gravatar/60b283fe6f2a85b3e620d1d0ed3045b8?s=48&d=retro)||37<br><br>**[kursk](/member/kursk)**  <br><br>   39 天前<br><br>@[Ashe007](/member/Ashe007) 因为我早已掌握透明代理技术，我就没有找 K8S 镜像仓库等一系列所需仓库的镜像，我想大致找不完整  <br>  <br>透明代理不是在服务器上实现科学上网，而必须在服务器所连接的路由器上实现。了解一下 openwrt [https://openwrt.org/](https://openwrt.org/) ，都是基于这个操作系统  <br>  <br>二者的区别在于，一般的科学上网需要安装客户端，这个客户端会开通一个端口，每个程序都需要通过这个代理端口才能访问，但是这种做法局限太大，一是本地 Dns 查询需要另想办法，二是每个服务器的每个应用程序都需要配置，配置起来太麻烦，如果还考虑容器运行的需求则实际不可能采用这种办法  <br>  <br>所以只能在网络层解决问题，让每台服务器连接到路由器后，统一在路由器上做路由控制，这个就要借助 iptables 或者 nftables 的功能了，这也是 K8S 中 service 这种资源干的事情，所以你迟早要懂  <br>  <br>相关知识不敢多说，你 google 一下 透明代理 openwrt dnsmasq iptables 等关键词|

|   |   |   |
|---|---|---|
|![kursk](https://cdn.v2ex.com/gravatar/60b283fe6f2a85b3e620d1d0ed3045b8?s=48&d=retro)||38<br><br>**[kursk](/member/kursk)**  <br><br>   39 天前<br><br>@[darkgeek](/member/darkgeek) 我 CPU 和内存的负载都不大，而且 10 个有 9 个都是坏的有线网口，一定是质量问题|

|   |   |   |
|---|---|---|
|![nicholasxuu](https://cdn.v2ex.com/gravatar/6ee59a624f2fc0cccf481375bcf3e53c?s=48&d=retro)||39<br><br>**[nicholasxuu](/member/nicholasxuu)**  <br><br>   39 天前<br><br>极客时间买节课，好好上完应该还行。|

|   |   |   |
|---|---|---|
|![halov](https://cdn.v2ex.com/avatar/c192/717c/548686_normal.png?m=1735521196)||40<br><br>**[halov](/member/halov)**  <br><br>   39 天前<br><br>可以试一下 k3s ，轻量级的 k8s ，部署起来不需要太多的资源，用来学习不错|

|   |   |   |
|---|---|---|
|![dufzh](https://cdn.v2ex.com/gravatar/bc29023dd8a515ced866c93536dbc8e1?s=48&d=retro)||41<br><br>**[dufzh](/member/dufzh)**  <br><br>   39 天前<br><br>硬件有限，单机部署可以试试 k3s,kind ，minikube 也行|

|   |   |   |
|---|---|---|
|![mohuani](https://cdn.v2ex.com/avatar/7ae3/4ce7/568301_normal.png?m=1737938045)||42<br><br>**[mohuani](/member/mohuani)**  <br><br>   39 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>[https://github.com/guangzhengli/k8s-tutorials](https://github.com/guangzhengli/k8s-tutorials) 试试这个，这个我全程走过一遍，基本上没有什么大坑，比较丝滑|

|   |   |   |
|---|---|---|
|![pckillers](https://cdn.v2ex.com/avatar/0562/d2f7/65223_normal.png?m=1712295654)||43<br><br>**[pckillers](/member/pckillers)**  <br><br>   39 天前<br><br>仅用一台 2 核 8g 的 Centos 服务器。 这个硬件基础服务的 pod 都会报资源不足。  <br>  <br>平时本地调试新的 k8s 集群都是先起 8 个 4c8g 的虚拟机。3master 3node 1 负载均衡 1 仓库。 然后再看情况加机器。|

|   |   |   |
|---|---|---|
|![LokiSharp](https://cdn.v2ex.com/avatar/1c55/ed11/29137_normal.png?m=1731045836)||44<br><br>**[LokiSharp](/member/LokiSharp)**  <br><br>   39 天前<br><br>先弄个 64G 内存的机器吧|

|   |   |   |
|---|---|---|
|![wellbeing](https://cdn.v2ex.com/gravatar/58dff0533227df869ae22466a42f9887?s=48&d=retro)||45<br><br>**[wellbeing](/member/wellbeing)**  <br><br>   39 天前<br><br>先搞清楚 K8S 的大概的定义：Kubernetes is an open-source container orchestration platform that automates the deployment, management, and scaling of containerized applications  <br>  <br>container orchestration platform 这个就说明为什么需要容器了，至于不需要 docker ，你可以理解为 docker 只是一个 implementation ，现在的 K8S 是基于 CRI ，CRI 是一个 specification ，底层无论是 docker 或者 containerd ，只要他符合 CRI 的规范就可以|

|   |   |   |
|---|---|---|
|![liuliancao](https://cdn.v2ex.com/avatar/15e6/93a1/544167_normal.png?m=1671781734)||46<br><br>**[liuliancao](/member/liuliancao)**  <br><br>   39 天前<br><br>看看电子书 kubernetes in action 然后多操作|

|   |   |   |
|---|---|---|
|![lveye](https://cdn.v2ex.com/gravatar/2778ed4b511f5414cf69d2499c596f6a?s=48&d=retro)||47<br><br>**[lveye](/member/lveye)**  <br><br>   39 天前   ![❤️](/static/img/heart_neue_red.png?v=16ec2dd0a880be6edda1e4a2e35754b3) 1<br><br>哈哈，看了下上边的回复，分享下我的推荐。看过极客时间，练过官方文档，翻过数 10 本 k8s 相关书。入门的书籍，推荐奈吉尔波尔顿的《 kubernetes 修炼手册》，基本概念讲的比较清晰。环境搭建，minikube 或者 kubeasz 脚本一把梭（ [https://github.com/easzlab/kubeasz](https://github.com/easzlab/kubeasz) ）这个可以在环境搭建上省 80-90%的时间，把精力集中到 k8s 的使用和熟悉上|

|   |   |   |
|---|---|---|
|![donnylai](https://cdn.v2ex.com/avatar/34b1/33a2/302410_normal.png?m=1736324772)||48<br><br>**[donnylai](/member/donnylai)**  <br><br>   39 天前<br><br>推荐一个大佬的文章，前阵子就参考的这个 [https://blog.csdn.net/weixin_52799373/article/details/140430146](https://blog.csdn.net/weixin_52799373/article/details/140430146)|

|   |   |   |
|---|---|---|
|![kivmi](https://cdn.v2ex.com/avatar/f035/930d/599386_normal.png?m=1710077859)||49<br><br>**[kivmi](/member/kivmi)**  <br><br>   39 天前<br><br>@[kursk](/member/kursk) K8S 只是一个容器编排工具，管理 pod 和容器，当然会涉及网络，存储，服务暴露之类的东东。|

|   |   |   |
|---|---|---|
|![kivmi](https://cdn.v2ex.com/avatar/f035/930d/599386_normal.png?m=1710077859)||50<br><br>**[kivmi](/member/kivmi)**  <br><br>   39 天前<br><br>@[LokiSharp](/member/LokiSharp) 自己玩 16G ，可以的|

|   |   |   |
|---|---|---|
|![kivmi](https://cdn.v2ex.com/avatar/f035/930d/599386_normal.png?m=1710077859)||51<br><br>**[kivmi](/member/kivmi)**  <br><br>   39 天前<br><br>@[gdw1986](/member/gdw1986) 用 kubeadmin 就绕过了|

|   |   |   |
|---|---|---|
|![ceclinux](https://cdn.v2ex.com/gravatar/c94496ed19500aeba409f129e935717e?s=48&d=retro)||52<br><br>**[ceclinux](/member/ceclinux)**  <br><br>   39 天前<br><br>要做好学习一门课程的准备，我认为理解成把它理解成面向部署的一个 api 服务器比较容易上手。  <br>楼上提到的 kubernetes in action 是好书，我看过，不过我记得有点老了。|

|   |   |   |
|---|---|---|
|![userdhf](https://cdn.v2ex.com/gravatar/774befc079db2edf25e2a7ef0e7ff08d?s=48&d=retro)||53<br><br>**[userdhf](/member/userdhf)**  <br><br>   39 天前<br><br>先提问：为什么要用 k8s ？ k8s 解决了什么问题？ k8s 比 docker 单例有什么区别和优势？什么是微服务？微服务怎么管理？微服务如何公用和通信？ k8s 有内外之分吗？|

|   |   |   |
|---|---|---|
|![cxmtime](https://cdn.v2ex.com/gravatar/b0e727180a039eee905ce85bac112af5?s=48&d=retro)||54<br><br>**[cxmtime](/member/cxmtime)**  <br><br>   39 天前<br><br>正在打算考 cka 认证。我用一台 4c 8g 的旧电脑用 kubeadmin 搭建 3 个节点的 k8s 集群，跑起来没问题。  <br>  <br>楼主的 gitlab cicd 是怎么练习的？|

|   |   |   |
|---|---|---|
|![Ashe007](https://cdn.v2ex.com/avatar/cdb3/c329/683571_normal.png?m=1717585814)||55<br><br>**[Ashe007](/member/Ashe007)**  <br><br>OP<br><br>   39 天前<br><br>@[cxmtime](/member/cxmtime) 就在云服务器上安装 Gitlab & Gitlab Runner ，将 runner 注册至 Gitlab ，推送代码至 Gitlab ，Gitlab 会根据项目的.gitlab-ci.yml 文件触发 ci/cd 。  <br>  <br>yml 文件的内容则是 Pipeline 的 job ，job 的行为则是由 runner 执行|

|   |   |   |
|---|---|---|
|![Ashe007](https://cdn.v2ex.com/avatar/cdb3/c329/683571_normal.png?m=1717585814)||56<br><br>**[Ashe007](/member/Ashe007)**  <br><br>OP<br><br>   39 天前<br><br>@[cxmtime](/member/cxmtime) [https://www.cnblogs.com/ashet/p/18636441](https://www.cnblogs.com/ashet/p/18636441)  <br>可以参考这篇 blog 练习|

|   |   |   |
|---|---|---|
|![firefox12](https://cdn.v2ex.com/gravatar/c0c6c84d38b3dc0cfcc775a7466481b2?s=48&d=retro)||57<br><br>**[firefox12](/member/firefox12)**  <br><br>   38 天前<br><br>一个软件叫 k8seasy 可以一键安装 kubernetes 无需翻墙，无需下载镜像，所有配置都配好了 一键就好了。可惜已经 4 年多没更新了，只能装老版本，最新版本 政区 025 年会发。  <br>  <br>[https://github.com/xiaojiaqi/k8seasy_release_page](https://github.com/xiaojiaqi/k8seasy_release_page)  <br>  <br>[https://github.com/xiaojiaqi/deploy-microservices-to-a-Kubernetes-cluster](https://github.com/xiaojiaqi/deploy-microservices-to-a-Kubernetes-cluster)|
