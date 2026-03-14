---
status: draft
last_updated: 2026-03-14
source: .sisyphus/drafts/cinema-on-air-research.md §16, §18, §22 + 대화 기반
---

# 08. 결정 기록부 (Decision Log)

이 문서는 Cinema on Air 프로젝트의 주요 아키텍처 및 비즈니스 결정을 기록합니다. 각 결정은 ADR(Architecture Decision Record) 형식을 따릅니다.

## 결정 요약
- **DECIDED**: 13개
- **OPEN**: 5개

---

### ADR-001: 타겟 시장 설정
- **상태**: [DECIDED]
- **결정**: 한국 시장을 우선 타겟으로 설정하고, 이후 글로벌 시장으로 확장한다.
- **컨텍스트**: 한국 단편영화 생태계의 강한 수요와 제작 인프라를 기반으로 초기 검증이 필요하다.
- **대안**: 처음부터 글로벌 타겟으로 시작.
- **근거**: 로컬 시장의 깊은 이해와 네트워크를 활용한 초기 콘텐츠 확보가 용이함.
- **소스**: .sisyphus/drafts/cinema-on-air-research.md §16
- **관련 문서**: [→ see docs/01-product-definition.md]

### ADR-002: 플랫폼 벤치마크 모델
- **상태**: [DECIDED]
- **결정**: Steam의 양면 플랫폼(Two-sided Platform) 모델을 벤치마킹한다.
- **컨텍스트**: 단순 스트리밍을 넘어 크리에이터 도구와 소비자 발견 메커니즘이 통합된 구조가 필요하다.
- **대안**: Netflix(구독형), YouTube(광고형) 단순 모델.
- **근거**: 게이트키퍼를 제거하고 데이터 기반으로 작품을 발견하는 Steam의 구조가 단편영화 생태계 문제 해결에 적합함.
- **소스**: .sisyphus/drafts/cinema-on-air-research.md §15, §16
- **관련 문서**: [→ see docs/01-product-definition.md]

### ADR-003: 초기 수익 모델
- **상태**: [DECIDED]
- **결정**: MVP 단계에서는 무료로 시작하며, 사용자 데이터를 기반으로 추후 수익 모델을 확정한다.
- **컨텍스트**: 초기 유저 확보와 플랫폼 활성화가 최우선 과제이다.
- **대안**: 초기부터 구독제 또는 건당 결제 도입.
- **근거**: 진입 장벽을 낮추어 최대한 많은 작품과 관객을 확보하기 위함.
- **소스**: .sisyphus/drafts/cinema-on-air-research.md §16
- **관련 문서**: [→ see docs/01-product-definition.md]

### ADR-004: 콘텐츠 품질 관리 메커니즘
- **상태**: [DECIDED]
- **결정**: Steam Direct 방식을 차용하여 소액의 등록비($10-30)를 부과한다.
- **컨텍스트**: 무분별한 업로드를 방지하고 최소한의 품질을 유지해야 한다.
- **대안**: 에디터 전수 검사, 완전 무료 업로드.
- **근거**: 자율성을 보장하면서도 스팸성 콘텐츠를 필터링할 수 있는 실질적인 허들 제공.
- **소스**: .sisyphus/drafts/cinema-on-air-research.md §16
- **관련 문서**: [→ see docs/01-product-definition.md]

### ADR-005: 아카이빙 데이터 깊이
- **상태**: [DECIDED]
- **결정**: IMDB 수준의 풀 크레딧(출연진, 스태프) 및 감독 필모그래피를 구축한다.
- **컨텍스트**: 단순 영상 시청을 넘어 영화인들의 포트폴리오 역할을 수행해야 한다.
- **대안**: 제목, 감독, 시놉시스 등 최소 정보만 기록.
- **근거**: 감독의 스타일 변화 추적 및 스태프들의 경력 증명 수요 충족.
- **소스**: .sisyphus/drafts/cinema-on-air-research.md §16
- **관련 문서**: [→ see docs/01-product-definition.md]

