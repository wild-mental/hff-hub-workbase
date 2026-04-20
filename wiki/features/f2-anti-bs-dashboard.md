---
title: F2 — Anti-BS Dashboard (마케팅 노이즈 필터·팩트체크)
type: feature
status: stable
last_updated: 2026-04-20
sources: [raw/00_PRD_v1.md, raw/05_SRS_v1.md, raw/9_aos-dos-analysis.md]
related: [wiki/personas/c2-park-soyeon.md, wiki/personas/a2-jung-subin.md, wiki/concepts/pain-catalog.md, wiki/concepts/value-proposition.md]
tags: [#feature, #F2, #MVP-MUST]
---

## 한 줄 정의

**광고 카피·인플루언서 영상·홈쇼핑 멘트를 입력받아 식약처 표시 기준 위반 가능성과 의학 팩트와의 일치도를 1초 안에 표시하는 검증 대시보드.**

## 해결 Pain

| Pain ID | 페르소나 | 동작 |
|---|---|---|
| **CORE-2** | C2, A2, N1 | 광고/뒷광고 신뢰 붕괴 → 즉시 검증 |
| **CORE-3** | C2, E1 | 마케팅 용어 → 식약처 표준 표현 환언 |
| **ADJ-1** | A2 | 트렌드 진위 즉시 검증 |
| **CJM-1** | C2, E1 | 인지 단계의 막연한 불안 → 1차 안심 |

## 핵심 AC

| ID | 기준 |
|---|---|
| F2-AC-1 | 입력: 텍스트 카피 / 이미지(OCR) / 짧은 영상(자막 추출) |
| F2-AC-2 | 출력: ✅ 인용 가능 / ⚠️ 위반 가능성 / 🔴 명백한 위반 + 근거 1줄 |
| F2-AC-3 | 응답 ≤ 3초 (P95) |
| F2-AC-4 | 식약처 「건강기능식품 표시·광고 사전심의 가이드」와 1:1 매핑 |
| F2-AC-5 | 같은 카피에 대해 반복 검증 시 동일 결과 (캐싱) |
| F2-AC-6 | 사용자 신고 → F4 Data Trust로 자동 라우팅 |
| F2-AC-7 | 결과는 그대로 1-Tap 공유 가능 (F3 연계) |

## NFR / 임계치

| 항목 | 임계치 |
|---|---|
| 검증 응답 시간 | ≤ 3초 (P95) |
| 정확도 | ≥ 90% (식약처 가이드 100문항 검수 표본) |
| 거짓양성률 | ≤ 5% |
| 처리 모달리티 | 텍스트 / 이미지(OCR) — 영상은 Phase 2 |
| LLM 비용 | ≤ 50원/검증 1건 (Gemini Flash) |

## 외부·내부 의존성

### 외부

- **식약처 표시·광고 가이드 (PDF/HTML)** — RAG 인덱싱
- **건강기능식품 부작용 사례 DB** (식약처 공개)
- **Gemini Flash (LLM)** — 카피 분류, 위반 가능성 판단
- **Google Cloud Vision API / Gemini Vision** — OCR
- **국내외 의학 논문 메타데이터** (PubMed Open Access) — Phase 2

### 내부

- **F4 Data Trust System** — 검증 근거 공개, 신고 라우팅
- **F1 HFF-Hub Engine** — 동일 제품의 단가와 동시 노출
- **F3 Viral Engine** — 검증 결과를 공유 카드에 그대로 사용

## 리스크

| ID | 리스크 | 완화 |
|---|---|---|
| R2 | 잘못된 위반 판정 → 광고주 분쟁 | 결정적 단어("치료/예방")만 자동 판정, 회색 영역은 ⚠️ 처리 |
| R5 | LLM 환각 (없는 식약처 조항 인용) | RAG로만 답변, 인용문 원문 보존 + 출처 URL 필수 |
| R3 | 식약처 가이드 개정 시 반영 지연 | 분기 1회 업데이트 + RSS/뉴스 모니터링 |

## 관련 페르소나

- **★★★ C2 박소연** — 메인 사용자 (광고 검증 = 첫 인상)
- **★★ A2 정수빈** — 트렌드 검증 + 공유
- **★★ N1 조미라** — 전환 트리거 (광고 논란 발생 시)
- **★ C1 한정훈** — 단가 비교 시 신뢰 보강

자세한 매핑은 [`../personas/`](../personas/).

## 결론·시사점

- F2는 본 사업의 **신뢰 자산을 만드는 가장 중요한 기능**. F1이 도구라면 F2는 자세(Posture).
- F2 결과 화면 = 우리가 광고주가 아니라 사용자 편이라는 시각적 증거. 이 시각화 품질이 [`../concepts/value-proposition.md`](../concepts/value-proposition.md)의 핵심 메시지를 만든다.
- 거짓양성(잘못된 위반 판정)은 거짓음성보다 위험 → 임계치를 보수적으로.
