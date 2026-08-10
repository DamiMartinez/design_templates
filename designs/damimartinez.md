# Damian Martinez (damian_site)

## Meta
- **Source:** https://damimartinez.github.io/
- **Style keywords:** neo-brutalist, hard flat shadows, chunky ink borders, pill stickers, editorial cream/lavender-neutral, OKLCH color system, Jekyll/GitHub Pages
- **Best for:** personal blog, developer portfolio, tech/AI writer site, single-author content site with categorized posts

Note: this is a direct, near-1:1 implementation of [[nick-nisi]] — same token names, same shadow system, same sticker component. Site's own blog post ("How I Redesigned My Website Using an AI-Curated Design Library") confirms it was rebuilt from this design-template library. Differences from the nick-nisi source are called out below; everything else is shared vocabulary.

---

## Colors

OKLCH token system, single fixed accent (no theme picker, no dark mode — light-only, unlike nick-nisi's swappable-accent + dark-mode version).

| Role | Token | OKLCH | Usage |
|------|-------|-------|-------|
| Page background | `--color-paper` | `oklch(97.5% .006 300)` | Body bg |
| Secondary background | `--color-paper-2` | `oklch(95% .012 298)` | Code inline bg, table header bg, hover dividers |
| Card surface | `--color-card` | `oklch(99.6% .004 300)` | Header bg, cards, stickers, buttons |
| Primary text | `--color-ink` | `oklch(23% .03 295)` | Headings, body, borders, shadows |
| Secondary text | `--color-ink-soft` | `oklch(45% .026 295)` | Taglines, excerpts, category labels |
| Muted text | `--color-ink-faint` | `oklch(62% .022 295)` | Dates, metadata |
| Accent (primary) | `--color-tomato` | `oklch(54% .2 348)` | Links, underlines, post-card stripe, star ratings |
| Light accent surface | `--color-marigold` | `oklch(82% .07 348)` | Text selection bg, blockquote bg, favicon/theme-color |
| Deep accent | `--color-grape` | `oklch(45% .19 350)` | Hero name accent word, logo hover |
| Footer background | `--color-footer-bg` | `oklch(16% .018 295)` | Site footer (only dark surface on the site) |
| Footer text | `--color-footer-fg` | `oklch(98% .008 300)` | All text/icons in footer |

**Sticker palette (fixed hex, not OKLCH — hardcoded exceptions):**

| Variant | Hex | Text color |
|---------|-----|-----------|
| `--tomato` | `#C02A86` | footer-fg (white) |
| `--cobalt` | `#2563EB` | footer-fg (white) |
| `--pine` | `#15803D` | footer-fg (white) |
| `--amber` | `#D97706` | ink (dark) |
| `--grape` | uses `--color-grape` token | footer-fg |
| `--marigold` | uses `--color-marigold` token | ink |

**Color philosophy:** same near-monochromatic purple-hued ink system as nick-nisi (hue ~295–300), single vivid magenta/pink accent (hue 348). This instance drops the accent-swap picker and dark mode entirely — it's the single "Magenta" theme, permanently, plus a fixed set of category sticker colors (tomato/cobalt/pine/amber) used to tag post topics (AI, Data Engineering, Python, Agents).

---

## Typography

Identical type system to nick-nisi, same three Google Fonts.

| Role | Font family | Weight | Size (desktop) | Size (mobile) | Notes |
|------|-------------|--------|----------------|----------------|-------|
| Hero H1 | Bricolage Grotesque | 800 | `clamp(48px, 8vw, 72px)` | 48px floor | line-height 1, letter-spacing -0.025em |
| Post H1 (article) | Bricolage Grotesque | 800 | `clamp(32px, 5vw, 56px)` | 32px floor | line-height 1.1 |
| H2 | Bricolage Grotesque | 800 | 32px (28px in `.entry`) | same | letter-spacing -0.01em |
| H3 | Bricolage Grotesque | 700 | 22px | same | |
| H4 | Bricolage Grotesque | 700 | 18px | same | |
| Hero tagline | Bricolage Grotesque | 700 | 20px | same | max-width 52ch |
| Post-card title | Bricolage Grotesque | 700 | 20px | same | underlines tomato on hover |
| Nav links / logo | Bricolage Grotesque | 700–800 | 14–18px | same | |
| Body | Atkinson Hyperlegible | 400 | 17px | same | line-height 1.75 (1.8 in article `.entry`) |
| Eyebrow / label | JetBrains Mono | 400 | 12px | same | uppercase, letter-spacing 0.14em |
| Code / mono | JetBrains Mono | 400 | 0.875em | same | |

**Font source:** Google Fonts, self-preconnected — `Bricolage Grotesque` (variable, 200–800), `Atkinson Hyperlegible` (400/700), `JetBrains Mono` (400/700).
**Line height:** body `1.75` (site-wide), article body `1.8`, headings `1.2` (`1.3` under 640px), display/hero `1`.
**Letter spacing:** H1/hero `-0.025em`, H2 `-0.01em`, eyebrow/mono labels `0.14em`.

---

## Spacing & Layout

- **Grid:** free-flow sections, single-column container
- **Max content width:** `896px` (`.container`, matches nick-nisi's `max-w-4xl`)
- **Section horizontal padding:** `24px` both desktop and mobile
- **Main content vertical padding:** `40px` top / `80px` bottom
- **Hero:** `4rem` (64px) top, `3rem` (48px) bottom padding, `2px` bottom border, `3rem` margin below
- **Hero columns:** `grid-template-columns: 1.4fr 1fr` — same asymmetric split as nick-nisi (content wider than photo), collapses to 1 column under 640px
- **Post grid:** `repeat(auto-fill, minmax(280px, 1fr))`, gap `24px`; collapses to 1 column under 640px
- **Post-card body padding:** `20px`
- **Sticker row gap:** `10px`
- **Base unit:** implicit 4–8px rhythm (no CSS custom property defined for it)
- **Border radius:** cards/media `14px`, hero/about photo `16px`, buttons/stickers/pagination/search input `999px` (full pill), inline code `4px`

---

## Visual Style

### Shadows — identical hard-shadow system to nick-nisi

```css
--shadow-hard-sm: 3px 3px 0 var(--color-ink);
--shadow-hard:    5px 5px 0 var(--color-ink);
--shadow-hard-lg: 8px 8px 0 var(--color-ink);
```

Zero blur throughout. Used on: post cards, media cards, stickers, buttons, pagination pills, search input, blockquotes, code blocks, hero/about portrait photos.

### Borders
Every structural border is `2px solid var(--color-ink)` — header bottom, hero bottom, post/media cards, buttons, stickers, pagination, search input, blockquotes, code blocks, tables, post-header/post-footer dividers. Inline `<code>` uses a thinner `1px` border as the one exception.

### Images
- Hero photo and about-page portrait: square-ish clamp-sized, `border-radius: 16px`, `2px` ink border, `shadow-hard-lg`, tilted (`rotate(-3deg)` hero, `rotate(2deg)` about) — same handmade "pinned photo" treatment as nick-nisi's avatar
- Media covers (movies/books grid): `aspect-ratio: 2/3`, object-fit cover, `2px` bottom border, no radius (grid tile look)

### Icons
Inline SVG, outline style, `stroke-width: 2`, `14×14`–`16×16` — used for footer social links (email, GitHub, LinkedIn, YouTube, Substack, RSS) and the sticker icon slots.

### Texture / background
Flat color only — no gradients, no blur, no glass, no noise. Matches nick-nisi's "zero gradient" rule exactly.

### No dark mode, no theme picker
Unlike the nick-nisi source, this site ships one fixed light theme. No `.dark` class, no `data-accent` swap, no toggle in the header.

---

## Components

### Navigation
- Sticky top (`position: sticky; top: 0; z-index: 100`), `background: var(--color-card)` (near-white, not marigold like nick-nisi), `border-bottom: 2px solid ink`
- Logo: 32×32px circular avatar photo, `2px` ink border, next to "damian_site" wordmark in Bricolage 800, hover → `--color-grape`
- Nav links: Bricolage 700, 14px, `opacity: 0.65` → `1` + tomato underline on hover, `4px 10px` padding, `6px` radius
- 5 links: Home, About, Search, Archive, Movies & Books
- No mobile hamburger — nav simply wraps (`flex-wrap`) on narrow screens; no drawer/JS toggle observed

### Hero / Above the fold
- Two-column asymmetric grid (1.4fr content / 1fr photo), border-bottom 2px, bottom margin 3rem
- H1: two-line stacked name — "Damian" in ink, "Martinez" in `--color-grape` (block-level span, no wavy SVG underline — simpler than nick-nisi's hero)
- Tagline below in Bricolage 700/20px, ink-soft, max 52ch
- 4 topic stickers (AI / Data Engineering / Python / Agents) in tomato/cobalt/pine/amber variants
- Photo: square clamp(180–280px), rounded 16px, ink border, hard-lg shadow, -3° rotation

### Buttons
- **Primary (`.btn-primary`):** filled `--color-ink` bg, `--color-card` text, `2px` ink border, full pill radius, `shadow-hard-sm`, press-state collapses shadow + translates 3px,3px
- No distinct secondary/ghost button class found — stickers and pagination pills fill that role instead

### Cards
**Post card:** `--color-card` bg, 2px ink border, 14px radius, `shadow-hard-sm`, top 12px color stripe (tomato, `2px` bottom border) that signals category, `20px` padding body, title underlines tomato on hover, full-card click target via `::after` overlay, `.tactile` press interaction (shadow collapses, translates 3px on `:active`).
**Media card** (movies/books): same card shell, `2/3` aspect-ratio cover image instead of stripe, star-rating row in tomato with empty/half states via CSS `::before` overlay trick.

### Forms / Inputs
Search input: full-width-ish (`80%`), pill radius `999px`, `2px` ink border, `shadow-hard-sm` → `shadow-hard` (bigger) on focus instead of a focus ring — same tactile-shadow language extended to form state.

### Footer
- Full-bleed dark block, `--color-footer-bg` (near-black purple, same value as nick-nisi's footer), `48px` vertical padding, `2px` ink top border
- Tagline repeats site description, Bricolage 800/20px
- Social row: 6 pill "dark" stickers (transparent bg, footer-fg border/text/shadow, `opacity: 0.8→1` on hover) — Email, GitHub, LinkedIn, YouTube, Substack, RSS, each with inline SVG icon
- Copyright line: JetBrains Mono 12px, `opacity: 0.5`

---

## Interactions & Animation

- **Default transition:** `80ms` for shadow/transform press-states (faster than nick-nisi's 150ms default), `150ms` for opacity/color fades
- **Press/tactile state (`.tactile`, stickers, buttons, pagination):** hard shadow collapses to `none` (or smaller `2px 2px`) + `translate(3px, 3px)` on `:active` — physical "pressed button" feel, applied broadly (cards, stickers, buttons, pagination)
- **Hover effects:** nav links and post-card titles underline in tomato; logo text shifts to grape; footer icons fade from 0.8→1 opacity
- **Search input focus:** shadow grows from `hard-sm` (3px) to `hard` (5px) — no ring/outline
- **No scroll animations, no page transitions, no parallax, no dark-mode toggle animation** — everything is instant and local, consistent with nick-nisi's philosophy

---

## Tone & Personality

Same warm-but-confident developer-brutalist voice as its source: chunky ink borders and flat hard shadows read as intentional and sturdy, not aggressive, softened by the -3°/+2° tilted photos and Atkinson Hyperlegible body copy (an accessibility-first font choice). Slightly more restrained than nick-nisi — no accent picker, no dark mode, no wavy SVG underline — which makes it read a touch more editorial/content-first and a touch less "look what I can theme." Fixed category sticker colors (pink/blue/green/amber) double as a lightweight taxonomy for the AI/data-engineering/Python writing that fills the blog.

---

## Notes & Reuse Tips

- **This is a live case study of reusing [[nick-nisi]]** — same CSS custom property names (`--color-ink`, `--shadow-hard-sm`, etc.), same sticker component markup/CSS almost verbatim, same card/pagination/button shadow language. If you want the nick-nisi neo-brutalist system but leaner (no theme switcher, no dark mode, no JS-dependent `<details>` picker), this is the reference to copy instead — it's the same vocabulary with the optional complexity stripped out.
- **Fixed sticker palette as content taxonomy:** `--tomato/#C02A86`, `--cobalt/#2563EB`, `--pine/#15803D`, `--amber/#D97706` are hardcoded hex (not tokens) used purely to color-code post categories on the stripe/sticker. Cheap, effective way to add scannable variety without a full multi-accent system.
- **Post-card top stripe** reused directly from nick-nisi's suggestion — `h-3`-equivalent (12px) tomato bar with 2px ink border-bottom. Here it's static tomato rather than per-category; swapping the stripe's background per post category (using the sticker hex above) would be a natural one-line upgrade.
- **Press-state pattern (`.tactile`)** is the most reusable primitive: shadow-collapse + `translate(3px,3px)` on `:active`, 80ms transition. Applied uniformly to buttons, cards, stickers, pagination — copy this class wholesale for any neo-brutalist project needing a "physical button" feel.
- **Search input focus state grows the hard shadow instead of adding an outline/ring** — accessible-enough and stays on-brand; worth reusing over default browser focus rings in this style family.
- **No mobile hamburger drawer:** nav just wraps via flexbox. Simpler than nick-nisi's icon-swap toggle, fine for a 5-link nav, would not scale past ~6 links.
- **Built on Jekyll + GitHub Pages**, plain CSS custom properties (no Tailwind, no build step beyond Jekyll's SCSS/CSS pipeline) — the entire system is one `style.css` file with a `:root` token block at the top. Easiest of the OKLCH-brutalist family to port into a non-JS static site.
