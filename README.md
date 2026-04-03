# /reviewdesign — UI/UX Design Review Skill for Claude Code

A professional UI/UX design review skill that analyzes your code, screenshots, or Figma designs and provides actionable feedback based on **60+ evidence-based rules** curated from top UI/UX designers.

## What it does

`/reviewdesign` acts as a senior design reviewer. It:

- Analyzes your UI code, screenshots, Figma URLs, or live URLs
- Identifies issues across 8 categories (hierarchy, typography, color, spacing, components, motion, UX, anti-patterns)
- Provides a scored report with specific problems, current code, and recommended fixes
- **Never modifies your code** — only reviews and suggests. You decide what to fix

## Example output

```
## Design Review: dashboard.tsx

### Score: 6/10

Clean layout foundation but several hierarchy and spacing issues hurt readability.

---

### CRITICAL Issues

#### Broken visual hierarchy
- Rule: Visual hierarchy (3 levels) [10/21]
- Problem: Heading (18px) and body (16px) are too close in size — no clear L1/L2 distinction
- Current:  font-size: 18px / font-size: 16px
- Recommended:  font-size: 32px; letter-spacing: -1px / font-size: 16px
- Why: Users can't scan the page — everything looks equally important

### What's Done Well
- Consistent icon set (Lucide)
- Good use of semantic colors for status badges
- Clean single-column form layout
```

After the review, just say **"fix these issues"** and Claude will apply the changes.

## Installation

### Option A: Copy into your project (recommended)

Copy the `.claude/skills/reviewdesign/` folder into your project root:

```
your-project/
├── .claude/
│   └── skills/
│       └── reviewdesign/
│           ├── SKILL.md          # Main skill definition
│           └── reference.md      # Knowledge base (50+ rules)
├── src/
└── ...
```

### Option B: Install globally (available in all projects)

Copy to your global Claude Code config:

**macOS / Linux:**
```bash
cp -r .claude/skills/reviewdesign ~/.claude/skills/
```

**Windows:**
```powershell
Copy-Item -Recurse .claude\skills\reviewdesign $env:USERPROFILE\.claude\skills\
```

## Usage

In Claude Code, type:

```
/reviewdesign path/to/file.tsx
```

Or just:

```
/reviewdesign
```

...and then paste a screenshot, share a Figma URL, or let it scan your project for UI files.

### Workflow

1. `/reviewdesign` — get the review report
2. Read the report, decide what matters
3. "Fix these issues" or "Fix only critical and high" — Claude applies the changes
4. You can also be specific: "Fix items 2 and 5" or "Fix everything except animations"

## What it checks

| Priority | Category | Examples |
|----------|----------|---------|
| CRITICAL | Visual Hierarchy | 3 levels of importance, squint test, de-emphasis |
| HIGH | Typography | Font sizes/weights limits, line height, letter spacing, text width |
| HIGH | Color | 60/30/10 rule, WCAG contrast, semantic colors, dark mode |
| HIGH | Spacing & Layout | 8pt grid, relationship proximity, white space |
| MEDIUM | Components | Buttons, icons, border radius, cards, empty states, navigation |
| MEDIUM | Motion | Purposeful animation, micro-interactions, loading states |
| MEDIUM | UX Principles | Content-first, affordance, progressive disclosure, copy quality |
| IMMEDIATE | Anti-patterns | Emojis as icons, AI-chosen colors, missing states, stacked effects |

## Knowledge base

The skill is backed by a curated knowledge base (`reference.md`) with 60+ rules covering typography, color systems, spacing, visual hierarchy, components, motion design, UX principles, and common anti-patterns.

**Top 10 most critical rules:**

| Rule | Why it matters |
|------|---------------|
| 60/30/10 color distribution | Broken = everything fights for attention |
| Visual hierarchy (3 levels) | Broken = user can't scan the page |
| Contrast & WCAG accessibility | Broken = users literally can't read |
| 8-point grid spacing | Broken = feels "off" and unprofessional |
| Max 4 font sizes, 2 weights | Broken = messy, inconsistent typography |
| White space is active | Broken = cramped, overwhelming layout |
| Clear action-based button labels | Broken = users don't know what happens on click |
| Line height ratios | Broken = text feels too tight or too loose |
| Every interaction needs a response | Broken = "did my click work?" anxiety |
| Letter spacing by context | Missing = headlines look amateur, CTAs get skipped |

## Key principles

- **Evidence-based only** — every rule traces back to the knowledge base, nothing invented
- **Review, don't break** — analyzes and suggests, never auto-edits
- **Prioritized by impact** — critical issues first, polish last
- **Always acknowledges good work** — not just a list of complaints
- **Responds in your language** — write in English, get English; write in Russian, get Russian

## License

MIT
