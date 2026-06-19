# Amp (ampcode.com)

**Source:** https://ampcode.com/
**Style:** Editorial cream, self-hosted variable fonts, flat, light/dark dual-mode, frontier-tech confidence
**Best for:** AI dev tools, coding agents, SaaS products with an editorial edge, frontier-tech startups

---

## Colors

| Role | Name | Hex | Usage |
|------|------|-----|-------|
| Background (light) | Sage Cream | `#dfdfc1` | Page bg, primary foreground text on dark |
| Background (dark) | Deep Forest | `#091c1e` | Dark mode page bg, dark panel sections |
| Text / Foreground | Near-Black | `#0b0d0b` | Body text, headings, all main copy |
| Muted Text | Forest Teal | `#29564e` | Secondary text, labels, subdued UI |
| Accent / Primary | Teal Blue | `#1588b2` | CTA buttons, links, brand accent |
| Border | Warm Gray | `#b1b1a5` | Dividers, input borders, subtle separators |
| Status / Success | Emerald | `#10b981` | "All Systems Operational" dot, success states |
| Accent Yolk | Orange | `#f6833b` | Grid column highlight, rare accent pop |
| Light Surface | Off-White | `#fafafc` | Text on dark backgrounds |
| Dark Surface | Pitch Near-Black | `#171917` | Hero CTA button bg, dark inline elements |

**Color philosophy:** The sage cream `#dfdfc1` is the defining choice — warm, slightly desaturated, editorial rather than sterile. Pair with forest muted tones; reserve teal blue only for interactive elements. The design supports true CSS light/dark via `light-dark(#dfdfc1, #091c1e)` on the body. Dark mode swaps to deep forest teal, not black — keeps warmth in both modes.

---

## Typography

| Role | Font | Weight | Size (desktop) | Size (mobile) | Notes |
|------|------|--------|----------------|---------------|-------|
| Display / H1 | Sagittaire Display | 400 | `--type-3xl` ≈ 65px | fluid | Line height 0.9 (very tight), letter-spacing -3.9px |
| H2 | Sagittaire Display | 300 | `--type-lg` ≈ 21px | fluid | Normal letter-spacing |
| H3 | Sagittaire Display | 400 | `--type-lg` ≈ 21px | fluid | Used for feature card headings |
| Body / Paragraph | PolySans Var | 400 | `--type-base` ≈ 17px | fluid | Line height 1.414 |
| UI / Caption | PolySans Var | 500 | 12–13px | 12–13px | Nav links, button labels, small text |
| Muted / Secondary | PolySans Var | 400 | 13px | 13px | Footer links, system status |
| Monospace / Code | Berkeley Mono | variable | 13px | 13px | CLI commands, install scripts, code |

**Font source:** All three fonts are self-hosted woff2 at `/fonts/`:
- `SagittaireDisplay-Regular.woff2` (400) and `SagittaireDisplay-Extralight.woff2` (200)
- `SagittaireDisplay-ExtralightItalic.woff2` (extralight italic)
- `PolySans-variable.woff2` and `PolySansItalic-variable.woff2` (300–800 range)
- `TX-02-Variable.woff2` (Berkeley Mono, variable weight)

**Type scale:** Fluid clamp system via CSS custom properties:
```css
--type-xs:  clamp(0.69rem, 0.65rem + 0.11vi, 0.94rem);
--type-sm:  clamp(0.83rem, 0.77rem + 0.15vi, 1.13rem);
--type-base: clamp(1rem, 0.91rem + 0.22vi, 1.5rem);
--type-lg:  clamp(1.2rem, 1.04rem + 0.4vi, 2.1rem);
--type-xl:  clamp(1.44rem, 1.14rem + 0.75vi, 3rem);
--type-2xl: clamp(1.73rem, 1.18rem + 1.36vi, 4.5rem);
--type-3xl: clamp(2.07rem, 1.07rem + 2.5vi, 7rem);
--type-4xl: clamp(2.49rem, 0.69rem + 4.5vi, 11rem);
--type-5xl: clamp(2.99rem, -0.26rem + 8.1vi, 17rem);

--type-lh-tight:   1.1;
--type-lh-snug:    1.25;
--type-lh-normal:  1.414;
--type-lh-relaxed: 1.65;
```

