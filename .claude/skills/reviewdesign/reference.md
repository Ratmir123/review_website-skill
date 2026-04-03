# UI/UX Design Knowledge Base — Reference

> Curated from expert UI/UX designer video breakdowns and best practices.
> This file is the SINGLE SOURCE OF TRUTH for the reviewdesign skill. Do not invent rules outside this file.

---

## 1. TYPOGRAPHY

### 1.1 Font Selection & Pairing
- **Font = brand decision**. Arial/Times New Roman = amateur signal.
- **Anchor font** = headline font, sets personality. Pick first, then find support fonts.
- **3 levels**: L1 = one font family. L2 = super families (Source Sans/Serif/Code, DM Sans/Serif, Tato Sans/Slab). L3 = cross-foundry combos (advanced).
- **Pairing rule**: same world, different roles. Don't pair too-similar fonts (Georgia + Times = bad).
- **Variable fonts** with many weights = precise attention control.
- **Resource**: fontsinuse.com for pairing inspiration.

### 1.2 Font Sizes & Weights
- **Max 4 font sizes, 2 font weights**. More = messy.
- Heading, subheading, body, caption — usually enough.
- Recommended: semi-bold headings, regular body.
- Display fonts for attention; legible fonts for reading. >7-10 words = legibility priority.
- **Landing pages**: up to 6 font sizes OK, large range allowed. **Dashboards**: max ~24px, smaller range due to info density.
- You'll **rarely need more than one font** for any design. Find a nice sans-serif and stick to it.

### 1.3 Line Height
- **Headings**: 1.0-1.3x font size (Spotify production: exact 1:1 on headers).
- **Body**: 1.3-1.5x font size.
- Larger text = smaller ratio.
- Line height acts as implicit margin — can reduce explicit spacing needs.

### 1.4 Letter Spacing
- **Headlines**: negative (-1px to -3px) for scanability.
- **Body**: 0px default — don't touch.
- **CTAs**: positive (+1px to +2px) — slows users down to read.
- Negative spacing ONLY on large headings — kills readability on small text.

### 1.5 Text Width
- Body: **50-75 characters per line** (~600px desktop).
- Long lines = intimidating, users skip, fewer conversions.
- Break every 2-3 sentences.

### 1.6 Text Alignment
- >3 lines = left align always.
- Short headings = center OK.
- **NEVER mix** center heading + left body (or vice versa).

---

## 2. COLOR

### 2.1 The 60/30/10 Rule
- **60%** neutral (white, light gray, dark bg).
- **30%** brand/complementary.
- **10%** accent — **reserve for CTAs**.
- Everything screams = nothing gets attention.
- Tints/shades of ONE color > multiple colors.

### 2.2 Contrast & Accessibility
- High contrast text always.
- Checker tools: Figma "Contrast" plugin, coolers.co.
- **WCAG compliance** required. Test on different devices.
- Brand color fails WCAG? Darken until pass.

### 2.3 Neutral Balance
- Backgrounds stay in background — no bright bg colors.
- Light: neutral gray bg + white foreground.
- Dark: darker bg + slightly lighter foreground.
- **Brand-tint neutrals**: hint of brand color in gray (Headspace: orange-tinted cards).
- Sometimes border-only (no bg) is cleanest.

### 2.4 Avoid Pure Black & White
- Dark gray > pure black for secondary text.
- Professional UIs use gray shades, not #000000.
- Dark mode: pure white ONLY for most important elements.
- Separates amateurs from pros.

### 2.5 Extending Brand Palette
- **Analogous**: rotate on wheel (purple -> blue, pink).
- **Complementary**: across wheel (purple -> yellow).
- Real examples: Mailchimp (yellow + turquoise), Airbnb (bright + deep pink).

### 2.6 Semantic Colors
- **Red** = destructive (delete, error, danger/urgency). Always. Even if not brand color.
- **Green** = success.
- **Blue** = trust. **Yellow** = warning.
- Keep red/green regardless of brand palette.
- Don't use brand color for destructive actions.
- Use color for **purpose, not decoration**. Every colored element should have a reason.

