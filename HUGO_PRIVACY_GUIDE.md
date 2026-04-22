# Hugo Privacy Policy 模板使用指南

## 文件结构

```
your-hugo-site/
├── layouts/
│   ├── page/
│   │   └── privacy.html          # 单页面模板
│   └── partials/
│       └── privacy-policy.html   # 可复用 partial
├── i18n/
│   ├── zh-CN.toml                # 中文翻译
│   └── en.toml                   # 英文翻译
└── content/
    └── privacy.md                # 内容文件
```

## 使用方式

### 方式一：独立页面

创建 `content/privacy.md`:

```markdown
---
title: "隐私政策"
date: 2026-04-22
type: "privacy"
---
```

然后在 `layouts/page/privacy.html` 中使用定义好的模板。

### 方式二：作为 partial 嵌入其他页面

```html
{{ partial "privacy-policy.html" . }}
```

### 方式三：内容文件中直接使用

在任意 Markdown 文件中：

```markdown
{{</* partial "privacy-policy.html" . */>}}
```

## 在 hugo.toml 中配置

```toml
[params.privacy]
last_updated = "2026年4月22日"
contact_email = "support@nodalert.app"
```

## 编译静态 HTML（可选）

如果需要生成静态 HTML 文件用于 App 内置，可使用 Hugo 的 `--disableLiveReload` 和 `--destination`：

```bash
hugo --disableLiveReload --destination ./app/src/main/assets
```

## 自定义样式

在 `assets/` 或 `static/css/` 中添加自定义样式，例如 `static/css/privacy.css`:

```css
.privacy-policy__section {
  margin-top: 2rem;
}

.privacy-policy__title {
  font-size: 2rem;
  color: #1a1a1a;
}

.privacy-policy__section h2 {
  margin-top: 1.5rem;
  color: #333;
}
```

然后在 `layouts/_default/baseof.html` 中引入：

```html
{{ range .Site.Languages }}
{{ end }}
```
