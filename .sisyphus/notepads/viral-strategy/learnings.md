# Learnings — viral-strategy

## [2026-03-15] Session: ses_31946f544ffeQUUrAWWMaP4ADY

### Document Conventions (from existing docs)
- metadata header format: `---\nstatus: draft\nlast_updated: YYYY-MM-DD\nsource: ...\n---`
- H1 = doc title only. H2 = major sections. H3 = subsections
- All section headers in Korean (English technical terms allowed inline)
- Cross-reference format: `→ see docs/XX-filename.md`
- Decision markers: [DECIDED], [OPEN], [HYPOTHESIS], [SUPERSEDED]
- [UNVERIFIED] on claims without direct verifiable source URL
- End every doc with "## 이 문서에 포함되지 않는 내용" section
- Commit format: `docs(#N): description` (issue number mandatory)
- Push: `git remote set-url origin "https://$(gh auth token)@github.com/dead-pool-aka-wilson/cinema-on-air.git" && git push`

### Indiground Service Count: 9 (NOT 6)
- 02-market-research.md lists 9 핵심 사업 영역 (authoritative)
- Draft said "6 core services" = was summarizing highlights only
- 10-indiground-analysis.md MUST use 9

### 하꼬 유튜버 Range
- 1,000~50,000 subscribers total
- 나노: 1K~5K | 마이크로: 5K~20K | 스몰: 20K~50K

### 09-viral-strategy.md Framing
- Must be "바이럴 확산 전략 리서치" (research), NOT "홍보 계획" (plan)
- 00-index.md exclusion clause updated: "마케팅 및 홍보 실행 계획" (실행 추가)

### Git State
- Currently on: main branch
- Last commit: cf7d60f docs(#5): Korean indie film infrastructure map + Pro Mode ecosystem
- Need: new GitHub Issue (NOT reuse #5) → branch from that issue

## [2026-03-15] Task 2: docs/10-indiground-analysis.md
- Document structure: 10 sections with metadata header, all Korean headers
- Critical: 9개 사업 영역 MUST match 02-market-research.md exactly (order + names)
- B2B vs B2C framing is the key differentiator for dual analysis
- Partnership scenarios ordered by implementation difficulty (low→high)
- [UNVERIFIED] tags used for: 배급 매칭 80%, 10주 교육, 93% 만족도, Wavve 협업
- Evidence files pattern: task-2-{doc-structure,nine-services,consistency,line-count}.txt
- Line count target: 200-300 (achieved 227)

## [2026-03-15] Task 1: docs/09-viral-strategy.md
- 264 lines (target 250-350): PASS
- 11 sections, all Korean headers, metadata header follows convention
- 6 distinct [UNVERIFIED] claims (9 occurrences due to repeats in cost table + sources)
- Unverified ratio: ~12% (< 20% threshold)
- 5 cross-references all validated against existing files
- Key structure: 6 YouTuber subcategories table → 3-tier targeting → 5 collaboration models → cost matrix → 3-phase timeline
- "감독 인터뷰 접근권" positioned as Cinema on Air's unique non-monetary asset (dedicated section §8)
- Evidence files: task-1-{doc-structure,unverified-ratio,line-count,crossref-valid}.txt

## [2026-03-15] Task 3: docs/infrastructure/06-funding.md
- 282 → 336 lines (+54 lines added, 0 deletions)
- Added: §2.4 AI table expansion, §2.7 기획개발지원(작가), §3.6 기타 지역(인천스테이+부산다큐), §5.1 신고증 info, §5.2 이강길+후반+미디액트, §8.3 신고증불필요 7개 종합표, §10 source rows
- 핵심수치 update: 13편→25편 확대 (2026)
- Edit tool content-matching approach worked well for additive-only edits — no line number drift issues
- Line count 336 vs target 360-400: slightly below estimate but all specified content included
- Evidence files: task-3-{preservation,new-content,line-count,sources}.txt
