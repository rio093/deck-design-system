# Example Design Token Set — ARTH
## A reference `design.md` for the deck-design-system skill

This file is an **example design token set** demonstrating how to fill out a `design.md` (or `DESIGN_TEMPLATE.md`) for the brand-neutral deck-design-system skill. It carries ONLY the brand layer — colors, typography, logo rules, atmosphere, mood. It does NOT define structure, patterns, or build mechanics (those live in the skill's `references/structure_skeleton.md`, `pattern_library.md`, and `build_pipeline.md` and never change per brand).

Swap this file out for any other brand's `design.md` to retheme the entire deck system. The skeleton, the A–Z patterns, and the build pipeline stay identical; only the tokens below change.

---

## 1. Brand Identity Summary

- **Brand:** ARTH (어스) — Korean aromatherapy & fragrance brand (이래에프엔씨㈜)
- **Voice:** refined, minimal, warm, organic, restrained. Apple-grade product clarity meets Korean aromatherapy stillness.
- **Atmosphere:** warm off-white canvas, deep charcoal ink, muted sand-gold accents echoing dried botanicals.

---

## 2. Color Tokens

### Trinity (foundation — required for every design.md)
| Role | Token | HEX |
|---|---|---|
| INK (primary text / dominant weight) | `INK` | `#1A1A1A` |
| CANVAS (default slide background) | `CANVAS` | `#F7F5F0` |
| ACCENT (signature accent — never full-bleed background) | `ACCENT` | `#B8A48C` |

### Accent scale
- `ACCENT_LIGHT` `#D4C8B5` — subtle tints, table header rows, progress tracks
- `ACCENT_500` `#B8A48C` — divider lines, KPI highlights, icon strokes, bullets
- `ACCENT_DARK` `#8C7A64` — pressed/emphasized accent, secondary icon fills

### Text
- `TEXT_PRIMARY` `#1A1A1A` · `TEXT_SECONDARY` `#3D3D3A` · `TEXT_MUTED` `#6C6A64` · `TEXT_FINE` `#8E8B82`
- On dark: `TEXT_ON_DARK` `#F7F5F0` · `TEXT_ON_DARK_MUTED` `#A09D96`

### Surface (used by the Surface-Alternation rule)
- `SURFACE_CANVAS` `#F7F5F0` (mode 1) · `SURFACE_CARD` `#EDE8DF` (mode 2) · `SURFACE_DARK` `#1A1A1A` (mode 3)
- `SURFACE_BAND` `#F0EBE3` · `SURFACE_ELEVATED_DARK` `#2A2A28`
- Hairlines: `HAIRLINE_CANVAS` `#DDD8CE` · `HAIRLINE_DARK` `#3A3A38`

### Sub colors (data / charts — optional per brand)
- `SUB_1` `#45463E` (Dark Olive) · `SUB_2` `#8C9B58` (Olive Green, positive) · `SUB_3` `#8F7C75` (Mauve Taupe) · `SUB_4` `#3D2920` (Dark Brown)

### Point color (≤2 uses per deck — CTA/alert only, never surface or body text)
- `POINT` `#DF3623` (ARTH Red)

### Semantic
- positive `#8C9B58` · negative `#C25050` · neutral `#B8A48C`

### Shadows (warm-tinted — never pure black)
- `SHADOW_STD` `rgba(60,50,40,0.08) 0px 4px 6px`
- `SHADOW_GLOW` `rgba(140,122,100,0.16) 0px 0px 15px` (featured, ≤1/slide)
- `SHADOW_ELEVATED` `rgba(40,30,20,0.08) 0px 12px 16px -4px`

### Hero Tonal Wash (premium gradient — ≤3 elements/deck, ≤1/slide; never on charts/text/headers)
- `HERO_WASH_DARK` `linear-gradient(135deg, #1A1A1A 0%, #45463E 50%, #8C7A64 100%)`
- `HERO_WASH_WARM` `linear-gradient(135deg, #8C7A64 0%, #B8A48C 50%, #D4C8B5 100%)`
- Fixed: 135°, 3 stops at 0/50/100%. Text on wash = `TEXT_ON_DARK`.

---

## 3. Typography Tokens

- `FONT_FAMILY`: **AppleSDGothicNeo** (sole family; weight, not family, builds hierarchy)
- Fallback string (export-safety only): `"Apple SD Gothic Neo", "AppleSDGothicNeo", -apple-system, system-ui, sans-serif`
- Embed the font in the .pptx on export.

### Weight → role map
| Token | Weight | Role |
|---|---|---|
| `W_ULTRALIGHT` | 100 | chapter numbers, decorative display |
| `W_THIN` | 200 | large pull-quotes |
| `W_LIGHT` | 300 | subtitles, leads, on-dark secondary |
| `W_REGULAR` | 400 | body, captions, sources |
| `W_MEDIUM` | 500 | emphasized body, card titles, KPI units |
| `W_SEMIBOLD` | 600 | section labels, body H2/H3, chart titles |
| `W_BOLD` | 700 | headlines, KPI numbers |
| `W_EXTRABOLD` | 800 | chapter titles, hero headlines |
| `W_HEAVY` | 900 | max-impact single words (rare) |

### Type scale (16:9, 1920×1080 ref)
- Headline `W_BOLD` 32–40pt / lh 1.20 / track −0.3pt / `INK`
- Subtitle `W_LIGHT` 16pt / lh 1.45 / `TEXT_MUTED`
- Body H2 `W_SEMIBOLD` 18–20pt · Body H3 `W_SEMIBOLD` 14–16pt
- Body `W_REGULAR` 12–14pt (floor 12pt) / lh 1.50 / `TEXT_SECONDARY`
- KPI number `W_BOLD` 36–48pt · KPI unit `W_LIGHT` 14–16pt · KPI label `W_MEDIUM` 11–12pt
- Chapter label `W_SEMIBOLD` 11pt / track 2pt uppercase / `TEXT_MUTED`
- Page number `W_REGULAR` 9–10pt / `TEXT_MUTED` · Source `W_REGULAR` 9–10pt / `TEXT_FINE`
- Max 3 text sizes per slide.

---

## 4. Logo Tokens

- `LOGO_FILE`: `ARTH_BI.png` (transparent PNG / 누끼, alpha preserved)
- `LOGO_FILE_WHITE` (optional): `ARTH_logo_white_transparent.png`
- Aspect ratio: 1 : 4.4 (height : width). Never alter.
- Color forms: black on light BG (default); white on dark BG (uniform inversion only).
- Placement: content/divider → top-right ≈0.5" from right edge, Y≈0.44", height ≈0.24"; cover/closing → centered.
- **Forbidden:** underline, shadow, glow, border, box-behind, recolor (other than B/W), crop, stretch, skew, rotate, letter-spacing change, typeface substitution, complex/patterned backgrounds.
- Brightness rule: BG ≥50% → black mark; <50% → white mark.
- Optional 3-dot motif (●●● vertical) = Body/Mind/Soul; cover/divider/closing only, never in body as padding.

---

## 5. Mood / Atmosphere Directives

- Surface pacing: alternate `SURFACE_CANVAS` → `SURFACE_CARD` → `SURFACE_DARK`; never two identical surfaces back-to-back.
- Depth: color-block & hairline first, shadow rare. `SHADOW_GLOW` ≤1 element/slide. Flat is default.
- Cards: radius 12–24pt; buttons 8pt; tabs/pills 9999px. Never sharp corners on content cards.
- Headlines: So-what noun phrases (한 구 단위), conclusion-first, MECE. Avoid verbose "~합니다/~입니다" sentences.
- No emojis anywhere.
- Default background = `CANVAS` (warm off-white), never pure white.

---

## 6. Brand-Specific Assets (optional manifest)

| Asset | Path |
|---|---|
| Logo (black/누끼) | `/mnt/project/ARTH_BI.png` |
| Logo (white transparent) | `/mnt/project/ARTH_logo_white_transparent.png` |
| Product cutouts (PNG) | `/mnt/project/*.png` |
| Product master list | `/mnt/project/ARTH_전상품.xlsx` |
| Brand introduction | `/mnt/project/브랜드소개서_ARTH어스.pdf` |

---

*This is an EXAMPLE design token set. To retheme: copy this file's structure, replace every token value with the new brand's colors/fonts/logo, and feed it to the deck-design-system skill as the active `design.md`. Structure, patterns, and build pipeline never change.*
