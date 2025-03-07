---
link: https://www.v2ex.com/t/1101192
site: V2EX
date: 2024-12-30T10:28
excerpt: 分享创造 - @devdes - 今年 Claude 的开发商 Anthropic 发布了模型上下文协议（ Model Context
  Protocol ）。MCP 作为一个开放协议，标准化了应用程序如何向大型语言模型（ LLMs ）
twitter: https://twitter.com/@V2EX
slurped: 2025-02-10T10:02
title: 苦于 Claude 接连被封，我把 5ire 做成了一款 MCP 客户端 - V2EX
---

**今年 Claude 的开发商 Anthropic 发布了模型上下文协议（ Model Context Protocol ）。MCP 作为一个开放协议，标准化了应用程序如何向大型语言模型（ LLMs ）提供上下文信息。用开发商的话来说 MCP 就好比 AI 应用的 USB-C 端口。USB-C 提供了一种标准化的方式来连接你的设备到各种外围设备和配件，而 MCP 提供了一种标准化的方式来连接 AI 模型到不同的数据源和工具。 具体来说，MCP 的作用是帮助开发者构建基于 LLMs 的代理和复杂工作流程。**

但 Anthropic 一系列封号连招我已暂时放弃了 Claude 客户端。于是把 5ire ( [https://5ire.app](https://5ire.app/))做了一次升级，支持了 MCP 标准，并内置了一些 MCP Servers.

[![](https://i.imgur.com/4biA20l.png)](https://i.imgur.com/4biA20l.png)

由于现在的 MCP Servers 基本是采用 Python 和 Node 构建，使用前需安装 Python 和 Node 运行环境，并确保 npx 和 uvx 能正常执行。

目前 5ire 对 MCP 的支持还处于早期，并未在不同操作系统下对所有模型进行测试，各模型的支持程度也存在差异，测试效果比较好的是 GPT-4 系列模型和 Gemini 系列模型，Claude 按理说效果也不错，但因为账号被封，无法测试。

尽管还有一些兼容性问题，尤其是在 Window 系统上，也算赶是在 2025 前将 5ire 打造成了一款 MCP 客户端。感兴趣的朋友可以试试，[https://5ire.app](https://5ire.app/)