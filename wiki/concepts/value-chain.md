---
title: 가치사슬(Value Chain) — 에셋 라이트 정보 중개 모델
type: concept
status: stable
last_updated: 2026-04-20
sources: [raw/3_value-chain.md, raw/00_PRD_v1.md, raw/05_SRS_v1.md]
related: [wiki/concepts/ksf.md, wiki/concepts/porters-five-forces.md, wiki/features/]
tags: [#가치사슬, #BM, #에셋라이트]
---

## 정의

Michael Porter의 가치사슬 모형을 본 프로젝트(데이터 중개·정보 큐레이션 비즈니스)에 맞춰 재해석한 모델. 본 사업의 가치는 **물리적 제품 흐름(In→Out 물류)이 아니라 데이터 흐름(원본 → 정제 → 가공 → 신뢰 → 의사결정 지원)**에서 발생한다.

## 본 프로젝트에서 의미

### 주(主)활동 매핑

| 전통적 활동 | 본 프로젝트 적응형 활동 |
|---|---|
| Inbound Logistics | **데이터 수집·정제 (Data Refinement)** — 채널·식약처·논문 크롤링 + 정규화 |
| Operations | **로직 엔진 운영** — HFF-Hub Engine + 팩트체크 LLM 파이프라인 |
| Outbound Logistics | **결과 전달 채널** — 모바일 웹 UI + 1-Tap 공유 카드(F3) |
| Marketing & Sales | **신뢰 마케팅** — Q4 진입 → Q1 정착 SEO/바이럴 (→ [`q4-q1-flywheel.md`](q4-q1-flywheel.md)) |
| Service | **데이터 신뢰 시스템 (F4)** — 오류 신고/제보 루프 |

### 지원 활동

| 활동 | 본 프로젝트 |
|---|---|
| Firm Infrastructure | 1인 기획+1인 개발 + LLM 보조 (린·에셋 라이트 구조) |
| HRM | Vibe Coding 기반 자기충족 개발 체계 (→ [`vibe-coding.md`](vibe-coding.md)) |
| Technology Development | LLM(Gemini) + RAG + Vector Search + 시멘틱 매칭 알고리즘 |
| Procurement | API/DB 제휴 (식약처 OPEN-API · 쿠팡파트너스 · iHerb Affiliate) |

## 핵심 도표·수치

| 단가/규모 | 값 | 검증 |
|---|---|---|
| 평균 신규 사용자 획득 비용(CAC) 목표 | < 1,000원 | ⚠️ 추정 |
| Asset-Light 비용 구조의 변동비/매출 비율 | < 25% | ⚠️ 추정 |
| LLM 호출 비용/MAU 1명 | < 50원/월 (Gemini Flash 기준) | ⚠️ 추정 |

## 결론·시사점

- **자체 재고·물류 0%**: 모든 거래는 제휴 채널을 통한 트래픽 송출이다.
- **수익 모델 단계**:
  1. (단기) 제휴 수수료 (쿠팡파트너스 · iHerb Affiliate)
  2. (중기) 데이터 라이선싱 (정제된 단가/성분 DB → 약사·언론사·연구기관)
  3. (장기) 광고 — 단, 약사 관점 큐레이션 등 신뢰 자산을 훼손하지 않는 형태로만
- **방어선:** 데이터 정제 알고리즘과 신뢰 자산 자체가 모방 비용이 가장 큰 자산. (→ [`ksf.md`](ksf.md))
