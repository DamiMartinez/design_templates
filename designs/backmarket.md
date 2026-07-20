# Back Market (backmarket.es)

## Meta
- **Source:** https://www.backmarket.es/ (comparison page: `/es-es/c/iphone/iphone-15-vs-iphone-14`; catalog: `/es-es/search?q=...`; PDP: `/es-es/p/[slug]`)
- **Style keywords:** Trustworthy e-commerce, flat, near-black + off-white base with pastel accent chips, editorial serif accents, dense filter/config UI, sustainability-forward
- **Best for:** Refurbished/marketplace e-commerce, comparison/buying-guide content hubs, product configurators with condition/storage/color variants

---

## Colors

| Role | Name | Hex | Usage |
|------|------|-----|-------|
| Primary text / CTA | Near-Black | `#110F15` | Body text, primary "Comprar" buttons, price emphasis |
| Background | Off-White | `#F8F9FC` | Page background (cool, very light gray-blue) |
| Surface | White | `#FFFFFF` | Cards, header, footer, popovers |
| Surface alt | Cool Gray | `#EDEFF3` / `#F2F3F7` | Secondary surfaces, promo tiles, disabled states |
| Info accent | Light Blue | `#D9E4FC` | Info/reassurance boxes (shipping, warranty, trust) |
| Selected accent | Pale Lavender | `#F6F2FD` | Selected radio card background (condition, battery, storage pickers) |
| Success / savings | Mint bg `#94F5BC` · text `#006B40` | Savings badge ("Ahorra X €"), positive price-trend arrows |
| Link / decorative accent | Berry Magenta | `#9D3963` | "Ofertones" nav link, occasional decorative accent text |
| Campaign accent | Crimson Red (gradient, promo-only) | `~#C4122F → #7A1018` | Homepage hero campaign banners — swapped per promotion, not a stable brand color |
| Highlight strip | Lime/Chartreuse | `#E3F77E` | Sitewide top promo bar, editorial ("Tecnoteca") section highlight background |
| Border | Warm Light Gray | `~#D9DBE0` | Hairline borders on ghost buttons, dividers, input outlines |

**Color philosophy:** The functional UI (nav, buttons, cards, filters) is almost entirely near-black `#110F15` on off-white `#F8F9FC` — deliberately neutral and "boring" so it reads as trustworthy and doesn't compete with product photography. Color is reserved for meaning: mint green = money saved, light blue = reassurance/logistics, lavender = "this is your current selection." Red and lime are campaign/seasonal accents layered on top, not core brand identity — treat them as swappable promo skins.

---

## Typography

| Role | Font family | Weight | Size (desktop) | Size (mobile) | Transform |
|------|-------------|--------|----------------|---------------|-----------|
| Display / editorial headline | IvarSoft (serif) | 600 | ~56px | fluid, scales down | none |
| H2 / section heading | BMDupletDSP | 600 | 28px | ~20-24px | none |
| Body / UI text | BMDupletTXT | 400 | 16px | 16px | none |
| Small / caption / nav link | BMDupletTXT | 400–600 | 12–14px | 12–14px | none |
| Bold emphasis (prices, labels) | BMDupletTXT | 600–900 | inherits | inherits | none |

