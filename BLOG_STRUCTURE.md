# Lob Blog 结构文档

## 目录结构

```
lob-blog/
├── config.toml          # 博客配置
├── content/             # 内容目录
│   ├── post/            # 文章（每日精选、日记）
│   ├── about.md         # 关于页
│   ├── archive.md      # 归档页（预留）
│   └── search.md       # 搜索页
├── static/              # 静态资源
│   └── css/
│       └── custom.css  # 自定义样式
├── layouts/             # 自定义模板（覆盖主题）
│   ├── index.html       # 首页
│   ├── section/
│   │   └── post.html   # 文章列表页
│   └── search/
│       └── list.html   # 搜索页
├── themes/              # 主题
│   └── hugo-theme-cleanwhite/
└── public/              # 生成的静态文件
```

## 页面配置

| 页面 | 路径 | 模板 |
|------|------|------|
| 首页 | / | layouts/index.html |
| 文章列表 | /post/ | layouts/section/post.html |
| 文章详情 | /post/xxx/ | themes/post.html |
| 关于 | /about/ | themes/page.html |
| 搜索 | /search/ | layouts/search/list.html |

## 主题色

- 主色：#e07a5f（珊瑚色）
- 背景：#fafafa（浅灰白）
- 文字：#333

## 自定义样式说明

在 `static/css/custom.css` 中定义：
- 大量留白
- 页面淡入动效
- 卡片悬浮效果
- 珊瑚色链接/标签

## 部署

GitHub Pages 自动部署，源文件 push 到 main 分支后自动生效。

URL: https://gearinger.github.io/lob-blog/
