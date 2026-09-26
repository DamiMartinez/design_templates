# WorkOS (workos.com)

## Meta
- **Source:** https://workos.com/ (also reviewed: `/pricing`, `/customers`, and `/docs`)
- **Style keywords:** monochrome enterprise SaaS, developer-first, technical, spacious, product-led, polished
- **Best for:** enterprise identity or infrastructure SaaS, API platforms, developer tools with a sales motion, multi-product marketing sites

---

## Colors

| Role | Name | Hex | Usage |
|------|------|-----|-------|
| Primary | Black | `#000000` | Primary CTAs, headings, navigation text, code chrome |
| Background | White | `#ffffff` | Default page and product-section background |
| Surface | Off-white | `#f8f8f8` | Alternating sections, product cards, restrained separation |
| Surface dark | Near-black navy | `#05070e` | High-emphasis pricing, trust, or technical sections |
| Text primary | Black | `#000000` | Headlines and primary body copy |
| Text secondary | Black 70–80% | `oklab(0 0 0 / 0.7–0.8)` | Descriptions and supporting UI text |
| Text on dark | White 75–90% | `oklab(1 0 0 / 0.75–0.9)` | Dark-section headlines and copy |
| Border | Light gray | `rgb(186, 186, 186)` | Card outlines, data-table rules, and dividers |
| Accent | Product/brand imagery | varies | Use sparingly in product screenshots, integration logos, and patterned art—not as general UI color |

**Color philosophy:** WorkOS is almost entirely black, white, and gray. It earns enterprise credibility through restraint, then permits color in proof assets: customer marks, identity-provider logos, product UI, and the occasional subtle patterned or technical background. Keep interactive UI monochrome; color should communicate product context, not decorate the layout.

---

## Typography

| Role | Font family | Weight | Size (desktop) | Size (mobile) | Transform |
|------|-------------|--------|----------------|---------------|-----------|
| Display / H1 | InterDisplay | 600 | 72–84px | 42–52px | Sentence case |
| H2 | Inter | 600 | 48–64px | 32–40px | Sentence case |
| H3 | Inter | 600 | 20–24px | 18–20px | Sentence case |
| Body | Inter | 400 | 16–18px | 16px | None |
| Caption / small | Inter | 400–500 | 13–14px | 13–14px | None |
| Label / tag | Inter | 500–600 | 12–14px | 12–14px | Usually sentence case |
| Monospace / code | ui-monospace / SFMono-Regular / Menlo | 400–500 | 13–15px | 12–14px | Preserve code case |

**Font source:** Inter and InterDisplay variable fonts, likely self-hosted or loaded through a framework font loader.
**Line height:** body `1.4–1.5`; display headings approximately `1.0–1.08`.
**Letter spacing:** large headings are tight (`-0.02em` to `-0.03em`); small UI labels are near normal.

---

## Spacing & Layout

- **Grid:** centered marketing container with a wide 12-column feel; copy and product visual commonly split into balanced two-column sections
- **Max content width:** approximately `1200px`; hero prose is constrained to roughly `680–760px`
- **Section padding (vertical):** `112–160px` desktop / `64–96px` mobile
- **Component gap:** `16–24px` within cards; `32–48px` between related groups
- **Base unit:** `8px`
- **Border radius:** full pill (`9999px`) for CTAs, tabs, and compact chips; `12–24px` for cards, screenshots, and code panels

The site uses long, confident sections rather than a dense dashboard grid. Alternate white and off-white surfaces to segment product narratives; use a single dark section as a high-contrast pause for trust, pricing-plan distinction, or a technical proof point.

---

## Visual Style

- **Shadows:** minimal. Cards are normally separated with a hairline border; shadows, if present, are soft and ambient rather than elevated-material effects.
- **Borders:** thin light-gray rules are a core structural element, especially around product modules, code samples, pricing tables, and cards.
- **Images:** product screenshots and interface fragments are the primary artwork. Use clean, real UI, identity-provider imagery, customer logos, and small purpose-built illustration assets rather than generic stock photography.
- **Icons:** compact custom product icons plus recognizable partner/integration brand marks. Keep generic UI iconography simple and monochrome.
- **Texture / background:** primarily flat white or off-white. Patterned light/dark fields and faint grids support major sections without competing with text.
- **Code as visual proof:** syntax-highlighted, tabbed SDK snippets and API-response blocks are first-class marketing components—not an afterthought. Pair code with a concise claim and product UI wherever possible.

---

