---
title: 고객 여정 맵 (CJM) — 5단계 표준 모델
type: concept
status: stable
last_updated: 2026-04-20
sources: [raw/8_customer-journey-map.md, raw/00_PRD_v1.md]
related: [wiki/concepts/pain-catalog.md, wiki/personas/, wiki/features/]
tags: [#CJM, #여정]
---

## 정의

본 프로젝트가 다루는 표준 5단계 구매 여정. 각 단계마다 페르소나별 Pain·Gain·감정·기회가 다르게 발생한다.

```
① 인지(Awareness) → ② 탐색·평가(Consideration) → ③ 결정(Decision) → ④ 구매·복용(Purchase/Usage) → ⑤ 재구매·확장(Retention)
```

## 단계별 핵심

### ① 인지 (Awareness)

- **트리거:** 건강 신호(피로, 검진 결과), 광고/콘텐츠, 가족·지인 추천
- **감정:** 막연한 불안 ↑, 정보 욕구 ↑
- **기회 기능:** F2 Anti-BS Dashboard (광고 진위 즉시 검증)
- **CJM ID:** CJM-1

### ② 탐색·평가 (Consideration) — **여정의 가장 깊은 골짜기**

- **활동:** 30~60분 검색, 가격 비교, 후기 검색, 성분 검색
- **Pain (집중):** CORE-1 단가 비교 어려움, CORE-2 광고 노이즈, CORE-3 성분 해석 불가, CORE-4 결정 기준 부재
- **이탈률:** 약 55~75% (⚠️ 추정)
- **감정:** 좌절 → 회의 → 의심
- **기회 기능:** F1 HFF-Hub Engine (가장 큰 가치 전달 지점), F2 Anti-BS Dashboard
- **CJM ID:** CJM-2, CJM-3

### ③ 결정 (Decision)

- **활동:** 장바구니 → 결제
- **Pain:** "정말 이게 맞나?" 마지막 회의 (확신 부재)
- **감정:** 안도와 불안 공존
- **기회 기능:** F4 Data Trust System (식약처 데이터 출처 명시), F3 Viral Engine (지인 검증)
- **CJM ID:** CJM-4

### ④ 구매·복용 (Purchase / Usage)

- **활동:** 도착, 복용 시작, 효과 체감 시도
- **Pain:** EXT-1 효능 불확실, EXT-2 복용 누락, EXT-3 부작용/상호작용 우려
- **감정:** 기대 → 의구심
- **기회 기능:** (Should) F7 복용 알람, F8 효능 후기 매칭

### ⑤ 재구매·확장 (Retention)

- **활동:** 같은 제품 재구매 / 다른 성분 추가 / 가족용 확장
- **Pain:** "이걸 계속 먹는 게 맞나?" 재의심
- **감정:** 관성 vs 회의
- **기회 기능:** F4 Data Trust (변경 사항 알림), F1 (가격 변동 알림)
- **CJM ID:** CJM-5

## 본 프로젝트에서 의미

- **MVP는 ② 탐색·평가 단계에 100% 베팅한다.** 이 단계 이탈률을 절반으로 줄이는 것이 사업 가치의 70% 이상.
- ④·⑤ 단계는 Phase 3+ 기능(복용 알람, 약사 큐레이션 라이브)으로 확장.
- ③ 결정 단계는 F4 Data Trust가 "마지막 0.1초의 확신"을 만든다 → MVP에서 절대 빠질 수 없음.

## CJM × 페르소나 교차

| 단계 | 가장 고통받는 페르소나 |
|---|---|
| ① 인지 | E1 (디지털 약자), C2 (건강 계기 진입) |
| ② 탐색 | C1, C2, A2, E2 — **거의 전부** |
| ③ 결정 | C2, E1, N1 |
| ④ 복용 | C2, A2 |
| ⑤ 재구매 | C1, N1 |

## 결론·시사점

- 페르소나는 6명이지만 **여정의 ②~③을 못 견디는 4명(C1·C2·A2·E2)**이 MVP의 절대 핵심.
- F1·F2·F4는 모두 ②~③ 단계의 다른 면을 담당하는 **세트 기능**이다(분리 불가).
- 자세한 Pain ID 매핑은 [`pain-catalog.md`](pain-catalog.md).
