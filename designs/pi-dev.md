# Pi (pi.dev)

## Meta
- **Source:** https://pi.dev/
- **Style keywords:** terminal, engineering-paper, editorial serif, monospace UI, warm paper tone, brutalist-minimal, developer tool
- **Best for:** CLI tool landing page, developer product, open-source project site, technical docs homepage

---

## Colors

| Role | Name | Hex / RGBA | Usage |
|------|------|-----|-------|
| Background | Warm parchment | `#EBE7E4` (rgb 235,231,228) | Page background |
| Surface (nav / panels) | Paper white | `#F3F2F0` blended over bg | Sticky nav, dropdown menus |
| Surface (install box) | Off-white card | `#F4F2F0` | Install command panel |
| Text primary | Ink navy-black | `rgba(37,47,61,0.96)` ≈ `#252F3D` | Headings, body copy |
| Text secondary | Warm grey | `rgba(92,87,82,0.77)` ≈ `#5C5752` | Inactive tabs, muted labels |
| Text on buttons | Slate | `rgba(57,67,82,0.84)` ≈ `#394352` | Button/UI label text |
| Border / hairline | Warm taupe | `rgba(139,132,125,0.35)` / `rgba(92,87,82,0.25)` | Button borders, panel borders |
| Accent gold | Muted gold | `#EACD7C` at ~12% opacity | Nav gradient wash (very subtle) |
| Accent blue-grey | Steel blue | `#4B607C` | Live/status dot, gradient wash, small accents |
| Shadow tint | Warm brown-grey | `color(srgb .36 .34 .32 / 0.12)` | Soft floating-panel shadow |

**Color philosophy:** Almost monochrome — everything sits on one warm parchment background with near-black ink text. Color is rationed to two barely-there gradient washes (gold + steel blue) and one small blue accent dot. Feels like aged paper/graph paper, not a "designed" palette.

---

## Typography

| Role | Font family | Weight | Size (desktop, 1440px) | Size (mobile, 500px) | Letter spacing |
|------|-------------|--------|----------------|---------------|-----------|
| Display / H1 | Plantin MT Pro (serif) | 400 | 47.7px / lh 48.6px | 24px / lh 24.5px | -0.72px |
| H2 | Plantin MT Pro | 400 | 49.5px / lh 47.5px | 40px / lh 38.4px | -1.98px |
| H3 | Plantin MT Pro | 400 | 27px / lh 27px | 23.4px / lh 23.4px | -0.4px |
| Body | Plantin MT Pro | 400 | 23px / lh 32.3px | 20.25px / lh 28.35px | -0.35px |
| UI label / tab | Commit Mono | 700 | 14px, uppercase | same | +1.12px (~0.08em) |
| Button label | Departure Mono | 400 | 13.3–14px, uppercase | same | +1.5–1.9px (~0.14em) |
| Code / inline | Commit Mono | 400 | 15.5px / lh 22.4px | same | normal |

**Font sources:**
- Plantin MT Pro → licensed serif (fallback: Plantin MT Std → Plantin → Georgia → serif)
- Commit Mono / Departure Mono → licensed monospace (fallback: SFMono-Regular, ui-monospace, Menlo, Monaco, Consolas)

**Key typographic moves:**
- Hard split: **serif for all prose/headings**, **monospace for all UI chrome** (buttons, tabs, labels, code). This is the single most defining trait.
- All monospace UI text is uppercase with wide tracking (~0.08–0.14em) — reads as terminal/CLI labeling.
- Headings carry mild negative letter-spacing on the serif (tightens large type), body text also slightly negative (-0.015em) which is unusual for serif body copy but keeps it dense/editorial.
- Type appears fluid-scaled (clamp/vw), not fixed breakpoints — sizes grow continuously between the mobile and desktop numbers above.

---

## Spacing & Layout

- **Grid:** flex/grid hybrid, free-flow sections; feature cards use CSS grid (`three-up` = 3 columns)
- **Max content width:** ~1368px inner content at 1440px viewport (≈36px side gutters, no hard container cap observed)
- **Install/command box width:** 828px max, centered
- **Section gap (vertical rhythm):** ~48–58px between stacked blocks
- **Callout grid gap:** ~43px row/column
- **Nav padding:** 12.6px vertical / 17px horizontal
- **Base unit:** ~9px increments visible (likely 16px base × fluid scale factor, not a clean 8px grid)
- **Border radius:** essentially none — buttons/panels 0–1px, install box 4px, icon-only burger button 4.5px. Reads as square/terminal, not soft.

---

## Visual Style

