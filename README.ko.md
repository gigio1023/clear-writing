# clear-writing

[![skills.sh](https://skills.sh/b/gigio1023/clear-writing)](https://skills.sh/gigio1023/clear-writing)
![prose](https://img.shields.io/badge/prose-EN%20%C2%B7%20KO-22684E)
![package](https://img.shields.io/badge/SKILL.md-router%20%2B%2016%20references-555)
[![license](https://img.shields.io/badge/license-MIT-555)](LICENSE)

산문 문서 작업을 스킬 하나로: 저장소에 근거한 문서 작성, AI 티를 걷어내는
개고, 용어 점검, 한국어 수술 윤문까지 사실관계는 그대로 두고 처리합니다.

하나로 묶은 이유는 원래 이 일들이 여러 스킬로 흩어져 있었고, "이 README 좀
정리해줘" 같은 요청 하나에 여러 스킬이 동시에 걸렸기 때문입니다. 이제 라우터
하나가 요청을 읽고 문서에 실제로 필요한 작업을 판단해 그 작업의 규칙만
로드합니다. 한국어는 영어 조언을 옮긴 것이 아니라 별도 계층입니다. 한국어
문서에는 문장 단위 패턴 레이어가 따로 붙고, 상류 분류 체계와 동기화하며
규칙마다 어떤 종류의 근거에 기대는지 표기합니다.

편집은 지우는 방향으로만 합니다. 원문이 뒷받침하지 않는 사실, 예시, 인용,
연결어를 새로 넣지 않고, 어떤 글도 AI가 썼다고 단정하지 않습니다. 대신
문제가 되는 표현 자체를 지적합니다.

[구성](#구성) · [예시](#예시) · [근거](#근거와-계보) ·
[구조](#패키지-구조) · [설치](#설치) · [개발](#로컬-개발)

## 구성

`SKILL.md`는 얇은 라우터입니다. 산출물, 언어, 근거 기반, 수정 권한, 스타일
프로파일, 저자 글 샘플을 파악한 뒤 필요한 reference만 로드합니다.

| 작업 | 범위 | 주 reference |
| --- | --- | --- |
| Authoring | 저장소 근거 기반의 README, 가이드, API 문서, ADR, 스펙 | `references/authoring.md` |
| Revision | 휴머나이즈, 재구성, 메모의 독립 문서화 | `references/revision.md` |
| Pass | 용어 점검, 한국어 문장 단위 윤문 | `references/terminology.md`, `references/korean-tells.md` |

설계 지점:

- **근거 장부.** 규칙마다 근거 유형을 표기합니다: 실측 AI 판별 신호, 한국어
  문체 근거, 관측 전용, 하우스 스타일. 코퍼스 연구에서 기각된 규칙은
  조건화하고 그대로 두지 않습니다.
- **목소리 보존.** 제거만 하고 삽입하지 않는 편집. 저자의 voice 마커를
  보호하고, 사용자가 준 글 샘플이 모든 스타일 규칙보다 우선합니다.
- **납품 게이트.** 사실 보존 검사, 변경률 가드(30% 경고, 50% 중단), 자기
  출력에 대한 editor-slop 검사.
- **프로파일.** 하우스 스타일 강화(em-dash 금지, 업무 어휘)는 스킬의 분기가
  아니라 선택 항목입니다.
- **상시 코어.** 스킬은 필요할 때만 로드되므로 평소 답변까지 관장하지
  못합니다. 그 몫이 `references/core-rules.md`의 한국어 답변 수칙 15개입니다.
  마커로 감싼 블록을 상시 계층에 그대로 복사하면, 이후 갱신은 버전 마커
  기준으로 블록만 교체됩니다.

## 예시

문장 수준 개선:

```text
Before: This initiative enables cross-functional alignment and drives
        strategic clarity across key stakeholders.
After:  This document explains who owns the rollout, what changes this week,
        and which teams need to review it before launch.
```

메모의 독립 문서화:

```text
Before: - metrics weird
        - auth issue maybe cache
        - users saw old dashboard
        - fix before friday
After:  Users saw stale dashboard data, and the metrics also looked unusual.
        The cause is not confirmed; the notes suggest the authentication cache
        may be involved. We should investigate that hypothesis and fix the
        issue before Friday.
```

한국어 수술 윤문(사실, 명령어, 격식 보존):

```text
Before: 데이터를 정제하고, 모델을 학습시킨 다음, 결과를 검증합니다.
After:  데이터를 정제하고 모델을 학습시킨 다음 결과를 검증합니다.
```

## 근거와 계보

규칙은 2026년 7월 조사에 기반합니다: 상류 저장소 감사, 글쓰기 스킬 생태계
조사, AI 텍스트 신호 학술 연구(ACL 2025의 KatFishNet, 어휘 과용과 리라이트
드리프트 연구), 한국어 번역투 학술 자료. 설계와 트리거 경계는
[docs/redesign-plan.md](docs/redesign-plan.md), 계보는
[docs/merge-notes.md](docs/merge-notes.md), 가벼운 트리거·보존 검사는
[docs/eval-prompts.md](docs/eval-prompts.md)에 있습니다.

## 패키지 구조

```text
clear-writing/
├── README.md
├── README.ko.md
├── LICENSE                 # MIT
├── docs/                   # 설계 기록, 설치 대상 아님
└── clear-writing/          # 설치되는 스킬
    ├── SKILL.md
    └── references/         # 16개, 작업별 로드
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
