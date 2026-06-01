# Nick Nisi

## Meta
- **Source:** https://nicknisi.com/
- **Style keywords:** neo-brutalist, bold typography, hard shadows, playful stickers, accessible, warm, OKLCH color system, swappable accent themes
- **Best for:** developer portfolio, personal blog, DX tooling site, personal brand site, technical writer portfolio

---

## Colors

The site uses a semantic OKLCH-based token system with **6 swappable accent palettes** (default: Magenta). Each accent swaps `--color-tomato`, `--color-grape`, and `--color-marigold` via `data-accent` on `:root`.

| Role | Token | OKLCH | Usage |
|------|-------|-------|-------|
| Page background | `--color-paper` | `oklch(97.5% .006 300)` | Body bg — very light lavender-neutral |
| Secondary background | `--color-paper-2` | `oklch(95% .012 298)` | Hover surfaces, subtle separators |
| Card surface | `--color-card` | `oklch(99.6% .004 300)` | Cards, panels, avatar bg |
| Primary text | `--color-ink` | `oklch(23% .03 295)` | Headings, body text, borders (near-black purple-tinted) |
| Secondary text | `--color-ink-soft` | `oklch(45% .026 295)` | Subheadings, card excerpts, nav labels |
| Muted text | `--color-ink-faint` | `oklch(62% .022 295)` | Captions, dates, metadata |
| Accent (default: magenta) | `--color-tomato` | `oklch(54% .2 348)` | Links, underlines, bullets, card top stripe, sticker bg |
| Light accent surface | `--color-marigold` | `oklch(91% .05 348)` | Nav/header bg, blockquote bg, sticker variant |
| Deep accent | `--color-grape` | `oklch(45% .19 350)` | H1 accent word color, sticker variant |
| Green accent | `--color-pine` | `oklch(62% .13 166)` | Sticker variant |
| Teal accent | `--color-sky` | `oklch(72% .11 196)` | Sticker variant |
| Footer background | — | `oklch(16% .018 295)` | Dark near-black purple footer |
| Text on dark | `--text-on-dark` | `oklch(98% .008 300)` | All text on dark/footer bg |
| Text on light | `--text-on-light` | `oklch(21% .03 295)` | Text on marigold/light accent surfaces |

**Accent palette options (via `data-accent`):**

| Name | `--color-tomato` | hue |
|------|-----------------|-----|
| Magenta (default) | `oklch(54% .2 348)` | 348 — pink/magenta |
| Grape | `oklch(52% .18 294)` | 294 — purple-violet |
| Iris | `oklch(52% .18 278)` | 278 — blue-violet |
| Cobalt | `oklch(52% .17 256)` | 256 — blue |
| Teal | `oklch(50% .12 195)` | 195 — teal |
| Forest | `oklch(50% .13 150)` | 150 — green |

**Color philosophy:** Near-monochromatic ink system (all purples at hue ~295) with a single vivid accent. OKLCH keeps perceived brightness consistent across all accent swaps — colors change hue but never feel clashing. The paper/card/ink triad is almost invisible until you add the accent.

---

## Typography

| Role | Font family | Weight | Size (desktop) | Line height | Letter spacing |
|------|-------------|--------|----------------|-------------|----------------|
| Display / H1 | Bricolage Grotesque Variable | 800 | 72px (4.5rem md) | 0.95 | -1.8px (-0.025em) |
| H2 | Bricolage Grotesque Variable | 800 | 36px | 1.25 | -0.72px |
| H3 / card title | Bricolage Grotesque Variable | 700 | 20px | 1.375 | normal |
| Tagline / hero subhead | Bricolage Grotesque Variable | 700 | 20–24px | 1.375 | normal |
| Body | Atkinson Hyperlegible | 400 | 17px (1.0625rem) | 1.5 | normal |
| Nav / stickers / buttons | Bricolage Grotesque Variable | 700–800 | 14–16px | 1 | tight |
| Eyebrow / label | JetBrains Mono Variable | 400 | 12px | 1.33 | 0.14em |
| Code / mono | JetBrains Mono Variable | 400 | 1em (inherited) | inherited | inherited |

