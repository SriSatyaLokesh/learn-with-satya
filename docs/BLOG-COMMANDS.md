# Blog Commands Quick Reference

**Professional blog creation system for Learn with Satya K**

---

## Commands Overview

| Command | Purpose | Time | Output |
|---------|---------|------|--------|
| `/blog write <topic>` | Write complete blog post from scratch | 15-20 min | `.md` file in `_posts/[category]/` |
| `/blog analyze <file>` | Quality audit with 0-100 scoring | 30 sec | Score breakdown + recommendations |
| `/blog brief <topic>` | Generate content brief | 5 min | Research requirements + structure |
| `/blog outline <topic>` | SERP-informed outline | 5 min | H2/H3 structure with notes |
| `/blog seo-check <file>` | Post-writing SEO validation | 1 min | SEO checklist (pass/fail) |
| `/blog rewrite <file>` | Optimize existing post | 10-15 min | Updated `.md` file |

---

## 1. Writing a New Post

### Command
```
/blog write "Understanding Transformer Architecture"
```

### What It Does
1. **Asks clarifying questions:**
   - Category (ai, system-design, backend, devops, frontend, career, tools)
   - Difficulty (beginner, intermediate, advanced)
   - Series (optional - which series and part number)
   - Target word count (default: 2,000-2,500)

2. **Auto-selects template** (from 12 types):
   - How-to Guide, Listicle, Case Study, Comparison
   - Pillar Page, Product Review, Thought Leadership, Roundup
   - Tutorial, News Analysis, Data Research, FAQ Knowledge

3. **Researches topic:**
   - Finds 8-12 current statistics (2025-2026 data)
   - Sources images from Pixabay/Unsplash/Pexels
   - Identifies Tier 1-3 sources

4. **Generates outline** (for your approval):
   - 60-70% question headings
   - Answer-first structure
   - Image/chart placement
   - Internal linking zones

5. **Writes complete post:**
   - Valid Jekyll front matter
   - TL;DR box after intro
   - Answer-first paragraphs (40-60 words with stat)
   - Citation capsules (AI-friendly)
   - Information gain markers (2-3)
   - FAQ section (3-5 questions)
   - 5-10 internal link zones
   - 4-6 images with credits

6. **Saves to:** `_posts/[category]/YYYY-MM-DD-[slug].md`

### Output Example

```yaml
---
title: "How Do Transformers Work? A Beginner's Guide to Attention Mechanisms"
date: 2026-03-10
category: ai
tags: [transformers, attention-mechanism, neural-networks, deep-learning]
excerpt: "Learn how transformer architecture revolutionized NLP with self-attention mechanisms"
description: "Transformers process sequences 10x faster than RNNs (Google, 2025). Learn attention mechanisms, positional encoding, and real-world applications."
difficulty: beginner
header:
  image: /assets/img/posts/transformer-architecture.jpg
  credit: Pixabay
  credit_url: https://pixabay.com/...
author: satya-k
---

# How Do Transformers Work? A Beginner's Guide to Attention Mechanisms

Imagine a system that can read an entire book and understand the context of
every word, all at once. That's the power of transformers...

> **TL;DR:** Transformers use self-attention mechanisms to process entire
> sequences simultaneously, achieving 10x faster training than RNNs (Google, 2025).
> This architecture powers ChatGPT, BERT, and 90% of modern NLP systems...

## What Are Transformers in Machine Learning?

Transformers are neural network architectures that process sequences by computing
relationships between all positions simultaneously ([Attention Is All You Need](https://arxiv.org/abs/1706.03762),
Vaswani et al., 2017). Unlike RNNs which process sequentially, transformers
achieve parallelization, reducing training time from weeks to days...

[... rest of post ...]
```

### After Writing

**Next steps you'll need to do:**

1. **Download images** - Save URLs to `/assets/img/posts/`
2. **Resolve internal links** - Convert `[INTERNAL-LINK: ...]` to actual URLs
3. **Run quality check** - `/blog analyze [file]`
4. **Preview locally** - `jekyll serve`
5. **Commit** - `git add`, `git commit`, `git push`

---

## 2. Analyzing Post Quality

### Command
```
/blog analyze _posts/ai/2026-03-10-transformer-architecture.md
```

### What It Does

Runs Python quality analyzer with 5-category scoring:

