---
layout: post
title: "用 Jekyll 搭建 GitHub Pages 博客"
date: 2026-03-13 10:00:00 +0800
categories: [技术]
tags: [Jekyll, GitHub Pages, 静态网站, 教程]
description: 一步步教你用 Jekyll 在 GitHub Pages 上搭建免费的个人博客，适合新手入门。
---

**GitHub Pages** + **Jekyll** 是搭建个人博客最流行的免费方案之一。本文记录我的搭建过程，希望对你有帮助。

## 前置知识

- 基本的命令行操作
- Git 基础（clone、push）
- 会写 Markdown

## 核心概念

### GitHub Pages 是什么？

GitHub Pages 是 GitHub 提供的**静态网站托管服务**，对公开仓库完全免费。只要你的仓库名称为 `<username>.github.io`，push 代码后网站就会自动部署到 `https://<username>.github.io`。

### Jekyll 是什么？

Jekyll 是一个**静态网站生成器**，用 Ruby 编写，GitHub Pages 原生支持它。它能将 Markdown 文件 + HTML 模板编译成完整的静态网站。

```
📁 my-blog/
├── _config.yml      # 全局配置
├── _layouts/        # 页面模板
├── _posts/          # 博客文章（Markdown）
├── assets/          # CSS / JS / 图片
└── index.html       # 首页
```

## 创建步骤

### 1. 新建仓库

在 GitHub 创建名为 `<你的用户名>.github.io` 的仓库，注意必须是 **公开仓库**。

### 2. 配置 `_config.yml`

```yaml
title: 我的博客
description: 分享技术与生活
author: 你的名字
url: "https://username.github.io"
```

### 3. 创建首篇文章

在 `_posts/` 目录下创建文件，命名格式必须是：

```
YYYY-MM-DD-文章标题.md
```

例如：`2026-03-14-hello-world.md`

文章头部加上 Front Matter：

```markdown
---
layout: post
title: "第一篇文章"
date: 2026-03-14 12:00:00 +0800
categories: [技术]
tags: [入门]
---

正文内容写在这里...
```

### 4. 推送到 GitHub

```bash
git add .
git commit -m "初始化博客"
git push origin main
```

推送完成后，等几分钟，访问 `https://<username>.github.io` 即可看到你的博客！

## 常见问题

**Q：本地如何预览？**

安装 Jekyll 后运行：
```bash
bundle exec jekyll serve
```
然后访问 `http://localhost:4000`。

**Q：如何绑定自定义域名？**

在仓库设置的 Pages 选项中填写你的域名，并在 DNS 服务商处配置 CNAME 记录指向 `<username>.github.io` 即可。

## 总结

GitHub Pages + Jekyll 方案的优点：**免费、快速、无需服务器**，非常适合个人博客。

祝你的博客越写越好 ✍️