**Font sources:**
- Bricolage Grotesque Variable → Google Fonts (free, variable weight 200–800)
- Atkinson Hyperlegible → Google Fonts (free, designed by Braille Institute for legibility)
- JetBrains Mono Variable → Google Fonts (free, variable weight)

**Key typographic moves:**
- H1 is split-color: first part in `--color-ink`, accent word in `--color-grape` — creates immediate visual anchor without needing a color block
- The accent word also gets a hand-drawn wavy SVG underline in `--color-tomato` — pure CSS trick with a `<svg viewBox="0 0 200 18">` path absolutely positioned below the word
- Eyebrow text uses JetBrains Mono at 12px + 0.14em tracking + uppercase — signals developer identity before the user reads a word
- Nav links use `font-display` (Bricolage) at small weight 700 — consistent with headings, reinforces brand feel everywhere

---

## Spacing & Layout

- **Grid:** free-flow sections with Tailwind utility classes
- **Max content width:** `max-w-4xl` = 56rem / 896px
- **Section horizontal padding:** `px-6` = 24px (desktop), same mobile
- **Hero:** `pt-12 pb-10 md:pt-16` = 48–64px top, 40px bottom
- **Hero columns:** `md:grid-cols-[1.4fr_1fr]` — intentionally asymmetric: content side wider than photo side
- **Card grid gap:** 24px (`gap-6`)
- **Sticker row gap:** 10px (`gap-2.5`)
- **CTA button row gap:** 12px (`gap-3`)
- **Base unit:** 4px (`--spacing: .25rem` in Tailwind v4)
- **Border radius:** cards `14px`, stickers pill `999px`, avatar full circle, dark panel `12px`, buttons (see below)

---

## Visual Style

### Shadows — The Signature System

Hard flat shadows with **zero blur** — neo-brutalist stack shadow effect:

```css
--shadow-hard-sm:  3px 3px 0 var(--color-ink)
--shadow-hard:     5px 5px 0 var(--color-ink)
--shadow-hard-lg:  8px 8px 0 var(--color-ink)
```

Every card, sticker, avatar, and interactive element uses one of these three. The shadow color is always `--color-ink` (the near-black), never grey or transparent — this creates the defining "block print" aesthetic.

### Borders

All bordered elements use `border-2` (2px) `border-ink` — same color as shadows. Hairline borders don't exist here; every border is chunky and intentional.

### `.tactile` class

Post cards have a `.tactile` CSS class that adds an active/press state: the hard shadow collapses and the element translates slightly, simulating a physical button press. Not defined in extracted CSS but used on all cards.

### Rotations

Avatar (`-rotate-3`), stickers (`-rotate-2`, `rotate-1`, `-rotate-1`, `rotate-2`) have small CSS transforms for a handmade, pinned-to-a-board feel. These are static, not animated — the slight imperfection is intentional.

### Dark mode

`.dark` class on `:root`. Accent colors lighten (higher OKLCH lightness value) to stay vivid against dark backgrounds. Paper/card/ink presumably invert to dark surfaces. Toggle in header (sliding knob switch).

### No gradients, no blur, no glass

This design uses **zero gradients**, zero backdrop-blur, zero drop shadows with feathering. Depth comes entirely from hard shadows + chunky borders.

---

## Components

### Navigation
- Sticky top, `bg-marigold` (light accent surface) with `border-b-2 border-ink`
- Logo: small circular avatar photo (36×36px, `rounded-full border-2 border-ink shadow-hard-sm`, `-rotate-3`), rotates to `+rotate-3` on `group-hover` via `transition-transform duration-150` — charming micro-interaction
- Logo text: "Nick Nisi" in Bricolage Grotesque, `text-lg font-extrabold tracking-tight`
- Nav links (desktop): Bricolage, `text-sm font-bold`, `opacity-65` default → `hover:opacity-100`, no underline, `transition-opacity`
- Right controls: accent color picker (`<details>` dropdown with color swatches) + dark mode toggle (custom sliding knob switch)
- Mobile: hamburger toggle (icon swaps between menu and close icons via `aria-expanded`)

