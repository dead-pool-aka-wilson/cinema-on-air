# Completion Report 시스템 — 프로세스 규약

## 목적

플랜이 완료될 때마다 구조화된 마무리 레포트를 `.sisyphus/reports/{plan-name}.md`에 생성한다.
두 가지 역할을 겸한다:

1. **세션 복구**: 세션이 죽거나 컨텍스트가 초기화됐을 때 새 세션이 즉시 현황 파악
2. **작업 아카이빙**: 나중에 "Phase N에서 뭘 했지?" 를 되돌아볼 때 참조

---

## 생성 시점

**플랜 완료 시 (PR 머지 직후)**. 구체적으로:

- 모든 새 플랜의 **마지막 태스크**에 "Completion Report 생성" 태스크를 반드시 포함한다
- 레포트 생성은 PR 머지 직전 또는 직후에 수행 (머지 커밋 정보가 필요하므로 직후 권장)
- 이 과정은 **코드/스크립트가 아닌 프로세스 규약(convention)** — 에이전트가 수동으로 수행

---

## 파일 명명 규칙

```
.sisyphus/reports/{plan-name}.md
```

- plan 파일(`.sisyphus/plans/{plan-name}.md`)과 **1:1 대응**
- 날짜 접두사, phase 번호 접두사 사용 금지
- 예: `docs-foundation.md`, `viral-strategy.md`

---

## 6개 필수 섹션 및 데이터 소스

| 섹션 | 데이터 소스 |
|------|-----------|
| 사용자 요청 원문 | plan 파일의 `### Original Request` 섹션 |
| 산출물 | plan 파일 `Deliverables` + `git diff --stat` + `gh pr view {N} --json files` |
| 핵심 결정사항 | `notepads/{plan}/decisions.md` + plan 파일 `### Interview Summary` |
| Git 상태 스냅샷 | `git log --oneline` + `gh pr view {N} --json title,mergedAt,mergeCommit` |
| 다음 단계 | plan 파일 기재사항 + 자연스러운 후속 작업 추론. 소급 레포트는 "실제로 한 것" 기준 |
| 에이전트 세션 ID | `boulder.json` + notepads에 기록된 세션 |

---

## 데이터 없음 처리 규칙

**추정/날조 금지.** 데이터가 없으면 아래 형식으로 표기:

```
데이터 없음 ({이유})
```

예시:

- `데이터 없음 (세션 추적 시작 전)`
- `데이터 없음 (notepad 디렉토리 미존재)`

---

## 미완료/취소 플랜 처리

- **Status** 필드: `cancelled` 또는 `paused`로 표기
- 중단 사유 기록 (`## 중단 사유` 섹션 추가)
- PR이 없으면 Git 상태 섹션에 `PR: 생성 안 됨` 표기

---

## 템플릿

레포트 작성 시 `.sisyphus/reports/_template.md`를 기반으로 한다.
섹션을 삭제하거나 이름을 바꾸지 않는다.

---

## 현재까지 생성된 레포트

| Phase | Plan | 레포트 |
|-------|------|--------|
| 1 | docs-foundation | [docs-foundation.md](./docs-foundation.md) |
| 2 | validation | [validation.md](./validation.md) |
| 3 | infrastructure-research | [infrastructure-research.md](./infrastructure-research.md) |
| 4 | viral-strategy | [viral-strategy.md](./viral-strategy.md) |
| 5 | completion-reports | [completion-reports.md](./completion-reports.md) |
