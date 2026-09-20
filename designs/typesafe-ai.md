# TypeSafe AI

## Meta
- **Source:** https://typesafe.ai/
- **Style keywords:** retro-futurist, terminal brutalism, early-GUI, dithered, editorial grotesk, technical, pink monochrome, data-heavy
- **Best for:** AI research labs, developer infrastructure, model launches, technical product storytelling, experimental startup landing pages

---

## Colors

| Role | Name | Hex | Usage |
|------|------|-----|-------|
| Primary | System Pink | `#f386a1` | Long-form product section, data-panel fields, dominant brand color |
| Secondary | Machine Sage | `#abbab9` | Blog section background and cool neutral contrast |
| Background | Paper White | `#fefefe` | Hero, page background, navigation cells |
| Surface | Pure White | `#ffffff` | Faux application windows, plots, content panels |
| Text primary | Soft Ink | `#1e1e1edb` | Most headings and body copy; near-black at 86% opacity |
| Dark surface | Terminal Black | `#1e1e1e` | Window title bars, FAQ, footer, reversed CTA |
| Text on dark | Paper White | `#fefefe` | FAQ, footer, dark title bars |
| Text secondary | Terminal Grey | `#dedede` | Window-bar metadata and muted UI copy |
| Hover accent | CRT Magenta | `#d45bb6` | Navigation hover fill, selected/highlighted editorial labels |
| Data accent | Signal Teal | `#09aea1` | Featured artwork and isolated chart/data details |
| Success | System Green | `#03aa5c` | Positive data series and status accents |
| Border | Black | `#000000` | Window outlines, chart rules, registration marks |

**Color philosophy:** The identity is carried by one unapologetically large field of dusty pink, not a conventional accent-on-neutral system. White, soft black, and grey recreate old workstation UI; sage provides one full-width section break. Teal, green, magenta, and blue appear only inside data graphics or tiny state labels. Do not turn the supporting colors into broad gradients.

---

## Typography

| Role | Font family | Weight | Size (desktop) | Size (mobile) | Transform |
|------|-------------|--------|----------------|---------------|-----------|
| Display / H1 | Die Grotesk C Medium | 500 | 150px / 120px | 54px / 43.2px | Capitalize |
| H2 | Die Grotesk C Medium | 500 | 64px / 57.6px | 33px / 29.7px | Capitalize |
| CTA heading | Die Grotesk C Medium | 500 | 64px / 57.6px | 28px / 25.2px | Capitalize |
| H3 / blog title | Die Grotesk C Medium | 500 | 48px / 43.2px featured; 30px / 27px small | 30px / 27px | Capitalize |
| Body large | Die Grotesk C Regular | 400 | 22px / 26.4px | 22px / 26.4px | None |
| Body / card copy | Die Grotesk C Regular | 400 | 17px / 20.4px | 17px / 20.4px | None |
| Technical label | JetBrains Mono | 300 | 10px / 12px | 10px / 12px | Capitalize |
| FAQ label | JetBrains Mono | 300 | 13px / 15.6px | 13px / 15.6px | Capitalize |
| Window / terminal UI | LisaTerminal Paper 2X3Y Medium | 500 | 18–20px / 18–20px | 14–18px / 14–18px | None |
| Footer | Die Grotesk C Regular | 400 | 15px / 15px | 15px / 15px | Mixed |

**Font source:**
- Die Grotesk C Regular/Medium → self-hosted proprietary webfonts
- LisaTerminal Paper 2X3Y Medium → self-hosted display bitmap/terminal face
- JetBrains Mono → Fontshare/Google-hosted webfont
- Inter and SF Pro Variable appear only in small supporting glyphs and simulated system UI

**Line height:** display `0.8`, H2 `0.9`, large body `1.2`, card body `1.2`

**Letter spacing:** display `normal`; body `0.05em`; technical labels `0.05em`; navigation `0.03em`

**Key typographic moves:**
- The 150px display type is compressed vertically with a `0.8` line height, producing dense, poster-like blocks rather than airy SaaS headlines.
- Headings use CSS capitalization rather than all caps. Body copy is unusually tracked (`0.05em`), helping it sit beside bitmap and monospace UI without feeling generic.
- Tiny mono labels establish hierarchy above otherwise borderless sections. The terminal face is reserved for artifacts that should feel like software, not for normal prose.

---

## Spacing & Layout