### ADR-006: 플랫폼 형태
- **상태**: [DECIDED]
- **결정**: 웹 우선(PC/모바일 웹)으로 개발한다.
- **컨텍스트**: 접근성이 높고 개발 속도가 빠른 플랫폼이 필요하다.
- **대안**: 네이티브 앱(iOS/Android) 우선 개발.
- **근거**: 링크 공유를 통한 바이럴과 검색 엔진 최적화(SEO)에 유리함.
- **소스**: .sisyphus/drafts/cinema-on-air-research.md §16
- **관련 문서**: [→ see docs/01-product-definition.md]

### ADR-007: 기술 스택 확정
- **상태**: [DECIDED]
- **결정**: Next.js + TypeScript를 핵심 기술 스택으로 사용한다.
- **컨텍스트**: SEO, 성능, 타입 안정성을 모두 고려해야 한다.
- **대안**: React SPA, Vue.js, Django.
- **근거**: 개발자의 숙련도와 현대적인 웹 개발 표준 준수.
- **소스**: .sisyphus/drafts/cinema-on-air-research.md §18
- **관련 문서**: [→ see docs/01-product-definition.md]

### ADR-008: MVP 핵심 기능 범위
- **상태**: [DECIDED]
- **결정**: 업로드, 프로필, 검색, 태그, 큐레이션, 영화제 이력, 대시보드, 스트리밍 등 8개 기능을 포함한다.
- **컨텍스트**: 최소 기능 제품으로서의 가치를 증명해야 한다.
- **대안**: 스트리밍 기능만 우선 런칭.
- **근거**: 아카이빙과 발견이라는 플랫폼의 핵심 가치를 전달하기 위한 최소 단위.
- **소스**: .sisyphus/drafts/cinema-on-air-research.md §18
- **관련 문서**: [→ see docs/01-product-definition.md]

### ADR-009: 플랫폼 서비스 범위(Scope)
- **상태**: [SUPERSEDED]
- **결정**: "만든 후의 플랫폼"(배급/발견)에 집중하며, 제작 도구는 제외한다.
- **컨텍스트**: 플랫폼의 정체성을 명확히 하고 리소스를 집중해야 한다.
- **대안**: 캐스팅, 장소 DB 등 제작 지원 기능 포함.
- **근거**: 현재 시장의 가장 큰 페인 포인트는 "만든 후 보여줄 곳이 없다"는 점임.
- **소스**: .sisyphus/drafts/cinema-on-air-research.md §22
- **관련 문서**: [→ see docs/01-product-definition.md]
- **폐기 사유**: Pro Mode/Enjoy Mode Two-sided App 전환으로 제작 인프라를 플랫폼 범위에 포함. ADR-013으로 대체.

### ADR-010: 핵심 비즈니스 메커니즘
- **상태**: [DECIDED]
- **결정**: 관객 지표를 기반으로 배급사가 감독을 발굴하는 구조를 구축한다.
- **컨텍스트**: 플랫폼의 지속 가능성을 위한 B2B 가치를 창출해야 한다.
- **대안**: 단순 광고 수익 모델.
- **근거**: 감독들에게 실질적인 커리어 상승 기회를 제공함으로써 플랫폼 충성도 확보.
- **소스**: .sisyphus/drafts/cinema-on-air-research.md §22
- **관련 문서**: [→ see docs/01-product-definition.md]

### ADR-011: 라이선스 정책
- **상태**: [DECIDED]
- **결정**: 비독점 라이선스(Non-exclusive)를 표준으로 채택한다.
- **컨텍스트**: 감독들이 다른 플랫폼이나 영화제에 자유롭게 출품할 수 있어야 한다.
- **대안**: 독점 라이선스 계약.
- **근거**: 인디 영화 업계의 표준이며 크리에이터의 권리를 존중함.
- **소스**: .sisyphus/drafts/cinema-on-air-research.md §12
- **관련 문서**: [→ see docs/01-product-definition.md]

### ADR-012: 수익 분배 비율 방향
- **상태**: [DECIDED]
- **결정**: 크리에이터 70%, 플랫폼 30% 분배를 지향한다.
- **컨텍스트**: 공정한 수익 배분을 통해 크리에이터 생태계를 지원한다.
- **대안**: 50/50 또는 플랫폼 우위 분배.
- **근거**: Steam, Apple App Store 등 글로벌 플랫폼의 표준이자 크리에이터 친화적 정책.
- **소스**: .sisyphus/drafts/cinema-on-air-research.md §12, §15
- **관련 문서**: [→ see docs/01-product-definition.md]

