---
name: deck-design-system
description: "브랜드 중립 16:9 PPTX 슬라이드 디자인·생성·리디자인 스킬. 컬러·타이포·로고·분위기는 외부 design.md(디자인 토큰 파일)에서 주입받고, Locked Skeleton 구조·26개 레이아웃 패턴(A–Z)·pptxgenjs 빌드 파이프라인은 어떤 브랜드에도 동일하게 적용한다. design.md만 교체하면 같은 구조·패턴으로 전혀 다른 컬러와 분위기의 덱을 만들 수 있다. '슬라이드 만들어', 'PPT 만들어', '발표자료', '덱 제작', '제안서', '미디어킷', '리디자인', '브랜드 디자인 적용', 'design.md로 만들어', '다른 컬러로 적용' 등 .pptx 생성·편집 요청 시 활성화. 항상 public pptx 스킬과 함께 사용하며, 사용자가 design.md를 제공하면 그것을 적용하고, 없으면 references/example_design_arth.md(ARTH 예시 토큰)를 폴백으로 쓴다."
---

# Deck Design System — 브랜드 중립 PPTX 디자인 스킬

16:9 프레젠테이션을 만드는 **구조·패턴·빌드 엔진**. 브랜드의 컬러·타이포·로고·분위기는 이 스킬이 소유하지 않는다 — 외부 **`design.md`(디자인 토큰 파일)**에서 주입받는다. design.md만 갈아끼우면 동일한 Locked Skeleton과 26개 패턴(A–Z)으로 전혀 다른 브랜드 덱을 생성한다.

## 핵심 분리 원칙

| 레이어 | 소유자 | 브랜드별 교체 |
|---|---|---|
| **구조** (Locked Skeleton, 존 좌표, 그리드) | 이 스킬 (`references/structure_skeleton.md`) | ❌ 불변 |
| **패턴** (A–Z 레이아웃, 컴포넌트) | 이 스킬 (`references/pattern_library.md`) | ❌ 불변 (좌표=구조) |
| **빌드** (pptxgenjs, QA 파이프라인) | 이 스킬 (`references/build_pipeline.md`) + public pptx 스킬 | ❌ 불변 |
| **컬러·타이포·로고·분위기** (토큰) | **외부 `design.md`** | ✅ 매번 교체 |

패턴 안의 모든 색은 `INK`·`CANVAS`·`ACCENT` 같은 **토큰명**으로만 적혀 있다. 빌드 시 활성 design.md에서 실제 hex로 해석한다.

## 작업 시작 전 필수 절차 (READ FIRST)

슬라이드 생성·편집 요청을 받으면 코드 작성 전 **반드시** 이 순서를 따른다:

1. **활성 design.md를 확정한다.**
   - 사용자가 design.md(또는 디자인 토큰)를 제공했으면 → 그것을 활성 토큰으로 사용.
   - 제공하지 않았으면 → 사용자에게 "어떤 브랜드/디자인 토큰을 적용할까요? 없으면 ARTH 예시로 진행합니다"라고 한 번 확인하거나, 명시적 지시가 없으면 `references/example_design_arth.md`를 폴백으로 사용.
   - 새 브랜드를 처음 적용한다면 `DESIGN_TEMPLATE.md`를 사용자에게 안내해 채우게 한다.
2. **`references/structure_skeleton.md`를 읽는다** — 존 좌표·하드 바운더리·시각화 우선·슬라이드 타입.
3. **`references/pattern_library.md`를 읽는다** — 메시지에 맞는 패턴(A–Z) 선택.
4. **`references/build_pipeline.md` + public pptx SKILL.md를 읽는다** — 빌드 방식 확정.
5. **활성 design.md의 토큰·자산 경로를 확인한다** — 로고 파일, 폰트, 컬러, 자산 매니페스트.
6. 빌드 → PDF 변환 → JPEG 미리보기 QA → 체크리스트 통과 → 산출물 제출.

**절대 색·폰트·로고 규칙을 기억에 의존해 추정하지 않는다.** 정본은 활성 design.md다. 좌표·구조의 정본은 references 파일이다.

## 파일 구조

```
deck-design-system/
├── SKILL.md                          ← (이 파일) 브랜드 중립 라우터 + design.md 주입 로직
├── DESIGN_TEMPLATE.md                ← 빈 design.md 작성 양식 (새 브랜드용)
└── references/
    ├── structure_skeleton.md         ← Locked Skeleton·존·그리드·시각화 규칙 (불변)
    ├── pattern_library.md            ← 패턴 A–Z + 컴포넌트 (좌표=구조, 색=토큰)
    ├── build_pipeline.md             ← pptxgenjs 빌드·QA·기술 규칙 (불변)
    └── example_design_arth.md        ← ARTH 예시 디자인 토큰 (폴백/샘플)
```

