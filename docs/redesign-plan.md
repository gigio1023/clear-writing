# clear-writing 재설계 계획 (P1 산출물, 2026-07-26)

> 상태: 이 문서는 초기 설계를 보존한 historical 기록이며 현재 실행
> 계획으로는 superseded 상태다. 하단의 보류 표기를 현재 결정으로 읽지
> 않는다. D4는 후속 구현에서 해결했다. 한국어 답변 수칙 15개를
> `slop-aware-writing/references/core-rules.md`의 당시
> `clear-writing:core v1` 블록으로
> 당시 상시 계층을 구성했다. 현재 정본은 v2며 상시 계층 반영은
> 설치자가 별도로 갱신해야 한다. 현재 작동 규약은
> `slop-aware-writing/SKILL.md`와 `slop-aware-writing/references/`를 따른다.
> 설치 마커는 배포 호환성을 위해 기존 이름을 유지한다. 아래 본문은 2026-07-26 당시의
> 계획과 미해결 상태를 설명하므로 고치지 않았다.
> 2026-08 다국어 재설계에서는 아래의 `known-slop-terms.md`와
> `replacement-patterns.md`를 중복된 과거 목표로 판정하고 현재의
> `terminology-catalog.md`로 합쳤다. 영어, 이탈리아어, 중국어 계층도 이후
> 추가됐다. 아래 트리는 현재 패키지 목록이 아니다.

이 문서는 통합 스킬 `clear-writing` 저작(P2)의 입력이다. 배경·근거·전체 로드맵의
정본은 워크스페이스의 `notes/humanize-consolidation/launch-brief.md`와 계획
아티팩트에 있다. 여기에는 P2가 그대로 따라 할 수 있는 것만 담는다:
목표 레포 구조, 규칙 단위 이관 매트릭스, 트리거 시뮬레이션.

결정 전제 (P0 확정): 이름 `clear-writing`(스킬=레포=디렉터리), 정본은 이 레포,
회사/개인 구분 없음(엄격 프로파일로 수용), python-docstrings·english-prompt-review
제외, 코어 수칙의 상시 계층 기재는 최종 완성 후 결정(D4 보류).

## 1. 목표 레포 구조

```
clear-writing/                      # 레포 루트
├── clear-writing/                  # 설치되는 스킬 패키지 (유일)
│   ├── SKILL.md                    # 라우터, 200줄 이하
│   └── references/
│       ├── core-rules.md           # 상시 코어 정본 (초안, D4 보류 표기)
│       ├── authoring.md            # 레포 기반 문서 작성·수정
│       ├── templates.md            # 문서 모양 메뉴 (원본 그대로 이관)
│       ├── doc-patterns.md         # 기술 문서 문제·수리 사례 (원본 그대로 이관)
│       ├── revision.md             # 기존 텍스트 개선 워크플로
│       ├── anti-slop-core.md       # 언어 중립 AI-tell 지속 신호
│       ├── structure-anti-patterns.md  # 구조 단위 장황함 (영/한 예시 병합)
│       ├── voice-preservation.md   # 신규: 저자 목소리 보존
│       ├── terminology.md          # 용어 판정 워크플로
│       ├── known-slop-terms.md     # 용어 감시 목록 (원본 그대로 이관)
│       ├── replacement-patterns.md # 용어 교체 후보 (원본 그대로 이관)
│       ├── verification-procedure.md # 용어 근거 조사 절차 (원본 그대로 이관)
│       ├── korean-tells.md         # 한국어 문장 단위 패턴 (upstream v2.3 재동기화)
│       ├── profiles.md             # 신규: 기본/엄격 프로파일
│       └── gates.md                # 납품 게이트
├── docs/                           # 지원 문서 (스킬 페이로드 아님)
│   ├── redesign-plan.md            # 이 문서
│   ├── merge-notes.md              # 계보 기록 (갱신 예정)
│   └── eval-prompts.md             # 평가 시드 (P3에서 확장)
├── humanize-doc/                   # 구 스킬 — P2 완료·검증 후 제거
├── README.md / README.ko.md        # P2에서 재작성
└── (레포 관리 파일)
```

원칙: 이미 좋은 원본 파일은 다시 쓰지 않고 그대로 이관한다(templates,
doc-patterns, 용어 refs 3종). 새로 쓰는 것은 라우터, core-rules,
voice-preservation, profiles, 그리고 병합이 필요한 파일들뿐이다.
`npx skills add . --list --full-depth`가 `clear-writing` 하나만 보고해야 한다
(구 humanize-doc/ 제거 이후).

## 2. 이관 매트릭스 (규칙 단위 keep / merge / drop)

### 출처 A — humanize-doc (이 레포의 구 스킬)

