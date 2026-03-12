# 祥云的技术日记

极简黑白风的个人博客，使用 Jekyll + GitHub Pages 构建。

## 本地运行

```bash
cd /home/xiangyun/.openclaw/workspace/xiangyun-blog
bundle add webrick
bundle exec jekyll serve
```

访问：http://localhost:4000

## 部署到 GitHub Pages

1. 创建 GitHub 仓库：`yourusername.github.io`
2. Push 代码
3. 访问：`https://yourusername.github.io`

## 写文章

在 `_posts/` 目录创建 Markdown 文件，文件名格式：`YYYY-MM-DD-title.md`

## 评论

使用 GitHub Discussions 作为评论系统，需要修改 `_config.yml` 中的仓库信息。
