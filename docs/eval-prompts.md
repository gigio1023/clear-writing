# Evaluation Prompts

Lightweight prompts to inspect trigger boundaries, job selection, and
preservation behavior after a skill change. Record the harness, model, effort,
and available tools when results are used as compatibility evidence. The
expected behavior below is a rubric, not a recorded test result. A fuller
three-arm comparison protocol and its 2026-07 results live in the workspace
notes (`notes/humanize-consolidation/p3-eval.md`), outside this repository.

## Prompt 1: sentence-level humanize (Korean)

> 아래 문단 AI 티 안 나게 자연스럽게 다듬어줘. 사실관계는 바꾸지 말고.

Expected:

- revision job, sentence-level pass; structure left intact
- formulaic wrap-ups and undue-significance phrasing deleted, not reworded
- comma-after-connective cleanup (korean-tells C-11); conditioned rules
  (single "~를 통해", uniform 어미 in short formal text) left alone
- dates, numbers, and uncertainty hedges preserved verbatim; no new
  connectives inserted (removal only)

## Prompt 2: compose notes into a standalone doc

> Turn these notes into a short incident summary the on-call team can read
> standalone.

Expected:

- revision job, compose path; result-first structure
- every source fact carried over; suspected causes stay suspected
- no invented severity, IDs, timestamps, or next steps
- medium calibration: status-update register, no ceremonial open/close

## Prompt 3: revision with voice preservation (English)

> Edit this blog draft so it doesn't read AI-generated. Keep my voice.

Expected:

- voice signals noted and kept: first person, humor, profanity, asides,
  concrete numbers
- rhetorical patterns removed: throat-clearing openers, lone-expert framing,
  colon reveals, negative listing, synonym cycling
- a fake-profound kicker is deleted, never rewritten into a better metaphor;
  the piece ends on the last concrete sentence
- change-rate guard reported when deletions push past 30%

## Prompt 4: factual preservation under edit pressure

> 이 장애 공지 자연스럽게 다듬어줘. 날짜, 영향 범위, 원인 불확실성은 그대로
> 유지해줘.

Expected:

- generic boilerplate (mission statements, closing pledges) deleted
- dates, impact scope, and "possible but unconfirmed" hedges preserved
  word-for-word; no invented remediation promises
- ends on the concrete remediation step, not a generic closing line

## Prompt 5: review-only terminology pass

> 이 문단 용어 이상한 거 없나 봐줘. 고치지는 말고 봐주기만 해.

Expected:

- findings only, no edits (authority rule); each finding quotes the line,
  names the pattern, states the fix
- coined consultant names flagged or marked uncertain with the
  mechanism question to ask the author; established domain terms
  (e.g., Kubernetes Operator, sidecar) kept
- no confidence beyond evidence; no authorship claims, no scores

## Prompt 6: should not trigger

> 이 문장 문법만 체크해줘.

> 이 한국어 문서를 영어로 번역해줘.

Expected:

- neither request loads this skill: grammar-only checks and translation are
  out of scope (NOT-for list in `../clear-writing/SKILL.md`)

## Package checks

From the repository root, both commands should discover exactly one skill
named `clear-writing`:

```bash
npx --yes skills add . --list
npx --yes skills add . --list --full-depth
```
