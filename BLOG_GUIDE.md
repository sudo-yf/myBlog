# Blog Article Template

Use this template when creating new blog posts. Copy this to `src/content/blog/` directory.

## Required Frontmatter Fields

```yaml
---
title: 'Your Article Title'           # ⭐ Required, max 60 characters
description: 'Brief description'       # ⭐ Required, max 155 characters  
date: 2024-12-13                      # ⭐ Required, format: YYYY-MM-DD
tags: ['tag1', 'tag2']                # Optional, use kebab-case
image: './cover.jpg'                  # Optional, 1200×630px recommended
authors: ['yifan']                    # Optional, matches filename in authors/
draft: false                          # Optional, true = not published
---
```

## File Organization

### Option 1: Single File (Simple)
```
src/content/blog/
└── my-article.md
```

### Option 2: Directory (Recommended for articles with images)
```
src/content/blog/
└── my-article/
    ├── index.md        # Article content
    ├── cover.jpg       # Cover image
    └── image1.png      # Other images
```

## Image Storage

### Local Images (Recommended)
Store images in the same directory as your article:

```markdown
![Description](./image.png)
```

### Public Images
Store in `public/images/blog/`:

```markdown
![Description](/images/blog/image.png)
```

## Supported Features

- ✅ **Markdown** - Standard syntax
- ✅ **MDX** - Import React components
- ✅ **Code Highlighting** - Multiple languages
- ✅ **Math** - KaTeX for formulas
- ✅ **Emoji** - :smile: :rocket:
- ✅ **Tables** - GitHub Flavored Markdown

## Example Article Structure

```markdown
---
title: 'My First Post'
description: 'Learning to use this blog system'
date: 2024-12-13
tags: ['tutorial', 'getting-started']
authors: ['yifan']
---

# Introduction

Your opening paragraph...

## Main Content

### Subsection

Content here...

## Conclusion

Wrap up your article...
```

## Publishing Workflow

1. Create article file in `src/content/blog/`
2. Add frontmatter metadata
3. Write content in Markdown
4. Test locally: `npm run dev`
5. Build: `npm run build`
6. Deploy to GitHub Pages

## Tips

- Keep titles under 60 characters for SEO
- Write descriptions under 155 characters
- Use descriptive image alt text
- Optimize images before uploading
- Use kebab-case for tags (e.g., `web-development`)
- Set `draft: true` for unpublished articles
