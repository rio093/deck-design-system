# Design Token Template — `design.md`
## Fill this out to retheme the deck-design-system skill for any brand

Copy this file, rename it `design.md` (or any name), and replace every `«...»` placeholder with your brand's values. Feed the completed file to the deck-design-system skill. The skill's structure (Locked Skeleton), patterns (A–Z), and build pipeline stay identical — only the tokens below change the look and mood.

**Rule of thumb:** if it's a color, font, logo, radius, shadow, or mood directive → it belongs here. If it's a coordinate, zone, pattern, or build step → it belongs to the skill, not here. Do not redefine structure in this file.

> See `references/example_design_arth.md` for a fully filled-out example.

---

## 1. Brand Identity Summary
- **Brand:** «brand name»
- **Voice:** «3–5 adjectives: e.g., bold, energetic, tech-forward»
- **Atmosphere:** «one-line mood: e.g., high-contrast dark UI with electric accents»

## 2. Color Tokens

### Trinity (REQUIRED)
| Role | Token | HEX |
|---|---|---|
| INK (primary text) | `INK` | «#______» |
| CANVAS (default background) | `CANVAS` | «#______» |
| ACCENT (signature accent, never full-bleed BG) | `ACCENT` | «#______» |

### Accent scale
- `ACCENT_LIGHT` «#______» · `ACCENT_500` «#______» · `ACCENT_DARK` «#______»

### Text
- `TEXT_PRIMARY` «#______» · `TEXT_SECONDARY` «#______» · `TEXT_MUTED` «#______» · `TEXT_FINE` «#______»
- On dark: `TEXT_ON_DARK` «#______» · `TEXT_ON_DARK_MUTED` «#______»

### Surface (drives Surface-Alternation rule — need ≥3 distinct modes)
- `SURFACE_CANVAS` «#______» (mode 1) · `SURFACE_CARD` «#______» (mode 2) · `SURFACE_DARK` «#______» (mode 3)
- `SURFACE_BAND` «#______» · `SURFACE_ELEVATED_DARK` «#______»
- `HAIRLINE_CANVAS` «#______» · `HAIRLINE_DARK` «#______»

### Sub colors (data/charts — optional, list as many as needed)
- `SUB_1` «#______» · `SUB_2` «#______ (positive)» · `SUB_3` «#______» · `SUB_4` «#______»

### Point color (≤2 uses/deck — CTA/alert only)
- `POINT` «#______»

### Semantic
- positive «#______» · negative «#______» · neutral «#______ (usually = ACCENT)»

### Shadows (define tint — pure black is discouraged)
- `SHADOW_STD` «rgba(...) 0px 4px 6px»
- `SHADOW_GLOW` «rgba(...) 0px 0px 15px» (featured, ≤1/slide)
- `SHADOW_ELEVATED` «rgba(...) 0px 12px 16px -4px»

### Hero Tonal Wash (optional premium gradient — ≤3/deck, ≤1/slide; never on charts/text/headers)
- `HERO_WASH_DARK` «linear-gradient(135deg, #__ 0%, #__ 50%, #__ 100%)»
- `HERO_WASH_WARM` «linear-gradient(...)»
- Keep angle/stops fixed across the deck. If your brand has no gradient, write "none — flat surfaces only".

## 3. Typography Tokens
- `FONT_FAMILY`: «sole family name»
- Fallback string (export only): «"Family", -apple-system, system-ui, sans-serif»
- Embed the font in the .pptx on export.

### Weight → role map (map your font's weights)
| Token | Weight | Role |
|---|---|---|
| `W_LIGHT` | «300» | subtitles, leads |
| `W_REGULAR` | «400» | body, captions, sources |
| `W_MEDIUM` | «500» | emphasized body, card titles |
| `W_SEMIBOLD` | «600» | section labels, H2/H3, chart titles |
| `W_BOLD` | «700» | headlines, KPI numbers |
| `W_EXTRABOLD` | «800» | chapter/hero titles |
(add UltraLight/Thin/Heavy if your font has them)

### Type scale (16:9, 1920×1080 ref — adjust sizes if brand demands, keep ≤3 sizes/slide & 12pt body floor)
- Headline `W_BOLD` «32–40»pt / lh «1.20» / track «−0.3»pt / `INK`
- Subtitle `W_LIGHT` «16»pt / `TEXT_MUTED`
- Body `W_REGULAR` «12–14»pt / lh «1.50» / `TEXT_SECONDARY`
- KPI number `W_BOLD` «36–48»pt · Chapter label `W_SEMIBOLD` «11»pt track «2»pt uppercase
- Page number / Source `W_REGULAR` «9–10»pt

## 4. Logo Tokens
- `LOGO_FILE`: «path/to/logo.png» (transparent PNG preferred)
- `LOGO_FILE_WHITE` (optional): «path/to/logo_white.png»
- Aspect ratio: «1 : __» — never alter.
- Color forms: «black on light / white on dark» (inversion rules).
- Placement: content/divider → top-right; cover/closing → centered. (Coordinates fixed by skeleton.)
- Forbidden ops: «list any brand-specific don'ts, plus the universal: no decoration, no recolor beyond B/W, no skew/stretch».
- Brightness rule: BG ≥50% → «dark» mark; <50% → «light» mark.

## 5. Mood / Atmosphere Directives
- Surface pacing: «alternate which surfaces? default = CANVAS→CARD→DARK, never repeat back-to-back».
- Depth: «shadow-heavy or flat? glow usage limit».
- Corner radius: cards «12–24»pt · buttons «8»pt · pills «9999px».
- Headline voice: «So-what noun phrases? full sentences? language?».
- Emoji policy: «allowed / forbidden».
- Default background: «CANVAS token».

## 6. Brand Assets Manifest (optional)
| Asset | Path |
|---|---|
| Logo | «/mnt/project/...» |
| Product images | «...» |
| Data source | «...» |

---

*Once filled, this file IS the brand. The deck-design-system skill reads these tokens and applies them to its fixed structure + patterns + build pipeline. To switch brands, swap this file — nothing else.*
