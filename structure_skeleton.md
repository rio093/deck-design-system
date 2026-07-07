# Structure & Skeleton (Brand-Neutral)
## The fixed structural layer of the deck-design-system skill

This file defines structure ONLY — zones, coordinates, grid, spacing, density rules, visualization-first logic. **None of this changes per brand.** Colors, fonts, logo, and mood come from the active `design.md` and are referenced here only as `TOKEN` names (e.g., `CANVAS`, `INK`, `ACCENT`). Resolve every `TOKEN` against the active `design.md` at build time.

---

## 0. Production Constraints (READ FIRST)

- **16:9 slides only.** 13.333" × 7.5" (1920×1080 ref). Reject 4:3, 1:1, 9:16, A4, letter.
- **Logo:** use `LOGO_FILE` from the active design.md exactly as provided. No substitution, no decoration. See design.md §4 for color/placement forbidden ops.
- **Typography:** use `FONT_FAMILY` from design.md as the sole family. Weight — not family — builds hierarchy. Embed the font on export.

### Slide Skeleton — Locked Positions (identical on every slide)

| Zone | Y-range | Contents | Style (tokens from design.md) |
|---|---|---|---|
| **Header strip** | 0.4" – 0.7" | Chapter name (left), logo (right) | Chapter: `W_SEMIBOLD` 11pt `TEXT_MUTED`, uppercase, charSpacing 2pt. Logo: `LOGO_FILE`, height ≈0.24", top-right ≈0.5" from right edge |
| **Headline zone** | 1.0" – 1.75" | Slide headline (대제목) | `W_BOLD` 32–40pt `INK`, lh 1.20, track −0.3pt |
| **Subtitle zone** | 1.63" – 2.03" | Subtitle (one-line lead) | `W_LIGHT` 16pt `TEXT_MUTED`, lh 1.45 |
| **Body box** | 2.39" – 6.85" | All body components (see pattern_library.md) | mixed |
| **Clearance buffer** | 6.85" – 7.05" | Empty — no content | — |
| **Footer strip** | 7.05" – 7.3" | Page number (left), source (right) | Page: `W_REGULAR` 10pt `TEXT_MUTED`. Source: `W_REGULAR` 9pt `TEXT_FINE` |

**Outer margins:** 0.5" L/R, 0.4" top, 0.3" bottom. Content width = 12.333", height = 6.8". Internal: 12-column grid, 0.2" gutters (col ≈0.95").

### Vertical Rhythm (intentional, non-uniform)
Header→Headline = 0.3" (loose). Headline→Subtitle ≈0.13" text-to-text (tight — title+subtitle read as one unit). Subtitle→Body = 0.36" (medium). Pattern: loose top, tight middle, medium bottom.

### Lock Rule
Zones never move between slides. Override only when structurally unavoidable: full-bleed cover, section divider that intentionally breaks the frame, closing slide. "Body is taller than usual" is NOT a valid override — restructure or split.

### Hard Boundary
Body lives strictly inside 2.39"–6.85" (height 4.46"). No bleed into subtitle zone above or clearance/footer below. Keep the 0.2" buffer (6.85"–7.05") empty. Anything taller than 4.46" must be split, scaled, or moved to a second slide.

### Body Density Rule
Do not leave the lower body half-empty. Fill at comfortable reading density — charts, KPI tiles, dual-column, evidence stacks, callouts. Density never overrides the hard boundary. For thin content, use side panels, a "So What" callout box, a reinforcing diagram, a 2-column claim/evidence split, or Pattern F. **Never** fake density with decorative shapes, dot motifs, or stock illustrations.

### Visualization-First Rule (strong default)
If a slide carries data, comparison, process, structure, or relationship → visualize it, don't narrate. Triggers (any → must visualize): 2+ compared numbers; trend over time; composition/share; process/sequence; cross-category comparison; structural relationship; geographic/hierarchical breakdown.

Priority: 1) charts (bar/line/area/scatter/donut, brand chart tokens) → 2) KPI tiles w/ sparklines → 3) diagrams (flow/2×2/layered/funnel/hierarchy) → 4) annotated images → 5) tables (last resort). Max 1–2 visualizations/slide. Every chart/diagram gets a title (`W_SEMIBOLD` 14pt), axis labels (`W_REGULAR` 10pt `TEXT_MUTED`), source (`W_REGULAR` 9pt `TEXT_FINE`). If fonts must drop below 9pt to fit → split the slide. Pure-prose body is reserved for openers, hero takeaways, single-quote callouts, definitions.

