# Phase 4: 하꼬 영화 유튜버 바이럴 전략 + 인디그라운드 분석 + 제작지원사업 보강

## TL;DR

> **Quick Summary**: Cinema on Air의 시장 확산 전략과 생태계 파트너십을 위한 기획 문서 3건 신규 작성 + 기존 문서 4건 업데이트. 하꼬 영화 유튜버 협업 전략, 인디그라운드 양면 분석(경쟁+파트너), 제작지원사업 데이터 보강을 수행한다.
>
> **Deliverables**:
> - `docs/09-viral-strategy.md` — 하꼬 영화 유튜버 바이럴 확산 전략 (신규)
> - `docs/10-indiground-analysis.md` — 인디그라운드 경쟁/파트너 양면 분석 (신규)
> - `docs/infrastructure/06-funding.md` — 제작지원사업 데이터 보강 (업데이트)
> - `docs/00-index.md`, `docs/02-market-research.md`, `docs/infrastructure/00-index.md`, `docs/08-decision-log.md` — 교차참조 및 인덱스 업데이트
>
> **Estimated Effort**: Medium
> **Parallel Execution**: YES — 3 waves
> **Critical Path**: T0 (Issue+Branch) → T1/T2/T3 (신규문서 병렬) → T4/T5/T6/T7 (업데이트 병렬) → T8 (검증)

---

## Context

### Original Request
- "한국은 영화 유튜버들이 매우 많다. 너무 유명한 유튜버가 아니라 하꼬 (1000명 이상 구독자) 위주로 단편영화 플랫폼 홍보를 위한 바이럴 전략을 작성하기 위한 계획을 세워"
- "인디그라운드에 대해서도 조사하고 감독들이 영화를 제작하기 위해서 국내에서 지원받을 수 있는 사업들도 모두 조사해"
- "모든 문서 추가 및 기존 문서 변경에는 깃허브를 통해 버전관리를 해야함"

### Interview Summary
**Key Discussions**:
- **문서 구조**: 각 주제별 별도 문서 (09, 10 신규 + 06 업데이트) → [DECIDED]
- **인디그라운드 포지셔닝**: 경쟁 분석 + 파트너십 가능성 양면 관점 → [DECIDED]
- **제작지원사업 반영**: 기존 06-funding.md 업데이트 (추가 발견 사업 보강) → [DECIDED]
- **바이럴 타이밍**: 사전 홍보 → 런칭 → 성장 단계별 전략 모두 포함 → [DECIDED]

**Research Findings**:
- 한국 영화 유튜버 6개 서브카테고리 분류 완료, 최적 타겟 3개 식별
- 하꼬 유튜버 협업 비용 3단계 (0~300만원) 매핑
- 핵심 인사이트: "감독 인터뷰 접근권"이 Cinema on Air 고유 자산
- 인디그라운드: 영진위 산하 공공기관, 9개 사업 영역, 경쟁자 아닌 잠재 파트너
- 영화제작업신고증 없이 신청 가능한 제작지원사업 7개 정리

### Metis Review
**Identified Gaps** (addressed):
- **00-index.md 배제 조항 충돌**: line 114 "마케팅 및 홍보 계획" 배제 vs 09-viral-strategy.md 존재 → 09를 "바이럴 확산 전략 리서치"로 프레이밍하고 00-index.md 배제 조항 업데이트로 해결
- **인디그라운드 서비스 수 불일치**: 리서치 요약 "6 core services" vs 02-market-research.md "9개 핵심 사업 영역" → 02-market-research.md의 9개가 정확. 10-indiground-analysis.md에서 9개로 통일
- **하꼬 유튜버 상한선 미정의**: → 기본 범위 1,000~50,000으로 설정, 단계별 세분화 (나노 1K~5K, 마이크로 5K~20K, 스몰 20K~50K)
- **infrastructure/00-index.md 누락**: 06-funding.md 줄 수 변경 반영 필요 → 스코프에 추가
- **ADR 미등록**: 인디그라운드 포지셔닝 결정 → ADR-014 추가
- **00-index.md 마커 카운트 테이블 업데이트 누락**: → 스코프에 추가

---

## Work Objectives

### Core Objective
Cinema on Air 프로젝트의 시장 확산 전략(하꼬 유튜버 협업)과 생태계 파트너십(인디그라운드) 및 제작 인프라(제작지원사업 보강)에 대한 기획 문서를 작성하고, 기존 문서 체계와 일관성 있게 통합한다.

### Concrete Deliverables
1. `docs/09-viral-strategy.md` — 하꼬 영화 유튜버 바이럴 확산 전략 리서치 (신규, 250~350줄)
2. `docs/10-indiground-analysis.md` — 인디그라운드 경쟁/파트너 양면 분석 (신규, 200~300줄)
3. `docs/infrastructure/06-funding.md` — 제작지원사업 데이터 보강 (업데이트, +80~120줄)
4. `docs/00-index.md` — 09/10 문서 행 추가, 마커 카운트 업데이트, 배제 조항 수정
5. `docs/02-market-research.md` — 인디그라운드 심층 분석 교차참조 추가
6. `docs/infrastructure/00-index.md` — 06-funding.md 줄 수/설명 업데이트
7. `docs/08-decision-log.md` — ADR-014 (인디그라운드 포지셔닝) 추가

### Definition of Done
- [ ] 모든 신규/수정 문서에 metadata header (status/last_updated/source) 존재
- [ ] 모든 [UNVERIFIED] 마커가 문서 전체 주장의 20% 미만
- [ ] 모든 교차참조 (`→ see docs/XX`) 대상 파일이 실제 존재
- [ ] 기존 문서 내용이 보존됨 (추가만, 삭제 없음)
- [ ] git commit 형식: `docs(#N): description`
- [ ] PR 생성 및 리뷰 가능 상태

### Must Have
- 09-viral-strategy.md: 3단계 타이밍 (사전 홍보 → 런칭 → 성장), 유튜버 6개 카테고리, 비용 테이블, 감독 인터뷰 접근권 전략
- 10-indiground-analysis.md: 9개 사업 영역 분석, Cinema on Air 비교 테이블, 파트너십 시나리오
- 06-funding.md: AI영화 지원 확대, CJ스토리업 상세 확장, 영화제작업신고증 불필요 사업 종합표, 기존 내용 100% 보존

### Must NOT Have (Guardrails)
- ❌ 일반 마케팅/홍보 계획 (09는 유튜버 협업 전략 리서치만)
- ❌ 일반 SNS 전략, 유료 광고, PR/미디어 릴레이션 (09 스코프 벗어남)
- ❌ 개발 코드 또는 기술 구현 명세
- ❌ 06-funding.md 기존 섹션 재작성/삭제 (추가만 허용)
- ❌ 추측성 사용자 여정 또는 가상 시나리오 (리서치 기반 분석만)
- ❌ 영어 섹션 헤더 (한국어 전체, 기술 용어 영어 병기만 허용)
- ❌ docs/validation/ 파일 수정
- ❌ 02-market-research.md의 기존 인디그라운드 섹션 (lines 52-81) 수정 (교차참조 추가만)

