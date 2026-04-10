# Jamsread.github.io

基于 [Jekyll](https://jekyllrb.com/) + [Chirpy](https://github.com/cotes2020/jekyll-theme-chirpy) 主题的个人技术博客。

## 本地预览

```bash
bundle install
bundle exec jekyll serve
```

访问 `http://localhost:4000` 查看效果。

## 站点结构

```
├── _config.yml       # 站点配置
├── _tabs/            # 导航页面（关于、归档、分类、标签）
├── _posts/           # 博客文章
├── assets/           # 静态资源
├── index.html        # 首页
├── Gemfile           # Ruby 依赖
└── .github/workflows # GitHub Actions 部署
```

## 写文章

在 `_posts/` 目录下创建 `YYYY-MM-DD-title.md` 文件：

```yaml
---
title: "文章标题"
date: 2026-04-10 10:00:00 +0800
categories: [分类1, 分类2]
tags: [标签1, 标签2]
---

正文内容...
```

## 部署

推送到 `master` 分支后，GitHub Actions 会自动构建并部署到 [jamsread.github.io](https://jamsread.github.io)。

> 需要在 GitHub 仓库的 Settings → Pages 中将 Source 设置为 **GitHub Actions**。
