# Build Pipeline (Brand-Neutral)
## PPTX generation, QA, and pptxgenjs technical rules

This file is the build layer. It is independent of brand — it works identically whatever the active `design.md` is. Always pair this skill with the public **pptx** skill (`/mnt/skills/public/pptx/SKILL.md`) for the underlying pptxgenjs / python-pptx / OOXML mechanics. This file adds the verified deck-build workflow and the hard-won technical rules on top of it.

---

## 1. Verified Build Workflow

1. **`node build.js`** (pptxgenjs) → generate the PPTX.
2. **`python /mnt/skills/public/pptx/scripts/office/soffice.py --headless --convert-to pdf [file]`** → LibreOffice PDF conversion.
3. **`pdftoppm -jpeg -r 110-150 [pdf] slide`** → per-slide JPEG previews → `view` each for visual QA.

Iterate build → convert → preview → fix until the iteration checklist (structure_skeleton.md §3 + brand checks from design.md) passes.

---

## 2. pptxgenjs Technical Rules (must follow)

- Use `p.ShapeType.ellipse` (v4; not `oval`). BUT **`oval`/`ellipse` lose fill color in LibreOffice PDF** — for circles, use `roundRect` with `rectRadius` = half the width/height for a visually identical circle that renders correctly.
- HEX colors **without `#` prefix** in pptxgenjs.
- **Create shadow objects via a fresh factory call per shape** — pptxgenjs mutates shadow objects in place, so never reuse one object across shapes.
- Shadow opacity uses the `opacity` property (0–1 float), never 8-char hex.
- Overwrite files with `cat > build.js << 'EOF'` heredoc via bash (create_file can silently fail on overwrite).
- Font/spacing compatibility (LibreOffice QA ↔ PowerPoint): fixed-point line spacing (`spcPts`) not percentage (`spcPct`); `noAutofit` not `normAutofit` for fixed placement; add safety margins to text-box heights.
- Empty `<p:txBody>` corrupts PPTX in PowerPoint (LibreOffice renders fine) → guard with `if not paras` (not `if paras is None`) to catch empty lists. Verify `presentation.xml` element order: `notesMasterIdLst` before `sldIdLst`.

---

## 3. Logo / Image Handling

- If a white-on-transparent logo variant is needed and only a dark/누끼 source exists: extract bright pixels (brightness >128–200 threshold) as white-on-transparent; reuse the mask filled black for the dark variant; anti-alias mid-range brightness (20–200) with partial alpha.
- **LibreOffice PDF conversion degrades PNG transparency** → logo previews may look faint/clipped; the actual PowerPoint render is correct. Logo safe zone: keep x-position inward (e.g. `x:11.55`, not `x:11.77`) to avoid edge clipping in LibreOffice preview.
- Korean (or other non-ASCII) filenames: macOS NFD normalization can stop Node.js reading them → copy assets to ASCII-named equivalents with Python first.
- Insert the logo PNG as-is, aspect-locked, alpha preserved. Resolve `LOGO_FILE` / `LOGO_FILE_WHITE` and all placement/forbidden-ops from the active design.md §4.

---

## 4. Cover / Closing Preservation & Transplant

- Many briefs require **slide 1 (cover) preserved exactly as-is** and often the closing too. Treat "preserve cover" as a default unless told otherwise.
- Cover transplant workflow: stage the cover slide XML + media assets into the body deck package → prepend the cover slide ID to `sldIdLst` in `presentation.xml`.

---

## 5. Key Paths

- Public pptx skill: `/mnt/skills/public/pptx/SKILL.md`
- LibreOffice converter: `/mnt/skills/public/pptx/scripts/office/soffice.py`
- Brand assets: resolve from the active design.md §6 manifest (e.g. `/mnt/project/`)
- Working scratch: `/home/claude/`
- Final outputs: `/mnt/user-data/outputs/`

---

*Build mechanics are brand-independent. The only brand-dependent inputs are the token values and asset paths supplied by the active design.md.*
