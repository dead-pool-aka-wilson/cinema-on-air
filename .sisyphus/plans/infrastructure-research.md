# 한국 독립영화 단편영화 제작 인프라 조사 및 Pro Mode 생태계 기반 구축

## TL;DR

> **Quick Summary**: ADR-009를 폐기하고 Cinema on Air를 "Pro Mode(크리에이터) / Enjoy Mode(관객)" Two-sided App으로 확장한다. 이를 위해 한국 독립영화/단편영화 제작에 필요한 7개 인프라 카테고리(장비, 장소, 인력, 후반, 교육, 자금, 법적/행정)를 체계적으로 조사하고 카테고리별 독립 문서로 정리한다.
>
> **Deliverables**:
> - ADR-009 폐기 + ADR-013 신설 (Pro Mode/Enjoy Mode Two-sided App)
> - docs/01-product-definition.md 업데이트 (Scope Boundaries, 타겟 사용자, 가치 제안 확장)
> - docs/04-creator-insights.md 결정 마커 업데이트
> - docs/00-index.md 인프라 섹션 추가
> - docs/infrastructure/00-index.md (인프라 마스터 인덱스)
> - docs/infrastructure/01-equipment-rental.md (장비 렌탈)
> - docs/infrastructure/02-filming-locations.md (촬영 장소)
> - docs/infrastructure/03-crew-casting.md (인력/캐스팅)
> - docs/infrastructure/04-post-production.md (후반작업)
> - docs/infrastructure/05-education-workshop.md (교육/워크숍)
> - docs/infrastructure/06-funding.md (자금/펀딩)
> - docs/infrastructure/07-legal-admin.md (법적/행정)
>
> **Estimated Effort**: Large
> **Parallel Execution**: YES — 3 waves
> **Critical Path**: Task 1(ADR 변경) → Task 2(제품정의 업데이트) → Tasks 4-10(인프라 리서치, 병렬) → Task 11(인덱스) → Task 12(검증)

---

## Context

### Original Request
"한국에서 독립영화 단편영화를 촬영하기 위해서 필요한 인프라들에 대한 정보를 최대한 많이 수집하기 위한 계획을 세워"

### Interview Summary
**Key Discussions**:
- **조사 목적**: 플랫폼 기획 보강 + 생태계 이해 심화 + 인프라 연동 검토 (3가지 전부 선택)
- **인프라 범위**: 7개 카테고리 전부 조사 (장비/장소/인력/후반/교육/자금/법적행정)
- **산출물 형식**: 카테고리별 분리 문서
- **핵심 비전**: "영화를 본 사람들은 또 영화를 만들 사람일 확률이 높음. 그래서 영화를 찍은 장소, 장비, 인력, 배급 등을 연계해서 하나의 생태계를 만들어야 함. 서비스는 투 사이드 앱 — **Pro Mode**(감독/크리에이터)와 **Enjoy Mode**(관객)로 나뉨"
- **ADR-009 폐기**: 기존 "만든 후의 플랫폼, 제작 도구 제외" 결정 폐기 → Pro Mode에서 제작 인프라를 플랫폼에 직접 연계

**Research Findings**:
- docs/04-creator-insights.md에 시청자미디어센터(63개소), 필름메이커스(8,638+ 포스트) 등 일부 인프라 데이터가 이미 존재
- .sisyphus/drafts/cinema-on-air-research.md §20에 아마추어 감독 Case Study — 장비(중고구매→재판매), 장소(수십군데 거절→공공시설), 인력(필름메이커스 서울중심), 후반(새벽 주차장 후시녹음) 등 1차 데이터 확보
- 영진위 제작지원 단편 부문 총예산 4억원, 편당 최대 3천만원, 전국 ~13편 선정

### Metis Review
**Identified Gaps** (addressed):
- **ADR-009 폐기의 연쇄 영향**: docs/01, docs/04, docs/08, docs/00 최소 4개 파일 업데이트 필요 → Wave 1에 구조적 변경 태스크로 선행 배치
- **"최대한 많이"의 종료 조건**: 카테고리별 정량적 수락 기준(최소 항목 수, 최소 출처 수) 필요 → 각 태스크 Acceptance Criteria에 명시
- **AI 환각 차단**: `[UNVERIFIED]` 마커 정책 + 출처 URL/기관명 필수 → Must NOT Have에 가드레일 설정
- **Phase A/B 분리**: 구조적 변경(ADR/제품정의) 먼저, 리서치 실행은 그 다음 → Wave 순서로 반영

---

## Work Objectives

### Core Objective
ADR-009를 폐기하여 Cinema on Air의 서비스 범위를 "Pro Mode/Enjoy Mode" Two-sided App으로 확장하고, Pro Mode의 핵심 데이터가 될 한국 독립영화/단편영화 제작 인프라 7개 카테고리를 체계적으로 조사하여 카테고리별 독립 문서로 정리한다.

### Concrete Deliverables
- docs/08-decision-log.md: ADR-009 상태를 `[SUPERSEDED]`로 변경, ADR-013 신설
- docs/01-product-definition.md: 섹션 8 Scope Boundaries 업데이트, Pro Mode/Enjoy Mode 개념 반영
- docs/04-creator-insights.md: 결정 마커 업데이트
- docs/00-index.md: 인프라 문서 섹션 추가
- docs/infrastructure/ 디렉토리 하위 8개 문서 (인덱스 + 7개 카테고리)

### Definition of Done
- [ ] ADR-009가 `[SUPERSEDED]`이고 ADR-013이 `[DECIDED]`로 존재
- [ ] docs/01-product-definition.md Scope Boundaries에서 캐스팅/장소/장비가 IN으로 이동
- [ ] docs/infrastructure/ 디렉토리에 8개 .md 파일 존재
- [ ] 각 인프라 문서가 최소 80줄 이상, 최소 5개 실명 기관/서비스 포함
- [ ] 모든 수치/주장에 출처(URL, 기관명, 날짜) 명시
- [ ] 교차참조 무결 (존재하지 않는 문서 링크 없음)
- [ ] docs/00-index.md에 infrastructure/ 문서 목록 반영

### Must Have
- 모든 문서 한국어 작성 (기술 용어 영어 병기 허용)
- 문서 메타데이터 헤더: `status`, `last_updated`, `source`
- 결정 마커: `[DECIDED]` / `[OPEN]` / `[HYPOTHESIS]` / `[SUPERSEDED]`
- 교차 참조: `→ see docs/XX-name.md`
- 각 인프라 문서에 "Pro Mode 연동 시사점" 섹션 포함
- `[UNVERIFIED]` 마커: 출처를 찾지 못한 수치/주장에 반드시 표시
- 카테고리당 최소 5개 실명 기관/서비스/채널 조사
- 카테고리당 최소 3개 출처(URL 또는 기관 공식 정보)

### Must NOT Have (Guardrails)
- 출처 없는 수치/비용/통계 창작 금지 — 확인 불가 시 `[UNVERIFIED]` 마커 사용
- 개발 코드 포함 금지 (기획 문서만)
- 영어 전용 문서 금지 (한국어 필수)
- 인프라 문서에 플랫폼 기능 설계/와이어프레임 포함 금지 (리서치만, 설계는 별도 Phase)
- 기존 확정된 ADR(001-008, 010-012) 변경 금지 (009만 폐기)
- docs/validation/ 디렉토리 문서 수정 금지
- "마켓플레이스 기능 설계", "DB 스키마", "API 엔드포인트" 등 구현 수준 내용 금지

