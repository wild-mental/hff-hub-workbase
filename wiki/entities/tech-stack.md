---
title: 기술 스택 — HFF-Hub MVP
type: entity
status: stable
last_updated: 2026-04-20
sources: [raw/05_SRS_v1.md, raw/00_PRD_v1.md, raw/3_value-chain.md]
related: [wiki/entities/product-HFF-Hub.md, wiki/concepts/vibe-coding.md, wiki/features/]
tags: [#tech, #stack]
---

## 한 줄 요약

**Next.js 풀스택(App Router) + Supabase + Vercel + Gemini AI** 의 1인 운영 친화 스택. [`../concepts/value-chain.md`](../concepts/value-chain.md)의 "에셋 라이트" 운영을 코드 레벨에서 구현.

## 레이어 구성

| 레이어 | 기술 | 비고 |
|---|---|---|
| 프론트엔드 | Next.js 14+ (App Router), React Server Components | PWA, 모바일 우선 |
| UI | Tailwind CSS + shadcn/ui | 디자인 토큰 일관성 |
| 백엔드 | Next.js Route Handlers + Server Actions | 풀스택 단일 코드베이스 |
| ORM | Prisma 5+ | 스키마 우선 |
| DB | Supabase (PostgreSQL 15) | + pgvector (RAG용) |
| 인증 | Supabase Auth | 이메일 + 카카오 OAuth |
| 호스팅 | Vercel | Edge Functions + ISR |
| AI | Vercel AI SDK + Google Gemini Flash/Pro | 단가 환산·광고 검증·RAG |
| 결제 (Phase 2) | 토스페이먼츠 | 구독·일회성 |
| 분석 | PostHog (Self-host 옵션) | 이벤트·퍼널 |
| 알림 | Resend (이메일) + Web Push | F4 신고 응답 |

## 외부 API

| 카테고리 | API | 용도 |
|---|---|---|
| 가격 | 쿠팡파트너스, 네이버 쇼핑, iHerb Affiliate | F1 입력 |
| 식약처 | OPEN-API (건강기능식품 정보) | F1·F2·F4 |
| 논문 (Phase 2) | PubMed Open Access | F2 팩트체크 |
| OCR | Gemini Vision | F2 광고 이미지 입력 |
| 카카오 | 카카오 공유 SDK | F3 |

## CI/CD

| 단계 | 도구 |
|---|---|
| 코드 호스팅 | GitHub |
| CI | GitHub Actions (lint, test, build) |
| 배포 | Vercel (PR Preview + main 자동 배포) |
| 마이그레이션 | Prisma Migrate (CI에서 자동) |
| E2E | Playwright (Vercel Preview 대상) |
| 모니터링 | Vercel Analytics + Sentry |

## 보안·컴플라이언스

- **개인정보:** 최소 수집 원칙. 이메일 + (선택) 전화. 건강 정보는 저장 안 함.
- **결제:** PG사 위임 (자체 카드 정보 미보유)
- **건기식법:** F2 검증 결과는 식약처 표시·광고 가이드와 1:1 매핑, 서비스 본문에서 의학적 단정 표현 금지
- **광고/제휴:** 「표시·광고의 공정화에 관한 법률」 준수. 모든 제휴 링크에 표기 의무화.

## 1인 운영 친화 결정

- **단일 코드베이스 (Next.js 풀스택):** 프론트·백엔드 분리 없음 → 컨텍스트 스위칭 비용 ↓
- **관리형 인프라:** Vercel + Supabase = 서버 운영 0
- **shadcn/ui:** 자체 호스팅 가능한 디자인 시스템 → 디자이너 부재 보완
- **LLM 1차 페어 개발:** Cursor + Claude/Codex (→ [`../concepts/vibe-coding.md`](../concepts/vibe-coding.md))

## 결론·시사점

- 스택 결정의 최상위 원칙은 **"1인이 6개월 안에 F1~F4를 운영 가능한가"** — 멀티 클라우드/마이크로서비스/자체 운영 DB 모두 회피.
- 비용 모델: MAU 1만까지 월 < 50만 원 (Vercel Pro + Supabase Pro + Gemini API 합산 기준 ⚠️ 추정).
- Phase 3 이후 트래픽 증가 시 캐싱 레이어(Redis/Upstash) + Worker 분리 검토.
