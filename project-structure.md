# Rome-AI Comparative Study
## Git Repository 구조 및 워크플로우 설계

---

## 1. 레포지토리 개요

```
repo: rome-ai-labor-study
설명: 로마 노예 노동력 도입과 현대 AI/자동화의 구조적 비교 연구
라이선스: CC BY-SA 4.0 (연구 노트) / MIT (도구·스크립트)
```

**핵심 원칙**
- 마크다운 기반 → GitHub/GitLab에서 바로 렌더링, VSCode에서 편집·미리보기
- 커밋 = 연구 활동 단위 → 커밋 메시지가 연구 일지 역할
- 브랜치 = 탐구 방향 → 결론이 나면 main에 머지, 막다른 골목이면 아카이브
- 태그 = 마일스톤 → 특정 시점의 연구 스냅샷

---

## 2. 디렉토리 구조

```
rome-ai-labor-study/
│
├── README.md                          # 프로젝트 소개, 핵심 질문, 현재 상태
├── CHANGELOG.md                       # 주요 연구 진전 기록 (태그와 연동)
├── .vscode/
│   ├── settings.json                  # 마크다운 린터, 추천 익스텐션 설정
│   └── extensions.json                # 추천 VSCode 익스텐션 목록
│
├── 00-meta/                           # 🧭 프로젝트 메타 정보
│   ├── research-questions.md          # 핵심 연구 질문 목록 (진화하는 문서)
│   ├── roadmap.md                     # 로드맵 및 진행 상태
│   ├── methodology.md                 # 비교 방법론, 유추의 한계 명시
│   └── glossary.md                    # 용어사전 (라틴어/경제학/AI 용어)
│
├── 01-rome/                           # 🏛️ 로마 측 자료 및 분석
│   ├── _index.md                      # 이 섹션의 개요 및 내비게이션
│   ├── sources/                       # 참고문헌·자료 정리
│   │   ├── bibliography.md            # 서지 목록 (BibTeX 형식 병행 가능)
│   │   ├── bowes-2025.md              # 개별 문헌 노트 (1문헌 = 1파일)
│   │   ├── rosenstein-2004.md
│   │   ├── de-ligt-2012.md
│   │   ├── scheidel-guthmann-2025.md
│   │   ├── temin-2004.md
│   │   ├── harper-2011.md
│   │   ├── roth-2007.md
│   │   └── ...
│   ├── topics/                        # 주제별 분석
│   │   ├── smallholder-economy.md     # 소농 경제의 실상
│   │   ├── slavery-labor-market.md    # 노예와 노동시장
│   │   ├── manumission-mobility.md    # 해방과 사회적 이동
│   │   ├── consumer-revolution.md     # 서민의 소비생활
│   │   ├── monetization-credit.md     # 화폐화와 신용
│   │   ├── diet-health.md             # 식생활과 건강 (생물고고학)
│   │   ├── land-concentration.md      # 토지 집중과 라티푼디움
│   │   ├── political-crisis.md        # 정치적 위기 (그라쿠스~내전)
│   │   ├── grain-dole.md              # 곡물 배급 정책
│   │   └── military-reform.md         # 마리우스 군제 개혁
│   └── debates/                       # 학술 논쟁 정리
│       ├── traditional-vs-revisionist.md
│       ├── high-vs-low-count.md       # 인구 논쟁
│       └── decline-vs-adaptation.md   # 몰락 vs 적응 논쟁
│
├── 02-modern/                         # 🤖 현대 AI/자동화 측 자료 및 분석
│   ├── _index.md
│   ├── sources/
│   │   ├── bibliography.md
│   │   └── ...                        # 개별 문헌 노트
│   ├── topics/
│   │   ├── automation-scope.md        # 자동화 범위와 속도
│   │   ├── labor-displacement.md      # 노동 대체 현황
│   │   ├── gig-economy.md            # 긱 이코노미와 포트폴리오 소득
│   │   ├── wealth-concentration.md    # 부의 집중 (빅테크)
│   │   ├── ubi-debate.md             # UBI 논쟁
│   │   ├── political-polarization.md  # 정치적 양극화
│   │   └── aggregate-demand.md        # 총수요 문제
│   └── data/                          # 데이터·통계 자료
│       └── ...
│
├── 03-comparison/                     # ⚖️ 비교 분석 (프로젝트의 핵심)
│   ├── _index.md
│   ├── framework.md                   # 비교 프레임워크 (방법론)
│   ├── by-dimension/                  # 차원별 비교
│   │   ├── labor-replacement.md       # 노동 대체의 메커니즘
│   │   ├── economic-agents.md         # 경제주체별 비교
│   │   ├── wealth-concentration.md    # 자본/토지 집중
│   │   ├── social-mobility.md         # 사회적 이동성
│   │   ├── consumption-demand.md      # 소비와 총수요 ⭐ (핵심 차이점)
│   │   ├── political-response.md      # 정치적 대응
│   │   ├── adaptation-speed.md        # 적응 속도 ⭐ (핵심 차이점)
│   │   └── institutional-capacity.md  # 제도적 역량
│   ├── by-actor/                      # 행위자별 비교
│   │   ├── smallholder-vs-worker.md   # 소농 ↔ 현대 노동자
│   │   ├── slave-vs-ai.md            # 노예 ↔ AI/로봇
│   │   ├── elite-vs-bigtech.md       # 원로원 귀족 ↔ 빅테크/자본
│   │   ├── freedmen-vs-reskilled.md  # 해방노예 ↔ 재교육 노동자
│   │   └── state-vs-state.md         # 로마 국가 ↔ 현대 국가
│   ├── false-analogies.md            # ⚠️ 잘못된 유추 경고 목록
│   └── synthesis.md                   # 종합 비교표 (현재 버전)
│
├── 04-implications/                   # 💡 함의와 교훈
│   ├── _index.md
│   ├── survival-strategies.md         # 서민/노동자의 생존전략
│   ├── policy-lessons.md             # 정책적 교훈
│   ├── institutional-design.md       # 제도 설계 시사점
│   └── open-questions.md             # 미해결 질문들
│
├── 05-journal/                        # 📓 연구 일지 (선택적)
│   ├── 2026-02-17.md                 # 날짜별 연구 노트
│   └── ...                            # Claude 대화에서 나온 인사이트 기록
│
└── assets/                            # 이미지, 다이어그램 등
    ├── diagrams/
    └── images/
```

