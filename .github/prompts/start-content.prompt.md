---
description: 'Use when starting to create new blog content — when you say "create a new post", "write about X", "start a series post", "create standalone article". Confirms content type (series vs standalone), gathers requirements, then starts the research phase. Required before generating any content.'
agent: 'Orchestrator'
tools: ['terminal', 'editFiles', 'fetch']
model: 'claude-sonnet-4.5'
---
# Start Content — Define Before Writing

Before any content generation, we gather requirements and set up the content brief.

**Topic**: ${input:topic:What topic do you want to write about? (e.g., "Transformer Architecture in AI")}
**Content Type**: ${input:content-type:Is this a series post or standalone? (series/standalone)}

---

## Step 1 — Determine Content Type

Ask the developer:

> "Is this content part of a **learning series** or a **standalone post**?
>
> **A) Series Post** — Part of a sequential learning path (requires series ID and part number)
>
> **B) Standalone Post** — Independent article not part of any series"

Wait for the developer to choose **A** or **B**.

---

## Step 2A — (If Series Post) Gather Series Information

Ask the following questions:

1. **"Which series is this for?"** 
   - Check `_data/series.yml` for existing series
   - Show list of available series
   - If new series, collect: series ID (slug), title, description, category, difficulty

2. **"What part number is this?"**
   - Check `_data/series.yml` for last part number
   - Suggest next sequential number
   - Ensure no gaps in part numbers

3. **"What is the specific topic for this part?"**
   - Get detailed topic description
   - Examples: "Self-attention mechanism", "Load balancing strategies"

---

## Step 2B — (If Standalone Post) Gather Post Information

Ask the following questions:

1. **"What category does this belong to?"**
   - Must be one of: ai, system-design, backend, devops, frontend, career, tools
   - Show category descriptions from `_data/categories.yml`

2. **"What difficulty level?"**
   - beginner, intermediate, or advanced

3. **"What is the topic?"**
   - Get detailed topic description

---

## Step 3 — Create Content Brief

Create a content brief document at `docs/series/CONTENT-{YYYY-MM-DD}-{slug}.md`:

```markdown
# Content Brief: {Title}

**Status**: 📝 In Progress
**Created**: {timestamp}
**Category**: {category}
**Type**: {series/standalone}
{If series: **Series**: {series-title} - Part {N}}
**Difficulty**: {difficulty}

---

## Phase 1: Requirements ✅

### Topic
{detailed topic description}

### Target Audience
{who is this for - based on difficulty and category}

### Scope
{what will be covered}

### What's Out of Scope
{what won't be covered}

---

## Phase 2: Research 🔍

**Status**: [ ] Not Started

{Will be filled by Research Agent}

---

## Phase 3: SEO Planning 📊

**Status**: [ ] Not Started

{Will be filled by SEO Planner Agent}

---

## Phase 4: Writing ✍️

**Status**: [ ] Not Started

{Will be filled by Writer Agent}

---

## Phase 5: Formatting & Validation ✅

**Status**: [ ] Not Started

{Will be filled by Formatter Agent}

---

## Final Output

**Post File**: `_posts/{category}/{date}-{slug}.md`
**Status**: [ ] Not Published
```

---

## Step 4 — Mark Phase 1 Complete

Mark Phase 1 as complete in the content brief:

```markdown
## Phase 1: Requirements ✅

**Status**: [x] Complete
```

---

## Step 5 — Hand Off to Research Phase

Present to the developer:

> "✅ Content brief created at `docs/series/CONTENT-{date}-{slug}.md`
>
> **Phase 1 (Requirements)** complete.
>
> **Next step**: Run `/research-topic` to gather sources and insights.
>
> Or use agent: `@research` with the content brief path."

---

## Output

- Content brief document created
- Phase 1 marked complete
- Ready for research phase
