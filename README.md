# Review Website — UI/UX + Marketing Review Skills for Claude Code

Two complementary Claude Code skills for reviewing websites and landing pages. Drop them into any project and run a senior-level audit without leaving your editor.

| Skill | What it reviews | Knowledge base |
|-------|-----------------|----------------|
| [`/reviewdesign`](.claude/skills/reviewdesign/) | UI/UX — visual hierarchy, typography, color, spacing, components, motion, accessibility | 60+ evidence-based rules from top UI/UX designers |
| [`/reviewmarketing`](.claude/skills/reviewmarketing/) | Marketing & conversion — offer, headlines, CTAs, structure, social proof, trust, meaning | 159 приёмов по методологии «Смыслоген» (7 категорий + ТОП-20) |

Both skills **review only** — they produce a structured report with priorities (CRITICAL → LOW), concrete before/after examples, and rule-level citations. You decide what to fix.

---

## `/reviewdesign` — UI/UX audit

Acts as a senior design reviewer. Analyzes your UI code, screenshots, Figma URLs, or live URLs and scores it across 8 categories (hierarchy, typography, color, spacing, components, motion, UX, anti-patterns).

### Example output

```
## Design Review: dashboard.tsx

### Score: 6/10

Clean layout foundation but several hierarchy and spacing issues hurt readability.

### CRITICAL Issues

#### Broken visual hierarchy
- Rule: Visual hierarchy (3 levels)
- Problem: Heading (18px) and body (16px) are too close in size — no L1/L2 distinction
- Current:  font-size: 18px / font-size: 16px
- Recommended:  font-size: 32px; letter-spacing: -1px / font-size: 16px
- Why: Users can't scan — everything looks equally important
```

### What it checks

| Priority | Category | Examples |
|----------|----------|----------|
| CRITICAL | Visual Hierarchy | 3 levels of importance, squint test, de-emphasis |
| HIGH | Typography | Font sizes/weights limits, line height, letter spacing, text width |
| HIGH | Color | 60/30/10 rule, WCAG contrast, semantic colors, dark mode |
| HIGH | Spacing & Layout | 8pt grid, relationship proximity, white space |
| MEDIUM | Components | Buttons, icons, border radius, cards, empty states |
| MEDIUM | Motion | Purposeful animation, micro-interactions, loading states |
| MEDIUM | UX Principles | Content-first, affordance, progressive disclosure |
| IMMEDIATE | Anti-patterns | Emojis as icons, AI-chosen colors, stacked effects |

---

## `/reviewmarketing` — маркетинг-аудит по методологии «Смыслоген»

Senior маркетолог-аудитор. Проверяет сайт/лендинг на смысловые и конверсионные дыры: заголовки, тексты, призывы (CTA), структура блоков, соцдоказательства, доверие, визуальные акценты. Выдаёт балл 0–10, отчёт с приоритетами CRITICAL → LOW, ссылки на конкретные приёмы из базы знаний и ТОП-20 экспресс-чек.

### Что проверяет (159 приёмов, 7 категорий)

| Раздел | Приёмов | Что закрывает |
|--------|---------|---------------|
| Текст | 22 | Заголовки, подзаголовки, конкретика, сегментация, двусмысленности |
| Призывы | 17 | CTA-кнопки, формы, мессенджеры, калькуляторы, персонализация |
| Структура | 20 | Порядок блоков, первые 3 экрана, «Проблема → Решение → Доказательства» |
| Соцдоказательства | 12 | Отзывы, рейтинги, цифры масштаба, до/после, эксперты |
| Доверие | 15 | Гарантии, кейсы, ответственные, реквизиты, сертификаты, медиа |
| Визуал | 14 | Реальные фото, инфографика, контраст CTA, цветовые якоря |
| Другое | 19 | Меню, слайдер, бейджи, чат, таймер, тарифы, варианты оплаты |

Плюс раздел **ТОП-20** — кураторская подборка самых критичных приёмов для экспресс-ревью.

### Пример отчёта

```
# Маркетинг-ревью: landing.tsx

Балл: 5/10
Категория зрелости: Рабочий

🔴 CRITICAL

### Абстрактный заголовок первого экрана
- Приём: «Заголовок с числом вместо абстракции» (раздел «Текст»)
- Что сейчас: > «Эффективное похудение»
- Почему это теряет заявки: Conductor — заголовки с цифрами на 36% более кликабельные
- Как переделать: > «Минус 6 кг за 30 дней по программе питания»
```

---

## Installation

### Option A: Copy into your project (recommended)

Copy the `.claude/skills/` folder into your project root:

```
your-project/
├── .claude/
│   └── skills/
│       ├── reviewdesign/
│       │   ├── SKILL.md
│       │   └── reference.md
│       └── reviewmarketing/
│           ├── SKILL.md
│           └── reference.md
├── src/
└── ...
```

### Option B: Install globally (available in all projects)

**macOS / Linux:**
```bash
cp -r .claude/skills/reviewdesign ~/.claude/skills/
cp -r .claude/skills/reviewmarketing ~/.claude/skills/
```

**Windows:**
```powershell
Copy-Item -Recurse .claude\skills\reviewdesign $env:USERPROFILE\.claude\skills\
Copy-Item -Recurse .claude\skills\reviewmarketing $env:USERPROFILE\.claude\skills\
```

---

## Usage

In Claude Code, type one of:

```
/reviewdesign path/to/file.tsx
/reviewmarketing https://your-site.com
```

Or just `/reviewdesign` / `/reviewmarketing` without arguments — the skill will ask what to review (file, URL, screenshot, or Figma link).

### Workflow

1. Run the skill → get a priority-sorted report
2. Read it, decide what matters
3. Say "fix CRITICAL and HIGH" → Claude applies the changes
4. Or target specific items: "Fix items 2 and 5", "Fix everything except motion"

### Which skill to pick?

- Launching the page, worried about **conversion and meaning** → `/reviewmarketing`
- Polishing **look & feel**, accessibility, components → `/reviewdesign`
- Want both? Run them sequentially — they don't overlap. `/reviewdesign` won't touch copy/offer/CTA labels, and `/reviewmarketing` won't touch spacing/fonts/accessibility.

---

## Key principles (both skills)

- **Evidence-based only** — every recommendation traces back to the knowledge base; nothing invented
- **Review, don't break** — analyzes and suggests, never auto-edits
- **Prioritized by impact** — CRITICAL first, polish last
- **Always acknowledges good work** — not just a list of complaints
- **Responds in your language** — English → English; Russian → Russian

---

## License

MIT
