# 祥云的技术日记

一个使用 Jekyll 和 GitHub Pages 搭建的个人博客。

## 访问地址

✅ **首页（纯 HTML 版本）**：https://xuanxuan669966.github.io/xiangyun-blog/index.html

⏳ **首页和文章（Jekyll 版本）**：https://xuanxuan669966.github.io/xiangyun-blog/

> 注意：Jekyll 版本正在部署中，可能需要 3-5 分钟

## GitHub Pages 配置步骤

如果访问 Jekyll 版本出现 404，请按以下步骤配置：

1. **进入仓库设置页面**
   - 访问：https://github.com/xuanxuan669966/xiangyun-blog/settings/pages

2. **选择构建和部署方式**
   - 在 "Build and deployment" 部分
   - "Source" 选择：**GitHub Actions**
   - 点击 "Save"

3. **等待部署完成**
   - 访问：https://github.com/xuanxuan669966/xiangyun-blog/actions
   - 等待工作流显示绿色勾勾（✓）
   - 通常需要 2-3 分钟

4. **验证部署**
   - 访问：https://xuanxuan669966.github.io/xiangyun-blog/
   - 应该能看到文章卡片和侧边栏

## 文章列表

- [AI 日报 | 2026-03-13](/ai/ai-daily-report/)
- [欢迎来到我的博客](/life/welcome-to-my-blog/)

## 技术栈

- **Jekyll** - 静态站点生成器
- **GitHub Pages** - 免费托管
- **GitHub Actions** - 自动部署
- **Markdown** - 内容编写

## 本地预览

```bash
# 安装依赖
gem install jekyll jekyll-feed jekyll-seo-tag jekyll-sitemap

# 启动本地服务器
bundle exec jekyll serve

# 访问 http://localhost:4000
```

## 添加新文章

在 `_posts` 目录创建 Markdown 文件，文件名格式为：`YYYY-MM-DD-title.md`

```markdown
---
layout: post
title: 文章标题
date: 2026-03-13 12:00:00 +0800
categories: [分类]
tags: [标签1, 标签2]
---

文章内容...
```

## 许可证

© 2026 祥云. All rights reserved.
