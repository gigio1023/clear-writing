# humanize-doc

AI 티가 나는 초안, 거친 메모, 읽기 어려운 문서를 사람이 쓴 것처럼 읽히는 문서로 다시 쓰기 위한 writing skill입니다.

이 repo는 `humanize-doc` 하나를 패키징합니다. 역할은 분명합니다.

- AI 냄새가 나는 과장되고 추상적인 문장을 줄이기
- 원래 대화 맥락이 없어도 읽히는 문서 구조로 다시 세우기

즉, 단순 문법 교정이 아니라 **rewrite + readability**용 skill입니다.

## Installation

설치 방식은 플랫폼마다 조금 다르지만, 기본 원칙은 같습니다. 가능하면 먼저 skills ecosystem으로 설치하고, 직접 파일 복사가 필요할 때만 수동 설치를 사용합니다.

### Skills CLI

```bash
npx skills add gigio1023/humanize-doc@humanize-doc
npx skills add gigio1023/humanize-doc@humanize-doc -g
```

### Claude Code

```bash
mkdir -p ~/.claude/skills && \
  git clone https://github.com/gigio1023/humanize-doc.git /tmp/humanize-doc && \
  cp -r /tmp/humanize-doc/humanize-doc ~/.claude/skills/ && \
  rm -rf /tmp/humanize-doc
```

### Codex CLI

```bash
mkdir -p ~/.codex/skills && \
  git clone https://github.com/gigio1023/humanize-doc.git /tmp/humanize-doc && \
  cp -r /tmp/humanize-doc/humanize-doc ~/.codex/skills/ && \
  rm -rf /tmp/humanize-doc
```

### Other skills-compatible agents

```bash
mkdir -p ~/.agents/skills && \
  git clone https://github.com/gigio1023/humanize-doc.git /tmp/humanize-doc && \
  cp -r /tmp/humanize-doc/humanize-doc ~/.agents/skills/ && \
  rm -rf /tmp/humanize-doc
```

### Verify installation

새 세션을 열고, 문장 톤 수정과 문서 재구성이 동시에 필요한 요청을 줘보면 됩니다.

예:

- `이 메모를 humanize 해줘.`
- `이 노트를 읽히는 standalone 문서로 바꿔줘.`
- `기술 내용은 유지하고 README를 더 사람답게 다시 써줘.`

설치가 잘 됐다면, 에이전트가 단순 문장 치환이 아니라 문서 전체의 readability까지 같이 손보는 방향으로 반응해야 합니다.

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

## 언제 쓰면 좋은가

이런 요청에 잘 맞습니다.

- `이거 humanize 해줘`
- `사람이 쓴 것처럼 다시 써줘`
- `이 문서를 읽기 좋게 고쳐줘`
- `이 메모를 standalone 문서로 정리해줘`
- `사실은 유지하면서 AI 티만 줄여줘`

## 언제 쓰면 안 되는가

다음 작업에는 맞지 않습니다.

- 번역
- fact-checking이나 웹 검증
- 새로운 도메인 전문지식이 필요한 리뷰
- 구조는 충분히 괜찮고 문법만 손보면 되는 경우

## 모드

### `correction`
구조는 대체로 맞고, 진짜 문제는 문장 톤, vague함, filler, AI 냄새일 때 사용합니다.

### `compose`
소스가 메모, bullet, fragment, 약한 초안이라서 그대로는 문서로 읽히지 않을 때 사용합니다.

### `hybrid`
두 문제가 같이 있을 때 사용합니다. 대부분의 중간 길이 이상 문서에서는 이 모드가 기본입니다.

## Skill 동작 방식

`humanize-doc/SKILL.md`의 workflow는 단순합니다.

1. 결과물 종류를 먼저 파악합니다
2. `references/document-modes.md`로 모드를 고릅니다
3. anti-slop / output 규칙을 읽습니다
4. 매체에 맞는 최소 추상화 수준으로 다시 씁니다
5. 사실, uncertainty, intended tone을 유지합니다
6. 마지막에 readability gate를 통과시킵니다

핵심 reference는 아래 네 개입니다.

- `references/anti-slop-patterns.md`
- `references/document-modes.md`
- `references/output-contract.md`
- `references/readability-gates.md`

## 잘 맞는 요청 예시

- `이 전략 메모를 덜 AI스럽게 바꿔줘.`
- `이 회의 메모를 팀에 공유할 문서로 정리해줘.`
- `기술 내용은 유지하되 README를 더 읽기 쉽게 다시 써줘.`
- `사실과 불확실성은 유지하고, 문장만 사람이 쓴 것처럼 다듬어줘.`

## Repo layout

```text
humanize-doc/
├── README.md
├── README.ko.md
├── docs/
│   ├── eval-prompts.md
│   └── merge-notes.md
└── humanize-doc/
    ├── SKILL.md
    └── references/
        ├── anti-slop-patterns.md
        ├── document-modes.md
        ├── output-contract.md
        └── readability-gates.md
```

## Development notes

이 repo는 두 갈래를 합친 결과물입니다.

- `stop-slop`에서 온 anti-slop 레퍼런스
- `human-readable-doc-composer`에서 온 문서 구성 아이디어

어떻게 합쳤는지는 `docs/merge-notes.md`에 기록되어 있고, 개선용 평가 프롬프트는 `docs/eval-prompts.md`에 정리되어 있습니다.

여기서 `humanize`는 외부 기준점이 아니라, 인접한 내부 선행 자산으로 취급합니다.
