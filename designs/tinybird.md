# Tinybird

## Meta
- **Source:** https://www.tinybird.co/
- **Style keywords:** terminal, developer-tool, dark, technical, brutalist-minimal, monospace-driven
- **Best for:** SaaS landing page, dev tool / infra product, API platform, docs-adjacent marketing site

---

## Colors

| Role | Name | Hex | Usage |
|------|------|-----|-------|
| Primary | Signal green | `#27F795` | CTAs, links, highlights, terminal accents |
| Secondary | — | — | (none; green carries all accent duty) |
| Background | Near-black | `#0A0A0A` | Page background |
| Surface | Dark green tint | `#0D1F16` approx | Diagram panels, code block interiors |
| Text primary | White | `#FFFFFF` | Headings, nav, footer links |
| Text secondary | Grey | `#8D8D8D` | Body copy, subheads |
| Accent | Diff red | `#3A1418` bg / `#F87171` text approx | "removed" lines in diff-style code blocks |
| Border | Hairline grey | `rgba(255,255,255,0.1)` approx | Card outlines, dividers |

---

## Typography

| Role | Font family | Weight | Size (desktop) | Size (mobile) | Transform |
|------|-------------|--------|----------------|---------------|-----------|
| Display / H1 | Roboto | 400 | 64px / lh 72px, ls -1.28px | scales down ~36-40px | none |
| H2 | Roboto | 400 | 64px / lh 72px | ~32px | none |
| H3 | Roboto | 400 | 40px / lh 48px, ls 0.4px | ~24px | none |
| Body | Roboto Mono | 400 | 14px / lh 22px | 14px | none |
| Caption / small | Roboto Mono | 400 | 12-14px | 12px | uppercase for eyebrow labels |
| Label / tag | Roboto Mono | 400 | 14-16px | same | uppercase, e.g. `ENTERPRISE READY`, `[SaaS / Dashboards]` |
| Monospace / code | Roboto Mono | 400 | 14-16px | same | none |

**Font source:** Google Fonts (Roboto, Roboto Mono) with local "Fallback" faces defined
**Line height:** body `1.5-1.6`, headings `1.1-1.2`
**Letter spacing:** display headings `-0.02em` (tight), H3/eyebrows slightly loose `+0.01-0.02em`

Notable pairing: **serif-free grotesque (Roboto) for large display type**, switching to **monospace (Roboto Mono) for every other role** — body copy, nav links, buttons, labels, footer. This mono-everywhere-except-headlines choice is the signature of the whole system, reinforcing "written in a terminal."

---

## Spacing & Layout

- **Grid:** free-flow single column, centered content blocks up to ~3-col diagrams
- **Max content width:** ~1360px outer, ~1125px for text-focused sections
- **Section padding (vertical):** ~120-160px desktop / ~64px mobile
- **Component gap:** 24-32px
- **Base unit:** 8px
- **Border radius:** none — all corners square (buttons, cards, code blocks, tags all 0px radius)

---

## Visual Style

- **Shadows:** none observed; flat design throughout
- **Borders:** hairline 1px, low-opacity white/grey, used to frame code blocks, stat panels, diagram nodes
- **Images:** none used as hero imagery — replaced by code blocks, terminal windows, and node/flow diagrams
- **Icons:** small outline icons inside bordered squares (used for pipeline/diagram nodes); brand logos shown in flat grayscale for social-proof strip
- **Texture / background:** decorative diagonal line-pattern (green hairlines fanning into slashes) used as section background filler; macOS-style traffic-light dots on code block headers

---

## Components

### Navigation
Static (non-sticky observed at scroll), logo left (paper-plane mark + "tinybird" wordmark in Roboto), text nav links center-right with `[+]` suffix on items that have dropdowns (Product, Resources), "Sign in" as plain link + "Sign up" as filled green square button, right-aligned.

### Hero / Above the fold
Centered layout: large two-line H1, grey subhead below, two CTAs side-by-side (filled green primary + plain-text green secondary), then a horizontal row of bracketed use-case tags (`[SaaS / Dashboards] | [Observability] | ...`) with one tag boxed/active. Below that, a bordered stat/testimonial panel (big green numbers + customer quote) sits inside the hero, followed by a grayscale logo strip.

### Buttons
- Primary: filled solid green (`#27F795`) on dark text, square corners, mono font, generous padding (`16px 24px`), no shadow, `0.3s` ease transition (likely opacity/scale or bg-shift on hover)
- Secondary: transparent bg, green mono text, no border box — reads as a link but sized like a button
- Ghost / text: plain green text link, no underline by default

### Cards
Diagram/stat cards: dark surface, 1px hairline border, square corners, small icon + label inside; code-block "cards" have a dark-green–tinted background for the "build" column vs plain dark for adjacent columns, plus colored diff rows (green-tinted bg for additions, red-tinted for removals) inside terminal-style panels with dot-decorated title bars.

### Forms / Inputs
Not prominently featured on homepage (auth is external); assume same square, hairline-border, mono-font treatment as buttons if built.

### Footer
Multi-column flat link list (About, product links, resource links, integration links), all in white mono text, no card treatment. Includes a small "All systems operational" status pill (green bars icon). Bottom bar: copyright + legal links + social icons, full-bleed giant outlined/solid wordmark logo cropped at the very bottom edge with decorative dot accents — a large branding flourish closing the page.

---

## Interactions & Animation

- **Default transition:** `0.3s cubic-bezier(0.4, 0, 0.2, 1)` on interactive elements (buttons/links)
- **Hover effects:** likely color/opacity shift on green elements (exact hover state not sampled, but transition timing confirms animated states)
- **Scroll animations:** not confirmed, page reads static/flat but diagram sections likely animate node flow (motion cues present in the pipeline diagram)
- **Page transitions:** none
- **Loading state:** not observed

---

## Tone & Personality

Cold, precise, and unmistakably built-for-engineers. Every visual choice — monospace type, terminal windows, diff-style code blocks, bracket-notation tags, square corners, single neon-green accent on near-black — reinforces "this is a tool made by people who live in a terminal." It's dense with technical proof (numbers, logos, code) rather than lifestyle imagery, but breathes via generous dark negative space and a single disciplined accent color instead of a full palette.

---

## Notes & Reuse Tips

- The core trick to steal: **pair a plain sans (Roboto) exclusively for large display headlines with a monospace (Roboto Mono) for literally everything else** — nav, body, buttons, labels, footer. That contrast alone signals "developer tool" without needing extra ornamentation.
- Single accent color discipline (`#27F795` on `#0A0A0A`) does a lot of work — resist adding a second accent hue.
- Square corners everywhere (0px radius) is load-bearing for the "terminal/brutalist" feel; rounding any component breaks the illusion.
- Bracket-notation labels (`[Product]`, `[SaaS / Dashboards]`) and macOS traffic-light dots on code panels are cheap, distinctive details worth reusing directly.
- Diff-style red/green code blocks are an effective way to show before/after or pros/cons without building custom comparison UI.
- Skip: the giant cropped wordmark at the footer is a nice flourish but only works if the brand name is short and reads well at huge scale — don't force it for longer names.