---

## Verification Strategy

> **ZERO HUMAN INTERVENTION** — ALL verification is agent-executed.

### Test Decision
- **Infrastructure exists**: N/A (기획 문서 프로젝트, 코드 없음)
- **Automated tests**: None (문서 작성)
- **Framework**: N/A

### QA Policy
Every task MUST include agent-executed QA scenarios.
Evidence saved to `.sisyphus/evidence/task-{N}-{scenario-slug}.{ext}`.

- **문서 검증**: Bash (wc, grep, cat) — 줄 수 확인, 필수 섹션 존재 확인, [UNVERIFIED] 비율 계산
- **교차참조 검증**: Bash (ls, grep) — 참조 대상 파일 존재 확인
- **Git 검증**: Bash (git diff, git log) — 커밋 형식, 변경 내용 확인

---

## Execution Strategy

### Parallel Execution Waves

```
Wave 0 (Start Immediately — setup):
└── Task 0: GitHub Issue 생성 + 브랜치 생성 [quick]

Wave 1 (After Wave 0 — core documents, MAX PARALLEL):
├── Task 1: docs/09-viral-strategy.md 신규 작성 [unspecified-high]
├── Task 2: docs/10-indiground-analysis.md 신규 작성 [unspecified-high]
└── Task 3: docs/infrastructure/06-funding.md 업데이트 [unspecified-high]

Wave 2 (After Wave 1 — index/reference updates, MAX PARALLEL):
├── Task 4: docs/00-index.md 업데이트 [quick]
├── Task 5: docs/02-market-research.md 업데이트 [quick]
├── Task 6: docs/infrastructure/00-index.md 업데이트 [quick]
└── Task 7: docs/08-decision-log.md ADR-014 추가 [quick]

Wave 3 (After Wave 2 — verification + delivery):
└── Task 8: 종합 검증 + Push + PR 생성 [quick]

Wave FINAL (After ALL tasks — independent review, 4 parallel):
├── Task F1: Plan compliance audit (oracle)
├── Task F2: Document quality review (unspecified-high)
├── Task F3: Cross-reference integrity check (unspecified-high)
└── Task F4: Scope fidelity check (deep)

Critical Path: T0 → T1 → T4 → T8 → F1-F4
Parallel Speedup: ~60% faster than sequential
Max Concurrent: 3 (Wave 1)
```

### Dependency Matrix

| Task | Depends On | Blocks | Wave |
|------|-----------|--------|------|
| T0 | — | T1, T2, T3 | 0 |
| T1 | T0 | T4, T5 | 1 |
| T2 | T0 | T4, T5, T7 | 1 |
| T3 | T0 | T4, T6 | 1 |
| T4 | T1, T2, T3 | T8 | 2 |
| T5 | T2 | T8 | 2 |
| T6 | T3 | T8 | 2 |
| T7 | T2 | T8 | 2 |
| T8 | T4, T5, T6, T7 | F1-F4 | 3 |
| F1-F4 | T8 | — | FINAL |

### Agent Dispatch Summary

- **Wave 0**: **1** — T0 → `quick`
- **Wave 1**: **3** — T1 → `unspecified-high`, T2 → `unspecified-high`, T3 → `unspecified-high`
- **Wave 2**: **4** — T4-T7 → `quick`
- **Wave 3**: **1** — T8 → `quick`
- **FINAL**: **4** — F1 → `oracle`, F2 → `unspecified-high`, F3 → `unspecified-high`, F4 → `deep`

---

## TODOs

