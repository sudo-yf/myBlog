# GitHub Pages 部署指南

## 前置设置

### 1. 创建 GitHub 仓库

1. 在 GitHub 创建新仓库，命名为 `myBlog`
2. 初始化本地 git 仓库并推送代码：

```bash
cd /Users/a123/Desktop/Blog/myBlog
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/sudo-yf/myBlog.git
git push -u origin main
```

### 2. 配置 GitHub Pages

1. 进入仓库设置: `Settings` → `Pages`
2. 在 **Source** 下选择 `GitHub Actions`
3. 保存设置

### 3. 触发部署

GitHub Actions 会在每次推送到 `main` 分支时自动构建和部署。

首次推送代码后，Actions 会自动运行，您可以在仓库的 `Actions` 标签页查看进度。

## 自动部署流程

工作流文件位于：`.github/workflows/deploy.yml`

每次推送代码时，GitHub Actions 会：
1. ✅ 检出代码
2. ✅ 安装 Node.js 和依赖
3. ✅ 构建生产版本（`npm run build`）
4. ✅ 部署到 GitHub Pages

## 访问您的网站

部署成功后，网站将在以下地址可访问：

**https://sudo-yf.github.io/myBlog/**

## 常见问题

### 部署失败？

1. 检查 Actions 日志查看错误信息
2. 确保 `package.json` 中的构建命令正确
3. 确保 `astro.config.ts` 中的 `site` 配置正确

### 更新网站内容

1. 在本地修改文章或配置
2. 提交并推送到 GitHub：

```bash
git add .
git commit -m "Update content"
git push
```

3. GitHub Actions 会自动重新部署

### 手动触发部署

在仓库的 Actions 标签页，选择 "Deploy to GitHub Pages" 工作流，点击 "Run workflow"。

## 本地预览

在推送前，始终先在本地预览：

```bash
npm run dev      # 开发模式
npm run build    # 构建生产版本
npm run preview  # 预览生产版本
```

## 自定义域名（可选）

如果有自定义域名：

1. 在仓库根目录创建 `public/CNAME` 文件
2. 文件内容为您的域名，例如：`blog.yourdomain.com`
3. 在域名提供商设置 DNS:
   - 类型：`CNAME`
   - 名称：`blog` (或 `www`)
   - 值：`sudo-yf.github.io`

---

**准备好部署了吗？** 按照上述步骤操作即可！🚀
