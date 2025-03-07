---
link: https://www.v2ex.com/t/1098315
site: V2EX
date: 2024-12-17T21:33
excerpt: "分享发现 - @740moe - 支持 worker && pages 部署！使用 pages 部署可以 fork
  仓库，或者下载_worker.js 文件打包成压缩文件上传！# 免费套餐介绍- **存储**: 每月"
twitter: https://twitter.com/@V2EX
slurped: 2025-02-08T10:47
title: 利用 CloudFlare R2 搭建图床/视频床！无服务器快速部署！ - V2EX
---
  
  [740moe](/member/740moe) · 52 天前 · 1270 次点击

这是一个创建于 52 天前的主题，其中的信息可能已经有所发展或是发生改变。

支持 worker && pages 部署！使用 pages 部署可以 fork 仓库，或者下载_worker.js 文件打包成压缩文件上传！

# 免费套餐介绍

- **存储**: 每月 10 GB
- **A 类操作**: 每月 100 万次请求
- **B 类操作**: 每月 1000 万次请求
- **出口（数据传输到互联网）**: 免费

个人使用完全足够！图床默认开启压缩，可以储存更多的图片文件！

## 功能特点

- 查看本地历史记录
- 可选的访客验证功能
- 单文件最大支持 20MB
- 支持多文件上传和粘贴上传
- 支持批量操作和显示上传时间
- 图片自动压缩（ GIF 和视频除外）
- Cloudflare Cache API 缓存支持
- 基于 Cloudflare R2 的文件存储
- 支持多种链接格式（ URL 、BBCode 、Markdown ）
- 支持常见的图片和视频格式（ jpg 、png 、gif 、mp4 ）

## 部署教程：

### 1. 环境变量说明

需要在 Cloudflare Workers 中配置以下环境变量:

|变量名|说明|必填|示例|
|---|---|---|---|
|DOMAIN|自定义域名|是|example.workers.dev|
|DATABASE|D1 数据库绑定变量名称|是|DATABASE|
|USERNAME|管理员用户名|是|admin|
|PASSWORD|管理员密码|是|password123|
|ADMIN_PATH|管理后台路径|是|admin|
|ENABLE_AUTH|访客验证（设置为 true 开启，不设置或设置为 false 则关闭）|否|false|
|R2_BUCKET|R2 存储桶名称|是|R2_BUCKET|

### 2. 创建 R2 存储桶

