---
title: JTBD — Jobs to be Done (Job Story 6종)
type: concept
status: stable
last_updated: 2026-04-20
sources: [raw/10_jtbd-interview-report.md, raw/00_PRD_v1.md]
related: [wiki/personas/, wiki/concepts/aos-dos-framework.md, wiki/features/]
tags: [#JTBD, #JobStory]
---

## 정의

Clayton Christensen의 JTBD(Jobs to be Done) 프레임에 따라, "고객이 우리 서비스를 '고용(hire)'하는 진짜 이유"를 페르소나별로 1줄 Job Story로 정리.

> **포맷:** *"When ____, I want to ____, so I can ____."*

## 6개 Job Story

### J1 — C1 (가성비 최적화자)

> When 새로운 영양제를 사야 하거나 기존 제품의 가격이 올랐을 때,
> I want 동일 성분 기준 1일 단가를 채널 간 자동 비교받고,
> so I can 30분 이상의 비교 노가다 없이 가장 효율적인 선택을 할 수 있다.

- 매핑 기능: F1 HFF-Hub Engine, F2 Anti-BS Dashboard
- 핵심 Pain: CORE-1, CORE-2

### J2 — C2 (건강 계기 진입자)

> When 건강 검진에서 안 좋은 신호를 받거나 가족이 아플 때,
> I want 광고 노이즈 없이 검증된 정보로 첫 영양제를 안전하게 고르고,
> so I can "이거 진짜 효과 있나?"라는 죄책감 없이 가족과 나를 챙길 수 있다.

- 매핑 기능: F2 Anti-BS Dashboard, F4 Data Trust System
- 핵심 Pain: CORE-2, CORE-4, CJM-1

### J3 — A2 (트렌드 탐색자)

> When 인스타·유튜브에서 새로운 성분을 발견했을 때,
> I want 그게 진짜 트렌드인지 마케팅 부풀림인지 1초 안에 검증하고,
> so I can 친구들에게 자신감 있게 공유하고 트렌드 리더로 보일 수 있다.

- 매핑 기능: F3 Viral Engine, F2 Anti-BS Dashboard
- 핵심 Pain: ADJ-1, CJM-3

### J4 — E1 (디지털 약자)

> When 자녀가 영양제를 추천했거나 약국에서 권유받았을 때,
> I want 복잡한 비교 없이 "이거 안전하고 값 적당한지" 한 화면으로 확인하고,
> so I can 자녀에게 다시 묻지 않고 스스로 결정해 가족을 챙길 수 있다.

- 매핑 기능: F1 (단순 모드), F4 Data Trust
- 핵심 Pain: EXT-1, CJM-1

### J5 — E2 (데이터 검증가)

> When 어떤 비교 결과를 보았을 때,
> I want 그 숫자의 출처와 산식을 추적할 수 있고 잘못이 있으면 신고할 수 있어야 하고,
> so I can "데이터를 못 믿는 죄책감" 없이 사용할 수 있다.

- 매핑 기능: F4 Data Trust System (출처 추적, 신고)
- 핵심 Pain: CORE-4, EXT-3

### J6 — N1 (브랜드 충성 비사용자)

> When 지금 먹는 브랜드의 가격이 갑자기 오르거나 광고 논란이 터졌을 때,
> I want 같은 성분의 더 합리적인 대체재를 부담 없이 확인하고,
> so I can "내 선택이 틀린 게 아니었다"는 안도감을 유지하면서 합리적으로 환승할 수 있다.

- 매핑 기능: F1 + F2 (전환 트리거 콘텐츠)
- 핵심 Pain: NON-1, ADJ-2

## 본 프로젝트에서 의미

- **6개 Job Story 중 J1·J2는 MVP에서 100% 충족되어야 함.** 나머지(J3·J4·J5·J6)는 Phase 2~3에서 단계 충족.
- 모든 Job Story의 **공통 결론절(so I can ___)** 에는 "**죄책감 없이 / 부담 없이 / 자신감 있게**" 같은 정서 키워드가 등장 — 본 사업의 진짜 가치는 **인지 부담 제거 = 정서적 안도**라는 의미.
- 인터뷰 원본 문장 인용은 raw/10 §2 참조.

## 결론·시사점

> 우리는 "영양제 비교 정보"를 파는 게 아니라 **"비교 노가다와 죄책감으로부터의 해방"**을 판다.
> 이 명제가 모든 페르소나·기능·UX 카피의 최상위 가이드.
