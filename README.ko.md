# humanize-doc

AI 티가 나는 초안이나 메모를 사람이 쓴 것처럼 읽히는 문서로 다시 쓰는 skill입니다.

`humanize-doc`는 문장 수준의 AI slop과 문서 수준의 readability 문제를 같이 고칩니다.

## Install

기본 설치:

```bash
npx skills add gigio1023/humanize-doc@humanize-doc
```

### Codex

Codex에게 이렇게 말하세요:

```text
Fetch and follow instructions from https://raw.githubusercontent.com/gigio1023/humanize-doc/refs/heads/main/.codex/INSTALL.md
```

상세 문서: `docs/README.codex.md`

## 이런 작업에 맞습니다

- AI스럽게 들리는 문장 humanize
- 거친 메모를 standalone 문서로 재구성
- 사실은 유지하고 톤만 자연스럽게 개선
- 구조와 문장을 한 번에 다시 쓰기

## 모드

- `correction` — 문장 톤과 prose 중심 수정
- `compose` — 메모를 문서로 재구성
- `hybrid` — 둘 다 같이

## 핵심 reference

- `anti-slop-patterns.md`
- `document-modes.md`
- `output-contract.md`
- `readability-gates.md`

## Repo layout

```text
humanize-doc/
├── docs/
└── humanize-doc/
    ├── SKILL.md
    └── references/
```
