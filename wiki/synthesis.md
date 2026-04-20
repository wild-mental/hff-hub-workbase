---
title: 종합 (Synthesis) — 한 페이지 의사결정 요약
type: meta
status: stable
last_updated: 2026-04-20
sources: [raw/00_PRD_v1.md, raw/9_aos-dos-analysis.md, raw/6_TAM-SAM-SOM+MarketSegment.md, raw/4_ksf-report.md]
related: [wiki/index.md, wiki/AGENTS.md, wiki/entities/product-HFF-Hub.md, wiki/concepts/, wiki/features/, wiki/personas/]
tags: [#meta, #synthesis]
---

# HFF-Hub (Health Functional Food Hub) 한 페이지 종합

본 문서는 13개 raw 소스 + 본 위키 30+ 페이지를 1장으로 압축한 의사결정 요약. 새 사람·새 LLM·새 의사결정자가 들어올 때 가장 먼저 읽는 페이지.

## 1줄 비전

> **"비교 노가다와 죄책감으로부터의 해방."**

## 한 문단 정의

국내 건강기능식품 시장은 정보 과잉·가치 실전 상태. 6조 시장(TAM)에 누적된 19개 Pain Point의 74%가 누구도 풀고 있지 않은 명백한 블루오션. 우리는 추천(Recommender)도 취합(Aggregator)도 아닌 **정제자(Refiner)** 자리에 들어가, 1일 복용량 기준 단가 환산(F1) + 광고 진위 검증(F2) + 1-Tap 공유(F3) + 데이터 신뢰 시스템(F4)의 4종 패키지를 1인 + LLM 운영으로 6~12주 안에 출시한다.

## 시장

| 지표 | 값 | 검증 |
|---|---|---|
| TAM | 6.4조 원 | ✅ |
| SAM | 4.6조 원 | ✅ |
| SOM (5년, 1.0%) | 460억 원 | ⚠️ |
| 5년 MAU 목표 | 95만 | ⚠️ |
| 5년 ARPU 목표 | 14,500원 | ⚠️ |

자세한 내용은 [`concepts/tam-sam-som.md`](concepts/tam-sam-som.md).

## 페르소나 (우선순위)

| Phase | 페르소나 | 동기 | 핵심 기능 |
|---|---|---|---|
| **1 (0~6m)** | **C1** 한정훈 | 효율 | F1 |
| **2 (6~12m)** | **C2** 박소연 + **A2** 정수빈 | 안전 + 자기실현 | F2·F3 |
| 3 (12~24m) | E1 나경아 + E2 김도현 | 단순 + 정확 | F1·F4 |
| 4 (24~36m) | N1 조미라 | 관성 합리화 | F1·F2 |

자세한 내용은 [`personas/`](personas/) · [`concepts/persona-spectrum.md`](concepts/persona-spectrum.md).

## 기능 (MVP F1~F4)

| ID | 한 줄 | 핵심 Pain | 핵심 KPI |
|---|---|---|---|
| **F1** HFF-Hub Engine | 1일 단가 환산 | CORE-1·3 | TTC ≤ 5초 |
| **F2** Anti-BS Dashboard | 광고 진위 검증 | CORE-2 | 거짓양성 ≤ 5% |
| **F3** Viral Engine | 1-Tap 공유 카드 | CJM-3 | 공유율 ≥ 5% |
| **F4** Data Trust System | 출처·산식·신고 | CORE-4·5 | 신고 SLA 24h |

자세한 내용은 [`features/`](features/).

## 경쟁 구도

| 카테고리 | 그들의 동작 | 우리의 차별 |
|---|---|---|
| 필라이즈 | 추천 | 검증 |
| 에누리/다나와 | 절대 가격 | 1일 단가 |
| 약사 유튜버 | 1인 의견 | 데이터 + 검수 |
| 빅테크 채널 | 자체 채널 비교 | 멀티 채널 + 광고 분리 |

자세한 내용은 [`competitors/`](competitors/) · [`concepts/market-refiner-positioning.md`](concepts/market-refiner-positioning.md).

## 4대 KSF (모방 방어선)

1. **데이터 신뢰성** — F4가 시간 누적 자산으로 키움
2. **UX 명료성** — MVP 0~3개월에 결정
3. **광고/제휴-신뢰 균형** — 알고리즘 룰로 분리
4. **약사·전문가 큐레이션** — Phase 2+ 인적 자산 영입

자세한 내용은 [`concepts/ksf.md`](concepts/ksf.md).

## 성장 모델 (Q4→Q1 Flywheel)

```
Q4 진입 (낮은 CAC) ──> Q1 정착 (높은 LTV)
   ↑                       │
   │                       ▼
   └── 신뢰 자산 (F4) ─────┘
```

자세한 내용은 [`concepts/q4-q1-flywheel.md`](concepts/q4-q1-flywheel.md).

## 기술 (1인 운영 친화)

Next.js (App Router) + Prisma + Supabase + Vercel + Gemini Flash.
1인 + LLM 페어 = [`concepts/vibe-coding.md`](concepts/vibe-coding.md).

자세한 내용은 [`entities/tech-stack.md`](entities/tech-stack.md).

## 리스크 Top 5

| ID | 리스크 | 1차 완화 |
|---|---|---|
| R1 | 채널 API 정책 변경 | 다채널 분산 |
| R2 | LLM 환각 / 환산 오류 | 룰 1차 + LLM 2차 + 사람 샘플 검수 |
| R3 | 식약처 규제 변화 | 분기 가이드 갱신, 보수적 임계 |
| R4 | 신고 폭주 / 1인 한계 | 자동 분류 + 약사 자문단(Phase 2) |
| R5 | 빅테크 직접 진입 | KSF-1·4 시간 누적 자산화 |

## 첫 6주 로드맵

| 주차 | 목표 |
|---|---|
| W1 | 데이터 모델 + 식약처 OPEN-API 인덱싱 |
| W2 | F1 v0.1 (단일 채널, 단일 성분) |
| W3 | F2 v0.1 (텍스트 카피 위반 감지) |
| W4 | F4 v0.1 (출처·산식·신고 폼) |
| W5 | F3 v0.1 (단일 비율 카드) + 인증·결제(추후) |
| W6 | 통합 + Vercel 배포 + 알파 사용자 10명 |

## 마지막으로

> 본 사업의 진짜 자산은 코드도 아니고 디자인도 아니다. **시간이 누적된 데이터 신뢰**다. 본 위키 자체가 그 신뢰의 첫 적금 통장이다.

다음 단계는 [`AGENTS.md`](AGENTS.md)의 운영 워크플로(ingest / query / lint)에 따라 라이브 운영.
