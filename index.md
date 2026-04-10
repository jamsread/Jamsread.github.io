---
layout: default
title: Home
---

# Hi, I'm Jamsread 👋

C++ 客户端工程师，专注于**桌面应用**、**NAS** 和**工具链**开发。

我喜欢用代码解决实际问题，尤其是在文件管理、文档处理和跨设备同步方面。

---

## 最新文章

{% for post in site.posts limit:5 %}
- **[{{ post.title }}]({{ post.url | relative_url }})** — {{ post.date | date: "%Y-%m-%d" }}
{% endfor %}

{% if site.posts.size == 0 %}
_暂无文章，敬请期待..._
{% endif %}

---

## 我的项目

| 项目 | 简介 |
|------|------|
| **Markdown Reader** | NAS 上的 Markdown 阅读器，支持离线浏览与全文搜索 |
| **Qt Editor** | 基于 Qt 的轻量级文本编辑器 |
| **Remote Sync** | 跨设备文件远程同步工具 |

→ [查看全部项目](./projects)

---

## 联系我

- GitHub: [github.com/jamsread](https://github.com/jamsread)
