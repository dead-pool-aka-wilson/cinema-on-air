# Cinema On Air — 기획 문서 체계 구축

## TL;DR

> **Quick Summary**: 지금까지 수행한 모든 서비스 기획 리서치(경쟁 분석, Steam 벤치마킹, 크리에이터/관객 인사이트, 기술 검토)와 확정된 결정 사항, 가설 검증 계획을 체계적인 `docs/` 문서로 정리한다. AI 에이전트가 개발 시 참조할 수 있는 영구적 컨텍스트 기반을 만드는 것이 목적.
>
> **Deliverables**:
> - `docs/` 폴더에 9개 기획 문서 (00~08)
> - 각 문서에 메타데이터 헤더, 결정 마커(`[DECIDED]`/`[OPEN]`/`[HYPOTHESIS]`), 교차 참조 포함
> - AI 에이전트 라우팅 가이드 (`00-index.md`)
>
> **Estimated Effort**: Medium (9개 문서, 각 50~200줄)
> **Parallel Execution**: YES — 3 waves
> **Critical Path**: Task 1 (디렉토리 정리) → Tasks 2-9 (문서 작성, 병렬) → Task 10 (인덱스) → Final Verification

---

## Context

### Original Request
사용자가 "제품의 구체적인 기획을 하나씩 다 마크다운으로 작성하고 해당 기획을 확정지은 다음에 개발을 하도록 해서 확장성이랑 개발 용이성 그리고 컨텍스트를 잃는 환경이 없도록 만들자"라고 요청.

이후 "피자를 한입에 먹으려 하지 말자. 최초 검증 가능한 방향들을 설정하고 해당 방향들이 워킹하는지 실제 개발 전에 진행할 수 있는 테스트 리스트를 만들어"로 방향 수정 → 가설 검증 프레임워크 포함 결정.

### Interview Summary
**Key Discussions**:
- 전세계 30+ 단편영화 플랫폼 경쟁 분석 완료
- Steam 벤치마킹 매핑 확정 (15개 요소 대응)
- 크리에이터 Pain Point 검증 (아마추어 제작기 + 커뮤니티 분석)
- 관객 인사이트 수집 (누벨바그 갤러리 20+ 게시글)
- MVP 8개 기능 확정
- 플랫폼 범위 확정: "만든 후의 플랫폼" — 배급/발견에 집중
- 핵심 메커니즘: "배급사가 관객 데이터로 감독을 발굴하러 오는 구조"
- 6개 핵심 가설 + 6개 사전 검증 테스트 프레임워크 수립
- 기술 스택: Next.js + TypeScript, Mux/Cloudflare Stream

**Research Findings**:
- 단편영화 전용 아카이빙+스트리밍+발견 통합 플랫폼은 전세계에 없음
- 한국 시장 민간 범용 플랫폼 공백
- 영화제 선정률 1~2.5%, 연간 1,505편 제작 중 95%+ 사장
- 영진위 제작지원은 아마추어에게 사실상 접근 불가 (자격 증명 함정)
- 커뮤니티: "양산형" 비판, "개성/훅" 갈증, "보여주고 싶다" 수요

### Metis Review
**Identified Gaps** (addressed):
- Doc 06 (Validation Plan) 소스 파일에 미기록 → 대화 내용에서 추출하여 포함
- `docs/04-feature-specs/` 디렉토리 명명 충돌 → `docs/feature-specs/`로 이동
- §12 법률/권리 콘텐츠 고아 → Doc 07에 포함
- §19 인트로/Ident 콘텐츠 고아 → Doc 01에 포함
- AI 에이전트 라우팅 부재 → `00-index.md` 추가
- 결정 사항 분산 → `08-decision-log.md` 추가
- 결정 마커 미사용 → 모든 문서에 `[DECIDED]`/`[OPEN]`/`[HYPOTHESIS]` 적용
- 문서 메타데이터 헤더 부재 → 각 문서에 status/last_updated/source 포함

---

## Work Objectives

### Core Objective
지금까지 수행한 모든 기획 리서치와 결정 사항을 `docs/` 폴더에 9개 체계적 문서로 정리하여, 이후 개발 및 가설 검증 과정에서 컨텍스트 유실 없이 참조할 수 있는 기반을 만든다.

### Concrete Deliverables
- `docs/00-index.md` — 문서 인덱스 & AI 에이전트 라우팅 가이드
- `docs/01-product-definition.md` — 제품 정의
- `docs/02-market-research.md` — 시장 조사
- `docs/03-steam-benchmarking.md` — Steam 벤치마킹
- `docs/04-creator-insights.md` — 크리에이터 인사이트
- `docs/05-audience-insights.md` — 관객 인사이트
- `docs/06-validation-plan.md` — 가설 검증 계획
- `docs/07-technical-preliminary.md` — 기술 사전 검토
- `docs/08-decision-log.md` — 결정 기록부 (ADR)

### Definition of Done
- [ ] 9개 문서 모두 생성 완료
- [ ] 모든 문서에 메타데이터 헤더 포함 (status, last_updated, source)
- [ ] `[DECIDED]`/`[OPEN]`/`[HYPOTHESIS]` 마커 사용
- [ ] 교차 참조 (`→ see docs/XX.md`) 정상 작동
- [ ] 소스 드래프트(`cinema-on-air-research.md`)의 모든 섹션이 하나 이상의 문서에 매핑됨
- [ ] `00-index.md`에 기능→문서 매핑 완성

### Must Have
- 모든 문서는 한국어로 작성
- 소스 드래프트의 §1~§23 모든 섹션이 하나 이상의 문서에 반영
- 각 문서에 "이 문서에 포함되지 않는 내용" 명시
- 교차 참조 시 문서 간 내용 중복 최소화 (원본은 한 곳, 다른 곳은 참조)
- 검증 계획 문서에 GO/NO-GO 결정 매트릭스 포함

