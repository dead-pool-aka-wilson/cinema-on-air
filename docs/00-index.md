---
status: draft
last_updated: 2026-03-15
source: 전체 docs/ 문서 종합
---

# Cinema on Air — 기획 문서 마스터 인덱스

## 프로젝트 개요

**Cinema on Air**는 단편영화 제작자(감독)가 작품을 직접 업로드하고 아카이빙하며, 관객은 스트리밍으로 감상하고, 배급사는 관객 지표를 통해 신인 감독을 발굴하는 양면 플랫폼이다. Steam의 성공적인 인디 게임 생태계 모델을 단편영화 산업에 이식하여, 기존 게이트키퍼(배급사·영화제) 중심의 수직적 구조를 해체하고 데이터 기반의 수평적 발견 생태계를 구축하는 것을 목표로 한다.

---

## 문서 구조

| 문서 | 제목 | 목적 | 상태 |
|:---|:---|:---|:---|
| [01-product-definition.md](./01-product-definition.md) | 제품 정의 및 포지셔닝 | 서비스 정체성, 핵심 가치 제안, 타겟 사용자, MVP 기능 범위 정의 | draft |
| [02-market-research.md](./02-market-research.md) | 시장 조사 및 경쟁 분석 | 한국 단편영화 시장 규모, 경쟁 플랫폼 분석, 시장 공백 식별 | draft |
| [03-steam-benchmarking.md](./03-steam-benchmarking.md) | Steam 벤치마킹 | Steam 양면 플랫폼 구조의 단편영화 플랫폼 매핑 (15개 요소) | draft |
| [04-creator-insights.md](./04-creator-insights.md) | 크리에이터 인사이트 | 한국 단편영화 제작자 생태계, 게이트키퍼 구조, 아마추어/지방 감독 프로필 | draft |
| [05-audience-insights.md](./05-audience-insights.md) | 관객 인사이트 | 단편영화 관객 커뮤니티 분석, 수요 시그널, 관객 페르소나 | draft |
| [06-validation-plan.md](./06-validation-plan.md) | 가설 검증 계획 | 개발 전 검증 가능한 핵심 가설 목록 및 테스트 방법론 | draft |
| [07-technical-preliminary.md](./07-technical-preliminary.md) | 기술 예비 조사 | 기술 스택 선택 근거, 비디오 호스팅 옵션, 인프라 비용 추정 | draft |
| [08-decision-log.md](./08-decision-log.md) | 결정 기록부 (ADR) | 모든 아키텍처·비즈니스 결정을 ADR 형식으로 기록 | draft |
| [09-viral-strategy.md](./09-viral-strategy.md) | 바이럴 확산 전략 리서치 | 하꼬 영화 유튜버 협업 전략, 비용 분석, 단계별 확산 방안 | draft |
| [10-indiground-analysis.md](./10-indiground-analysis.md) | 인디그라운드 분석 | 인디그라운드 경쟁/파트너 양면 분석, Cinema on Air 비교 | draft |
| [infrastructure/00-index.md](./infrastructure/00-index.md) | 인프라 마스터 인덱스 | Pro Mode 생태계 구성 7개 카테고리(장비, 장소, 인력, 후반, 교육, 자금, 법적) 종합 | draft |

---

## 결정 현황 요약

### 문서별 마커 현황

| 문서 | [DECIDED] | [OPEN] | [HYPOTHESIS] |
|:---|:---:|:---:|:---:|
| 01-product-definition.md | 9 | 0 | 0 |
| 02-market-research.md | 3 | 0 | 0 |
| 03-steam-benchmarking.md | 2 | 0 | 0 |
| 04-creator-insights.md | 2 | 0 | 0 |
| 05-audience-insights.md | 2 | 0 | 0 |
| 06-validation-plan.md | 6 | 0 | 0 |
| 07-technical-preliminary.md | 8 | 0 | 0 |
| 08-decision-log.md | 13 | 5 | 0 |
| 09-viral-strategy.md | 0 | 0 | 0 |
| 10-indiground-analysis.md | 0 | 0 | 0 |
| infrastructure/01-equipment-rental.md | 0 | 0 | 0 |
| infrastructure/02-filming-locations.md | 0 | 0 | 0 |
| infrastructure/03-crew-casting.md | 0 | 0 | 0 |
| infrastructure/04-post-production.md | 0 | 0 | 0 |
| infrastructure/05-education-workshop.md | 0 | 0 | 0 |
| infrastructure/06-funding.md | 0 | 0 | 0 |
| infrastructure/07-legal-admin.md | 0 | 0 | 0 |
| **합계** | **45** | **5** | **0** | **10 문서** |

