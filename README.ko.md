# clear-writing

[![skills.sh](https://skills.sh/b/gigio1023/clear-writing)](https://skills.sh/gigio1023/clear-writing)
![prose](https://img.shields.io/badge/prose-EN%20%C2%B7%20KO-22684E)
![package](https://img.shields.io/badge/SKILL.md-router%20%2B%2017%20references-555)
[![license](https://img.shields.io/badge/license-MIT-555)](LICENSE)

산문 문서 작업을 스킬 하나로 처리합니다. 근거에 기반한 문서 작성, AI 티를
걷어내는 개고, 용어 점검, 한국어 수술 윤문을 다루며 사실과 드러난 불확실성을
보존합니다.

하나로 묶은 이유는 원래 이 일들이 여러 스킬로 흩어져 있었고, "이 README 좀
정리해줘" 같은 요청 하나에 여러 스킬이 동시에 걸렸기 때문입니다. 이제 라우터
하나가 요청을 읽고 문서에 실제로 필요한 작업을 판단해 그 작업의 규칙만
로드합니다. 한국어는 영어 조언을 옮긴 것이 아니라 별도 계층입니다. 한국어
문서에는 문장 단위 패턴 레이어가 따로 붙고, 상류 분류 체계와 동기화하며
규칙마다 어떤 종류의 근거에 기대는지 표기합니다.

휴머나이즈와 표면 표현 정리는 삭제를 우선합니다. 새 문서를 쓰거나 메모를
문서로 엮거나 전체 개고할 때는 사용자 자료, 확인한 저장소 근거, 검증한 외부
출처가 뒷받침하는 맥락과 연결 논리만 더합니다. 사실, 예시, 인용문, 출처를
지어내지 않으며 어떤 글도 AI가 썼다고 단정하지 않습니다. 대신 문제가 되는
표현을 지적합니다.

[구성](#구성) · [예시](#예시) · [근거](#근거와-계보) ·
[구조](#패키지-구조) · [설치](#설치) · [개발](#로컬-개발)

## 구성

`SKILL.md`는 얇은 라우터입니다. 산출물, 언어, 근거 기반, 수정 권한, 스타일
프로파일, 저자 글 샘플을 파악한 뒤 필요한 reference만 로드합니다.

| 작업 | 범위 | 주 reference |
| --- | --- | --- |
| Authoring | 근거 경계를 명시한 README, 가이드, API 문서, ADR, 스펙 | `references/authoring.md` |
| Revision | 휴머나이즈, 재구성, 메모의 독립 문서화 | `references/revision.md` |
| Pass | 용어 점검, 한국어 문장 단위 윤문 | `references/terminology.md`, `references/korean-tells.md` |

설계 지점:

- **출처 근거.** 중요한 외부 주장은 출처가 해당 주장을 뒷받침하는지, 현재도
  유효한지, 직접 근거인지 추론인지 확인합니다. 검색 스니펫과 생성형 요약은
  조사 단서로만 씁니다.
- **한국어 근거 장부.** 한국어 패턴 규칙은 실측 AI 판별 신호, 한국어 문체
  근거, 관측 전용 진단을 구분합니다. 코퍼스 연구에서 기각된 규칙은 탐지
  신호로 제시하지 않고 조건을 붙입니다.
- **목소리 보존.** 표면 표현 정리는 삭제를 우선하며 새 문서 작성, 메모 구성,
  전체 개고는 근거 경계 안에서만 내용을 더합니다. 저자의 voice 마커를
  보호하고 사용자가 준 글 샘플이 모든 스타일 규칙보다 우선합니다.
- **납품 게이트.** 처음 읽는 독자의 이해, 주장과 근거의 연결, 사실 보존,
  변경률 가드(30% 경고, 50% 중단), 자기 출력에 대한 editor-slop을 검사합니다.
- **독자 과업에 맞는 형식.** 추론은 산문으로 씁니다. 목록, 표, 차트, 도식은
  짧은 산문보다 구조를 더 잘 보여줄 때만 사용합니다.
- **프로파일.** 하우스 스타일 강화(em-dash 금지, 업무 어휘)는 스킬의 분기가
  아니라 선택 항목입니다.
- **상시 코어.** 스킬은 필요할 때만 로드되므로 평소 답변까지 관장하지
  못합니다. 그 몫이 `references/core-rules.md`의 한국어 답변 수칙 15개입니다.
  마커로 감싼 블록을 상시 계층에 그대로 복사하면, 이후 갱신은 버전 마커
  기준으로 블록만 교체됩니다.

## 예시

문장 수준 개선:

```text
Before: The dashboard serves as a centralized hub for release status and
        functions as the team's primary source of deployment updates.
After:  The dashboard is the team's source for release status and deployment
        updates.
```

메모의 독립 문서화:

```text
Before: - users saw the old dashboard and wrong metrics
        - cause unconfirmed
        - investigate auth cache
        - fix before Friday
After:  Users saw the old dashboard and incorrect metrics. The cause is not
        confirmed. Investigate the authentication cache and fix the issue
        before Friday.
```

한국어 수술 윤문(사실, 명령어, 격식 보존):

```text
Before: 데이터를 정제하고, 모델을 학습시킨 다음, 결과를 검증합니다.
After:  데이터를 정제하고 모델을 학습시킨 다음 결과를 검증합니다.
```

## 근거와 계보

[출처와 영감 문서](docs/sources-and-inspiration.md)는 이 스킬에 영향을 준
프로젝트, 연구, 공식 지침, 메인테이너 자료의 확인 버전과 라이선스 또는 상태,
채택한 인사이트, 거부한 아이디어를 기록합니다.
[설계와 계보 기록](docs/merge-notes.md)은 이전 스킬을 통합한 과정을 설명합니다.
[재설계 계획](docs/redesign-plan.md)은 당시의 설계 상태를 보존하고
[평가 프롬프트](docs/eval-prompts.md)는 가벼운 트리거·보존 검사를 담습니다.

## 패키지 구조

```text
clear-writing/
├── README.md
├── README.ko.md
├── LICENSE                 # MIT
├── docs/                   # 설계 기록, 설치 대상 아님
└── clear-writing/          # 설치되는 스킬
    ├── SKILL.md
    └── references/         # 17개, 작업별 로드
```

패키지는 [Agent Skills 형식](https://agentskills.io/)을 따르고
[Skills CLI](https://github.com/vercel-labs/skills)로 배포됩니다. 저장소는
에이전트별 설치 어댑터를 두지 않습니다.

## 설치

Node.js 22.20.0 이상이 필요합니다.

```bash
npx --yes skills add 'gigio1023/clear-writing#main' \
  --skill clear-writing \
  --agent codex claude-code \
  --global \
  --yes
```

에이전트 ID는 필요에 따라 바꿉니다(`cursor`, `gemini-cli`, `antigravity`도
지원). 프로젝트 안에만 설치하려면 `--global`을 빼세요. 설치 확인은
`npx --yes skills list --global`, 이후 갱신은
`npx --yes skills update clear-writing --global --yes`.

따옴표로 묶은 `#main` 소스가 업데이트에 필요한 출처를 기록하고, 각
에이전트의 설치 위치는 CLI가 관리합니다.

## 로컬 개발

```bash
npx --yes skills add . --list --full-depth
```

변경을 공개하기 전에: 목록이 정확히 `clear-writing` 하나를 보고하는지,
`SKILL.md` 이름이 폴더와 일치하는지, 참조 경로가 모두 존재하는지, 이 문서가
`README.md`와 어긋나지 않는지 확인합니다.