**Key typographic move:** The H1 "Everything Is Changing" uses `--type-3xl`, tight line-height (0.9), and heavy negative letter-spacing (-3.9px). It reads like a magazine cover headline — not a software product page.

---

## Spacing & Layout

- **Grid system:** Fluid lens grid with `--lens-margin-ratio: 4.098vw` side margins and `--lens-cell-padding: clamp(0.75rem, 1.5vw, 1.5rem)` per cell
- **Max content width:** ~1200px
- **Section padding:** ~64px vertical on major sections; inner components ~24–32px
- **Base unit:** `--lens-grid-margin: 1rem`
- **Feature grid:** 4-column on desktop, collapses on mobile
- **Footer:** 5-column grid (Status/Legal | Product | Resources | Guides | Community)
- **Border radius:** 4px on small elements (nav CTA, tab buttons), 6–8px on larger panels, 8px on command pill
- **Nav layout:** Logo mark far left, text links center-right, Sign In + Get Started CTA far right

---

## Visual Style

- **No shadows anywhere.** Completely flat design. No `box-shadow`, no `drop-shadow`. Depth comes from color contrast and type scale.
- **Background grid:** Fixed-position SVG grid overlay at z-index 0, pointer-events none. Very subtle — structural, not decorative.
- **Texture pseudo-element:** `#marketing-root::before` uses a JPG texture (`footer-bg-inverted.jpg`) at 3% opacity with `mix-blend-mode: darken`. In dark mode switches to `mix-blend-mode: screen`. Creates a barely-perceptible grain/paper feel without being obvious.
- **Light/dark:** Uses native CSS `light-dark()` function for the body background. The page honors the OS setting automatically.
- **Borders:** `1px solid rgba(135, 139, 134, 0.12)` — near-invisible, warm-toned. Only appears on interactive elements.
- **Icons:** Minimal, functional — small SVG icons in navigation. No decorative iconography.
- **No gradients** on the light mode. Dark mode may use subtle color gradations in the teal palette.
- **Color contrast:** The sage cream / near-black pairing is high contrast and readable. The teal accent has sufficient contrast on both cream and dark surfaces.

### The Background Grid — The Subtle Identity Mark
The `background-grid` is a fixed SVG that tiles a faint grid across the entire viewport. It's invisible at a glance but adds a structural, technical underpinning — like graph paper or engineering notation. This is the visual element that makes the cream bg feel "designed" rather than just "off-white."

---

## Components

### Navigation
- Fixed/sticky at top; transparent background — sits over the cream page
- **Logo:** "amp" wordmark (custom logotype), left-aligned
- **Links (center-right):** Chronicle, Owner's Manual, Models, Pricing — all in PolySans Var 500, 12–13px
- **Auth actions:** "Sign In" (ghost, no bg) + "Get Started" (filled teal `#1588b2`, cream text, 4px radius, padding `4px 10px`)
- Nav items use standard `ring-offset-background focus-visible:ring-ring` Tailwind focus styles

### Hero
- Large-format serif headline: "Everything Is Changing" — Sagittaire Display 400, tight line-height, dramatic negative letter-spacing
- Subhead: small PolySans body copy introducing the product
- Single hero CTA: "Get Started →" — near-black `#171917` bg, off-white text `#fafafc`, 6px radius, 6px/12px padding, 16px text
- Centered or slight left-leaning layout; headline dominates at ~65px+

### Install / CLI Section
- Command pill: dark `#0b0d0b` background, rounded-lg (8px), mono font (Berkeley Mono), cream text
- Three platform tabs: Mac/Linux/WSL (active) | Windows | Homebrew — tab pattern with subtle active border
- Copy button beside command string
- Full install command: `curl -fsSL https://ampcode.com/install.sh | bash`

### Feature Cards
- 4-column grid of key feature descriptions
- Each card: Sagittaire Display H3 (400, ~21px) + PolySans body at ~17px
- No card borders or backgrounds — features float on the cream page bg
- Feature labels: "Ruthlessly On The Frontier", "Only What We Love", "Fast", "Extensible"

### Announcements / Chronicle List
- Dated list format — date label (muted/small) + Sagittaire Display title + one-line excerpt
- Left-column section label "NEW" in small caps
- Items are clickable rows, no card chrome
- Entries: "A Finer Librarian", "Dille", "Faster Deep Research & Build", etc.