**1. Content Quality (30 pts)**
- Depth and comprehensiveness
- Readability (Flesch 60-70, Grade 7-8)
- Originality (information gain markers)
- Structure (paragraph/sentence length)
- Engagement (TL;DR, callouts)
- Grammar and style

**2. SEO Optimization (25 pts)**
- Title (50-60 chars, keyword placement)
- Headings (hierarchy, keywords in 2-3)
- Keyword density and placement
- Internal linking (3-5 contextual)
- Meta description (150-160 chars with stat)
- URL structure

**3. E-E-A-T Signals (15 pts)**
- Author attribution and bio
- Source citations (8+ unique, Tier 1-3)
- Trust indicators
- Experience signals (first-hand)

**4. Technical Elements (15 pts)**
- Images (alt text, credits, optimization)
- Structured data (lists, tables, code)
- Performance (no heavy embeds)
- Mobile-friendliness

**5. AI Citation Readiness (15 pts)**
- Citability (citation capsules)
- Q&A format (question headings, FAQ)
- Entity clarity (proper nouns, terms)
- Extraction friendly (clean markdown)

### Output Example

```markdown
# Blog Quality Analysis: Understanding Transformer Architecture

**Overall Score: 87/100 (Strong)**

## Score Breakdown

| Category | Score | Max | Pass |
|----------|-------|-----|------|
| Content Quality | 26 | 30 | ✅ |
| SEO Optimization | 22 | 25 | ✅ |
| E-E-A-T Signals | 13 | 15 | ✅ |
| Technical Elements | 14 | 15 | ✅ |
| AI Citation Readiness | 12 | 15 | ✅ |

## Strengths
- Excellent readability (Flesch: 65)
- Strong heading structure (8 H2s, 70% questions)
- Well-sourced (10 unique citations, all Tier 1-2)
- Good information gain markers (3 identified)
- Proper answer-first formatting

## Priority Fixes

### High Priority
- Add 2 more citation capsules (currently 4, target 6)
- Include FAQ section (0/3-5 questions)

### Medium Priority
- Add alt text to 2 images
- Resolve 6 internal link placeholders

### Low Priority
- Shorten meta description by 5 chars (currently 165)

## AI Content Detection
- AI Trigger Phrases: 2 (target: <5 per 1,000 words) ✅
- Vocabulary Diversity (TTR): 0.52 (target: 0.40-0.65) ✅
- Burstiness Score: High ✅
- **Assessment:** Likely Human-written

## Recommendations Summary
Strong post ready to publish after adding FAQ section and citation capsules.
Minor image alt text fixes recommended but not blocking.
```

### Scoring Bands

| Score | Band | Action |
|-------|------|--------|
| 90-100 | **Exceptional** | Publish immediately |
| 80-89 | **Strong** | Minor tweaks, ready to publish |
| 70-79 | **Acceptable** | Needs optimization before publish |
| 60-69 | **Below Standard** | Significant work needed |
| <60 | **Rewrite** | Fundamental issues, major revision |

**Minimum to publish:** 80+ (Strong band)

---

## 3. Generating Content Briefs

### Command
```
/blog brief "Kubernetes Deployment Strategies"
```

### What It Does

Creates a content brief with:

1. **Target keyword** and search intent analysis
2. **Competitor analysis** (SERP top 10)
   - Common topics covered
   - Gaps in existing content
   - Average word counts
3. **Required statistics** and source suggestions
4. **Recommended template** (based on intent)
5. **Outline structure** with H2/H3 suggestions
6. **Image requirements** (count, types)
7. **Internal linking opportunities**

### Output Example

