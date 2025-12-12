# 字体使用指南

## 当前字体配置

网站默认使用系统字体栈，无需额外下载。配置位于 `src/styles/global.css`：

```css
font-family: 
  -apple-system, BlinkMacSystemFont, 
  'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell,
  'Fira Sans', 'Droid Sans', 'Helvetica Neue',
  sans-serif;
```

## 添加自定义字体

### 选项 1: Google Fonts（推荐）

Google Fonts 提供免费的网络字体。

#### 步骤：

1. 访问 [Google Fonts](https://fonts.google.com/)
2. 选择喜欢的字体（推荐：Inter, Roboto, Outfit, Poppins）
3. 点击字体，选择需要的字重
4. 复制生成的 `<link>` 代码
5. 添加到 `src/components/Favicons.astro` 的 `<head>` 中：

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
```

6. 更新 `src/styles/global.css`：

```css
:root {
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
}
```

### 选项 2: 本地字体文件

如果有自己的字体文件（.woff2, .woff, .ttf）：

#### 步骤：

1. 创建目录：

```bash
mkdir -p /Users/a123/Desktop/Blog/myBlog/public/fonts
```

2. 将字体文件放入 `public/fonts/`

3. 在 `src/styles/global.css` 中添加 `@font-face`：

```css
@font-face {
  font-family: 'CustomFont';
  src: url('/fonts/CustomFont-Regular.woff2') format('woff2'),
       url('/fonts/CustomFont-Regular.woff') format('woff');
  font-weight: 400;
  font-style: normal;
  font-display: swap;
}

@font-face {
  font-family: 'CustomFont';
  src: url('/fonts/CustomFont-Bold.woff2') format('woff2'),
       url('/fonts/CustomFont-Bold.woff') format('woff');
  font-weight: 700;
  font-style: normal;
  font-display: swap;
}
```

4. 使用字体：

```css
:root {
  font-family: 'CustomFont', sans-serif;
}
```

### 选项 3: Adobe Fonts (Typekit)

如果有 Adobe Creative Cloud 订阅：

1. 访问 [Adobe Fonts](https://fonts.adobe.com/)
2. 选择字体并创建网络项目
3. 复制生成的 `<link>` 代码
4. 添加到 `src/components/Favicons.astro`

## 推荐字体组合

### 现代简洁风格
- **标题**: Outfit, Poppins
- **正文**: Inter, Roboto

### 技术博客风格
- **标题**: DM Sans, Space Grotesk  
- **正文**: Inter, Source Sans Pro
- **代码**: Fira Code, JetBrains Mono

### 优雅阅读风格
- **标题**: Playfair Display, Merriweather
- **正文**: Lora, Crimson Text

## 代码编辑器字体

代码块字体在 `astro.config.ts` 中配置。如需更改：

```typescript
// 在 expressiveCode 配置中
theme: 'vitesse-dark', // 代码主题
```

推荐的代码字体（需要本地安装）：
- Fira Code（支持连字）
- JetBrains Mono
- Source Code Pro
- Cascadia Code

## 性能优化建议

1. **使用 WOFF2 格式**：文件最小，压缩最好
2. **限制字重数量**：只加载实际使用的字重
3. **使用 `font-display: swap`**：避免闪烁，优化加载
4. **Preconnect Google Fonts**：加快加载速度

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
```

## 中文字体特别说明

如需支持中文，推荐：
- **Noto Sans SC** (Google Fonts)
- **思源黑体** (本地)
- **霞鹜文楷** (开源)

中文字体文件较大，建议使用 CDN 或字体子集化。

---

**需要帮助？** 告诉我您想要的字体风格，我可以帮您配置！✨