### 2.6b Quick Color Palette Method
- Start with black or white bg. Opposite for text.
- Pick **one main color** (brand) for buttons, objects, attention.
- Find **opposite/complementary** for highlights, alerts, links, hover.
- **Main + secondary = gradient** for vibrant accent areas.
- Use hex color tool for lighter/darker tints to extend variance.
- **Reuse theme throughout** for consistency — same palette, every section.
- Shortcut: find a site you admire, extract their palette, adapt it.

### 2.7 Element States
- **Hover**: lighter/brighter.
- **Active/pressed**: darker.
- **Disabled**: desaturated + light gray + muted text.
- **Mobile**: no hover — press = slightly darker ("pressing into").

### 2.8 Dark Mode
- NOT inverse of light. Separate palette.
- Brighten borders/cards (dark needs bigger differences).
- Light gray for body text (not white — easier on eyes).
- Desaturate brand colors slightly.
- **Lower border contrast** — light borders on dark bg create too much contrast; dim them.
- **Lighter card than background** to create depth (no shadows in dark mode — elevation = lightness).
- **Chips/badges**: dim down saturation + brightness, flip for text to create hierarchy.
- Tons of flexibility with **deep purples, reds, greens** — not just navy or gray.
- **Color ramp**: lighten brand for bg tints, darken for text colors — subtle way to incorporate brand.

### 2.9 Shadow Colors
- Match shadow to background behind element.
- Purple bg -> purple-tinted shadow, NOT gray.
- Soft: low opacity, high blur, brand-tinted.
- Default Figma shadows = amateur.
- **Realistic shadows**: mix darker+shorter shadow with lighter+longer shadow. Never use single flat shadow.

### 2.10 Grayscale-First Validation
- Desaturate to test. If hierarchy breaks without color -> design is broken.
- Color enhances, doesn't carry.
- Never let AI choose colors.

### 2.11 Color Format & Palette Construction
- **Use HSL or OKLCH** instead of hex/RGB — code should make visual sense.
- HSL: Hue (0-360), Saturation (0-100), Lightness (0-100). Easy math for harmonic shades.
- **OKLCH** (Tailwind v4 default): more perceptually uniform than HSL, better saturation across lightness range.
- HSL biggest issue: dark/light shades lose saturation. OKLCH increments look more natural.
- Create shades by **varying only lightness** while keeping hue+saturation constant.
- Minimum palette: 3 background shades + 2 text shades + 1 brand + 1 accent = functional UI.

### 2.12 Background Color Hierarchy (Elevation System)
- **Dark mode**: base 0% lightness, cards/surfaces 5%, raised/important elements 10%.
- **Light mode**: subtract from 100 (base 100%, cards 95%, raised 90%), then adjust visually.
- **Lighter = closer to user = more important.** Only use lightest shades for important, raised elements.
- Name variables by role (BG-dark, BG-light), not by mode — BG-dark is always darkest shade.
- Light comes from top: lightest surface should be the topmost/raised element.

### 2.13 Text Color Shades
- **Headings**: high contrast but NOT 100% white in dark mode — too harsh on eyes. Use ~90-95%.
- **Body/secondary text**: muted shade — still legible, just not in your face.
- Dark mode: heading ~90% lightness, body ~65-70%.
- Light mode: heading ~10-15% lightness (dark gray), body ~35-40%.
- Every text color must serve a hierarchy purpose — no random grays.

### 2.14 Borders, Gradients & Highlights
- **Border**: clearly visible but not distracting. Match to nearby background shade.
- **Gradient**: use background color shades for subtle gradients. Reveal full gradient on hover.
- **Top highlight border**: slightly lighter color on top edge = "light from above" effect. Sells depth.
- Light mode: border can match background to "blend in" — depth comes from shadow instead.
- **Hue + saturation on neutrals** = brand personality. Cool+vibrant or warm+neutral — adjust to project.

### 2.15 Personalization & Contextual Color
- Use color to differentiate user engagement levels (new, returning, power-user).
- Category screens: **soft monochrome backgrounds + clean isolated images** for instant scanning.
- Color graphics on category cards help users parse options in seconds.
- Answers questions before they arise — color as wayfinding, not decoration.

---

## 3. SPACING & LAYOUT

