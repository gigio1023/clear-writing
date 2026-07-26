# clear-writing

[![skills.sh](https://skills.sh/b/gigio1023/clear-writing)](https://skills.sh/gigio1023/clear-writing)

영어와 한국어 산문 문서 작업을 하나로 다루는 Agent Skill입니다. 저장소에
근거한 문서 작성, AI 티가 나는 초안 다듬기, 거친 메모의 독립 문서화, 용어
점검, 한국어 기술 문서의 수술적 윤문까지 사실관계는 유지하면서 처리합니다.

이 스킬은 [Agent Skills 형식](https://agentskills.io/)을 따르며 `SKILL.md`
라우터와 그 옆의 reference 파일들로 구성됩니다.
[`npx skills`](https://github.com/vercel-labs/skills)로 설치하고, 같은 추적
소스에서 이후 개정판을 받으세요.

[전환 상태](#humanize-doc에서의-전환) · [설치](#npx-skills로-설치) ·
[업데이트](#스킬-업데이트) · [구성](#구성) · [예시](#예시) ·
[근거와 계보](#근거와-계보) · [로컬 개발](#로컬-개발)

## humanize-doc에서의 전환

이 저장소는 2026-07-26에 `gigio1023/humanize-doc`에서 개명되었고, 이제 통합
스킬 `clear-writing`을 배포합니다. 여러 곳에 흩어져 있던 것을 하나로
합쳤습니다: `humanize-doc` 스킬(이 저장소), `terminology-review`와
`engineering-docs` 스킬(`gigio1023/agent-skills` 팩), 그리고
[`epoko77-ai/im-not-ai`](https://github.com/epoko77-ai/im-not-ai)와 동기화되는
한국어 수술 윤문 규칙 계열입니다.

전환 기간 동안:

- 구 `humanize-doc/` 패키지는 통합 스킬이 평가 단계를 통과할 때까지 이
  저장소에서 계속 설치 가능하며, 그 뒤 제거됩니다.
- `gigio1023/humanize-doc`을 가리키는 기존 설치 소스는 GitHub의 개명
  리다이렉트로 계속 동작하지만, 새 설치는 아래의 `gigio1023/clear-writing`
  소스를 사용하세요.
- `terminology-review`와 `engineering-docs`는 아직 `agent-skills`에서
  배포되며, 이 스킬이 대체를 마치면 그쪽에서 퇴역할 예정입니다.
  `clear-writing`과 함께 설치하지 마세요. 트리거가 의도적으로 겹칩니다.

## `npx skills`로 설치

현재 Skills CLI 릴리스 기준으로 Node.js 22.20.0 이상이 필요합니다.

설치 전에 공개 패키지를 확인합니다.

```bash
npx --yes skills add 'gigio1023/clear-writing#main' --list --full-depth
```

사용할 에이전트에 전역 설치합니다.

```bash
npx --yes skills add 'gigio1023/clear-writing#main' \
  --skill clear-writing \
  --agent codex claude-code \
  --global \
  --yes
```

필요에 따라 에이전트 ID를 바꾸면 됩니다. Skills CLI는 `cursor`,
`gemini-cli`, `antigravity` 등도 지원합니다. 프로젝트 안에만 설치하려면
`--global`을 빼세요.

따옴표로 묶은 `#main` 소스는 공개 브랜치를 명확히 지정하고, 이후 업데이트에
필요한 출처 정보를 CLI 잠금 파일에 남깁니다. 각 에이전트의 설치 위치는
CLI에 맡기세요. 이 저장소는 `.claude/`, `.codex/`, `.cursor/`, `.gemini/`
설치 어댑터를 따로 유지하지 않습니다.

설치 상태를 확인합니다.

```bash
npx --yes skills list --global
```

## 스킬 업데이트

```bash
npx --yes skills update clear-writing --global --yes
```

업데이트는 pull 기반이며 설치 시점에 기록된 원격 소스를 사용합니다. 이전
`humanize-doc` 설치가 미추적으로 나오거나 옛 소스에서 계속 갱신된다면,
제거한 뒤 위의 `gigio1023/clear-writing#main` 소스로 한 번 재설치하세요.

## 구성

`clear-writing/SKILL.md`는 얇은 라우터입니다. 산출물, 언어, 근거 기반,
수정 권한, 스타일 프로파일, 저자 글 샘플을 파악한 뒤 작업 유형을 고르고
그 작업에 필요한 reference만 로드합니다.

| 작업 | 범위 | 주 reference |
| --- | --- | --- |
| Authoring | 저장소 근거 기반의 README, 가이드, API 문서, ADR, 스펙 | `references/authoring.md` |
| Revision | 휴머나이즈, 재구성, 메모의 독립 문서화 | `references/revision.md` |
| Pass | 용어 점검, 한국어 문장 단위 윤문 | `references/terminology.md`, `references/korean-tells.md` |

알아둘 설계 지점:

- **근거 장부.** 규칙마다 근거 유형을 표기합니다: 실측 AI 판별 신호, 한국어
  문체 근거, 관측 전용 지표, 하우스 스타일. 상류 코퍼스 연구에서 기각된
  규칙은 조용히 유지하지 않고 조건화했습니다.
- **목소리 보존.** 리라이트 자체가 글을 동질화하므로, 제거만 하고 삽입하지
  않는 편집을 강제하고 저자의 voice 마커를 보호하며, 사용자가 준 글 샘플을
  모든 스타일 규칙보다 우선합니다.
- **납품 게이트.** 모든 산출물이 사실 보존 검사, 변경률 가드(30% 경고,
  50% 중단), 자기 출력에 대한 editor-slop 검사를 통과해야 합니다.
- **프로파일.** 하우스 스타일 강화(em-dash 금지, 업무 어휘)는 스킬의 분기가
  아니라 `references/profiles.md`의 선택 항목입니다.
- **상시 코어 초안.** `references/core-rules.md`는 상시 로드 계층용 한국어
  답변 수칙 14개의 초안을 보관합니다. 실제 설치 여부는 파일에 기록된 대로
  보류된 결정입니다.

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

통합과 규칙은 2026년 7월 조사에 기반합니다: 상류 저장소 감사, 글쓰기 스킬
생태계 조사, AI 텍스트 신호 학술 연구(ACL 2025의 KatFishNet, 어휘 과용과
리라이트 드리프트 연구), 한국어 번역투 학술 자료. 이관 매트릭스와 트리거
경계는 [docs/redesign-plan.md](docs/redesign-plan.md), 전체 계보는
[docs/merge-notes.md](docs/merge-notes.md)를 보세요.
[docs/eval-prompts.md](docs/eval-prompts.md)는 가벼운 트리거·보존 검사를
제공합니다.

## 패키지 구조

```text
clear-writing/
├── README.md
├── README.ko.md
├── docs/
│   ├── eval-prompts.md
│   ├── merge-notes.md
│   └── redesign-plan.md
├── clear-writing/          # 설치되는 스킬
│   ├── SKILL.md
│   └── references/         # 16개, 작업별 로드
└── humanize-doc/           # 구 패키지, 평가 후 제거
```

## 로컬 개발

업데이트 추적 없이 체크아웃을 검사합니다.

```bash
npx --yes skills add . --list --full-depth
```

전환 기간에는 목록에 두 패키지(`clear-writing`, 구 `humanize-doc`)가
보이고, 퇴역 후에는 정확히 하나만 보여야 합니다. 변경을 공개하기 전에
`SKILL.md` 이름이 폴더와 일치하는지, 참조된 경로가 모두 존재하는지, 이
문서와 `README.md`가 같은 설치 방법과 동작을 설명하는지 확인하세요.
