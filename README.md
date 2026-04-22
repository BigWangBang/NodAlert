# NodAlert Privacy Policy - Hugo Site

一个使用 Hugo 构建的隐私政策页面，支持中英文双语，可直接部署到 Vercel。

## 目录结构

```
Privacys/
├── content/
│   ├── privacy.md          # 中文隐私政策
│   └── en/
│       └── privacy.md      # 英文隐私政策
├── layouts/
│   ├── _default/
│   │   ├── baseof.html     # 基础模板
│   │   └── single.html     # 单页面模板
│   └── partials/
│       └── privacy-policy.html  # 隐私政策 partial
├── i18n/
│   ├── zh.toml             # 中文翻译
│   └── en.toml             # 英文翻译
├── static/
│   └── css/
│       └── style.css       # 样式文件
├── hugo.toml               # Hugo 配置
└── vercel.json            # Vercel 部署配置
```

## 快速部署到 Vercel

### 方式一：Vercel CLI

```bash
npm i -g vercel
cd Privacys
vercel
```

### 方式二：Git 部署

1. 将此目录推送到 GitHub/GitLab 仓库
2. 在 Vercel 导入项目
3. Vercel 会自动识别 Hugo 并部署

### 方式三：手动部署

```bash
# 安装 Hugo
# macOS
brew install hugo

# Windows (使用 Chocolatey)
choco install hugo -y

# 构建
hugo

# 部署 public 目录
```

## 本地开发

```bash
hugo server -D
```

访问 http://localhost:1313/zh/privacy/ 查看中文版

## 配置

在 `hugo.toml` 中修改：

```toml
[params.privacy]
  last_updated = "2026年4月22日"
  contact_email = "support@nodalert.app"
  app_name = "NodAlert"
```

## 自定义域名

在 Vercel 控制台设置自定义域名后，更新 `hugo.toml` 中的 `baseURL`。

## 技术栈

- [Hugo](https://gohugo.io/) - 静态网站生成器
- [Vercel](https://vercel.com/) - 部署平台
- 中英双语 i18n 支持