### Agents Panel (Dark Section)
- Background: dark teal `#091c1e`, full-bleed width
- Shows live product UI: terminal window, agent conversation, sidebar
- Header: "Agents, Everywhere" in Sagittaire Display (light weight) on dark surface
- Sub-copy in light PolySans on dark
- This is the product-in-context "hero" for the app section of the page

### Testimonials
- Simple quote format: large-ish quote text + attribution (name, handle/role)
- No card chrome, no avatar — pure typography on cream bg
- Understated; reinforces editorial feel

### Footer
- 5 columns: left anchored with "All Systems Operational" green status dot + legal links; then Product, Resources, Guides, Community
- All PolySans 400, 12–13px, muted color `#29564e` or body color
- No background color — floats on cream
- Logo "amp" + status dot at bottom-left corner
- Simple, dense, text-only

---

## Interactions & Animation

- **Default transition:** `transition-colors` with `duration-150` on interactive elements
- **News card hover:** `translate` + `scale` at 180ms `cubic-bezier(0.22, 1, 0.36, 1)` (spring-like ease-out), plus `opacity` at 240ms `ease-out`
- **Card "trumpeter" element:** 260ms same spring easing — the card has a layered reveal with a foreground element animating separately
- **Sidebar:** 350ms `cubic-bezier(0.32, 0.72, 0, 1)` on transform + opacity (mobile slide-in)
- **Accordion:** `accordion-down`/`accordion-up` keyframes for height 0 → var(--bits-accordion-content-height)
- **Caret blink:** Custom `caret-blink` keyframe at 0%/70%/100% = opacity 1, 20%/50% = opacity 0.5 (soft blink, not harsh)
- **Status dot:** `ping` animation — scale 2 + opacity 0 at 75–100% (radial pulse on green operational dot)
- **Fade-in:** Simple opacity 0 → 1 used for page/component entrance
- **No parallax, no scroll-triggered animations visible on homepage**

---

## Tone & Personality

Amp feels like a frontier research publication that happens to be building software. The cream editorial palette, self-hosted display serif, and heavy negative-tracked headline "Everything Is Changing" project confidence without hype. It's neither minimalist startup nor corporate SaaS — it's a design-literate team signaling that they take craft seriously. The absence of gradients, glass effects, and shadows reads as restraint, not limitation. The product comes through in the embedded terminal UI, not in marketing metaphors.

---

## Notes & Reuse Tips

1. **Sage cream as the foundation.** `#dfdfc1` is the entire personality. It's not beige, not yellow, not gray — it sits between aged newsprint and sage. Don't substitute with a generic `#f5f5f5`; the warmth is load-bearing.

2. **Sagittaire Display is not available from Google Fonts.** It's a self-hosted proprietary typeface. Closest substitutes for the editorial high-contrast display feel: `Playfair Display` (more classical), `DM Serif Display` (lighter), or `Editorial New` if you have a license. The key characteristics to match: optical-size aware, thin-stroke serif, slightly condensed at large sizes.

3. **PolySans Var is also proprietary (Lettermatic).** Substitute with `Inter` (variable), `Plus Jakarta Sans` (variable), or `Geist` for a clean variable sans. The weight range 300–800 is important — the font switches between very light and medium weight.

4. **Berkeley Mono is a premium monospace.** Substitute: `JetBrains Mono` (variable), `Fira Code`, or `Geist Mono`. Amp uses it only for code/CLI contexts.

5. **The fluid type scale is portable.** The `--type-xs` through `--type-5xl` clamp system is framework-agnostic. Copy the CSS custom props and the only change needed is assigning the right token to each element role.

6. **Light/dark is baked in architecturally.** The `light-dark()` function requires no JS — it reads from `prefers-color-scheme`. The dark background `#091c1e` (deep teal, not black) keeps the brand warmth in dark mode. If reusing this palette in dark-only: use `#091c1e` as bg + `#dfdfc1` as primary text.

7. **Spring easing is the signature interaction.** `cubic-bezier(0.22, 1, 0.36, 1)` at 180–260ms for card hovers gives the page its kinetic quality without being showy. Use this consistently on any interactive card or list item.

8. **The background grid + texture combo.** The SVG grid creates technical authority; the 3% JPG texture adds tactile warmth. Together they make the cream bg feel intentional. If you can't do both, prioritize the texture — it's the subtler and more distinctive touch.
