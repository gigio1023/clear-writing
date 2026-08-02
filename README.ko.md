# clear-writing

[![skills.sh](https://skills.sh/b/gigio1023/clear-writing)](https://skills.sh/gigio1023/clear-writing)
![prose](https://img.shields.io/badge/prose-EN%20%7C%20KO%20%7C%20IT%20%7C%20ZH-22684E)
![package](https://img.shields.io/badge/SKILL.md-router%20%2B%2019%20references-555)
[![license](https://img.shields.io/badge/license-MIT-555)](LICENSE)

처음 읽는 사람도 이해할 수 있고 근거보다 센 주장을 하지 않는 문서를 작성하고
고칩니다. 원문의 의미와 저자 목소리를 보존합니다. 영어식 문체 조언을 언어
공통 규칙으로 포장하지 않고 영어, 한국어, 이탈리아어, 중국어를 따로 다룹니다.

`clear-writing`은 README, 가이드, 스펙, API 문서, ADR, 메모, 위키, 블로그
초안을 다룹니다. 메모를 독립 문서로 엮고 오래됐거나 대화 세션에 기대는 문서를
고치며 용어와 상투적인 모델 보조 문체를 점검합니다. 문체만 보고 AI가 썼다고
판정하지 않습니다. 독자가 실제로 겪는 문제를 밝히고 의미를 보존할 수 있을
때만 고칩니다.

[구조](#구조) · [언어 계층](#언어-계층) · [근거](#근거와-계보) ·
[패키지](#패키지-구조) · [설치](#설치) · [개발](#로컬-개발)

## 구조

`SKILL.md`는 라우터입니다. 독자 과업, 언어와 지역, 근거 경계, 수정 권한,
저장소 정책, 저자 샘플을 확인합니다. 이후 공통 무결성 계층과 작업 흐름 하나,
각 문단에 맞는 언어 계층만 불러옵니다.

| 작업 | 범위 | 주 reference |
|---|---|---|
| Authoring | 새로 쓰거나 사실을 크게 갱신하는 근거 기반 문서 | `references/authoring.md` |
| Revision | 휴머나이즈, 재구성, 메모의 독립 문서화 | `references/revision.md` |
| Focused pass | 용어 또는 언어별 문장 점검 | `references/terminology.md`와 언어 계층 하나 |

공통 계층은 다음을 지킵니다.

- 근거 경계와 현재도 유효하며 주장을 실제로 뒷받침하는 출처
- 사실, 조건, 요구 수준, 논리 관계, 드러난 불확실성
- Codex, Claude Code, 이슈, PR 대화를 보지 못한 독자에게 필요한 맥락
- 문서의 독자 과업과 관계있는 내용
- 저자의 반복된 목소리와 필요한 만큼만 고치는 원칙
- 사실, 예시, 인용, 출처, 행위자, 구체 수치를 지어내지 않는 원칙

검색 스니펫, 다른 문서의 출처 목록, 생성형 요약, 로컬 조사 메모는 원문을 찾는
단서입니다. 원 출처의 권위를 넘겨받지 않습니다. 냉독은 문서의 자기완결성을
점검하지만 사실 정확성을 증명하거나 실제 독자 검사를 대신하지 않습니다.

## 언어 계층

| 계층 | 더하는 기준 | 주장하지 않는 것 |
|---|---|---|
| 영어 | 격식에 맞춘 능동과 수동 선택, 수사 패턴, `-ing` 연결, 표지어 밀도, 목소리 점검 | 단어 하나, 축약형, 대시, 문장 모양이 작성 주체를 증명한다는 주장 |
| 한국어 | `im-not-ai` 분류를 한국어 말뭉치와 번역투 근거에 연결한 keep test와 근거 등급 | 집단 차이로 문장 하나의 작성 주체를 판정하는 것 |
| 이탈리아어 | 쉼표의 의미 범위, `gerundio` 연결, 정보 흐름, 행정 문체, 번역 간섭 | 오래가는 이탈리아어 AI 표현 목록 |
| 중국어 | `zh-CN`, `zh-TW`, `zh-HK`를 먼저 정하는 문장 부호, 용어, 문자, 공문 계층 | 간체와 번체만 보고 지역을 정하는 것 |

그 밖의 언어에는 공통 무결성 계층, 저자 샘플, 해당 지역이나 출판물의 규칙만
적용합니다. 영어 표면 규칙을 번역해 근거 없는 탐지 목록을 만들지 않습니다.

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