## design.md 교체 방법 (리테마)

1. `DESIGN_TEMPLATE.md`를 복사해 `design.md`로 만든다.
2. 모든 `«...»` 자리표시자를 새 브랜드의 컬러·폰트·로고·분위기로 채운다. (예시는 `references/example_design_arth.md` 참고)
3. 완성된 design.md를 이 스킬에 활성 토큰으로 전달한다.
4. **구조·패턴·빌드는 그대로** — 같은 Locked Skeleton과 A–Z 패턴이 새 팔레트로 렌더링된다.

## 필수 토큰 (design.md가 반드시 정의해야 함)

최소 트리니티 + surface 3모드 + 폰트 + 로고가 없으면 빌드 불가:
- 컬러: `INK` / `CANVAS` / `ACCENT`, `SURFACE_CANVAS` / `SURFACE_CARD` / `SURFACE_DARK`, `TEXT_*`, `HAIRLINE_*`, `SHADOW_STD`
- 타이포: `FONT_FAMILY` + weight 맵(`W_LIGHT`~`W_BOLD` 최소)
- 로고: `LOGO_FILE` + 종횡비 + 배치/금지 규칙
- 선택: `SUB_*`(차트), `POINT`(CTA ≤2/덱), `HERO_WASH_*`(그라데이션 ≤3/덱)

design.md에 토큰이 빠져 있으면 사용자에게 해당 토큰을 물어보고 채운 뒤 진행한다. 빈 값으로 임의 추정하지 않는다.

## 브랜드 중립 절대 규칙 (구조 레이어 — 항상 적용)

design.md가 무엇이든 아래는 불변이다:

1. **16:9 전용** (13.333"×7.5"). 다른 비율 거부.
2. **단일 폰트 패밀리** — design.md의 `FONT_FAMILY` 하나만. 위계는 굵기로. 임베드.
3. **로고 무결성** — `LOGO_FILE` 원본 그대로. 장식·박스·왜곡·B/W 외 리컬러 금지.
4. **Locked Skeleton 고정 좌표** — 5존 동일 좌표. 커버·디바이더·클로징만 오버라이드.
5. **Hard Boundary** — 본문 Y 2.39"–6.85" 안에만. 안 들어가면 슬라이드 분할.
6. **Visualization-First** — 숫자·비교·프로세스·구조는 시각화. 슬라이드당 1–2개.
7. **Body Density** — 하단 비우지 않되 장식 패딩·존 침범으로 채우지 않음.
8. **Surface 교차** — 연속 슬라이드 동일 surface 모드 금지.
9. **POINT 컬러 ≤2/덱**, surface·본문 텍스트 금지.
10. **HERO_WASH ≤3/덱·≤1/슬라이드**, 차트·텍스트·헤더 금지.
11. **이모지 정책은 design.md 따름** (기본 금지 권장).
12. **헤드라인 텍스트 크기 ≤3종/슬라이드, 본문 12pt 플로어.**

## 패턴 인덱스 (A–Z)

A KPI Strip · B Two-Col Compare · C Diagram-Centered · D Process Flow · E Quote+Evidence · F Stacked Layers · G TOC · H Spec+Visual(★) · I Multi-Stage · J Compare Matrix · K 2×2 Infographic · L Big Number · M Three-Up · N Cover+Hero · O Closing+CTA · P Center+KPI Wings · Q Radial · R Hub-Spoke · S Timeline · T Persona · U Asymmetric · V Statement+Callout · W 3-Col Compare(1 rec) · X Character Flow · Y Bottom-Left Divider · Z Mini Divider. (상세 좌표: `references/pattern_library.md`)

## 빌드 파이프라인 (요약)

`node build.js` → `python soffice.py --convert-to pdf` → `pdftoppm -jpeg` → `view` QA. pptxgenjs 기술 규칙(ellipse→roundRect, hex no #, fresh shadow factory, heredoc 덮어쓰기, spcPts/noAutofit, 빈 txBody 가드)과 로고/이미지 처리, 커버 보존은 `references/build_pipeline.md` 참조.

## 출력 전 체크리스트

`references/structure_skeleton.md` §3의 18항목(구조 불변) + 활성 design.md의 브랜드 토큰 일치 검증(폰트·로고·컬러가 토큰과 정확히 맞는지)을 실행. 하나라도 실패하면 고치기 전 완료 선언 금지.

---

*이 스킬은 구조·패턴·빌드를 소유하고, 브랜드는 design.md가 소유한다. design.md를 교체하면 동일 엔진으로 다른 분위기의 덱이 만들어진다. 실제 빌드는 public pptx 스킬과 병행한다.*