### ADR-013: 플랫폼 아키텍처 — Two-sided App (Pro Mode / Enjoy Mode)
- **상태**: [DECIDED]
- **결정**: Cinema on Air를 "Pro Mode(감독/크리에이터)"와 "Enjoy Mode(관객)"의 Two-sided App으로 구성하며, 제작 인프라(장비, 장소, 인력, 후반작업, 교육, 자금, 법적/행정)를 플랫폼 생태계에 직접 연계한다.
- **컨텍스트**: 영화를 본 관객이 제작자가 될 확률이 높으며, 촬영 장소/장비/인력/배급 정보를 연계하여 관객→제작자 전환을 유도하는 순환 생태계가 필요하다. 기존 ADR-009는 "만든 후의 플랫폼"으로 범위를 한정했으나, 이는 생태계 비전과 충돌함.
- **대안**: 기존 ADR-009 유지 (배급/발견만 집중)
- **근거**: 사용자 인터뷰 — "영화를 본 사람들은 또 영화를 만들 사람일 확률이 높음. 서비스는 투 사이드 앱. 프로모드랑 인조이 모드로 나뉨."
- **소스**: Phase 3 사용자 인터뷰 (2026-03-14)
- **관련 문서**: [→ see docs/01-product-definition.md], [→ see docs/infrastructure/00-index.md]

---

### ADR-OPEN-001: 구체적 수익 모델 확정
- **상태**: [OPEN]
- **결정**: 광고(AVOD), 구독(SVOD), 건당 결제(TVOD) 중 어떤 것을 주력으로 할지 미정.
- **컨텍스트**: 트래픽 규모와 사용자 반응에 따라 결정 필요.
- **소스**: .sisyphus/drafts/cinema-on-air-research.md §18
- **관련 문서**: [→ see docs/01-product-definition.md]

### ADR-OPEN-002: 비디오 호스팅 서비스 선택
- **상태**: [OPEN]
- **결정**: Mux와 Cloudflare Stream 중 최종 선택 미정.
- **컨텍스트**: 비용 효율성과 API 유연성을 비교 검토 중.
- **소스**: .sisyphus/drafts/cinema-on-air-research.md §18
- **관련 문서**: [→ see docs/01-product-definition.md]

### ADR-OPEN-003: 인증 및 사용자 시스템 설계
- **상태**: [OPEN]
- **결정**: 자체 인증 vs 소셜 로그인 vs NextAuth.js 등 구현 방식 미정.
- **컨텍스트**: 보안과 사용자 편의성 사이의 균형 필요.
- **소스**: .sisyphus/drafts/cinema-on-air-research.md §18
- **관련 문서**: [→ see docs/01-product-definition.md]

### ADR-OPEN-004: 디자인 및 UI/UX 방향성
- **상태**: [OPEN]
- **결정**: 시네마틱한 어두운 테마 vs 깔끔한 아카이브 스타일 등 미정.
- **컨텍스트**: 브랜드 정체성을 결정짓는 중요한 요소.
- **소스**: .sisyphus/drafts/cinema-on-air-research.md §18
- **관련 문서**: [→ see docs/01-product-definition.md]

### ADR-OPEN-005: 초기 콘텐츠 확보 전략
- **상태**: [OPEN]
- **결정**: 영화학교 협약 vs 개별 감독 섭외 vs 공모전 개최 등 구체적 실행 방안 미정.
- **컨텍스트**: 플랫폼 런칭 시점의 'Cold Start' 문제 해결 필요.
- **소스**: .sisyphus/drafts/cinema-on-air-research.md §18
- **관련 문서**: [→ see docs/01-product-definition.md]

---

## 이 문서에 포함되지 않는 내용
- 개별 기능의 상세 기술 명세 (→ docs/feature-specs/ 디렉토리 참조)
- 상세 UI 디자인 가이드 (향후 작성 예정)
- 마케팅 및 홍보 세부 계획
- 법적 계약서 전문
