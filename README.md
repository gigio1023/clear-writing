# clear-writing

[![skills.sh](https://skills.sh/b/gigio1023/clear-writing)](https://skills.sh/gigio1023/clear-writing)
![prose](https://img.shields.io/badge/prose-EN%20%7C%20KO%20%7C%20IT%20%7C%20ZH-22684E)
![package](https://img.shields.io/badge/SKILL.md-router%20%2B%2019%20references-555)
[![license](https://img.shields.io/badge/license-MIT-555)](LICENSE)

Write, revise, and review documents that stand on their own, preserve the
writer's meaning and voice, and make each material claim no stronger than its
evidence. The skill supports English, Korean, Italian, and Chinese without
pretending that English style advice is language-neutral.

`clear-writing` handles README, guides, specs, API references, ADRs, memos,
wiki pages, and blog drafts. It can compose notes, repair stale or
session-dependent documentation, review terminology, and reduce formulaic
model-assisted prose. It does not infer whether AI wrote a passage. It names
the reader-visible defect and fixes it only when meaning can be preserved.

[Architecture](#architecture) · [Languages](#language-layers) ·
[Evidence](#evidence-and-lineage) · [Layout](#package-layout) ·
[Install](#install) · [Development](#local-development)

## Architecture

`SKILL.md` is a router. It establishes the reader job, language and locale,
evidence boundary, edit authority, governing policy, and voice sample. It then
loads a common integrity layer, one job workflow, and only the language layer
that matches each span.

| Job | Covers | Primary reference |
|---|---|---|
| Authoring | new or materially updated evidence-grounded documents | `references/authoring.md` |
| Revision | humanizing, restructuring, and composing notes into a standalone document | `references/revision.md` |
| Focused pass | terminology or language-specific prose review | `references/terminology.md` plus one language layer |

The common layer enforces:

- an explicit evidence boundary and current, claim-fitting sources;
- facts, conditions, requirement levels, logical relations, and uncertainty;
- enough context for a reader who did not see the Codex, Claude Code, issue,
  or PR session;
- relevance to the document's reader job;
- the writer's established voice and minimal effective edits;
- no invented facts, examples, quotations, citations, actors, or specificity.

Search snippets, copied citation lists, generated summaries, and local research
notes can locate evidence. They do not inherit the authority of the original
source. A cold read checks self-containment; it does not prove factual accuracy
or replace representative-reader testing.

## Language layers

| Layer | What it contributes | What it does not claim |
|---|---|---|
| English | register-aware active/passive choice, rhetorical patterns, `-ing` attachment, marker-density and voice checks | that one word, contraction, dash, or sentence shape proves authorship |
| Korean | `im-not-ai` taxonomy mapped to Korean corpus and translationese evidence, with keep tests and evidence labels | that an aggregate group difference identifies one passage |
| Italian | punctuation scope, `gerundio` attachment, information flow, administrative weight, and translation interference | a durable Italian AI-tell list |
| Chinese | locale-first `zh-CN`, `zh-TW`, and `zh-HK` punctuation, terminology, script, and official-document overlays | that Simplified or Traditional script alone determines locale |

For another language, the skill uses only the common integrity layer, the
writer's sample, and governing locale or publication guidance. It does not
translate an English surface checklist into an unsupported tell list.

The optional block in `references/core-rules.md` is a Korean always-on answer
layer. It is not the generation baseline for English, Italian, or Chinese.

## Evidence and lineage

The [sources and inspiration register](docs/sources-and-inspiration.md) records
the inspected version, source status or license, adopted insight, scope limit,
and rejected idea for every source family. It covers `im-not-ai`,
`petergyang/no-ai-slop`, the local `brain/clips` and `brain/research` notes,
official language and plain-language guidance, regional Chinese standards, and
research on model-assisted revision and generated prose.

[Design and lineage notes](docs/merge-notes.md) explain how the earlier skills
were consolidated. The [redesign plan](docs/redesign-plan.md) is a historical
record. [Evaluation prompts](docs/eval-prompts.md) contain lightweight trigger
and preservation checks, not benchmark results.

## Package layout

```text
clear-writing/
├── README.md
├── README.ko.md
├── LICENSE
├── docs/                   # provenance and design records; not installed
└── clear-writing/          # the one installable skill
    ├── SKILL.md
    └── references/         # 19 files, loaded by job and language
```

The package follows the [Agent Skills format](https://agentskills.io/) and is
distributed with the [Skills CLI](https://github.com/vercel-labs/skills). It
contains no Codex-only or Claude Code-only workflow in the portable core.

## Install

Requires Node.js 22.20.0 or newer.

```bash
npx --yes skills add 'gigio1023/clear-writing#main' \
  --skill clear-writing \
  --agent codex claude-code \
  --global \
  --yes
```

Change the agent IDs as needed. The CLI also supports `cursor`, `gemini-cli`,
and `antigravity`. Omit `--global` for a project install. Verify with
`npx --yes skills list --global`; update with
`npx --yes skills update clear-writing --global --yes`.

## Local development

```bash
npx --yes skills add . --list --full-depth
```

Before publishing, confirm that the command finds exactly one skill named
`clear-writing`, frontmatter matches the folder, every linked reference exists,
and both READMEs describe the same package.
