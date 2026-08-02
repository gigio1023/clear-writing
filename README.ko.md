# clear-writing

[![skills.sh](https://skills.sh/b/gigio1023/clear-writing)](https://skills.sh/gigio1023/clear-writing)
![prose](https://img.shields.io/badge/prose-EN%20%7C%20KO%20%7C%20IT%20%7C%20ZH-22684E)
![package](https://img.shields.io/badge/SKILL.md-router%20%2B%2019%20references-555)
[![license](https://img.shields.io/badge/license-MIT-555)](LICENSE)

문서에서 AI slop을 걷어내면서 원문의 의미와 저자 목소리를 보존합니다. 이
스킬에서 slop은 작성 주체를 가리키는 표지가 아닙니다. 그럴듯하게 완성하려는
압력이 선택, 근거, 독자 맥락, 관점을 밀어낸 기능적 글쓰기 결함입니다.

`clear-writing`은 휴머나이즈와 deslop 작업을 중심으로 README, 가이드, 스펙,
ADR, 메모, 위키, 블로그 초안을 다룹니다. 일반 문법과 관용 표현은 LLM의 기본
언어 능력에 맡깁니다. 스킬에는 AI slop 진단, 근거 경계, 목소리 보호, 최소 수정
판정처럼 기본 유창성만으로 지키기 어려운 규칙을 남깁니다.

[구조](#구조) · [언어 오버레이](#언어-오버레이) · [근거](#근거와-계보) ·
[패키지](#패키지-구조) · [설치](#설치) · [개발](#로컬-개발)

## 구조

`SKILL.md`는 라우터입니다. 독자 과업, 근거 경계, 수정 권한, 저장소 정책, 저자
샘플을 확인합니다. 공통 slop 진단은 항상 불러옵니다. 언어별 오버레이는 후보
표현이 해당 언어나 지역 규칙에 걸릴 때만 불러옵니다.

| 작업 | 범위 | 주 reference |
|---|---|---|
| Authoring | 새로 쓰거나 사실을 크게 갱신하는 근거 기반 문서 | `references/authoring.md` |
| Revision | 휴머나이즈, 재구성, 메모의 독립 문서화 | `references/revision.md` |
| Focused pass | 용어 또는 언어별 slop 패턴 점검 | `references/terminology.md`나 언어 오버레이 하나 |

공통 계층은 네 가지 실패를 진단합니다.

- 다른 문서에도 그대로 들어갈 수 있는 일반적 완성
- 출처가 세우지 않은 관계를 인용과 연결어로 연기하는 추론
- 템플릿, 숨은 세션 맥락, 곁가지가 독자 과업을 밀어내는 구조
- 안전하고 균일한 문장으로 저자 목소리를 평탄화하는 수정

후보 표현은 독자 과업, 근거, 삭제했을 때 잃는 정보, 저자의 반복된 선택으로
검사합니다. 사실, 조건, 요구 수준, 논리 관계, 불확실성을 보존하며 구체 내용을
지어내지 않습니다.

검색 스니펫, 다른 문서의 출처 목록, 생성형 요약, 로컬 조사 메모는 원문을 찾는
단서입니다. 원 출처의 권위를 넘겨받지 않습니다. 냉독은 문서의 자기완결성을
점검하지만 사실 정확성을 증명하거나 실제 독자 검사를 대신하지 않습니다.

## 언어 오버레이

| 계층 | 더하는 기준 | 주장하지 않는 것 |
|---|---|---|
| 영어 | 공식적인 수사 구조, 근거 없는 `-ing` 관계, 과장된 중요성, 격식 평탄화 | 영어 문체 전반을 가르치는 규칙 |
| 한국어 | 한국어 근거와 keep test를 붙인 `im-not-ai` 패턴 묶음 | 모든 문장과 패턴 ID를 훑는 필수 검사 |
| 이탈리아어 | 공식적 연결어, 행정 문체의 무게, 번역 간섭, 수정 중 의미 보호 | 이탈리아어 문법 교본이나 고정 AI 표현 목록 |
| 중국어 | 병렬 표현 팽창, 공문식 골격, 지역 변환이 필요한 경우의 안전 규칙 | 일반 교정이나 요청하지 않은 현지화 |

그 밖의 언어에서는 LLM의 문맥 유창성에 공통 진단, 저자 샘플, 해당 지역 규칙을
더합니다. 허가된 개고 중 답이 하나뿐인 명백한 오류는 조용히 고칠 수 있습니다.
문법 검사만 요청한 작업에는 이 스킬을 쓰지 않습니다. 영어 규칙도 번역하지
않습니다.

`references/core-rules.md`의 선택형 블록은 한국어 상시 답변 계층입니다. 영어,
이탈리아어, 중국어의 생성 기준이 아닙니다.

## 근거와 계보

[출처와 영감 문서](docs/sources-and-inspiration.md)는 각 자료의 확인 버전,
출처 상태나 라이선스, 채택한 통찰, 적용 범위, 기각한 아이디어를 기록합니다.
`im-not-ai`, `petergyang/no-ai-slop`, 로컬 `brain/clips`와 `brain/research`,
공식 언어 지침과 쉬운 글쓰기 지침, 중국어 지역별 표준, 모델 보조 수정과 생성
문체 연구를 포함합니다.

[설계와 계보 기록](docs/merge-notes.md)은 이전 스킬을 통합한 과정을 설명합니다.
[재설계 계획](docs/redesign-plan.md)은 과거 설계 기록입니다.
[평가 프롬프트](docs/eval-prompts.md)는 가벼운 트리거와 보존 점검을 담으며
벤치마크 결과가 아닙니다.

## 패키지 구조

```text
clear-writing/
├── README.md
├── README.ko.md
├── LICENSE
├── docs/                   # 출처와 설계 기록, 설치 대상 아님
└── clear-writing/          # 설치되는 스킬 하나
    ├── SKILL.md
    └── references/         # 19개, 작업과 언어에 따라 로드
```

패키지는 [Agent Skills 형식](https://agentskills.io/)을 따르고
[Skills CLI](https://github.com/vercel-labs/skills)로 배포합니다. 이식 가능한
코어에는 Codex나 Claude Code 한쪽에만 맞춘 흐름을 넣지 않습니다.

## 설치

Node.js 22.20.0 이상이 필요합니다.

```bash
npx --yes skills add 'gigio1023/clear-writing#main' \
  --skill clear-writing \
  --agent codex claude-code \
  --global \
  --yes
```

에이전트 ID는 필요에 따라 바꿉니다. `cursor`, `gemini-cli`, `antigravity`도
지원합니다. 프로젝트에만 설치하려면 `--global`을 뺍니다. 설치 확인은
`npx --yes skills list --global`, 갱신은
`npx --yes skills update clear-writing --global --yes`를 씁니다.

## 로컬 개발

```bash
npx --yes skills add . --list --full-depth
```

공개하기 전에 명령이 `clear-writing` 하나만 찾는지, frontmatter와 폴더 이름이
같은지, 모든 reference 링크가 존재하는지, 두 README가 같은 패키지를 설명하는지
확인합니다.