### Hero
- Asymmetric two-column: `md:grid-cols-[1.4fr_1fr]`, items-center, gap-12
- **Left column (content):**
  - Eyebrow: job title in JetBrains Mono, 12px, uppercase, tracking-wide, `--color-ink-soft`
  - H1: "Nick" in `--color-ink` + "Nisi" in `--color-grape` with wavy SVG underline in `--color-tomato`
  - Tagline: Bricolage, 20–24px, bold, `--color-ink` — max 24ch
  - Bio: Atkinson, `--color-ink-soft` — max 48ch
  - Sticker row: 4 stickers with variant colors and slight rotations (see Stickers below)
  - CTA buttons: "Read the blog →" (primary) + "About me" (ghost)
- **Right column:** profile photo in `rounded-2xl border-2 border-ink bg-card shadow-hard-lg -rotate-3` container, `w-[clamp(220px,26vw,300px)]`

### Buttons
- **Primary (`.btn-primary`):** filled dark; likely `bg-ink text-paper` or `bg-grape text-on-dark`; border-2 border-ink; rounded pill; Bricolage bold
- **Ghost (`.btn-ghost`):** transparent bg, `border-2 border-ink`, same font — converts to filled on hover
- Both: `padding ~10px 20px`, `border-radius: 999px` (pill), `font-display font-bold`

### Sticker Component
The `.sticker` is this design's most distinctive reusable primitive:

```css
.sticker {
  font-family: var(--font-display);
  border: 2px solid var(--color-ink);
  background: var(--color-card);
  color: var(--color-ink);
  border-radius: 999px;
  padding: 0.32rem 0.7rem;  /* ~5px 11px */
  font-size: 0.84rem;        /* ~13.4px */
  font-weight: 700;
  line-height: 1;
  display: inline-flex;
  align-items: center;
  gap: 0.4rem;
}
.sticker-solid { box-shadow: var(--shadow-hard-sm); }
.sticker-grape  { background: var(--color-grape);    color: var(--text-on-dark); }
.sticker-marigold { background: var(--color-marigold); color: var(--text-on-light); }
.sticker-sky    { background: var(--color-sky);      color: var(--text-on-light); }
.sticker-pine   { background: var(--color-pine);     color: var(--text-on-dark); }
.sticker-tomato { background: var(--color-tomato);   color: var(--text-on-dark); }
```

Used for skills, tags, event names, roles — anything that needs a label with personality.

### Post Cards
```
rounded-[14px] border-2 border-ink bg-card shadow-hard-sm
```
- Accent top stripe: `h-3 bg-tomato border-b-2 border-ink` (12px colored bar, changes with accent)
- Category label: JetBrains Mono, 12px, uppercase, tracking-wide, `--color-ink-soft`
- Title: Bricolage, 20px, bold, `group-hover:underline decoration-tomato underline-offset-4`
- Excerpt: Atkinson, 14px, `--color-ink-soft`, `line-clamp-3`
- Internal padding: `p-5` (20px)
- Hover: title underline reveals in `--color-tomato`

### Accent Color Picker
- `<details>` element (no JS required for open/close)
- Summary shows current accent dot (14px circle in `--color-tomato`) + caret arrow
- Dropdown panel: `bg-card border-2 border-ink rounded-[12px] shadow-hard-sm padding: 4px`
- Each option: color dot (16px circle) + label text; `background: var(--color-paper-2)` on selected/hover
- Sets `data-accent` on `:root` + persists to localStorage

