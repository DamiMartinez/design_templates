# Hermes Agent

## Meta
- **Source:** https://hermes-agent.nousresearch.com/
- **Style keywords:** brutalist-editorial, electric blue monochrome, engraving illustration, serif display, uppercase everywhere
- **Best for:** AI agent/product landing page, open-source dev tool, research-lab site, desktop app marketing page

---

## Colors

| Role | Name | Hex | Usage |
|------|------|-----|-------|
| Primary | Electric blue | `#0000F2` | Page background, dominant brand color |
| Secondary | — | — | (none; blue carries all brand duty) |
| Background | Electric blue | `#0000F2` | Hero, most sections |
| Surface | Off-white | `#F5F5F5` | Feature-card section bg, download buttons |
| Text primary | Off-white | `#F5F5F5` | Headings, nav, body on blue bg |
| Text secondary | Blue (on white) | `#0000F2` | Headings/body inside white surface sections |
| Accent | Pure white | `#FFFFFF` | Card panels, button fills |
| Border | Hairline off-white | `rgba(245,245,245,0.15)` approx | Card dividers, panel outlines |

Effectively a **two-tone flip system**: blue-bg/white-text sections alternate with white-bg/blue-text sections — no third color anywhere. Halftone/engraving illustrations are duotone, always rendered in the same blue as the background (tinted lighter/darker, never a new hue).

---

## Typography

| Role | Font family | Weight | Size (desktop) | Size (mobile) | Transform |
|------|-------------|--------|----------------|---------------|-----------|
| Display / H1 | Custom serif ("displayFont", Times New Roman fallback) | 300 | ~107px / lh ~95px, ls ~3.2px | scales down via clamp | uppercase |
| H2 | Same serif | 300 | ~52px / lh ~52px | scales via clamp | uppercase |
| H3 | Same serif | 300 | large, section-title scale | scales via clamp | uppercase |
| Body | Custom monospace ("monoFont", Courier New fallback) | 400 | ~14.6px / lh ~22px, ls ~1.5px | same | uppercase |
| Caption / small | monospace | 400 | ~12-14px | same | uppercase (eyebrow labels like "OPEN SOURCE • MIT LICENSE") |
| Label / tag | serif (nav/buttons), extrabold | 800 | ~24px / lh ~37px, ls ~0.7px | smaller | uppercase |
| Monospace / code | system-ui/sans fallback in code snippets | 400 | 14px / lh 21px | 14px | none |

**Font source:** self-hosted custom variable fonts (`displayFont` for serif display, `monoFont` for body/mono) with system fallback stacks (Times New Roman / Courier New)
**Line height:** headings tight (~0.9-1.0x), body loose (~1.5x)
**Letter spacing:** headings +0.02-0.03em (uppercase serif needs the extra air), body/labels +0.1em uppercase tracking

Notable pairing: **all-caps serif Didone-style display type** (feels like an engraved masthead) contrasted with **all-caps monospace for every UI/body role** — nav, paragraphs, labels, buttons. Nothing on the page is lowercase or unstyled default weight.

---

## Spacing & Layout

- **Grid:** free-flow single column, 3-col feature-card grid mid-page
- **Max content width:** full-bleed sections (no visible max-width cap on hero), content padding scales via CSS `clamp()`/custom `--u` unit
- **Section padding (vertical):** large, ~120-160px desktop equivalent
- **Component gap:** generous, 24-40px between stacked elements
- **Base unit:** custom fluid unit variable (`--u`) driving `clamp()` sizing throughout — not a fixed 8px grid
- **Border radius:** none — all corners square (buttons, cards, panels)

---

## Visual Style

- **Shadows:** none observed; flat design throughout
- **Borders:** hairline 1px, low-opacity white, used to separate feature-card columns and frame the product-screenshot mockup
- **Images:** blue-duotone halftone/engraving-style illustrations (mythological figure motif — winged messenger/Hermes imagery) used as large decorative art, not photography; a light-mode product screenshot (desktop app UI) is dropped into a bordered browser-chrome-style frame as the one non-blue visual
- **Icons:** minimal — small OS glyphs (Apple/Windows/Linux) inline in download buttons, small brand mark (illustrated portrait) as favicon/logo
- **Texture / background:** engraving/etching linework (radiating hairline rays, halftone dot-shading) as the dominant decorative texture; giant cropped wordmark ("HERMES") used as a closing footer flourish, echoing the tinybird-style oversized-logo pattern

