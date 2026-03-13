# Validation Plan — Cinema on Air 가설 검증 실행

## 목표
`docs/06-validation-plan.md`에 정의된 H1~H6 가설을 개발 없이 검증하기 위한
실행 도구(설문, 랜딩페이지 콘텐츠, 뉴스레터, 큐레이션 프로토타입, 인터뷰 가이드)를 제작한다.

## 브랜치
`3-feat-execute-hypothesis-validation-plan-h1-h6`

## 이슈
#3

## 산출물 위치
`docs/validation/` 디렉토리

---

## Wave 1: 설문 및 랜딩페이지 콘텐츠 (H1, H2, H6)

- [ ] **Task 1**: H1+H6 설문 문항 설계 (`docs/validation/h1-h6-survey.md`)
  - 감독 대상 설문: 업로드 의향, 등록비 수용도
  - 배포 채널 목록: 필름메이커스, 누벨바그 갤러리, 대학 영화과 커뮤니티
  - 성공 기준 명시: 50명 중 10명+ 확답, 등록비 1만원 60%+ 수용

- [ ] **Task 2**: H2 랜딩페이지 콘텐츠 초안 (`docs/validation/h2-landing-page.md`)
  - 헤드라인, 서브헤드라인, 가치 제안 3가지
  - CTA 문구 (이메일 등록 버튼)
  - A/B 테스트 변형안 2개
  - 성공 기준: 방문자 5%+ 이메일 등록

## Wave 2: 뉴스레터 및 큐레이션 프로토타입 (H2, H3, H4)

- [ ] **Task 3**: H2+H4 뉴스레터 1호 콘텐츠 초안 (`docs/validation/h2-h4-newsletter-issue1.md`)
  - 제목, 소개글, 이번 주 추천 단편 3편 (실제 존재하는 작품)
  - 감독 소개 섹션
  - 독자 참여 유도 CTA
  - 성공 기준: 오픈율 40%+, 4주 연속 구독 유지율 30%+

- [ ] **Task 4**: H3 큐레이션 프로토타입 설계 (`docs/validation/h3-curation-prototype.md`)
  - Notion DB 구조 설계 (필드 정의: 제목, 감독, 태그, 무드, 런닝타임, 수상이력 등)
  - 태그 분류 체계 (장르 10개, 무드 10개, 테마 10개)
  - 테스트 방법론: 태그 기반 추천 vs 랜덤 추천 만족도 비교
  - 성공 기준: 태그 추천 만족도 랜덤 대비 2배+

## Wave 3: B2B 검증 도구 (H5)

- [ ] **Task 5**: H5 배급사 인터뷰 가이드 (`docs/validation/h5-distributor-interview.md`)
  - 인터뷰 대상 프로필 (독립영화 배급사, 영화제 프로그래머)
  - 질문 목록 15개 (오픈형 + 구조화)
  - 데이터 활용 의향 측정 방법
  - 성공 기준: 5명 중 3명+ "데이터 활용하겠다" 답변

## Wave 4: 종합 및 GO/NO-GO

- [ ] **Task 6**: 검증 결과 종합 보고서 템플릿 (`docs/validation/validation-results-template.md`)
  - H1~H6 결과 기록 테이블
  - GO/NO-GO 매트릭스 (docs/06-validation-plan.md §4 기반)
  - 피벗 시나리오별 다음 액션
  - 검증 완료 후 채울 수 있는 빈 템플릿

- [ ] **Task 7**: 인덱스 문서 (`docs/validation/00-index.md`)
  - 전체 검증 도구 목록 및 링크
  - 실행 순서 및 타임라인
  - 각 도구의 사용 방법 안내

---

## 완료 기준
- 7개 문서 모두 생성
- 각 문서 50줄 이상
- 실제 실행 가능한 수준의 구체성 (문항 텍스트, 콘텐츠 초안 포함)
- PR #3 머지

## 참조 문서
- `docs/06-validation-plan.md` — 가설 정의 및 성공 기준
- `docs/04-creator-insights.md` — 크리에이터 페인 포인트
- `docs/05-audience-insights.md` — 관객 수요 시그널
- `docs/01-product-definition.md` — 제품 정의