### Must NOT Have (Guardrails)
- 문서 간 동일 내용 복사/붙여넣기 금지 → 교차 참조 사용
- 소스에 없는 내용 창작 금지 → 근거 없는 주장/수치 삽입 불가
- 영어 문서 금지 → 전부 한국어 (기술 용어 병기 허용)
- `[DECIDED]` 마커 없는 결정 사항 금지
- 개발 코드 포함 금지 → 이 단계는 기획 문서만

---

## Verification Strategy (MANDATORY)

> **ZERO HUMAN INTERVENTION** — ALL verification is agent-executed.

### Test Decision
- **Infrastructure exists**: NO (문서 작성 태스크, 코드 테스트 불필요)
- **Automated tests**: None (마크다운 문서)
- **Framework**: N/A

### QA Policy
Every task includes agent-executed QA scenarios.
Evidence saved to `.sisyphus/evidence/task-{N}-{scenario-slug}.{ext}`.

- **Documentation tasks**: Use Bash — `wc -l` (줄 수), `grep` (마커 확인), `ls` (파일 존재)

---

## Execution Strategy

### Parallel Execution Waves

```
Wave 1 (Start Immediately — 디렉토리 준비):
└── Task 1: 디렉토리 구조 정리 [quick]

Wave 2 (After Wave 1 — 문서 작성, MAX PARALLEL):
├── Task 2: 01-product-definition.md [writing]
├── Task 3: 02-market-research.md [writing]
├── Task 4: 03-steam-benchmarking.md [writing]
├── Task 5: 04-creator-insights.md [writing]
├── Task 6: 05-audience-insights.md [writing]
├── Task 7: 06-validation-plan.md [writing]
├── Task 8: 07-technical-preliminary.md [writing]
└── Task 9: 08-decision-log.md [writing]

Wave 3 (After Wave 2 — 인덱스 & 교차참조):
└── Task 10: 00-index.md + 교차참조 검증 [writing]

Wave FINAL (After ALL tasks — verification):
├── Task F1: 문서 완전성 검증 [unspecified-high]
├── Task F2: 소스 매핑 검증 [deep]
└── Task F3: 교차참조 무결성 검증 [quick]

Critical Path: Task 1 → Tasks 2-9 (parallel) → Task 10 → F1-F3
Parallel Speedup: ~75% faster than sequential
Max Concurrent: 8 (Wave 2)
```

### Dependency Matrix

| Task | Depends On | Blocks |
|------|-----------|--------|
| 1 | — | 2-9 |
| 2-9 | 1 | 10 |
| 10 | 2-9 | F1-F3 |
| F1-F3 | 10 | — |

### Agent Dispatch Summary

- **Wave 1**: 1 task → `quick`
- **Wave 2**: 8 tasks → all `writing`
- **Wave 3**: 1 task → `writing`
- **Final**: 3 tasks → `unspecified-high`, `deep`, `quick`

---

## TODOs

> **EVERY task MUST have: Recommended Agent Profile + QA Scenarios.**