### 3.1 The 8-Point Grid
- All values divisible by **8** (or 4).
- 25px -> 24px. 11px -> 12px.
- **Within groups**: base value (e.g., 16px).
- **Between groups**: 2x base (e.g., 32px).
- **Between sections**: consistent larger value (e.g., 104px).

### 3.2 White Space
- Active element, not passive.
- "More white space than you think."
- Break text into chunks.
- Start with MORE spacing, reduce until happy.

### 3.3 Relationship Proximity
- Related = closer. Unrelated = farther (Gestalt proximity).
- Heading->body below = 1x. Heading->body above = 2x.
- Same shape/size/color = perceived as group (Gestalt similarity).

### 3.4 Layout Patterns
- 12-column grid = **guideline, not law**. Custom landing pages often don't align to columns — that's fine.
- Structured pages (galleries, blogs, repeating content) benefit from grids for responsive behavior.
- **Responsive grid breakpoints**: 12 columns desktop, 8 columns tablet, 4 columns mobile.
- Top-to-bottom, left-to-right flow.
- Nav at top, CTA prominent.
- Mix section styles for scroll engagement.
- Dashboards use grids more strictly.
- 4-point grid: everything a multiple — not because it looks better, but because you can always split in half = consistency.

### 3.5 Single Column Forms
- Side-by-side fields = bad.
- Exception: country code + phone.
- Single column = spacious, clear flow.

### 3.6 Responsive / Mobile
- Must adapt to any screen.
- **Thumb zone**: primary CTAs bottom of mobile screen.
- Buttons large enough to tap.
- No lorem ipsum — use real content.
- REM units (px / 16) for responsive.

---

## 4. VISUAL HIERARCHY

### 4.1 Three Levels
- **L1**: biggest/boldest — grabs attention.
- **L2**: secondary — visible, doesn't compete.
- **L3**: details — for deep divers.
- F-pattern outdated. Use visual weight.

### 4.2 Four Mechanisms
1. **Large text** — noticed first.
2. **Animation/movement** — yanks attention.
3. **Color contrast** — saturated vs neutral pulls eye.
4. **Heavy font weight** — bold pops.

### 4.3 Opacity for Hierarchy
- Material Design: 87% = high, 60% = medium.
- Headlines 100%, subheadings ~70%, supporting ~60%.
- Creates hierarchy without changing font size.

### 4.4 De-emphasize to Emphasize
- To make X stand out, turn down everything else.
- Don't just crank primary — reduce secondary.
- Zoom out test: key elements scannable from distance?
- Not all H1s need same size.

### 4.5 Squint Test
- Squint until blurry. Headline and CTA must pop.
- If not -> hierarchy broken.
- Use after every design pass.

---

## 5. COMPONENTS & PATTERNS

### 5.1 Buttons
- Adequate padding (tappability + legibility). **Padding guideline**: width = 2x height.
- **Title case**, not UPPERCASE.
- Clear labels: "Send Reset Link" not "Next" / "Submit" / "Let's Do This".
- **Ghost buttons** = buttons without background until hover. Common for secondary CTA next to primary. Users may miss them if used as primary.
- Brand color for **primary CTA only**.
- Border radius matches surrounding UI.
- **4 states minimum**: default, hovered, active/pressed, disabled. Sometimes loading (spinner).
- Can be built with or without icons.
- Inner + outer shadows = raised, tactile feel.

