---
marp: true
theme: default
paginate: true
size: 16:9
header: "HFF-Hub LLM-Wiki Overview"
footer: "hff-hub-workbase · 2026-04-20"
style: |
  section {
    font-size: 22px;
    padding: 50px 60px;
  }
  section.lead {
    justify-content: center;
    text-align: center;
    background: linear-gradient(135deg, #1e293b 0%, #0f172a 100%);
    color: #f1f5f9;
  }
  section.lead h1 {
    font-size: 56px;
    margin-bottom: 10px;
    color: #f8fafc;
    border-bottom: none;
    padding-bottom: 0;
  }
  section.lead h2 { font-size: 28px; font-weight: 400; color: #cbd5e1; }
  section.lead p { color: #e2e8f0; }
  section.lead strong { color: #f8fafc; }
  section.lead blockquote { color: #cbd5e1; border-left-color: #60a5fa; }
  section.lead a { color: #93c5fd; }
  section.section {
    justify-content: center;
    text-align: center;
    background: #0f172a;
    color: #e2e8f0;
  }
  section.section h1 {
    font-size: 72px;
    color: #f8fafc;
    border-bottom: none;
    padding-bottom: 0;
  }
  section.section h2 { color: #cbd5e1; font-weight: 400; }
  section.section p { color: #94a3b8; font-size: 24px; }
  section.section :not(pre) > code { background: #1e293b; color: #93c5fd; }
  section.section a { color: #93c5fd; }
  section h1 { color: #0f172a; border-bottom: 3px solid #3b82f6; padding-bottom: 6px; }
  section h2 { color: #1e40af; }
  :not(pre) > code { background: #e0e7ff; color: #1e3a8a; padding: 1px 6px; border-radius: 4px; }
  pre {
    background: #0f172a;
    color: #f8fafc;
    padding: 16px 20px;
    border-radius: 8px;
    overflow: auto;
  }
  pre code {
    background: transparent !important;
    color: #f8fafc !important;
    padding: 0;
    border-radius: 0;
  }
  /* Marp 구문 강조(span)가 기본 어두운 팔레트로 덮이는 것 방지 + 밝은 팔레트 */
  pre code span {
    color: #f1f5f9 !important;
  }
  pre code .hljs-comment { color: #94a3b8 !important; }
  pre code .hljs-string { color: #bbf7d0 !important; }
  pre code .hljs-keyword,
  pre code .hljs-meta,
  pre code .hljs-section { color: #93c5fd !important; }
  pre code .hljs-attr,
  pre code .hljs-name { color: #7dd3fc !important; }
  pre code .hljs-number { color: #fde68a !important; }
  pre code .hljs-title,
  pre code .hljs-built_in { color: #e2e8f0 !important; }
  table { font-size: 18px; }
  th { background: #1e40af; color: white; }
  tr:nth-child(even) { background: #f1f5f9; }
  .two-col { display: grid; grid-template-columns: 1fr 1fr; gap: 30px; }
  .tag { display: inline-block; background: #dbeafe; color: #1e40af; padding: 2px 10px; border-radius: 999px; font-size: 16px; margin: 2px; }
  .big { font-size: 42px; font-weight: 700; color: #1e40af; }
  blockquote { border-left: 4px solid #3b82f6; color: #475569; font-style: italic; }
---

<!-- _class: lead -->

# HFF-Hub LLM-Wiki

## 원본 13건 → 위키 49 페이지로의 재구성

재료 · 스키마 · 결과물 · 운영 방식 한 번에 보기

---

<!-- _class: section -->

# 01
## 왜 LLM 전용 위키인가

---

# 문제 — 답은 매번 채팅에 흩어진다

- LLM과의 대화는 **휘발적**이다. 오늘 정리한 맥락이 내일 사라진다.
- 같은 질문을 반복하면 매번 다른 답이 나온다 (**일관성 부족**).
- 프로젝트 문서는 사람이 쓰는 구조 → LLM이 1000줄 PRD 매번 전부 읽어야 함.
- **채팅 메모리 ≠ 지식 자산.** 기록 없이 쌓일 수 없다.

> **위키는 기억의 인프라다.** 1회성 답변이 아니라 누적되는 자산이어야 한다.

---

# llm-wiki 패턴이 제안하는 세 가지

<div class="two-col">

### 🔒 Raw Sources

- 불변(읽기 전용)
- 사람이 만든 원본
- 결코 LLM이 덮어쓰지 않음

### 📚 The Wiki

- LLM이 **직접 쓰고 갱신**
- 마크다운 + 교차 참조
- 페르소나·개념·기능 단위로 파편화

</div>

### 🧭 The Schema (AGENTS.md)

- "어떻게 쓸지"에 대한 규칙서
- 파일 이름 · 프론트매터 · 섹션 가이드 · 링크 규약
- LLM이 이 규칙을 매번 따르므로 결과가 일관됨

---

<!-- _class: section -->

# 02
## 재료 — Raw Sources

---

# 입력: `raw/` 13개 문서

기획자가 작성한 **사업 설계 산출물 13건** (총 약 40만 자).

| # | 파일 | 분류 |
|---|---|---|
| 00 | `00_PRD_v1.md` | 제품 요구사항 문서 |
| 05 | `05_SRS_v1.md` | 소프트웨어 요구사항 명세 |
| 06 | `06_value-proposition-sheet.md` | 가치 제안 시트 |
| 1 | `1_porters-foreces.md` | Porter's 5 Forces |
| 2 | `2_competents-analysis.md` | 경쟁사 분석 |
| 3 | `3_value-chain.md` | 가치사슬 분석 |
| 4 | `4_ksf-report.md` | 핵심 성공 요인 |
| 5 | `5_problem-definition.md` | 문제 정의 |
| 6 | `6_TAM-SAM-SOM+MarketSegment.md` | 시장 규모·세그먼트 |
| 7 | `7_persona-spectrum-map.md` | 페르소나 스펙트럼 |
| 8 | `8_customer-journey-map.md` | 고객 여정 맵 |
| 9 | `9_aos-dos-analysis.md` | 19개 Pain 우선순위 |
| 10 | `10_jtbd-interview-report.md` | JTBD 인터뷰 |

---

# 재료의 성격 — 의미 단위의 벽돌

- **제품 단:** PRD(비전·로드맵) + SRS(AC·NFR)
- **시장 단:** Porter + 경쟁사 + Value Chain + KSF
- **고객 단:** TAM/SAM/SOM + 페르소나 맵 + CJM + AOS-DOS + JTBD
- **메시지 단:** Value Proposition Sheet (6×4 매트릭스)

### 공통 특징

- 기획자가 **이미 ID 체계**로 정리 (C1~N1, CORE/ADJ/EXT, F1~F4, CJM-1~5…)
- 각 문서에 **교차 참조가 이미 있음** (PRD가 AOS-DOS를 인용하는 식)
- **그대로 LLM에게 먹이면** 맥락 유실 — 위키가 필요한 이유

---

<!-- _class: section -->

# 03
## 스키마 — AGENTS.md

---

# 스키마가 하는 일

`wiki/AGENTS.md` 는 LLM이 위키를 일관되게 쓰도록 하는 **운영 계약서**다.

### 7개 조항

1. **도메인 한 줄** — "무엇에 대한 위키인가"
2. **디렉터리 구조** — raw/ vs wiki/, 6개 카테고리
3. **페이지 작성 관례** — 파일명·프론트매터·본문 섹션
4. **링크·인용** — 상대 경로, 검증 수준 마커
5. **ID 컨벤션** — 원본 ID 그대로 전역 사용
6. **운영 워크플로** — ingest / query / lint
7. **인덱스·로그 규약** — 카탈로그 / append-only 로그

---

# 디렉터리 구조

```text
hff-hub-workbase/
├── llm-wiki.md            # 패턴 원본(EN)
├── llm-wiki.ko.md         # 패턴 원본(KO)
├── raw/                   # 🔒 원본(불변)
│   ├── 00_PRD_v1.md ... 10_jtbd-interview-report.md
│   └── assets/
└── wiki/                  # 📚 LLM이 만들고 유지
    ├── AGENTS.md          # 🧭 스키마
    ├── README.md          # 진입점
    ├── index.md           # 전체 페이지 카탈로그
    ├── log.md             # 시간순 로그
    ├── synthesis.md       # 한 페이지 종합
    ├── sources/           # 원본 1건 ↔ 요약 1장
    ├── entities/          # 제품·스택·세그먼트
    ├── personas/          # C1~N1 (6명)
    ├── features/          # F1~F4
    ├── competitors/       # 4개 카테고리
    └── concepts/          # 분석 프레임 14종
```

---

# 페이지 작성 관례 — 표준 프론트매터

모든 페이지는 동일한 YAML 헤더로 시작한다.

```yaml
---
title: <한국어 제목>
type: source | entity | persona | feature | competitor | concept | meta
status: draft | stable | stale
last_updated: YYYY-MM-DD
sources: [raw/<file>.md, ...]      # 근거 원본
related: [wiki/<path>.md, ...]     # 위키 내 교차 참조
tags: [#건기식, #MVP, ...]
---
```

### 효과

- **Lint 자동화 가능** — 누락 필드·오래된 날짜 즉시 검출
- **질의 시 필터링** — "status: stable 만 인용해"
- **고아 페이지 0건** — related 필수 → 모두 연결됨

---

# ID 컨벤션 — 원본 ID를 전역 사용

원본에서 이미 쓰던 ID를 위키 어디서든 똑같이 인용한다.

<div class="two-col">

### 도메인 ID

- 페르소나: `C1 C2 A2 E1 E2 N1`
- 세그먼트: `Q1 Q2 Q3 Q4` (+ `Q1-A` 등)
- Pain: `CORE-1..5 ADJ-1..3 EXT-1..4 NON-1..2 CJM-1..5`
- 기능: `F1 F2 F3 F4` (+ Should `F7..F12`)
- 리스크: `R1..R5`

### 수치 검증 마커

- ✅ 공개 조사 (논문·공식 통계)
- ⚠️ 추정 (내부 모델링)
- 🔴 미검증 (원본 주장만)

</div>

> 같은 기호가 어디서든 같은 의미 → LLM이 섞지 않음.

---

<!-- _class: section -->

# 04
## 결과물 — 49개 위키 페이지

---

# 한눈에 보기 — 생성된 49 페이지

| 카테고리 | 개수 | 역할 |
|---|---:|---|
| **메타** | 5 | README · AGENTS · synthesis · index · log |
| **엔티티** | 3 | 제품 · 기술 스택 · 세그먼트 |
| **페르소나** | 6 | C1 · C2 · A2 · E1 · E2 · N1 |
| **기능** | 4 | F1 · F2 · F3 · F4 |
| **경쟁사** | 4 | 직접 · 간접 · 대체재 · 잠재 |
| **컨셉/프레임** | 14 | Porter · VC · KSF · TAM · JTBD · AOS-DOS 등 |
| **소스 요약** | 13 | raw/ 1:1 매핑 |
| | **49** | |

### 변환 비율

원본 13 → 요약 13 + 재구성 23 + 메타 5 = **49 페이지**

---

# 엔티티 — 제품·기술·시장 (3)

<div class="two-col">

### `entities/product-HFF-Hub.md`
- HFF-Hub MVP의 단일 정의 페이지
- F1~F4·페르소나·KPI·로드맵 한 곳에
- 모든 경로의 교차점

### `entities/tech-stack.md`
- Next.js + Supabase + Vercel + Gemini
- 1인 운영 친화 선택의 근거
- 외부 API 카탈로그

</div>

### `entities/market-segments.md`

- 9개 세그먼트(Q1-A, Q1-B, Q2, Q3, Q4-A/B/C/D, NON)
- 인구·LTV·Phase별 우선순위
- `tam-sam-som.md` · `persona-spectrum.md` 와 삼각 링크

---

# 페르소나 — 6개의 엔진 (1/2)

| ID | 이름 | 동기 | 세그먼트 | Phase |
|---|---|---|---|---|
| **C1** | 한정훈 | 효율 최적화 | Q1-A | **1 (메인 매출)** |
| **C2** | 박소연 | 안전·책임감 | Q4-A | **2 (진입 트래픽)** |
| **A2** | 정수빈 | 자기실현·트렌드 | Q4-C | **2 (바이럴)** |
| E1 | 나경아 | 단순성·관계 | Q4-B | 3 (확장) |
| E2 | 김도현 | 정확성·검증 | Q1-B | 3 (데이터 신뢰) |
| N1 | 조미라 | 관성·소속 | Q3 | 4 (전환) |

각 페르소나 페이지 = **프로필 · Pain · Goal · 감정 곡선 · JTBD · AOS/DOS · 관련 기능 · 카피 톤** 8개 섹션 표준화.

---

# 페르소나 — 스펙트럼 맵 (2/2)

```text
인지 高 │  E2 (데이터 검증)         C1 (가성비 최적화)
        │  Q1-B 정확성               Q1-A 효율성 ★
        │
인지 중 │
        │
인지 低 │  N1 (브랜드 충성)         C2 (건강 계기) ★
        │  Q3 정서 안정              Q4-A 안전
        │  E1 (디지털 약자)         A2 (트렌드) ★
        │  Q4-B 가족 보호             Q4-C 자기실현
        └────────────────────────────────────────────
            구매 무경험              구매 유경험
```

★ = MVP 1~2단계 핵심 타깃. Q4→Q1 Flywheel의 입력·출력.

---

# 기능 — MVP F1~F4

| ID | 이름 | 1줄 | 핵심 Pain | KPI |
|---|---|---|---|---|
| **F1** | HFF-Hub Engine | 1일 단가 환산 | CORE-1, CORE-3 | TTC ≤ 5초 |
| **F2** | Anti-BS Dashboard | 광고 진위 검증 | CORE-2 | 거짓양성 ≤ 5% |
| **F3** | Viral Engine | 1-Tap 공유 카드 | CJM-3 | 공유율 ≥ 5% |
| **F4** | Data Trust System | 출처·산식·신고 | CORE-4, CORE-5 | 신고 SLA 24h |

### 각 기능 페이지 8개 섹션

한 줄 정의 · 해결 Pain · AC · NFR · 의존성 · 리스크 · 관련 페르소나 · 결론

> **F1~F4는 분리 출시 불가 패키지** — 세트의 가치 > 부분합.

---

# 경쟁사 — 4 카테고리

| 페이지 | 유형 | 핵심 차별 |
|---|---|---|
| `pillyze.md` | 직접 경쟁 (Recommender) | 추천 vs **검증** |
| `enuri.md` | 간접 (Aggregator) | 절대 가격 vs **1일 단가** |
| `pharmacist-youtubers.md` | 대체재 | 1인 의견 vs **데이터+검수** |
| `big-tech-channels.md` | 잠재 위협 | 자체 채널 vs **멀티+광고 분리** |

### 우리의 자리 = Market Refiner (정제자)

> "추천도 취합도 아닌 재정리"

---

# 컨셉 — 14개 분석 프레임 (1/2)

<div class="two-col">

### 시장·경쟁

- `problem-definition.md`
- `porters-five-forces.md`
- `value-chain.md`
- `ksf.md`
- `market-refiner-positioning.md`

### 고객·수요

- `tam-sam-som.md`
- `persona-spectrum.md`
- `customer-journey-map.md`
- `jtbd.md`
- `pain-catalog.md`

</div>

### 전략·운영

- `q4-q1-flywheel.md` · `aos-dos-framework.md` · `value-proposition.md` · `vibe-coding.md`

---

# 컨셉 — Top 5 인사이트 (2/2)

1. **19개 Pain의 74%가 Q1 블루오션 사분면에 몰려 있다** — 블루오션 ([`aos-dos-framework.md`])
2. **시장의 본질은 "정보 과잉 + 가치 실전"** — 추천이 아니라 정제가 답 ([`problem-definition.md`])
3. **Q4 진입 → Q1 정착 → 신뢰 자산 복리** 플라이휠이 CAC를 시간의 함수로 떨어뜨림 ([`q4-q1-flywheel.md`])
4. **4대 KSF 모두 한 문장으로 환원** — "신뢰는 ① 정제 + ② 인간 검수 + ③ 신고 루프의 3중 구조" ([`ksf.md`])
5. **모든 JTBD의 결론절이 정서 단어로 끝남** — "죄책감 없이 / 부담 없이 / 자신감 있게". 우리가 파는 건 정보가 아니라 **해방** ([`jtbd.md`])

---

# 소스 요약 — raw/ 1:1 매핑 (13)

각 원본 1건은 wiki/sources/ 의 요약 1장과 **항상 짝을 이룬다.**

| raw | → | wiki/sources | 링크된 위키 페이지 |
|---|---|---|---|
| `00_PRD_v1.md` | → | `00-prd-v1.md` | 6개 페이지 |
| `05_SRS_v1.md` | → | `05-srs-v1.md` | 5개 페이지 |
| `06_value-proposition-sheet.md` | → | `06-vps.md` | 10개 페이지 |
| `1_porters-foreces.md` | → | `01-porters.md` | 4개 페이지 |
| … (총 13건) | | | |

### 소스 페이지 5개 섹션 표준

한 줄 요약 · 핵심 포인트 · **위키에 미친 영향** · 인용용 발췌 · 출처

> "원본을 통째로 복사하지 않고 요약 + 재구성 + 교차 참조"

---

# 메타 — 위키의 내비게이션 (5)

| 페이지 | 역할 |
|---|---|
| `README.md` | 위키 진입점 · 프로젝트 1분 요약 |
| `AGENTS.md` | 스키마/운영 규칙 (LLM이 따르는 계약) |
| `synthesis.md` | **한 페이지 의사결정 종합** — 신규 진입자용 |
| `index.md` | 전체 49 페이지 카탈로그 (상태·갱신일 테이블) |
| `log.md` | 시간순 append-only 로그 (ingest/query/lint/decision) |

### 읽는 순서 권장

```text
README.md → synthesis.md → index.md → (관심 카테고리 딥다이브) → AGENTS.md
```

---

<!-- _class: section -->

# 05
## 운영 — ingest / query / lint

---

# 운영 워크플로 — 3 동사

### 📥 Ingest — 새 원본을 위키에 편입

1. `raw/` 에 파일 추가
2. LLM에게 `"ingest <파일명>"`
3. LLM이 요약 → 영향받는 페이지 갱신 → index/log 갱신

### ❓ Query — 위키에 질문

1. LLM이 `index.md` → 카테고리 → 후보 페이지 순으로 좁힘
2. 답 합성 + **위키 내부 경로로 인용**
3. 새 통찰은 `concepts/` 또는 `entities/`에 **환원**

### 🩺 Lint — 건강 검사

- 페이지 간 수치 모순 · 고아 페이지 · 검증 마커 누락 · 오래된 `stale` 주장

---

# 금기 — 위키가 되지 않게 막는 것

- **원본 통째로 복사 금지** — 요약·재구성·교차 참조만
- **마케팅 표현 금지** — 위키는 내부 의사결정용
- **건기식법 금지 표현 금지** — 치료/예방 단어 본문에 쓰지 않음
- **추정 수치 검증 마커 누락 금지** — ✅/⚠️/🔴 필수
- **고아 페이지 금지** — `index.md` + 최소 1곳에 링크
- **LLM이 원본을 덮어쓰기 금지** — `raw/` 는 Read-Only

> 이 금기 목록 자체가 위키 Lint의 자동 검사 항목이 된다.

---

<!-- _class: section -->

# 06
## 종합 — 무엇이 남았나

---

# 위키가 실제로 달성한 것

### Before (원본만 있음)

- 13개 산출물을 LLM이 매번 전부 읽어야 함
- 같은 질문에 매번 다른 답 가능성
- "페르소나 C2가 F2를 쓸 때 CJM-3에서" 같은 교차 질의 불가

### After (위키 + 스키마)

- LLM은 `index.md` → 관련 2~3 페이지만 읽으면 됨 (**토큰 20% 이하**)
- 질문·답변이 위키에 적재되어 시간이 갈수록 **정확도 상승**
- `C1 × F1 × CJM-2` 같은 **3차원 질의 즉시** 가능
- Lint·자동 갱신으로 **일관성 자가 유지**

---

# 숫자로 본 위키

<div class="two-col">

### 입력

- **13** raw 파일
- **~40만 자** 원본
- **6** 개 ID 체계
- **19** 개 Pain Point

### 출력

- **49** wiki 페이지
- **6** 개 카테고리
- **~25,000 자** 재구성
- **0** 개 고아 페이지

</div>

### 평균 페이지

- 길이: 약 100~150줄 (LLM이 1번에 읽기 좋은 크기)
- 링크: 페이지당 평균 6개 교차 참조
- 프론트매터: 100% 표준 준수

---

# 다음 단계 — 살아있는 위키로

### 단기 (이번 주)

- [ ] 첫 `query` 실행 — "F1 TTC 5초를 깨는 첫 병목은?"
- [ ] 첫 `lint` 실행 — 검증 수준 마커 누락, 링크 깨짐 검사

### 중기 (이번 달)

- [ ] `concepts/ttc-north-star.md` — TTC 메트릭 정밀 정의
- [ ] `concepts/ingredient-normalization.md` — 성분 정규화 알고리즘
- [ ] 사용자 인터뷰 2~3건 ingest

### 장기 (분기)

- [ ] 월간 Data Trust Report 자동 생성 파이프라인
- [ ] 위키 그래프 시각화 (Obsidian Graph View 활용)

---

<!-- _class: lead -->

# 한 줄 결론

## "위키는 기억의 적금 통장이다"

<br>

**재료** 13건 → **스키마** 1장 → **결과** 49 페이지 →
**앞으로** 매 ingest 마다 이자처럼 누적

<br>

> 이 프레젠테이션 자체가 위키의 1번째 query 결과입니다.

---

<!-- _class: section -->

## 부록

Marp로 이 슬라이드 렌더링하기:

```bash
# CLI
marp slides/llm-wiki-overview.md -o slides/llm-wiki-overview.html
marp slides/llm-wiki-overview.md --pdf

# Obsidian
# Obsidian Marp Slides 플러그인 설치 후
# 본 파일을 열고 "Start Presentation"
```

참고: [Obsidian Marp Slides](https://samuele-cozzi.github.io/obsidian-marp-slides/)