---

## 1. Grid & Spacing

### Common body grid patterns
- **Single column:** X 0.5"→12.83" (full width).
- **Two-column equal:** L 0.5"–6.27" · R 6.57"–12.83" · 0.3" gutter.
- **Two-column 1/3+2/3:** L 0.5"–4.35" · R 4.95"–12.83" · 0.6" gutter.
- **Three-column equal:** 4.0" cols at X 0.5" / 4.7" / 8.9".
- **Four-column equal:** 2.95" cols at X 0.5" / 3.65" / 6.8" / 9.95".

### Spacing scale (within body)
Base 4px @144dpi. Steps 4/8/12/16/20/24/32/40/48/64/80px. Card-to-card 16–24px. Card padding 16–24px. Headline→subtitle ≈0.13". Subtitle→body 0.36".

### Border radius scale
4pt (inline badges) · 8pt (buttons) · 12pt (data tiles) · 16–20pt (large cards) · 22–24pt (hero cards) · 30–32pt (badge pills) · 9999px (full pill).

### Depth / elevation (resolve shadow tokens from design.md)
L0 flat (default) · L1 `SHADOW_STD` (standard cards) · L2 ambient glow · L3 `SHADOW_GLOW` (featured, ≤1/slide) · L4 `SHADOW_ELEVATED` (hero). Philosophy: color-block & hairline first, shadow rare.

---

## 2. Slide Types (structure-level; styling from design.md)

1. **Cover** — full-bleed `SURFACE_DARK` or `HERO_WASH`. Logo centered Y≈2.5". Title centered Y≈4.5" `W_EXTRABOLD` 36pt `TEXT_ON_DARK`. No page#, no chapter label.
2. **Chapter / Section Divider** — `SURFACE_DARK` or `HERO_WASH`. Chapter number `W_ULTRALIGHT` 72pt; title `W_EXTRABOLD` 36pt; description `W_LIGHT` 16pt. Logo top-right. (Or use Pattern Y bottom-left anchor.)
3. **Standard Content** (default) — `SURFACE_CANVAS`. Full Locked Skeleton. Body = Pattern A–Z.
4. **Key-Message / Highlight** — `SURFACE_CARD` full-bleed or canvas w/ one large card. Single statement or centered pull-quote.
5. **Data / KPI** — `SURFACE_CANVAS`. Pattern A or F. Source bar mandatory.
6. **Closing** — `SURFACE_DARK` full-bleed. Logo centered. Thank-you `W_LIGHT` 28pt. (Or Pattern O with CTA pills for sales decks.)

### Surface Alternation Rule
Never repeat the same surface mode on consecutive slides: `SURFACE_CANVAS` → `SURFACE_CARD` → `SURFACE_DARK` → back. This pacing rhythm is non-negotiable.

---

## 3. Universal Iteration Checklist (structure portion)

Run before exporting. Brand-token checks (font/logo/color correctness) are validated against the active design.md; structure checks below are invariant.

1. ✓ 16:9 (13.333"×7.5")?
2. ✓ Sole `FONT_FAMILY` everywhere, embedded?
3. ✓ `LOGO_FILE` correct position, original asset, no decoration?
4. ✓ All 5 zone anchors match across slides?
5. ✓ Body strictly inside 2.39"–6.85", no zone invasion?
6. ✓ Lower body filled (no empty bottom 30%)?
7. ✓ Data/comparison/process/structure visualized, not narrated?
8. ✓ Every data point has a source line (`TEXT_FINE` 9–10pt)?
9. ✓ `SHADOW_GLOW` ≤1 element/slide?
10. ✓ `HERO_WASH` only on permitted spots, ≤1/slide & ≤3/deck, never charts/text/headers?
11. ✓ Headline Bold / subtitle Light / body Regular; ≤3 text sizes/slide?
12. ✓ Surface alternates from previous slide?
13. ✓ `POINT` color ≤2/deck, never on text/surface?
14. ✓ Chart/data text live (not rasterized)?
15. ✓ Emoji policy from design.md respected?
16. ✓ Card radius 12–24pt, buttons 8pt, pills 9999px?
17. ✓ Shadows use the tint defined in design.md (not arbitrary pure black unless brand specifies)?
18. ✓ Chapter label uppercase, 2pt charSpacing, `TEXT_MUTED`?

If any fails, fix before declaring success.

---

*Structure is invariant. To change the look, change the active design.md — not this file. Pattern coordinates live in `pattern_library.md`; build mechanics in `build_pipeline.md`.*
