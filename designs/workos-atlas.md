# Atlas by WorkOS (workos.com/atlas)

**Source:** https://workos.com/atlas
**Style:** Monochrome SaaS, huge Inter type scale, product-demo mockups, playful 3D robot mascot, dark trust section
**Best for:** AI product / agent landing pages, enterprise SaaS with a friendly mascot, Slack/tool-integration marketing pages

---

## Colors

| Role | Name | Hex/Value | Usage |
|------|------|-----|-------|
| Background | White | `#ffffff` | Page bg, hero, most sections |
| Background alt | Off-White Gray | `#f8f8f8` | Alternating section bg ("Build your AI team") |
| Background dark | Near-Black Navy | `#05070e` | "Built on WorkOS. Secure by default." trust section |
| Text primary | Black | `#000000` | Headlines, primary copy |
| Text secondary | Black 80% | `oklab(0 0 0 / 0.8)` | Subheads, body copy |
| Text tertiary | Black 55–70% | `oklab(0 0 0 / 0.55–0.7)` | Muted captions, timestamps |
| Text on dark | White ~75–85% | `oklab(1 0 0 / 0.75–0.85)` | Copy on the dark trust section, button label |
| Border / hairline | Light Gray | `rgb(186, 186, 186)` | Card borders, dividers |
| Muted gray | Mid Gray | `rgb(118, 117, 119)` / `rgb(97, 96, 97)` | Slack-mockup chrome, secondary UI text |
| Accent (illustration only) | Sky Blue → Deep Navy | `rgb(17,122,174)` → `rgb(0,37,85)` | Robot mascot face/visor radial gradient |
| Accent (illustration only) | Rainbow gradient | blue → purple → magenta → orange | Border frame around Slack-mockup cards |

**Color philosophy:** The UI chrome itself is strictly monochrome — black text on white, gray borders, one dark navy section for contrast/trust-building. All color lives in the illustration layer: the 3D robot mascot's glowing visor and the rainbow gradient borders wrapping product screenshots. This keeps the page feeling like a serious enterprise tool while the mascot supplies warmth and personality.

---

## Typography

| Role | Font family | Weight | Size (desktop) | Letter spacing | Notes |
|------|-------------|--------|----------------|-----------------|-------|
| Display / H1 | InterDisplay | 600 | 84px | -1.68px | Line height ~1.02 (85.68px), tight hero headline |
| H2 (standard) | Inter | 600 | 48px | -0.96px | Line height 1.0, most section headers |
| H2 (emphasis) | Inter | 600 | 72–80px | -1.6px | "Build your AI team.", "Built on WorkOS." — bigger sections get bigger type |
| H3 | Inter | 600 | 16px | -0.16px | Feature card labels (small, all-caps feel via weight not case) |
| Body | Inter | 400 | 16–18px | normal | Paragraph copy, ~1.4 line height |
| UI / chat text | Inter | 400–600 | 13–14px | normal | Slack-mockup message text, timestamps |

**Font source:** Inter + InterDisplay, both variable, likely self-hosted or `next/font` (`"Inter", "Inter Fallback", sans-serif` / `"InterDisplay", "InterDisplay Fallback", sans-serif`) — the `Fallback` suffix indicates a metric-matched fallback font is generated, a Vercel/Next.js convention.

**Key typographic move:** Headline size scales with section importance rather than following a fixed type ramp — hero is 84px, most section H2s sit at 48px, but the two "closing argument" sections ("Build your AI team", "Built on WorkOS") jump to 72–80px to punctuate the page's rhythm before the final CTA.

---

## Spacing & Layout

- **Grid:** Centered single column for hero/CTA; two-column split (text + illustration/mockup) for feature sections, alternating left/right
- **Max content width:** ~1200px, hero copy narrower (~700px) and centered
- **Section padding (vertical):** Generous — roughly 120–160px between major sections
- **Border radius:** Fully-rounded pill (`border-radius: 1.68e7px`, i.e. `9999px`) on all buttons and avatar/icon chips; medium rounding (~16–24px) on mockup cards and panels
- **Carousel pattern:** Several feature sections are swipeable/paginated — prev/next chevron buttons flanking a dot-indicator strip below the content

---

## Visual Style