---

## 3. Git 워크플로우

### 브랜치 전략

```
main                        ← 검증된 내용만 머지. "출판 가능" 상태 유지
├── research/rome-peasant   ← 로마 소농 관련 자료 수집·분석 작업
├── research/ai-labor       ← 현대 AI/노동 관련 자료 수집·분석 작업
├── compare/consumption     ← 특정 비교 차원 심화 탐구
├── compare/political       ← 정치적 대응 비교 탐구
├── draft/synthesis-v2      ← 종합 비교표 개선 작업
└── archive/dead-ends       ← 탐구했으나 유의미하지 않았던 방향 (삭제 대신 보존)
```

### 커밋 메시지 컨벤션

```
[분류] 간단한 설명

분류 태그:
  [source]    새 자료 추가 또는 문헌 노트 작성
  [analysis]  분석·해석 작성 또는 수정
  [compare]   비교 분석 작성 또는 수정
  [meta]      프로젝트 구조, 로드맵, 방법론 변경
  [fix]       오류 수정, 사실관계 정정
  [journal]   연구 일지 기록
  [refactor]  문서 구조 개편 (내용 변경 없이)

예시:
  [source] Bowes 2025 문헌 노트 작성 — 소농 포트폴리오 소득 핵심 논점 정리
  [analysis] 해방노예 사회이동 경로 분석 추가 (manumission-mobility.md)
  [compare] 소비/총수요 차원 비교 초안 — AI의 비소비성이 핵심 차이점
  [journal] 2026-02-17 Claude 대화에서 도출된 핵심 인사이트 5개 정리
  [fix] Scheidel 해방률 수치 오류 수정 (10%/5년 → 출처 재확인)
```

### 태그 (마일스톤)

```
v0.1  프로젝트 구조 수립 + 기존 대화 내용 이관
v0.2  로마 측 기초 자료 정리 완료
v0.3  현대 측 기초 자료 정리 완료
v0.4  비교 프레임워크 확립
v0.5  차원별 비교 초안 완성
v1.0  1차 종합 — 핵심 논지 확립
...
```

---

## 4. 추천 VSCode 익스텐션

```jsonc
// .vscode/extensions.json
{
  "recommendations": [
    // 마크다운 편집·미리보기
    "yzhang.markdown-all-in-one",        // 단축키, TOC 자동생성, 목록 편집
    "bierner.markdown-preview-github-styles", // GitHub 스타일 미리보기
    "bierner.markdown-mermaid",          // Mermaid 다이어그램 미리보기

    // 위키 링크·지식 그래프
    "foam.foam-for-vscode",             // ⭐ 핵심! 위키링크, 백링크, 그래프 뷰
                                         //    [[파일명]]으로 문서 간 연결
                                         //    지식 그래프 시각화

    // Git 관련
    "eamodio.gitlens",                   // 커밋 히스토리, 블레임, 비교
    "mhutchie.git-graph",               // 브랜치 시각화

    // 생산성
    "gruntfuggly.todo-tree",            // TODO/FIXME/QUESTION 태그 추적
    "bierner.markdown-checkbox",         // 체크박스 토글

    // 참고문헌 (선택)
    "james-yu.latex-workshop"            // BibTeX 관리 시 유용
  ]
}
```

