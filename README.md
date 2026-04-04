# humanize-doc

Rewrite AI-sounding drafts into readable human documents.

`humanize-doc` fixes both sentence-level AI slop and document-level readability problems.

## Install

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

## Use it for

- humanizing AI-sounding prose
- rewriting rough notes into a standalone doc
- improving tone without dropping facts
- fixing both structure and sentence quality in one pass

## Modes

- `correction` — tone and prose cleanup
- `compose` — notes to document
- `hybrid` — both at once

## Core references

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
