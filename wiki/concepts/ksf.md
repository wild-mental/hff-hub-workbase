---
title: KSF — 핵심 성공 요인 (Key Success Factors)
type: concept
status: stable
last_updated: 2026-04-20
sources: [raw/4_ksf-report.md, raw/00_PRD_v1.md]
related: [wiki/concepts/value-chain.md, wiki/concepts/porters-five-forces.md, wiki/features/]
tags: [#KSF, #전략]
---

## 정의

본 사업이 성공하기 위해 반드시 우월하게 보유해야 할 역량 4가지. 각 KSF는 [`porters-five-forces.md`](porters-five-forces.md)와 [`value-chain.md`](value-chain.md) 분석에서 도출된 위협을 직접 상쇄한다.

## 4대 KSF

### KSF-1. 데이터 신뢰성 — "위키피디아급 신뢰의 영양제판"

가장 어렵고 가장 강력한 방어선. 식약처 + 논문 + 사용자 검증 루프(F4)가 결합되어 시간이 갈수록 강화되는 자산.

- 관련 기능: F4 Data Trust System
- 위협 상쇄: 구매자 교섭력(신뢰 대리인 갈망), 대체재(약사 유튜버)

### KSF-2. UX/UI의 명료성 — "1초 안에 비싼지 싼지 안다"

복잡한 데이터를 직관 한 컷으로. 진입 장벽 = 인지 노력 ≈ 0.

- 관련 기능: F1 HFF-Hub Engine, F3 Viral Engine
- 위협 상쇄: 기존 비교 앱(필라이즈) 정체, 페르소나 E1(노년) 진입 장벽

### KSF-3. 광고/제휴 의존도와 신뢰의 균형

수익은 제휴에서 오지만 신뢰는 광고를 거를 때 만들어진다. 이 모순을 분리 운영하는 룰(예: 노출 알고리즘 ≠ 광고 단가)이 필수.

- 관련 기능: F2 Anti-BS Dashboard, F4 Data Trust System
- 위협 상쇄: 공급자 교섭력(광고비 전가), 대체재(스토리텔링 홈쇼핑)

### KSF-4. 약사·전문가 큐레이션 자산

LLM 자동 분석을 인간 전문가가 검수하는 하이브리드. 일반 비교 앱과의 가장 명확한 차별점.

- 관련 기능: F4 Data Trust System (인간 검수 루프)
- 위협 상쇄: 신규 진입자(OEM D2C, 빅테크 비교 기능)

## 본 프로젝트에서 의미

- KSF-1과 KSF-4는 즉시 구축 불가능한 시간 누적 자산이다 → 초기 사용자 신뢰 1건이 미래 모방 방어선 1건이 된다.
- KSF-2는 MVP 0~3개월에 모두 결정된다(첫 화면 = 평가 기준).
- KSF-3은 BM 설계 단계에서 미리 룰을 박지 않으면 후행 수정 불가능 → [`value-chain.md`](value-chain.md) 수익화 단계 참조.

## 결론·시사점

> 본 사업의 진짜 자산은 **데이터의 양**이 아니라 **데이터의 신뢰**이며, 그 신뢰는 ① 정제 알고리즘, ② 인간 검수, ③ 사용자 신고 루프의 3중 구조에서만 만들어진다. 4대 KSF는 모두 이 한 문장으로 환원된다.