### 5.1b Signifiers
- Good UI **signifies** how things work without instructions.
- Container around items = they're related/grouped.
- Highlighted/selected state = active item.
- Grayed out text = inactive (clicking won't do anything).
- Button press states, active nav highlights, hover states, tooltips = all signifiers.
- **If user has to guess what's clickable or what state something is in, signifiers are missing.**

### 5.2 Icons
- ONE icon set, ONE style. Stick with it.
- Exception: filled for active nav state.
- Must be recognizable without labels.
- Recommended: **Phosphor, Lucide, Untitled UI, Huge Icons, Feather**.
- Different styles OK only if visually separated.
- **Emojis are NOT icons.** Replace with proper libraries.
- **Icon sizing**: match the line-height of adjacent text. If body text has 24px line-height, icons should be 24px. Then tighten gap.
- Most icons are too large by default — size down to match text metrics.

### 5.3 Border Radius
- **Nested**: inner = outer - padding. Card 16px, 4px padding -> image 12px.
- Deeper nesting = smaller radius.
- Consistent across similar components.

### 5.4 Cards
- Light mode: bg color. Dark mode: borders.
- Selectable cards > text lists/dropdowns.
- Reduce noise: triple-dot menus, centered dates.

### 5.5 Charts
- Always: legend, labels, axis values, grid lines, date selector.
- Gray out incomplete data.
- Readability > aesthetics.
- Flat bar tops (rounded = hard to read values).
- Show comparison data. Offer drill-down.
- Stick to line, bar, doughnut. Don't invent types.

### 5.6 Navigation
- Simple, grouped by relevance.
- Icons + short titles. Rarely-used items at bottom.
- Collapsible: icons work alone.
- Active state indicator.

### 5.7 Modals, Popovers, Toasts
- **Popover**: simple, non-blocking.
- **Modal**: complex, blocking (confirm/cancel).
- **New page**: permanent/large content.
- **Toast**: confirm actions without blocking.

### 5.8 Empty States
- NEVER blank. No "You have no projects" dead ends.
- Include: explanation + guidance + CTA ("Create New Project").
- Educate, guide, encourage.

### 5.9 Dashboards
- Sidebar = spine (nav, profile, search).
- Most important data at top.
- Smaller fonts, tighter spacing than landing pages.
- Strict grids. Tables need search/filter/sort.
- Optimistic UI (update instantly, assume success).

---

## 6. MOTION & EMOTIONAL DESIGN

### 6.1 Animation
- Personality: rotate, fly in, bob, slide — not just fade.
- **Purposeful** motion adds clarity, not flash.
- Buttons: always hover/click animation.
- No scroll-jacking.
- Parallax in spacious margins.
- Overusing = worse than none.

### 6.2 Micro-interactions & Interaction States
- Button press -> gray out / spinner for loading.
- Save -> fill icon + notification dot.
- **"Did my click register?"** — user must never wonder.
- Success -> bounce, glow, sparkle (not just green check).
- Celebrate small wins.
- **Copy action**: chip/toast slides up to confirm. Not just visual state change — clear micro-interaction.
- **Input states are critical**: focus (highlight border), error (red border + message), warning (optional issues), success.
- **Loading**: spinners when data fetching, skeleton screens for layout.
- **Success messages** when action completes. **Every interaction needs a response.**
- Micro-interactions range from practical to playful — match to brand personality.

### 6.3 Emotional Design
- Usefulness isn't enough — feelings matter.
- Duolingo: animations -> DAU 14.2M to 34M.
- Phantom wallet: animations -> #2 US utility app.
- Revolut: tactile charts, 3D flip -> premium feel.
- Every micro-interaction = trust signal. Polish = trust.

### 6.4 Emotional Tactics
- Micro-interactions on repeated behaviors.
- Mascots/characters for encouragement.
- Progress: streaks, levels, completion bars -> momentum.
- Intimidating domains (finance, health): friendly visuals + warm details.
- First impression/onboarding = critical for trust.
- Subtle animation in security flows = trust.

### 6.5 Playfulness
- Illustrations, doodles without clutter.
- Draw attention to center, trail at edges.
- Match vibe: professional -> realistic images, fun -> blobs/colors.
- 404 pages = perfect for personality.
- "We sweat the details" > "We take pride in our attention to detail."

### 6.6 Progressive Disclosure
- Show what's needed now, reveal more on demand.
- "Load more" > infinite scroll (user control + footer).
- Collapsible sections. Search bar icon -> expands on click.

---

## 7. UX PRINCIPLES

### 7.1 User Intent First
- What does user need to DO? Not what should layout look like.
- List tasks -> rank importance -> hierarchy matches.
- Primary = most contrast. Secondary = less.
- "If design doesn't consider conversion, it's useless."

### 7.2 Content-First
- Content drives design, not reverse.
- Display based on user interaction patterns.
- Edge cases: long names -> truncate, icons on bright images -> contrast circle.
- No lorem ipsum.

### 7.3 Personalization & Contextual UX
- Adapt interface to **user engagement level** (new, returning, power-user) — show relevant content, not identical screen for everyone.
- **Smart search**: recent queries, popular items, personal recommendations under search bar reduce friction.
- **Input method depends on context**: sliders/wheels for approximate actions, text fields/steppers for precise or repeated tasks.
- **Order/status tracking** reduces stress: confident messaging, clear delivery details, visual icons, humanizing elements (photos, names), history timeline.
- Great design **answers questions before they arise** — creates sense of control and confidence.

### 7.4 Affordance & Conventions
- Mental models: account top-right, Escape closes modals, nav at top.
- Work WITH expectations.
- "Intuitive" = established patterns + small flair.
- Don't reinvent — check Dribbble/Behance first.

### 7.5 Conversion
- **Clarity**: who, what, why in 5 seconds.
- **Scannability**: people scan, not read.
- **Motivation**: speak to heart, not features.
- 80% leave after first fold -> make it crystal clear.
- Reduce interaction cost: expose content directly.

### 7.6 Copy & Labels
- Clear, short, action-based.
- Natural language > jargon.
- Don't repeat same word in heading + label.
- Button text = actual action. "Send Reset Link" not "Submit."

### 7.7 Accessibility
- WCAG contrast compliance.
- Keyboard navigation (tab through without mouse).
- Don't rely on color alone (add icons, labels, patterns).
- Alt text. One H1 per page. Thumb zones on mobile.

### 7.8 Design Validation
- **Squint test**: blur -> headline + CTA pop?
- **Scroll backward**: bottom to top reveals issues.
- **Grayscale test**: does hierarchy work without color?
- **Test on real devices**.

### 7.9 Vibe-Coded / AI Anti-patterns
- Emojis as icons
- AI-chosen bright clashing colors
- Duplicate KPIs shown 3x on same page
- Gradient profile circles with letters
- Sparse modals with too much empty space
- No analytics pages
- Landing pages without graphics = zero trust
- AI-generated over-complex navigation
- Stacked effects (shadow + glow + gradient)
- No empty/loading/error states

---

## 8. DESIGN CONCEPTS

### 8.1 Star of the Show
- ONE standout element per page that makes people feel.
- Connected to brand, not just cool.
- Build from a "seed" question. Everything supports the star.

### 8.2 Visual Rhyming
- Repeat elements (shapes, colors, textures) across site.
- Echo star components in buttons, icons, cards.
- Creates "one universe" cohesion.

### 8.3 Depth & Texture
- Subtle texture (noise, dots) -> content sits ON something.
- Glass effects, soft shadows.
- Radial gradient behind text over textured backgrounds.
- Corner gradients for color without loudness.
- NEVER compete with content.

### 8.4 Design Systems
- Define: spacing, typography, colors, interactions.
- Lean = flexible. Large = deeply defined.
- Shared language, not just visual consistency.
- Master rules, then intentionally break them.

### 8.5 Images
- Match image colors to site palette.
- People looking toward key content (eyes guide gaze).
- WebP, ~300KB max. Rule of thirds.
- Export at exact needed dimensions.
- Natural expressions > staged stock.

### 8.6 Image Overlays
- Text over images without overlay = unreadable. Never leave it raw.
- **Full-screen overlay**: darkens image but hides it too much.
- **Linear gradient overlay**: shows image at top, smoothly fades to readable bg for text. Best balance.
- **Progressive blur + gradient**: modern look. Blur on top of gradient for extra polish.
- If shadow is the first thing you notice, you're not using it right.

---

## TOP 10 MOST CRITICAL RULES

| # | Rule | Impact |
|---|------|--------|
| 1 | 60/30/10 color distribution | Broken = everything fights for attention |
| 2 | Visual hierarchy (3 levels) | Broken = user can't scan the page |
| 3 | Contrast & WCAG accessibility | Broken = users literally can't read |
| 4 | 8-point grid spacing | Broken = feels "off" and unprofessional |
| 5 | Max 4 font sizes, 2 weights | Broken = messy, inconsistent typography |
| 6 | White space is active, not passive | Broken = cramped, overwhelming layout |
| 7 | Clear action-based button labels | Broken = users don't know what happens on click |
| 8 | Line height ratios | Broken = text feels too tight or too loose |
| 9 | Every interaction needs a response | Broken = "did my click work?" anxiety |
| 10 | Letter spacing by context | Missing = headlines look amateur, CTAs get skipped |
