# humanize-doc

AI 티가 나는 초안, 거친 메모, 읽기 어려운 문서를 사람이 쓴 것처럼 읽히는 문서로 다시 쓰는 skill입니다.

이 repo는 `humanize-doc` skill을 패키징합니다. 핵심은 문장 수준의 AI slop과 문서 수준의 readability 문제를 같이 고치는 것입니다.

## Installation

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

### Claude Code

Claude Code에게 이렇게 말하세요:

```text
Fetch and follow instructions from https://raw.githubusercontent.com/gigio1023/humanize-doc/refs/heads/main/.claude/INSTALL.md
```

상세 문서: `docs/README.claude.md`

### Gemini CLI

Gemini CLI에게 이렇게 말하세요:

```text
Fetch and follow instructions from https://raw.githubusercontent.com/gigio1023/humanize-doc/refs/heads/main/.gemini/INSTALL.md
```

상세 문서: `docs/README.gemini.md`

### Cursor

Cursor에게 이렇게 말하세요:

```text
Fetch and follow instructions from https://raw.githubusercontent.com/gigio1023/humanize-doc/refs/heads/main/.cursor/INSTALL.md
```

상세 문서: `docs/README.cursor.md`

## 이런 작업에 맞습니다

- AI스럽게 들리는 문장 humanize
- 거친 메모를 standalone 문서로 재구성
- 사실은 유지하고 톤만 자연스럽게 개선
- 구조와 문장을 한 번에 다시 쓰기

## 이 skill이 해결하는 문제

`humanize-doc`는 보통 AI 글의 문제를 두 층으로 봅니다.

1. **문장 수준의 slop**
   - vague label
   - placeholder actor
   - false agency
   - 기계적인 리듬
2. **문서 수준의 약함**
   - 부족한 맥락
   - 약한 구조
   - 흔들리는 용어
   - 이전 채팅을 알아야만 이해되는 전개

이 skill은 둘 중 하나만 고치지 않고, 둘을 함께 고쳐서 결과물이 더 읽히고 더 믿을 만하게 보이도록 합니다.

## 모드

- `correction` — 문장 톤과 prose 중심 수정
- `compose` — 메모를 문서로 재구성
- `hybrid` — 둘 다 같이

## 핵심 reference

- `anti-slop-patterns.md`
- `document-modes.md`
- `output-contract.md`
- `readability-gates.md`

## 잘 맞는 요청 예시

- `이 전략 메모를 덜 AI스럽게 바꿔줘.`
- `이 회의 메모를 팀에 공유할 문서로 정리해줘.`
- `기술 내용은 유지하되 README를 더 읽기 쉽게 다시 써줘.`
- `사실과 불확실성은 유지하고, 문장만 사람이 쓴 것처럼 다듬어줘.`

## Repo layout

```text
humanize-doc/
├── docs/
└── humanize-doc/
    ├── SKILL.md
    └── references/
```