## Components

### Navigation
- Wide desktop navigation with WorkOS wordmark at left, grouped product/resource links in the center, and clear conversion actions at right.
- Product navigation should accommodate a multi-product platform: use menus or grouped categories rather than a single flat list.
- Primary action is a black pill button (for example, getting started); secondary actions are text links or a quieter outlined treatment.
- On mobile, collapse navigation into a compact menu while retaining one prominent action.

### Hero / Above the fold
- Centered, oversized value proposition in black InterDisplay on a generous white canvas.
- Brief supporting copy frames WorkOS as developer-friendly infrastructure that removes enterprise identity complexity.
- Follow quickly with tangible proof: an interactive-looking product surface, SDK/code example, integration diagram, or product-status matrix.
- Prefer one primary CTA and one low-emphasis supporting link. Avoid a marketing-illustration-only hero—the design sells through product reality.

### Buttons
- **Primary:** filled black, white medium-weight text, fully rounded pill, comfortable horizontal padding; may include a small arrow or product glyph.
- **Secondary:** white/off-white surface with black text and thin gray border, or plain text with an arrow.
- **Ghost / text:** black text, minimal treatment; use for navigation, docs, and tertiary paths.
- Keep labels direct and action-oriented: “Get started,” “View docs,” or “Talk to an expert.”

### Cards
- White or off-white rounded rectangles with a 1px gray border, limited or no shadow, and generous internal padding.
- Cards should contain operational proof—an auth method, product capability, pricing rule, code example, quote, or customer story—not generic feature filler.
- Repeated-card groups should retain simple, consistent geometry. Introduce color only through contained logos, screenshots, or specialized visual assets.

### Forms / Inputs
- Clean white fields with a subtle gray border and black label text above or within the field.
- Use a visible black focus ring or high-contrast border state; reserve red for validation errors.
- Submit controls follow the primary black pill button treatment.

### Footer
- Full multi-column utility footer for a platform site: product, developers/resources, company, and legal groupings.
- White or near-white background with thin divider rules, small muted links, and the WorkOS mark.
- Include documentation, status, security, privacy, and terms alongside company/social paths; the footer should feel comprehensive but quiet.

---

## Interactions & Animation

- **Default transition:** `150–200ms ease` for color, border, opacity, and transform.
- **Hover effects:** subtle border darkening, text/link emphasis, or a minor background shift; buttons may soften/lighten slightly rather than lift dramatically.
- **Interactive demos:** SDK tabs, language selectors, carousel controls, and product-state modules demonstrate breadth without requiring long explanatory copy.
- **Scroll animations:** restrained fades or reveals may be used for product visuals and patterns. Avoid heavy parallax or constant motion.
- **Page transitions:** none required; responsiveness and product-demo clarity are more important than cinematic movement.
- **Loading state:** simple skeleton or low-key progress treatment consistent with the neutral palette.

---

## Tone & Personality

WorkOS feels precise, calm, and highly capable: enterprise-ready without looking like legacy enterprise software. Its huge, economical typography and nearly colorless UI signal confidence, while real code, product surfaces, and integration marks make the message legible to developers. The voice should be direct and specific—make a strong promise, then substantiate it with implementation details, scale, customer proof, or a real interface.

---

## Notes & Reuse Tips

1. **Treat this as the parent system; keep Atlas separate.** Reuse the neutral palette, type, pills, borders, and dark-section punctuation from WorkOS. Do not import Atlas’s robot mascot, rainbow frames, or Slack-specific visual language unless building for Atlas.
2. **Show the implementation.** A multi-product WorkOS-style page needs real code snippets, API responses, setup flows, and/or product screenshots early and often.
3. **Use customer and integration marks as evidence.** Logo fields are dense but controlled proof of enterprise adoption. Give them breathing room and keep the surrounding layout monochrome.
4. **Make information hierarchy do the work.** Large headlines, restrained subheads, a focused CTA, and strong section spacing are more characteristic than decorative gradients or elaborate cards.
5. **Use dark backgrounds once or twice, purposefully.** Reserve near-black sections for security, scale, technical architecture, or plan contrast; returning to white restores the core WorkOS rhythm.
6. **Design for a platform, not a single feature.** Navigation, page modules, and footer should comfortably point to products, docs, customers, pricing, and security without losing the primary conversion path.
7. **Keep enterprise warm through clarity, not whimsy.** The main site’s personality comes from polished details and developer empathy; color and character should stay subordinate to the product proof.
