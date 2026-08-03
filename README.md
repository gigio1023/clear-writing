# slop-aware-writing

[![skills.sh](https://skills.sh/b/gigio1023/slop-aware-writing)](https://skills.sh/gigio1023/slop-aware-writing)
![writing](https://img.shields.io/badge/writing-EN%20%7C%20KO%20%7C%20IT%20%7C%20ZH-22684E)
![package](https://img.shields.io/badge/SKILL.md-router%20%2B%2019%20references-555)
[![license](https://img.shields.io/badge/license-MIT-555)](LICENSE)

Write and revise documents while preventing or removing AI slop without
flattening the writer's meaning or voice. The skill treats slop as a functional
writing failure: plausible completion has replaced selection, evidence, reader
context, or a real point of view. It does not treat grammar mistakes or surface
markers as proof of authorship.

`slop-aware-writing` handles humanizing and deslop passes, plus slop-aware work
on README, guides, specs, API references, ADRs, memos, wiki pages, and blog
drafts. It trusts the LLM's base fluency for ordinary grammar and idiom. The
skill adds the diagnosis, evidence boundary, voice protection, and minimal-edit
tests that general language competence does not supply reliably.

[Architecture](#architecture) · [Languages](#language-overlays) ·
[Evidence](#evidence-and-lineage) · [Layout](#package-layout) ·
[Install](#install) · [Development](#local-development)

## Architecture

`SKILL.md` is a router. It establishes the reader job, evidence boundary, edit
authority, governing policy, and voice sample. It always loads the common slop
diagnosis. A language overlay loads only when a candidate depends on that
language or locale.

| Job | Covers | Primary reference |
|---|---|---|
| Authoring | new or materially updated evidence-grounded documents | `references/authoring.md` |
| Revision | humanizing, restructuring, and composing notes into a standalone document | `references/revision.md` |
| Focused pass | terminology or a language-specific slop pattern | `references/terminology.md` or one language overlay |

The common layer defines four recurring failures:

- generic completion that could fit an unrelated document;
- performed reasoning whose citations or transitions do not establish the
  claimed relation;
- reader displacement by templates, hidden sessions, and irrelevant detail;
- voice flattening through safe, uniform, over-polished prose.

It tests candidate spans against the reader job, evidence, deletion cost, and
writer's repeated choices. It preserves facts, conditions, requirement levels,
logical relations, and uncertainty. It never invents specificity.

Search snippets, copied citation lists, generated summaries, and local research
notes can locate evidence. They do not inherit the authority of the original
source. A cold read checks self-containment; it does not prove factual accuracy
or replace representative-reader testing.

## Language overlays

| Layer | What it contributes | What it does not claim |
|---|---|---|
| English | formulaic rhetoric, unsupported `-ing` relations, inflated significance, and register flattening | a general English style guide |
| Korean | `im-not-ai` pattern families with Korean evidence, keep tests, and explicit limits | a required scan of every sentence or pattern ID |
| Italian | formulaic connectors, bureaucratic weight, translation interference, and meaning safety during repair | an Italian grammar syllabus or durable AI-tell list |
| Chinese | parallel inflation, bureaucratic scaffolding, and locale safety when normalization is in scope | general proofreading or unrequested localization |

For another language, the model uses its contextual fluency with the common
diagnosis, writer sample, and governing locale guidance. During an authorized
rewrite it may silently fix one obvious local error. Grammar-only proofreading
does not trigger this skill, and no English checklist is translated into a new
language.

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
slop-aware-writing/
├── README.md
├── README.ko.md
├── LICENSE
├── docs/                   # provenance and design records; not installed
└── slop-aware-writing/     # the one installable skill
    ├── SKILL.md
    └── references/         # 19 files, loaded by job and language
```

The package follows the [Agent Skills format](https://agentskills.io/) and is
distributed with the [Skills CLI](https://github.com/vercel-labs/skills). It
contains no Codex-only or Claude Code-only workflow in the portable core.

## Install

Requires Node.js 22.20.0 or newer.

```bash
npx --yes skills add 'gigio1023/slop-aware-writing#main' \
  --skill slop-aware-writing \
  --agent codex claude-code \
  --global \
  --yes
```

Change the agent IDs as needed. The CLI also supports `cursor`, `gemini-cli`,
and `antigravity`. Omit `--global` for a project install. Verify with
`npx --yes skills list --global`; update with
`npx --yes skills update slop-aware-writing --global --yes`.

### Rename migration

An existing `clear-writing` install is not renamed in place. Install
`slop-aware-writing`, verify that the new handle appears, then remove the old
global handle:

```bash
npx --yes skills remove --global clear-writing --yes
```

For a project-scoped installation, omit `--global`. The published source is
`gigio1023/slop-aware-writing`.

## Local development

```bash
npx --yes skills add . --list --full-depth
```

Before publishing, confirm that the command finds exactly one skill named
`slop-aware-writing`, frontmatter matches the folder, every linked reference
exists, and both READMEs describe the same package.