### 핵심 결정 사항 Top 5

1. **[DECIDED] 타겟 시장**: 한국 우선 → 글로벌 확장 (→ see docs/08-decision-log.md ADR-001)
2. **[DECIDED] 벤치마크 모델**: Steam 양면 플랫폼 — 크리에이터 도구 + 소비자 발견 메커니즘 통합 (→ see docs/03-steam-benchmarking.md)
3. **[DECIDED] 핵심 메커니즘**: 관객 지표(조회수·완주율·리뷰) 기반 배급사 감독 발굴 구조 (→ see docs/04-creator-insights.md)
4. **[DECIDED] 플랫폼 아키텍처**: Pro Mode(감독/크리에이터) + Enjoy Mode(관객) Two-sided App, 제작 인프라(장비·장소·인력·후반·교육·자금·법적) 연계 (→ see docs/08-decision-log.md ADR-013)
5. **[DECIDED] 기술 스택**: Next.js + TypeScript, 웹 우선(PC/모바일 웹) (→ see docs/07-technical-preliminary.md)

### 주요 미결 사항 (OPEN)

1. **[OPEN] 수익 모델 확정**: AVOD·SVOD·TVOD 중 주력 모델 미정 (→ see docs/08-decision-log.md ADR-OPEN-001)
2. **[OPEN] 비디오 호스팅**: Mux vs Cloudflare Stream 최종 선택 미정 (→ see docs/08-decision-log.md ADR-OPEN-002)
3. **[OPEN] 인증 시스템**: 자체 인증 vs 소셜 로그인 vs NextAuth.js 미정 (→ see docs/08-decision-log.md ADR-OPEN-003)
4. **[OPEN] UI/UX 방향**: 시네마틱 다크 테마 vs 아카이브 스타일 미정 (→ see docs/08-decision-log.md ADR-OPEN-004)
5. **[OPEN] 초기 콘텐츠 확보**: 영화학교 협약 vs 개별 섭외 vs 공모전 미정 (→ see docs/08-decision-log.md ADR-OPEN-005)

---

## 가설 검증 로드맵

개발 전 검증해야 할 핵심 가설 3개 (→ 상세 내용: docs/06-validation-plan.md):

1. **수요 가설**: "단편영화 감독들은 유료 등록비($10-30)를 내고서라도 자신의 작품을 아카이빙하고 싶어한다"
   - 검증 방법: 랜딩 페이지 + 사전 등록 폼 → 전환율 측정

2. **발견 가설**: "관객은 영화제 선정 여부와 무관하게 독립 단편영화를 스트리밍으로 감상할 의향이 있다"
   - 검증 방법: 커뮤니티(누벨바그 갤러리 등) 설문 + 시청 의향 조사

3. **B2B 가설**: "배급사/제작사는 플랫폼의 관객 지표 데이터를 신인 감독 발굴에 활용할 의향이 있다"
   - 검증 방법: 배급사 인터뷰 5건 이상

---

## 다음 단계

이 문서 세트 완성 후 진행할 작업:

1. **가설 검증 테스트 실행** (docs/06-validation-plan.md 기반)
    - 랜딩 페이지 제작 (개발 없이 Notion/Framer 활용)
    - 커뮤니티 설문 배포
    - 배급사 인터뷰 섭외

2. **Pro Mode 인프라 연계 전략 수립** (docs/infrastructure/00-index.md 기반)
    - 7개 카테고리별 제휴 협약 대상 선정 (렌탈 업체, 스튜디오, 교육 기관 등)
    - Pro Mode 내 "리소스 가이드" 섹션 설계
    - 제작자 전환 경로(관객 → 제작자) 프로토타입 설계

3. **기술 스택 최종 확정** (docs/07-technical-preliminary.md 기반)
    - 비디오 호스팅 서비스 선택 (Mux vs Cloudflare Stream)
    - 인증 시스템 설계

4. **MVP 개발 착수**
    - 기능 명세서 작성 (docs/feature-specs/ 디렉토리 활용)
    - 데이터베이스 스키마 설계 (Pro Mode/Enjoy Mode 분리 고려)

---

## 이 문서에 포함되지 않는 내용
- 각 문서의 상세 내용 (→ 해당 문서 직접 참조)
- 개발 코드 및 기술 구현 명세
- 마케팅 및 홍보 실행 계획
