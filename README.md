# humanize-doc

Rewrite AI-sounding drafts into readable human documents.

This repo packages the `humanize-doc` skill: a writing skill that fixes both sentence-level AI slop and document-level readability problems.

## Installation

Preferred:

```bash
npx skills add gigio1023/humanize-doc@humanize-doc
```

### Codex

Tell Codex:

```text
Fetch and follow instructions from https://raw.githubusercontent.com/gigio1023/humanize-doc/refs/heads/main/.codex/INSTALL.md
```

Detailed docs: `docs/README.codex.md`

### Claude Code

Tell Claude Code:

```text
Fetch and follow instructions from https://raw.githubusercontent.com/gigio1023/humanize-doc/refs/heads/main/.claude/INSTALL.md
```

Detailed docs: `docs/README.claude.md`

### Gemini CLI

Tell Gemini CLI:

```text
Fetch and follow instructions from https://raw.githubusercontent.com/gigio1023/humanize-doc/refs/heads/main/.gemini/INSTALL.md
```

Detailed docs: `docs/README.gemini.md`

### Cursor

Tell Cursor:

```text
Fetch and follow instructions from https://raw.githubusercontent.com/gigio1023/humanize-doc/refs/heads/main/.cursor/INSTALL.md
```

Detailed docs: `docs/README.cursor.md`

## What this skill improves

Most bad AI writing fails in two places at once:

1. **sentence-level slop**
   - vague labels instead of concrete actions
   - placeholder actors instead of named responsibility
   - false agency and inflated wording
   - repetitive, metronomic rhythm
2. **document-level weakness**
   - missing context
   - weak flow
   - unstable terminology
   - reasoning that only makes sense if you saw the earlier chat

`humanize-doc` fixes both layers together so the output is easier to read, easier to trust, and more durable outside the original conversation.

## Example: sentence-level cleanup

**Weak AI-sounding draft**

```text
This initiative enables cross-functional alignment and drives strategic clarity across key stakeholders.
```

**Better output**

```text
This document explains who owns the rollout, what changes this week, and which teams need to review it before launch.
```

## Example: document-level cleanup

**Weak note dump**

```text
- metrics weird
- auth issue maybe cache
- users saw old dashboard
- fix before friday
```

**Better output**

```text
Users briefly saw stale dashboard data because the auth cache was not invalidated during the metrics refresh. We should fix the cache invalidation path before Friday's rollout and verify the dashboard against a cold session.
```

## When to use it

Use this skill when the request sounds like any of these:

- `humanize this`
- `rewrite this so it reads like a person wrote it`
- `make this document readable`
- `organize these notes into a standalone doc`
- `remove AI smell without losing the facts`

## When not to use it

Do not use this skill for:

- translation
- fact-checking or web verification
- domain-expert review that needs new subject-matter knowledge
- grammar-only cleanup when the document structure is already fine

## Modes

### `correction`
Use when the structure is mostly right and the real problem is synthetic prose, vagueness, filler, or AI smell.

### `compose`
Use when the source is rough notes, fragments, bullets, or a weak draft that does not stand on its own.

### `hybrid`
Use when both problems are present. This is the default for most medium or long documents.

## How it works

The workflow in `humanize-doc/SKILL.md` is intentionally simple:

1. identify the deliverable type
2. choose a mode using `references/document-modes.md`
3. load the anti-slop and output rules
4. rewrite at the lowest abstraction level that still fits the medium
5. preserve facts, uncertainty, and intended tone
6. run the readability gates before delivering

Core reference files:

- `references/anti-slop-patterns.md`
- `references/document-modes.md`
- `references/output-contract.md`
- `references/readability-gates.md`

## Example prompts

- `Make this strategy memo sound less AI-generated.`
- `Turn these meeting notes into a document I can send to the team.`
- `Rewrite this README so it is clearer without losing technical detail.`
- `Keep the facts and uncertainty, but make the prose read like competent human writing.`

## What's inside

```text
humanize-doc/
├── docs/
└── humanize-doc/
    ├── SKILL.md
    └── references/
```

## Development notes

This repo combines two source lines:

- anti-slop reference work from `stop-slop`
- internal document-composition ideas from `human-readable-doc-composer`

`docs/merge-notes.md` records how those lines were combined. `docs/eval-prompts.md` holds prompts for testing and improving the skill.

`humanize` is treated here as an adjacent internal precedent, not as an external baseline to copy blindly.
