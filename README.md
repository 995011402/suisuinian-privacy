# suisuinian-privacy · 隐私政策与用户协议站点

> 岁岁念（com.suisuinian.app）配套的隐私政策 + 用户协议静态站点。
> 部署在 GitHub Pages，自定义域 `privacy.suisuinian.net`。

---

## 文件结构

```
privacy-site/
├── README.md                   # 本文件
├── _config.yml                 # Jekyll 配置
├── CNAME                       # privacy.suisuinian.net（GitHub Pages 自动识别）
├── privacy-policy.md           # 隐私政策（最终公开版）
├── terms.md                    # 用户协议（占位，待补）
├── _layouts/
│   └── default.html            # 移动端友好的 HTML 模板
├── assets/
│   └── css/
│       └── style.css           # 响应式样式
└── .github/
    └── workflows/
        └── jekyll.yml          # GitHub Actions 监听 main → 部署 gh-pages
```

## 部署流程

1. 修改 `privacy-policy.md` 或 `terms.md`
2. `git add . && git commit -m "update policy" && git push`
3. GitHub Actions 自动构建 Jekyll → 部署到 gh-pages 分支
4. 1-2 分钟后生效：`https://privacy.suisuinian.net/privacy-policy/` / `https://privacy.suisuinian.net/terms/`

## 本地预览（可选）

需要 Ruby 3.x：
```bash
cd privacy-site
gem install jekyll bundler
bundle install
bundle exec jekyll serve
# 访问 http://localhost:4000
```

## DNS 配置（一次性）

域名服务商（阿里云/腾讯云/Cloudflare）添加：

| 记录类型 | 主机记录 | 记录值 |
|---------|---------|--------|
| CNAME | privacy | `995011402.github.io.` |

GitHub 仓库 → Settings → Pages → Custom domain 输入 `privacy.suisuinian.net` → Save。
勾选 `Enforce HTTPS`（Let's Encrypt 自动签发证书，约 5-10 分钟）。
