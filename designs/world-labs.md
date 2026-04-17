# World Labs

## Meta
- **Source:** https://www.worldlabs.ai/
- **Style keywords:** editorial, minimal, dark-light contrast, medieval/engraving illustration, spatial, premium AI, serif headings
- **Best for:** AI product landing page, research lab, creative tech company, spatial/3D product showcase

---

## Colors

| Role | Name | Hex | Usage |
|------|------|-----|-------|
| Background | Off-white | `#f9f9fb` | Page background, nav background |
| Pure white | White | `#ffffff` | Card surfaces |
| Text primary | Near-black | `#2e2e38` | Headings, body text, nav links, footer |
| Text secondary | Grey 100 | `#9494a8` | Body paragraphs, subtitles, muted copy |
| Text muted mid | Grey 150 | `#73738c` | Supporting text |
| Text muted dark | Grey 200 | `#5f5f75` | Labels, secondary elements |
| Dark surface | Near-black | `#111111` | Dark sections (Marble Labs block) |
| Accent / CTA section | Steel blue | `#2a679c` | Full-bleed CTA/footer section background |
| Text on dark | Off-white | `#f9f9fb` | Text on dark or blue sections |

**Color philosophy:** Extremely restrained palette — essentially two neutrals (`#2e2e38` and `#f9f9fb`) plus a single blue accent. All visual richness comes from the illustrations, not the UI chrome.

---

## Typography

| Role | Font family | Weight | Size (desktop) | Line height | Letter spacing |
|------|-------------|--------|----------------|-------------|----------------|
| Display / H1 | Gilda Display | 400 | 64px | 71px (1.11) | -3.2px (-0.05em) |
| H2 | Gilda Display | 400 | 64px | 76.8px (1.2) | -3.2px (-0.05em) |
| H3 | roobert | 500 | 24px | 28.8px (1.2) | -1.44px (-0.06em) |
| Body large | roobert | 400 | 20px | 25px (1.25) | normal |
| Body / nav links | roobert | 500 | 16px | 24px (1.5) | normal |
| Body default | roobert | 400 | 16px | 24px (1.5) | normal |

**Font sources:**
- Gilda Display → Google Fonts
- roobert → custom/licensed (Fontshare or direct license)

**Key typographic moves:**
- Headings are serifed (Gilda Display), elegant, thin-weight — feels editorial/classical
- All body/UI text is roobert (geometric sans) — clean contrast with the serif headings
- Aggressive negative letter-spacing on headings (`-0.05em`) tightens the large type beautifully
- H3 on dark sections uses `#f9f9fb` (inverted)

---

## Spacing & Layout

- **Grid:** free-flow, full-bleed sections
- **Max content width:** ~1200px (visually estimated; no explicit CSS container found)
- **Section horizontal padding:** 40px left/right
- **Section vertical padding:** 64px top/bottom (standard sections)
- **Hero:** no vertical padding — illustration overflows to fill viewport
- **Card internal padding:** 64px 48px
- **Card gap (grid):** ~24px
- **Base unit:** 8px implied
- **Border radius:** cards 16px, buttons fully pill (`border-radius: 9999px`), sections 16px (CTA block)

---

## Visual Style

- **Shadows:** none — completely flat UI, depth comes from illustration only
- **Borders:** none visible on cards; hairline implied on nav via transparent border that activates on scroll
- **Background texture:** `slidePattern` animation — a subtle grid/diagonal texture slides horizontally at `5.66px` offset (suggests 45° grid at 4×4 unit, creating a very faint animated blueprint/graph-paper feel on specific elements)
- **Images:** full-bleed `object-fit: cover` within rounded containers; no image filters
- **Icons:** minimal — arrow circles on CTA buttons; custom bird-wing logo mark
- **Illustration style (the signature element — see below)**

### Illustration Style — The Core Identity

There are two distinct illustration modes used throughout:

**Mode 1 — Mechanical Pencil Sketch (Hero)**
- Isometric pencil-drawn machine (marble run / Rube Goldberg device) with architectural/medieval proportions
- Rendered in grey graphite pencil with strategic copper/bronze metallic ink accents
- Fades at the edges into the off-white background with no hard crop (feathered/vignette blend)
- Highly detailed cross-hatching and construction lines visible — feels like a Renaissance inventor's notebook
- Interactive: a 3D globe sits at the center, animated with a generative world render on click

**Mode 2 — Etching + Painterly Color (Content sections & CTA)**
- Classical engraving linework with painterly watercolor/gouache color fills
- Subjects: medieval stone ruins, mountain landscapes, dramatic cloudscapes, figure portraits
- Color palette: warm sepia/amber, muted cobalt blue, dusty sage, parchment yellow
- These images are used as full-bleed card backgrounds with text overlaid directly
- The CTA section uses a full-bleed engraving of a crystal sphere hovering over a mountain village

**How to replicate this aesthetic:**
- Commission or generate illustrations in "Leonardo da Vinci sketchbook" + "19th century scientific engraving" style
- For AI generation: prompt with "isometric pencil sketch, mechanical device, crosshatching, copper ink accents, white background, fading edges, Renaissance notebook style"
- Card images: "classical engraving, watercolor fills, warm sepia palette, [subject], high detail"