- [ ] 1. 디렉토리 구조 정리

  **What to do**:
  - `docs/04-feature-specs/` → `docs/feature-specs/`로 이동 (번호 충돌 해소)
  - `docs/` 디렉토리 하위에 9개 문서 파일 자리 확보

  **Must NOT do**:
  - 기존 파일 삭제 금지
  - `.sisyphus/` 디렉토리 구조 변경 금지

  **Recommended Agent Profile**:
  - **Category**: `quick`
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: NO
  - **Parallel Group**: Wave 1 (단독)
  - **Blocks**: Tasks 2-9
  - **Blocked By**: None

  **References**:
  - `docs/04-feature-specs/` — 현재 빈 디렉토리, `docs/feature-specs/`로 이동 필요

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: 디렉토리 구조 확인
    Tool: Bash
    Steps:
      1. ls -la docs/ 실행
      2. feature-specs/ 디렉토리 존재 확인
      3. 04-feature-specs/ 디렉토리 부재 확인
    Expected Result: docs/feature-specs/ 존재, docs/04-feature-specs/ 부재
    Evidence: .sisyphus/evidence/task-1-dir-structure.txt
  ```

  **Commit**: YES (group with Tasks 2-9)
  - Message: `docs: set up documentation directory structure`
  - Files: `docs/`

- [ ] 2. 제품 정의 문서 (01-product-definition.md)

  **What to do**:
  - 소스 §8(포지셔닝), §16(확정 결정), §18(MVP), §19(인트로/Ident), §22(플랫폼 범위) 기반
  - 포함 내용: 한 줄 정의, 문제 정의(감독/관객/업계/배급사), 해결책(핵심 메커니즘), 타겟 사용자(5개 세그먼트), 핵심 가치 제안(3면), 핵심 원칙(5개: 게이트키퍼 제거, 관객이 판사, 영구 아카이빙, 데이터가 배급사 대신, 시네마틱 경험), 경쟁 포지셔닝 매트릭스, MVP 기능 목록(8개), MVP 미포함 기능, 스코프 경계(IN/OUT), 비즈니스 모델 방향, 성공 지표, 기술 스택 요약, 플랫폼 인트로(Ident) 전략
  - `[DECIDED]`/`[OPEN]`/`[HYPOTHESIS]` 마커 사용
  - 메타데이터 헤더: status: draft, last_updated, source sections
  - "이 문서에 포함되지 않는 내용" 섹션 포함
  - 교차 참조: Steam 상세 → `03-steam-benchmarking.md`, 경쟁사 상세 → `02-market-research.md`

  **Must NOT do**:
  - 경쟁사 상세 분석 포함 금지 (→ Doc 02로 참조)
  - Steam 매핑 테이블 전체 복사 금지 (→ Doc 03으로 참조)
  - 소스에 없는 수치/주장 창작 금지

  **Recommended Agent Profile**:
  - **Category**: `writing`
  - **Skills**: []
    - writing 카테고리가 한국어 기술 문서 작성에 적합

  **Parallelization**:
  - **Can Run In Parallel**: YES
  - **Parallel Group**: Wave 2 (Tasks 2-9)
  - **Blocks**: Task 10
  - **Blocked By**: Task 1

  **References**:

  **Pattern References**:
  - `.sisyphus/drafts/cinema-on-air-research.md` §8 (핵심 포지셔닝 기회) — "IMDB + Letterboxd + Vimeo = 단편영화 전용" 공식
  - `.sisyphus/drafts/cinema-on-air-research.md` §16 (확정된 결정 사항) — 타겟 시장, 핵심 정체성, 수익 모델, 품질 관리, 아카이빙 깊이 등 10+ 결정
  - `.sisyphus/drafts/cinema-on-air-research.md` §18 (MVP 기능 리스트) — 7개 기능 + 스트리밍 = 8개
  - `.sisyphus/drafts/cinema-on-air-research.md` §19 (인트로/Ident) — Netflix/MUBI/Pixar 벤치마크, "인트로 자체가 단편영화" 전략
  - `.sisyphus/drafts/cinema-on-air-research.md` §22 (플랫폼 범위) — "만든 후의 플랫폼", 배급사 발굴 구조, B2B 기회

  **Content References (대화에서 추출 — 소스 파일 미기록 내용)**:
  - 문제 정의 상세: 감독 문제(영화제 1~2.5% 선정률, 자격 증명 함정), 관객 문제(발견 경로 없음, "왓챠 DB 업뎃" 불만, "불행포르노" 편견), 업계 문제(제도가 창작 왜곡, "양산형" 비판), 배급사 문제(데이터 없음)
  - 핵심 가치 제안: 감독("사장되지 않는 곳"), 관객("양산형이 아닌 발견"), 배급사("관객 검증 감독 발굴")
  - 핵심 원칙 5개: P1 게이트키퍼 제거, P2 관객이 판사, P3 영구 아카이빙, P4 데이터가 배급사 대신, P5 시네마틱 경험
  - 성공 지표: Launch(3개월): 영화 100편/감독 50명/월 시청 1,000회, Growth(1년): 1,000편/300명/10,000회, Validation: 배급사 컨택/영화제 대신 플랫폼 선택/커뮤니티 언급
  - 경쟁 매트릭스: Cinema On Air vs 인디그라운드/Shortverse/Cineshort/Klipist/YouTube/Letterboxd/MUBI (아카이빙/스트리밍/발견/감독도구/관객지표 축)

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: 문서 구조 검증
    Tool: Bash
    Steps:
      1. wc -l docs/01-product-definition.md 실행
      2. head -5 docs/01-product-definition.md 로 메타데이터 헤더 확인
      3. grep -c "\[DECIDED\]" docs/01-product-definition.md 로 마커 사용 확인
      4. grep -c "→ see" docs/01-product-definition.md 로 교차참조 확인
    Expected Result: 100줄 이상, 헤더에 "status:" 포함, DECIDED 마커 5개 이상, 교차참조 2개 이상
    Evidence: .sisyphus/evidence/task-2-product-def.txt

  Scenario: 필수 섹션 존재 확인
    Tool: Bash
    Steps:
      1. grep "## " docs/01-product-definition.md 로 섹션 목록 추출
      2. 필수 섹션 존재 확인: 문제 정의, 해결책, 타겟 사용자, 핵심 가치 제안, 핵심 원칙, MVP 기능, 스코프 경계
    Expected Result: 7개 필수 섹션 모두 존재
    Evidence: .sisyphus/evidence/task-2-sections.txt
  ```

  **Commit**: YES (group 1)
  - Message: `docs: add product definition and market research`
  - Files: `docs/01-product-definition.md`