---

## Verification Strategy

> **ZERO HUMAN INTERVENTION** — ALL verification is agent-executed. No exceptions.

### Test Decision
- **Infrastructure exists**: NO (기획 문서 프로젝트, 코드 테스트 불필요)
- **Automated tests**: None
- **Framework**: none

### QA Policy
Every task MUST include agent-executed QA scenarios.
Evidence saved to `.sisyphus/evidence/task-{N}-{scenario-slug}.{ext}`.

- **문서 검증**: Bash (wc -l, grep) — 줄 수 확인, 필수 섹션 존재 확인, 마커 검증
- **교차참조 검증**: Bash (grep + ls) — 참조된 파일이 실제 존재하는지 확인
- **출처 검증**: Grep — `[UNVERIFIED]` 없는 수치에 출처 URL/기관명이 있는지 확인

---

## Execution Strategy

### Parallel Execution Waves

```
Wave 1 (Start Immediately — 구조적 변경):
├── Task 1: ADR-009 폐기 + ADR-013 신설 (docs/08-decision-log.md) [quick]
├── Task 2: docs/01-product-definition.md Pro Mode/Enjoy Mode 반영 [quick]
└── Task 3: docs/04-creator-insights.md 결정 마커 업데이트 [quick]

Wave 2 (After Wave 1 — 인프라 리서치, MAX PARALLEL):
├── Task 4: 장비 렌탈 리서치 (docs/infrastructure/01-equipment-rental.md) [unspecified-high]
├── Task 5: 촬영 장소 리서치 (docs/infrastructure/02-filming-locations.md) [unspecified-high]
├── Task 6: 인력/캐스팅 리서치 (docs/infrastructure/03-crew-casting.md) [unspecified-high]
├── Task 7: 후반작업 리서치 (docs/infrastructure/04-post-production.md) [unspecified-high]
├── Task 8: 교육/워크숍 리서치 (docs/infrastructure/05-education-workshop.md) [unspecified-high]
├── Task 9: 자금/펀딩 리서치 (docs/infrastructure/06-funding.md) [unspecified-high]
└── Task 10: 법적/행정 리서치 (docs/infrastructure/07-legal-admin.md) [unspecified-high]

Wave 3 (After Wave 2 — 인덱스 + 검증):
├── Task 11: docs/infrastructure/00-index.md + docs/00-index.md 업데이트 [quick]
└── Task 12: 전체 검증 (교차참조, 줄 수, 출처, 마커) [unspecified-high]

Wave FINAL (After ALL tasks — 독립 리뷰, 4 parallel):
├── Task F1: Plan compliance audit (oracle)
├── Task F2: Code quality review — 문서 품질 리뷰 (unspecified-high)
├── Task F3: Real manual QA — 전체 교차참조/출처 재검증 (unspecified-high)
└── Task F4: Scope fidelity check (deep)

Critical Path: Task 1 → Task 2 → Tasks 4-10 (병렬) → Task 11 → Task 12 → F1-F4
Parallel Speedup: ~60% (Wave 2에서 7개 병렬)
Max Concurrent: 7 (Wave 2)
```

### Dependency Matrix

| Task | Depends On | Blocks | Wave |
|:---|:---|:---|:---|
| 1 (ADR 변경) | — | 2, 3, 4-10 | 1 |
| 2 (제품정의 업데이트) | 1 | 4-10 | 1 |
| 3 (크리에이터 마커) | 1 | 11 | 1 |
| 4-10 (인프라 리서치 7개) | 1, 2 | 11 | 2 |
| 11 (인덱스 업데이트) | 3, 4-10 | 12 | 3 |
| 12 (전체 검증) | 11 | F1-F4 | 3 |
| F1-F4 (최종 리뷰) | 12 | — | FINAL |

### Agent Dispatch Summary

- **Wave 1**: **3** — T1-T3 → `quick`
- **Wave 2**: **7** — T4-T10 → `unspecified-high`
- **Wave 3**: **2** — T11 → `quick`, T12 → `unspecified-high`
- **FINAL**: **4** — F1 → `oracle`, F2 → `unspecified-high`, F3 → `unspecified-high`, F4 → `deep`

---

## TODOs

