---
link: https://www.v2ex.com/t/1112908
site: V2EX
date: 2025-02-20T13:41
excerpt: 分享创造 - @dearzhzhao - 对于个人开发者或尝鲜者而言，本地想要部署 DeepSeek
  有很多种方案，但是一旦涉及到企业级部署，则步骤将会繁琐很多。比如我们的第一步就需要先根据实际业务场景评估出我们到底需要部署什么规格的
twitter: https://twitter.com/@V2EX
slurped: 2025-02-20T16:44
title: DeepSeek 企业级部署实战指南：从服务器选型到 Dify 私有化落地 - V2EX
---
    [dearzhzhao](/member/dearzhzhao) · 3 小时 3 分钟前 · 182 次点击

对于个人开发者或尝鲜者而言，本地想要部署 DeepSeek 有很多种方案，但是一旦涉及到企业级部署，则步骤将会繁琐很多。

比如我们的第一步就需要先根据实际业务场景评估出我们到底需要部署什么规格的模型，以及我们所要部署的模型，到底需要多少服务器资源来进行承接，也就是**资源预估先行。**

预估完我们的服务器资源以后，还需要评估我们的业务场景是否需要二次开发模型。

如果只是简单的微调模型就可以符合我们的业务需求，那么使用 Ollama 、LM Studio 、GTP4All 或许就可以满足我们的诉求。

**但是如果需要对模型进行定制化开发，则需要考虑进行模型的原生部署。**

所以本篇文章主要解决四个问题：

1. 如何合理评估我们的服务器资源
2. Ollama 部署指定版本的 DeepSeek
3. 原生部署 DeepSeek
4. 搭建 Dify 构建企业内的私有知识库、工作流

