---
description: "Hard rules for Jekyll blog post front-matter — layout, image placement, canonical URL"
applyTo: "_posts/**/*.md"
---

# Blog Post Front-Matter Rules

## ⛔ NEVER MISS THESE — Post Renders as Plain Text Without Them

### Rule 1 — `layout: post` is REQUIRED in every post

`_config.yml` has NO front-matter defaults for posts. Without `layout: post`, Jekyll has no template and the post renders as unstyled plain text.

```yaml
---
layout: post   # ← ALWAYS the first field
title: "..."
```

**Every post file must have this. No exceptions.**

### Rule 2 — `image` belongs at root level, NOT inside `header:`

The theme's `_layouts/post.html` reads `page.image` for the `<img>` tag. If you put `image` inside `header:`, it becomes `page.header.image` — the image will not appear.

**Wrong:**
```yaml
header:
  image: /assets/images/posts/hero.jpg      # ← never here
  image_credit: "Photographer on Unsplash"
  image_credit_url: "https://unsplash.com/..."
```

**Correct:**
```yaml
image: /assets/images/posts/hero.jpg        # ← root level
header:
  image_credit: "Photographer on Unsplash"  # ← header: only for credit
  image_credit_url: "https://unsplash.com/..."
```

Why this split: `page.image` → renders `<img>`, `page.header.image_credit` → renders attribution line via `image-credit.html` include.

---

## Complete Valid Front-Matter Template

```yaml
---
layout: post
title: "Post Title Including Primary Keyword"
subtitle: "Optional subtitle"
date: YYYY-MM-DD HH:MM:SS +0530
last_modified_at: YYYY-MM-DD
category: tools
tags: [tag-one, tag-two, tag-three, tag-four]
excerpt: "2-3 sentence summary. Max 250 chars."
description: "SEO meta description 140-160 chars with primary keyword."
image: /assets/images/posts/{slug}/hero.jpg
header:
  image_credit: "Photographer Name on Unsplash"
  image_credit_url: "https://unsplash.com/photos/xyz"
author: satya-k
difficulty: beginner
read_time: true
toc: true
toc_sticky: true
seo:
  primary_keyword: "primary keyword phrase"
  secondary_keywords: [keyword-two, keyword-three]
  canonical_url: "https://srisatyalokesh.is-a.dev/learn-ai/{slug}/"
---
```

## Validation Checklist (run before every commit)

- [ ] `layout: post` present as first field
- [ ] `image:` is at root level (not inside `header:`)
- [ ] `canonical_url` uses `https://srisatyalokesh.is-a.dev/learn-ai/{slug}/`
- [ ] `description` is 140-160 characters
- [ ] `category` matches one of: `ai`, `system-design`, `backend`, `devops`, `frontend`, `career`, `tools`
- [ ] Related/internal links use `{{ '/{slug}/' | relative_url }}` Liquid filter (not bare root-relative paths)
