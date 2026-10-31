# Qiang 的博客

基于 [Hexo](https://github.com/hexojs/hexo) + [Butterfly](https://github.com/jerryc127/hexo-theme-butterfly) 主题的个人博客。

## 常用命令

```bash
npm install                 # 安装依赖
npx hexo new "文章标题"      # 新建文章（生成于 source/_posts/）
npm run server              # 本地预览 http://localhost:4000
npm run clean && npm run build   # 构建静态文件到 public/
```

## 目录说明

| 路径 | 作用 |
| --- | --- |
| `_config.yml` | 站点配置：标题、作者、网址、永久链接、搜索、RSS |
| `_config.butterfly.yml` | 主题配置（覆盖主题默认值）：菜单、头像、封面、侧边栏、特效 |
| `source/_posts/` | 文章（Markdown） |
| `source/about/` `tags/` `categories/` | 独立页面 |
| `source/img/` | 头像、横幅、默认封面 |
| `source/css/custom.css` | 自定义美化样式 |
| `themes/butterfly/` | 主题源码（不建议直接修改） |

## 部署到 GitHub Pages

1. 在 GitHub 新建仓库 `<用户名>.github.io`，把本项目推送到 `main` 分支
2. 仓库 Settings → Pages → Source 选择 **GitHub Actions**
3. 把 `_config.yml` 里的 `url` 改成 `https://<用户名>.github.io`

之后每次 push，`.github/workflows/deploy.yml` 会自动构建并发布。
