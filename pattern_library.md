# Pattern Library A–Z (Brand-Neutral)
## 26 body composition patterns for the deck-design-system skill

All patterns operate strictly inside the body box (Y 2.39"–6.85", 4.46" tall × 12.333" wide) defined in `structure_skeleton.md`. **Coordinates and dimensions are structure — they never change per brand.** Every color is written as a `TOKEN` name; resolve against the active `design.md`. Where a pattern says e.g. `ACCENT`, substitute the brand's accent color.

Pattern picker: decide the slide's core message first, then choose. A–F = core; G–O = sales/media-kit; P–Z = inhouse/global/diagram-heavy.

---

## Core Patterns A–F

### A — KPI Strip + Detail (default for data slides)
- Top half (Y 2.39"–4.2"): row of 3–4 KPI cards (~2.95"w × 1.4"h, surface `SURFACE_BAND`, 12pt radius, `SHADOW_STD`, 20pt padding). Each: number `W_BOLD` 32–40pt `INK`, unit `W_LIGHT` 14pt `TEXT_MUTED`, label `W_MEDIUM` 11pt `TEXT_MUTED`.
- Bottom half (Y 4.3"–6.85"): supporting chart OR 2-col claim/evidence.
- Optional: 2pt `ACCENT` top-border on the featured KPI card.

### B — Two-Column Compare
- Left (X 0.5"–6.27"): claim + bullets. H2 `W_SEMIBOLD` 18pt, bullets `W_REGULAR` 13pt `INK`, lh 1.50.
- Right (X 6.57"–12.83"): chart/diagram/visual.
- Optional full-width "So What" callout Y 6.0"–6.7": `SURFACE_CARD`, 3pt left-border `ACCENT`, 12pt radius, `W_MEDIUM` 14pt `INK`.

### C — Diagram-Centered
- Centered diagram ~70% of body (Y 2.6"–5.8", X 1.5"–11.83"). 3–4 caption boxes around it. Bottom strip (Y 6.0"–6.85"): source + takeaway.

### D — Process Flow
- Horizontal arrow flow, 4–6 stages, Y 3.0"–4.5". Each: numbered circle (`ACCENT` fill or hairline), label `W_SEMIBOLD` 14pt, 1–2 line desc `W_REGULAR` 12pt. Below (Y 4.8"–6.85"): outcomes/pull-quote w/ metrics.

### E — Quote + Evidence
- Large pull-quote (`W_THIN` 24–28pt, `ACCENT` quotation marks) left half (X 0.5"–6.27", Y 2.6"–6.0"). 2–3 supporting data cards right half (X 6.57"–12.83"). Source under quote `W_REGULAR` 10pt `TEXT_FINE`.

### F — Stacked Insight Layers (thin content → keep density)
- Top band (Y 2.39"–3.5"): 3-metric KPI row. Middle (Y 3.7"–5.4"): one chart/diagram. Bottom (Y 5.6"–6.85"): 3-up evidence cards (claim + 1-line proof + source).

**Picker:** A=data · B=compare · C=system · D=journey · E=testimonial · F=thin content.

---

## Sales / Media-Kit Patterns G–O

