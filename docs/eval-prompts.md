# Evaluation Prompts

Use these lightweight prompts to inspect trigger boundaries, mode selection,
and preservation behavior after a skill change. Record the harness, model,
effort, and available tools when results are used as compatibility evidence.
The expected behavior below is a rubric, not a recorded test result.

## Prompt 1: correction

> 이 문단 AI 티 안 나게 자연스럽게 다듬어줘. 사실관계는 바꾸지 말고 표현만 고쳐줘.

Expected:

- `correction` mode
- keeps structure mostly intact
- lowers abstraction and removes filler

## Prompt 2: compose

> 아래 메모를 팀 공유용 문서로 정리해줘. 채팅 맥락 없이 읽어도 이해되게 써줘.

Expected:

- `compose` mode
- standalone document
- clear result-first structure

## Prompt 3: hybrid

> 이 전략 메모 전체를 읽기 좋게 다시 써줘. 지금은 너무 AI가 쓴 것 같고 흐름도 별로야.

Expected:

- `hybrid` mode
- restructures sections and rewrites prose together
- preserves uncertainty and evidence markers

## Prompt 4: should not trigger

> 이 문장 문법만 체크해줘.

Expected:

- do not force this skill unless the text clearly has a readability or AI-slop problem

## Prompt 5: factual preservation

> 아래 장애 공지를 자연스럽게 다듬어줘. 날짜, 영향 범위, 원인에 대한
> 불확실성은 그대로 유지해줘.

Expected:

- preserves dates and scope exactly
- does not turn a suspected cause into a confirmed cause
- improves prose without adding evidence or reassurance

## Prompt 6: adjacent translation request

> 이 한국어 문서를 영어로 번역해줘.

Expected:

- does not trigger `humanize-doc` for a translation-only request

## Package checks

From the repository root, both commands should discover exactly one skill named
`humanize-doc`:

```bash
npx --yes skills add . --list
npx --yes skills add . --list --full-depth
```
