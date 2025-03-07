---
link: https://www.v2ex.com/t/1110795
site: V2EX
date: 2025-02-11T23:47
excerpt: "分享创造 - @websong188 - ## cursor 生成 markdown 会出现代码块转义混乱问题使用 cursor
  生成带有代码片段的 markdown 文件时,包含代码和 json 的地方，它会自动分割成块只能"
twitter: https://twitter.com/@V2EX
slurped: 2025-02-12T10:09
title: 烦了很久的 cursor markdown 代码块转义混乱问题 ! 写 prompt 解决了 - V2EX
---

使用 cursor 生成带有代码片段的 markdown 文件时,包含代码和 json 的地方，它会自动分割成块

只能局部应用到 cursor,无法全部应用到 md 文件

甚至有时候还会出现断开的混乱渲染情况

提问如果没特别要求,每次输出的情况都可能不一样

参考 cursor 社区和网上的方法,整合了个常用的 prompt,使用起来挺稳定的

## 解决 cursor markdown 格式渲染和代码缩进问题的 prompt

```
Format your response in markdown according to the following requirements:

- When proposing an edit to a markdown file, first evaluate whether the content will contain code snippets
- If the content contains no code snippets, enclose the entire response in backticks with 'markdown' as the language identifier
- If the content includes code snippets, ensure all code blocks are indented with exactly 2 spaces and specify the correct language for proper rendering
- Only 2-space indentation is allowed for code blocks - level 0 and 4 space indentations are not permitted
- Automatically correct any code block indentation that doesn't follow the 2-space rule

```

需要 cursor 输出 markdown 内容时，复制上面提示词贴入 cursor 聊天框即可

具体示例和效果可看博客文章: [解决 Cursor Markdown 格式代码块转义、缩进问题](https://blog.taoluyuan.com/blog/complete-fix-cursor-markdown-chaos)

有普通 markdown 结果 和使用 prompt 的结果对比