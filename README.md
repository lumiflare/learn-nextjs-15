# Next.js 15 학습 프로젝트 — 4주 배포 로드맵

> 대상: lumiflare
> 목표: **4주 내 Next.js 15(App Router 중심)로 웹앱 배포**

## 기술 스택 / 환경
- **Next.js 15 + React 19**, **TypeScript**
- 개발 서버: **Turbopack**, prod: `next build`
- 데이터: **Prisma** 또는 **Drizzle** (Edge/Node 제약 고려)
- 인증/세션: OAuth 또는 이메일+비번(**Server Actions 기반 폼 처리**, CSRF/레이트리밋)
- 테스트: **Vitest**(유닛), **React Testing Library**(컴포넌트), **Playwright**(E2E)
- 배포: **Vercel** (Docker 미러 제공)
- 성능/운영: 이미지/폰트 최적화, 캐시 태그/무효화, ISR/SSG/SSR, Web Vitals, Sentry
- 접근성/국제화: a11y 체크리스트, i18n 라우팅

---

## 학습 운영 가이드
- 세션 단위 **60–90분**. 각 세션 시작 10–20분은 **React 기초 보강**(state/props/hooks 복습)
- 실습은 **작게 자주 커밋**. 예시 커밋 메시지 포함
- 주4~5일 *x* 2세션 = 주 8–10세션 페이스

---

## 4주 학습 스케줄(요약표)

| 주 | 일 | 세션 | 목표 | PR |
|---|---|---|---|---|
| 1 | 1 | S1 | 프로젝트 초기화, RSC 사고 전환 |
| 1 | 1 | S2 | 파일 기반 라우팅/중첩 레이아웃 |
| 1 | 2 | S3 | RSC 데이터 패칭/캐싱 규칙 |
| 1 | 2 | S4 | Route Handlers(READ API) |
| 1 | 3 | S5 | Prisma/Drizzle 셋업 & 읽기 |
| 1 | 3 | S6 | RSC 직결 vs API 경유 트레이드오프 |
| 1 | 4 | S7 | 로딩/에러 경계, 서스펜스 |
| 1 | 4 | S8 | 스트리밍/Partial Rendering |
| 1 | 5 | S9 | 이미지/폰트/메타/동적 OG |
| 1 | 5 | S10 | **미니프로젝트#1**(읽기 전용 완성) |
| 2 | 1 | S1 | **Server Actions** 폼 처리 |
| 2 | 1 | S2 | 낙관적 업데이트/에러 바운더리 |
| 2 | 2 | S3 | CSRF/레이트리밋 |
| 2 | 2 | S4 | Route Handlers: REST/웹훅 |
| 2 | 3 | S5 | 인증(NextAuth/커스텀) |
| 2 | 3 | S6 | 권한/미들웨어/보안 헤더 |
| 2 | 4 | S7 | 캐시 태그/무효화 |
| 2 | 4 | S8 | i18n 라우팅 + a11y |
| 2 | 5 | S9 | **미니프로젝트#2**(CRUD+Auth) |
| 2 | 5 | S10 | 단위/컴포넌트 테스트 |
| 3 | 1 | S1 | ISR/SSG/SSR 트레이드오프 |
| 3 | 1 | S2 | Turbopack/번들 최적화 |
| 3 | 2 | S3 | Web Vitals 수집/RUM |
| 3 | 2 | S4 | 로깅/에러 추적(Sentry) |
| 3 | 3 | S5 | 이미지/폰트 고급 최적화 |
| 3 | 3 | S6 | Playwright E2E |
| 3 | 4 | S7 | Vercel env/프리뷰/롤백 |
| 3 | 4 | S8 | Docker 미러 빌드 |
| 3 | 5 | S9 | **미니프로젝트#3**(관측/성능) |
| 3 | 5 | S10 | Capstone 설계 킥오프 |
| 4 | 1 | S1 | Capstone 기능 명세 동결 |
| 4 | 1 | S2 | 라우팅/데이터/권한 설계 |
| 4 | 2 | S3 | 캐싱 전략 표/무효화 |
| 4 | 2 | S4 | 보안 체크리스트/미들웨어 |
| 4 | 3 | S5 | 구현 스프린트 1(핵심 경로) |
| 4 | 3 | S6 | 구현 스프린트 2(뮤테이션/웹훅) |
| 4 | 4 | S7 | 테스트 패스(a11y/E2E/유닛) |
| 4 | 4 | S8 | 배포 런북 실행(Vercel/Docker) |
| 4 | 5 | S9 | 운영: 알림/대시보드 |
| 4 | 5 | S10 | 회고/부채 백로그 |

---

## 주간 결과물
- Week1: Read-only 카탈로그(+스트리밍/OG)
- Week2: CRUD + Auth + 태그 캐시
- Week3: 관측/성능 + E2E + 배포 전략
- Week4: Capstone 설계→구현→테스트→배포→운영

---

## 브랜치 전략

- `main`: 배포 브랜치
- `docs/*`: 개념정리를 위한 실습
- `feat/*`: 신규 기능추가 
- `fix/*`: 기존 기능 수정