- **Grid:** modular 12-column feel built from a 1240px desktop frame; common spans are 400px, 620px, 820px, and 1240px
- **Max content width:** 1240px
- **Desktop gutters:** 100px at a 1440px viewport
- **Mobile gutters:** 10px for display frames; 20px for prose and card content
- **Section padding (vertical):** usually 100px; headline frames commonly use 20–60px internal separation
- **Component gap:** 20px for compact grids, 50px for content groups, 100px between major modules
- **Base unit:** 10px
- **Border radius:** predominantly 0; occasional 4px image/data viewport only
- **Desktop split patterns:** 620/620 for paired data cards; 820/270 for featured blog plus side posts; 820/190 for prose plus encoded-data marginalia
- **Responsive behavior:** two-column modules become a single vertical stack below 810px; the 1240px frame becomes full width, display type scales down sharply, and decorative side content may remain deliberately clipped off-canvas

The layout is framed by tiny L-shaped corner marks, dotted field edges, short vertical rules, and glyph pairs such as `∵ ⩆`. These registration marks replace conventional section borders and make the page resemble a plotted technical sheet.

---

## Visual Style

- **Shadows:** none; depth comes from hard black title bars, overlapping windows, and color-field changes
- **Borders:** crisp 1px black/grey rules on faux windows and charts; many editorial cards use only one vertical rule or corner marks
- **Images:** square-cornered and diagrammatic; product imagery looks like screenshots from an early workstation rather than polished app mockups
- **Icons:** custom angular TypeSafe mark, tiny chevrons, square accordion arrows, text glyphs, and pixel/system symbols
- **Texture / background:** dense 1px halftone and dither fields, noise clouds, scan-like dots, encoded strings, and registration marks
- **Color blocking:** white cloud hero → long pink product narrative → sage blog block → near-black FAQ/footer
- **Decorative data:** base64 strings are used as visible marginalia, including one vertical line beside the hero and encoded blocks beside text sections

### Graphic Language — The Signature Element

The homepage combines three visual eras:

1. **Dithered synthetic atmosphere:** A full-width animated GIF of hot-pink clouds against pale cyan fades into the white hero. The image has obvious raster dots and color reduction rather than photoreal polish.
2. **Early desktop GUI:** Black title bars, grey panels, white document windows, checkbox rails, monospaced labels, and overlapping model cards evoke classic Mac/Lisa workstation software.
3. **Scientific plotter sheet:** Data plots, benchmark bars, encoded strings, corner crop marks, fine rules, and sparse captions make the page feel measured and machine-readable.

To reproduce the look, dither imagery before use, keep pixel edges crisp, use flat color fills, and compose illustrations from real data/UI structures. Avoid soft glass panels, glossy 3D renders, rounded SaaS cards, and ornamental gradients.

---

## Components

### Navigation
- Static, edge-to-edge, and only 36px tall on desktop; it scrolls away rather than sticking
- Brand cell hugs the far left, primary links form a centered cluster, and account actions align to the far right
- Each item is an independent white rectangular cell with 6px horizontal and 8px vertical padding; no radius, border, or shadow
- Text is Die Grotesk C Medium, 18px/18px, weight 500, `0.03em` tracking
- Primary action uses a Terminal Black cell with white text
- White navigation cells fill with CRT Magenta on hover using a 200ms custom easing
- Mobile keeps the same thin desktop-strip concept rather than introducing a hamburger; low-priority items are hidden, leaving a tightly packed subset of links

### Hero / Above the fold
- Full-width dithered pink-cloud GIF occupies the atmospheric upper layer and fades into white
- A floating 400px-wide retro news window sits over the clouds with a black title bar, grey content area, and terminal typography
- The editorial frame is 1240px wide with corner registration marks and 100px side gutters
- Eyebrow line: 17px grotesk copy joined by a long dotted leader (`Introducing Jev ........ Intelligence beyond chat`)
- H1: 150px/120px on desktop, 54px/43.2px on mobile; left aligned but visually fills the frame
- A 10px JetBrains Mono base64 string runs vertically down the left side
- Two oversized underlined text CTAs sit beneath the headline with wide spacing: Join Waitlist and Join Discord

### Buttons
- **Primary nav:** square Terminal Black block, white 18px label; hover toward magenta
- **Editorial CTA:** no container; 64px display text with a hard underline and triple-chevron marker. Mobile scales this to 28px
- **Secondary / inline:** plain text underline for references such as `(Proof)`; underline properties and color transition over 500ms
- **Avoid:** pills, gradients, rounded corners, shadows, and icon circles

### Cards
- Product cards are bento-like frames rather than floating surfaces. Use thin crop marks, a top-left black label tab, pink dotted fields, and embedded white/grey data windows
- Desktop data modules use two 620px columns or one full-width 1240px panel; mobile stacks them
- Feature copy sits below each diagram and is separated by a short vertical rule, not a filled card background
- Benchmark comparison uses side-by-side terminal windows: white for TypeSafe, light grey for LLMs
- Blog layout uses one large 820px illustrated feature and two 270px text stories; mobile removes the large feature image and stacks all stories as text
- All cards stay flat and square. Any visual layering should come from intentionally overlapping faux windows