| 원 위치 | 내용 | 처분 | 목적지 |
| --- | --- | --- | --- |
| SKILL.md 모드 3종(correction/compose/hybrid) | 모드 선택 로직 | merge — "revision 작업의 내부 판단"으로 격하, 이름은 버림 | revision.md |
| SKILL.md Core Diagnosis(추상화 인플레이션 + 독자 맥락) | 2축 진단 | keep — revision의 진단 프레임 | revision.md |
| SKILL.md Medium Calibration | 매체별 강도 | keep | revision.md |
| SKILL.md Non-Negotiables, Output Behavior | 불변 원칙, 출력 규칙 | merge — 통합 불변 원칙으로 | SKILL.md |
| references/anti-slop-patterns.md | 문장 슬롭 5범주 | merge — 지속 신호 중심으로 재편, stop-slop 패턴명 추가 | anti-slop-core.md |
| references/document-modes.md | 모드 선택 사례 | drop — revision.md 본문 몇 줄로 충분 | — |
| references/output-contract.md | 독립 문서 규칙, 매체 가드레일 | merge | revision.md |
| references/readability-gates.md | 납품 게이트 6종 | merge | gates.md |
| docs/merge-notes.md | 계보 기록 | keep(문서) — clear-writing 계보로 갱신 | docs/ |

### 출처 B — engineering-docs (agent-skills 현행판이 정본)

| 원 위치 | 내용 | 처분 | 목적지 |
| --- | --- | --- | --- |
| SKILL.md Modes(create/structure/review) | 작업 모드·권한 | merge — 통합 인테이크의 권한 규칙으로 | SKILL.md + authoring.md |
| SKILL.md Document Jobs 표 | 독자 과업 6종 | keep | authoring.md |
| SKILL.md Five Zoom Levels | 문장~페이지 구조 수리 | keep | authoring.md |
| SKILL.md Content and Editing Contract | 사실 보존·형식 선택 | keep | authoring.md |
| SKILL.md Verification | 경로·명령·링크 검증 | merge | gates.md |
| TEMPLATES.md / PATTERNS.md | 문서 모양 메뉴, 사례 | keep — 그대로 이관 | templates.md, doc-patterns.md |
| CHECKLIST.md | 납품 체크 | merge — readability-gates와 병합 | gates.md |
| references/style-zoom-rules.md | 구조 휴리스틱 | merge | authoring.md 부속 또는 유지 |
| references/style-anti-patterns.md | 장황함 실패 사례 | merge — V-패턴과 병합 | structure-anti-patterns.md |

### 출처 C — terminology-review (agent-skills 현행판이 정본)

| 원 위치 | 내용 | 처분 | 목적지 |
| --- | --- | --- | --- |
| SKILL.md Decision Test, 분류(keep/replace/rewrite/uncertain) | 용어 판정 | keep | terminology.md |
| SKILL.md Anchor New Names To Real Systems | 새 이름은 실물 시스템 어휘로 | keep — 고유 가치 높음 | terminology.md |
| SKILL.md Evidence Proportional / 외부 페이지 불신 규칙 | 근거 규모 조절 | keep | terminology.md |
| references 3종 | 감시 목록, 교체 후보, 조사 절차 | keep — 그대로 이관 | known-slop-terms.md 외 2 |
| 회사 anti-ai-slop-terminology 전체 | 전신 | drop — 현행판이 상위 호환 | — |

### 출처 D — im-not-ai (회사) + upstream epoko77-ai/im-not-ai v2.3

| 원 위치 | 내용 | 처분 | 목적지 |
| --- | --- | --- | --- |
| quick-rules A(번역투 19종), B(영어 인용), D(관용구), F(수식), G(hedging), H(접속사), I(형식명사) | 문장 단위 패턴 | merge — upstream v2.3 기준 재동기화. 패턴 ID 유지, 근거를 외부 실측 / 비재현 자체 연구 / 한국어 문체로 구분 | korean-tells.md |
| A-2 "~를 통해", I-1 "것이다" | upstream 2026-07 실증에서 AI-tell 기각 | keep(강등) — AI-tell 아님·번역투 문체 근거만 남김(국립국어원). S1 금지 | korean-tells.md |
| C(구조), E(리듬) 중 C-11 연결어미 뒤 쉼표, C-8 대구, E-1/2 리듬 | 외부 연구와 비재현 상류 자체 연구를 구분한 검토 우선순위 | keep — 코어 수칙과 상호 참조 | korean-tells.md |
| E-6 (POS 다양성 metric) | 계량 지표 | drop — LLM 눈대중 윤문에 부적합(원 스킬도 보조로만 둠) | — |
| verbosity V-1~V-16 | 구조 단위 장황함 | merge — 언어 중립 개념은 영/한 예시로 일반화, style-anti-patterns와 병합. V-13(가이드 톤 허용), V-15(WHY 한 문장 보존) 같은 보존 규칙 필수 유지 | structure-anti-patterns.md |
| rewrite-recipes.md | before/after 사례 | merge — korean-tells 사례 절로 압축 | korean-tells.md |
| J-0(em-dash·가운뎃점·불릿 0회), K(업무 slang 금지) | 회사 하우스 스타일 | move — 탐지 룰 아님을 명시하고 프로파일로 | profiles.md(strict) |
| 워크플로(invariants→진단→수술→diff 증거→보고), 등급·변경률 합격선 금지 | 편집 규율 | keep — 통합 revision/pass 공통 규율로 | SKILL.md + gates.md |
| upstream-*.md 스냅샷 3종 | v2.0 사본 | drop — 재동기화로 대체, 분기별 델타 절차만 문서화 | korean-tells.md 머리말 |
| dev-doc-style 전체 | 전신 | drop — engineering-docs가 상위 호환 | — |