- **Shadows:** none anywhere except the floating install-command box — one soft diffused shadow `0 4px 40px rgba(warm-grey, 0.12)`. Everything else is flat.
- **Borders:** hairline only, warm taupe (`rgba(139,132,125,.35)` / `rgba(92,87,82,.25)`), used on buttons and the install panel — never on plain cards/text blocks.
- **Background texture (signature element):** the entire page sits on a fixed, layered **graph-paper grid** drawn via `body::before`:
  - fine 4px grid at 3% opacity
  - coarse 20px grid at 7% opacity
  - a second 20px grid pass at 11.4% opacity (creates emphasis lines, like real graph paper's bold every-5th-line)
  - a dot pattern at each grid intersection (`radial-gradient` circles, 2px)
  - `body::after` adds a soft vignette fade back to the base background color at the edges
  - Both layers are `position: fixed`, so the grid stays static while content scrolls over it — subtle parallax-free paper backdrop.
- **Images:** minimal use; hero uses an interactive `<canvas>`-rendered logo/animation, not photography.
- **Icons:** custom SVG only (20 inline SVGs found), no icon library — logo mark, copy icon, theme toggle, social icons.
- **Live/status indicator:** a tiny 5.6px circular dot (steel blue `#4B607C`), blinking via `steps(1) infinite` animation named `terminal-cursor-blink` — literally reuses a terminal cursor blink for a "live" status dot. Distinctive, cheap-to-copy detail.

---

## Components

### Navigation
- Sticky top, `position: sticky`, z-index 20
- Background: layered gradient wash (paper white + faint gold/blue tint) over the page bg — not solid
- Logo left (custom animated mark, has a right-click context menu with "Copy SVG" / "Download SVG" — playful easter egg)
- Burger-style toggle button (`sticky-nav-toggle`) at 4.5px radius, opens a slide-out nav sheet (`nav-sheet-inner` / `nav-sheet-footer`) rather than a classic horizontal link row
- No visible always-on nav links at rest — nav is collapsed-first even at desktop widths

### Hero / Above the fold
- Centered layout: H1 (two-line, serif, large) → subhead line → tabbed install command box → doc link
- Install command box: tabbed by package manager (CURL / POWERSHELL / NPM / PNPM / BUN), active tab bold + full-opacity ink color, inactive tabs muted warm-grey
- Command shown in monospace with a `[ COPY ]` bracket-style button, border hairline, uppercase mono label
- Below: `[ READ THE DOCUMENTATION ]` styled as a bracket-wrapped text link (brackets are literal characters in the string, not pseudo-content)
- Background: the fixed graph-paper grid described above; hero canvas logo animation sits over it

### Buttons
- **Primary/action (Copy, Revert):** hairline border (`1px solid rgba(139,132,125,.35)`), transparent/near-transparent bg, uppercase monospace label with wide tracking, square corners (0–1px radius)
- **Tab buttons (install switcher):** no border, uppercase bold monospace, color shifts from muted grey (inactive) to full ink (active) — no underline or bg change, just color/weight
- **Icon-only (burger, theme toggle):** no border, transparent bg, 4–4.5px radius on the hit target only
- **Bracket-style text links:** `[ LABEL ]` treated as a button-equivalent CTA without ever using a filled/pill button — this is the site's only "primary CTA" pattern

### Cards (feature/callout grid)
- Completely flat: no background, no border, no shadow — separation comes purely from grid gap (~43px) and whitespace
- Structure: H3 title (serif, 27px) + body paragraph (serif, 18–23px), horizontal padding only (~22px), no vertical padding/framing
- Used for the "What we didn't build" 3-up grid (No MCP / No sub-agents / No permission popups / etc.)

### Forms / Inputs
- No traditional form inputs observed on the homepage (install tabs act as the only interactive input-like control)

### Footer
- Transparent background (inherits page bg + grid texture)
- Padding ~22px top, 36px sides/bottom
- Serif body font for copyright/legal line, monospace/icon links for GitHub/npm/Discord/X
- Theme toggle button ("Auto / Light / Dark") sits inline in the footer, monospace label, no border

---

## Interactions & Animation

- **Default transition:** not explicitly probed, but color/weight changes on tabs read as fast (~150ms) discrete swaps, not eased fades
- **Terminal cursor blink:** `steps(1) infinite`, 1.25s — used on the live-status dot; reuse this exact animation for any "recording/live" indicator to match the CLI feel
- **Hero canvas:** interactive logo animation — click-to-play behavior (`"Play the Pi logo animation"` button)
- **Scroll:** feature cards use a `home-scroll-fade-item` class suggesting fade-in-on-scroll for callout cards
- **Fixed background:** the graph-paper grid is pinned via `position: fixed`, so it never scrolls with content — reinforces the "page as a sheet of paper on a table" metaphor

---

## Tone & Personality

Feels like an engineer's paper notebook rendered as a website: serif prose for reading, monospace/uppercase for anything you'd type or click, laid over a faint graph-paper grid instead of a plain white void. It's confident and slightly austere — no gradients-as-decoration, no rounded-soft SaaS feel, no marketing color. The warm parchment tone (not stark white) keeps it from feeling cold despite the flat, borderless component style. Reads as "built by developers, for developers," technical without being sterile.

---

## Notes & Reuse Tips

- **The serif-for-prose / mono-for-UI split is the single most portable idea here.** Even without matching fonts exactly, applying "headings & paragraphs get a serif, every button/label/tab gets an uppercase tracked monospace" instantly gives a similar technical-editorial feel.
- **Graph-paper `body::before` background is cheap to replicate:** stack 2–3 `repeating-linear-gradient`s (fine grid + coarse grid) at 3–11% opacity in your ink color, plus one radial-gradient dot pattern at grid intersections, set `position: fixed`. Skip the vignette (`::after`) if it feels unnecessary.
- **Bracket-style CTAs (`[ READ THE DOCS ]`)** are a good zero-cost alternative to filled buttons when you want a CTA that still reads as "text," not "chrome."
- **Terminal-cursor blink (`steps(1) infinite`) on a tiny dot** is a nice reusable micro-detail for any "live/status" indicator — much more on-theme than a standard CSS pulse/ease animation.
- **Almost no border-radius anywhere (0–4px max)** — don't round corners if trying to copy this look; softness would break the terminal aesthetic immediately.
- **Warm parchment bg (`#EBE7E4`) instead of pure white** is what keeps the whole flat, borderless, shadowless design from feeling cold or unfinished — this single color choice is doing a lot of work.
- **Licensed fonts (Plantin MT Pro, Commit Mono, Departure Mono) aren't free** — substitutes: serif → `Source Serif 4`, `Lora`, or `PT Serif`; monospace → `JetBrains Mono`, `IBM Plex Mono`, or `Space Mono` for the uppercase tracked labels.