- [x] 0. GitHub Issue 생성 + 브랜치 생성

  **What to do**:
  - GitHub Issue 생성: `gh issue create --title "docs: Phase 4 viral strategy + Indiground analysis + funding update" --body "..."` (body에 3개 산출물 + 4개 업데이트 파일 목록 명시)
  - 생성된 이슈 번호로 브랜치 생성: `gh issue develop <N> --checkout`
  - 브랜치명 형식: `{issue-number}-docs-phase4-viral-indiground-funding`

  **Must NOT do**:
  - 기존 이슈 (#5) 재사용 금지 — 새 이슈 생성 필수
  - 브랜치 생성 없이 main에 직접 커밋 금지

  **Recommended Agent Profile**:
  - **Category**: `quick`
    - Reason: 단순 CLI 명령 2개 실행
  - **Skills**: [`git-master`]
    - `git-master`: Git 워크플로우 관리

  **Parallelization**:
  - **Can Run In Parallel**: NO (최초 설정)
  - **Parallel Group**: Wave 0 (단독)
  - **Blocks**: T1, T2, T3
  - **Blocked By**: None

  **References**:
  **Pattern References**:
  - Phase 3 커밋 로그: `git log --oneline -10` — 기존 커밋 메시지 형식 참조 (`docs(#5): ...`)

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: GitHub Issue 생성 확인
    Tool: Bash
    Steps:
      1. `gh issue list --state open --limit 5` 실행
      2. 방금 생성한 이슈가 목록에 존재하는지 확인
    Expected Result: "docs: Phase 4 viral strategy" 제목의 이슈가 open 상태로 존재
    Evidence: .sisyphus/evidence/task-0-issue-created.txt

  Scenario: 브랜치 생성 확인
    Tool: Bash
    Steps:
      1. `git branch --show-current` 실행
      2. 브랜치명이 `{N}-docs-phase4-viral-indiground-funding` 형식인지 확인
    Expected Result: main이 아닌 이슈 번호 기반 브랜치에 위치
    Evidence: .sisyphus/evidence/task-0-branch-created.txt
  ```

  **Commit**: NO (설정 작업)

- [ ] 1. docs/09-viral-strategy.md 신규 작성 — 하꼬 영화 유튜버 바이럴 확산 전략 리서치

  **What to do**:
  - `docs/09-viral-strategy.md` 신규 파일 생성 (250~350줄 목표)
  - metadata header: `status: draft`, `last_updated: 2026-03-15`, `source: 웹 리서치 + .sisyphus/drafts/viral-strategy.md + Phase 4 에이전트 리서치`
  - **09 문서는 "바이럴 확산 전략 리서치"로 프레이밍** (마케팅 계획이 아님). 리서치 기반 분석 및 전략적 권고안 형태
  - 주요 섹션 구성:
    1. **개요** — 왜 하꼬 유튜버인가 (마이크로 인플루언서 ROI 데이터, Cinema on Air의 포지셔닝)
    2. **한국 영화 유튜버 생태계 분석** — 6개 서브카테고리 정의 및 분류:
       ① 줄거리 요약/리뷰 ② 분석/해설 ③ 촬영 브이로그 ④ 추천/큐레이션 ⑤ 영화제/독립영화 전문 ⑥ 라이프스타일
       각 카테고리별: 특성, 구독자 규모 분포, Cinema on Air 적합도 평가
    3. **타겟 유튜버 선별 기준** — Cinema on Air 최적 타겟: ② 분석/해설 + ⑤ 영화제/독립 전문 + ③ 촬영 브이로그
       구독자 규모 3단계 세분화:
       - 나노 (1K~5K): 특성, 접근 전략
       - 마이크로 (5K~20K): 특성, 접근 전략
       - 스몰 (20K~50K): 특성, 접근 전략
    4. **협업 모델 5가지**:
       A. 현금 광고비 (브랜디드 콘텐츠)
       B. 서비스 협찬 (프리미엄 구독권 + 선공개 접근권)
       C. 수익 쉐어 (레퍼럴 코드)
       D. 콘텐츠 공동제작 (**감독 인터뷰 접근권** — Cinema on Air 고유 자산으로 강조)
       E. 이벤트 초청 (시사회, 감독 Q&A)
    5. **비용 테이블** — 구독자 규모 × 협업 모델 매트릭스:
       | 구독자 | 비용 범위 | 추천 협업 모델 |
       나노 1K~5K: 0~30만원 + 구독권 협찬
       마이크로 5K~20K: 50~100만원 + 감독 인터뷰 기회
       스몰 20K~50K: 100~300만원 브랜디드
    6. **단계별 전략** — 3단계 타이밍:
       - **사전 홍보 (Pre-launch)**: 시딩, 얼리 액세스, 베타 테스터 모집
       - **런칭 (Launch)**: 동시다발 리뷰, 감독 인터뷰 시리즈, 프레스킷 배포
       - **성장 (Growth)**: 레퍼럴 프로그램, 월간 큐레이션 콜라보, 커뮤니티 앰배서더
    7. **피해야 할 패턴 (Anti-patterns)**:
       - 결말포함 요약 채널 (저작권 이슈 리스크)
       - MCN 소속 채널 (4.7배 프리미엄)
       - 영화와 무관한 라이프스타일 채널
    8. **핵심 전략 자산: 감독 인터뷰 접근권** — Cinema on Air만이 제공할 수 있는 차별적 가치
    9. **Pro Mode 연동 시사점** — 유튜버 협업이 Pro Mode 생태계와 어떻게 연결되는지
    10. **출처 및 참고 링크** — 모든 수치/주장의 출처 테이블
    11. **이 문서에 포함되지 않는 내용** — 명시적 배제 (일반 마케팅 계획, 유료 광고, PR 전략 등)
  - **모든 비용 수치**에 출처가 없으면 `[UNVERIFIED]` 마커 부착
  - 마이크로 인플루언서 ROI 578% 수치: "피처링 2024" 출처 기재 (URL 있으면 기재, 없으면 `[UNVERIFIED]`)
  - **교차참조**: `→ see docs/02-market-research.md`, `→ see docs/01-product-definition.md`, `→ see docs/08-decision-log.md ADR-006` 등

  **Must NOT do**:
  - 일반 마케팅/홍보 계획 작성 (유튜버 협업 리서치만)
  - SNS 전략, 유료 광고, PR/미디어 릴레이션 포함
  - 영어 섹션 헤더 사용
  - 추측성 사용자 여정 또는 가상 시나리오 작성
  - 출처 없는 수치를 [UNVERIFIED] 없이 기재

  **Recommended Agent Profile**:
  - **Category**: `unspecified-high`
    - Reason: 다양한 리서치 데이터를 종합하여 250~350줄 분량의 체계적인 기획 문서 작성 필요
  - **Skills**: []
  - **Skills Evaluated but Omitted**:
    - `coding-standards`: 코드 작성이 아닌 기획 문서이므로 불필요
    - `frontend-patterns`: 프론트엔드 개발과 무관

  **Parallelization**:
  - **Can Run In Parallel**: YES
  - **Parallel Group**: Wave 1 (with Tasks 2, 3)
  - **Blocks**: T4, T5
  - **Blocked By**: T0

  **References**:

  **Pattern References** (기존 문서 형식 따르기):
  - `docs/02-market-research.md:1-10` — metadata header 형식, 문서 구조 패턴 (status/last_updated/source 3줄 헤더)
  - `docs/infrastructure/06-funding.md:1-17` — 개요 섹션 작성 패턴 (핵심 수치 인용, 구조적 문제 제기)
  - `docs/infrastructure/06-funding.md:196-209` — 테이블 형식 패턴 (자격 요건 매트릭스 스타일)
  - `docs/02-market-research.md:154-159` — "이 문서에 포함되지 않는 내용" 섹션 작성 패턴
  - `docs/02-market-research.md:160-162` — 문서 말미 [DECIDED]/[OPEN] 마커 배치 패턴

  **Content References** (리서치 데이터):
  - `.sisyphus/drafts/viral-strategy.md:23-29` — 영화 유튜버 6개 카테고리 및 비용 데이터
  - `.sisyphus/drafts/viral-strategy.md:27` — "감독 인터뷰 접근권" 핵심 인사이트
  - `.sisyphus/drafts/viral-strategy.md:28` — 마이크로 인플루언서 ROI 578% 데이터

  **Cross-reference Targets** (교차참조 대상):
  - `docs/01-product-definition.md` — 플랫폼 포지셔닝 참조
  - `docs/02-market-research.md` — 경쟁 플랫폼 매트릭스 참조
  - `docs/08-decision-log.md:62-69` — ADR-006 (웹 우선 → 링크 공유 바이럴) 참조
  - `docs/infrastructure/00-index.md` — Pro Mode 생태계 연동 참조

  **External References**:
  - 랜딩페이지 카피: "유튜브에서 찾을 수 없는 단편영화" — 이 포지셔닝과 유튜버 전략의 시너지 설명 필요
  - H2 검증 채널: DC Inside 누벨바그, Twitter, Instagram, Naver Cafe (→ see docs/06-validation-plan.md)

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: 문서 구조 및 필수 섹션 확인
    Tool: Bash (grep)
    Steps:
      1. `head -5 docs/09-viral-strategy.md` — metadata header 확인
      2. `grep -c "^## " docs/09-viral-strategy.md` — H2 섹션 수 확인 (≥10)
      3. `grep "이 문서에 포함되지 않는 내용" docs/09-viral-strategy.md` — 배제 섹션 존재 확인
      4. `grep "감독 인터뷰 접근권" docs/09-viral-strategy.md` — 핵심 전략 자산 언급 확인
    Expected Result: metadata 존재, H2 ≥ 10개, 배제 섹션 존재, "감독 인터뷰 접근권" 1회 이상 언급
    Evidence: .sisyphus/evidence/task-1-doc-structure.txt

  Scenario: [UNVERIFIED] 비율 20% 미만 확인
    Tool: Bash
    Steps:
      1. `grep -c "UNVERIFIED" docs/09-viral-strategy.md` — UNVERIFIED 수
      2. `grep -cE "^[^|#>-]" docs/09-viral-strategy.md` — 대략적 주장 문장 수
      3. 비율 계산
    Expected Result: [UNVERIFIED] 마커 비율 < 20%
    Evidence: .sisyphus/evidence/task-1-unverified-ratio.txt

  Scenario: 줄 수 범위 확인
    Tool: Bash
    Steps:
      1. `wc -l docs/09-viral-strategy.md`
    Expected Result: 250~350줄 범위
    Evidence: .sisyphus/evidence/task-1-line-count.txt

  Scenario: 교차참조 유효성 확인
    Tool: Bash
    Steps:
      1. `grep -oP "→ see docs/[^\s)]*" docs/09-viral-strategy.md` — 모든 교차참조 추출
      2. 각 참조 대상 파일의 `ls` 확인
    Expected Result: 모든 교차참조 대상 파일이 실제 존재
    Evidence: .sisyphus/evidence/task-1-crossref-valid.txt
  ```

  **Commit**: YES
  - Message: `docs(#N): add viral marketing research with YouTuber collaboration strategy`
  - Files: `docs/09-viral-strategy.md`
  - Pre-commit: `wc -l docs/09-viral-strategy.md && head -5 docs/09-viral-strategy.md`

- [ ] 2. docs/10-indiground-analysis.md 신규 작성 — 인디그라운드 경쟁/파트너 양면 분석

  **What to do**:
  - `docs/10-indiground-analysis.md` 신규 파일 생성 (200~300줄 목표)
  - metadata header: `status: draft`, `last_updated: 2026-03-15`, `source: 웹 리서치 + .sisyphus/drafts/viral-strategy.md + indieground.kr`
  - **양면 분석 관점**: 경쟁 플랫폼으로서의 분석 + 잠재적 파트너로서의 가능성
  - 주요 섹션 구성:
    1. **개요** — 인디그라운드 정체 (영진위 설립 독립·예술영화 유통배급지원센터), URL, 설립 배경
    2. **9개 핵심 사업 영역** — 02-market-research.md의 9개와 일치시키기:
       ① 독립영화 라이브러리 ② 온라인 상영관 ③ 배급아카데미 ④ 1:1 배급상담소 ⑤ 공동체상영 지원 ⑥ 청소년 추천 독립영화 ⑦ 독립예술영화 DB ⑧ 비즈매칭 ⑨ 인디토크
       각 영역별: 운영 방식, 규모, 특징
    3. **핵심 서비스 심층 분석** — 라이브러리(92편, 단편 69편), 퍼스트링크(배급 매칭 80% 성공률), 배급아카데미(10주 무료 교육), 1:1 배급상담소(93% 만족도)
    4. **기술 및 UX 현황** — 웹사이트 중심, 레거시 기술, 팝업 방식 UX (02-market-research.md와 일관성)
    5. **Cinema on Air와의 비교 분석 테이블**:
       | 비교 항목 | 인디그라운드 | Cinema on Air |
       - 운영 주체 (공공 vs 민간)
       - 사업 모델 (B2B 배급매칭 vs B2C 직접 관객)
       - 콘텐츠 규모 (연 92편 선정 vs 무제한 업로드)
       - 아카이빙 (기간제 vs 영구)
       - 수익 모델 (공적 자금 vs 크리에이터 수익 공유)
       - 크리에이터 도구 (없음 vs 대시보드/프로필)
       - 소셜 레이어 (없음 vs 리뷰/평점/팔로우)
       - 모바일 앱 (없음 vs 웹 우선 반응형)
       - 글로벌 확장성 (한국어 전용 vs 글로벌 지향)
    6. **전략적 포지셔닝** — B2B(감독→배급사→극장) vs B2C(감독→관객 직접) 차이 분석
    7. **파트너십 가능성 분석**:
       - 콘텐츠 파이프라인: 인디그라운드 라이브러리 선정작 연계
       - 공동 상영: 인디그라운드 온라인 상영관 종료 후 Cinema on Air 아카이빙
       - 감독 네트워크: 배급아카데미/퍼스트링크 수료자 → Cinema on Air 얼리 어답터
       - 데이터 교류: 관객 지표 ↔ 배급 매칭 연계
       - 선례 참고: Wavve + 인디그라운드 협업 (2022년 독립영화 59편 OTT 최초 공개)
    8. **전략적 시사점** — Cinema on Air가 인디그라운드와 어떻게 상생할 수 있는지 종합
    9. **출처 및 참고 링크**
    10. **이 문서에 포함되지 않는 내용** — 일반 경쟁 플랫폼 매트릭스 (→ see docs/02-market-research.md)

  **Must NOT do**:
  - 일반 경쟁 분석 (02-market-research.md와 중복)
  - 02-market-research.md lines 52-81의 기존 인디그라운드 분석 내용과 모순
  - 인디그라운드를 단순 경쟁자로만 프레이밍 (양면 관점 필수)
  - 영어 섹션 헤더

  **Recommended Agent Profile**:
  - **Category**: `unspecified-high`
    - Reason: 경쟁 분석 + 파트너십 전략이라는 이중 관점의 체계적 기획 문서 작성 필요
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: YES
  - **Parallel Group**: Wave 1 (with Tasks 1, 3)
  - **Blocks**: T4, T5, T7
  - **Blocked By**: T0

  **References**:

  **Pattern References**:
  - `docs/02-market-research.md:52-81` — 기존 인디그라운드 분석 섹션 (9개 사업 영역 목록, 기술/UX 현황, 한계 분석). **이 내용과 모순 없이 심층 확장해야 함**
  - `docs/02-market-research.md:73-81` — "[DECIDED] 인디그라운드의 한계와 Cinema On Air의 기회" 8개 항목. 10-indiground-analysis.md에서 이들을 더 상세히 분석
  - `docs/infrastructure/06-funding.md:1-5` — metadata header 형식 참조
  - `docs/02-market-research.md:154-159` — "이 문서에 포함되지 않는 내용" 작성 패턴

  **Content References**:
  - `.sisyphus/drafts/viral-strategy.md:31-37` — 인디그라운드 리서치 결과 (정체, URL, 핵심 서비스, 전략적 판단)

  **External References**:
  - 인디그라운드 공식: https://indieground.kr
  - Wavve + 인디그라운드 협업 선례 (2022)

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: 문서 구조 및 양면 분석 확인
    Tool: Bash (grep)
    Steps:
      1. `head -5 docs/10-indiground-analysis.md` — metadata header 확인
      2. `grep "파트너" docs/10-indiground-analysis.md` — 파트너십 관점 존재 확인
      3. `grep "경쟁\|비교" docs/10-indiground-analysis.md` — 경쟁 분석 관점 존재 확인
      4. `grep "이 문서에 포함되지 않는 내용" docs/10-indiground-analysis.md` — 배제 섹션 존재 확인
    Expected Result: metadata 존재, 파트너 + 경쟁 양면 모두 언급, 배제 섹션 존재
    Evidence: .sisyphus/evidence/task-2-doc-structure.txt

  Scenario: 9개 사업 영역 일치 확인
    Tool: Bash (grep)
    Steps:
      1. `grep -c "라이브러리\|상영관\|배급아카데미\|배급상담소\|공동체상영\|청소년\|DB\|비즈매칭\|인디토크" docs/10-indiground-analysis.md`
    Expected Result: 9개 사업 영역 모두 언급 (카운트 ≥ 9)
    Evidence: .sisyphus/evidence/task-2-nine-services.txt

  Scenario: 02-market-research.md와 비모순 확인
    Tool: Bash
    Steps:
      1. `grep "92편\|장편 23\|단편 69" docs/10-indiground-analysis.md` — 핵심 수치 일치 확인
    Expected Result: 02-market-research.md의 "장편 23편, 단편 69편" 수치와 일치
    Evidence: .sisyphus/evidence/task-2-consistency.txt

  Scenario: 줄 수 범위 확인
    Tool: Bash
    Steps:
      1. `wc -l docs/10-indiground-analysis.md`
    Expected Result: 200~300줄 범위
    Evidence: .sisyphus/evidence/task-2-line-count.txt
  ```

  **Commit**: YES
  - Message: `docs(#N): add Indiground dual analysis (competitor + partner)`
  - Files: `docs/10-indiground-analysis.md`
  - Pre-commit: `wc -l docs/10-indiground-analysis.md && head -5 docs/10-indiground-analysis.md`

- [ ] 3. docs/infrastructure/06-funding.md 업데이트 — 제작지원사업 데이터 보강

  **What to do**:
  - 기존 `docs/infrastructure/06-funding.md` (282줄) 업데이트 (+80~120줄 추가, 총 360~400줄 목표)
  - `last_updated` → `2026-03-15` 변경
  - `source` 필드에 ` + Phase 4 에이전트 리서치` 추가
  - **기존 282줄 내용 100% 보존 (추가만, 삭제/수정 없음)**
  - 추가할 내용:
    1. **§2.2 (line 36~41) 업데이트**: "핵심 수치" blockquote에 단편 부문 13편→25편 (2배 확대) 반영
       - 기존: `> **핵심 수치**: 영진위 단편 부문 연간 선정 ~13편`
       - 변경: `> **핵심 수치**: 영진위 단편 부문 연간 선정 ~13편 → 2026년 25편으로 확대`
    2. **§2.4 (lines 53-58) AI 기반 영화 제작지원 확장**: 기존 3줄을 상세 테이블로 확장
       - 편당 지원금, 자격 요건, 접수 시기, 신인 접근성 평가 추가
    3. **§2.6 이후 신규 섹션 추가: §2.7 기획개발지원 (작가 부문)**
       - 85편 선정, 신인 작가 접근 가능
    4. **§5.1 CJ문화재단 스토리업 확장** (lines 129-139):
       - 현재 접수 중 정보 추가 (시기 민감 → "2026년 3월 기준" 명시)
       - 영화제작업신고증 불필요 명시
       - 단편 연출 경험만 필요 조건 강조
    5. **§5.2 기타 민간 지원 확장**:
       - 서울독립영화제 이강길 창작지원 (1천만원, 경력 무관) 추가
       - 서울독립영화제 후반제작지원 (현물) 추가
       - 미디액트 장비 현물 (200만원 상당, 상시 접수) 추가
    6. **§3 지역 기금에 추가**:
       - 인천스테이 (인천 기반 단편 지원) 추가
       - 전주 후반제작지원 확장 (전국 단편 1편 포함 상세)
       - 부산 다큐 개인신청 가능 정보 추가
    7. **§8 이후 신규 섹션: §8.3 영화제작업신고증 불필요 사업 종합표**
       - 7개 사업을 한눈에 볼 수 있는 종합 테이블:
         | 사업명 | 주관 | 지원 규모 | 자격 요건 | 접수 시기 | 신인 접근성 |
         CJ스토리업, 서울독립영화제 이강길, 영진위 시나리오공모, 미디액트 장비, 서울독립영화제 후반제작, 전주 후반제작, 인디그라운드 라이브러리
    8. **§10 출처 테이블 업데이트**: 새로 추가된 사업들의 출처 URL 추가
  - **시기 민감 정보**: "2026년 3월 기준" 또는 "현재 접수 중 (2026년 기준)" 형태로 명시

  **Must NOT do**:
  - 기존 282줄 중 어떤 내용도 삭제하지 않음
  - 기존 섹션 번호/구조 재배치하지 않음
  - 기존 테이블 데이터 변경하지 않음 (추가만)
  - 400줄 초과하지 않음

  **Recommended Agent Profile**:
  - **Category**: `unspecified-high`
    - Reason: 기존 282줄 문서에 정확하게 내용을 추가하면서 기존 구조를 보존해야 하는 세밀한 작업
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: YES
  - **Parallel Group**: Wave 1 (with Tasks 1, 2)
  - **Blocks**: T4, T6
  - **Blocked By**: T0

  **References**:

  **Pattern References**:
  - `docs/infrastructure/06-funding.md:1-282` — **전체 파일이 참조 대상**. 기존 구조를 정확히 이해하고 보존해야 함
  - `docs/infrastructure/06-funding.md:24-33` — §2.1 단편 부문 테이블 형식 (신규 테이블도 이 형식 따르기)
  - `docs/infrastructure/06-funding.md:196-209` — §8.1 자격 요건 매트릭스 형식 (§8.3 종합표도 이 형식 따르기)
  - `docs/infrastructure/06-funding.md:258-282` — §10 출처 테이블 형식 (새 출처 추가시 이 형식 따르기)
  - `docs/infrastructure/06-funding.md:129-139` — §5.1 CJ스토리업 기존 내용 (확장시 기존 정보 보존하며 추가)

  **Content References**:
  - `.sisyphus/drafts/viral-strategy.md:39-43` — 제작지원사업 리서치 결과 (AI영화, CJ스토리업 상세, 7개 신인 접근 사업)

  **External References**:
  - 영화진흥위원회: https://www.kofic.or.kr
  - CJ문화재단 스토리업: https://www.cjazit.org/support/story-up
  - 미디액트: https://www.mediact.org
  - 서울독립영화제: https://siff.kr

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: 기존 내용 보존 확인
    Tool: Bash
    Steps:
      1. `wc -l docs/infrastructure/06-funding.md` — 총 줄 수 확인 (282 이상)
      2. `grep "자격 증명 함정" docs/infrastructure/06-funding.md` — 기존 핵심 개념 보존 확인
      3. `grep "Credentialing Trap" docs/infrastructure/06-funding.md` — 영어 용어 보존 확인
    Expected Result: 줄 수 ≥ 360, 기존 핵심 내용 모두 보존
    Evidence: .sisyphus/evidence/task-3-preservation.txt

  Scenario: 신규 내용 추가 확인
    Tool: Bash
    Steps:
      1. `grep "영화제작업신고증 불필요" docs/infrastructure/06-funding.md` — 종합표 존재 확인
      2. `grep "미디액트" docs/infrastructure/06-funding.md` — 미디액트 추가 확인
      3. `grep "이강길" docs/infrastructure/06-funding.md` — 서울독립영화제 이강길 추가 확인
      4. `grep "인천" docs/infrastructure/06-funding.md` — 인천스테이 추가 확인
    Expected Result: 모든 신규 항목이 문서에 존재
    Evidence: .sisyphus/evidence/task-3-new-content.txt

  Scenario: 줄 수 범위 확인
    Tool: Bash
    Steps:
      1. `wc -l docs/infrastructure/06-funding.md`
    Expected Result: 360~400줄 범위
    Evidence: .sisyphus/evidence/task-3-line-count.txt

  Scenario: 출처 테이블 업데이트 확인
    Tool: Bash
    Steps:
      1. `grep "mediact\|siff\|cjazit" docs/infrastructure/06-funding.md` — 새 출처 URL 존재 확인
    Expected Result: 신규 출처 URL 3개 이상 추가
    Evidence: .sisyphus/evidence/task-3-sources.txt
  ```

  **Commit**: YES
  - Message: `docs(#N): expand funding docs with AI film support and newcomer-accessible programs`
  - Files: `docs/infrastructure/06-funding.md`
  - Pre-commit: `wc -l docs/infrastructure/06-funding.md`

- [ ] 4. docs/00-index.md 업데이트 — 09/10 문서 행 추가, 마커 카운트 업데이트, 배제 조항 수정

  **What to do**:
  - `docs/00-index.md` (114줄) 업데이트
  - `last_updated` → `2026-03-15` 변경
  - **3가지 변경 사항**:
    1. **문서 구조 테이블 (lines 17-28)에 2행 추가**:
       - `| [09-viral-strategy.md](./09-viral-strategy.md) | 바이럴 확산 전략 리서치 | 하꼬 영화 유튜버 협업 전략, 비용 분석, 단계별 확산 방안 | draft |`
       - `| [10-indiground-analysis.md](./10-indiground-analysis.md) | 인디그라운드 분석 | 인디그라운드 경쟁/파트너 양면 분석, Cinema on Air 비교 | draft |`
       - 위치: infrastructure/00-index.md 행 바로 위에 삽입
    2. **마커 현황 테이블 (lines 35-52) 업데이트**:
       - 09-viral-strategy.md, 10-indiground-analysis.md 행 추가 (실제 마커 수 반영)
       - 합계 행 업데이트
    3. **배제 조항 (line 114) 수정**:
       - 기존: `- 마케팅 및 홍보 계획`
       - 변경: `- 마케팅 및 홍보 실행 계획 (→ 바이럴 확산 전략 리서치는 docs/09-viral-strategy.md 참조)`
       - 이유: 09는 "리서치"이지 "실행 계획"이 아님을 명확히

  **Must NOT do**:
  - 기존 문서 행 수정/삭제
  - 핵심 결정 사항 Top 5 수정
  - 다음 단계 섹션 수정

  **Recommended Agent Profile**:
  - **Category**: `quick`
    - Reason: 기존 파일에 행 추가 + 숫자 업데이트 수준의 단순 편집
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: YES
  - **Parallel Group**: Wave 2 (with Tasks 5, 6, 7)
  - **Blocks**: T8
  - **Blocked By**: T1, T2, T3 (마커 카운트 산출을 위해 신규 문서 완성 필요)

  **References**:
  - `docs/00-index.md:17-28` — 문서 구조 테이블 (행 추가 위치)
  - `docs/00-index.md:35-52` — 마커 현황 테이블 (카운트 업데이트)
  - `docs/00-index.md:111-114` — 배제 조항 (수정 대상)
  - `docs/09-viral-strategy.md` — [DECIDED]/[OPEN] 마커 카운트 산출 (T1 완료 후)
  - `docs/10-indiground-analysis.md` — [DECIDED]/[OPEN] 마커 카운트 산출 (T2 완료 후)

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: 문서 테이블에 09, 10 행 존재 확인
    Tool: Bash (grep)
    Steps:
      1. `grep "09-viral-strategy" docs/00-index.md`
      2. `grep "10-indiground-analysis" docs/00-index.md`
    Expected Result: 두 행 모두 존재
    Evidence: .sisyphus/evidence/task-4-index-rows.txt

  Scenario: 배제 조항 수정 확인
    Tool: Bash (grep)
    Steps:
      1. `grep "마케팅" docs/00-index.md`
    Expected Result: "마케팅 및 홍보 실행 계획" (실행 추가됨)
    Evidence: .sisyphus/evidence/task-4-exclusion-fix.txt
  ```

  **Commit**: NO (T7과 함께 Commit 4로 통합)

- [ ] 5. docs/02-market-research.md 업데이트 — 인디그라운드 심층 분석 교차참조 추가

  **What to do**:
  - `docs/02-market-research.md` (162줄) 업데이트
  - `last_updated` → `2026-03-15` 변경
  - **변경 사항**:
    1. **섹션 2 제목 또는 하단에 교차참조 추가**:
       - lines 52-81 인디그라운드 분석 섹션 하단에: `> 인디그라운드의 심층 분석(경쟁/파트너 양면 분석)은 → see docs/10-indiground-analysis.md 참조.`
    2. **기존 내용 수정 없음** — 교차참조 한 줄 추가만

  **Must NOT do**:
  - 기존 인디그라운드 분석 내용 (lines 52-81) 수정
  - 다른 섹션 수정
  - 새로운 분석 내용 추가

  **Recommended Agent Profile**:
  - **Category**: `quick`
    - Reason: 교차참조 1줄 추가
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: YES
  - **Parallel Group**: Wave 2 (with Tasks 4, 6, 7)
  - **Blocks**: T8
  - **Blocked By**: T2

  **References**:
  - `docs/02-market-research.md:52-81` — 인디그라운드 분석 섹션 (교차참조 추가 위치)
  - `docs/10-indiground-analysis.md` — 교차참조 대상 (T2 완료 후)

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: 교차참조 추가 확인
    Tool: Bash (grep)
    Steps:
      1. `grep "10-indiground-analysis" docs/02-market-research.md`
    Expected Result: 교차참조 1회 이상 존재
    Evidence: .sisyphus/evidence/task-5-crossref.txt

  Scenario: 기존 내용 보존 확인
    Tool: Bash
    Steps:
      1. `grep "9개 핵심 사업 영역" docs/02-market-research.md`
    Expected Result: 기존 "9개 핵심 사업 영역" 문구 보존
    Evidence: .sisyphus/evidence/task-5-preservation.txt
  ```

  **Commit**: NO (T7과 함께 Commit 4로 통합)

- [ ] 6. docs/infrastructure/00-index.md 업데이트 — 06-funding.md 줄 수/설명 업데이트

  **What to do**:
  - `docs/infrastructure/00-index.md` (124줄) 업데이트
  - `last_updated` → `2026-03-15` 변경
  - **변경 사항**:
    1. **인프라 카테고리 테이블 (line 26)에서 06-funding.md 행 업데이트**:
       - 줄 수: 282 → 실제 `wc -l` 결과로 변경
       - 설명에 "AI 기반 영화 제작지원, 영화제작업신고증 불필요 사업 종합" 추가
    2. **총 줄 수 (line 29) 업데이트**: 1,677 → 실제 합산 줄 수로 변경

  **Must NOT do**:
  - 다른 카테고리 행 수정
  - Pro Mode 연동 섹션 수정
  - 메타데이터 섹션 외 기타 내용 수정

  **Recommended Agent Profile**:
  - **Category**: `quick`
    - Reason: 숫자 2개 + 설명 문구 1개 업데이트
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: YES
  - **Parallel Group**: Wave 2 (with Tasks 4, 5, 7)
  - **Blocks**: T8
  - **Blocked By**: T3 (06-funding.md 최종 줄 수 확인 필요)

  **References**:
  - `docs/infrastructure/00-index.md:19-29` — 인프라 카테고리 테이블 (업데이트 대상)
  - `docs/infrastructure/06-funding.md` — 최종 줄 수 산출 (T3 완료 후 `wc -l`)

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: 줄 수 정확성 확인
    Tool: Bash
    Steps:
      1. 실제 `wc -l docs/infrastructure/06-funding.md` 결과와 00-index.md 테이블의 숫자 비교
    Expected Result: 일치
    Evidence: .sisyphus/evidence/task-6-linecount-match.txt
  ```

  **Commit**: NO (T7과 함께 Commit 4로 통합)

- [ ] 7. docs/08-decision-log.md 업데이트 — ADR-014 추가

  **What to do**:
  - `docs/08-decision-log.md` (178줄) 업데이트
  - `last_updated` → `2026-03-15` 변경
  - **변경 사항**:
    1. **결정 요약 (line 12) 업데이트**: DECIDED: 13개 → 14개
    2. **ADR-013 뒤 (line 134)에 ADR-014 추가**:
       ```
       ### ADR-014: 인디그라운드(Indieground) 전략적 포지셔닝
       - **상태**: [DECIDED]
       - **결정**: 인디그라운드를 경쟁자가 아닌 잠재적 파트너로 포지셔닝하며, 보완적 역할 분담(B2B 배급매칭 vs B2C 직접 관객)을 지향한다.
       - **컨텍스트**: 인디그라운드는 영진위 산하 공공기관으로 독립영화 유통배급을 지원하지만, 영구 아카이빙, 크리에이터 수익화, 소셜 레이어, 모바일 앱 등은 제공하지 않는다.
       - **대안**: 인디그라운드를 순수 경쟁자로 간주하고 차별화에만 집중.
       - **근거**: 인디그라운드=B2B(감독→배급사→극장), Cinema on Air=B2C(감독→관객 직접)로 사업 모델이 상이하며, Wavve+인디그라운드 협업(2022) 선례가 파트너십 가능성을 입증.
       - **소스**: Phase 4 에이전트 리서치 (2026-03-15)
       - **관련 문서**: [→ see docs/10-indiground-analysis.md], [→ see docs/02-market-research.md]
       ```

  **Must NOT do**:
  - 기존 ADR 001-013 수정
  - OPEN 항목 수정
  - 기존 DECIDED 카운트를 잘못 반영

  **Recommended Agent Profile**:
  - **Category**: `quick`
    - Reason: ADR 1개 추가 + 카운트 1개 업데이트
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: YES
  - **Parallel Group**: Wave 2 (with Tasks 4, 5, 6)
  - **Blocks**: T8
  - **Blocked By**: T2 (인디그라운드 분석 내용 기반)

  **References**:
  - `docs/08-decision-log.md:126-134` — ADR-013 형식 (동일 패턴으로 ADR-014 작성)
  - `docs/08-decision-log.md:11-13` — 결정 요약 카운트 (업데이트 대상)
  - `docs/10-indiground-analysis.md` — ADR-014 근거 문서 (T2 완료 후)

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: ADR-014 존재 및 형식 확인
    Tool: Bash (grep)
    Steps:
      1. `grep "ADR-014" docs/08-decision-log.md`
      2. `grep "DECIDED.*14" docs/08-decision-log.md`
    Expected Result: ADR-014 존재, DECIDED 카운트 14
    Evidence: .sisyphus/evidence/task-7-adr014.txt

  Scenario: 기존 ADR 보존 확인
    Tool: Bash (grep)
    Steps:
      1. `grep -c "### ADR-" docs/08-decision-log.md`
    Expected Result: ADR 개수 ≥ 19 (DECIDED 14 + OPEN 5)
    Evidence: .sisyphus/evidence/task-7-adr-count.txt
  ```

  **Commit**: YES (T4, T5, T6과 통합)
  - Message: `docs(#N): update indexes and cross-references for Phase 4 documents`
  - Files: `docs/00-index.md`, `docs/02-market-research.md`, `docs/infrastructure/00-index.md`, `docs/08-decision-log.md`
  - Pre-commit: `grep "09-viral" docs/00-index.md && grep "ADR-014" docs/08-decision-log.md`

- [ ] 8. 종합 검증 + Push + PR 생성

  **What to do**:
  - **종합 검증**:
    1. 모든 신규/수정 파일 존재 확인 (`ls`)
    2. 줄 수 확인 (09: 250~350, 10: 200~300, 06: 360~400)
    3. metadata header 확인 (모든 파일에 status/last_updated/source)
    4. [UNVERIFIED] 비율 확인 (각 문서 20% 미만)
    5. 교차참조 유효성 확인 (모든 `→ see docs/XX` 대상 파일 존재)
    6. git diff 확인 (예상 변경 파일 7개)
  - **Push**:
    ```bash
    git remote set-url origin "https://$(gh auth token)@github.com/dead-pool-aka-wilson/cinema-on-air.git"
    git push -u origin HEAD
    ```
  - **PR 생성**:
    ```bash
    gh pr create --title "docs(#N): Phase 4 viral strategy + Indiground analysis + funding update" --body "..."
    ```
    - PR body에 체크리스트 포함: 7개 파일, 각 변경 요약

  **Must NOT do**:
  - main 브랜치에 직접 push
  - force push
  - PR 없이 merge

  **Recommended Agent Profile**:
  - **Category**: `quick`
    - Reason: CLI 검증 명령 + push + PR 생성
  - **Skills**: [`git-master`]
    - `git-master`: Git push 및 PR 생성

  **Parallelization**:
  - **Can Run In Parallel**: NO (최종 단계)
  - **Parallel Group**: Wave 3 (단독)
  - **Blocks**: F1-F4
  - **Blocked By**: T4, T5, T6, T7

  **References**:
  - Phase 3 PR: `gh pr view 6` — 기존 PR 형식 참조
  - 모든 이전 태스크 산출물

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: PR 생성 확인
    Tool: Bash
    Steps:
      1. `gh pr list --state open --limit 5`
    Expected Result: Phase 4 관련 PR이 open 상태로 존재
    Evidence: .sisyphus/evidence/task-8-pr-created.txt

  Scenario: 커밋 형식 확인
    Tool: Bash
    Steps:
      1. `git log --oneline -5`
    Expected Result: 모든 커밋이 `docs(#N): ...` 형식
    Evidence: .sisyphus/evidence/task-8-commit-format.txt

  Scenario: 변경 파일 수 확인
    Tool: Bash
    Steps:
      1. `git diff main --name-only`
    Expected Result: 7개 파일 (09, 10 신규 + 06, 00-index, 02, infra-00-index, 08 수정)
    Evidence: .sisyphus/evidence/task-8-changed-files.txt
  ```

  **Commit**: NO (이미 커밋 완료 상태)

---

## Final Verification Wave (MANDATORY — after ALL implementation tasks)

> 4 review agents run in PARALLEL. ALL must APPROVE. Rejection → fix → re-run.

- [ ] F1. **Plan Compliance Audit** — `oracle`
  Read the plan end-to-end. For each "Must Have": verify implementation exists (read file, check section headers). For each "Must NOT Have": search documents for forbidden patterns — reject with file:line if found. Check evidence files exist in .sisyphus/evidence/. Compare deliverables against plan.
  Output: `Must Have [N/N] | Must NOT Have [N/N] | Tasks [N/N] | VERDICT: APPROVE/REJECT`

- [ ] F2. **Document Quality Review** — `unspecified-high`
  Review all new/modified documents for: metadata header completeness, consistent heading levels (H1 title only, H2 sections, H3 subsections), Korean language consistency, table formatting, [UNVERIFIED] marker presence where needed, source citations. Check AI slop: excessive repetition, generic filler text, over-abstraction.
  Output: `Docs [N clean/N issues] | Headers [PASS/FAIL] | Tables [PASS/FAIL] | VERDICT`

- [ ] F3. **Cross-reference Integrity Check** — `unspecified-high`
  For every `→ see docs/XX` reference in ALL 7 files: verify target file exists and target section/anchor exists. Check 00-index.md document table matches actual file list. Check 00-index.md marker counts match actual counts in each document. Check infrastructure/00-index.md line counts match actual `wc -l` output.
  Output: `References [N/N valid] | Index [PASS/FAIL] | Line Counts [PASS/FAIL] | VERDICT`

- [ ] F4. **Scope Fidelity Check** — `deep`
  For each task: read "What to do", read actual file content. Verify 1:1 — everything in spec was built (no missing), nothing beyond spec was built (no creep). Check "Must NOT do" compliance. Verify 06-funding.md has zero deletions from original 282-line content. Flag unaccounted changes.
  Output: `Tasks [N/N compliant] | No Creep [CLEAN/N issues] | Original Preserved [YES/NO] | VERDICT`

---

## Commit Strategy

- **Commit 1** (after T1): `docs(#N): add viral marketing research with YouTuber collaboration strategy`
  - Files: `docs/09-viral-strategy.md`
- **Commit 2** (after T2): `docs(#N): add Indiground dual analysis (competitor + partner)`
  - Files: `docs/10-indiground-analysis.md`
- **Commit 3** (after T3): `docs(#N): expand funding docs with AI film support and newcomer-accessible programs`
  - Files: `docs/infrastructure/06-funding.md`
- **Commit 4** (after T4-T7): `docs(#N): update indexes and cross-references for Phase 4 documents`
  - Files: `docs/00-index.md`, `docs/02-market-research.md`, `docs/infrastructure/00-index.md`, `docs/08-decision-log.md`

---

## Success Criteria

### Verification Commands
```bash
# 신규 문서 존재 확인
ls -la docs/09-viral-strategy.md docs/10-indiground-analysis.md

# 줄 수 확인 (09: 250~350, 10: 200~300, 06: 360~400)
wc -l docs/09-viral-strategy.md docs/10-indiground-analysis.md docs/infrastructure/06-funding.md

# metadata header 확인
head -5 docs/09-viral-strategy.md docs/10-indiground-analysis.md

# [UNVERIFIED] 비율 확인 (각 문서 20% 미만)
grep -c "UNVERIFIED" docs/09-viral-strategy.md
grep -c "UNVERIFIED" docs/10-indiground-analysis.md

# 교차참조 유효성 확인
grep -o "→ see docs/[^ )]*" docs/09-viral-strategy.md docs/10-indiground-analysis.md

# 06-funding.md 기존 내용 보존 확인 (원본 282줄 이상)
wc -l docs/infrastructure/06-funding.md

# 00-index.md에 09, 10 행 존재 확인
grep "09-viral" docs/00-index.md
grep "10-indiground" docs/00-index.md

# git log 확인
git log --oneline -5
```

### Final Checklist
- [ ] 7개 파일 모두 수정/생성됨
- [ ] 모든 "Must Have" 항목 문서에 존재
- [ ] 모든 "Must NOT Have" 항목 문서에 부재
- [ ] 06-funding.md 원본 282줄 내용 100% 보존
- [ ] PR 생성 완료