### 출처 E — 조사 신규 유입 (5레인)

| 유래 | 내용 | 목적지 |
| --- | --- | --- |
| van Nuenen 2026, blader Voice Calibration | 축약형·1인칭·기능어·인과 사슬 보존, 사용자 샘플이 룰보다 우선 | voice-preservation.md |
| upstream 사고 사례 | 제거만, 삽입 금지 | SKILL.md 불변 원칙 |
| pilcrow | editor slop test(내 출력도 같은 텔 검사), "voice trumps rule" | gates.md, voice-preservation.md |
| 생태계 공통(DaleSeo, moai) | 변경률 가드 30% 경고 / 50% 중단 | gates.md |
| Wikipedia Signs of AI writing, 논문 | 지속 신호 우선, 빈도 임계값(단건 무시·군집 발화), 미신 배제 목록 | anti-slop-core.md |
| KatFishNet, 국립국어원 | 한국어 규칙의 근거 표기 | korean-tells.md, core-rules.md |

## 3. 트리거 시뮬레이션 (12종)

description 초안(P2에서 확정): "산문 문서의 작성·정리·윤문·용어 작업 전반.
Use when creating, restructuring, rewriting, humanizing, or reviewing prose
documents (README, guides, specs, memos, wiki, 기술 문서) in English or
Korean, including de-AI-ifying tone, terminology naturalization, and turning
notes into standalone docs. NOT for Python docstrings, prompt coaching,
diagrams, PR/commit copy, or translation."

| # | 요청 | 발화 | 통합 전 문제 |
| --- | --- | --- | --- |
| 1 | "README 정리해줘" | clear-writing (authoring) | 3파 경합 |
| 2 | "이 문서 AI 티 빼줘" | clear-writing (revision) | 2파 경합 |
| 3 | "이 노트를 문서로 만들어줘" | clear-writing (revision·compose) | 2파 경합 |
| 4 | "한국어 기술문서 윤문해줘" | clear-writing (pass: korean) | 회사/개인 이원화 |
| 5 | "용어 이상한 거 없나 봐줘" | clear-writing (pass: terminology) | 별도 스킬 |
| 6 | "API 문서 새로 써줘" | clear-writing (authoring) | 별도 스킬 |
| 7 | "블로그 초안 다듬어줘" | clear-writing (revision) | 2파 경합 |
| 8 | "이 함수 docstring 달아줘" | 발화 안 함 → python-docstrings | 경계 유지 |
| 9 | "영어 프롬프트 리뷰해줘" | 발화 안 함 → english-prompt-review | 경계 유지 |
| 10 | "PR 올려줘 / 커밋 메시지 써줘" | 발화 안 함 → draft-pr / commit-and-push | NOT-for 명시 |
| 11 | "아키텍처 다이어그램 그려줘" | 발화 안 함 → mermaid/drawio | NOT-for 명시 |
| 12 | "이 영어 문서 한국어로 번역해줘" | 발화 안 함 — 번역은 제외. 단, 이미 한국어인 글의 번역투 제거는 4번과 같음 | 경계 사례 문서화 |

경계 메모: "답변 좀 자연스럽게 써줘"처럼 대화 답변 자체에 대한 요청은 스킬이
아니라 상시 코어의 영역이다(스킬 로드 불필요).

## 4. P2 저작 순서와 남은 결정

저작 순서(의존성 기준): ① 그대로 이관 5종 복사 → ② korean-tells.md
(upstream v2.3 클론 대조 필요) → ③ 병합 3종(anti-slop-core,
structure-anti-patterns, gates) → ④ 신규 3종(voice-preservation, profiles,
core-rules 초안) → ⑤ revision.md, authoring.md, terminology.md →
⑥ SKILL.md 라우터 → ⑦ README 재작성.

P2 중 소결정(리드 재량, 기록만 남김): style-zoom-rules 유지 vs authoring.md
흡수, terminology refs의 압축 수준, korean-tells의 사례 분량.

P2 이후: P3 평가(문서 과업 6종 3안 비교 + 한국어 Q&A 코어 A/B + 실전 파일럿 2건)
→ P4 퇴역·배포(agent-skills에서 terminology-review·engineering-docs 제거,
agent-skills README의 humanize-doc 링크를 clear-writing으로 갱신, 구
humanize-doc/ 폴더 제거, 전 하네스 재설치, 회사 반입 zip 재포장, D4 결정).