1. 登录 [Cloudflare Dashboard](https://dash.cloudflare.com)
2. 进入 `R2 对象储存` → `创建存储桶`
3. 设置存储桶名称和区域
4. 保存存储桶的名称以便后续使用

### 3. 创建 D1 数据库

1. 登录 [Cloudflare Dashboard](https://dash.cloudflare.com)
2. 进入 `Workers & Pages` → `D1 SQL 数据库`
3. 点击 `创建` 创建数据库
    - 数据库名称可自定义，例如 `images`
    - 建议选择数据库位置为 `亚太地区`，可以获得更好的访问速度
4. 创建数据表:
    - 点击数据库名称进入详情页
    - 选择 `控制台` 标签
    - 执行以下 SQL 语句:

```sql
CREATE TABLE media (
    url TEXT PRIMARY KEY
);
```

### 4. 创建 Worker

1. 进入 `Workers & Pages`
2. 点击 `创建`
3. 选择 `创建 Worker`
4. 为 Worker 设置一个名称
5. 点击 `部署` 创建 Worker
6. 点击继续处理项目

### 5. 配置环境变量

1. 在 Worker 的 `设置` → `变量和机密` 中
2. 点击 `添加` 添加变量
3. 点击 `部署`

### 6. 绑定数据库和 R2 储存

1. 在 Worker 设置页面找到 `设置` → `绑定`
2. 点击 `添加`
3. 选择 `D1 数据库`
4. 设置变量名为 `DATABASE`
5. 选择之前创建的数据库
6. 点击 `部署`
7. 重复上述步骤绑定 R2 储存，变量名为 `R2_BUCKET`

### 7. 绑定域名

1. 在 Worker 的 `设置` → `域和路由`
2. 点击 `添加` → `自定义域`
3. 输入你在 Cloudflare 绑定的域名
4. 点击 `添加域`
5. 等待域名生效

### 8. 部署代码

1. 进入 Worker 的编辑页面
2. 将 `_worker.js` 的完整代码复制粘贴到编辑器中
3. 点击 `部署`

### 9. 配置缓存

1. 进入 Cloudflare Dashboard
2. 进入 `网站` → `选择你的自定义域名` → `缓存` → `Cache Rules` → `创建缓存规则`
3. 选择 `缓存所有内容模板`
4. 设置 `边缘 TTL` → `忽略缓存控制标头，使用此 TTL` → `30 天`（根据需要设置）
5. 点击 `部署`

源码： [https://github.com/0-RTT/JSimages](https://github.com/0-RTT/JSimages)

测试： ![image](https://baipiao.de/1734401106722.png)

![image](https://baipiao.de/1734438813282.png)

[

Cloudflare](/tag/Cloudflare)[

R2](/tag/R2)[

图床](/tag/图床)

9 条回复  **•**  2024-12-19 23:48:21 +08:00

|   |   |   |
|---|---|---|
|![mayli](https://cdn.v2ex.com/gravatar/208dc525906db4a320e01914cc0f7af4?s=48&d=retro)||1<br><br>**[mayli](/member/mayli)**  <br><br>   52 天前<br><br>域名不错|

|   |   |   |
|---|---|---|
|![hanguofu](https://cdn.v2ex.com/gravatar/108099cd4cea8dd2f44cffc10e0ae2b9?s=48&d=retro)||2<br><br>**[hanguofu](/member/hanguofu)**  <br><br>   52 天前<br><br>谢谢分享。请问在哪里可以设置 访问图床/视频床的频次 ？|

|   |   |   |
|---|---|---|
|![740moe](https://cdn.v2ex.com/gravatar/87debd9e71f45569cc3a756c22be6dc2?s=48&d=retro)||3<br><br>**[740moe](/member/740moe)**  <br><br>OP<br><br>   51 天前<br><br>@[hanguofu](/member/hanguofu) cf 的防火墙配置规则估计可以|

|                                                                                 |     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| ------------------------------------------------------------------------------- | --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ![Lunrry](https://cdn.v2ex.com/avatar/f625/5dae/635681_normal.png?m=1730706709) |     | 4<br><br>**[Lunrry](/member/Lunrry)**  <br><br>   51 天前<br><br>按照你的步骤来，上传图片报错：R2 上传错误: TypeError: R2_BUCKET.put is not a function  <br>at handleUploadRequest (worker.js:881:21)  <br>at async Object.fetch (worker.js:20:44)  <br>at async jsonError (.internal-0c998967-b…e-facade-1.js:12:12)  <br>at async jsonError (.internal-0c998967-b…e-facade-1.js:12:12)  <br>at async jsonError (.internal-0c998967-b…e-facade-1.js:12:12)  <br>at async jsonError (.internal-0c998967-b…e-facade-1.js:12:12) |

|   |   |   |
|---|---|---|
|![740moe](https://cdn.v2ex.com/gravatar/87debd9e71f45569cc3a756c22be6dc2?s=48&d=retro)||5<br><br>**[740moe](/member/740moe)**  <br><br>OP<br><br>   51 天前<br><br>@[Lunrry](/member/Lunrry) 估计变量没对。照着 readme 弄下吧。我更新了下部署的流程。[https://github.com/0-RTT/JSimages/blob/main/README](https://github.com/0-RTT/JSimages/blob/main/README)|

|   |   |   |
|---|---|---|
|![Lunrry](https://cdn.v2ex.com/avatar/f625/5dae/635681_normal.png?m=1730706709)||6<br><br>**[Lunrry](/member/Lunrry)**  <br><br>   51 天前<br><br>@[740moe](/member/740moe) #5 现在可以使用了，请问有将其接入到 picgo 的方案吗|

|   |   |   |
|---|---|---|
|![liulicaixiao](https://cdn.v2ex.com/avatar/8818/6464/599423_normal.png?m=1732329733)||7<br><br>**[liulicaixiao](/member/liulicaixiao)**  <br><br>   50 天前<br><br>op 的域名： [https://baipiao.de/](https://baipiao.de/) 非常好|

|   |   |   |
|---|---|---|
|![740moe](https://cdn.v2ex.com/gravatar/87debd9e71f45569cc3a756c22be6dc2?s=48&d=retro)||8<br><br>**[740moe](/member/740moe)**  <br><br>OP<br><br>   50 天前<br><br>@[Lunrry](/member/Lunrry) 目前没有，让 gpt 帮你试试。我没用过 picgo|

|   |   |   |
|---|---|---|
|![740moe](https://cdn.v2ex.com/gravatar/87debd9e71f45569cc3a756c22be6dc2?s=48&d=retro)||9<br><br>**[740moe](/member/740moe)**  <br><br>OP<br><br>   50 天前<br><br>@[liulicaixiao](/member/liulicaixiao) 嘿嘿👍|
