---
title: 위키 README — HFF-Hub (Health Functional Food Hub) 지식 베이스
type: meta
status: stable
last_updated: 2026-04-20
sources: [llm-wiki.md, llm-wiki.ko.md]
related: [wiki/AGENTS.md, wiki/index.md, wiki/synthesis.md, wiki/log.md]
tags: [#meta, #README]
---

# HFF-Hub 지식 베이스 (LLM-Wiki)

본 디렉터리는 **국내 건강기능식품 성분·가격 비교 플랫폼(코드명 HFF-Hub)** MVP 기획·개발을 위한 누적형 지식 베이스다. `raw/` 폴더의 13개 비즈니스/제품 문서를 LLM이 읽고, 요약·재구성·교차 참조해 만들어낸 위키다.

원본 패턴: 루트의 [`llm-wiki.ko.md`](../llm-wiki.ko.md) (영문은 [`llm-wiki.md`](../llm-wiki.md)).

## 한눈에 보기

- **무엇을 만드나:** 쿠팡/iHerb 등 멀티 채널의 영양제를 "1일 복용량 기준 원화 단가"로 자동 환산하고, 광고 노이즈를 차단한 식약처/논문 기반 팩트체크를 제공하는 모바일 웹 플랫폼.
- **누구를 위한 것:** Q1-A 가성비 최적화자(C1) + Q4-A 건강 계기 진입자(C2)가 핵심. Q4-C 트렌드 탐색자(A2)가 SEO/바이럴 진입.
- **왜 가능한가:** 시장은 "정보 과잉, 가치 실전(失傳)" 상태. AOS-DOS 분석 결과 19개 Pain 중 14개(74%)가 Q1 혁신 기회 사분면에 몰려 있어 명백한 블루오션.
- **핵심 기능 4종:** F1 HFF-Hub Engine · F2 Anti-BS Dashboard · F3 Viral Engine · F4 Data Trust System.
- **기술:** Next.js(App Router) 풀스택 + Prisma + Supabase + Vercel + Tailwind/shadcn.

## 어디서부터 읽으면 되나

| 목적 | 출발 페이지 |
|---|---|
| 위키 전체 카탈로그 | [`index.md`](index.md) |
| 무엇이 어떻게 묶이는지 한 번에 | [`synthesis.md`](synthesis.md) |
| 위키 운영 규칙(에이전트용) | [`AGENTS.md`](AGENTS.md) |
| 활동 기록 | [`log.md`](log.md) |
| 제품 자체 | [`entities/product-HFF-Hub.md`](entities/product-HFF-Hub.md) |
| 시장 기회 핵심 | [`concepts/aos-dos-framework.md`](concepts/aos-dos-framework.md) |
| 페르소나 6명 | [`personas/`](personas/) |
| MVP 기능 4종 | [`features/`](features/) |

## 위키를 새로 시작하는 사람에게

1. `AGENTS.md`를 먼저 읽어 위키의 규약(파일 명명, 프론트매터, ingest/query/lint 워크플로)을 익힌다.
2. `index.md`에서 관심 카테고리로 이동한다.
3. 새 원본을 추가하고 싶다면 `raw/`에 파일을 넣고 LLM에게 *"ingest <파일명>"* 이라고 말하면 된다.
4. 답변/통찰이 새로 만들어졌다면 위키에 환원한다(채팅 기록에 두지 말 것).
