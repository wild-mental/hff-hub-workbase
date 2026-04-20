---
title: 제품 — HFF-Hub (코드명)
type: entity
status: stable
last_updated: 2026-04-20
sources: [raw/00_PRD_v1.md, raw/05_SRS_v1.md, raw/06_value-proposition-sheet_260410(fin).md]
related: [wiki/features/, wiki/personas/, wiki/concepts/value-proposition.md, wiki/entities/tech-stack.md]
tags: [#product, #MVP]
---

## 한 줄 요약

**HFF-Hub** = 국내 건강기능식품 성분·가격 비교 모바일 웹 플랫폼. 1일 복용량 기준 단가 환산 + 광고 진위 팩트체크 + 1-Tap 공유 + 데이터 신뢰 시스템을 결합한 MVP.

(*"HFF-Hub"는 코드명. 정식 브랜드명은 별도 결정 예정.*)

## 핵심 기능 (MVP F1~F4)

| ID | 이름 | 한 줄 |
|---|---|---|
| **F1** | HFF-Hub Engine | 1일 단가 환산 |
| **F2** | Anti-BS Dashboard | 광고 진위 검증 |
| **F3** | Viral Engine | 1-Tap 공유 카드 |
| **F4** | Data Trust System | 출처/산식/신고 루프 |

자세한 내용은 [`../features/`](../features/).

## 타깃 페르소나 (Phase 1~2)

- C1 한정훈 (가성비 최적화)
- C2 박소연 (건강 계기)
- A2 정수빈 (트렌드)

자세한 내용은 [`../personas/`](../personas/).

## 가치 제안 한 줄

> "수동 엑셀 비교와 뒷광고 필터링에 지친 건기식 소비자에게,
> 1초 만의 1일 단가 환산과 의학 팩트체크를 제공하는 단 하나의 신뢰 가능한 대리인."

자세한 내용은 [`../concepts/value-proposition.md`](../concepts/value-proposition.md).

## 형태

| 항목 | 값 |
|---|---|
| 플랫폼 | 모바일 웹 (PWA) |
| 백엔드 | Next.js Route Handlers (App Router) |
| DB | Supabase (PostgreSQL) + Vector |
| 호스팅 | Vercel |
| AI | Vercel AI SDK + Google Gemini |
| 인증 | Supabase Auth (이메일·카카오 OAuth) |
| 결제 | Phase 2 — 토스페이먼츠 (구독형) |

자세한 내용은 [`tech-stack.md`](tech-stack.md).

## 핵심 KPI (North Star)

- **TTC (Time to Calculation)** ≤ 5초 (P95)
- 30일 리텐션 ≥ 35% (Phase 2 목표)
- 1-Tap 공유율 ≥ 5%
- F4 신고 응답 SLA 24h

## 로드맵 요약

| Phase | 기간 | 핵심 |
|---|---|---|
| 0 | -2~0주 | 본 위키, PRD/SRS 정제 |
| 1 | 0~6개월 | F1~F4 MVP, C1 메인 |
| 2 | 6~12개월 | C2·A2 확장, F7 복용 알람 |
| 3 | 12~24개월 | E1·E2, 음성 UI, 약사 라이브 |
| 4 | 24~36개월 | N1, B2B 라이선싱 |

## 결론·시사점

- 본 제품은 "또 하나의 영양제 추천 앱"이 아니라 [`../concepts/market-refiner-positioning.md`](../concepts/market-refiner-positioning.md)에 정의된 **정제자(Refiner) 자리**를 차지한다.
- F1~F4는 분리 출시 불가능한 패키지 — 개별 기능의 가치가 아니라 **세트의 가치**.
- 본 제품의 진짜 자산은 코드가 아니라 **시간이 누적된 데이터 신뢰** ([`f4-data-trust.md`](../features/f4-data-trust.md)).
