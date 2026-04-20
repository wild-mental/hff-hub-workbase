---
title: AOS-DOS 분석 — 19개 Pain의 우선순위 사분면
type: concept
status: stable
last_updated: 2026-04-20
sources: [raw/9_aos-dos-analysis.md, raw/00_PRD_v1.md]
related: [wiki/concepts/pain-catalog.md, wiki/features/, wiki/concepts/jtbd.md]
tags: [#AOSDOS, #우선순위, #기회분석]
---

## 정의

- **AOS (Adjusted Opportunity Score):** Pain의 **시급성(Importance) × 미해결도(Underserved)** 기반 우선순위 점수.
- **DOS (Discovered Opportunity Score):** AOS 결과를 **2×2 사분면(시급성 × 미해결도)** 으로 시각화한 매트릭스.

목적: 19개 Pain Point 중 **MVP에서 무엇을 풀고 무엇을 미룰지 데이터로 결정**하기 위함.

## 핵심 발견 (시장 기회)

- 19개 Pain 중 **14개(74%)가 Q1 사분면(시급성 高 / 미해결 高)에 집중**.
- 즉 본 시장은 **"풀어야 할 문제가 명확히 알려져 있고, 누구도 풀고 있지 않은" 명백한 블루오션**.
- 가장 점수가 높은 Top 5 Pain이 [`features/`](../features/) F1~F4에 1:1 매핑된다.

## 4사분면 사분면 정의

```
시급성   高 │  Q1 (혁신 기회)              Q2 (방어 기회)
            │  →★ MVP 핵심 ★              → 차별화 포인트
            │  14건 (74%)                   2건 (10%)
            │
시급성   저 │  Q3 (관망)                   Q4 (제외)
            │  → 모니터링                  → 후순위
            │  2건 (10%)                    1건 (6%)
            └─────────────────────────────────
              미해결 高                      미해결 저
```

## 본 프로젝트에서 의미

### Top 5 Pain → MVP 기능 매핑

| 순위 | Pain ID | 한 줄 | AOS | 매핑 기능 |
|---|---|---|---|---|
| 1 | CORE-1 | 채널 간 단가 비교 노가다 | 9.2 | **F1** HFF-Hub Engine |
| 2 | CORE-2 | 광고/뒷광고 신뢰 붕괴 | 9.0 | **F2** Anti-BS Dashboard |
| 3 | CORE-3 | 성분 해석 불가 | 8.7 | F1 + F2 (성분 사전) |
| 4 | CORE-4 | 결정 기준 부재 | 8.5 | **F4** Data Trust |
| 5 | CJM-3 | 비교 결과 공유·설득 | 8.1 | **F3** Viral Engine |

(전체 19개 Pain은 [`pain-catalog.md`](pain-catalog.md) 참조.)

### Q2 차별화 포인트(2건)

- "약사·전문가 큐레이션" — 미해결도는 낮으나 시급성은 高 → 후속 차별화 포인트.
- "복용 알람·복용량 자동 계산" — Phase 3 후보.

### Q3·Q4 (관망/후순위)

- 후기 진정성, 가족 공유 기능 — Should/Could 기능군(F7~F12)으로 라우팅.

## 결론·시사점

- **MVP의 Pain Coverage = 14/14 (Q1 100%) + 1/2 (Q2 50%)** 가 목표.
- F1~F4가 동시에 출시되어야 하는 이유는 AOS Top 5가 모두 **상호 의존적**이기 때문 (예: F1만 있고 F2 없으면 "이 비교 결과를 왜 믿어?" 라는 메타 Pain 발생).
- 자세한 점수 산정 방식과 19개 항목 전체 표는 raw/9 §3~5 참조.
