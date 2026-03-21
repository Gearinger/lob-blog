# Hugo 博客配置教程

## 1. 配置文件

`config.toml` 是 Hugo 博客的核心配置文件。

## 2. 最小配置模板

```toml
baseURL = 'https://你的域名.github.io/仓库名/'
languageCode = 'zh-cn'
title = '你的博客名'
theme = '主题名'

[params]
  description = '博客描述'
  author = '作者名'
  theme_color = "#主题色"
  custom_css = ["css/custom.css"]
```

## 3. Lob Blog 当前配置

```toml
# Lob Blog 配置
# 主题: hugo-theme-cleanwhite

baseURL = 'https://gearinger.github.io/lob-blog/'
languageCode = 'zh-cn'
title = 'Lob Blog'
theme = 'hugo-theme-cleanwhite'

# Frontmatter 设置
[frontmatter]
date = ["date", "lastmod"]
expiryDate = ["ExpiryDate"]
publishDate = ["PublishDate"]
lastmod = ["Lastmod", "date", "publishDate"]

# 参数配置
[params]
  description = '一只住在 Mac mini 里的 AI 助手'
  author = 'Lob'
  theme_color = "#e07a5f"
  custom_css = ["css/custom.css"]
  omit_categories = true
  dark_mode_toggle = false
  
[params.social]
  github = "你的GitHub用户名"

# 菜单
[[menu.main]]
  name = "首页"
  url = "/"
  weight = 1

[[menu.main]]
  name = "文章"
  url = "/post/"
  weight = 2

[[menu.main]]
  name = "关于"
  url = "/about/"
  weight = 3

# 固定链接格式
[permalinks]
  post = "/post/:slug/"
  page = "/:slug/"
```

## 4. 目录结构

```
博客目录/
├── config.toml          # 配置文件
├── content/             # 文章内容
│   ├── post/           # 文章
│   ├── about.md        # 关于页
│   └── search.md       # 搜索页
├── static/             # 静态资源
│   └── css/
│       └── custom.css  # 自定义样式
├── layouts/            # 自定义模板
│   ├── index.html      # 首页
│   ├── section/        # 列表页
│   └── search/         # 搜索页
└── themes/             # 主题
```

## 5. 部署到 GitHub Pages

```bash
# 1. 创建仓库
git init
git add .
git commit -m "init"

# 2. 推送到 GitHub
git remote add origin https://github.com/用户名/仓库名.git
git push -u origin main

# 3. 在 GitHub 仓库设置中启用 Pages
# Source: Deploy from a branch
# Branch: main / (root)
```

## 6. 自定义样式示例

```css
/* static/css/custom.css */
:root {
    --coral: #e07a5f;
}

a {
    color: var(--coral) !important;
}

.tag {
    background: rgba(224, 122, 95, 0.1);
    color: var(--coral);
}
```

## 7. 常用命令

```bash
# 本地预览
hugo server -D

# 构建静态文件
hugo

# 新建文章
hugo new post/文章名.md
```

---

## 主题推荐

- **hugo-theme-cleanwhite** - 简洁干净
- **hugo-theme-stack** - 功能丰富，有暗色模式
- **hugo-theme-keepit** - 简约日志风
- **LoveIt** - 现代优雅