```markdown
# Content Brief: Kubernetes Deployment Strategies

## Primary Keyword
`kubernetes deployment strategies` (Vol: 2,400/mo, CPC: $12)

## Search Intent
- **Dominant intent:** Informational (70%), Tutorial (30%)
- **Recommended template:** Tutorial (hands-on technical walkthrough)
- **Target audience:** Intermediate DevOps engineers

## SERP Analysis (Top 10)

**Common Topics Covered:**
1. Rolling updates (10/10 articles)
2. Blue-green deployments (9/10)
3. Canary deployments (9/10)
4. Recreate strategy (7/10)
5. Health checks and readiness probes (6/10)

**Content Gaps (Opportunities):**
- Real-world rollback procedures (only 2/10 cover)
- Performance comparison data (only 1/10 has metrics)
- Cost implications of each strategy (none cover)
- Hybrid strategy patterns (none cover)

**Average Metrics:**
- Word count: 2,350 words
- Images: 5-7 (mostly diagrams)
- Code examples: 8-12 snippets

## Required Research

**Statistics Needed (8-12):**
1. Deployment failure rates by strategy
2. Rollback time comparisons
3. Adoption rates (rolling vs blue-green vs canary)
4. Resource overhead percentages
5. Time-to-deploy benchmarks
6. Production incident rates
7. Recovery time objectives (RTO)
8. Cost comparison data

**Tier 1-3 Source Suggestions:**
- Kubernetes official docs (kubernetes.io)
- CNCF annual surveys
- Google Cloud blog (cloud.google.com)
- Datadog State of Kubernetes report
- Stack Overflow Developer Survey

## Recommended Outline

### H1: Which Kubernetes Deployment Strategy Should You Use in 2026?

**Introduction (100-150 words)**
- Hook: Deployment failure statistic
- Problem: Choosing wrong strategy causes downtime
- Promise: Compare 5 strategies with real data

**TL;DR:** [40-60 word summary]

### H2: What Are the 5 Main Kubernetes Deployment Strategies?
- Overview table comparing all 5
- Use case matrix
- [IMAGE: Strategy comparison diagram]

### H2: How Do Rolling Updates Work?
- Answer-first paragraph with adoption stat
- Step-by-step process
- [CODE: Rolling update YAML]
- Pros and cons
- [CITATION CAPSULE]

### H2: When Should You Use Blue-Green Deployments?
- Answer-first with rollback time stat
- Implementation guide
- [CODE: Blue-green setup]
- Cost implications
- [CITATION CAPSULE]

[... continue for all strategies ...]

### FAQ Section (5 questions)
- "Which strategy is fastest?"
- "What's the safest deployment method?"
- "How do I roll back a failed deployment?"
- "Which strategy costs the most?"
- "Can I combine multiple strategies?"

### Conclusion
- Decision matrix
- Next steps
- [INTERNAL-LINK: related content]

## Success Criteria
- Word count: 2,500-3,000
- Statistics: 10+ unique sources
- Code examples: 8-10 working snippets
- Images: 6-8 (diagrams + screenshots)
- Target score: 85+
```

---

## 4. Creating SEO-Optimized Outlines

### Command
```
/blog outline "Docker Best Practices for Production"
```

### What It Does

Generates SERP-informed outline with:

1. **H2/H3 structure** (60-70% questions)
2. **Answer-first paragraph notes** for each section
3. **Statistic placement** markers
4. **Image/chart suggestions**
5. **Internal linking zones**
6. **Citation capsule reminders**

### Output Example

```markdown
# Outline: Docker Best Practices for Production

## H1: What Are the Best Docker Practices for Production in 2026?

**Introduction (100-150 words)**
- Hook: Production Docker incident statistic
- Problem: Development practices don't scale to production
- Promise: 12 practices that prevent downtime

**TL;DR:** [Placeholder - will include key stat on container failure rates]

---

## H2: Why Do 67% of Docker Deployments Fail in Production?
**Word target:** 300-400 words

**Answer-first paragraph:**
- Stat: "67% of first-time Docker production deployments fail within the first month" (source: Datadog State of Containers 2025)
- Direct answer: Most failures stem from image bloat, missing health checks, and inadequate resource limits

**Content points:**
- Common failure patterns (with data)
- Root cause analysis
- [IMAGE: Failure rate chart by issue type]
- [CITATION CAPSULE: Self-contained passage about failure statistics]
- [INTERNAL-LINK: Docker fundamentals guide]

---

## H2: How Should You Structure Production Docker Images?
**Word target:** 400-500 words

**Answer-first paragraph:**
- Stat: "Multi-stage builds reduce image size by 82% on average" (Docker, 2025)
- Direct answer: Use multi-stage builds, minimal base images (alpine/distroless), and layer caching

**Content points:**
- Multi-stage build example
- [CODE: Optimized Dockerfile with comments]
- Base image comparison (alpine vs distroless vs scratch)
- Layer caching strategy
- [IMAGE: Image size comparison chart]
- [CITATION CAPSULE: Build time vs image size tradeoff]

[... continue for 8-10 more H2 sections ...]

---

## FAQ Section (5 questions)

### Should I use alpine or distroless base images?
**Answer:** [40-60 words with stat, compare security, size, compatibility]

### How many layers should a production Dockerfile have?
**Answer:** [40-60 words with stat, discuss optimization vs readability]

### What's the ideal Docker image size?
**Answer:** [40-60 words with stat, provide benchmarks by language]

### How often should I rebuild base images?
**Answer:** [40-60 words with stat, discuss security vs stability]

### Can I run Docker containers as root in production?
**Answer:** [40-60 words with stat, explain security implications]

---

## Conclusion (100-150 words)
- Key takeaways (bulleted)
- Implementation roadmap
- [INTERNAL-LINK: Kubernetes deployment guide]

---

## Checklist
- [ ] 60-70% question headings (currently 70%)
- [ ] Answer-first paragraphs (all H2s)
- [ ] 10+ unique statistics
- [ ] 6-8 images/charts
- [ ] 6-8 code examples
- [ ] 5-10 internal link zones
- [ ] Citation capsules in each major section
- [ ] FAQ with 5 questions
```

