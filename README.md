# storage-information

Hugo + PaperMod 博客，用来记录系统、存储和个人思考。该仓库包含源码，GitHub Pages 通过 Workflow 自动构建并部署。

## 本地开发

```bash
brew install hugo # 确保是 extended 版本
hugo server -D    # 预览草稿
```

## 自动部署

1. 将仓库推送到 GitHub，并在 Settings → Pages 中把部署分支设为 `gh-pages`。
2. Workflow `.github/workflows/deploy.yml` 会在 push 到 `main` 或手动触发时运行：
   - checkout 最新代码；
   - 安装 Hugo（extended）；
   - 执行 `hugo --gc --minify`；
   - 把 `public/` 内容推送到 `gh-pages` 分支。
3. 首次运行后，等待 GitHub Pages 构建完成，即可通过 `https://alexanderWangzz.github.io/storage-information/` 访问。

如需自定义域名，在仓库根目录的 `static/CNAME` 写入域名，并在域名注册商配置 CNAME 解析到 `alexanderWangzz.github.io`。
