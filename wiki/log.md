---
title: 위키 활동 로그
type: meta
status: stable
last_updated: 2026-04-20
sources: []
related: [wiki/AGENTS.md, wiki/index.md]
tags: [#meta, #log]
---

# 활동 로그

본 위키의 시간순 활동 기록. AGENTS.md §5 형식.

> 형식: `## [YYYY-MM-DD] <op> | <한 줄 요약>`
> op ∈ {ingest, query, lint, decision, refactor}

---

## [2026-04-20] decision | 위키 패턴 채택 + 디렉터리 트리 확정

- llm-wiki.md / llm-wiki.ko.md 패턴을 본 프로젝트에 채택.
- 디렉터리 트리 확정: `raw/`(불변) + `wiki/{personas,features,competitors,concepts,entities,sources}`.

## [2026-04-20] ingest | 13개 raw 소스 일괄 적재

- 처리 원본:
  - `raw/00_PRD_v1.md` → [`sources/00-prd-v1.md`](sources/00-prd-v1.md)
  - `raw/05_SRS_v1.md` → [`sources/05-srs-v1.md`](sources/05-srs-v1.md)
  - `raw/06_value-proposition-sheet_260410(fin).md` → [`sources/06-value-proposition-sheet.md`](sources/06-value-proposition-sheet.md)
  - `raw/1_porters-foreces.md` → [`sources/01-porters-five-forces.md`](sources/01-porters-five-forces.md)
  - `raw/2_competents-analysis.md` → [`sources/02-competitors-analysis.md`](sources/02-competitors-analysis.md)
  - `raw/3_value-chain.md` → [`sources/03-value-chain.md`](sources/03-value-chain.md)
  - `raw/4_ksf-report.md` → [`sources/04-ksf-report.md`](sources/04-ksf-report.md)
  - `raw/5_problem-definition.md` → [`sources/05-problem-definition.md`](sources/05-problem-definition.md)
  - `raw/6_TAM-SAM-SOM+MarketSegment.md` → [`sources/06-tam-sam-som.md`](sources/06-tam-sam-som.md)
  - `raw/7_persona-spectrum-map.md` → [`sources/07-persona-spectrum.md`](sources/07-persona-spectrum.md)
  - `raw/8_customer-journey-map.md` → [`sources/08-customer-journey-map.md`](sources/08-customer-journey-map.md)
  - `raw/9_aos-dos-analysis.md` → [`sources/09-aos-dos-analysis.md`](sources/09-aos-dos-analysis.md)
  - `raw/10_jtbd-interview-report.md` → [`sources/10-jtbd-interview-report.md`](sources/10-jtbd-interview-report.md)
- 신규 생성 페이지 합계: 49건
  - 메타 5 / 엔티티 3 / 페르소나 6 / 기능 4 / 경쟁사 4 / 컨셉 14 / 소스 13
- 핵심 결과: 4개 MVP 기능(F1~F4)·6명 페르소나(C1~N1)·19개 Pain·4대 KSF·9개 세그먼트가 모두 ID 단위로 위키 전역에 교차 참조 가능.

## [2026-04-20] decision | 운영 스키마 AGENTS.md 확정

- 페이지 작성 규약: kebab-case 파일명, YAML 프론트매터(필수 필드 7종), 본문 섹션 가이드 5종(source/persona/feature/concept/competitor).
- ID 컨벤션: 페르소나 C1~N1, Pain CORE/ADJ/EXT/NON/CJM, 기능 F1~F4, 리스크 R1~R5 — 원본의 ID를 위키 전역에서 그대로 사용.
- 워크플로 3종: ingest / query / lint.
- 검증 수준 마커 의무화: ✅ 공개 조사 / ⚠️ 추정 / 🔴 미검증.

## [2026-04-20] decision | North Star = TTC, MVP = F1+F2+F3+F4 동시 출시

- 분리 출시 시 [`concepts/aos-dos-framework.md`](concepts/aos-dos-framework.md) Top 5 Pain 중 일부만 풀려 [`concepts/value-proposition.md`](concepts/value-proposition.md)가 깨짐 → 동시 출시 결정.
- 첫 6주 로드맵은 [`synthesis.md`](synthesis.md) 참조.

## [2026-04-20] query | 위키 구성 내용 종합 슬라이드 제작

- 질문: "재료(raw 13건)와 결과물(위키 49 페이지)을 종합 소개하는 슬라이드를 만들어줘."
- 결과: `slides/llm-wiki-overview.md` 생성 — Obsidian Marp Slides 문법 기반 25장 프레젠테이션.
- 구성: Why(1) → Raw Materials(2) → Schema(3) → Results(4) → Workflow(5) → Synthesis(6) + 부록.
- 참고 패턴: https://samuele-cozzi.github.io/obsidian-marp-slides/
- 환원: 본 위키 설명 자체가 자기 참조 콘텐츠가 되어 신규 진입자 온보딩에 활용 가능.

---

## 다음 단계 (다음 ingest/query/lint 후보)

- **ingest 후보:** 새 사용자 인터뷰 결과, 식약처 가이드 개정, 경쟁사 신기능 출시 시.
- **query 후보:** "F1 TTC 5초를 깨는 첫 번째 병목은?", "C1과 C2가 동시에 만족하는 첫 화면은?".
- **lint 후보:** 모든 페이지의 검증 수준 마커 누락 검사, 고아 페이지 검사, 산식·출처 링크 깨짐 검사.
