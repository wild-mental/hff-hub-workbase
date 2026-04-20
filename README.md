# HFF-Hub Workbase

국내 건강기능식품 성분·가격 비교 플랫폼 **HFF-Hub (Health Functional Food Hub)** MVP를 기획하고 구조화한 **LLM 전용 위키 기반 프로젝트 저장소**입니다.

이 저장소의 핵심은 코드보다 먼저 **지식 베이스를 만드는 것**입니다. `raw/` 에 있는 원본 기획 문서 13건을 바탕으로, LLM이 읽기 좋고 계속 갱신 가능한 `wiki/` 를 구축했습니다.

> 한 줄 정의:  
> **"비교 노가다와 죄책감으로부터의 해방"을 목표로 하는 건강기능식품 비교·팩트체크 플랫폼의 지식 인프라**

## 이 저장소에서 다루는 것

- 멀티 채널 영양제 가격을 **1일 복용량 기준 단가**로 환산하는 제품 설계
- 광고/뒷광고 표현을 검증하는 **Anti-BS Dashboard**
- 공유 중심 유입을 위한 **Viral Engine**
- 출처·산식·신고 루프를 포함한 **Data Trust System**
- 시장, 페르소나, JTBD, AOS-DOS, 경쟁사, KSF, 가치사슬 등 사업 전반의 구조화

## 저장소 구조

```text
hff-hub-workbase/
├── README.md               # GitHub 루트 소개 문서
├── llm-wiki.md             # LLM Wiki 패턴 원본 (EN)
├── llm-wiki.ko.md          # LLM Wiki 패턴 원본 (KO)
├── raw/                    # 원본 문서 13건 (불변)
├── wiki/                   # LLM이 구축·유지하는 지식 베이스
└── slides/                 # 위키/프로젝트 소개 슬라이드 (Marp)
```

## 어디서부터 읽으면 되나

### 프로젝트를 3분 안에 이해하고 싶다면

1. [`wiki/synthesis.md`](wiki/synthesis.md)  
   한 페이지로 압축한 전체 요약입니다.
2. [`wiki/README.md`](wiki/README.md)  
   위키의 목적과 읽는 방법을 설명합니다.
3. [`wiki/index.md`](wiki/index.md)  
   전체 페이지 카탈로그입니다.

### 위키 운영 방식을 이해하고 싶다면

1. [`wiki/AGENTS.md`](wiki/AGENTS.md)  
   파일 규약, 프론트매터, ingest/query/lint 워크플로를 정의한 스키마입니다.
2. [`wiki/log.md`](wiki/log.md)  
   위키가 어떻게 쌓여 왔는지 시간순으로 볼 수 있습니다.

### 발표 자료로 빠르게 훑고 싶다면

- [`slides/llm-wiki-overview.md`](slides/llm-wiki-overview.md)
- [`slides/README.md`](slides/README.md)

## 현재 들어있는 결과물

- `raw/` 원본 문서: **13건**
- `wiki/` 지식 베이스 페이지: **49건**
  - 메타: 5
  - 엔티티: 3
  - 페르소나: 6
  - 기능: 4
  - 경쟁사: 4
  - 컨셉/프레임: 14
  - 소스 요약: 13

## 핵심 문서

### 제품/전략

- [`wiki/entities/product-HFF-Hub.md`](wiki/entities/product-HFF-Hub.md)
- [`wiki/entities/tech-stack.md`](wiki/entities/tech-stack.md)
- [`wiki/concepts/market-refiner-positioning.md`](wiki/concepts/market-refiner-positioning.md)
- [`wiki/concepts/q4-q1-flywheel.md`](wiki/concepts/q4-q1-flywheel.md)

### 고객/시장

- [`wiki/concepts/tam-sam-som.md`](wiki/concepts/tam-sam-som.md)
- [`wiki/concepts/persona-spectrum.md`](wiki/concepts/persona-spectrum.md)
- [`wiki/concepts/customer-journey-map.md`](wiki/concepts/customer-journey-map.md)
- [`wiki/concepts/jtbd.md`](wiki/concepts/jtbd.md)
- [`wiki/concepts/aos-dos-framework.md`](wiki/concepts/aos-dos-framework.md)

### 기능

- [`wiki/features/f1-HFF-Hub-engine.md`](wiki/features/f1-HFF-Hub-engine.md)
- [`wiki/features/f2-anti-bs-dashboard.md`](wiki/features/f2-anti-bs-dashboard.md)
- [`wiki/features/f3-viral-engine.md`](wiki/features/f3-viral-engine.md)
- [`wiki/features/f4-data-trust.md`](wiki/features/f4-data-trust.md)

## 이 저장소를 어떻게 쓰나

이 저장소는 일반적인 "코드 저장소"보다는 **지식 베이스 중심 저장소**에 가깝습니다.

### 원칙

- `raw/` 는 원본 보관소입니다. 직접 수정하지 않습니다.
- `wiki/` 는 LLM이 읽고 쓰기 좋은 구조로 정리된 지식 베이스입니다.
- 새로운 문서나 질문에서 나온 통찰은 채팅에만 두지 말고 다시 위키에 환원합니다.

### 기본 워크플로

1. 새 문서를 `raw/` 에 추가합니다.
2. LLM에게 `ingest <파일명>` 을 요청합니다.
3. LLM이 `wiki/sources/` 요약과 관련 페이지를 갱신합니다.
4. `wiki/index.md` 와 `wiki/log.md` 에 반영합니다.

자세한 규칙은 [`wiki/AGENTS.md`](wiki/AGENTS.md) 를 참고하세요.

## 슬라이드 보기

Marp 기반 슬라이드는 Obsidian 또는 Marp CLI로 볼 수 있습니다.

```bash
npm install -g @marp-team/marp-cli
marp slides/llm-wiki-overview.md -o slides/llm-wiki-overview.html
```

자세한 방법은 [`slides/README.md`](slides/README.md) 에 정리되어 있습니다.

## 왜 이런 형태로 만들었나

기획 문서가 많아질수록 LLM은 매번 긴 문서를 다시 읽어야 하고, 같은 질문에도 답변이 흔들릴 수 있습니다.  
이 저장소는 그 문제를 해결하기 위해:

- 원본은 그대로 보존하고
- 위키는 LLM 친화적으로 재구성하고
- 운영 규칙은 `AGENTS.md` 로 고정하는

**Raw + Wiki + Schema** 구조를 채택했습니다.

## 현재 상태

- 코드 구현보다 먼저 **지식 베이스 구조화**를 완료한 상태입니다.
- 제품, 시장, 고객, 기능, 경쟁, 메시지에 대한 핵심 설계가 위키에 정리되어 있습니다.
- 이후 실제 구현 단계에서도 이 위키를 단일한 컨텍스트 소스로 사용할 수 있습니다.

## 참고

- [`llm-wiki.md`](llm-wiki.md)
- [`llm-wiki.ko.md`](llm-wiki.ko.md)
- [`wiki/README.md`](wiki/README.md)
- [`wiki/synthesis.md`](wiki/synthesis.md)
- [`wiki/index.md`](wiki/index.md)
