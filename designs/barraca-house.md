# Barraca Founders House

## Meta
- **Source:** https://barraca.house/es
- **Style keywords:** neo-brutalist, punk poster, rave-flyer, dark, high-contrast, monospace-tech
- **Best for:** community/event landing page, founder/builder meetup site, startup club, ticketed session page

---

## Colors

| Role | Name | Hex | Usage |
|------|------|-----|-------|
| Primary | Acid (neon lime) | `#c8ff3d` | Primary CTA buttons, active/open states |
| Secondary | Magenta deep | `#e01f74` | Accents, offset shadows, hover underlines, brand mark |
| Background | Nit (near-black navy) | `#0c0912` | Page background |
| Surface | Nit-2 | `#150f1f` | Cards, ticket panels, elevated blocks |
| Text primary | Paper (warm cream) | `#f3ece0` | Headings, body copy on dark |
| Text secondary | Muted | `#8a7f94` | Captions, dimmed/unrevealed copy, metadata |
| Accent | Cian (cyan) | `#33e6ff` | Chromatic-aberration text outline, decorative glow |
| Border | Paper at low opacity | `rgba(243,236,224,0.1–0.15)` | Hairline/dashed dividers |

Notes: on the light CTA section near the footer, background flips to Paper (`#f3ece0`) with Nit-colored text/buttons — an inverted panel used to break up the long dark page.

---

## Typography

| Role | Font family | Weight | Size (desktop) | Size (mobile) | Transform |
|------|-------------|--------|----------------|---------------|-----------|
| Display / H1 (wordmark) | Syne Variable | 800 | `clamp(2rem, 10vw, 8.25rem)` | scales fluidly | uppercase |
| H2 / Section title | Syne Variable | 800 | `clamp(1.6rem, 4.5vw, 2.75rem)` | fluid | uppercase |
| H3 / Card title | Syne Variable | 800 | ~21.6px (1.35rem) | same, fluid | uppercase |
| Body | Space Mono | 400 | 16px | 16px | none |
| Caption / small | Space Mono | 400 | `.7rem` (ticket size) | same | uppercase, tracked |
| Label / tag / nav | Space Mono | 400 | `.7rem` | same | uppercase, letter-spacing `0.18em` |
| Monospace / code | Space Mono | 400 | 16px | 16px | none |

**Font source:** Google Fonts — Syne (Variable) for display, Space Mono for everything else (body doubles as the "monospace" role, giving the whole site a terminal/ticket feel).
**Line height:** body `1.6`, headings tight (`1.25` leading-tight / `1.375` leading-snug).
**Letter spacing:** headings tight `-0.025em`, nav/labels wide `0.18em`.

---

## Spacing & Layout

- **Grid:** free-flow single column with occasional 2-col card grids (`md:grid-cols-2`)
- **Max content width:** `76rem` (`--container-page`)
- **Section padding (vertical):** generous, sections separated by full-width dashed hairlines rather than background blocks
- **Component gap:** ~24–32px between stacked text blocks
- **Base unit:** 4px (Tailwind default scale)
- **Border radius:** none — fully square corners everywhere (brutalist)

---

## Visual Style

- **Shadows:** no soft/blur shadows; instead a hard-edged "ink-offset" effect — a solid-color duplicate block offset a few px behind buttons/cards (magenta or acid), like risograph misregistration
- **Borders:** hairline 1px, mostly dashed (`border-dashed border-paper/15`) as section dividers; some solid borders on outline/ghost buttons
- **Images:** minimal photography; content relies on typography, ticket-style cards, and a scrolling marquee ticker
- **Icons:** none decorative — bullets (`•`), arrows (`▶ / ▼` for FAQ accordions), plus signs (`+`) for empty partner-logo slots
- **Texture / background:** flat dark color, no gradients on the page shell; gradient/glow only inside the "session" ticket card (dark teal-to-magenta radial) and on the chromatic-aberration wordmark (cyan/magenta text-shadow duplicate offset like a glitch)

---

## Components