- [ ] 3. 시장 조사 문서 (02-market-research.md)

  **What to do**:
  - 소스 §1~§6(글로벌/한국 플랫폼 분석), §9(시장 규모), §10(비즈니스 모델), §14(인디그라운드 심층) 기반
  - 포함 내용: 글로벌 단편영화 플랫폼 매트릭스(큐레이션/구독/제작자/장르별), 한국 시장 분석(인디그라운드 심층 포함), 범용 플랫폼의 단편 지원, 영화제 제출 플랫폼, 실패 사례와 교훈(Quibi/Withoutabox/ONFIFN), 시장 규모 & 수치, 비즈니스 모델 벤치마크(Mometu/EO Flix/Shortverse), 오픈소스 기술 옵션, 시장 갭 분석
  - 경쟁 포지셔닝 다이어그램 포함 (축: 아카이빙 깊이 vs 발견 메커니즘)
  - 메타데이터 헤더 + 교차참조 사용

  **Must NOT do**:
  - Steam 매핑 상세 포함 금지 (→ Doc 03)
  - 크리에이터 Pain Point 상세 포함 금지 (→ Doc 04)

  **Recommended Agent Profile**:
  - **Category**: `writing`
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: YES
  - **Parallel Group**: Wave 2 (Tasks 2-9)
  - **Blocks**: Task 10
  - **Blocked By**: Task 1

  **References**:
  - `.sisyphus/drafts/cinema-on-air-research.md` §1 (글로벌 플랫폼) — 4개 카테고리 테이블
  - `.sisyphus/drafts/cinema-on-air-research.md` §2 (범용 플랫폼) — Vimeo, MUBI 등
  - `.sisyphus/drafts/cinema-on-air-research.md` §3 (영화제 제출) — FilmFreeway 등
  - `.sisyphus/drafts/cinema-on-air-research.md` §4 (한국/아시아) — 무빌리지, MovieBloc, 인디그라운드 등
  - `.sisyphus/drafts/cinema-on-air-research.md` §5 (실패 사례) — Quibi, Withoutabox, ONFIFN
  - `.sisyphus/drafts/cinema-on-air-research.md` §6 (오픈소스) — MediaCMS, PeerTube
  - `.sisyphus/drafts/cinema-on-air-research.md` §7 (시장 갭 분석) — 크리에이터/시청자/시장 관점
  - `.sisyphus/drafts/cinema-on-air-research.md` §9 (시장 규모) — TAM $500M-$2B, BISFF 5,350편
  - `.sisyphus/drafts/cinema-on-air-research.md` §10 (비즈니스 모델 벤치마크) — Mometu, EO Flix
  - `.sisyphus/drafts/cinema-on-air-research.md` §14 (인디그라운드 심층) — 9개 사업, UX, 한계 8가지

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: 플랫폼 매트릭스 완전성
    Tool: Bash
    Steps:
      1. grep -c "|" docs/02-market-research.md 로 테이블 행 수 확인
      2. grep -i "인디그라운드\|무빌리지\|MovieBloc\|Cineshort\|Klipist" docs/02-market-research.md
    Expected Result: 테이블 행 30개 이상, 핵심 경쟁사 5개 모두 언급
    Evidence: .sisyphus/evidence/task-3-market.txt
  ```

  **Commit**: YES (group 1)
  - Message: `docs: add product definition and market research`
  - Files: `docs/02-market-research.md`

- [ ] 4. Steam 벤치마킹 문서 (03-steam-benchmarking.md)

  **What to do**:
  - 소스 §15 (Steam 벤치마킹) 기반
  - 포함 내용: Steam→단편영화 매핑 테이블(15개 요소), Steam 알고리즘 핵심 원리(CTR, 태그, 큐레이터), 가져와야 할 것(7개), 피해야 할 것(3개), 각 매핑 요소의 MVP 우선순위 표시
  - MVP에서 구현할 요소 vs 추후 구현 요소 구분
  - 메타데이터 헤더 + 교차참조

  **Must NOT do**:
  - 경쟁사 분석 포함 금지 (→ Doc 02)
  - 기술 구현 상세 포함 금지 (→ Doc 07)

  **Recommended Agent Profile**:
  - **Category**: `writing`
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: YES
  - **Parallel Group**: Wave 2
  - **Blocks**: Task 10
  - **Blocked By**: Task 1

  **References**:
  - `.sisyphus/drafts/cinema-on-air-research.md` §15 — Steam 매핑 테이블, 알고리즘 원리, 가져올 것/피할 것

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: 매핑 테이블 완전성
    Tool: Bash
    Steps:
      1. grep -c "Steam" docs/03-steam-benchmarking.md
      2. grep "MVP" docs/03-steam-benchmarking.md 로 우선순위 표시 확인
    Expected Result: "Steam" 15회 이상 언급, MVP 우선순위 구분 존재
    Evidence: .sisyphus/evidence/task-4-steam.txt
  ```

  **Commit**: YES (group 2)
  - Message: `docs: add benchmarking, creator/audience insights`
  - Files: `docs/03-steam-benchmarking.md`

