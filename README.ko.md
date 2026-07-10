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

## 이 skill이 개선하는 것

나쁜 AI 글은 보통 두 층에서 동시에 망가집니다.

1. **문장 수준의 slop**
   - vague label 남발
   - placeholder actor 사용
   - false agency와 과장된 표현
   - 기계적인 리듬
2. **문서 수준의 약함**
   - 부족한 맥락
   - 약한 흐름
   - 흔들리는 용어
   - 원래 대화를 알아야만 이해되는 전개

`humanize-doc`는 이 둘을 함께 고쳐서 결과물이 더 읽히고, 더 믿을 만하고, 원래 채팅 바깥에서도 쓸 수 있게 만듭니다.

## 예시: 문장 수준 수정

**AI 티가 나는 초안**

```text
This initiative enables cross-functional alignment and drives strategic clarity across key stakeholders.
```

**더 나은 출력**

```text
This document explains who owns the rollout, what changes this week, and which teams need to review it before launch.
```

## 예시: 문서 수준 수정

**약한 메모 덤프**

```text
- metrics weird
- auth issue maybe cache
- users saw old dashboard
- fix before friday
```

**더 나은 출력**

```text
Users saw stale dashboard data, and the metrics also looked unusual. The cause is
not confirmed; the notes suggest the authentication cache may be involved. We
should investigate that hypothesis and fix the issue before Friday.
```

## 이런 작업에 맞습니다

- AI스럽게 들리는 문장 humanize
- 거친 메모를 standalone 문서로 재구성
- 사실은 유지하고 톤만 자연스럽게 개선
- 구조와 문장을 한 번에 다시 쓰기

## 맞지 않는 작업

- 번역
- fact-checking이나 웹 검증
- 새로운 도메인 전문지식이 필요한 리뷰
- 구조는 충분히 괜찮고 문법만 손보면 되는 경우

## 모드

- `correction` — 문장 톤과 prose 중심 수정. 단순 `humanize` 요청의 기본값
- `compose` — 메모를 문서로 재구성
- `hybrid` — 문장과 문서 구조에 모두 문제가 있거나 둘 다 요청한 경우

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