### G — Table of Contents
- Two columns (L 0.5"–6.27" main · R 6.57"–12.83" appendix, 0.3" gutter). Section header `W_BOLD` 18pt `INK` w/ 1.5pt `ACCENT` underline 0.15" below. Rows (height 0.32"): index `W_REGULAR` 11pt `TEXT_MUTED` · title `W_MEDIUM` 13pt `INK` · leader dots `TEXT_MUTED`/`HAIRLINE_CANVAS` · page# `W_REGULAR` 11pt. Titles hyperlinked. Footer note Y 6.55" `W_REGULAR` 9pt `TEXT_FINE`.

### H — Spec Table + Visual Evidence ★workhorse
- Left (X 0.5"–6.27", Y 2.39"–6.85"): numbered subsection spec table. Subsection header `1)` `W_SEMIBOLD` 12pt `ACCENT` + title `W_SEMIBOLD` 14pt `INK` + 0.5pt `HAIRLINE_CANVAS` rule. Key-value mini-table: key `W_MEDIUM` 11pt `TEXT_MUTED` (≈1.7"), value `W_REGULAR` 11pt `INK` (≈4.0"), 0.5pt `HAIRLINE_CANVAS` row dividers, no vertical. 2–3 subsections; 4+ → split.
- Right (X 6.57"–12.83"): visual evidence frame, 16pt radius, 0.5pt `HAIRLINE_CANVAS`. Phone mockup 9:19.5, frame ≈2.6"w, centered. Optional 1.5pt `ACCENT` callout arrows.

### I — Multi-Stage Process with Screenshots
- 4–6 columns. 5-stage: cols 2.27"w at X 0.5"/2.97"/5.44"/7.91"/10.38". Per stage: Y 2.39"–2.7" numbered circle 0.32" (`ACCENT` or `INK` fill, white `W_BOLD` 14pt digit) + label `W_SEMIBOLD` 11pt; Y 2.85"–4.5" screenshot frame 12pt radius 1.65"h; Y 4.65"–6.85" bullets `W_REGULAR` 9–10pt `TEXT_SECONDARY`. Connectors: 1pt `ACCENT` arrows Y 2.55". Bottom takeaway band Y 6.0"–6.7" `SURFACE_CARD` 3pt left-border `ACCENT` `W_MEDIUM` 13pt.

### J — Comparison Spec Matrix
- Full-width table X 0.5"–12.83". Header row 0.55"h `SURFACE_CARD`. Header: category badge pill (`ACCENT`/sub-color, white `W_SEMIBOLD` 9pt) + name `W_SEMIBOLD` 13pt + tagline `W_REGULAR` 10pt `TEXT_MUTED`. Body rows alternate `SURFACE_CANVAS`/`SURFACE_BAND`, 0.5pt `HAIRLINE_CANVAS` dividers. Cells `W_REGULAR` 11pt `INK`. First col = spec labels `W_MEDIUM` 11pt `TEXT_MUTED`. Numeric right-aligned. Bottom/total row `W_BOLD` 14pt, 1pt `ACCENT` divider above. **4 cols sweet spot, 5 max.**

### K — 2×2 Infographic Grid
- 4 cells 6.07"w × 2.13"h. Top Y 2.39"–4.52", bottom Y 4.72"–6.85". L 0.5"–6.57", R 6.77"–12.83". Cell `SURFACE_BAND` or canvas w/ 0.5pt `HAIRLINE_CANVAS`, 12pt radius, 0.2" padding. Per cell: left zone (≈1.7") icon 0.6–0.8" `ACCENT`-tinted or mini-donut or KPI `W_BOLD` 28pt; right zone heading `W_SEMIBOLD` 14pt `INK` + body `W_REGULAR` 11pt `TEXT_SECONDARY`.

### L — Big Number Hero
- Left half (X 0.5"–6.27"): number `W_BOLD` 96–144pt `INK`, baseline Y 4.6". Unit `W_LIGHT` 28pt `TEXT_MUTED`. Desc below `W_MEDIUM` 14pt `INK`. Optional label above Y≈3.2" `W_SEMIBOLD` 11pt `ACCENT` uppercase 2pt track.
- Right half (X 6.57"–12.83"): 3 stacked evidence cards (1.4"h, `SURFACE_BAND`, 12pt radius) OR one chart. Source Y 6.55" `W_REGULAR` 9pt `TEXT_FINE`.
- Number floor 96pt; if it won't fit, it's not a Big Number Hero.

### M — Three-Up Screenshot/Platform Comparison
- 3 cols 3.97"w at X 0.5"/4.6"/8.7". Per col: Y 2.39"–2.7" label pill (`ACCENT`, white `W_SEMIBOLD` 11pt); Y 2.85"–4.5" screenshot frame 16pt radius 1.65"h (max 1 col highlighted w/ `SHADOW_GLOW`); Y 4.65"–4.95" subtitle `W_SEMIBOLD` 13pt; Y 5.05"–6.85" bullets `W_REGULAR` 11pt `TEXT_SECONDARY`.

### N — Cover with Hero Image + CTA Pills (skeleton override)
- Half-bleed image (X 0"–6.67" or mirror) + title block on canvas half. Title `W_EXTRABOLD` 44pt `INK` lh 1.15. Subtitle `W_LIGHT` 18pt `TEXT_MUTED`. 2 CTA pills Y 5.5" (see components). Logo top-right of canvas half. Optional `HERO_WASH` overlay 30% on image for contrast.

### O — Closing with CTA Pills (skeleton override)
- Full-bleed `SURFACE_DARK` or `HERO_WASH`. Title centered Y 2.8" `W_EXTRABOLD` 36pt `TEXT_ON_DARK`. Subtitle Y 4.2" `W_LIGHT` 18pt. 2 CTA pills Y 5.6" (on-dark variant). Logo centered top Y 0.7". No page#, no chapter label.

---

## Inhouse / Global / Diagram Patterns P–Z

### P — Center Hero with KPI Wings
- Center (X 4.5"–8.83", Y 2.5"–6.7"): hero visual, 16pt radius, anchored Y 4.6". Left wing (X 0.5"–4.2") & right wing (X 9.13"–12.83"): 2–3 KPI cards each (1.2–1.5"h, 12pt radius, `SURFACE_BAND`, 0.18" padding; number `W_BOLD` 28–32pt `INK`). Optional `SHADOW_GLOW` on center (≤1/slide). Wings balanced L/R.

### Q — Radial Label Layout
- Center anchor (X 5.66"–7.66", Y 3.4"–5.6"), 16pt radius. Labels at clock positions (12: X 6.16"–7.16" Y 2.55"; 3: X 9.5"–12.83" Y 4.35"; 6: X 6.16"–7.16" Y 6.25"; 9: X 0.5"–3.83" Y 4.35"; optional diagonals 1/5/7/11). Each label: pill 9999px, `SURFACE_CANVAS`+1pt `HAIRLINE_CANVAS` or `SURFACE_BAND`, `W_SEMIBOLD` 11–12pt `INK`, 8×14pt padding. Optional 0.75pt dashed `HAIRLINE_CANVAS` spokes. 4–8 labels at clean clock positions only.

### R — Hub-and-Spoke Diagram
- Hub centered X 6.67" Y 4.62", diameter 2.0", `INK` or `HERO_WASH` fill, center text `W_BOLD` 18pt `TEXT_ON_DARK`, optional 3pt `ACCENT` ring. 5–8 spokes at radius 2.4", diameter 1.1", `SURFACE_BAND`+0.5pt `HAIRLINE_CANVAS` (or ≤3 sub-color fills). Spoke text `W_SEMIBOLD` 12pt `INK`. Connectors 0.75pt `ACCENT` behind circles (z-order). Even distribution (6→60°, 8→45°). Diagram owns the body box — no other chart.

### S — Day-Cycle / Time-Series Timeline
- Spine Y 4.6", X 0.5"–12.83", 1pt `ACCENT`. 4–6 markers evenly spaced, 0.32" circles `SURFACE_CANVAS`+1.5pt `ACCENT` border. Above (Y 2.85"–4.2"): abstract icon 0.6–0.8" `ACCENT`/`INK`. Below (Y 5.0"–6.85"): time label `W_SEMIBOLD` 12pt + desc `W_REGULAR` 10pt `TEXT_SECONDARY`. Icons abstract geometric only (no photo/3D/gradient).

### T — Persona / Profile Card Row
- 4 cards 2.85"w at X 0.5"/3.6"/6.7"/9.8", Y 2.5"–6.7", `SURFACE_BAND` or canvas+0.5pt `HAIRLINE_CANVAS`, 16pt radius. Per card: avatar circle 0.85" (`SURFACE_CARD` BG, abstract two-tone `INK`+`ACCENT`); name `W_SEMIBOLD` 14pt; sub-tag pill (`ACCENT`, white `W_SEMIBOLD` 9pt); 3–4 detail rows icon+`W_REGULAR` 10pt. **Avatars abstract/iconic — never photo-realistic, never identifiable real people.**

### U — Asymmetric Mixed Composition (pick one, 3 zones, one dominant)
- U-1: L 0.5"–4.0" 2 KPI cards · C 4.3"–8.0" hero visual · R 8.3"–12.83" large insight card.
- U-2: L 0.5"–6.0" big statement `W_BOLD` 24–28pt · C 6.3"–9.5" mockup · R 9.8"–12.83" 3 mini-KPI tiles.
- U-3: L 0.5"–4.0" pull-quote card · C 4.3"–8.5" mockup · R 8.8"–12.83" compact spec list.
- All zones align Y 2.5" top / 6.7" bottom; ≥95% body width; exactly one zone dominant.

### V — Statement + Visual + Floating Callout
- Left (X 0.5"–6.27"): statement `W_BOLD` 28–32pt `INK` lh 1.25 + body `W_REGULAR` 13pt `TEXT_SECONDARY` lh 1.55. Right (X 6.57"–12.5"): visual 16pt radius (~3.5–4.5"w). Floating callout: 1.5pt `ACCENT` arrow → hollow circle anchor; bubble `INK` (dark) or `SURFACE_CANVAS`+1pt `ACCENT`, 12pt radius, `W_MEDIUM` 12pt, ≤3.0"w. Callout must terminate at a specific anchor.

### W — Three-Column Compare Matrix (one column recommended)
- Full-width X 0.5"–12.83". Spec col X 0.5"–3.0" `W_MEDIUM` 11pt `TEXT_MUTED`. 3 compare cols X 3.3"–12.83" (3.18" each). Headers: cols 1–2 `SURFACE_CARD` + `W_SEMIBOLD` 14pt `INK`; col 3 (recommended) `INK` BG + `W_SEMIBOLD` 14pt `TEXT_ON_DARK` + optional badge pill (`ACCENT`, "RECOMMENDED"). Body: cols 1–2 alternate `SURFACE_CANVAS`/`SURFACE_BAND`; col 3 continuous `SURFACE_CARD` (elevated). 0.5pt `HAIRLINE_CANVAS` row dividers. 5–8 rows. Exactly one column highlighted.

### X — Character Process Flow
- 5 stages 2.34"w at X 0.5"/2.94"/5.38"/7.82"/10.26", Y 2.5"–6.7". Per stage: Y 2.7"–3.7" character circle 0.95" `SURFACE_BAND` w/ abstract two-tone (`INK`+`ACCENT`) figure, numbered badge 0.32" `ACCENT` white `W_BOLD` 12pt; Y 3.85"–4.25" label `W_SEMIBOLD` 13pt; Y 4.4"–6.7" desc `W_REGULAR` 10–11pt `TEXT_SECONDARY`. 1pt `ACCENT` arrows Y~3.2" (gutter only). Optional bottom band Y 6.0"–6.7" `SURFACE_CARD` 3pt left-border `ACCENT`. **Characters abstract two-tone — never photo-realistic / real people.**

### Y — Section Divider, Bottom-Left Anchor (skeleton override)
- Full-bleed `SURFACE_DARK` / `SURFACE_CARD` / `HERO_WASH` / `SURFACE_BAND`. Logo top-right X 12.13" Y 0.5". Optional tag X 0.6" Y 0.6" `W_SEMIBOLD` 11pt 2pt track. Decorative number X 0.6" Y 4.6" `W_ULTRALIGHT` 28pt. Title X 0.6" Y 5.1"–6.5" `W_EXTRABOLD` 56–72pt (`TEXT_ON_DARK` on dark / `INK` on light), lh 1.05, track −1.0pt. Subtitle X 0.6" Y 6.6"–6.95" `W_LIGHT` 18pt. No body content, no page#.

### Z — Sub-section Pre-Divider (standard skeleton, NOT override)
- `SURFACE_CARD` or `SURFACE_BAND` full-bleed. Standard header strip (chapter label continues — chapter doesn't change). Body box: single left-anchored sub-title X 0.6" centered Y 4.6" `W_BOLD` 36–44pt `INK`, optional sub-label `W_MEDIUM` 14pt `TEXT_MUTED`. Standard footer.

---

## Components (resolve tokens from design.md)

- **Header tag/badge:** pill 9999px, 4×10pt padding, `ACCENT`/sub-color/`POINT` BG, `W_SEMIBOLD` 9–10pt white. ≤1/slide.
- **Numbered subsection header:** `1)` `W_SEMIBOLD` 12pt `ACCENT` + title `W_SEMIBOLD` 14pt `INK`, optional 0.5pt `HAIRLINE_CANVAS` underline.
- **Back-to-TOC link:** `목차로 돌아가기 ↗` / `Back to contents ↗`, `W_REGULAR` 10pt `TEXT_MUTED`, arrow `ACCENT`, footer-right.
- **Pill CTA button (cover/closing only, ≤2/slide):** 9999px, 12×24pt padding. On-canvas: `SURFACE_CANVAS` BG, 1pt `HAIRLINE_CANVAS`, `W_MEDIUM` 13–14pt `INK`, arrow `ACCENT`. On-dark: `SURFACE_CANVAS` (primary) or transparent+border (secondary).
- **Hero image frame:** body evidence 16pt radius, 0.5pt `HAIRLINE_CANVAS`; cover full-bleed no frame. Phone mockup 9:19.5.
- **Question bubble:** rounded rect 24pt radius + tail, `SURFACE_BAND`/canvas+0.5pt `HAIRLINE_CANVAS`, `W_MEDIUM` 14pt `INK`. 3–5 staggered diagonal.
- **Quote card:** 16pt radius, `SURFACE_BAND`/canvas+1pt `HAIRLINE_CANVAS`, quote mark `W_BOLD` 48pt `ACCENT`, body `W_MEDIUM` 16–18pt `INK`, attribution `W_REGULAR` 12pt `TEXT_MUTED`.
- **Phone/device mockup pair:** 9:19.5, side-by-side/overlap/staggered, 16pt radius screen corners.
- **Floating arrow callout:** hollow circle anchor + 1.5pt `ACCENT` arrow + bubble (`INK` dark / `SURFACE_CANVAS`+`ACCENT` light), 12pt radius, `W_MEDIUM` 12pt, ≤3.0"w.
- **Bottom-anchored title block:** number `W_ULTRALIGHT` 24–32pt + title `W_EXTRABOLD` 56–72pt + subtitle `W_LIGHT` 16–18pt, left X 0.6", title baseline Y≈6.5".
- **Persona/profile avatar:** circle 0.85–1.0", `SURFACE_CARD`/`SURFACE_BAND` BG, abstract two-tone `INK`+`ACCENT`. Never photo-realistic / real people / copyrighted characters. Uniform diameter across deck.

---

## Pattern Picker (quick)
TOC→G · spec detail→H · journey w/ screenshots→I or X · 3–6 compare→J · 3 compare(1 rec)→W · 4 quadrants→K · single KPI→L · 3 platforms→M · center+KPI→P · radial labels→Q · ecosystem→R · timeline→S · personas→T · 3-zone asymmetric→U · statement+callout→V · cover→N · closing→O · section divider→Y · mini divider→Z · else core A–F.

If a slide fits no pattern, the message is unclear or overloaded — fix the message, then pick.

---

*Coordinates = structure (invariant). Colors = `TOKEN` (from active design.md). To retheme, swap design.md; these patterns render in the new palette automatically.*