---

## 5. SEO Validation Checklist

### Command
```
/blog seo-check _posts/backend/2026-03-10-docker-production.md
```

### What It Does

Validates SEO elements against best practices:

### Output Example

```markdown
# SEO Validation: Docker Best Practices for Production

## ✅ Passed Checks (15)

### Title Optimization
- ✅ Length: 56 characters (target: 50-60)
- ✅ Primary keyword in first 40 characters
- ✅ Power word present ("Best Practices")
- ✅ No all-caps or excessive punctuation

### Meta Description
- ✅ Length: 158 characters (target: 150-160)
- ✅ Includes primary keyword
- ✅ Contains statistic with source
- ✅ Compelling call-to-action

### Heading Structure
- ✅ Single H1 (in title)
- ✅ Proper hierarchy (H1 → H2 → H3, no skips)
- ✅ 70% question headings (7/10 H2s)
- ✅ Primary keyword in 3 headings

### Keyword Optimization
- ✅ Keyword in first 100 words
- ✅ Keyword density: 1.8% (target: 1-2%)
- ✅ LSI keywords present (10 identified)
- ✅ Natural keyword distribution

### Internal Linking
- ✅ 5 internal link zones marked
- ✅ Descriptive anchor text (no "click here")

## ⚠️ Warnings (2)

### URL Structure
- ⚠️ URL length: 42 characters (recommend <40)
  - Current: `/backend/docker-production-best-practices-guide/`
  - Suggested: `/backend/docker-production-practices/`

### Images
- ⚠️ 1 image missing alt text (6/7 have alt text)
  - File: `/assets/img/posts/docker-production-3.jpg`
  - Suggested alt: "Docker multi-stage build diagram showing optimization"

## ❌ Failed Checks (0)

---

## Recommendations

### High Priority
None - all critical SEO elements pass

### Medium Priority
1. Shorten URL slug by 10 characters
2. Add alt text to remaining image

### Low Priority
1. Consider adding 1-2 more internal links
2. Add schema markup (Article + FAQ)

---

## Overall SEO Score: 92/100 (Excellent)

**Assessment:** Post is SEO-optimized and ready for publish after addressing
the 2 warnings. URL length is a minor issue that can be fixed in future posts.
```

---

## 6. Rewriting Existing Posts

### Command
```
/blog rewrite _posts/ai/2025-01-15-old-transformer-post.md
```

### What It Does

Optimizes existing post while preserving:
- Unique insights and personal experiences
- Original voice and style
- First-hand examples and case studies

Applies improvements:
- Answer-first formatting to H2 sections
- Citation capsules
- Information gain markers
- Updated statistics (2025-2026)
- FAQ section if missing
- Internal linking zones
- Image optimization

### Output

Updated file with changelog comment:

```yaml
---
title: "..." # Updated for clarity
date: 2025-01-15
lastUpdated: 2026-03-10  # Added
# ... rest of front matter ...
---

<!-- REWRITE CHANGELOG (2026-03-10):
- Added answer-first formatting to 6 H2 sections
- Updated 8 statistics with 2025-2026 data
- Added 4 citation capsules for AI extraction
- Added FAQ section (5 questions)
- Marked 7 internal linking zones
- Added information gain markers (3 personal experiences)
- Improved readability score from 58 to 67
- Quality score improved from 72 to 86
-->

[... improved content ...]
```

