# humanize-doc

A writing skill for turning AI-sounding drafts, rough notes, and weak documents into writing that reads like a competent human wrote it.

This repo packages one skill, `humanize-doc`, with a narrow job:

- remove synthetic, inflated, abstraction-heavy prose
- rebuild the document so it still works for a reader who was not in the original chat

It is not a grammar checker and it is not a fact-checking workflow. It is a **rewrite + readability** skill.

## What the skill does

`humanize-doc` treats most bad AI writing as a two-layer problem:

1. **sentence-level slop**
   - vague labels
   - placeholder actors
   - false agency
   - repetitive cadence
2. **document-level weakness**
   - missing context
   - weak structure
   - unstable terminology
   - reasoning that only makes sense if you saw the earlier conversation

The skill fixes both layers together so the output is easier to read and easier to trust.

## When to use it

Use this skill when the request sounds like any of these:

- “humanize this”
- “rewrite this so it reads like a person wrote it”
- “make this document readable”
- “organize these notes into a standalone doc”
- “remove AI smell without losing the facts”

## When not to use it

Do **not** use this skill for:

- translation
- fact-checking or web verification
- domain-expert review that needs new subject-matter knowledge
- grammar-only cleanup when the document structure is already fine

## Modes

The skill has three working modes.

### `correction`
Use when the structure is mostly right and the real problem is synthetic prose, vagueness, filler, or AI smell.

### `compose`
Use when the source is rough notes, fragments, bullets, or a weak draft that does not stand on its own.

### `hybrid`
Use when both problems are present. This is the default for most medium or long documents.

## Install

This repo is currently private.

### Skills CLI

```bash
npx skills add gigio1023/humanize-doc@humanize-doc
npx skills add gigio1023/humanize-doc@humanize-doc -g
```

### Manual install

<details>
<summary>Claude Code</summary>

```bash
mkdir -p ~/.claude/skills && \
  git clone https://github.com/gigio1023/humanize-doc.git /tmp/humanize-doc && \
  cp -r /tmp/humanize-doc/humanize-doc ~/.claude/skills/ && \
  rm -rf /tmp/humanize-doc
```
</details>

<details>
<summary>Codex CLI</summary>

```bash
mkdir -p ~/.codex/skills && \
  git clone https://github.com/gigio1023/humanize-doc.git /tmp/humanize-doc && \
  cp -r /tmp/humanize-doc/humanize-doc ~/.codex/skills/ && \
  rm -rf /tmp/humanize-doc
```
</details>

<details>
<summary>Other agents</summary>

```bash
mkdir -p ~/.agents/skills && \
  git clone https://github.com/gigio1023/humanize-doc.git /tmp/humanize-doc && \
  cp -r /tmp/humanize-doc/humanize-doc ~/.agents/skills/ && \
  rm -rf /tmp/humanize-doc
```
</details>

## How the skill works

The workflow in `humanize-doc/SKILL.md` is intentionally simple:

1. identify the deliverable type
2. choose a mode using `references/document-modes.md`
3. load the anti-slop and output rules
4. rewrite at the lowest abstraction level that still fits the medium
5. preserve facts, uncertainty, and intended tone
6. run the readability gates before delivering

The key reference files are:

- `references/anti-slop-patterns.md`
- `references/document-modes.md`
- `references/output-contract.md`
- `references/readability-gates.md`

## Example requests

- “Make this strategy memo sound less AI-generated.”
- “Turn these meeting notes into a document I can send to the team.”
- “Rewrite this README so it is clearer without losing technical detail.”
- “Keep the facts and uncertainty, but make the prose read like competent human writing.”

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

This repo combines two source lines:

- anti-slop reference work from `stop-slop`
- internal document-composition ideas from `human-readable-doc-composer`

`docs/merge-notes.md` records how those lines were combined. `docs/eval-prompts.md` holds prompts for testing and improving the skill.

`humanize` is treated here as an adjacent internal precedent, not as an external baseline to copy blindly.
