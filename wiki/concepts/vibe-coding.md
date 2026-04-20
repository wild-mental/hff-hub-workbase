---
title: Vibe Coding — 1인 개발자의 LLM 보조 풀스택 전략
type: concept
status: stable
last_updated: 2026-04-20
sources: [raw/00_PRD_v1.md, raw/05_SRS_v1.md, raw/3_value-chain.md]
related: [wiki/concepts/value-chain.md, wiki/entities/tech-stack.md, wiki/features/]
tags: [#개발방법론, #LLM]
---

## 정의

**Vibe Coding** = 기획자 1명 + 개발자 1명(또는 1인 풀스택) + LLM 보조의 3자 협업으로, 풀스택 MVP를 6~12주 안에 실서비스 수준까지 끌어올리는 운영 방식.

핵심: **개발자는 코드를 직접 쓰지 않고 "설계의 의도"와 "검수"에 집중**, 보일러플레이트와 1차 구현은 LLM(Cursor/Codex/Claude)이 담당.

## 본 프로젝트에서 의미

본 사업은 [`value-chain.md`](value-chain.md)에서 정의한 **에셋 라이트 구조의 인적 자원 측면**을 구현하는 운영 모델이다.

- **인력:** 기획 1 + 개발 1 (실질 1.0 FTE)
- **LLM 보조:** Cursor/Codex/Claude를 1차 페어 개발자로 사용
- **외주:** 0건 (디자인 = shadcn/ui + Tailwind, 인프라 = Vercel + Supabase)
- **목표 속도:** PRD → 첫 배포까지 6주, MVP F1~F4 모두 12주

## 운영 원칙

### 1. 기획-개발 통합 산출물

- PRD/SRS/CJM/Persona Spectrum 등 모든 기획 산출물은 **LLM이 바로 읽을 수 있는 마크다운**으로 작성.
- 본 위키 자체가 그 산출물의 정제판이다.

### 2. LLM 친화적 코드베이스

- 폴더 구조·파일명·함수명에 **명시적 도메인 어휘** 사용 (예: `HFF-Hub-engine`, `anti-bs-dashboard`).
- 모든 핵심 모듈에 README + 의도(intent) 주석.
- 테스트는 사람이 읽기 쉬운 BDD 스타일.

### 3. 검수 우선 (Review-first)

- LLM이 생성한 코드는 **반드시 사람이 1줄씩 통과 후 머지**. 자동 머지 금지.
- 보안·결제·개인정보 영역은 LLM 생성 비율을 50% 이하로 제한.

### 4. 위키 환원 의무

- 채팅으로 풀린 답·설계 결정은 반드시 본 위키([`AGENTS.md`](../AGENTS.md) Query 워크플로 참조)에 환원.
- "기억"은 채팅 이력이 아니라 위키에 둔다.

## 핵심 도구 스택

| 단계 | 도구 |
|---|---|
| 기획 정제 | Cursor + 본 위키 |
| 코드 1차 생성 | Cursor (Claude/Codex 모델) |
| 코드 검수·디버깅 | Cursor + 사람 |
| 인프라/배포 | Vercel CLI + GitHub Actions |
| 데이터 정규화 | Gemini Flash (LLM) + 정규식 룰 |
| 테스트 | Vitest + Playwright |

## 결론·시사점

- **인적 자원의 변동비화:** 기획·디자인·구현·배포·운영을 1인 + LLM으로 묶어 인건비를 변동비처럼 운영.
- **전제 조건:** 도메인 산출물(본 위키)이 충분히 정제되어 있어야 LLM이 일관된 결과물을 만든다 → 위키의 품질 = 개발 속도의 상한.
- **금기:** "LLM이 다 알아서 한다"는 가정. 전체 흐름의 **운전석은 사람**이며 LLM은 보조석. 위키와 검수가 그 운전대다.
