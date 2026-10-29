# Winamp Classified — Silver / Cobalt Instrument Panel

## Meta
- **Source:** [Winamp5_Classified_v5.5.wsz — Winamp Skin Museum](https://skins.webamp.org/skin/b0fb83cc20af3abe264291bb17fb2a13/Winamp5_Classified_v5.5.wsz)
- **Visual reference:** [275 × 348 player screenshot](https://r2.webampskins.org/screenshots/b0fb83cc20af3abe264291bb17fb2a13.png)
- **Credits:** The skin readme credits original design to Sven Kistner, classic version to Zarko Jovic and GuidoD, and edits to Wildrose-Wally. It lists a January 17, 2004 release and a 2004–2007 copyright notice, all rights reserved.
- **Style keywords:** retro Winamp, silver hardware, cobalt LCD, beveled chrome, tactile skeuomorphism, pixel precision, compact instrumentation, early-2000s desktop audio
- **Best for:** music/audio products, creative-tool websites, developer dashboards, personal libraries, release archives, technical portfolios, community radio
- **Scope:** A proposed website system derived from the skin, not a reconstruction of its original UI. Colors marked as sampled come from the museum screenshot; web typography, dimensions, responsive rules, semantic states, and interactions are adaptation decisions, not measured website properties.

### Source Analysis → Website Translation

| Observed in this specific skin | Website interpretation | Do not copy literally |
|-------------------------------|------------------------|-----------------------|
| Silver player body with light top edges and dark lower edges | A restrained metallic page shell and tactile controls | A stretched bitmap background |
| Deep cobalt playback display and playlist | Recessed hero/data screens and collection lists | Blue behind every paragraph |
| Separate player, equalizer, and playlist modules | Repeated framed sections with compact title rails | Fixed-size draggable desktop windows |
| Circular transport buttons, capsule toggles, narrow sliders | Distinct control families for actions, modes, and adjustable values | Play/pause symbols used for unrelated actions |
| White pixel readout, micro-labels, numeric time fields | Short mono readouts beside readable sans-serif prose | Tiny raster text for navigation or body copy |
| Dense EQ bars, waveform, progress rail | Purposeful charts, progress, and metadata strips | Decorative fake controls implying functionality |
| Highlighted blue playlist row | Strong selected state in lists/tables | Selection indicated only by a subtle color change |

The signature is **silver equipment surrounding luminous blue information**. It is neither generic Windows 95 grey, black-and-neon terminal UI, nor cyberpunk neon. The tiny yellow/orange lightning emblem is a source detail, not the main palette or an asset to reuse.

---

## Colors

| Role | Name | Hex | Usage |
|------|------|-----|-------|
| Primary | Display Cobalt | `#284A89` | Primary CTA, display fill; sampled from playback screen |
| Secondary | Deep Playlist Blue | `#1C3D7D` | Lists, large recessed data panels; sampled |
| Background | Shell Silver | `#B2B8C4` | Page chassis; sampled |
| Surface | Panel Alloy | `#BDC3CE` | Cards, controls, EQ-inspired panels; sampled |
| Surface highlight | Brushed Highlight | `#F1F1F4` | Narrow upper gradient stop and bevel highlights; sampled |
| Text primary | Instrument Ink | `#162030` | Headings and prose on silver; web adaptation |
| Text secondary | Muted Steel | `#39465B` | Captions and metadata on silver; web adaptation |
| Text on blue | Readout White | `#FFFFFF` | Display text and primary CTA labels; sampled |
| Accent / selection | Playlist Highlight | `#6788C9` | Selected row fill and chart accents; sampled |
| Border / recess | Deep Recess | `#002263` | Display inner edges; sampled |
| Border / chrome | Steel Edge | `#828A98` | Decorative panel seams; sampled |
| Focus | Focus Cobalt | `#163C88` | Focus outline on light surfaces; web adaptation |
| Success | Status Green | `#1C5235` | Icon + explicit success label on silver; web adaptation |
| Error | Fault Red | `#802030` | Icon + error text on silver; web adaptation |

**Color philosophy:** Let silver dominate the overall shell; reserve blue for information wells, selected states, and primary actions. A useful starting balance is 65% silver, 30% blue, 5% highlights/details. Do not flood the page with white cards or add unrelated rainbow accents.

**Contrast rules:** Use white on Display Cobalt and Deep Playlist Blue. Use Instrument Ink, not white, on Playlist Highlight: the source's pale selected-row text is not a safe default for small web text. Keep silver-surface secondary copy in Muted Steel, not Steel Edge. Validate final combinations against WCAG AA (4.5:1 normal text; 3:1 large text and meaningful control boundaries). Decorative bevels may be subtle; an input's actual boundary must remain identifiable. Semantic colors above assume silver backgrounds; inside blue panels use white text plus a labeled icon instead.

---

## Typography

| Role | Font family | Weight | Size (desktop) | Size (mobile) | Transform |
|------|-------------|--------|----------------|---------------|-----------|
| Display / H1 | `"Arial Narrow", "Roboto Condensed", Arial, sans-serif` | 700 | 56px | 36px | None; optional short uppercase title |
| H2 | `"Arial Narrow", "Roboto Condensed", Arial, sans-serif` | 700 | 32px | 26px | None |
| H3 | `Tahoma, Verdana, Arial, sans-serif` | 700 | 20px | 20px | None |
| Body | `Tahoma, Verdana, Arial, sans-serif` | 400 | 16px | 16px | None |
| Caption / small | `Tahoma, Verdana, Arial, sans-serif` | 400 | 13px | 13px | None |
| Label / tag | `Tahoma, Verdana, Arial, sans-serif` | 700 | 12px | 12px | Uppercase for short labels only |
| Monospace / code | `"IBM Plex Mono", "Courier New", monospace` | 400 / 500 | 14px | 14px | None |
| Numeric readout | `"IBM Plex Mono", "Courier New", monospace` | 500 | 40px | 28px | None; tabular numerals |

**Font source:** System fonts by default; optional Roboto Condensed and IBM Plex Mono can be self-hosted from their open-source distributions. These are web substitutes, not identified fonts from the bitmap skin. Check fallback widths before shipping.

**Line height:** body `1.55`, headings `1.1–1.2`, labels `1.25`, readouts `1.1`.
**Letter spacing:** headings `-0.02em`; short uppercase title rails `0.08em`; body `normal`; readouts `0.02em`.

The original's pixel lettering belongs to its small raster canvas. Recreate the precision through tabular numbers, orderly alignment, and short mono labels—not by making all text look pixelated. A licensed bitmap face may be used for a nonessential wordmark, never required for reading content. Do not apply `image-rendering: pixelated` to ordinary text.

---

## Spacing & Layout

- **Grid:** 12 columns on desktop; 8:4 hero split or 8:4 main/utility layout. Use a single column on mobile.
- **Max content width:** 1200px; outer shell width `min(1200px, calc(100% - 48px))`, reducing to `calc(100% - 24px)` on mobile.
- **Section padding (vertical):** 48px desktop / 32px mobile; compact framed modules can sit 16–24px apart.
- **Component gap:** 24px between large modules; 16px card padding; 8px between related controls.
- **Base unit:** 4px; reserve 1px and 2px for seams, bevels, and focus rings.
- **Border radius:** 6px on major chassis frames, 2–4px on displays and cards, 3px on rectangular buttons. Full circles for actual transport controls; capsules for mode toggles only.
- **Title rails:** 28–32px tall with a centered/left-aligned label and thin recessed lines extending along unused width. Do not reproduce the source's illegibly small rail heights.
- **Responsive behavior:** below 900px, stack hero and utility modules; below 600px, wrap toolbars, stack form groups, and switch list rows to title + metadata lines. Real data tables may scroll in a labeled region; the page itself must not overflow horizontally.
- **Density:** Compact chrome around generous content. Keep prose to roughly 60–70 characters per line; do not compress a website into the player's 275px footprint.

---

## Visual Style

- **Shadows:** hard, shallow inset highlights and dark seams; at most one small exterior shadow on the outer shell. Depth should resemble stamped equipment rather than floating cards.
- **Borders:** a 1px dark perimeter plus light top/left and dark bottom/right bevels. Recessed blue screens reverse this lighting logic.
- **Images:** square or 4px corners, framed inside a blue or dark recessed viewport. Album art, spectrograms, product screenshots, and technical diagrams fit naturally. Keep photography's real colors; avoid a mandatory blue overlay.
- **Icons:** simple 16–20px SVGs with consistent strokes or solid transport glyphs. Place them on correctly sized controls, not tiny bitmap hit targets. Pair unfamiliar icons with visible labels.
- **Texture / background:** shallow vertical silver gradients over short distances; optional extremely subtle static grain on chrome only. Use crisp horizontal rails and inset tracks, not scanlines across text.
- **Metal treatment:** favor `#F1F1F4 → #BDC3CE → #B2B8C4` for a restrained light-to-dark chassis. Do not use sweeping mirror-chrome reflections or gradient-filled lettering.
- **Display treatment:** solid Deep Playlist Blue or a restrained Deep Recess → Display Cobalt gradient, white readouts, and a hard inner rim. Blue does not need a glow to feel illuminated.

### Suggested CSS Primitives

These are implementation starting points for the adaptation, not extracted source CSS.

```css
:root {
  --shell: #b2b8c4;
  --panel: #bdc3ce;
  --highlight: #f1f1f4;
  --edge: #828a98;
  --ink: #162030;
  --muted: #39465b;
  --cobalt: #284a89;
  --playlist: #1c3d7d;
  --recess: #002263;
  --selected: #6788c9;
}

.chassis {
  color: var(--ink);
  background: linear-gradient(#f1f1f4, #bdc3ce 20px, #b2b8c4);
  border: 1px solid #39465b;
  border-radius: 6px;
  box-shadow: inset 1px 1px 0 #fff,
              inset -1px -1px 0 #828a98,
              0 2px 4px rgb(24 35 52 / 20%);
}

.display {
  color: #fff;
  background: var(--playlist);
  border: 1px solid var(--recess);
  border-radius: 3px;
  box-shadow: inset 1px 2px 0 rgb(0 0 0 / 35%),
              0 1px 0 #f1f1f4;
}

.hardware-button {
  min-height: 44px;
  padding: 10px 16px;
  color: var(--ink);
  background: linear-gradient(#f1f1f4, #bdc3ce 55%, #b2b8c4);
  border: 1px solid #39465b;
  border-radius: 3px;
  box-shadow: inset 1px 1px 0 #fff, inset -1px -1px 0 #828a98;
  font: 700 14px/1.25 Tahoma, sans-serif;
}

.hardware-button:active {
  background: #b2b8c4;
  box-shadow: inset 1px 1px 2px #39465b;
}

.primary-button {
  color: #fff;
  background: var(--cobalt);
}

.selected-row {
  color: var(--ink);
  background: var(--selected);
  border-inline-start: 3px solid var(--ink);
}

/* Use a two-tone ring on both light chrome and blue displays. */
:where(a, button, input, select, textarea, summary):focus-visible {
  outline: 2px solid #fff;
  outline-offset: 2px;
  box-shadow: 0 0 0 5px #163c88;
}

.readout { font-variant-numeric: tabular-nums; }
```

Use native element semantics and implement disabled/selected states in markup as well as CSS. If a component already needs a shadow, combine it with the focus shadow rather than losing the focus indicator. Keep focus rings outside clipping containers.

---

## Components

### Navigation
- A silver equipment-style header with a small wordmark left, text links in the middle, and one blue primary action right.
- Approximately 64px high, with a narrow title rail above or a recessed line below—not three layers of ornamental chrome.
- Active links use a pressed tab treatment plus an underline or explicit marker. Keep navigation recognizable as links, not a row of unlabeled transport glyphs.
- On mobile, use a labeled Menu button opening a normal in-flow disclosure. Keep keyboard focus predictable and expose `aria-expanded`. No draggable or fake minimize/close controls.

### Hero / Above the fold
- One framed main module rather than a giant free-floating headline. A title rail names the product/category.
- Desktop: left side holds a short H1, two to three lines of explanation, one primary CTA, and one secondary action; right side is a recessed blue product or information display.
- The display might show an actual audio preview, a useful product metric, a release list, or a real waveform. Support the site's purpose; a non-audio product does not need a music player.
- A slim metadata strip below can contain version, availability, or format. Use truthful labels such as `VERSION 2.4` or `LATEST RELEASE`, not fabricated live statuses.
- Mobile: copy and CTAs first, display below. No autoplay, scrolling marquee headline, or clipped essential readout.

### Buttons
- **Primary:** cobalt fill, white label, small bevel, 44px minimum height. Hover shifts fill toward Deep Playlist Blue; active state looks inset.
- **Secondary:** silver hardware gradient, Instrument Ink label, dark outline. Hover brightens the upper highlight without lifting the button.
- **Ghost / text:** underlined cobalt link on silver; white underlined link on blue. Do not make text links look disabled.
- **Transport:** round silver control, dark glyph, 44 × 44px minimum. Reserve for actual playback, skipping, or recording actions; provide accessible names and visible tooltips when helpful.
- **Mode toggles:** compact capsule styling within a 44px-high target, explicit on/off state via text or checkmark, and correct native checkbox or `aria-pressed` semantics.
- **Disabled:** muted but legible label, no active bevel response, native `disabled` where applicable. Do not merely reduce the entire control to near-invisible opacity.

### Cards
- Silver framed modules with a compact title rail, 16–24px internal padding, and optional recessed image/data well.
- Use the same frame language for feature, release, and project cards. Avoid giving every paragraph its own window.
- Hover may emphasize the perimeter; no scaling, floating, or oversized shadow. Only show pointer affordances if the card has an actual action.
- Keep one clear card link; avoid nested clickable controls inside a whole-card button.

### Lists / Tables — The Playlist Pattern
- A key reusable component: blue well, white rows, aligned metadata, mono durations/version numbers, and fine separators.
- Desktop columns: index or state → title → secondary metadata → duration/date/action. Use 44px minimum interactive row targets instead of the source's tiny rows.
- Selected rows use Playlist Highlight with dark text and a left marker/check, with `aria-current` or native selection semantics as appropriate.
- Put muted metadata on its own readable line on mobile. Allow long titles to wrap; use truncation only where the full text is otherwise available.
- Browsing content belongs in semantic lists/tables with ordinary links. Do not apply a complex keyboard-driven `listbox` just to imitate a playlist.

### Forms / Inputs
- Silver labels above recessed, pale inputs (`#F1F1F4`), Instrument Ink text, 1px Muted Steel boundary, 3px radius, and 44px minimum height.
- Search/filter areas can live in a blue panel, but keep the actual field light for legibility. Use persistent labels, not placeholder-only instructions.
- Focus uses the two-tone ring above; errors add Fault Red text with an icon and a specific remedy, linked via `aria-describedby`. Never rely on red alone.
- Native ranges are the web equivalent of the EQ sliders: horizontal by default, visible numeric output, keyboard support, and a generously sized hit area. Vertical sliders belong only in a genuinely useful mixing interface.
- Prefer native selects, checkboxes, and validation behavior over custom bitmap replacements.

### Footer
- A final silver chassis module with a narrow title rail and a dark-blue inset status/legal strip.
- Group navigation and contact links in two or three compact columns, then stack on mobile. Keep legal text at 13px or larger.
- A version/build label is appropriate if real; avoid fake playback timers or decorative system warnings.

---

## Interactions & Animation

- **Default transition:** `background-color 120ms ease, color 120ms ease, border-color 120ms ease`; do not use `transition: all`.
- **Hover effects:** highlight a bevel, darken a blue action, or emphasize a row boundary. Controls remain anchored in place.
- **Pressed state:** reverse the bevel immediately. Persistent toggles retain a pressed appearance and a textual/state marker after activation.
- **Scroll animations:** none by default; the instrument-panel structure should appear stable and ready to use.
- **Page transitions:** normal navigation; no simulated OS boot sequence.
- **Loading state:** a labeled progress rail for measurable progress; otherwise a static `Loading…` status or restrained indeterminate bar. Do not show invented percentages.
- **Optional visualizer:** only inside a relevant media/data display, driven by real data when possible. Decorative motion is `aria-hidden`, pausable when persistent, and static under `prefers-reduced-motion: reduce`.
- **Audio:** never autoplay or add interface click sounds by default. Provide play/pause, volume, and appropriate media alternatives if real audio is present.

---

## Tone & Personality

A small, well-engineered piece of audio equipment translated into a website: tactile, orderly, technical, and quietly nostalgic. Silver chrome gives the site physical presence; cobalt displays make important information feel powered on. Copy should be direct and useful, not full of fake hacker jargon or nostalgia jokes. The experience is contemporary in usability even when the surface recalls early-2000s desktop software.

---

## Notes & Reuse Tips

1. **Keep the specific skin's identity.** Silver chassis + deep blue wells + precision rails matter more than adding generic retro icons. Black/green terminals, vaporwave pink, glass blur, and Windows 95 title bars would describe other aesthetics.
2. **Translate hierarchy, not scale.** Player → main story; EQ → adjustable settings/data; playlist → browsable collection. Do not literally scale the entire 275 × 348 screenshot to website width.
3. **Limit the chrome budget.** One outer frame, one title rail per module, and one recess around an information area are usually enough. Nested bevels around every sentence become visual noise.
4. **Scale content and controls independently.** Retain fine 1px detailing while enlarging text, spacing, and hit targets. Reflow at 200% zoom and support a 320 CSS-pixel viewport without losing functionality.
5. **Do not fake affordances.** A screw can be decorative; a close icon or slider implies a working action. Omit controls that do nothing. Do not make website sections draggable by default.
6. **Use proper document structure.** Real headings, links, buttons, landmarks, tables, and form labels remain essential underneath the hardware skin. Test keyboard navigation, focus visibility, zoom, and high-contrast/forced-colors modes.
7. **Keep effects optional.** The layout must remain understandable without gradients, texture, animation, or external fonts. In forced-colors mode retain native outlines/borders and do not depend on box shadows alone.
8. **Respect source rights.** The museum's readme says all rights reserved. Use this as stylistic reference, not permission to redistribute its bitmaps, emblems, or other artwork. Rebuild original CSS/SVG treatments; seek permission before using actual skin assets.
9. **Suggested page sequence:** header chassis → split copy/display hero → three feature modules → playlist-style collection or release table → focused form/CTA → footer status strip.
10. **Quick acceptance test:** Does the page still read as silver-and-cobalt audio equipment without a Winamp logo? Can users understand it without knowing Winamp? Can they navigate and read it comfortably on a phone? All three should be true.
