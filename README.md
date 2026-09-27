# Kaijie Yin 的个人学术主页

使用 [Jekyll](https://jekyllrb.com/) 构建，通过 GitHub Pages 部署。论文信息保存在 Markdown 文件的 front matter 中，无需 Node.js 或前端打包工具。

## 文件结构

| 文件或目录 | 用途 |
| --- | --- |
| `index.html` | 首页内容：个人简介、研究、论文、荣誉、经历和学术服务 |
| `_layouts/default.html` | 共同页面外壳、导航和页脚 |
| `_includes/publication.html` | 首页与论文详情页共用的论文展示模板 |
| `_layouts/post.html` | 单篇论文页面模板 |
| `_posts/` | 论文信息；按 Jekyll 文章日期排列 |
| `style.scss` | 页面样式与移动端布局 |
| `images/` | 头像、论文图片和机构 Logo |
| `_config.yml` | 网站名称、网址、Jekyll 配置等 |
| `_site/` | 本地生成的站点；请编辑源文件，而不是这个目录 |

首页有独立的 `index.html`。论文页面使用 `/publications/:title/` 路径，避免多篇文章覆盖首页。

## 本地预览

需要先安装 Ruby、Jekyll 及配置中使用的插件。可参照 [Jekyll 安装说明](https://jekyllrb.com/docs/installation/) 配置所在系统的环境；已有环境可跳过安装。以下命令在项目根目录运行：

```sh
gem install jekyll jekyll-sitemap
jekyll serve --host 127.0.0.1
```

在浏览器打开 `http://127.0.0.1:4000`。修改页面或样式后刷新查看；修改 `_config.yml` 后需重新启动预览。

只生成静态页面时运行：

```sh
jekyll build
```

本地 Ruby/Jekyll 版本可能与 GitHub Pages 不同，发布后也应检查 GitHub Pages 的构建结果和实际页面。

## 更新内容

- 修改个人简介、联系方式、荣誉和经历：编辑 `index.html`。
- 修改公共导航、页脚或页面元信息：编辑 `_layouts/default.html`。
- 修改排版、颜色与响应式布局：编辑 `style.scss`。
- 替换图片：将文件放入 `images/`，并同步更新对应路径。
- 修改站点名称或网址：编辑 `_config.yml`；自定义域名还需与 GitHub Pages 设置保持一致。

## 添加论文

在 `_posts/` 下新增 `YYYY-MM-DD-short-title.markdown`，并在文件开头填写 YAML front matter，例如：

```yaml
---
layout: post
title: "Your Paper Title"
date: 2026-09-01 00:00:00 +00:00
image: /images/your-paper.png
categories: research
author: "Kaijie Yin"
authors: "<strong>Kaijie Yin</strong>, Coauthor One, Coauthor Two"
venue: "Conference or Journal Name"
arxiv: https://arxiv.org/abs/YOUR_PAPER_ID
code: https://github.com/YOUR_ACCOUNT/YOUR_REPOSITORY
---
```

将示例内容替换为真实论文信息，并上传对应图片。没有的资源字段直接省略。现有模板使用的可选资源字段包括 `arxiv`、`paper`、`video`、`code`、`poster`、`slides`、`website` 和 `youtube`。

论文图片使用统一的 8:5 展示区域，默认按比例完整显示。如果原图上下有大幅白边，可添加 `image_fit: cover`，让图片放大填满展示区域；使用前请确认裁去的仅是白边，图表和文字仍完整可见。

`authors` 支持 HTML，可用 `<strong>` 突出本人姓名；共同一作等标注按论文实际情况保留。`date` 控制文章排序及显示年份，文件名日期也应与之保持一致。需要正文时，可在 front matter 的结束分隔线后添加 Markdown。

提交前建议检查首页与单篇论文页面、手机宽度的显示效果、所有新增链接，以及图片路径的大小写。GitHub Pages 使用的文件系统区分大小写。

## 部署

将修改推送到仓库当前 GitHub Pages 配置对应的发布分支，并在仓库 **Settings → Pages** 中确认部署来源。构建结果可在 GitHub 的部署记录或 Actions 中查看。源码保持为 GitHub Pages 支持的 Jekyll 站点，不需要提交本地 `_site/` 产物。

## 致谢与内容版权

项目源自 [Jekyll Now](https://github.com/barryclark/jekyll-now)，原始布局参考 [Jon Barron 的学术主页](https://jonbarron.info/)。本次视觉设计参考 [Zechun Liu 的学术主页](https://zechunliu.com/)。

使用模板时，请尊重 `images/`、`pdfs/` 和 `_posts/` 中图片、论文及个人内容的版权；替换为自己的内容，并保留相应来源说明。
