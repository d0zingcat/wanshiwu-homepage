# wanshiwu-homepage

[d0zingcat](https://wanshiwu.fyi) 的个人主页，部署在 [wanshiwu.fyi](https://wanshiwu.fyi)。

## 技术栈

- [Hugo](https://gohugo.io/) — 静态网站生成器
- [hugo-coder](https://github.com/luizdepra/hugo-coder) — 主题（通过 Hugo Modules 管理）
- [Cloudflare Pages](https://pages.cloudflare.com/) — 部署与托管

## 本地开发

**前置要求**

- [Hugo](https://gohugo.io/installation/) extended 版本（`brew install hugo`）
- [Go](https://go.dev/dl/)（Hugo Modules 依赖）

**启动开发服务器**

```bash
hugo server
```

访问 [http://localhost:1313](http://localhost:1313)

**生产构建**

```bash
hugo
# 输出到 public/ 目录
```

## 主题更新

主题通过 Hugo Modules 管理，更新方式：

```bash
hugo mod get -u github.com/luizdepra/hugo-coder
hugo mod tidy
```

## 替换头像

将头像图片覆盖 `static/images/avatar.jpg` 即可，推送后 Cloudflare Pages 自动重新部署。

## 部署配置（Cloudflare Pages）

| 配置项 | 值 |
|---|---|
| Framework preset | `Hugo` |
| Build command | `hugo` |
| Build output directory | `public` |
| 环境变量 `HUGO_VERSION` | `0.160.1` |

绑定自定义域名 `wanshiwu.fyi`：Cloudflare Pages → Custom Domains，因域名已由 Cloudflare 管理，DNS 记录会自动添加。
