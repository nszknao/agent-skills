---
name: marp-slides
description: >
  Create or edit Marp presentations as Markdown (.md), including slide structure, layout,
  CSS, visual QA, and export. Use when the user explicitly asks for Marp or a Markdown-based
  slide deck. Do not use for PowerPoint, Google Slides, Canva, or Figma deliverables unless
  Marp Markdown is also requested.
---

# Marp Slides

Create or edit presentation slides in Marp Markdown with proper information design, layout, and CSS quality from the start.

## Input

Determine the following before writing slides. Infer them from the user's request and source material when possible; ask only when a missing choice would materially change the result:

- Slide content, purpose, and source material (existing docs, notes, etc.)
- Target audience (executives, engineers, external stakeholders, etc.)
- Presentation length (estimate 1–2 minutes per slide)

## Workflow

### 1. Structure Planning

Before writing slides, confirm:

- **Audience**: Who will see this? (executives / engineers / external, etc.)
- **Slide count**: Derive from presentation time (1–2 min per slide)
- **Story arc**: Title → Current State → Problem → Proposal → Roadmap → Next Actions

### 2. Base CSS Template

Start from the following CSS. Adjust accent colors per project as needed.

```yaml
---
marp: true
theme: default
paginate: true
style: |
  /* ===== Base: top-aligned fixed layout ===== */
  section {
    font-family: 'Helvetica Neue', Arial, 'Hiragino Kaku Gothic ProN', sans-serif;
    font-size: 28px;
    padding: 40px 64px 32px;
    justify-content: flex-start;
  }
  h1 { font-size: 1.5em; color: #1a1a2e; margin: 0 0 4px; line-height: 1.3; }
  h1 + p { margin-top: 0; margin-bottom: 36px; color: #555; }
  h2 { font-size: 1.15em; color: #16213e; margin: 0 0 16px; }
  p, li { font-size: 1em; line-height: 1.6; }
  strong { color: #1a1a2e; }
  /* ===== Tables: always full width ===== */
  table { width: 100%; font-size: 0.85em; border-collapse: collapse; }
  th { background: #f0f2f5; text-align: left; }
  th, td { padding: 10px 14px; }
  /* ===== Title slide ===== */
  section.lead {
    justify-content: center; text-align: center;
    background: #1a1a2e; color: #fff;
  }
  section.lead h1 { font-size: 2.2em; color: #fff; margin-bottom: 16px; }
  section.lead h2 { color: #a0a0c0; font-size: 1.1em; font-weight: 400; }
  section.lead p { color: #666e8a; }
  /* ===== Section divider ===== */
  section.section-divider {
    justify-content: center; background: #16213e; color: #fff;
  }
  section.section-divider h1 { color: #fff; font-size: 2em; }
  section.section-divider h2 { color: #a0a0c0; font-weight: 400; }
  /* ===== .small ===== */
  .small { font-size: 0.75em; color: #888; }
---
```

**CSS rules:**
- Content slides use `justify-content: flex-start` (top-aligned). This keeps h1 position consistent across all slides.
- Only `section.lead` and `section.section-divider` use `justify-content: center`.
- Base font size is fixed at `section { font-size: 28px }`. All other elements use `em` for relative sizing.
- **Explicitly set color on every element inside dark backgrounds** — do not rely on inherited `color`.
- Tables always use `width: 100%`.

**Slide structure rules:**
- Every content slide has an h1 title + a keyline message at the top.
- The keyline is the slide's conclusion — the audience should grasp the point by reading it alone.
- **Keylines must be self-contained**: write out what the problem is or what you're proposing in plain language, not just a framework name or jargon. Multiple lines are fine.
- When the audience is non-technical (e.g., executives), replace all abbreviations (FE/BE/CI/SLO, etc.) with plain terms in both keylines and body text.
- Place visuals (tables, cards, diagrams) below the keyline.

### 3. Information Design

**Choose the best visual format for the data. Do not default to tables.**

| Data type | Recommended format | Why not a table? |
|---|---|---|
| 2–3 row definition list | Bullet list or cards | Table is overkill |
| Before/After comparison | 2-column with red/green | Table weakens the impact of change |
| 3–4 KPIs or metrics | Side-by-side cards | A single-row table is redundant |
| Linear process flow | Horizontal box pipeline | ASCII code blocks are unreadable |
| Stage/progress indicator | Progress bar + highlight | Text can't convey position |
| Cyclic/causal relationship | Node + arrow flow | ASCII art has no visual impact |
| ≤3 category comparison | Color-coded cards (low/med/high) | Table doesn't visualize differences |
| ≥4 rows of structured data | Table (this is appropriate) | — |
| Tasks + completion criteria | Checklist format | Easier to scan than a table |
| ≤3 action items | Card layout (horizontal) | Numbered lists are weak |

See `references/components.md` for CSS/HTML patterns for each component. Read only the section you need.

### 4. Slide Structure Template

```markdown
<!-- _class: lead -->
# Title
## Subtitle

---

# Content Slide (top-aligned)
Body text, tables, or visuals go here

---

<!-- _class: section-divider -->
# Section Name
## Short description (keep to one line)

---

<!-- _class: lead -->
# Next Actions
<!-- Action cards, etc. -->
```

### 5. Quality Checklist

After creating slides, export to PNG for visual review. Prefer an already-installed Marp CLI. If it is unavailable, ask for permission before downloading it with `npx` when the environment requires approval:

```bash
npx @marp-team/marp-cli <file>.md --images png -o /tmp/slides/slide.png --allow-local-files --no-stdin
```

Inspect every exported slide image with the environment's image-viewing capability. Fix clipping, overflow, weak contrast, inconsistent alignment, and unintended wrapping, then export and inspect again until the deck passes the checklist below.

**Layout**
- [ ] All content slide h1 positions are aligned at the top
- [ ] Only lead/divider slides are center-aligned
- [ ] No h1 wraps to a second line

**Font & Size**
- [ ] Base font size is consistent across slides
- [ ] No text is too small to read on a projected screen

**Tables**
- [ ] All tables span full slide width
- [ ] No table text is clipped or truncated

**Color & Readability**
- [ ] All text on dark backgrounds (lead/divider) is legible
- [ ] HTML components on dark backgrounds have explicit color declarations

**Information Design**
- [ ] 2–3 row tables have been replaced with cards or bullet lists where appropriate
- [ ] No ASCII art (code blocks) remains — use HTML components instead
- [ ] Before/After comparisons use 2-column layout, not tables
- [ ] KPIs/metrics use card layout, not single-row tables

**Content**
- [ ] No slide is overloaded with content (watch for overflow)
- [ ] Logical sections are separated by section-divider slides
- [ ] Slide count matches presentation time (1 slide per 1–2 min)

**Terminology & Audience**
- [ ] No jargon inappropriate for the audience (for executives: replace FE/BE/CI/SLO/DDD/WIP, etc.)
- [ ] Keylines alone convey the conclusion (not just framework names or abstract phrasing)

**Facts vs. Assumptions**
- [ ] No generic "common examples" applied without evidence from the actual situation
- [ ] Facts from interviews/data are not mixed with general assumptions
- [ ] Claims like "X is the problem" are backed by evidence that the problem actually occurs