- [ ] 5. 크리에이터 인사이트 문서 (04-creator-insights.md)

  **What to do**:
  - 소스 §17(크리에이터 Pain Point), §20(아마추어/지방 감독), §23 일부(감독 관련 커뮤니티 글) 기반
  - 포함 내용: 배급 구조 문제(게이트키퍼 흐름도), 자격 증명 함정(Credentialing Trap), 영화제 선정률 데이터(BISFF 1%/SIFF 1.5%/정동진 2.1%), 영진위 제작지원 접근성 분석, 아마추어/지방 감독 프로필(제작기 기반), 게이트키퍼 스택 6단계, 시청자미디어센터 네트워크(63개소), 필름메이커스 플랫폼 역할, 핵심 전략적 인사이트("공식 통계에 존재하지 않는 가장 큰 세그먼트")
  - 제작기 원문 요약 포함 (예산, 장비, 캐스팅, 장소, 스태프, 후반작업)
  - 커뮤니티 인용 포함: "보여주고 싶다", 김병규 비판 관련 감독 시각

  **Must NOT do**:
  - 관객 시각 커뮤니티 글 포함 금지 (→ Doc 05)
  - 기술 비용/솔루션 포함 금지 (→ Doc 07)

  **Recommended Agent Profile**:
  - **Category**: `writing`
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: YES
  - **Parallel Group**: Wave 2
  - **Blocks**: Task 10
  - **Blocked By**: Task 1

  **References**:
  - `.sisyphus/drafts/cinema-on-air-research.md` §17 — 배급 구조, 자기강화 루프, Steam 대응
  - `.sisyphus/drafts/cinema-on-air-research.md` §20 — 아마추어 프로필, 게이트키퍼 스택, 검증 데이터
  - `.sisyphus/drafts/cinema-on-air-research.md` §23 — 누벨바그 갤러리 감독 관련 글 (#005 김병규 비판, #012 보여주고 싶다, #019 캐스팅)
  - `/tmp/cinema-posts/` — 원문 커뮤니티 게시글 아카이브 (zip에서 추출)

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: 핵심 데이터 포함 확인
    Tool: Bash
    Steps:
      1. grep "1,505\|1%\|1.5%\|2.1%" docs/04-creator-insights.md
      2. grep "게이트키퍼\|자격 증명" docs/04-creator-insights.md
    Expected Result: 영화제 선정률 수치 + 게이트키퍼/자격 증명 개념 모두 포함
    Evidence: .sisyphus/evidence/task-5-creator.txt
  ```

  **Commit**: YES (group 2)
  - Message: `docs: add benchmarking, creator/audience insights`
  - Files: `docs/04-creator-insights.md`

- [ ] 6. 관객 인사이트 문서 (05-audience-insights.md)

  **What to do**:
  - 소스 §21(관객 관점 수집), §23(누벨바그 갤러리 분석) 기반 + 대화 중 공유된 추가 커뮤니티 글
  - 포함 내용: "누가 보냐?" 문제, "불행포르노" 편견, "양산형" 비판과 "개성/훅" 갈증, "왓챠 DB 업뎃" 불만(메타데이터 수요), 단편영화 추천 요청 패턴(작법 학습/장르별/무드별), 감독 필모그래피 추적 문화(나홍진 단편, 오바야시), 김병규 비판의 관객 시각 반응, 수요 시그널 테이블
  - **한계 명시**: "DC Inside 누벨바그 갤러리 1개 소스 기반, 추가 검증 필요" 경고
  - 잠재 관객 규모 추정 시도 (한국 시네필 인구, Letterboxd 한국 사용자 등 → 데이터 없으면 [OPEN] 마커)

  **Must NOT do**:
  - 감독/크리에이터 관점 포함 금지 (→ Doc 04)
  - 커뮤니티 글 전문 복사 금지 → 핵심 인용만

  **Recommended Agent Profile**:
  - **Category**: `writing`
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: YES
  - **Parallel Group**: Wave 2
  - **Blocks**: Task 10
  - **Blocked By**: Task 1

  **References**:
  - `.sisyphus/drafts/cinema-on-air-research.md` §21 — "왓챠 DB 업뎃", "불행포르노" 편견
  - `.sisyphus/drafts/cinema-on-air-research.md` §23 — 6개 핵심 발견, 수요 시그널 테이블
  - `/tmp/cinema-posts/` — 원문 아카이브

  **Content References (대화에서 추출)**:
  - 사용자가 공유한 게시글: "한국 단편영화 자주 챙겨보는 편임?" (조회 361, 댓글 5)
  - "맨날 한영 단편 불행포르노라고 욕하면서 정작 제대로 보지도 않는건 아니지?" — 관객의 자기모순

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: 한계 명시 확인
    Tool: Bash
    Steps:
      1. grep -i "한계\|limitation\|주의\|경고" docs/05-audience-insights.md
    Expected Result: 데이터 한계를 명시하는 문구 최소 1개 존재
    Evidence: .sisyphus/evidence/task-6-audience.txt
  ```

  **Commit**: YES (group 2)
  - Message: `docs: add benchmarking, creator/audience insights`
  - Files: `docs/05-audience-insights.md`

- [ ] 7. 가설 검증 계획 문서 (06-validation-plan.md)

  **What to do**:
  - **소스 파일에 미기록 — 대화 내용에서 추출하여 작성**
  - 포함 내용: 6개 핵심 가설(H1 공급, H2 수요, H3 발견, H4 리텐션, H5 배급사, H6 등록비), 가설별 위험도, 6개 사전 검증 테스트(방법/측정/성공 기준), 실행 타임라인(Week 1-2/2-4/4-6), GO/NO-GO 결정 매트릭스(H1+H2 조합 4가지 시나리오)
  - 모든 가설에 `[HYPOTHESIS]` 마커 사용
  - 테스트별 구체적 실행 방법 포함 (어디에 글 쓸지, 뭘 측정할지, 성공 기준 수치)

  **Must NOT do**:
  - 검증되지 않은 가설을 `[DECIDED]`로 마킹 금지
  - 테스트 실행 금지 (계획만 문서화)

  **Recommended Agent Profile**:
  - **Category**: `writing`
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: YES
  - **Parallel Group**: Wave 2
  - **Blocks**: Task 10
  - **Blocked By**: Task 1

  **References**:

  **Content References (대화에서 추출 — 이것이 유일한 소스)**:
  - **H1 (공급)**: "감독이 정말 올릴까?" — 위험도 높음. 테스트: 필름메이커스/누갤/영화과 커뮤니티에 설문. 성공 기준: 50명 중 10명+ "올리겠다"
  - **H2 (수요)**: "관객이 정말 볼까?" — 위험도 높음. 테스트 A: 랜딩페이지+대기자명단. 테스트 B: 수동 큐레이션 뉴스레터. 성공 기준: 방문자 5%+ 이메일 등록 / 오픈율 40%+
  - **H3 (발견)**: "태그/큐레이션이 작동할까?" — 위험도 중간. 테스트: 구글시트/노션 DB로 100편 수동 태깅 → 시네필 10명 A/B 테스트. 성공 기준: 태그 기반 만족도 랜덤 대비 2배+
  - **H4 (리텐션)**: "다시 올까?" — 위험도 높음. 테스트: 뉴스레터 4주 리텐션 측정. 성공 기준: 30%+ 4주 연속 오픈
  - **H5 (배급사)**: "데이터를 볼까?" — 위험도 중간. 테스트: 배급사/프로그래머 인터뷰 3~5건. 성공 기준: 5명 중 3명+ "참고하겠다"
  - **H6 (등록비)**: "돈 낼까?" — 위험도 낮음. 테스트: H1 설문에 포함. 성공 기준: 1만원 기준 60%+ 수용
  - **타임라인**: Week 1-2 (H1+H2A+H6 동시), Week 2-4 (H2B+H3+H5), Week 4-6 (H4+종합)
  - **GO/NO-GO**: H1+H2 성공→GO, H1만→PIVOT(감독도구), H2만→PIVOT(큐레이션미디어), 둘다 실패→NO-GO

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: 가설 + 테스트 완전성
    Tool: Bash
    Steps:
      1. grep -c "\[HYPOTHESIS\]" docs/06-validation-plan.md
      2. grep -c "성공 기준" docs/06-validation-plan.md
      3. grep "GO/NO-GO\|GO.*NO" docs/06-validation-plan.md
    Expected Result: HYPOTHESIS 마커 6개, 성공 기준 6개, GO/NO-GO 매트릭스 존재
    Evidence: .sisyphus/evidence/task-7-validation.txt
  ```

  **Commit**: YES (group 3)
  - Message: `docs: add validation plan, tech preliminary, decision log`
  - Files: `docs/06-validation-plan.md`

- [ ] 8. 기술 사전 검토 문서 (07-technical-preliminary.md)

  **What to do**:
  - 소스 §6(오픈소스), §11(기술 비용), §12(법률/권리), §18(기술 스택) 기반
  - 포함 내용: 기술 스택 결정(Next.js+TS), 비디오 호스팅 비교(Mux vs Cloudflare Stream vs AWS), 비용 추정(MVP $300-500/월), 오픈소스 옵션(MediaCMS/PeerTube), 법률/권리 프레임워크(DRM, 라이선스, 70/30 분배), 인증 전략 방향
  - `[DECIDED]` (스택) vs `[OPEN]` (비디오 호스팅 최종 선택, 인증, 데이터 모델) 구분

  **Must NOT do**:
  - DB 스키마/API 설계 포함 금지 (→ 추후 feature-specs)
  - 코드 예시 포함 금지

  **Recommended Agent Profile**:
  - **Category**: `writing`
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: YES
  - **Parallel Group**: Wave 2
  - **Blocks**: Task 10
  - **Blocked By**: Task 1

  **References**:
  - `.sisyphus/drafts/cinema-on-air-research.md` §6 — MediaCMS, PeerTube, CinemataCMS
  - `.sisyphus/drafts/cinema-on-air-research.md` §11 — Cloudflare Stream ~$375, Mux ~$100-300, AWS $500+
  - `.sisyphus/drafts/cinema-on-air-research.md` §12 — 비독점 라이선스, 70/30, DRM, 워터마킹
  - `.sisyphus/drafts/cinema-on-air-research.md` §18 — "Next.js + TypeScript"

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: DECIDED vs OPEN 구분 확인
    Tool: Bash
    Steps:
      1. grep "\[DECIDED\]" docs/07-technical-preliminary.md
      2. grep "\[OPEN\]" docs/07-technical-preliminary.md
    Expected Result: DECIDED (Next.js, TypeScript, 웹 우선) + OPEN (비디오 호스팅, 인증, DB) 모두 존재
    Evidence: .sisyphus/evidence/task-8-tech.txt
  ```

  **Commit**: YES (group 3)
  - Message: `docs: add validation plan, tech preliminary, decision log`
  - Files: `docs/07-technical-preliminary.md`

- [ ] 9. 결정 기록부 (08-decision-log.md)

  **What to do**:
  - 소스 §16(확정 결정) + 대화 전체에서 산재된 결정 사항 통합
  - ADR (Architecture Decision Record) 형식: 결정 / 컨텍스트 / 대안 / 근거 / 상태
  - 모든 `[DECIDED]` 항목 수집: 타겟 시장, 벤치마크 모델, 수익 모델 방향, 품질 관리, 아카이빙 깊이, 플랫폼 형태, 기술 스택, MVP 기능, 플랫폼 범위("만든 후"), 핵심 메커니즘(배급사 발굴 구조)
  - 모든 `[OPEN]` 항목 수집: 수익 모델 구체화, 비디오 호스팅, 인증 시스템, 디자인/UI, 데이터 모델
  - 각 결정에 "어디서 결정됨" 소스 표시

  **Must NOT do**:
  - 결정의 상세 분석 포함 금지 (→ 해당 문서로 참조)
  - 미결정 사항을 DECIDED로 마킹 금지

  **Recommended Agent Profile**:
  - **Category**: `writing`
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: YES
  - **Parallel Group**: Wave 2
  - **Blocks**: Task 10
  - **Blocked By**: Task 1

  **References**:
  - `.sisyphus/drafts/cinema-on-air-research.md` §16 — 핵심 결정 사항 목록
  - `.sisyphus/drafts/cinema-on-air-research.md` §18 — MVP 기능 + 기술 스택
  - `.sisyphus/drafts/cinema-on-air-research.md` §22 — 플랫폼 범위, 배급사 구조

  **Content References (대화에서 추출)**:
  - 타겟 시장: "한국 우선 → 글로벌 확장" (사용자 원문)
  - 벤치마크: "스팀을 벤치마킹 해야할 거 같은데" (사용자 원문)
  - 수익 모델: "아직 모르겠다" → MVP 무료 시작 (사용자 원문)
  - 품질 관리: "소액 등록비 (스팀 방식)" (사용자 원문)
  - 플랫폼 범위: "스트리밍과 관객의 지표로 배급사가 감독을 발굴하게" (사용자 원문)

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: 결정 완전성
    Tool: Bash
    Steps:
      1. grep -c "\[DECIDED\]" docs/08-decision-log.md
      2. grep -c "\[OPEN\]" docs/08-decision-log.md
    Expected Result: DECIDED 10개 이상, OPEN 5개 이상
    Evidence: .sisyphus/evidence/task-9-decisions.txt
  ```

  **Commit**: YES (group 3)
  - Message: `docs: add validation plan, tech preliminary, decision log`
  - Files: `docs/08-decision-log.md`

- [ ] 10. 문서 인덱스 & AI 에이전트 라우팅 가이드 (00-index.md)

  **What to do**:
  - Tasks 2-9 완료 후 작성
  - 포함 내용: 문서 목록(9개) + 각 문서 요약(1줄), 기능→문서 매핑 테이블 (예: "태그 시스템 구현 시 → 01 MVP 범위 + 03 Steam 태그 + 07 기술 스택"), 결정→문서 매핑 (예: "비디오 호스팅 선택 → 07"), 소스 드래프트 섹션→문서 매핑(§1~§23), 문서 상태 대시보드 (draft/reviewed/final), 용어 사전 (게이트키퍼 스택, 자격 증명 함정, 자기강화 루프 등)
  - 교차참조 무결성 검증 포함

  **Must NOT do**:
  - 다른 문서의 내용 반복 금지
  - 불필요한 설명 금지 — 라우팅에 집중

  **Recommended Agent Profile**:
  - **Category**: `writing`
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: NO
  - **Parallel Group**: Wave 3 (단독)
  - **Blocks**: Final Verification
  - **Blocked By**: Tasks 2-9

  **References**:
  - `docs/01-product-definition.md` ~ `docs/08-decision-log.md` — 모든 문서 읽어서 인덱싱

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: 라우팅 매핑 완전성
    Tool: Bash
    Steps:
      1. grep -c "→" docs/00-index.md 로 매핑 수 확인
      2. docs/ 내 모든 .md 파일이 인덱스에 언급되는지 확인
    Expected Result: 매핑 10개 이상, 9개 문서 모두 인덱스에 존재
    Evidence: .sisyphus/evidence/task-10-index.txt

  Scenario: 교차참조 무결성
    Tool: Bash
    Steps:
      1. grep -roh "→ see docs/[^ )]*\.md" docs/ | sort -u > /tmp/refs.txt
      2. while read ref; do file=$(echo "$ref" | grep -oP 'docs/\S+\.md'); test -f "$file" || echo "BROKEN: $file"; done < /tmp/refs.txt
    Expected Result: 깨진 참조 0개
    Evidence: .sisyphus/evidence/task-10-crossref.txt
  ```

  **Commit**: YES
  - Message: `docs: add index and cross-reference verification`
  - Files: `docs/00-index.md`

---

## Final Verification Wave

> 3개 검증 에이전트가 병렬 실행. 모두 APPROVE 필요. REJECT 시 수정 후 재실행.

- [ ] F1. **문서 완전성 검증** — `unspecified-high`

  **What to do**:
  - 9개 문서 모두 존재하는지 확인 (`docs/00-index.md` ~ `docs/08-decision-log.md`)
  - 각 문서의 메타데이터 헤더 존재 확인 (status, last_updated, source)
  - 각 문서의 `[DECIDED]`/`[OPEN]`/`[HYPOTHESIS]` 마커 적절히 사용되었는지 확인
  - 각 문서에 "이 문서에 포함되지 않는 내용" 섹션 존재 확인
  - 각 문서의 최소 줄 수 확인 (50줄 이상)
  - `docs/feature-specs/` 디렉토리 존재 + `docs/04-feature-specs/` 부재 확인

  **Must NOT do**:
  - 문서 내용 수정 금지 (검증만)
  - 누락 발견 시 직접 작성 금지 → REJECT 보고서에 기록

  **Recommended Agent Profile**:
  - **Category**: `unspecified-high`
    - Reason: 체계적 검증 + 스크립트 실행 필요
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: YES
  - **Parallel Group**: Wave FINAL (F1, F2, F3 동시)
  - **Blocks**: None
  - **Blocked By**: Task 10

  **References**:
  - `.sisyphus/plans/docs-foundation.md` — "Definition of Done" 섹션의 6개 완료 기준
  - `docs/` — 검증 대상 전체

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: 9개 문서 존재 + 최소 줄 수
    Tool: Bash
    Steps:
      1. ls docs/*.md | wc -l 실행
      2. for f in docs/*.md; do lines=$(wc -l < "$f"); echo "$f: $lines"; if [ "$lines" -lt 50 ]; then echo "FAIL: $f is under 50 lines"; fi; done
    Expected Result: 9개 파일 존재, 모든 파일 50줄 이상
    Failure Indicators: 파일 수 9 미만, 또는 50줄 미만 파일 존재
    Evidence: .sisyphus/evidence/F1-doc-completeness.txt

  Scenario: 메타데이터 헤더 전수 검사
    Tool: Bash
    Steps:
      1. for f in docs/*.md; do head -10 "$f" | grep -q "status:" && echo "$f: HEADER OK" || echo "FAIL: $f missing header"; done
    Expected Result: 9개 파일 모두 "HEADER OK"
    Failure Indicators: "FAIL" 메시지 1개 이상
    Evidence: .sisyphus/evidence/F1-metadata-headers.txt

  Scenario: 결정 마커 사용 확인
    Tool: Bash
    Steps:
      1. for f in docs/*.md; do count=$(grep -c "\[DECIDED\]\|\[OPEN\]\|\[HYPOTHESIS\]" "$f" 2>/dev/null || echo 0); echo "$f: $count markers"; done
    Expected Result: 대부분 문서에 마커 1개 이상 (00-index.md 제외 가능)
    Failure Indicators: 마커 0개인 문서가 2개 이상
    Evidence: .sisyphus/evidence/F1-decision-markers.txt
  ```

  **Output Format**: `문서 [9/9] | 헤더 [9/9] | 마커 [N/9] | 줄수 [9/9 ≥50] | VERDICT: APPROVE/REJECT`
  **Commit**: NO

- [ ] F2. **소스 매핑 검증** — `deep`

  **What to do**:
  - `.sisyphus/drafts/cinema-on-air-research.md`의 §1~§23 모든 섹션을 읽기
  - 각 섹션이 최소 1개 문서에 반영되었는지 매핑 테이블 작성
  - 매핑 누락 섹션 발견 시 REJECT + 어떤 문서에 포함되어야 하는지 명시
  - "소스에 없는 내용 창작" 여부 스팟체크 (각 문서에서 수치/데이터 3개씩 소스에서 역추적)

  **Must NOT do**:
  - 문서 수정 금지
  - 소스 파일 수정 금지

  **Recommended Agent Profile**:
  - **Category**: `deep`
    - Reason: 소스 파일 691줄 전체를 읽고 9개 문서와 대조하는 심층 작업
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: YES
  - **Parallel Group**: Wave FINAL (F1, F2, F3 동시)
  - **Blocks**: None
  - **Blocked By**: Task 10

  **References**:
  - `.sisyphus/drafts/cinema-on-air-research.md` — 소스 파일 전체 (§1~§23)
  - `docs/01-product-definition.md` ~ `docs/08-decision-log.md` — 대조 대상

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: §1~§23 전수 매핑
    Tool: Bash
    Steps:
      1. .sisyphus/drafts/cinema-on-air-research.md에서 ## 헤더로 섹션 목록 추출
      2. 각 섹션 키워드가 docs/*.md 중 최소 1개에 존재하는지 grep으로 확인
      3. 매핑 테이블 생성: 섹션 | 대상 문서 | 매핑 여부
    Expected Result: 23개 섹션 중 23개 매핑 완료 (100%)
    Failure Indicators: 매핑 안 된 섹션 1개 이상
    Evidence: .sisyphus/evidence/F2-source-mapping.txt

  Scenario: 수치 역추적 스팟체크
    Tool: Bash
    Steps:
      1. docs/ 문서에서 구체적 수치 9개 추출 (각 문서에서 1개씩)
      2. 해당 수치가 소스 파일에 존재하는지 grep으로 확인
    Expected Result: 9개 수치 중 9개가 소스에서 확인됨
    Failure Indicators: 소스에 없는 수치 발견 (창작 의심)
    Evidence: .sisyphus/evidence/F2-fact-check.txt
  ```

  **Output Format**: `매핑 [23/23] | 스팟체크 [9/9] | 창작 의심 [0건] | VERDICT: APPROVE/REJECT`
  **Commit**: NO

- [ ] F3. **교차참조 무결성 검증** — `quick`

  **What to do**:
  - 모든 `docs/*.md` 파일에서 `→ see docs/XX.md` 패턴 추출
  - 참조 대상 파일이 실제 존재하는지 확인
  - 양방향 참조 확인: A→B 참조 시 B에서도 A 관련 내용이 있는지 스팟체크
  - `00-index.md`의 문서 목록이 실제 파일과 1:1 매칭되는지 확인
  - 문서 간 내용 중복 검사: 동일 문장이 2개 이상 문서에 존재하는지 스팟체크

  **Must NOT do**:
  - 문서 수정 금지
  - 참조 링크 수정 금지

  **Recommended Agent Profile**:
  - **Category**: `quick`
    - Reason: grep 기반 단순 패턴 매칭 작업
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: YES
  - **Parallel Group**: Wave FINAL (F1, F2, F3 동시)
  - **Blocks**: None
  - **Blocked By**: Task 10

  **References**:
  - `docs/*.md` — 모든 문서

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: 깨진 교차참조 탐지
    Tool: Bash
    Steps:
      1. grep -roh "→ see docs/[^ )\"]*\.md" docs/ | sort -u > /tmp/refs.txt
      2. while IFS= read -r ref; do file=$(echo "$ref" | grep -oP 'docs/\S+\.md'); test -f "$file" && echo "OK: $file" || echo "BROKEN: $file"; done < /tmp/refs.txt
    Expected Result: 깨진 참조 0개
    Failure Indicators: "BROKEN" 메시지 1개 이상
    Evidence: .sisyphus/evidence/F3-crossref-integrity.txt

  Scenario: 인덱스-파일 1:1 매칭
    Tool: Bash
    Steps:
      1. ls docs/*.md | sort > /tmp/actual-docs.txt
      2. grep -oP 'docs/\d{2}-[a-z-]+\.md' docs/00-index.md | sort > /tmp/indexed-docs.txt
      3. diff /tmp/actual-docs.txt /tmp/indexed-docs.txt
    Expected Result: diff 출력 없음 (완전 일치)
    Failure Indicators: diff 출력 존재 (누락 또는 잉여)
    Evidence: .sisyphus/evidence/F3-index-match.txt

  Scenario: 내용 중복 스팟체크
    Tool: Bash
    Steps:
      1. docs/ 내 각 문서에서 40자 이상 문장 10개씩 무작위 추출
      2. 해당 문장이 다른 문서에도 존재하는지 grep
    Expected Result: 중복 문장 0개 (교차참조로 대체되어야 함)
    Failure Indicators: 동일 문장이 2개 이상 문서에 존재
    Evidence: .sisyphus/evidence/F3-duplication-check.txt
  ```

  **Output Format**: `교차참조 [N개 정상/0 깨짐] | 인덱스 매칭 [OK/FAIL] | 중복 [0건] | VERDICT: APPROVE/REJECT`
  **Commit**: NO

---

## Commit Strategy

- **1**: `docs: set up documentation directory structure` — docs/
- **2**: `docs: add product definition and market research` — docs/01, docs/02
- **3**: `docs: add benchmarking, creator/audience insights` — docs/03, 04, 05
- **4**: `docs: add validation plan, tech preliminary, decision log` — docs/06, 07, 08
- **5**: `docs: add index and cross-reference verification` — docs/00

---

## Success Criteria

### Verification Commands
```bash
# 9개 문서 존재 확인
ls docs/*.md | wc -l  # Expected: 9

# 각 문서 최소 줄 수 확인
for f in docs/*.md; do echo "$f: $(wc -l < "$f") lines"; done
# Expected: 모든 파일 50줄 이상

# 메타데이터 헤더 확인
for f in docs/*.md; do head -5 "$f" | grep -q "status:" && echo "$f: OK" || echo "$f: MISSING HEADER"; done

# 결정 마커 사용 확인
grep -c "\[DECIDED\]\|\[OPEN\]\|\[HYPOTHESIS\]" docs/*.md

# 교차참조 무결성
grep -roh "→ see docs/[^ ]*\.md" docs/ | sort -u | while read ref; do
  file=$(echo "$ref" | grep -oP 'docs/\S+\.md')
  test -f "$file" && echo "OK: $file" || echo "BROKEN: $file"
done
```

### Final Checklist
- [ ] 9개 문서 모두 생성
- [ ] 소스 §1~§23 매핑 완료
- [ ] 교차참조 모두 정상
- [ ] 메타데이터 헤더 모두 존재
- [ ] 결정 마커 사용됨