### Forms / Inputs
- No conventional marketing form appears on the homepage
- If the system is extended, style inputs like the simulated desktop UI: white or `#dedede` field, 1px black outline, 0 radius, terminal label above, and a strong magenta or teal focus indicator
- Do not use floating labels, soft grey pills, or large rounded controls

### FAQ / Accordion
- Full-width Terminal Black section with white content
- Questions form a narrow left column and use JetBrains Mono 13px/15.6px
- Each row is marked by a dotted left rule and a small square outlined chevron control
- Expanded answers switch to Die Grotesk C Regular at 22px/26.4px, preserving the editorial/technical font contrast
- The right side is intentionally sparse, holding a base64 block and angular logo inside corner marks

### Footer
- Continues the Terminal Black FAQ background so the transition feels seamless
- Oversized TypeSafe logo is centered in a large, sparse field
- A single base64 string sits above the legal row
- Bottom row distributes copyright left, legal links near center, and social/contact links right
- Footer text is 15px/15px with no columns, cards, borders, or background shift; mobile wraps it into a compact left-aligned stack

---

## Interactions & Animation

- **Navigation transition:** color, background, border-radius, and corner-shape at `200ms cubic-bezier(0.12, 0.23, 0.5, 1)`
- **Text-link transition:** color and underline properties at `500ms cubic-bezier(0.12, 0.23, 0.5, 1)`
- **Hover effects:** flat color replacement rather than lift; nav cells switch from white to magenta, while editorial links emphasize their underline
- **Hero motion:** looping dithered cloud GIF; no parallax is needed
- **Product motion:** looping GIF/MP4 clips inside faux windows, including rotating dithered forms and live comparison/error demonstrations
- **Data animation:** horizontal benchmark indicators animate through custom transform keyframes
- **Accordion:** question rows expand/collapse in place and invert the square chevron direction
- **Scroll animations:** none observed as a primary pattern; sections should feel laid out like one continuous technical poster
- **Page transitions:** standard navigation, no cinematic transition
- **Loading state:** not prominently represented; reuse monochrome terminal rows or a dithered placeholder instead of a soft shimmer

---

## Tone & Personality

TypeSafe AI feels like a speculative research poster rendered on a 1980s workstation. It is technical and assertive without adopting the usual black-and-neon AI aesthetic: dusty pink supplies warmth and memorability, while terminal artifacts signal machine-level rigor. The enormous grotesk headlines are bold and promotional, but the plots, encoded strings, and tiny labels keep the page analytical. The result is playful in form and serious in content.

---

## Notes & Reuse Tips

1. **Pink is the environment, not a highlight.** The long `#f386a1` field carries most of the product story. Using it only for buttons will lose the identity.
2. **The terminal font is load-bearing.** LisaTerminal Paper 2X3Y gives the faux OS windows their period specificity. If unavailable, use a bitmap face such as `Departure Mono`, `DOS VGA`, or `VT323`; do not substitute a polished coding font for window chrome.
3. **Use JetBrains Mono separately.** Technical captions are clean and contemporary; keeping them distinct from the bitmap UI prevents the entire page from becoming costume design.
4. **Respect the extreme display metrics.** The desktop H1 is 150px with a 0.8 line height, while mobile drops to 54px but keeps the same ratio. A normal 1.1–1.2 heading line height will feel far too polite.
5. **Registration marks unify the page.** Corner brackets, dotted borders, short rules, and mirrored `∵ ⩆` glyphs provide continuity between otherwise different color sections. They are more important than adding card borders everywhere.
6. **Build graphics from data.** The most convincing illustrations are actual plots, bars, labels, and windows. Decorative pseudo-code alone will feel generic.
7. **Allow controlled clipping on mobile.** The source keeps some encoded marginalia and technical decoration off-canvas. Preserve the impression of a larger machine sheet, but keep real content and controls inside 20px gutters.
8. **Use real motion sparingly.** A few looping raster/video regions make the page feel alive; animating every label or section would undermine the measured, poster-like composition.
9. **Proprietary font substitutions:** use `Arial Narrow` or `Roboto Condensed` only as rough fallbacks for Die Grotesk; closer design-led options include `Söhne Schmal`, `Helvetica Now Display`, or `Archivo`. Match the tight metrics before matching exact letterforms.
10. **Accessibility caution:** retain the original high contrast on dark sections, but test Soft Ink over System Pink carefully at small sizes. Do not put long prose in the pale grey terminal color.
