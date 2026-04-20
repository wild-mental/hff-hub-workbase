---
title: C1 — 한정훈, 가성비 최적화자 (Q1-A)
type: persona
status: stable
last_updated: 2026-04-20
sources: [raw/7_persona-spectrum-map.md, raw/06_value-proposition-sheet_260410(fin).md, raw/10_jtbd-interview-report.md]
related: [wiki/concepts/persona-spectrum.md, wiki/features/f1-HFF-Hub-engine.md, wiki/features/f4-data-trust.md, wiki/concepts/jtbd.md]
tags: [#persona, #C1, #Q1, #핵심타깃]
---

## 한 줄 요약

**가치 최적화 엔진** — "내 시간과 돈을 가장 효율적으로 쓰는 결정"을 끈질기게 추구하는 30~40대 직장인. **MVP 매출의 핵심.**

## 프로필

| 항목 | 값 |
|---|---|
| 나이 | 30대 후반 ~ 40대 초반 |
| 직업 | 사무직 직장인 (IT/제조/금융 등) |
| 가구 | 1~2인 가구, 맞벌이 가능 |
| 소득 | 중상위 (가처분 충분) |
| 디지털 친숙도 | 매우 높음 (엑셀·앱 자유) |
| 세그먼트 | Q1-A (인지 高 / 경험 有, 효율 동기) |
| 1인 LTV (추정) | 약 41.8만 원 |

## 핵심 Pain

| ID | Pain |
|---|---|
| **CORE-1** | 채널 간 단가 비교 노가다 (직접 엑셀로 환산) |
| **CORE-5** | 비교 앱 자체를 못 믿어 직접 검증 |
| **ADJ-3** | 비교 결과를 동료/지인에게 공유할 때의 자료 정리 부담 |
| **CJM-5** | 재구매 시 가격 변동 추적 부담 |

## Goal

> "30분 비교 노가다 없이, 1초 안에 1일 단가와 신뢰도까지 같이 보고 싶다."

## 감정 곡선 (CJM 기준)

```
  ① 인지 ──── ② 탐색 ─★── ③ 결정 ── ④ 복용 ──★ ⑤ 재구매
  중립        급격한 좌절   안도       관성       만족(반복)
              ★ 진입 지점                ★ 가격 변동 시 재의심
```

★ = 우리가 가장 큰 가치를 전달할 지점

## JTBD Job Story

> When 새로운 영양제를 사야 하거나 기존 제품의 가격이 올랐을 때,
> I want 동일 성분 기준 1일 단가를 채널 간 자동 비교받고,
> so I can 30분 이상의 비교 노가다 없이 가장 효율적인 선택을 할 수 있다.

## AOS / DOS

- 점유 사분면: **Q1 (혁신 기회)** — Pain 4개 모두 시급성 高 / 미해결 高.
- AOS 점수 기여: CORE-1 (9.2), CORE-5 (8.5), ADJ-3 (7.6).
- 자세한 점수는 [`../concepts/aos-dos-framework.md`](../concepts/aos-dos-framework.md).

## 관련 기능 · CJM 단계

| 우선순위 | 기능 | CJM | 동작 |
|---|---|---|---|
| ★★★ | F1 HFF-Hub Engine | ② | 1초 단가 비교 |
| ★★ | F4 Data Trust System | ②,③ | 산식·출처 노출 |
| ★ | F2 Anti-BS Dashboard | ② | 광고 노이즈 차단 |
| ★ | F3 Viral Engine | ②,③ | 비교 결과 공유 |

## 카피 톤 가이드

- 숫자 우선: "1일 1,200원 → 채널 평균 대비 32% 절약"
- 군더더기 없는 문장, 이모지 자제, 표·그래프 선호.
- "당신을 위한", "추천" 같은 마케팅 단어 회피.

## 결론·시사점

- C1은 **Phase 1 (0~6개월) 메인 타깃**. SEO 키워드는 "[성분명] 가성비", "[브랜드] 단가" 중심.
- F1 정밀도가 곧 C1 만족도. 환산 오차 ±5% 이내가 신뢰 임계.
- C1 1명을 잘 만족시키면 ADJ-3·CJM-3을 통해 평균 1.4명을 데려온다(공유). → F3와의 결합이 LTV 곱셈.