**Font source:** All self-hosted woff2 from `ds.statics.backmarket.com/fonts/`. Three families:
- `BMDupletTXT` — body/UI text sans, weights 400/italic. Fallback `HelveticaTXT` (metrics-adjusted local Helvetica via `ascent-override`/`size-adjust`, so layout doesn't shift before the webfont loads).
- `BMDupletDSP` — display/heading sans, semibold 600. Fallback `HelveticaDSP` (same metrics-matched-local-Helvetica trick).
- `IvarSoft` — a licensed serif (Production Type foundry), semibold 600 + italic, plus an `IvarSoftGreek` variant for Greek script. Used sparingly for big editorial/marketing punchlines (e.g. homepage "Donde el mundo compra tecnología reacondicionada"). Fallback: generic `serif`.

**Line height:** body `24px` (1.5) · display headline tight (~1.0–1.1) · H2 `40px` (1.43)
**Letter spacing:** normal throughout — no tracked-out headings or uppercase labels

**Key typographic move:** Two-sans-plus-one-serif system. The sans pair (BMDupletTXT/DSP) does 95% of the UI and feels like a clean, slightly rounded system sans — unremarkable on purpose. IvarSoft serif is dropped in only for a handful of big marketing/editorial headlines, giving those moments a warmer, more "human/press" feel against an otherwise clinical e-commerce UI.

---

## Spacing & Layout

- **Grid:** Fluid, content-width container (~1280–1568px observed), free-flowing card grids rather than a strict numbered column system
- **Max content width:** ~1240px for text/article content; wider for product grids
- **Section padding (vertical):** ~24–32px between major blocks; article/editorial sections looser
- **Component gap:** 8–24px depending on density (tight in filter pill rows, looser in product grids)
- **Base unit:** 4px (radii, paddings all multiples of 4)
- **Border radius:** 6px standard (buttons, inputs, cards, popovers) · 2px on tiny badges/chips · fully round on avatar/icon buttons

---

## Visual Style

- **Shadows:** none/near-none. Popovers and sticky elements rely on a hairline border or just being on a white surface over the off-white page — not drop shadows.
- **Borders:** hairline, low-contrast gray; used on ghost/outline buttons ("Renove"), input focus states, and to separate footer sections. Product cards themselves have **no border, no shadow, no background** — they float directly on the page background (image + text stack only).
- **Images:** product photography is full-color, clean studio shots on transparent/white; editorial article images are natural lifestyle photos (hands, real environments) with standard rounded corners.
- **Icons:** simple outline icons (truck, shield, location pin, heart, magnifier) — functional, not decorative, always paired with a text label in info boxes.
- **Texture / background:** flat color throughout, with one recurring decorative motif — soft pastel gradient tiles (lavender → pink → blue) used behind "how we refurbish" / reconditioning-step callouts and as circular sticker badges ("Reacondicionado por expertos") overlaid on product hero images.

---

## Components

### Navigation
- Fixed/sticky white header, two-tier: a slim utility row (trust link, repair/care, "Tecnoteca" content hub, postcode selector, locale/flag) above the main row (logo left, search bar center, "Renove" trade-in button + help link + account + cart icons right).
- Below that, a horizontal category row (Ofertones in berry/magenta with a sparkle icon as the one colored nav item, then Móviles/Portátiles/Tablets/Consolas/... in near-black, plus a catch-all "Más").
- A dismissible lime-green (`#E3F77E`) promo strip can appear pinned above everything on scroll (e.g. discount code banner), pushing content down.
- Mobile behavior not tested in this pass, but the two-tier + hamburger-for-"Más" pattern is standard for this density of nav.

### Search bar
- Pill-shaped input (6px radius), light gray fill, magnifier icon inline on the left, placeholder text rotates through example queries ("Buscar iPhone", "Buscar MacBook", "Buscar PlayStation…"). Centered in the header, roughly 350–400px wide on desktop.
- No visible live-suggestions were captured in this pass — treat autocomplete/typeahead as an assumption to verify if rebuilding.

### Hero / Above the fold
- Full-bleed campaign banner (red gradient in the observed instance, swaps with promotions), large bold sans headline, short subcopy line, a discount-code pill, and a black rounded CTA button ("¡Vamos!"), with a lifestyle product photo bleeding off the right edge. Carousel dots + prev/next arrows below.
- Directly under the hero, a centered editorial-style intro block using the IvarSoft serif for a large punchline ("Donde el mundo compra tecnología reacondicionada") plus a smaller sans subline with an inline link.

### Buttons
- **Primary:** filled near-black `#110F15` bg, white text, 6px radius, medium padding (~12px), no shadow, weight 400 (not bold) — label does the work, not the button styling. Used for "Comprar", "Ver X productos", "Me suscribo".
- **Secondary / ghost:** white bg, hairline border, near-black text, same 6px radius — used for "Renove" trade-in CTA (has a leading icon).
- **Icon-only:** circular black buttons for carousel prev/next arrows; plain outline square for wishlist/heart toggle next to primary CTA on PDP.

### Cards
- **Product cards** (catalog grid): no border/shadow/background — just product image, color-swatch dots (+N overflow), title, star rating with review count, "Desde" price prefix, current price bold + strikethrough original price + "nuevo" label.
- **Promo/inset cards** (e.g. "Hazte un renove y ahorra aún más"): soft lavender background tile inline within the product grid, same visual weight as a product card so it blends into the scroll.
- **Info/reassurance cards** (PDP): light blue `#D9E4FC` rounded blocks, icon + one-line text + chevron, stacked vertically (shipping date, postcode, 30-day trial/warranty, "compromiso" trust link).

### Forms / Inputs
- Newsletter/email inputs: simple rounded rectangle, thin border, envelope icon inline, paired with an adjacent solid black submit button — no floating labels observed.
- Filter/config selectors use a **radio-row pattern** rather than native selects: each option is a full-width rounded row with a radio dot on the left, label + optional subtext in the middle, price (and a green down-arrow if it's a discount) on the right. Selected state = pale lavender `#F6F2FD` fill + visible border/ring, filled black radio dot.

### Filters (catalog/search)
- Horizontal row of pill-shaped filter triggers (Precio, Marca, Modelo, Estado, Almacenamiento, plus a catch-all "Filtrar" icon button) beside a right-aligned "Ordenar" sort dropdown.
- Each pill opens a **popover** (white, 6px radius, no shadow beyond a subtle border) anchored below it:
  - **Precio:** a small price-distribution histogram (light blue bars) + dual-handle range slider + linked Min/Max numeric inputs + "precio medio" (average) hint text, ending in a black "Ver N productos" apply button that live-updates the count.
  - **Estado (condition):** simple checkbox list (Prémium, Excelente, Muy bueno, Correcto), same black apply button pattern.
- Applying filters updates the product count live in the button label — good pattern to replicate for any faceted search UI.

### Comparison / Editorial page (e.g. iPhone 14 vs 15)
- Structured as a long-form **article**, not a spec-sheet tool: yellow-green (`#E3F77E`) title band with breadcrumb, H1, byline ("Editorial Back Market, expertos en tecnología"), last-updated date, read time, and a share icon.
- A floating "Índice" (table of contents) pill button sits fixed bottom-left as a scroll companion.
- Early in the article, a **two-column verdict card**: each column = product photo, a checklist of pros (✅) and cons (❌) in plain text rows, ending in a black "Comprar desde X €" button per column.
- Further down, a plain **HTML-table-style spec comparison** (Peso, Tamaño, Pantalla, RAM, Almacenamiento, Cámaras, Procesador, Batería...) — two product columns, row labels in a muted left column, generous row padding, hairline row dividers, no zebra striping.
- A dark near-black floating newsletter card can appear bottom-right mid-scroll ("Tu dosis de tecnoactualidad") — same subscribe-input + button pattern as the footer, just dark-themed and dismissible.

### Product detail page (PDP)
- Two-column layout: left = vertical thumbnail rail + large main image with a circular pastel "Reacondicionado por expertos" seal badge overlaid; right = title, star rating + review count link, price block (current bold + strikethrough original + mint-green "Ahorra X €" chip), "IVA incluido" microcopy, black "Comprar" + outline heart button side by side, then the stacked light-blue info cards (shipping/postcode/trial/warranty).
- Below the fold: a horizontal "Reacondicionamiento profesional" carousel of pastel-gradient tiles (battery health, screen check, etc.), then sequential **variant selectors** — Estado (condition), Batería (battery), Almacenamiento (storage), Color — each using the radio-row pattern described above, each with its own supporting image/illustration alongside it.
- On scroll past the main image, a **sticky mini price-bar** appears at the very top: small thumbnail + a one-line breadcrumb of the current config ("Excelente - Batería estándar - 128 GB - eSIM - Negro") + price + Comprar button, with a thin black scroll-progress line beneath it.

### Footer
- White background, simple hairline divider from content above. Newsletter block first (headline + subcopy left, email input + black "Me suscribo" button + "Más información" disclosure right). Below that, a plain 5-column link grid (Sobre Back Market, Ayuda, Servicios, Guías de compra, Condiciones legales), all same-weight text links, no icons. Thin divider, then copyright line bottom-left only — no social icons or app-store badges observed on this page.

---

## Interactions & Animation

- **Default transition:** short, subtle `motion-safe` color/opacity transitions on links and hover states — nothing bouncy or dramatic
- **Hover effects:** nav links get a bold-weight shift on hover rather than a color change in some cases; buttons darken/lighten slightly
- **Scroll animations:** sticky header, sticky "Índice" TOC button, and a sticky mini price-bar with scroll-progress indicator on PDP — functional scroll-driven UI rather than decorative reveal animations
- **Page transitions:** standard SPA-style route changes, no visible custom transition
- **Loading state:** not captured in this pass

---

## Tone & Personality

Back Market reads as deliberately unglamorous-and-proud-of-it: a near-black-on-off-white UI that gets out of the way of product photos and price numbers, because the thing being sold is trust ("reacondicionado por expertos," visible warranty/trial terms, condition transparency) rather than aspiration. Color is rationed and meaningful — green means you saved money, blue means "we've got you covered," lavender means "this is what you picked" — so the palette itself teaches the user how to read the page. The one indulgence is the serif IvarSoft headline type dropped into otherwise-plain marketing moments, giving it a faint editorial/press credibility layer on top of a fundamentally dense, e-commerce-grade information architecture (spec tables, faceted filters, multi-step variant configuration).

---

## Notes & Reuse Tips

1. **Steal the radio-row config pattern.** The condition/battery/storage selector (radio dot + label/subtext + price + optional green discount arrow, selected = lavender fill + ring) is the single most reusable component here — it scales cleanly to any product with 2–5 mutually exclusive priced variants, and it's far more scannable than a native `<select>`.

2. **Color-code by meaning, not by brand.** Don't reach for the campaign red as a "brand color" — it's a rotating promo skin. The actual stable palette is near-black text/CTA + off-white bg + three pastel semantic accents (mint=savings, blue=reassurance, lavender=selection). This is the part worth porting to a new project.

3. **Flat product cards, no chrome.** Resist the urge to put borders/shadows on e-commerce grid cards — Back Market's cards are just image + text floating on the page bg, which keeps a 4-column grid from feeling boxy or heavy.

4. **Comparison pages are articles, not spec-tools.** If asked to build a "X vs Y" page, this reference treats it as long-form editorial content (byline, read time, TOC) with a pros/cons verdict card up top and a plain data table further down — not an interactive spec-picker widget.

5. **Font substitutions if IvarSoft/BMDuplet aren't available:** IvarSoft (serif, editorial headlines only) → `Tiempos`, `Freight Text`, or `Source Serif 4`. BMDupletDSP/TXT (sans, everything else) → `Inter` or `Public Sans` for a similarly neutral, slightly-rounded system-sans feel. Keep the metrics-matched-fallback trick (`ascent-override`/`size-adjust` against local Helvetica) if avoiding layout shift on font load matters.

6. **Filter popovers with live count feedback.** The "Ver N productos" button text updating live as filters change (rather than a static "Apply") is a small but effective trust-building detail for faceted search — worth replicating.
