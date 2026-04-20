---
title: 05_SRS_v1.md — 소프트웨어 요구사항 명세
type: source
status: stable
last_updated: 2026-04-20
sources: [raw/05_SRS_v1.md]
related: [wiki/features/, wiki/entities/tech-stack.md, wiki/concepts/vibe-coding.md]
tags: [#source, #SRS]
---

## 한 줄 요약

PRD의 4개 기능(F1~F4)을 기능 수용 기준(AC), 비기능 요구사항(NFR), 데이터 모델, 외부 의존성, API 계약 수준으로 구체화한 개발 사양서.

## 핵심 포인트

- **AC 단위:** F1 7건, F2 7건, F3 7건, F4 8건 — 본 위키 [`../features/`](../features/)에 1:1 반영.
- **NFR:** TTC ≤ 5초(P95), 가용성 99.5%, 데이터 신선도 24h, F4 신고 SLA 24h.
- **기술 스택:** Next.js + Prisma + Supabase + Vercel + Gemini.
- **데이터 모델:** Product, Ingredient, Channel, PriceSnapshot, Verification, Report.
- **API 계약:** 외부(쿠팡파트너스, 식약처 OPEN-API, iHerb, Gemini) + 내부 Route Handlers.
- **인증·권한:** Supabase Auth (이메일+카카오), 신고/검수 권한 분리.

## 위키에 미친 영향

- 신규: [`entities/tech-stack.md`](../entities/tech-stack.md)
- 영향: [`features/f1-HFF-Hub-engine.md`](../features/f1-HFF-Hub-engine.md), `f2-anti-bs-dashboard.md`, `f3-viral-engine.md`, `f4-data-trust.md` 의 AC/NFR 섹션
- 영향: [`concepts/vibe-coding.md`](../concepts/vibe-coding.md) (1인 운영 친화 결정 근거)

## 인용용 발췌

> "TTC는 단일 지표이지만, 측정 시 5단계 분해(검색 → 후보 매칭 → 가격 조회 → 환산 → 렌더)로 병목을 추적한다."

## 출처

- 경로: [`raw/05_SRS_v1.md`](../../raw/05_SRS_v1.md)
- 작성/갱신일: 2026-04-10 (v1)
