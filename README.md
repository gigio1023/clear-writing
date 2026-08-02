# clear-writing

[![skills.sh](https://skills.sh/b/gigio1023/clear-writing)](https://skills.sh/gigio1023/clear-writing)
![prose](https://img.shields.io/badge/prose-EN%20%C2%B7%20KO-22684E)
![package](https://img.shields.io/badge/SKILL.md-router%20%2B%2017%20references-555)
[![license](https://img.shields.io/badge/license-MIT-555)](LICENSE)

Write, rewrite, and review prose documents with one skill: evidence-grounded
authoring, humanizing revision, terminology checks, and surgical Korean
polish, while preserving facts and visible uncertainty.

It is one skill because those jobs used to be several, and a single request
("clean up this README") could match more than one of them at once. A router
now reads the request, works out what the document actually needs, and loads
only the rules for that job. Korean is first-class rather than translated
English advice: Korean documents get their own sentence-level pattern layer,
synced to an upstream taxonomy and tagged by what kind of evidence each rule
rests on.

Humanize and surface cleanup are removal-first. Authoring, composition, and
full revision may add context or connective reasoning only when user material,
inspected repository evidence, or verified external sources support it. The
skill never invents facts, examples, quotations, or citations, and it never
claims a document was written by AI; it reports the wording problem instead.

[What's inside](#whats-inside) · [Examples](#examples) ·
[Evidence](#evidence-and-lineage) · [Layout](#package-layout) ·
[Install](#install) · [Development](#local-development)

## What's inside

`SKILL.md` is a thin router. It establishes the deliverable, language,
grounding, edit authority, style profile, and voice sample, then loads only
the references its job needs.

| Job | Covers | Primary reference |
| --- | --- | --- |
| Authoring | README, guides, API references, ADRs, and specs grounded in an explicit evidence boundary | `references/authoring.md` |
| Revision | humanizing, restructuring, composing notes into standalone docs | `references/revision.md` |
| Passes | terminology review; Korean sentence-level polishing | `references/terminology.md`, `references/korean-tells.md` |

Design points:

- **Source grounding.** Material external claims are checked for source fit,
  currentness, and evidentiary status. Search snippets and generated summaries
  are leads, not proof.
- **Korean evidence ledger.** Korean pattern rules distinguish external
  measurements, unreproduced upstream self-study, Korean style evidence, and
  observation-only diagnostics. Group-level differences never become proof
  from one span, and rejected rules stay conditioned rather than becoming
  detection signals.
- **Voice preservation.** Surface cleanup is removal-first; authoring,
  composition, and full revision remain evidence-bounded. The author's voice
  markers are protected. A user-supplied sample outranks built-in profiles and
  defaults, while explicit current requirements and repository policy still
  bind the edit.
- **Delivery gates.** Cold-reader completeness, claim-to-evidence fit, fact
  preservation, a change-rate guard (warn at 30%, stop at 50%), and an
  editor-slop self-check on the skill's own output.
- **Form follows the reader job.** Prose carries reasoning; lists, tables,
  charts, and diagrams are used only when their structure clarifies the
  material better than short prose.
- **Profiles.** House-style strictness (em-dash prohibition, workplace
  vocabulary) is a selectable profile, not a fork.
- **Always-on core.** The skill loads on demand, so it cannot govern ordinary
  chat answers. `references/core-rules.md` holds a 15-rule Korean answer
  baseline for that job: copy the marked block verbatim into an always-on
  layer, and later updates replace it mechanically by version marker.

## Examples

Sentence-level revision:

```text
Before: The dashboard serves as a centralized hub for release status and
        functions as the team's primary source of deployment updates.
After:  The dashboard is the team's source for release status and deployment
        updates.
```

Composing notes into a standalone document:

```text
Before: - users saw the old dashboard and wrong metrics
        - cause unconfirmed
        - investigate auth cache
        - fix before Friday
After:  Users saw the old dashboard and incorrect metrics. The cause is not
        confirmed. Investigate the authentication cache and fix the issue
        before Friday.
```

Korean surgical polish (facts, commands, and register preserved):

```text
Before: 데이터를 정제하고, 모델을 학습시킨 다음, 결과를 검증합니다.
After:  데이터를 정제하고 모델을 학습시킨 다음 결과를 검증합니다.
```

## Evidence and lineage

The [sources and inspiration register](docs/sources-and-inspiration.md) records
the inspected version, license or status, adopted insight, and rejected ideas
for the projects, research, official guidance, and maintainer material that
informed the skill. [Design and lineage notes](docs/merge-notes.md) explain how
the earlier skills were consolidated. The
[redesign plan](docs/redesign-plan.md) preserves the historical design state,
and [evaluation prompts](docs/eval-prompts.md) hold lightweight trigger and
preservation checks.

## Package layout

```text
clear-writing/
├── README.md
├── README.ko.md
├── LICENSE                 # MIT
├── docs/                   # design record, not installed
└── clear-writing/          # the installable skill
    ├── SKILL.md
    └── references/         # 17 files, loaded per job
```

The package follows the [Agent Skills format](https://agentskills.io/) and is
distributed with the [Skills CLI](https://github.com/vercel-labs/skills); the
repository keeps no per-agent install adapters.

## Install

Requires Node.js 22.20.0 or newer.

```bash
npx --yes skills add 'gigio1023/clear-writing#main' \
  --skill clear-writing \
  --agent codex claude-code \
  --global \
  --yes
```

Swap the agent IDs as needed (`cursor`, `gemini-cli`, and `antigravity` are
also supported); omit `--global` for a project-local install. Verify with
`npx --yes skills list --global`, and update later with
`npx --yes skills update clear-writing --global --yes`.

The quoted `#main` source records the provenance updates rely on; the CLI
manages each agent's install destination.

## Local development

```bash
npx --yes skills add . --list --full-depth
```

Before publishing a change: the listing reports exactly `clear-writing`, the
`SKILL.md` name matches its folder, every referenced path exists, and this
README stays aligned with `README.ko.md`.