---

## Components

### Navigation
- Fixed top, same background as page (`#f9f9fb`)
- Logo left (small bird-wing mark + wordmark, `#2e2e38`)
- Links center: roobert 500 16px, `#2e2e38`, no underline, no hover color change observed
- CTA right: pill button, dark fill (`#2e2e38` bg, `#f9f9fb` text), padding 16px 20px
- No bottom border at rest; transparent border present in CSS (likely activates on scroll)
- No mobile hamburger visible at desktop width

### Hero / Above the fold
- Layout: headline top-left, description text top-right, full-bleed illustration below spanning both columns
- H1 two lines: line 1 dark (`#2e2e38`), line 2 muted grey (`#9494a8`) — creates a visual hierarchy within the single heading
- Illustration is large (~800px tall), centered, bleeds beyond the text area
- "CLICK TO EXPLORE" tooltip appears on the illustration: dark pill `#2e2e38` bg, white text, uppercase, small tracking
- No explicit CTA button in hero — the illustration itself is the interactive element

### Buttons
- **Primary (nav CTA):** pill, `#2e2e38` fill, `#f9f9fb` text, 16px 20px padding, roobert 500 16px
- **Secondary (inline CTA):** pill, `#2e2e38` fill, `#f9f9fb` text, with circled arrow icon right of text
- **Ghost / text link:** plain text with `→` arrow, no border, roobert regular

### Cards (Marble Labs grid)
- Dark section background (`#111111`)
- Cards: `#ffffff` surface, 16px radius, 64px 48px padding, no border, no shadow
- Full-bleed image fills top portion of card, text overlaid at bottom
- Image overlay: dark gradient from bottom so white text is readable
- Tags/category labels at bottom-left of image: uppercase, small font, spaced out, appear as light-coloured pill labels
- "Read more →" link at card bottom: roobert, white, arrow suffix

### Image + Text split (About section)
- 50/50 split: illustration left, text content right
- White card surface wraps the text side (`#ffffff`, 16px radius)
- Illustration bleeds to left edge, no radius on image side
- Body text in `#9494a8` (muted), heading in `#2e2e38`

### Footer / CTA Section
- Full-bleed blue (`#2a679c`) block with 16px border radius (floats above page footer)
- Large serif heading centered in white
- Single pill CTA button (dark) centered below heading
- Navigation links listed vertically on left side of the blue section
- Engraving illustration fills the right ~60% of the blue block as background image
- Page footer below: plain `#f9f9fb` bg, small text, World Labs logo left, social icons right

---

## Interactions & Animation

- **Default transition:** `all` (no duration specified in computed style — likely 150–200ms ease inherited from Tailwind defaults)
- **Hover effects:** subtle; no dramatic transforms observed — likely opacity or color shifts
- **Scroll animations:** illustrations appear to load/fade in on scroll (Next.js + likely Framer Motion or CSS scroll-driven)
- **`slidePattern` animation:** animates `background-position` from `0px 0px` → `5.66px 0px` — slides a repeating diagonal grid texture subtly. `5.66 ≈ √(4²+4²)` suggesting a 4px grid rotated 45°. Used on a specific textured element (likely the hero background or a section divider)
- **`accordion-down` / `accordion-up`:** standard accordion open/close for FAQ or expandable content
- **Hero globe:** interactive 3D world render activates on click of the central sphere in the hero illustration — the signature interaction of the site
- **Page transitions:** standard Next.js (no custom transition observed)

---

## Tone & Personality

Authoritative and quietly romantic — like a scientific atlas from the age of exploration. The sans-serif UI is crisp and modern but the serif headings and hand-drawn illustrations pull the whole experience toward something ancient and weighty. It feels like a lab that takes itself seriously without being cold; the medieval illustrations signal imagination and craft rather than corporate polish. The restraint in the color palette makes every illustration hit harder — the page earns visual richness through the art, not the UI.

---

## Notes & Reuse Tips

- **The two-tone heading trick is instantly reusable:** split H1 into two lines where line 2 uses `--grey-100` (`#9494a8`) — costs nothing, adds huge visual depth.
- **Illustration-as-hero works because the illustration IS the product demo** — don't copy this pattern unless the illustration has genuine interactive value. A static version would feel hollow.
- **The off-white background (`#f9f9fb`)** is warmer and softer than `#f5f5f5` — important detail that prevents the page from feeling clinical.
- **Roobert** is a licensed font (Fontshare). Substitute: `Inter` for neutral sans, `DM Sans` for slightly warmer feel.
- **Gilda Display** is free on Google Fonts. Good alternative serifs in the same vein: `Playfair Display`, `Cormorant Garamond`, `IM Fell English`.
- **The engraving illustration style** is the single most distinctive element — without it, this design would be a competent-but-generic minimal AI site. Prioritize sourcing or generating this style of art if replicating.
- **Dark section contrast:** the `#111111` Marble Labs block creates a strong visual break — use this pattern to reset reader attention mid-page.
- **No shadows anywhere** — the design relies entirely on background color contrast for depth. Don't add drop shadows; they'd break the aesthetic.