### Navigation
Sticky/fixed header, `backdrop-blur` over near-black background, bottom hairline border. Logo left ("BARRACA" + magenta "FH"), mono uppercase nav links right with wide letter-spacing, hover fades muted → paper. Primary CTA ("Guest List") rendered as a solid acid-lime button with ink-offset shadow, pinned at the far right. No visible mobile hamburger captured, but nav links are hidden below `lg` breakpoint (likely collapses to a drawer).

### Hero / Above the fold
Top marquee ticker (scrolling magenta stripe with repeating uppercase event info) sits above the header. Hero is left-aligned text over a dark page: small uppercase pill/tag ("EST. 2026 · VALÈNCIA → EL MUNDO") in acid-on-transparent outline, then a huge wordmark ("BARRACA") with a cyan/magenta chromatic-aberration outline effect, subhead in acid green, short lede paragraph in muted paper, then a primary acid CTA button with ink-offset shadow and a small caption below it. To the right, a floating "ticket" card (session lineup) sits at an angle with the same ink-offset shadow treatment.

### Buttons
- Primary: filled `bg-acid` (#c8ff3d), dark `text-nit` label, uppercase Syne Extrabold, no radius, `ink-offset` hard shadow (magenta or acid duplicate offset behind), no blur
- Secondary / outline: `border` only, transparent background, dashed or solid hairline border, uppercase mono label, subtle hover
- Ghost / text: underlined links (e.g. footer email, "Leer el manifiesto"-style), color shifts muted → paper or → magenta on hover

### Cards
Ticket/session cards use the darker surface color (`nit-2`) with a bright gradient panel on top (teal-to-magenta), pink outline border, ink-offset shadow, uppercase mono labels ("SESSION 001", "OPEN" tags in acid), and a numbered lineup list with a dashed divider before the footer line. Content cards ("La Casa" section) are borderless — separated by hairline dividers only, with a small colored bullet + uppercase Syne title + mono body text.

### Forms / Inputs
No visible standard form fields on this page — signup is handled via a link-style CTA button to an external guest-list flow, plus a mailto link ("hola@barraca.house").

### Footer
Dark background, large chromatic-aberration wordmark repeated, tagline in acid mono, short description in paper. Right-aligned link list (Luma, X, LinkedIn, "Read in English") in uppercase mono. Bottom hairline divider, then legal row (copyright left, "Hecho en València." right) in small muted mono.

---

## Interactions & Animation

- **Default transition:** `transition-colors` on links/nav (~150–200ms ease)
- **Hover effects:** color shift (muted → paper/magenta) on links; likely a slight press/offset shift on ink-offset buttons
- **Scroll animations:** content blocks appear dimmed/muted and brighten in (opacity/color reveal) as they scroll into view — used heavily on body paragraphs and section headers
- **Page transitions:** none observed (static page navigation)
- **Loading state:** none observed

---

## Tone & Personality

Loud, confident, underground-club-meets-startup-demo-night. It borrows 80s Valencia rave/flyer visual language (chromatic aberration, neon acid green, hot magenta, risograph-style offset shadows, monospace "ticket" typography) and applies it to a founder-community site. The copy is terse and mono-spaced like event signage; the huge display type and dashed section dividers keep it feeling like a printed flyer scrolled into a webpage rather than a typical SaaS landing page.

---

## Notes & Reuse Tips

- The signature move is the **"ink-offset" hard shadow**: a solid color block (magenta or acid) offset a few pixels behind buttons/cards with zero blur and zero border-radius — steal this for any brutalist/punk CTA treatment.
- Pair one loud accent (acid lime) with one hot accent (magenta) against near-black + warm cream text — resist adding more colors, the restraint is what makes it read as designed rather than gaudy.
- Body copy running in the same monospace as labels/nav is what sells the "ticket/terminal" feel — don't swap it for a humanist sans, that breaks the theme.
- Scroll-reveal (dim → full color) on paragraphs is subtle but does a lot of work keeping a very type-heavy, single-column page from feeling flat/static.
- Skip if the client wants anything soft, rounded, or corporate-safe — every corner on this site is square and every shadow is hard-edged by design.
