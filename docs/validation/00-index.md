---
status: draft
last_updated: 2026-03-13
source: docs/06-validation-plan.md 기반 실행 도구 모음
---

# Cinema on Air — 가설 검증 도구 인덱스

## 개요

이 디렉토리는 Cinema on Air의 6개 핵심 가설(H1~H6)을 **개발 없이** 검증하기 위한 실행 도구 모음입니다.
`docs/06-validation-plan.md`에 정의된 검증 계획을 실제로 실행할 수 있는 구체적인 문서들로 구성됩니다.

---

## 검증 도구 목록

| 파일 | 가설 | 도구 유형 | 상태 |
|------|------|---------|------|
| [h1-h6-survey.md](./h1-h6-survey.md) | H1, H6 | 설문 문항 (Google Forms) | draft |
| [h2-landing-page.md](./h2-landing-page.md) | H2 | 랜딩페이지 콘텐츠 초안 | draft |
| [h2-h4-newsletter-issue1.md](./h2-h4-newsletter-issue1.md) | H2, H4 | 뉴스레터 1호 콘텐츠 초안 | draft |
| [h3-curation-prototype.md](./h3-curation-prototype.md) | H3 | 큐레이션 프로토타입 설계 | draft |
| [h5-distributor-interview.md](./h5-distributor-interview.md) | H5 | 배급사 인터뷰 가이드 | draft |
| [validation-results-template.md](./validation-results-template.md) | H1~H6 | 결과 종합 보고서 템플릿 | template |

---

## 가설 요약

| 가설 | 내용 | 위험도 | 성공 기준 |
|------|------|--------|---------|
| **H1 공급** | 감독들이 작품을 올릴 의향이 있는가? | 높음 | 50명 중 10명+ 확답 |
| **H2 수요** | 관객이 독립영화 특화 플랫폼을 이용할 의향이 있는가? | 높음 | 전환율 5%+ 또는 오픈율 40%+ |
| **H3 발견** | 태그/큐레이션이 관객 만족도를 높이는가? | 중간 | 랜덤 추천 대비 만족도 2배+ |
| **H4 리텐션** | 관객이 정기적으로 재방문하는가? | 높음 | 4주 연속 오픈율 30%+ |
| **H5 B2B** | 배급사가 플랫폼 데이터를 활용할 의향이 있는가? | 중간 | 5명 중 3명+ 활용 의향 |
| **H6 수익화** | 감독들이 등록비를 낼 의향이 있는가? | 낮음 | 1만원 기준 60%+ 수용 |

---

## 실행 순서 및 타임라인

### Week 1~2: 기초 검증 (H1, H2, H6 동시 진행)

```
Day 1-3:   랜딩페이지 제작 (h2-landing-page.md 기반, Framer/Carrd 활용)
Day 3-5:   설문 제작 (h1-h6-survey.md 기반, Google Forms)
Day 5-7:   배포 시작
           - 랜딩페이지: 커뮤니티 게시글 + SNS
           - 설문: 필름메이커스, 누벨바그 갤러리, 대학 영화과
Day 7-14:  응답 수집 + 배급사 인터뷰 섭외 시작
```

### Week 2~4: 심화 검증 (H2, H3, H4, H5 진행)

```
Day 8:     뉴스레터 1호 발행 (h2-h4-newsletter-issue1.md 기반)
Day 10-14: Notion DB 구축 시작 (h3-curation-prototype.md 기반, 100편 태깅)
Day 14-21: 배급사 인터뷰 진행 (h5-distributor-interview.md 기반)
Day 15:    뉴스레터 2호 발행
Day 22:    뉴스레터 3호 발행
```

### Week 4~6: 분석 및 결정

```
Day 29:    뉴스레터 4호 발행 (마지막)
Day 28-35: H3 큐레이션 테스트 진행 (시네필 10명)
Day 35-42: 전체 데이터 수집 완료
Day 42:    validation-results-template.md 작성 완료
Day 42:    GO/NO-GO 최종 결정
```

---

## 각 도구 사용 방법

### h1-h6-survey.md
1. 문서의 설문 문항을 Google Forms에 그대로 입력
2. 배포 채널 목록에 따라 링크 공유
3. 응답 수집 후 Q5 4~5점 응답자 수 집계 → H1 판정
4. Q12 5,000원+ 응답자 비율 집계 → H6 판정

### h2-landing-page.md
1. 문서의 헤드라인/서브헤드라인/CTA를 Framer 또는 Carrd에 입력
2. A안/B안 두 버전 제작 후 A/B 테스트
3. Google Analytics 설치 후 전환율 측정
4. 2주 후 전환율 집계 → H2 판정

### h2-h4-newsletter-issue1.md
1. Substack 계정 생성
2. 문서 구조에 따라 실제 작품 정보 채워 넣기
3. 매주 목요일 발행 (4주 연속)
4. 4주차 오픈율 집계 → H2, H4 판정

### h3-curation-prototype.md
1. Notion에 DB 구조 생성 (필드 정의 참고)
2. 단편영화 100편 수집 및 태깅
3. 시네필 10명 모집 후 테스트 진행
4. 만족도 비교 → H3 판정

### h5-distributor-interview.md
1. 섭외 이메일 템플릿으로 배급사/영화제 관계자 5명 섭외
2. 인터뷰 질문 목록에 따라 30~45분 인터뷰 진행
3. 결과 기록 템플릿으로 메모 정리
4. B1 점수 집계 → H5 판정

### validation-results-template.md
1. 각 가설 검증 완료 후 해당 섹션 채워 넣기
2. 최종 GO/NO-GO 매트릭스 작성
3. 다음 액션 결정

---

## GO/NO-GO 결정 기준

**GO (MVP 개발 착수)**: H1 + H2 모두 성공
**PIVOT**: H1 또는 H2 중 하나만 성공
**NO-GO**: H1 + H2 모두 실패

→ 상세 매트릭스: `docs/06-validation-plan.md §4`

---

## 이 디렉토리에 포함되지 않는 내용
- 가설 정의 및 성공 기준 원본 (→ docs/06-validation-plan.md)
- 크리에이터 페인 포인트 상세 (→ docs/04-creator-insights.md)
- 관객 수요 시그널 상세 (→ docs/05-audience-insights.md)
- MVP 개발 계획 (→ GO 판정 후 별도 작성)