---

## Quality Standards

### Minimum to Publish

- ✅ Overall score: 80+ (Strong band)
- ✅ Zero Critical issues
- ✅ All High priority issues addressed
- ✅ AI detection: "Likely Human-written"
- ✅ Valid Jekyll front matter
- ✅ Correct category and file path

### Exceptional Post

- ✅ Overall score: 90+
- ✅ Content Quality: 27+/30
- ✅ SEO Optimization: 22+/25
- ✅ All 5 categories passing (>70%)
- ✅ Zero Medium or Low issues

---

## Tips & Best Practices

### For Best Quality Scores

1. **Research thoroughly** - 8-12 unique statistics minimum
2. **Use Tier 1-3 sources** - Government, academic, major tech companies
3. **Write answer-first** - 40-60 word opening paragraphs with stats
4. **Add citation capsules** - 40-60 word self-contained passages per H2
5. **Include personal experience** - "When we tested...", real examples
6. **Create FAQ section** - 3-5 questions with stats
7. **Mark internal links** - 5-10 opportunities throughout
8. **Optimize images** - Alt text, credits, proper sizing

### For Different Difficulty Levels

**Beginner Posts:**
- Simpler language (avoid jargon)
- More explanations and definitions
- Shorter paragraphs (40-60 words)
- More visual aids
- Step-by-step breakdowns

**Intermediate Posts:**
- Balanced depth
- Some technical terms explained
- Real-world examples
- Code with comments

**Advanced Posts:**
- Deep technical depth
- Assume domain knowledge
- Complex code examples
- Architecture discussions
- Link to research papers

### For Series Posts

1. **Maintain consistency:**
   - Similar word counts (±500 words)
   - Similar quality scores (±5 points)
   - Consistent readability (±5 Flesch score)
   - Progressive difficulty

2. **Link between parts:**
   - Reference previous parts in intro
   - Link to next part in conclusion
   - Use consistent series naming

3. **Check series integrity:**
   - Verify `_data/series.yml` metadata
   - Ensure `part` numbers are sequential
   - Check all parts have same `series` slug

---

## Troubleshooting

### "Category not found" Error

**Problem:** Category doesn't exist in `_data/categories.yml`

**Solution:** Use one of the 7 valid categories:
- `ai`
- `system-design`
- `backend`
- `devops`
- `frontend`
- `career`
- `tools`

### Low Readability Score

**Problem:** Flesch score below 60

**Solutions:**
- Shorten sentences (target 15-20 words)
- Shorten paragraphs (target 40-80 words)
- Use simpler words
- Add transitions
- Break up complex ideas

### "Likely AI-generated" Detection

**Problem:** AI content detector flags post

**Solutions:**
- Remove AI trigger phrases ("delve into", "leverage", "seamlessly")
- Vary sentence lengths (increase burstiness)
- Add personal experiences and examples
- Use more diverse vocabulary
- Include first-hand observations

### Failed Internal Link Resolution

**Problem:** `[INTERNAL-LINK: ...]` placeholders not resolved

**Solution:** Manually convert to actual links:

Before:
```markdown
[INTERNAL-LINK: complete guide to transformers → pillar page on attention mechanisms]
```

After:
```markdown
For more details, see our [complete guide to transformers](/ai/attention-mechanisms-guide/).
```

---

## Related Documentation

- **Main Guide:** [`.github/prompts/blog.prompt.md`](.github/prompts/blog.prompt.md)
- **Writing Agent:** [`.github/agents/blog-write.md`](.github/agents/blog-write.md)
- **Analysis Agent:** [`.github/agents/blog-analyze.md`](.github/agents/blog-analyze.md)
- **Templates:** [`.github/agents/blog/templates/`](.github/agents/blog/templates/)
- **Project Instructions:** [`.github/copilot-instructions.md`](.github/copilot-instructions.md)
- **Integration Analysis:** [`docs/CLAUDE-BLOG-ANALYSIS.md`](../CLAUDE-BLOG-ANALYSIS.md)

---

**Ready to create your first post?**

```
/blog write "Your Topic Here"
```
