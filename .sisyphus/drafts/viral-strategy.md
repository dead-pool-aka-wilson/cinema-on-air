# Draft: 하꼬 영화 유튜버 바이럴 전략 + 인디그라운드 + 제작지원사업

## Requirements (confirmed)
- "하꼬 유튜버 (1000명 이상 구독자) 위주로 단편영화 플랫폼 홍보를 위한 바이럴 전략 작성"
- 너무 유명한 유튜버가 아닌, 소규모 영화 유튜버 타겟
- 인디그라운드 조사 필요
- 감독들이 국내에서 지원받을 수 있는 제작 지원사업 조사 필요
- 모든 문서 추가/변경은 GitHub 버전관리 필수 (Issue → Branch → Commit → PR → Merge)

## Technical Decisions
- Git workflow: Phase 1~3과 동일 (docs(#N): description 형식)
- 문서 위치: docs/ 하위 (TBD — 별도 디렉토리 or 기존 docs/ 에 추가)

## Research Findings

### Explore Agent (기존 문서 탐색) — COMPLETED
- 기존 문서에 유튜버 인플루언서 전략 **없음** → 이번이 첫 작성
- 랜딩페이지 카피: "유튜브에서 찾을 수 없는 단편영화" 포지셔닝 존재
- ADR-006: 웹 우선 → 링크 공유 바이럴 + SEO 최적화
- H2 검증: DC Inside, Twitter, Instagram, Naver Cafe 채널 이미 파악
- 기존 docs/infrastructure/06-funding.md (282줄): 영진위, 지역영상위, 민간재단, 크라우드펀딩 포함

### Librarian Agent (영화 유튜버 생태계) — COMPLETED
- 한국 영화 유튜버 6개 서브카테고리 분류: ① 줄거리 요약/리뷰 ② 분석/해설 ③ 촬영 브이로그 ④ 추천/큐레이션 ⑤ 영화제/독립영화 전문 ⑥ 라이프스타일
- 최적 타겟: ② 분석/해설 + ⑤ 영화제/독립 전문 + ③ 촬영 브이로그
- 하꼬 유튜버 협업 비용: 구독자 1~5천 (0~30만원), 5천~2만 (50~100만원), 2~5만 (100~300만원)
- 핵심 인사이트: "감독 인터뷰 접근권"이 Cinema on Air만의 고유 자산 → 비금전적 협업 인센티브
- 마이크로 인플루언서 ROI: 578% (피처링 2024)
- 영화 유튜버 특성: 저작권 민감, 진정성 문화, 롱폼 콘텐츠

### Librarian Agent (인디그라운드) — COMPLETED
- 정체: 영진위 설립 독립·예술영화 유통배급지원센터 (정부 기관, 비상업)
- URL: https://indieground.kr
- 핵심 서비스: 온라인 상영관(큐레이션 2주 단위 교체), 퍼스트링크(배급 매칭 80% 성공), 배급아카데미, 1:1 배급상담소
- 2025 라이브러리: 92편 (장편 23 + 단편 69)
- 전략적 판단: **경쟁자 아님 → 잠재적 파트너**. 인디그라운드가 못하는 것: 영구 아카이브, 크리에이터 수익화, 소셜 레이어, 모바일 앱
- Cinema on Air와 차별점: 인디그라운드=B2B(감독→배급사→극장), Cinema on Air=B2C(감독→관객 직접)

### Librarian Agent (제작지원사업) — COMPLETED
- **핵심 발견**: 영진위 단편 부문 13편→25편 (2배 확대), AI 기반 단편 30편 신설
- 영화제작업신고증 없이 신청 가능한 사업 7개 정리 (CJ 스토리업, 서울독립영화제 이강길, 영진위 시나리오공모, 미디액트 장비 등)
- CJ문화재단 스토리업: 신인 최우선 추천 (단편 연출 경험만 필요, 앤솔로지 극장 개봉+OTT 배급 연계)
- 기존 06-funding.md에 없는 추가 발견: AI 영화 지원, CJ 스토리업 상세, 인천스테이, 전주 후반제작지원, 미디액트 장비현물, 부산 다큐 개인신청

## Decisions Made (인터뷰 결과)
- [DECIDED] 문서 구조: 각각 별도 문서 → docs/09-viral-strategy.md + docs/10-indiground-analysis.md + docs/infrastructure/06-funding.md 업데이트
- [DECIDED] 인디그라운드: 경쟁 분석 + 파트너십 가능성 양면 관점
- [DECIDED] 제작지원사업: 기존 06-funding.md 업데이트 (추가 발견 사업 보강)
- [DECIDED] 바이럴 타이밍: 사전 홍보 → 런칭 → 성장 단계별 전략 모두 포함
- [DECIDED] Git workflow: GitHub Issue → Branch → Commit → PR → Merge 필수

## Open Questions
- 예산 제약 있는지? (유튜버 광고비 등)

## Scope Boundaries
- INCLUDE: 하꼬 영화 유튜버 바이럴 전략(단계별), 인디그라운드 경쟁분석+파트너십, 06-funding.md 보강, docs/00-index.md 업데이트
- EXCLUDE: TBD
