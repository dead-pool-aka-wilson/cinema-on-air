# Draft: 플랜 완료 레포트 시스템

## Requirements (confirmed)
- **목적**: 세션 복구 + 작업 기록 아카이빙 (둘 다)
- **생성 시점**: 플랜 완료 시 자동 (PR 머지 직후)
- **적용 범위**: cinema-on-air 프로젝트 한정
- **파일 위치**: `.sisyphus/reports/{plan-name}.md`
- **소급 적용**: Phase 1~4 전부 레포트 생성

## 레포트 콘텐츠 (사용자 선택, 6개 전부)
1. **산출물**: 생성/수정된 파일, 커밋, PR 번호
2. **핵심 결정사항**: ADR 등 주요 결정
3. **Git 상태 스냅샷**: 브랜치, 커밋 해시, 머지 상태
4. **다음 단계 제안**: 이후 가능한 작업
5. **사용자 요청 원문**: 사용자가 실제로 말한 것 그대로
6. **에이전트 세션 ID**: 나중에 세션을 다시 읽을 수 있는 참조

## Technical Decisions
- 레포트는 markdown 파일
- 플랜 1:1 대응 (plan 하나 = report 하나)
- 기존 notepads/evidence는 그대로 유지 (report는 요약 레이어)

## Scope Boundaries
- INCLUDE: 레포트 템플릿 정의, Phase 1~4 소급 레포트 4개 생성
- EXCLUDE: OpenCode 설정 수정, 자동화 스크립트, 다른 프로젝트 적용