### Footer
- Full-width dark block: `bg-[oklch(16%_.018_295)]`, top margin 64px
- Inner max-w-4xl, py-12, px-6
- Top area: two-column — tagline + email left, nav links right
- Tagline: Bricolage, 24px, extrabold, `text-paper`
- Email: icon + address, Bricolage bold, `text-paper hover:underline`
- Nav links: Bricolage, 14px, bold, `text-paper/70 hover:text-paper hover:underline`
- Bottom row: social icons (LinkedIn, GitHub, Bluesky, YouTube) + copyright

---

## Interactions & Animation

- **Default transition:** `150ms cubic-bezier(.4, 0, .2, 1)` (Tailwind default)
- **Logo avatar hover:** `-rotate-3` → `rotate-3` via `transition-transform duration-150` — the most delightful micro-interaction on the page
- **Nav links:** `opacity-65` → `opacity-100` on hover, `transition-opacity`
- **Post card title:** no underline → `underline decoration-tomato` on `group-hover`
- **`.tactile` press state:** hard shadow collapses inward + small translate on `:active` — cards feel physically clickable
- **Accent picker caret:** rotates 180° when `<details>` is open
- **Dark mode toggle:** knob slides via `transform: translateX(26px)` with CSS transition
- **No scroll animations, no page transitions, no parallax** — interactions are all local, instant, responsive

---

## Tone & Personality

Direct and warm — a developer who has opinions and isn't afraid to show them, but leads with approachability rather than authority. The neo-brutalist visual language (hard borders, flat shadows, chunky type) signals confidence without aggression; the tilted stickers and wavy underlines pull it back toward playful. Atkinson Hyperlegible as the body font is a quiet statement: accessibility matters here. The accent theme picker is the personality in full — it says "I built this for myself and I gave you the option to make it yours too."

---

## Notes & Reuse Tips

- **The sticker component is immediately portable** — it's 10 lines of CSS with no dependencies. Drop it into any project for skill tags, category labels, or "featured" badges. The color variants + shadow give instant visual hierarchy.
- **Hard shadow system replaces drop shadows everywhere.** If you adopt `--shadow-hard-sm/md/lg`, commit fully — mixing one blurred shadow with hard shadows reads as an error, not a choice.
- **OKLCH color system:** the paper/ink tokens use hue ~295–300 (a purple-neutral), not grey. This subtle warmth is what prevents the page from feeling cold or clinical — `oklch(97.5% .006 300)` vs `#f5f5f5` is a noticeable difference at full-page scale. Worth preserving exactly.
- **The wavy SVG underline on H1** is pure HTML + CSS, no library. SVG path: `M3 12 C 50 6, 90 14, 130 9 S 188 6, 197 10` at `viewBox="0 0 200 18"`, `stroke-width: 5`, `stroke-linecap: round`. Position it `absolute -bottom-2 left-0 h-3 w-full overflow-visible`.
- **Bricolage Grotesque** is variable (200–800 weight range on Google Fonts). At 800 weight it competes with premium display type. At 400–600 it works well for body use if you drop Atkinson.
- **Atkinson Hyperlegible** substitute: `Inter` is close but loses the accessibility intent. Better alternatives: `Nunito`, `Source Sans 3`, or `Lexend`.
- **The accent theme system** is architecturally clean: change 3 CSS variables, entire site re-themes. To replicate: define `--color-accent`, `--color-accent-light`, `--color-accent-deep` and use them everywhere instead of hardcoded colors.
- **Don't add borders unless they're `2px solid ink`** — a hairline border would look accidental against this design's vocabulary. If you need a subtler divider, use `opacity-20` on ink or a background color shift instead.
- **Post card top stripe** (`h-3 bg-tomato border-b-2 border-ink`) is a clever category signal — change the stripe color per category to get a quick visual scan of content type.
- **Tech stack note:** built on Astro + Tailwind v4 (CSS-native, no `tailwind.config.js`). The OKLCH tokens live in `@layer theme` within Tailwind's generated CSS. Reproducible without Astro — just use the CSS custom properties directly.