### Foam 활용 핵심

Foam은 이 프로젝트의 핵심 도구. 문서 간 위키링크와 백링크를 통해
"연결된 지식 베이스"를 구축.

```markdown
<!-- 예: 01-rome/topics/slavery-labor-market.md 안에서 -->

## 노예와 자유민의 혼합 노동

[[temin-2004]]에 따르면 노예와 자유 계절노동자가 모든 직종에서
나란히 일했다. 이는 [[smallholder-economy]]에서 다룬 소농의
포트폴리오 소득 전략과 직접 연결된다.

해방 이후의 경로는 [[manumission-mobility]] 참조.
현대와의 비교는 [[slave-vs-ai]] 참조.

## 관련 항목
- [[consumer-revolution]] — 노예도 소비자였다는 논점
- [[false-analogies]] — "노예=AI" 등식의 위험
```

---

## 5. 즉시 실행 가능한 초기 작업 (v0.1)

### Step 1: 레포 초기화 + 구조 생성
```bash
mkdir rome-ai-labor-study && cd rome-ai-labor-study
git init
# 위 디렉토리 구조대로 폴더·파일 생성
git add -A
git commit -m "[meta] 프로젝트 초기 구조 수립"
git tag v0.1-skeleton
```

### Step 2: 기존 대화 내용 이관 (가장 중요!)
지금까지의 Claude 대화에서 나온 내용을 해당 파일에 배분:

| 대화 내용 | 이관 대상 파일 |
|---|---|
| 자영농 몰락 전통 서사 | `01-rome/topics/smallholder-economy.md` |
| Rosenstein, De Ligt, Bowes 등 수정주의 | `01-rome/debates/traditional-vs-revisionist.md` |
| 소농의 식생활·건강·소비 | `01-rome/topics/diet-health.md`, `consumer-revolution.md` |
| 소농과 노예의 관계 | `01-rome/topics/slavery-labor-market.md` |
| 해방과 사회이동 | `01-rome/topics/manumission-mobility.md` |
| 로마 vs AI 비교표 | `03-comparison/synthesis.md` |
| 잘못된 유추 경고 | `03-comparison/false-analogies.md` |
| 참고문헌 정보 | `01-rome/sources/` 아래 개별 파일 |

```bash
# 내용 이관 후
git add -A
git commit -m "[meta] 기존 Claude 대화 내용 이관 — 로마 소농, 비교표, 참고문헌"
git tag v0.1
```

### Step 3: 핵심 연구 질문 정리
`00-meta/research-questions.md`에 현재 시점의 질문 목록 작성:

```markdown
# 핵심 연구 질문

## 대질문
1. 로마의 노예 노동력 도입과 현대 AI/자동화는 구조적으로
   어떤 점에서 비교 가능하고, 어떤 점에서 비교 불가능한가?

## 하위 질문
### 경제적 차원
- Q1: 소농의 "적응"은 어디까지가 자발적 전략이고,
       어디부터가 강요된 하향 이동이었나?
- Q2: 노예의 비소비성(AI) vs 소비성(노예)이
       거시경제에 미치는 영향 차이는 어느 정도인가?
- Q3: ...

### 정치적 차원
- Q4: 그라쿠스의 개혁 실패 → 폭력의 정상화 패턴이
       현대 정치에서 재현되고 있는가?
- Q5: ...

### 생존전략 차원
- Q6: 로마 소농의 포트폴리오 소득 전략에서
       현대 긱워커가 배울 수 있는 것은 무엇인가?
- Q7: ...

> 이 목록은 연구가 진행되면서 계속 업데이트됩니다.
> 질문이 추가/삭제/수정될 때마다 커밋으로 추적합니다.
```

---

## 6. 지속적 작업 패턴

```
1) Claude 대화 세션
   └→ 특정 주제 심화 탐구 (예: "곡물 배급 vs UBI 비교")

2) 대화 후 VSCode에서 정리
   └→ 해당 .md 파일에 내용 추가/수정
   └→ Foam 위키링크로 관련 문서 연결
   └→ 커밋 + 적절한 태그

3) 주기적 리뷰 (1~2주 단위)
   └→ roadmap.md 업데이트
   └→ 새로 떠오른 질문 research-questions.md에 추가
   └→ synthesis.md (종합 비교표) 갱신
   └→ 마일스톤 태그
```

---

## 7. 선택적 확장

- **GitHub Pages / MkDocs**: 마크다운을 정적 사이트로 빌드하여 웹 공개
- **Mermaid 다이어그램**: 인과관계도, 타임라인 등 시각화
- **BibTeX 연동**: Zotero/JabRef로 참고문헌 체계 관리
- **GitHub Issues**: 미해결 질문이나 탐구 과제를 이슈로 관리
- **GitHub Projects (칸반)**: 로드맵을 칸반 보드로 시각화