---

## Components

### Navigation
Static top bar on blue background: "NOUS" and "DOCS" text links left, centered two-line serif wordmark logo ("HERMES AGENT") with small social icons (Discord/X/GitHub) beneath it, "PRODUCTS ▾" dropdown and "INSTALL →" link right. All nav text uppercase serif, extrabold, underline-on-hover.

### Hero / Above the fold
Split layout: left side has small uppercase eyebrow ("OPEN SOURCE • MIT LICENSE"), giant 3-line uppercase serif headline, then a stacked CTA block — white pill/rectangle "DOWNLOAD FOR MAC OS" button with Apple glyph, followed by a bordered "install via terminal" panel with OS tabs (macOS/Linux vs Windows) and a copyable `curl | bash` command. Right side is a full-bleed blue-duotone engraving illustration of a winged mythological figure with radiating line-ray effects, bleeding off the viewport edge.

### Buttons
- Primary: filled white/off-white rectangle, blue uppercase serif or mono label, square corners, icon + text inline (e.g. OS logo + "DOWNLOAD DESKTOP APP")
- Secondary: same white rectangle style used for "INSTALL VIA TERMINAL", visually equal weight to primary — buttons presented as an equal-weight row of 3 (Mac/Windows/Terminal) rather than a primary/secondary hierarchy
- Ghost / text: plain uppercase serif nav links, underline-on-hover, no border box

### Cards
Feature/numbered-step cards ("#1 CONNECT", "#2 REMEMBER", "#3 SCHEDULE"): white background section, blue uppercase serif headline per card, thin vertical hairline dividers between columns, each card topped with a small illustrated icon (portrait/face motif) and containing a blue-duotone halftone photo/illustration below the heading. A small "FEATURE / PREVIEW" toggle pill sits top-right of the card grid.

### Forms / Inputs
Terminal-style command panel: white rounded-corner-free box, tab switcher for OS choice, monospace command text with a copy-icon button on the right — no traditional form inputs shown on homepage.

### Footer
Blue background, small illustrated logo mark top-left, giant cropped uppercase serif wordmark ("HERMES") spanning full width as a bottom-edge branding flourish (matches the oversized-logo pattern seen in other terminal/dev-tool sites), faint watermark illustration layered behind it, small mono metadata bottom corners ("HERMES AGENT v0.21.1" left, "NOUS RESEARCH / MIT LICENSE · 2026" right with brand icon).

---

## Interactions & Animation

- **Default transition:** standard link/button hover transitions (underline reveal on nav/text links)
- **Hover effects:** underline slide-in on text links; button hover likely a subtle fill/opacity shift (not sampled in detail)
- **Scroll animations:** not confirmed from static inspection; page reads like it could support scroll-triggered reveals given the section-by-section illustration reveals, but not verified
- **Page transitions:** none
- **Loading state:** not observed

---

## Tone & Personality

Confident, mythic, and uncompromisingly monochrome — the single electric-blue-and-white palette combined with engraved-illustration imagery gives it the feel of a limited-edition print or record sleeve rather than a typical SaaS page. The all-caps serif-plus-mono type system reads as authoritative and slightly antique, deliberately at odds with "AI agent" being a bleeding-edge software category — that tension (classical engraving + terminal commands) is the whole personality.

---

## Notes & Reuse Tips

- The core trick to steal: **one saturated brand color (here `#0000F2`) used for both background AND as the tint for all illustration work** — nothing else needs to match a palette because there's only one hue plus white/black-equivalent.
- Alternating full-bleed blue-bg and white-bg sections (rather than a persistent dark or light mode) creates rhythm and lets duotone illustrations "invert" between sections without extra design work.
- All-caps serif display + all-caps mono body is a strong, easy-to-clone pairing — resist adding a third typeface or breaking the uppercase discipline anywhere.
- Square corners, no shadows, hairline borders only — matches other terminal/dev-tool sites in this library ([tinybird.md](tinybird.md)); the giant cropped wordmark footer is the same flourish tinybird uses, again only works with a short brand name.
- Numbered feature cards (`#1`, `#2`, `#3`) with a "FEATURE / PREVIEW" toggle is a cheap, reusable way to present a 3-part value prop without heavy custom UI.
- Skip: the light-mode product-screenshot mockup breaks the monochrome discipline — only use a full-color screenshot if you have a real product to show, otherwise stick to the illustration/typography system.