- [ ] 1. ADR-009 폐기 + ADR-013 신설

  **What to do**:
  - docs/08-decision-log.md에서 ADR-009 상태를 `[SUPERSEDED]`로 변경
  - ADR-009에 "폐기 사유" 필드 추가: "Pro Mode/Enjoy Mode Two-sided App 전환으로 제작 인프라를 플랫폼 범위에 포함. ADR-013으로 대체."
  - ADR-013 신설:
    - **상태**: [DECIDED]
    - **결정**: Cinema on Air를 "Pro Mode(감독/크리에이터)"와 "Enjoy Mode(관객)"의 Two-sided App으로 구성하며, 제작 인프라(장비, 장소, 인력, 후반, 교육, 자금, 법적/행정)를 플랫폼 생태계에 직접 연계한다.
    - **컨텍스트**: 영화를 본 관객이 제작자가 될 확률이 높으며, 촬영 장소/장비/인력/배급 정보를 연계하여 관객→제작자 전환을 유도하는 순환 생태계가 필요하다.
    - **대안**: 기존 ADR-009 유지 (배급/발견만 집중)
    - **근거**: 사용자 인터뷰 — "영화를 본 사람들은 또 영화를 만들 사람일 확률이 높음"
    - **소스**: Phase 3 인터뷰 (2026-03-14)
    - **관련 문서**: → see docs/01-product-definition.md, → see docs/infrastructure/00-index.md
  - 문서 상단 "결정 요약"의 DECIDED 카운트를 13으로 업데이트
  - 문서 메타데이터 `last_updated`를 오늘 날짜로 변경

  **Must NOT do**:
  - 기존 ADR-001~008, ADR-010~012 내용 변경 금지
  - ADR-OPEN 항목 변경 금지

  **Recommended Agent Profile**:
  - **Category**: `quick`
    - Reason: 단일 파일의 명확한 수정 작업
  - **Skills**: []
  - **Skills Evaluated but Omitted**:
    - `coding-standards`: 코드가 아닌 마크다운 문서 작업

  **Parallelization**:
  - **Can Run In Parallel**: YES (with Tasks 2, 3)
  - **Parallel Group**: Wave 1
  - **Blocks**: Tasks 4-10
  - **Blocked By**: None (can start immediately)

  **References**:

  **Pattern References**:
  - `docs/08-decision-log.md:89-96` — ADR-009 현재 내용 (SUPERSEDED로 변경할 대상)
  - `docs/08-decision-log.md:98-105` — ADR-010 형식 참고 (동일 ADR 형식 유지)
  - `docs/08-decision-log.md:11-13` — 결정 요약 카운트 (업데이트 대상)

  **External References**:
  - Phase 3 인터뷰 답변: "영화를 본 사람들은 또 영화를 만들 사람일 확률이 높음. 프로모드랑 인조이 모드로 나뉨"

  **WHY Each Reference Matters**:
  - ADR-009 위치를 정확히 알아야 SUPERSEDED로 변경 가능
  - 기존 ADR 형식을 따라야 문서 일관성 유지
  - 결정 요약 카운트가 실제 ADR 수와 일치해야 함

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: ADR-009 SUPERSEDED 확인
    Tool: Bash (grep)
    Preconditions: docs/08-decision-log.md 파일 존재
    Steps:
      1. grep "SUPERSEDED" docs/08-decision-log.md
      2. grep -A2 "ADR-009" docs/08-decision-log.md 에서 상태 확인
    Expected Result: ADR-009 행에 [SUPERSEDED] 마커 존재
    Failure Indicators: [DECIDED] 상태가 그대로이거나 ADR-009가 삭제됨
    Evidence: .sisyphus/evidence/task-1-adr009-superseded.txt

  Scenario: ADR-013 DECIDED 존재 확인
    Tool: Bash (grep)
    Preconditions: Task 1 완료
    Steps:
      1. grep "ADR-013" docs/08-decision-log.md
      2. grep -A5 "ADR-013" docs/08-decision-log.md 에서 Pro Mode/Enjoy Mode 언급 확인
    Expected Result: ADR-013이 [DECIDED] 상태로 존재, "Pro Mode" 및 "Enjoy Mode" 문자열 포함
    Failure Indicators: ADR-013이 없거나 상태가 [DECIDED]가 아님
    Evidence: .sisyphus/evidence/task-1-adr013-created.txt

  Scenario: 기존 ADR 미변경 확인
    Tool: Bash (grep)
    Preconditions: Task 1 완료
    Steps:
      1. grep -c "DECIDED" docs/08-decision-log.md 로 총 DECIDED 개수 확인
      2. ADR-001~008, 010~012의 내용이 원본과 동일한지 확인 (ADR-001 첫 줄 "한국 시장을 우선 타겟" 등 샘플 검증)
    Expected Result: DECIDED 개수 = 13 (기존 12 - ADR-009 + ADR-013 + ADR-009는 SUPERSEDED), 기존 ADR 내용 불변
    Failure Indicators: DECIDED 개수 불일치 또는 기존 ADR 텍스트 변경
    Evidence: .sisyphus/evidence/task-1-existing-adrs-intact.txt
  ```

  **Commit**: YES (그룹: Commit 1 — Wave 1 일괄)
  - Message: `docs(#5): supersede ADR-009, add Pro Mode/Enjoy Mode two-sided app concept`
  - Files: `docs/08-decision-log.md`
  - Pre-commit: `grep "SUPERSEDED" docs/08-decision-log.md && grep "ADR-013" docs/08-decision-log.md`

- [ ] 2. docs/01-product-definition.md Pro Mode/Enjoy Mode 반영

  **What to do**:
  - 섹션 1 "한 줄 정의" 업데이트: Pro Mode/Enjoy Mode 개념 반영
  - 섹션 4 "타겟 사용자"에 Pro Mode 사용자 세그먼트 추가 (장비 렌탈 탐색자, 장소 스카우터, 스태프 모집 감독 등)
  - 섹션 5 "핵심 가치 제안"에 Pro Mode향 가치 추가: "제작에 필요한 인프라(장비, 장소, 인력, 후반, 교육, 자금, 행정)를 한곳에서 발견하는 곳"
  - 섹션 8 "스코프 경계" 업데이트:
    - **IN에 추가**: 촬영 장소 정보, 장비 렌탈 정보, 인력/캐스팅 채널 연계, 후반작업 시설 정보, 교육/워크숍 정보, 자금/펀딩 가이드, 법적/행정 가이드
    - **OUT에서 제거**: "캐스팅 매칭, 촬영 장소 DB, 장비 공유/렌탈" (현재 75줄)
    - **OUT 유지**: 크라우드 펀딩 직접 운영, 장비 거래 마켓플레이스 직접 운영 (정보 제공은 IN, 직접 운영은 OUT)
  - 섹션 12 "주요 결정 및 미결 사항"에 ADR-013 관련 DECIDED 항목 추가
  - 문서 메타데이터 `last_updated` 업데이트

  **Must NOT do**:
  - MVP 기능 목록(섹션 7) 변경 금지 (기능 설계는 별도 Phase)
  - 성공 지표(섹션 9) 변경 금지
  - 기존 DECIDED 결정 변경 금지

  **Recommended Agent Profile**:
  - **Category**: `quick`
    - Reason: 단일 파일의 명확한 섹션 업데이트
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: YES (with Tasks 1, 3)
  - **Parallel Group**: Wave 1
  - **Blocks**: Tasks 4-10
  - **Blocked By**: Task 1 (ADR-013 내용 참조 필요)

  **References**:

  **Pattern References**:
  - `docs/01-product-definition.md:72-75` — 현재 Scope Boundaries (OUT 목록 변경 대상)
  - `docs/01-product-definition.md:39-45` — 현재 타겟 사용자 (확장 대상)
  - `docs/01-product-definition.md:47-51` — 현재 가치 제안 (Pro Mode향 추가 대상)
  - `docs/01-product-definition.md:96-105` — 현재 결정/미결 사항 (ADR-013 추가 대상)

  **WHY Each Reference Matters**:
  - Scope Boundaries에서 OUT → IN 이동이 핵심 변경사항
  - 기존 구조를 유지하면서 Pro Mode 개념을 자연스럽게 삽입해야 함

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: Scope Boundaries IN 항목 확인
    Tool: Bash (grep)
    Preconditions: docs/01-product-definition.md 업데이트 완료
    Steps:
      1. grep -A5 "IN (포함)" docs/01-product-definition.md
      2. "촬영 장소", "장비", "인력" 문자열 존재 확인
    Expected Result: IN 목록에 촬영 장소, 장비, 인력 관련 항목이 포함
    Failure Indicators: IN 목록에 인프라 항목이 없거나, OUT 목록에 여전히 남아있음
    Evidence: .sisyphus/evidence/task-2-scope-boundaries.txt

  Scenario: Pro Mode/Enjoy Mode 개념 반영 확인
    Tool: Bash (grep)
    Preconditions: Task 2 완료
    Steps:
      1. grep -i "Pro Mode" docs/01-product-definition.md
      2. grep -i "Enjoy Mode" docs/01-product-definition.md
    Expected Result: 두 키워드 모두 문서에 존재
    Failure Indicators: 키워드 미존재
    Evidence: .sisyphus/evidence/task-2-pro-enjoy-mode.txt

  Scenario: MVP 기능 목록 미변경 확인
    Tool: Bash (grep)
    Preconditions: Task 2 완료
    Steps:
      1. grep -c "영화 업로드/관리" docs/01-product-definition.md
      2. grep -c "감독 대시보드" docs/01-product-definition.md
    Expected Result: 기존 MVP 기능 8개 항목 텍스트 그대로 존재
    Failure Indicators: 기존 기능 항목이 변경되거나 삭제됨
    Evidence: .sisyphus/evidence/task-2-mvp-intact.txt
  ```

  **Commit**: YES (그룹: Commit 1 — Wave 1 일괄)
  - Message: `docs(#5): supersede ADR-009, add Pro Mode/Enjoy Mode two-sided app concept`
  - Files: `docs/01-product-definition.md`

- [ ] 3. docs/04-creator-insights.md 결정 마커 업데이트

  **What to do**:
  - 102줄의 결정 마커 업데이트: 기존 `[DECIDED] 플랫폼은 '만든 후의 배급/발견'에 집중하며, 제작 도구(캐스팅, 장소 DB)는 범위에서 제외한다.`를 `[SUPERSEDED] 플랫폼은 '만든 후의 배급/발견'에 집중하며, 제작 도구(캐스팅, 장소 DB)는 범위에서 제외한다. → ADR-013으로 대체: Pro Mode에서 제작 인프라를 플랫폼 생태계에 직접 연계.`로 변경
  - 문서 메타데이터 `last_updated` 업데이트

  **Must NOT do**:
  - 103줄의 두 번째 결정 마커 변경 금지
  - 문서 본문 내용 변경 금지

  **Recommended Agent Profile**:
  - **Category**: `quick`
    - Reason: 2줄 변경의 단순 작업
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: YES (with Tasks 1, 2)
  - **Parallel Group**: Wave 1
  - **Blocks**: Task 11
  - **Blocked By**: Task 1

  **References**:

  **Pattern References**:
  - `docs/04-creator-insights.md:101-103` — 현재 결정 마커 2개 (첫 번째만 변경)

  **WHY Each Reference Matters**:
  - 정확한 줄 위치를 알아야 올바른 마커만 변경 가능

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: 결정 마커 SUPERSEDED 확인
    Tool: Bash (grep)
    Preconditions: docs/04-creator-insights.md 업데이트 완료
    Steps:
      1. grep "SUPERSEDED" docs/04-creator-insights.md
      2. grep "ADR-013" docs/04-creator-insights.md
    Expected Result: SUPERSEDED 마커 1개 존재, ADR-013 참조 포함
    Failure Indicators: 여전히 [DECIDED]이거나 ADR-013 참조 없음
    Evidence: .sisyphus/evidence/task-3-creator-marker.txt

  Scenario: 두 번째 결정 마커 미변경 확인
    Tool: Bash (grep)
    Preconditions: Task 3 완료
    Steps:
      1. grep "게이트키퍼 없는" docs/04-creator-insights.md
    Expected Result: "게이트키퍼 없는 '셀프 업로드'" 텍스트 그대로 존재
    Failure Indicators: 두 번째 마커가 변경되거나 삭제됨
    Evidence: .sisyphus/evidence/task-3-second-marker-intact.txt
  ```

  **Commit**: YES (그룹: Commit 1 — Wave 1 일괄)
  - Message: `docs(#5): supersede ADR-009, add Pro Mode/Enjoy Mode two-sided app concept`
  - Files: `docs/04-creator-insights.md`

- [ ] 4. 장비 렌탈 리서치 (docs/infrastructure/01-equipment-rental.md)

  **What to do**:
  - docs/infrastructure/ 디렉토리 생성 (없으면)
  - docs/infrastructure/01-equipment-rental.md 작성
  - **조사 범위**:
    - 카메라 렌탈 업체 (소니, 블랙매직, RED 등 독립영화용 장비 위주)
    - 조명 장비 렌탈 업체
    - 음향 장비 (붐마이크, 레코더 등) 렌탈
    - 그립/전동 장비 (돌리, 짐벌, 삼각대 등)
    - 시청자미디어센터 장비 대여 현황 (기존 데이터: 전국 63개소)
    - 중고 장비 거래 채널 (기존 데이터: 중고 구매→촬영→재판매 패턴)
    - 장비 공유/커뮤니티 대여 문화
    - 예산대별 장비 세트 가이드 (30만원대 / 100만원대 / 500만원대)
  - **문서 구조**:
    - 메타데이터 헤더 (status, last_updated, source)
    - 개요
    - 렌탈 업체 리스트 (업체명, 위치, 주요 장비, 가격대, URL, 특이사항)
    - 공공 장비 대여 (시청자미디어센터, 영상위원회 등)
    - 중고/공유 채널
    - 예산대별 추천 세트
    - Pro Mode 연동 시사점 (어떤 데이터를 플랫폼에 노출할 수 있는지)
    - 출처 목록

  **Must NOT do**:
  - 출처 없는 가격/비용 수치 창작 금지 — `[UNVERIFIED]` 마커 사용
  - DB 스키마나 API 설계 포함 금지
  - 해외 장비 업체 포함 금지 (한국 내 업체만)

  **Recommended Agent Profile**:
  - **Category**: `unspecified-high`
    - Reason: 웹 리서치가 필요한 중간 규모 문서 작성 작업
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: YES (with Tasks 5-10)
  - **Parallel Group**: Wave 2
  - **Blocks**: Task 11
  - **Blocked By**: Tasks 1, 2

  **References**:

  **Pattern References**:
  - `docs/04-creator-insights.md:47` — 장비 관련 기존 데이터: "중고 구매 후 촬영 후 재판매(렌탈비보다 저렴), 시청자미디어센터 편집실 활용"
  - `.sisyphus/drafts/cinema-on-air-research.md:463-464` — "중고 구매 → 촬영 → 재판매 (렌탈비보다 저렴), 시청자미디어센터 편집실"
  - `.sisyphus/drafts/cinema-on-air-research.md:488-493` — 시청자미디어센터 상세: 전국 63개, 무료 편집실/녹음실/스튜디오/장비 대여

  **External References**:
  - 시청자미디어재단 공식 사이트: 장비 대여 목록 및 이용 절차 조사
  - 영화장비 렌탈 업체 검색: "영화 카메라 렌탈", "촬영장비 대여" 등

  **WHY Each Reference Matters**:
  - 기존 데이터에서 아마추어 감독의 실제 장비 확보 패턴을 이해하고 이를 확장
  - 시청자미디어센터는 공공 인프라의 핵심이므로 상세 조사 필수

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: 문서 구조 및 최소 요건 확인
    Tool: Bash (wc, grep)
    Preconditions: docs/infrastructure/01-equipment-rental.md 생성 완료
    Steps:
      1. wc -l docs/infrastructure/01-equipment-rental.md
      2. grep -c "##" docs/infrastructure/01-equipment-rental.md (섹션 수 확인)
      3. grep "Pro Mode" docs/infrastructure/01-equipment-rental.md (연동 시사점 섹션 확인)
      4. grep "status:" docs/infrastructure/01-equipment-rental.md (메타데이터 확인)
    Expected Result: 80줄 이상, 5개 이상 섹션, "Pro Mode" 문자열 포함, 메타데이터 헤더 존재
    Failure Indicators: 80줄 미만, Pro Mode 섹션 없음, 메타데이터 없음
    Evidence: .sisyphus/evidence/task-4-equipment-structure.txt

  Scenario: 실명 기관/서비스 최소 5개 확인
    Tool: Bash (grep)
    Preconditions: Task 4 완료
    Steps:
      1. 문서 내 실명 업체/기관명 수를 카운트 (시청자미디어센터, 구체적 렌탈 업체명 등)
    Expected Result: 5개 이상의 실명 기관/서비스/채널 명시
    Failure Indicators: 5개 미만 또는 가상의 이름 사용
    Evidence: .sisyphus/evidence/task-4-equipment-entities.txt

  Scenario: UNVERIFIED 비율 확인
    Tool: Bash (grep)
    Preconditions: Task 4 완료
    Steps:
      1. grep -c "UNVERIFIED" docs/infrastructure/01-equipment-rental.md
      2. 전체 데이터 항목 수 대비 비율 계산
    Expected Result: UNVERIFIED 비율 20% 미만
    Failure Indicators: 20% 이상이 UNVERIFIED
    Evidence: .sisyphus/evidence/task-4-equipment-unverified.txt
  ```

  **Commit**: YES (그룹: Commit 2 — Wave 2 일괄)
  - Message: `research(#5): add infrastructure research for 7 categories`
  - Files: `docs/infrastructure/01-equipment-rental.md`

- [ ] 5. 촬영 장소 리서치 (docs/infrastructure/02-filming-locations.md)

  **What to do**:
  - docs/infrastructure/02-filming-locations.md 작성
  - **조사 범위**:
    - 서울/수도권 로케이션 스카우팅 채널
    - 지방 촬영 장소 확보 방법
    - 필름 커미션 (서울영상위원회, 부산영상위원회, 전주영상위원회 등)
    - 촬영 허가 절차 (도로, 공공장소, 사유지)
    - 스튜디오 렌탈 (독립영화 규모)
    - 시청자미디어센터 스튜디오 (기존 데이터)
    - 촬영 장소 관련 커뮤니티/DB (로케이션 매니저 네트워크 등)
    - 촬영지 비용 구조 (무료 ~ 유료 범위)
    - 공공시설 촬영 협조 절차
  - **문서 구조**: 메타데이터, 개요, 필름커미션 네트워크, 스튜디오/공간 렌탈, 공공시설 활용, 허가 절차 가이드, Pro Mode 연동 시사점, 출처

  **Must NOT do**:
  - 해외 촬영지 포함 금지
  - 로케이션 DB 시스템 설계 금지

  **Recommended Agent Profile**:
  - **Category**: `unspecified-high`
    - Reason: 웹 리서치 + 공공기관 정보 조사 필요
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: YES (with Tasks 4, 6-10)
  - **Parallel Group**: Wave 2
  - **Blocks**: Task 11
  - **Blocked By**: Tasks 1, 2

  **References**:

  **Pattern References**:
  - `docs/04-creator-insights.md:49` — "수십 군데의 거절 끝에 시청자미디어센터 등 공공시설에서만 허락. 재촬영은 자기 집 화장실을 세트로 활용."
  - `.sisyphus/drafts/cinema-on-air-research.md:466` — "수십 군데 거절 → 시청자미디어센터만 허락. 재촬영은 자기 집 화장실을 세트로"

  **WHY Each Reference Matters**:
  - 아마추어 감독의 장소 확보 어려움을 이해하고, 해결책이 될 수 있는 채널을 조사

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: 문서 구조 및 최소 요건 확인
    Tool: Bash (wc, grep)
    Steps:
      1. wc -l docs/infrastructure/02-filming-locations.md → 80줄 이상
      2. grep "Pro Mode" docs/infrastructure/02-filming-locations.md → 존재
      3. grep "status:" docs/infrastructure/02-filming-locations.md → 메타데이터 존재
    Expected Result: 80줄 이상, Pro Mode 섹션 존재, 메타데이터 헤더 존재
    Evidence: .sisyphus/evidence/task-5-locations-structure.txt

  Scenario: 필름커미션 최소 3개 지역 포함 확인
    Tool: Bash (grep)
    Steps:
      1. "서울영상위원회" 또는 "서울" 관련 필름커미션 언급 확인
      2. 최소 3개 지역 필름커미션 명시 확인
    Expected Result: 3개 이상 필름커미션 실명 포함
    Evidence: .sisyphus/evidence/task-5-locations-commissions.txt
  ```

  **Commit**: YES (그룹: Commit 2)
  - Files: `docs/infrastructure/02-filming-locations.md`

- [ ] 6. 인력/캐스팅 리서치 (docs/infrastructure/03-crew-casting.md)

  **What to do**:
  - docs/infrastructure/03-crew-casting.md 작성
  - **조사 범위**:
    - 배우 캐스팅 플랫폼 (필름메이커스 — 기존 데이터: 8,638+ 포스트, 서울 중심)
    - 대안 캐스팅 채널 (엑터길드, OTR 등)
    - 스태프 모집 채널 (촬영감독, 조명, 사운드 등)
    - 프리랜서 스태프 네트워크
    - 영화학교 인력 풀 (한국예술종합학교, 동국대, 중앙대 등)
    - 지방 인력 확보의 어려움과 해결책
    - 자원봉사 vs 유급 구조
    - 독립영화 표준 일당/페이 관행
  - **문서 구조**: 메타데이터, 개요, 캐스팅 플랫폼 비교표, 스태프 모집 채널, 인력 풀 (교육기관 연계), 지방 인력 문제, 페이 관행, Pro Mode 연동 시사점, 출처

  **Must NOT do**:
  - 캐스팅 매칭 시스템 설계 금지
  - 출처 없는 일당/페이 수치 창작 금지

  **Recommended Agent Profile**:
  - **Category**: `unspecified-high`
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: YES (with Tasks 4-5, 7-10)
  - **Parallel Group**: Wave 2
  - **Blocks**: Task 11
  - **Blocked By**: Tasks 1, 2

  **References**:

  **Pattern References**:
  - `docs/04-creator-insights.md:65-68` — 필름메이커스 상세: "한국 독립영화 캐스팅의 지배적 플랫폼, 8,638+ 포스트, 서울 중심, 지방 응답률 저조"
  - `.sisyphus/drafts/cinema-on-air-research.md:495-499` — 필름메이커스 + 대안(엑터길드, OTR)

  **WHY Each Reference Matters**:
  - 이미 확보된 필름메이커스 데이터를 기반으로 확장 조사

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: 문서 구조 + 실명 기관 확인
    Tool: Bash (wc, grep)
    Steps:
      1. wc -l docs/infrastructure/03-crew-casting.md → 80줄 이상
      2. grep "필름메이커스" docs/infrastructure/03-crew-casting.md → 존재
      3. grep "Pro Mode" docs/infrastructure/03-crew-casting.md → 존재
      4. 실명 플랫폼/기관 5개 이상 포함 확인
    Expected Result: 80줄 이상, 필름메이커스 포함, Pro Mode 섹션 존재, 5개 이상 실명
    Evidence: .sisyphus/evidence/task-6-crew-structure.txt
  ```

  **Commit**: YES (그룹: Commit 2)
  - Files: `docs/infrastructure/03-crew-casting.md`

- [ ] 7. 후반작업 리서치 (docs/infrastructure/04-post-production.md)

  **What to do**:
  - docs/infrastructure/04-post-production.md 작성
  - **조사 범위**:
    - 색보정(Color Grading) 스튜디오/프리랜서
    - 사운드 믹싱/마스터링 시설
    - DI(Digital Intermediate) 시설
    - DCP(Digital Cinema Package) 제작 서비스
    - 편집 시설 (시청자미디어센터 편집실 — 기존 데이터: 월 6일×8시간)
    - 후시녹음/폴리 스튜디오
    - VFX/CG 프리랜서/스튜디오 (독립영화 규모)
    - 자막 제작 (한/영) 서비스
    - 무료/저비용 소프트웨어 대안 (DaVinci Resolve 등)
  - **문서 구조**: 메타데이터, 개요, 후반작업 단계별 가이드, 시설/서비스 리스트, 공공 인프라(미디어센터), 소프트웨어 도구, 비용 구조, Pro Mode 연동 시사점, 출처

  **Must NOT do**:
  - 소프트웨어 튜토리얼 포함 금지
  - 출처 없는 비용 수치 창작 금지

  **Recommended Agent Profile**:
  - **Category**: `unspecified-high`
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: YES (with Tasks 4-6, 8-10)
  - **Parallel Group**: Wave 2
  - **Blocks**: Task 11
  - **Blocked By**: Tasks 1, 2

  **References**:

  **Pattern References**:
  - `.sisyphus/drafts/cinema-on-air-research.md:468` — "새벽에 주차장에서 후시녹음 직접 수행"
  - `.sisyphus/drafts/cinema-on-air-research.md:491-493` — 시청자미디어센터: "편집실 6실, 녹음실, 1인미디어제작실" + 이용 시간

  **WHY Each Reference Matters**:
  - 아마추어 감독의 열악한 후반 환경을 이해하고 접근 가능한 대안을 조사

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: 문서 구조 + 후반작업 단계 포함 확인
    Tool: Bash (wc, grep)
    Steps:
      1. wc -l docs/infrastructure/04-post-production.md → 80줄 이상
      2. grep "색보정\|Color Grading" docs/infrastructure/04-post-production.md → 존재
      3. grep "DCP" docs/infrastructure/04-post-production.md → 존재
      4. grep "Pro Mode" docs/infrastructure/04-post-production.md → 존재
    Expected Result: 80줄 이상, 색보정/DCP 언급, Pro Mode 섹션 존재
    Evidence: .sisyphus/evidence/task-7-postprod-structure.txt
  ```

  **Commit**: YES (그룹: Commit 2)
  - Files: `docs/infrastructure/04-post-production.md`

- [ ] 8. 교육/워크숍 리서치 (docs/infrastructure/05-education-workshop.md)

  **What to do**:
  - docs/infrastructure/05-education-workshop.md 작성
  - **조사 범위**:
    - 정규 영화학교 (한국예술종합학교, 동국대, 중앙대, 건국대, 세종대 영화과 등)
    - 비정규 영화학교/아카데미 (서울독립영화제 아카데미, 미장센 워크숍 등)
    - 지역 영화학교 (기존 데이터: "시나리오 8회, 편집 4회, 조명 1회, 촬영 1회")
    - 시청자미디어센터 교육 프로그램
    - 온라인 교육 (YouTube 독학 — 기존 데이터: "비전공, 독학(YouTube)")
    - 영진위/지역 영상위 주관 교육 프로그램
    - 해외 온라인 과정 중 한국어 접근 가능한 것 (MasterClass 등)
    - 멘토링 프로그램
  - **문서 구조**: 메타데이터, 개요, 정규 교육기관, 비정규 아카데미, 공공 교육(미디어센터), 온라인 교육, 멘토링, 비용 비교, Pro Mode 연동 시사점, 출처

  **Must NOT do**:
  - 교육 과정 커리큘럼 상세 설계 금지
  - 해외 교육기관 상세 목록 금지 (한국 내 접근 가능한 것만)

  **Recommended Agent Profile**:
  - **Category**: `unspecified-high`
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: YES (with Tasks 4-7, 9-10)
  - **Parallel Group**: Wave 2
  - **Blocks**: Task 11
  - **Blocked By**: Tasks 1, 2

  **References**:

  **Pattern References**:
  - `docs/04-creator-insights.md:46` — "지역 영화학교 수강 (시나리오 8회, 편집 4회, 조명 1회, 촬영 1회). 장비 부족 환경에 맞춘 커리큘럼."
  - `.sisyphus/drafts/cinema-on-air-research.md:463` — "교육: 지역 영화학교 수강"

  **WHY Each Reference Matters**:
  - 아마추어 감독이 실제로 이용하는 교육 채널에서 출발하여 포괄적 교육 생태계 지도 작성

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: 문서 구조 + 교육기관 확인
    Tool: Bash (wc, grep)
    Steps:
      1. wc -l docs/infrastructure/05-education-workshop.md → 80줄 이상
      2. grep "한국예술종합학교\|한예종" docs/infrastructure/05-education-workshop.md → 정규교육 포함 확인
      3. grep "시청자미디어" docs/infrastructure/05-education-workshop.md → 공공 교육 포함 확인
      4. grep "Pro Mode" docs/infrastructure/05-education-workshop.md → 존재
    Expected Result: 80줄 이상, 정규/비정규/공공 교육 모두 포함, Pro Mode 섹션 존재
    Evidence: .sisyphus/evidence/task-8-education-structure.txt
  ```

  **Commit**: YES (그룹: Commit 2)
  - Files: `docs/infrastructure/05-education-workshop.md`

- [ ] 9. 자금/펀딩 리서치 (docs/infrastructure/06-funding.md)

  **What to do**:
  - docs/infrastructure/06-funding.md 작성
  - **조사 범위**:
    - 영화진흥위원회(영진위) 제작지원 (기존 데이터: 단편 4억원, 편당 최대 3천만원, ~13편)
    - 지역 영상위원회 제작지원 (전주, 부산, 경남, 광주 등)
    - 문화체육관광부 산하 기금
    - 한국콘텐츠진흥원(KOCCA) 지원
    - 크라우드펀딩 플랫폼 (텀블벅, 와디즈 등 영화 프로젝트 사례)
    - 민간 펀드/재단 (CJ문화재단, 롯데시네마 독립영화 지원 등)
    - 국제 펀드 (부산국제영화제 ACF 등)
    - 자격 요건 분석 (신인 vs 경력자 진입장벽)
    - 지원서 작성 팁과 일반적인 탈락 사유
  - **문서 구조**: 메타데이터, 개요, 공공 제작지원 (중앙/지방), 민간 펀드, 크라우드펀딩, 국제 지원, 자격 요건 비교표, 신인 접근성 분석, Pro Mode 연동 시사점, 출처

  **Must NOT do**:
  - 크라우드펀딩 플랫폼 직접 운영 제안 금지
  - 출처 없는 예산/지원금 수치 창작 금지

  **Recommended Agent Profile**:
  - **Category**: `unspecified-high`
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: YES (with Tasks 4-8, 10)
  - **Parallel Group**: Wave 2
  - **Blocks**: Task 11
  - **Blocked By**: Tasks 1, 2

  **References**:

  **Pattern References**:
  - `docs/04-creator-insights.md:55-59` — 영진위 제작지원 접근성: "총예산 4억원, 편당 최대 3천만원, 전국 약 13편, 영화연출경력+영화제작업신고증 필수"
  - `.sisyphus/drafts/cinema-on-air-research.md:482-486` — 영진위 상세 + 자격 증명 함정
  - `.sisyphus/drafts/cinema-on-air-research.md:485` — 지역 기금: "전주영상위원회 총 4천만원 ~6편, 경남 6,700만원 ~5편"

  **WHY Each Reference Matters**:
  - 기존 데이터에 이미 영진위/지역기금 정보가 있으므로 이를 확장하여 포괄적 펀딩 지도 작성
  - 자격 증명 함정은 Pro Mode에서 해결할 수 있는 핵심 페인포인트

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: 문서 구조 + 공공/민간 펀딩 확인
    Tool: Bash (wc, grep)
    Steps:
      1. wc -l docs/infrastructure/06-funding.md → 80줄 이상
      2. grep "영화진흥위원회\|영진위" docs/infrastructure/06-funding.md → 공공 지원 포함
      3. grep "크라우드펀딩\|텀블벅\|와디즈" docs/infrastructure/06-funding.md → 민간 채널 포함
      4. grep "Pro Mode" docs/infrastructure/06-funding.md → 존재
    Expected Result: 80줄 이상, 공공+민간 펀딩 모두 포함, Pro Mode 섹션 존재
    Evidence: .sisyphus/evidence/task-9-funding-structure.txt
  ```

  **Commit**: YES (그룹: Commit 2)
  - Files: `docs/infrastructure/06-funding.md`

- [ ] 10. 법적/행정 리서치 (docs/infrastructure/07-legal-admin.md)

  **What to do**:
  - docs/infrastructure/07-legal-admin.md 작성
  - **조사 범위**:
    - 영화제작업 신고 절차 (기존 데이터: 영진위 지원 시 필수)
    - 촬영 허가 절차 (도로, 공공장소, 산림 등)
    - 출연 동의서/초상권 처리
    - 음악 저작권 (배경음악 사용, KOMCA, 저작권료)
    - 영상물 등급 심의 (영상물등급위원회)
    - 촬영 보험 (촬영 현장 사고 대비)
    - 세금/회계 (프리랜서 감독의 세무 처리)
    - 계약서 (배우, 스태프, 장소 사용 계약)
    - 독립영화 배급 계약 표준
  - **문서 구조**: 메타데이터, 개요, 영화제작업 신고, 촬영 허가, 저작권/초상권, 등급 심의, 보험, 세무/회계, 계약서 가이드, Pro Mode 연동 시사점, 출처

  **Must NOT do**:
  - 법률 자문 제공 금지 (정보 안내만)
  - 계약서 전문/템플릿 제공 금지

  **Recommended Agent Profile**:
  - **Category**: `unspecified-high`
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: YES (with Tasks 4-9)
  - **Parallel Group**: Wave 2
  - **Blocks**: Task 11
  - **Blocked By**: Tasks 1, 2

  **References**:

  **Pattern References**:
  - `.sisyphus/drafts/cinema-on-air-research.md:484` — "영화제작업신고증 필요 → 첫 영화 만드는 사람은 자격 미달"
  - `docs/04-creator-insights.md:57` — "영화연출경력 및 영화제작업신고증 필수 요구"

  **WHY Each Reference Matters**:
  - 영화제작업신고가 신인 감독의 핵심 장벽이므로 절차를 명확히 안내
  - 법적/행정 정보는 Pro Mode에서 가이드 형태로 제공할 핵심 콘텐츠

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: 문서 구조 + 법적 항목 확인
    Tool: Bash (wc, grep)
    Steps:
      1. wc -l docs/infrastructure/07-legal-admin.md → 80줄 이상
      2. grep "영화제작업" docs/infrastructure/07-legal-admin.md → 신고 절차 포함
      3. grep "저작권\|초상권" docs/infrastructure/07-legal-admin.md → 권리 관련 포함
      4. grep "Pro Mode" docs/infrastructure/07-legal-admin.md → 존재
    Expected Result: 80줄 이상, 영화제작업/저작권/초상권 모두 포함, Pro Mode 섹션 존재
    Evidence: .sisyphus/evidence/task-10-legal-structure.txt
  ```

  **Commit**: YES (그룹: Commit 2)
  - Files: `docs/infrastructure/07-legal-admin.md`

- [ ] 11. 인프라 인덱스 + 마스터 인덱스 업데이트

  **What to do**:
  - docs/infrastructure/00-index.md 생성:
    - 메타데이터 헤더
    - 인프라 조사 개요: 목적, 조사 범위, Pro Mode 연계 비전
    - 7개 카테고리 문서 테이블 (문서명, 제목, 핵심 내용, 상태)
    - 카테고리 간 교차 시사점 요약
    - 조사 한계 및 향후 과제
  - docs/00-index.md 업데이트:
    - "문서 구조" 테이블에 infrastructure/ 문서 8개 추가
    - "다음 단계" 섹션에 인프라 리서치 완료 반영
    - "결정 현황 요약"에 ADR-013 반영 (DECIDED 카운트 업데이트)
    - 핵심 결정 사항 Top 5에서 4번(ADR-009) 내용을 ADR-013으로 교체

  **Must NOT do**:
  - 기존 문서 구조 테이블의 다른 행 변경 금지
  - 가설 검증 로드맵 섹션 변경 금지

  **Recommended Agent Profile**:
  - **Category**: `quick`
    - Reason: 기존 패턴을 따라 인덱스 업데이트하는 간단한 작업
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: NO
  - **Parallel Group**: Wave 3 (Sequential)
  - **Blocks**: Task 12
  - **Blocked By**: Tasks 3, 4-10

  **References**:

  **Pattern References**:
  - `docs/00-index.md:17-27` — 기존 문서 구조 테이블 (동일 형식으로 infrastructure/ 추가)
  - `docs/00-index.md:46-52` — 핵심 결정 사항 Top 5 (4번 ADR-009 → ADR-013 교체)
  - `docs/00-index.md:34-44` — 결정 현황 요약 테이블 (DECIDED 카운트 업데이트)
  - `docs/validation/00-index.md` — 서브 인덱스 패턴 참고 (infrastructure/ 인덱스도 동일 형식)

  **WHY Each Reference Matters**:
  - 기존 인덱스 형식을 정확히 따라야 문서 일관성 유지
  - ADR 카운트 불일치 방지

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: 인프라 인덱스 파일 존재 + 구조 확인
    Tool: Bash (ls, wc, grep)
    Steps:
      1. ls docs/infrastructure/00-index.md → 파일 존재
      2. wc -l docs/infrastructure/00-index.md → 30줄 이상
      3. grep "01-equipment-rental" docs/infrastructure/00-index.md → 장비 문서 링크 존재
      4. grep "07-legal-admin" docs/infrastructure/00-index.md → 법적 문서 링크 존재
    Expected Result: 파일 존재, 30줄 이상, 7개 카테고리 문서 모두 링크됨
    Evidence: .sisyphus/evidence/task-11-infra-index.txt

  Scenario: 마스터 인덱스 업데이트 확인
    Tool: Bash (grep)
    Steps:
      1. grep "infrastructure" docs/00-index.md → infrastructure 섹션 존재
      2. grep "ADR-013" docs/00-index.md → ADR-013 반영
      3. grep -c "DECIDED" docs/00-index.md 로 업데이트된 카운트 확인
    Expected Result: infrastructure 문서가 마스터 인덱스에 반영, ADR-013 포함
    Evidence: .sisyphus/evidence/task-11-master-index.txt

  Scenario: 교차참조 무결성 확인
    Tool: Bash (grep + ls)
    Steps:
      1. docs/00-index.md에서 모든 "→ see docs/" 참조 추출
      2. 각 참조 대상 파일이 실제 존재하는지 ls로 확인
      3. docs/infrastructure/00-index.md에서도 동일 검사
    Expected Result: 모든 교차참조 대상 파일이 실제 존재
    Failure Indicators: 존재하지 않는 파일을 참조
    Evidence: .sisyphus/evidence/task-11-crossref.txt
  ```

  **Commit**: YES (Commit 3)
  - Message: `docs(#5): update index files with infrastructure section`
  - Files: `docs/00-index.md`, `docs/infrastructure/00-index.md`

- [ ] 12. 전체 검증 (교차참조, 줄 수, 출처, 마커)

  **What to do**:
  - 모든 산출물의 최종 품질 검증 수행:
    1. **줄 수 검증**: 모든 인프라 문서 80줄 이상 확인
    2. **실명 기관 검증**: 카테고리당 5개 이상 실명 기관/서비스 확인
    3. **출처 검증**: 카테고리당 3개 이상 출처 확인
    4. **UNVERIFIED 비율**: 전체 20% 미만 확인
    5. **교차참조 무결**: docs/ 전체의 모든 교차참조가 실제 파일을 가리키는지 확인
    6. **메타데이터 헤더**: 모든 새 문서에 status, last_updated, source 존재
    7. **결정 마커 일관성**: ADR-009 SUPERSEDED, ADR-013 DECIDED, 기존 ADR 미변경
    8. **docs/validation/ 미변경**: git diff로 확인
    9. **Pro Mode 섹션**: 모든 인프라 문서에 "Pro Mode 연동 시사점" 섹션 존재

  **Must NOT do**:
  - 검증 실패 시 직접 수정 금지 (실패 내용을 리포트하고 해당 태스크로 돌아가서 수정)

  **Recommended Agent Profile**:
  - **Category**: `unspecified-high`
    - Reason: 다수 파일에 대한 체계적 검증 필요
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: NO
  - **Parallel Group**: Wave 3 (Task 11 이후)
  - **Blocks**: F1-F4
  - **Blocked By**: Task 11

  **References**:

  **Pattern References**:
  - 이 플랜의 "Success Criteria" 섹션 — 검증 커맨드 전체 목록
  - 이 플랜의 "Must Have" 섹션 — 검증 기준

  **Acceptance Criteria**:

  **QA Scenarios (MANDATORY):**

  ```
  Scenario: 전체 줄 수 검증
    Tool: Bash (wc)
    Steps:
      1. wc -l docs/infrastructure/01-equipment-rental.md → 80 이상
      2. wc -l docs/infrastructure/02-filming-locations.md → 80 이상
      3. wc -l docs/infrastructure/03-crew-casting.md → 80 이상
      4. wc -l docs/infrastructure/04-post-production.md → 80 이상
      5. wc -l docs/infrastructure/05-education-workshop.md → 80 이상
      6. wc -l docs/infrastructure/06-funding.md → 80 이상
      7. wc -l docs/infrastructure/07-legal-admin.md → 80 이상
    Expected Result: 7개 문서 모두 80줄 이상
    Evidence: .sisyphus/evidence/task-12-line-counts.txt

  Scenario: 교차참조 전수 검사
    Tool: Bash (grep + ls)
    Steps:
      1. docs/ 전체에서 "→ see docs/" 패턴 추출
      2. 각 참조 파일 존재 여부 ls로 확인
    Expected Result: 모든 교차참조 100% 유효
    Evidence: .sisyphus/evidence/task-12-crossref-audit.txt

  Scenario: docs/validation/ 미변경 확인
    Tool: Bash (git diff)
    Steps:
      1. git diff --name-only docs/validation/ → 빈 출력
    Expected Result: docs/validation/ 파일 변경 없음
    Evidence: .sisyphus/evidence/task-12-validation-untouched.txt

  Scenario: UNVERIFIED 비율 확인
    Tool: Bash (grep)
    Steps:
      1. grep -c "UNVERIFIED" docs/infrastructure/*.md 로 총 개수
      2. 전체 항목 대비 비율 계산
    Expected Result: 20% 미만
    Evidence: .sisyphus/evidence/task-12-unverified-ratio.txt
  ```

  **Commit**: NO (검증만 수행)

---

## Final Verification Wave (MANDATORY — after ALL implementation tasks)

> 4 review agents run in PARALLEL. ALL must APPROVE. Rejection → fix → re-run.

- [ ] F1. **Plan Compliance Audit** — `oracle`
  Read the plan end-to-end. For each "Must Have": verify implementation exists (read file, grep for markers). For each "Must NOT Have": search codebase for forbidden patterns — reject with file:line if found. Check evidence files exist in .sisyphus/evidence/. Compare deliverables against plan.
  Output: `Must Have [N/N] | Must NOT Have [N/N] | Tasks [N/N] | VERDICT: APPROVE/REJECT`

- [ ] F2. **문서 품질 리뷰** — `unspecified-high`
  모든 인프라 문서의 메타데이터 헤더, 결정 마커 일관성, 한국어 품질, 출처 형식을 검사한다. `[UNVERIFIED]` 마커가 전체 항목의 20% 이상이면 REJECT. 각 문서 최소 80줄 검증.
  Output: `Documents [N/N valid] | Unverified Ratio [N%] | Min Lines [N] | VERDICT`

- [ ] F3. **전체 교차참조/출처 재검증** — `unspecified-high`
  docs/ 전체의 교차참조(`→ see docs/`)가 실제 파일을 가리키는지 전수 검사. 인프라 문서의 모든 URL이 유효한 형식인지 확인. 기관명이 실명인지 검증 (Google 검색으로 존재 확인).
  Output: `Cross-refs [N/N valid] | URLs [N/N valid] | Entities [N/N verified] | VERDICT`

- [ ] F4. **Scope Fidelity Check** — `deep`
  ADR-009가 SUPERSEDED이고 ADR-013이 DECIDED인지 확인. docs/01-product-definition.md의 Scope Boundaries에서 캐스팅/장소/장비가 IN에 있는지 확인. docs/validation/ 파일이 변경되지 않았는지 확인. 기존 ADR(001-008, 010-012)이 변경되지 않았는지 확인.
  Output: `ADR Status [OK/FAIL] | Scope [OK/FAIL] | Validation Untouched [OK/FAIL] | ADRs Intact [OK/FAIL] | VERDICT`

---

## Commit Strategy

- **Commit 1** (Wave 1): `docs(#5): supersede ADR-009, add Pro Mode/Enjoy Mode two-sided app concept` — docs/08-decision-log.md, docs/01-product-definition.md, docs/04-creator-insights.md
- **Commit 2** (Wave 2, 일괄): `research(#5): add infrastructure research for 7 categories` — docs/infrastructure/*.md
- **Commit 3** (Wave 3): `docs(#5): update index files with infrastructure section` — docs/00-index.md, docs/infrastructure/00-index.md

---

## Success Criteria

### Verification Commands
```bash
# 인프라 문서 8개 존재 확인
ls docs/infrastructure/*.md | wc -l  # Expected: 8

# 각 인프라 문서 최소 80줄
wc -l docs/infrastructure/*.md  # Expected: 모두 80줄 이상

# ADR-009 SUPERSEDED 확인
grep -c "SUPERSEDED" docs/08-decision-log.md  # Expected: 1 이상

# ADR-013 DECIDED 확인
grep -c "ADR-013" docs/08-decision-log.md  # Expected: 1 이상

# 출처 없는 수치 방지 — UNVERIFIED 비율 확인
grep -c "UNVERIFIED" docs/infrastructure/*.md  # Expected: 전체 항목의 20% 미만

# 교차참조 무결
grep -roh "→ see docs/[^ ]*" docs/ | sort -u  # 모든 참조 대상 파일이 존재해야 함

# docs/validation/ 미변경 확인
git diff --name-only docs/validation/  # Expected: 빈 출력
```

### Final Checklist
- [ ] ADR-009 `[SUPERSEDED]` + ADR-013 `[DECIDED]` 확인
- [ ] docs/01-product-definition.md에 Pro Mode/Enjoy Mode 개념 반영
- [ ] docs/infrastructure/ 디렉토리에 8개 .md 파일 존재
- [ ] 모든 인프라 문서에 "Pro Mode 연동 시사점" 섹션 존재
- [ ] 카테고리당 최소 5개 실명 기관/서비스
- [ ] 카테고리당 최소 3개 출처
- [ ] `[UNVERIFIED]` 비율 20% 미만
- [ ] 교차참조 100% 무결
- [ ] docs/validation/ 미변경
- [ ] 기존 ADR(001-008, 010-012) 미변경
- [ ] 모든 테스트 통과