- **Flat, no drop shadows on UI chrome.** Shadows only appear as soft ambient glow behind the 3D robot renders and inside the dark trust section (grid + radial glow).
- **Product-in-context mockups:** Real-looking Slack UI (sidebar, channels, message thread) embedded directly in sections — not abstract graphics. This is the primary "trust" device instead of testimonial logos.
- **Rainbow gradient card frames:** Mockup cards (e.g. "Build your AI team") sit inside a rounded frame with an animated-looking blue → purple → magenta → orange gradient border, white panel content on top.
- **3D robot mascot:** A recurring rendered character (white shell, glowing gradient visor) appears in different "costumes" per section — plain, wearing a headset, wearing a hoodie — and as a lineup of teammate bots with different colored visors (teal, purple, navy/starfield, magenta, green) to represent custom AI agents.
- **Dark trust section:** Near-black navy `#05070e` background with a faint blue grid pattern and radial glow, white type — a deliberate tonal break from the rest of the white page, used once for the "Built on WorkOS. Secure by default." security pitch.
- **Icons:** Small flat tool/app logos (Gmail, GitHub, Notion, Slack, Google Drive, etc.) scattered around the robot to represent integrations — real brand marks, not generic icon set.

---

## Components

### Navigation
- Static (non-sticky observed), transparent over white bg
- Left: WorkOS diamond logo mark + wordmark, plus "Atlas" as a secondary product label
- Right: single black pill CTA button "Add to your Slack" with small Slack glyph, white text, `padding: 8px 16px 8px 12px` (asymmetric to fit the icon)

### Hero
- Centered layout, huge InterDisplay headline "Meet Atlas, your AI coworker." over two lines
- Short centered subhead in muted black
- Floating pill-shaped chips above the hero animate through example prompts ("Prep for a call", "Debug a regression", "Onboard a new hire", "Catch up after time off")
- Full Slack app mockup (window chrome, sidebar, channel list, message compose bar) as the hero's visual anchor, sitting inside a soft gradient-tinted rounded frame

### Buttons
- Primary: filled black, fully-rounded pill, white text, icon + label, 16px medium weight
- No visible secondary/outline button style on this page — single consistent black CTA repeated at nav, mid-page, and footer

### Cards / Mockup Panels
- White rounded panels (~16–24px radius) containing realistic Slack conversation threads
- Some wrapped in a multicolor gradient border frame for extra visual weight (used on the higher-emphasis sections)
- No shadow on the panel itself — the gradient frame or plain white edge does the separating

### Feature Blocks
- Alternating two-column layout: short H2 + one-paragraph description on one side, illustration/mockup on the other
- Small H3-labeled 3-up feature list ("Right where your team works", "Talk it through", "Turn questions into action") uses a simple icon + heading + one-line description, no card chrome

### Footer
- Minimal single row: `© 2026 WorkOS, Inc.` bottom-left, `Contact / Terms / WorkOS.com` links bottom-right
- Plain white background, no columns, no newsletter signup — deliberately lightweight given this is a sub-product page of the main WorkOS site

---

## Interactions & Animation

- **Hero prompt chips:** cycle/rotate through example prompts (radio-style active state indicated by a filled progress dot)
- **Carousel sections:** click-through with chevron buttons; active dot indicator elongates into a pill shape
- **Illustration reveal:** tool-integration icons appear to fade/scatter in around the robot on the "Connected to all your tools" section (icons are near-invisible until populated)
- **No visible page-transition or scroll-parallax effects** — animation budget is spent on the mascot and carousel, not on scroll-triggered reveals

---

## Tone & Personality

Atlas reads as a serious enterprise AI product that doesn't take itself too seriously. The strict black-and-white UI, huge confident Inter type, and a literal product screenshot in the hero all signal "this is a real, working tool" — while the rendered robot mascot and its costume changes (headset for support, hoodie for casual, starfield visor for a teammate persona) keep the page approachable and a little playful. The one dark section exists purely to slow the reader down for the security/trust pitch before returning to white for the close.

---

## Notes & Reuse Tips

1. **Monochrome UI + colorful mascot is the whole trick.** Don't spread color across buttons, links, or backgrounds — keep those black/white/gray. Put all the personality into one illustrated character or hero graphic instead.

2. **InterDisplay for hero, Inter for everything else** is a free, easy-to-reuse pairing (both on Google Fonts / Fontsource) — no proprietary type license needed to approximate this look.

3. **Real product screenshots beat abstract mockup graphics.** The Slack-window mockups with real avatars, channel names, and message text sell credibility far more effectively than icon-based feature graphics would.

4. **Scale H2 size by section importance, not uniformly.** Reserve the largest type (70–80px) for the two or three sections meant to feel like turning points in the page's argument (here: "Build your AI team" and the security pitch).

5. **Pill radius (`9999px`) everywhere on interactive elements** — buttons, chips, the "Add to Slack" CTA — creates a soft, friendly counterpoint to the otherwise sharp black-on-white type.

6. **One dark section, used once.** A single near-black `#05070e` section breaks up an otherwise all-white page and gives the security/trust message extra gravity — don't overuse this pattern or it loses its punctuation effect.

7. **Rainbow gradient card borders are the one deliberate color break in the UI layer** — reserve them for the one or two most important product-demo panels, not every card, or they stop reading as emphasis.
