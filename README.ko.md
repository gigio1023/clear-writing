# humanize-doc

[English](README.md) | [한국어](README.ko.md)

AI 티가 나는 문장과 추상적인 표현을 줄이면서, 읽는 사람이 맥락 없이도 이해할 수 있는 문서를 만들기 위한 draft skill repo입니다.

이 초안은 두 갈래를 합칩니다.

- `stop-slop`에서 참고한 anti-slop 접근
- `human-readable-doc-composer`에 있던 문서 구성 아이디어

`humanize`는 외부 레퍼런스가 아니라 사용자 내부 자산으로 취급합니다. 즉, 이 repo의 외부 출처 기준점은 아니고, 인접한 내부 선행 작업으로 봅니다.

## Install

이 repo는 현재 private 입니다.

- `gigio1023/humanize-doc`에 접근 권한이 있으면 `npx skills add`로 설치할 수 있습니다
- private 상태에서는 public `skills.sh` 검색이나 leaderboard 노출을 기대하면 안 됩니다

### npx skills

repo를 직접 지정해서 설치:

```bash
npx skills add gigio1023/humanize-doc --skill humanize-doc
```

자주 쓰는 변형:

```bash
npx skills add gigio1023/humanize-doc --skill humanize-doc --agent codex
npx skills add gigio1023/humanize-doc --skill humanize-doc --agent claude-code
npx skills add gigio1023/humanize-doc --skill humanize-doc -g
```

메모:

- 기본 설치는 project-local 입니다
- `-g`를 붙이면 global 설치입니다
- private repo이므로 public `find`나 `skills.sh` discovery보다 direct `add`가 더 확실합니다

### Manual install

<details>
<summary>Claude Code</summary>

`humanize-doc` 폴더를 `~/.claude/skills/humanize-doc` 아래로 복사합니다:

```bash
mkdir -p ~/.claude/skills && \
git clone https://github.com/gigio1023/humanize-doc.git /tmp/humanize-doc && \
cp -r /tmp/humanize-doc/humanize-doc ~/.claude/skills/ && \
rm -rf /tmp/humanize-doc
```
</details>

<details>
<summary>Codex CLI</summary>

`humanize-doc` 폴더를 `~/.codex/skills/humanize-doc` 아래로 복사합니다:

```bash
mkdir -p ~/.codex/skills && \
git clone https://github.com/gigio1023/humanize-doc.git /tmp/humanize-doc && \
cp -r /tmp/humanize-doc/humanize-doc ~/.codex/skills/ && \
rm -rf /tmp/humanize-doc
```
</details>

<details>
<summary>Other agents</summary>

공용 `.agents/skills` 규약을 따르는 agent는 `~/.agents/skills/humanize-doc` 아래로 복사합니다:

```bash
mkdir -p ~/.agents/skills && \
git clone https://github.com/gigio1023/humanize-doc.git /tmp/humanize-doc && \
cp -r /tmp/humanize-doc/humanize-doc ~/.agents/skills/ && \
rm -rf /tmp/humanize-doc
```
</details>

수동 설치 규칙:

- `humanize-doc/` 폴더 자체를 복사합니다
- 폴더 이름은 `humanize-doc`로 유지합니다
- 사용하는 agent의 skills 디렉터리 아래에 둡니다

## Goal

이 skill의 목표는 보통 따로 취급되는 두 작업을 한 번에 다루는 것입니다.

1. "AI가 쓴 것처럼 안 들리게 만들기"
2. "사람이 실제로 읽고 쓸 수 있는 문서로 다시 쓰기"

핵심 가정은 둘이 사실 같은 문제의 다른 단면이라는 점입니다.

- 문장 수준 문제: label, placeholder, false agency, 기계적인 리듬
- 문서 수준 문제: 약한 흐름, 부족한 맥락, 불안정한 용어, 과도한 압축

## Repo layout

```text
humanize-doc/
  SKILL.md
  references/
    anti-slop-patterns.md
    document-modes.md
    output-contract.md
    readability-gates.md
docs/
  merge-notes.md
```

## Current scope

- Correction mode: 사실은 유지한 채 기존 문서를 다듬기
- Compose mode: 메모나 거친 초안을 standalone 문서로 재구성하기
- Hybrid mode: 대부분의 중간 길이 이상 문서에서 구조와 문장 둘 다 손보기

## Not in scope

- fact-checking이나 웹 검증
- 번역
- readability 문제 없이 문법만 고치는 작업
- 도메인 전문성 자체를 대신하는 작업

## Next draft questions

- 이걸 계속 하나의 skill로 둘지, `humanize` + `doc-compose`로 나눌지
- repo-specific terminology 정책을 어디까지 skill 본문에 넣고 어디까지 reference로 뺄지
- DM/email 같은 short-form 출력을 별도 하위 workflow로 둘지