原创作者: 数字生命贾克斯，[如遇到图片不能正常显示等问题，可访问文章的原链接](https://mp.weixin.qq.com/s/U3RYRqNppuEX4oMdgiKu9Q?token=423632529&lang=zh_CN)

# 评估服务器资源

评估服务资源前我们需要先考虑将要部署的模型参数量、模型的序列长度、批次大小和量化类型。

## 模型参数量

模型参数量：就是该模型神经网络的输入权重和输出阈值的总和，模型参数量的大小，直接影响到模型智能化程度的高低，关于这点如果不足够清楚的可以参考之前我写过的一篇文章：[人人都能搞定的大模型原理 - 神经网络](https://mp.weixin.qq.com/s/O0k1o5x_iDNTVN-50D_fVQ?token=423632529&lang=zh_CN)

模型参数量越高耗费的服务器资源越多，反之亦然。

## 模型序列长度

那么在我们可以确认了模型的参数规模后，就需要根据业务场景评估该模型的序列长度。

序列长度是该模型一次能处理的最大 Token 数，针对 QA 问答的模型，你可以理解为你每次问模型问题时可以输入的最大 Token 限制，如果用户的问题超出了这个长度，则用户的问题可能会被截断或者被分为多个部分进行分别处理。

## 模型量化类型

而模型的量化类型，则是该模型的参数精度，我们在之前的模型原理中提到过，训练好的模型实际存储的就是一堆参数值，而这些参数值本身就是浮点数，所以量化类型的值越大则模型的精度越准确，智能化程度越高。

## 服务器资源计算

了解了上述的基本概念后，你可能会觉得我依然无法评估模型到底应该占用多少服务器资源呀？怎么办？

呐，不要急。

关于具体的参数映射到底应该配置什么样的服务器资源，有网友已经做了一个配置计算器工具。

6b983dc921c8a87cf0734d28143449e7-185431.jpg

你只需要根据上面的概念选择自己的模型规模，便会自动计算出所需要的服务器资源。

原创作者: 数字生命贾克斯，[如遇到图片不能正常显示等问题，可访问文章的原链接](https://mp.weixin.qq.com/s/U3RYRqNppuEX4oMdgiKu9Q?token=423632529&lang=zh_CN)

** [账号后台发送关键字：资源评估] 就可以获取该工具啦！**

# Ollama 部署 DeepSeek

---

Ollama 是本地运行大模型的一款工具，支持在 Mac 、Linux 、Windows 上下载并运行对应的模型。

## Ollama 安装

```java
# MacOS 、Windows 用户直接访问 Ollama 官网 https://ollama.com/download 下载对应的安装包直接安装即可

# Linux 安装
curl -fsSL https://ollama.com/install.sh | sudo bash
sudo usermod -aG ollama $USER  # 添加用户权限
sudo systemctl start ollama    # 启动服务
```

Ollama 安装完成后，在对应的命令行输入：

```java
ollama -v
```

此时输出 Ollama version is 0.5.7 ，则表示安装成功。

## DeepSeek 模型安装

Ollama 安装成功后则访问 Ollama 的官网查找我们要安装的模型

1 、[访问 Ollama 官网](https://ollama.com/library/deepseek-r1:7b)

2 、选择适合当前机器配置的模型参数，然后拷贝对应的执行命令即可

1. 命令行终端直接执行对应的命令

```
ollama run deepseek-r1:7b
# 执行后
pulling manifest
pulling 96c415656d37... 100% ▕██████████████▏ 4.7 GB
pulling 369ca498f347... 100% ▕██████████████▏ 387 B
pulling 6e4c38e1172f... 100% ▕██████████████▏ 1.1 KB
pulling f4d24e9138dd... 100% ▕██████████████▏ 148 B
pulling 40fb844194b2... 100% ▕██████████████▏ 487 B
verifying sha256 digest
writing manifest
success
> > > Send a message (/? for help)
> > > `
#当看到上述提示，即可开始模型对话，此时我发送一个问题：你是谁
>>> 你是谁
<think>
</think>
您好！我是由中国的深度求索（ DeepSeek ）公司开发的智能助手 DeepSeek-R1 。如您有任何任何问题，我会尽我所能为您提供帮助。
>>>
```

恭喜！出现上述的对话内容，表示当前 DeepSeek 已经在你本地可以正常运行了。

## nomic-embed-text 模型安装

此时我们需要另外再部署一个新的模型，nomic-embed-text ，这是一个文本向量化的模型，主要是后续基于 Dify 做向量化检索时使用。

```
ollama pull nomic-embed-text
#执行后
pulling manifest 
pulling 970aa74c0a90... 100% ▕█████████ 274 MB                         
pulling c71d239df917... 100%  █████████ 11 KB                         
pulling ce4a164fc046... 100%  █████████ 17 B                         
pulling 31df23ea7daa... 100%  █████████ 420 B                         
verifying sha256 digest 
writing manifest 
#看到该提示表示安装成功
success 
```

## 部署图形化客户端

有些同学在部署完 DeepSeek 后就想直接找个 UI 工具和 DeepSeek 聊天了，而不是一直在对应的命令行工具中聊天。

此时我们直接部署一套 UI 工具，连接我们的 DeepSeek 模型即可。

可以连接 DeepSeep 模型的 UI 工具有很多：

1. ChatBox 客户端（图形化界面）支持 Web 网页，也支持本地客户端。
2. AnythingLLM 客户端（图形化界面）
3. Open WebUI 客户端（图形化界面） 支持 Web 网页，类似 ChatGPT 。
4. Cherry Studio 客户端（图形化界面）
5. Page Assist 客户端（浏览器扩展）支持「联网搜索」

此时我们以 ChatBox 为例，直接访问对应的[官网](https://chatboxai.app/zh)下载对应的客户端即可

下载完成后我们在 ChatBox 的设置中填写 Ollama API 的地址和对应的模型名称，然后保存即可。

然后我们直接打开一个新的对话框，选择要运行的模型即可开始对话。

原创作者: 数字生命贾克斯，[如遇到图片不能正常显示等问题，可访问文章的原链接](https://mp.weixin.qq.com/s/U3RYRqNppuEX4oMdgiKu9Q?token=423632529&lang=zh_CN)

# 原生部署 DeepSeek

原生部署 DeepSeek 则需要参考官方所提供的部署方式进行部署

上述提到 DeepSeek 可以支持 SGLang 、LMDeploy 、TensorRT-LLM 、vLLM 框架进行部署。

此处我们使用 LMDeploy 来部署 DeepSeek

ppqq LMDeploy 是一个用于大型语言模型（ LLMs ）和视觉-语言模型（ VLMs ）压缩、部署和服务的 Python 库。 其核心推理引擎包括 TurboMind 引擎和 PyTorch 引擎。前者由 C++ 和 CUDA 开发，致力于推理性能的优化，而后者纯 Python 开发，旨在降低开发者的门槛。

想要使用 LMDeploy 的前提是需要先使用 conda 或者 pip 安装对应的 python 库依赖才行。

```
conda create -n lmdeploy python=3.8 -y
conda activate lmdeploy
pip install lmdeploy
```

关于 LMDeploy 具体的安装方式也可以直接参考[安装文档](https://lmdeploy.readthedocs.io/zh-cn/latest/get_started/installation.html)

## 编写运行代码

```
from lmdeploy import pipeline, TurbomindEngineConfig

# 模型路径，可以是以下几种选项之一：
# 1. 本地目录路径，指向一个 turbomind 模型
# 2. lmdeploy-quantized 模型的 model_id
# 3. 存放在模型仓库中的模型的 model_id
model = 'deepseek-ai/DeepSeek-R1-Distill-Qwen-7B'

# Turbomind 引擎配置，用于设置模型的后端参数
backend_config = TurbomindEngineConfig(
    cache_max_entry_count=0.2,  # 缓存最大条目数
    max_context_token_num=20544,  # 最大上下文 token 数量
    session_len=20544  # 会话长度
)

# 生成配置，用于设置生成文本的参数
gen_config = GenerationConfig(
    top_p=0.95,  # 采样阈值
    temperature=0.6,  # 温度参数，影响生成的多样性
    max_new_tokens=8192,  # 最大新生成 token 数量
    stop_token_ids=[151329, 151336, 151338],  # 停止 token 的 ID 列表
    do_sample=True  # 启用采样
)

# DeepSeekAI 服务类
class DeepSeekAiServicer:

    def __init__(self, model: str, backend_config: TurbomindEngineConfig, gen_config: GenerationConfig):
        # 初始化服务，加载模型和配置
        self.llm = pipeline(model, backend_config=backend_config)
        self.gen_config = gen_config

    def chat(self, content):
        # 根据 DeepSeek 官方推荐，每个提示需要以<think>\n 结尾
        # 如果是数学推理内容，建议包含以下（中英文）：
        # 请逐步推理，并将最终答案放在\boxed{}中。
        prompts = [{
            "role": "user",
            "content": "生活的意义是什么？<think>\n"
        }]

        # 响应示例：
        # "<think> 生活的意义是快乐。 </think> 我认为生活的意义是快乐。"
        response = self.llm(prompts, gen_config=self.gen_config)
        return response
```

将上述代码直接在 python 环境中运行便可以直接启动我们的 DeepSeek 模型。

由于我们采用 LMDeploy 代码来部署模型，因此我们获得了更大的调整灵活性。我们能够针对内存管理、并发处理和负载均衡等多个方面进行细致的优化。此外，LMDeploy 允许我们集成其他 Python 库，以便对模型进行微调并添加自定义层，这些功能进一步提升了我们的定制化能力，确保了模型部署的灵活性和效率。

# 部署 Dify

Dify 是一款开源的大语言模型(LLM) 应用开发平台。它融合了后端即服务（ Backend as Service ）和 LLMOps 的理念，使开发者可以快速搭建生产级的生成式 AI 应用。即使你是非技术人员，也能参与到 AI 应用的定义和数据运营过程中。

由于 Dify 内置了构建 LLM 应用所需的关键技术栈，包括对数百个模型的支持、直观的 Prompt 编排界面、高质量的 RAG 引擎、稳健的 Agent 框架、灵活的流程编排，并同时提供了一套易用的界面和 API 。这为开发者节省了许多重复造轮子的时间，使其可以专注在创新和业务需求上。

**简单来说如果你想使用模型构建自己的 RAG 知识引擎或者流程编排，那你少不了写一堆 LangChain 的代码，但是 Dify 将这块业务进行了封装，你只需要在可视化的页面上操作，便可以实现相同的效果，快速的构建出自己的 AI 应用。**

## 运行 Dify

Dify 的部署需要我们本地先支持 Docker 和 Git 的依赖环境，然后我们在对应的终端直接执行下面的代码，便可以直接运行 Dify

```
#克隆 Dify 源代码至本地环境。
git clone https://github.com/langgenius/dify.git

#进入 Dify 源代码的 Docker 目录
cd dify/docker

#复制环境配置文件
cp .env.example .env

#启动 Docker 容器
docker-compose up -d
```

## 添加模型

Dify 启动成功后，我们直接浏览器访问： http://localhost

此时进入到 Dify 的主页面会提示新建账号密码，账号密码新建完成后，在右上角 admin 处点击设置，然后新增我们的本地模型配置。

此处添加 LLM 模型为 deepseek-r1:7b ，基础 URL 为： [http://host.docker.internal:11434](http://host.docker.internal:11434)

添加完 LLM 模型后，我们再新增一个 Text Embedding 模型，还记得最开始我们使用 ollama 还安装了一套 nomic-embed-text 模型吗？对的，就是在这里使用的。

两个模型都添加完以后，就可以在模型列表中看到我们已经添加的模型信息了

原创作者: 数字生命贾克斯，[如遇到图片不能正常显示等问题，可访问文章的原链接](https://mp.weixin.qq.com/s/U3RYRqNppuEX4oMdgiKu9Q?token=423632529&lang=zh_CN)

## 构建知识库

在对应的知识库模块新建知识库，并上传我们的私有数据

文本分段与清洗中选择使用我们的 nomic-embed-text 模型进行清洗

然后我么直接保存为知识库即可

## 新建聊天助手

在机器人的上下文中选择我们刚刚新建的知识库：“数字生命贾克斯”

当我们问他一些知识库中独有的内容时，他便会根据知识库中独有的内容，来给与对应的回复。

我们可以点击发布将该机器人单独给发布出去，此时其他人也可以使用你这个机器人来获取知识库中的信息了。

## 工作流

Dify 中还有一个非常杀手锏的应用，那就是工作流！

我一直认为 Dify 中最有价值的一个模块就是工作流模块，合理构建自己的工作流，就好比让一个只有大脑能力的模型，瞬间具备了可以行动的双手。

原本只能通过问答来交互的模型，瞬间具备了和外界交互的能力。

通过工作流，Dify 可以自动执行一系列复杂任务，比如数据分析、报告生成、资源调度甚至是跨平台操作。

这些任务不再是孤立的指令，而是形成了一个有机的整体，每个步骤都紧密相连，协同工作，从而极大地提升了工作效率。

**工作流模块的详解，我将在后续文章中单独介绍，以保持当前文章的简洁性。**

以上，既然看到这里了，如果觉得不错，随手点个赞和关注，并转发给更多的朋友吧！感恩。

对 AI 学习感兴趣的朋友，欢迎后台留言“电子书”，我将无偿提供我精心整理的 20 本电子书资源，助你一臂之力。期待与你共同进步！

5 条回复

|   |   |   |
|---|---|---|
|![dearzhzhao](https://cdn.v2ex.com/avatar/df9d/4261/527193_normal.png?m=1740022460)||1<br><br>**[dearzhzhao](/member/dearzhzhao)**  <br><br>OP<br><br>   3 小时 2 分钟前<br><br>Good 👍|

|   |   |   |
|---|---|---|
|![pol](https://cdn.v2ex.com/gravatar/0d4f712558090208cd0386048b1bb766?s=48&d=retro)||2<br><br>**[pol](/member/pol)**  <br><br>   2 小时 44 分钟前<br><br>dify 有局限性，比如使用第三方云 api 会有 http 超时时间，比如模型输出 token 过长，超过整体工作流时间会立即截停输出，上传知识库语料信息有文件大小限制，更改配置后还是会提示不可用|

|   |   |   |
|---|---|---|
|![dearzhzhao](https://cdn.v2ex.com/avatar/df9d/4261/527193_normal.png?m=1740022460)||3<br><br>**[dearzhzhao](/member/dearzhzhao)**  <br><br>OP<br><br>   2 小时 42 分钟前<br><br>@[pol](/member/pol) 你们现在用的是那个？|

|   |   |   |
|---|---|---|
|![pol](https://cdn.v2ex.com/gravatar/0d4f712558090208cd0386048b1bb766?s=48&d=retro)||4<br><br>**[pol](/member/pol)**  <br><br>   2 小时 40 分钟前<br><br>@[dearzhzhao](/member/dearzhzhao) #3 用的 dify ，就是在使用中发现的这些问题，目前没啥跟好的解决方式，不知扣子会不会比 dify 好点|

|   |   |   |
|---|---|---|
|![dearzhzhao](https://cdn.v2ex.com/avatar/df9d/4261/527193_normal.png?m=1740022460)||5<br><br>**[dearzhzhao](/member/dearzhzhao)**  <br><br>OP<br><br>   2 小时 38 分钟前<br><br>@[pol](/member/pol) 据我了解扣子比 dify 好一些。只是扣子本身不能私有化部署。企业内用起来不太方便。|

[

](https://www.digitalocean.com/?refcode=1b51f1a7651d)

**[关于](/about)   ·   [帮助文档](/help)   ·   [博客](https://blog.v2ex.com/)   ·   [API](/help/api)   ·   [FAQ](/faq)   ·   [实用小工具](/tools)   ·   5491 人在线**   最高记录 6679   ·     [![](/static/img/language.png?v=6a5cfa731dc71a3769f6daace6784739)   Select Language](/select/language)

创意工作者们的社区

World is powered by solitude

VERSION: 3.9.8.5 · 51ms · [UTC 08:44](/worldclock#utc) · [PVG 16:44](/worldclock#pvg) · [LAX 00:44](/worldclock#lax) · [JFK 03:44](/worldclock#jfk)  
Developed with [CodeLauncher](https://cl.v2ex.pro/)  
♥ Do have faith in what you're doing.