# 上传 GitHub 与发布网页

本项目是静态网页，`index.html` 就是网站入口。使用 GitHub Pages 发布后，读者可以直接在浏览器中操作页面。

## 第一步 解压并检查

解压发布包，打开 `options-payoff-lab` 文件夹，双击 `index.html`，确认能正常打开和拖动滑块。

上传时使用这个文件夹内的内容，**不要只上传 ZIP 压缩包，也不要把整个项目再嵌套到仓库的子文件夹里**。仓库首页应直接能看到 `index.html` 和 `README.md`。

## 第二步 创建公开仓库

登录 GitHub，选择 New repository。

- 仓库名可以使用 `options-payoff-lab`。
- 可使用简介：`中文期权教学网页：拖动股价，对比四种策略与持股组合的到期损益。`
- 选择 Public，便于所有人查看源码和使用。
- 包内已经有 README 和 LICENSE，无需再选择自动生成相同文件。

创建仓库后，使用上传已有文件的入口；已有仓库可以选择 Add file → Upload files。把项目文件及 `docs` 文件夹拖入上传区域，保留目录结构，然后提交保存。

文件选择器如果看不到点开头的 `.nojekyll` 等文件，可以显示隐藏文件后再选取，或者使用 GitHub Desktop 上传完整目录。它们不是密钥。

## 第三步 开启 GitHub Pages

1. 打开仓库的 Settings。
2. 在侧边栏选择 Pages。
3. 在 Build and deployment 下，把 Source 设为 Deploy from a branch。
4. Branch 选择 `main`，目录选择 `/ (root)`，然后保存。若实际默认分支不是 `main`，选择含有 `index.html` 的分支。
5. 等待部署完成，回到 Pages 设置页，使用 Visit site 打开发布后的网页。

项目站点地址通常为 `https://你的用户名.github.io/仓库名/`，实际以 GitHub Pages 设置页显示的地址为准。这个格式是说明用的示例，包内没有预填他人的账户或仓库地址。

公开仓库可使用 GitHub Free 的 GitHub Pages。GitHub 官方说明，提交后网页更新可能需要最多约10分钟。

## 第四步 分享与更新

将发布后的网页链接放到仓库 About 的 Website 字段，其他人可以从仓库直接打开。

以后修改 `index.html` 并提交到发布分支，GitHub Pages 会重新部署。更新截图时，同步替换 `docs/preview.png`。

## 页面打不开时

- 显示404：确认发布分支的根目录直接包含 `index.html`，并确认部署已经完成。
- 只看到源码：请打开 Pages 发布后的站点地址；GitHub 的文件浏览页主要用于查看源码。
- 仍显示旧版：先确认新提交已部署，再刷新浏览器或重新打开页面。
- 手机上左右变成上下排列：这是窄屏适配；较宽窗口会显示左右两栏。

## 官方操作文档

- [向仓库添加文件](https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository)
- [创建 GitHub Pages 网站](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site)
- [配置发布来源](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
