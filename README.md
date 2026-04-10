# Jamsread.github.io

基于 Jekyll + GitHub Pages 的个人网站。

## 本地预览

```bash
gem install bundler jekyll
bundle exec jekyll serve
```

访问 `http://localhost:4000` 查看效果。

## 站点结构

```
├── index.md          # 首页
├── about.md          # 关于页面
├── projects.md       # 项目展示
├── _posts/           # 博客文章
├── _config.yml       # Jekyll 配置
└── assets/css/       # 自定义样式
```

## 发布

推送到 `main` 分支后，GitHub Pages 会自动构建并部署到 [jamsread.github.io](https://jamsread.github.io)。
