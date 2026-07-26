# clear-writing

[![skills.sh](https://skills.sh/b/gigio1023/clear-writing)](https://skills.sh/gigio1023/clear-writing)
![prose](https://img.shields.io/badge/prose-EN%20%C2%B7%20KO-22684E)
![package](https://img.shields.io/badge/SKILL.md-router%20%2B%2016%20references-555)

Write, rewrite, and review prose documents with one skill: repository-grounded
authoring, humanizing revision, terminology checks, and surgical Korean
polish — without changing the facts.

[Install](#install) · [What's inside](#whats-inside) · [Examples](#examples) ·
[Evidence](#evidence-and-lineage) · [Layout](#package-layout) ·
[Development](#local-development)

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

## What's inside

`SKILL.md` is a thin router. It establishes the deliverable, language,
grounding, edit authority, style profile, and voice sample, then loads only
the references its job needs.

| Job | Covers | Primary reference |
| --- | --- | --- |
| Authoring | README, guides, API references, ADRs, specs grounded in repository evidence | `references/authoring.md` |
| Revision | humanizing, restructuring, composing notes into standalone docs | `references/revision.md` |
| Passes | terminology review; Korean sentence-level polishing | `references/terminology.md`, `references/korean-tells.md` |

Design points:

- **Evidence ledger.** Every rule carries its justification type: measured
  AI-vs-human discriminator, Korean style evidence, observation-only, or
  house style. Rules rejected by corpus studies are conditioned, not kept.
- **Voice preservation.** Removal-only editing; the author's voice markers
  are protected, and a user-supplied writing sample outranks every style rule.
- **Delivery gates.** Fact-preservation checks, a change-rate guard (warn at
  30%, stop at 50%), and an editor-slop self-check on the skill's own output.
- **Profiles.** House-style strictness (em-dash prohibition, workplace
  vocabulary) is a selectable profile, not a fork.
- **Always-on core draft.** `references/core-rules.md` holds a 14-rule Korean
  answer baseline for always-on agent layers; whether to install it is a
  deferred decision tracked in the file.

## Examples

Sentence-level revision:

```text
Before: This initiative enables cross-functional alignment and drives
        strategic clarity across key stakeholders.
After:  This document explains who owns the rollout, what changes this week,
        and which teams need to review it before launch.
```

Composing notes into a standalone document:

```text
Before: - metrics weird
        - auth issue maybe cache
        - users saw old dashboard
        - fix before friday
After:  Users saw stale dashboard data, and the metrics also looked unusual.
        The cause is not confirmed; the notes suggest the authentication cache
        may be involved. We should investigate that hypothesis and fix the
        issue before Friday.
```

Korean surgical polish (facts, commands, and register preserved):

```text
Before: 데이터를 정제하고, 모델을 학습시킨 다음, 결과를 검증합니다.
After:  데이터를 정제하고 모델을 학습시킨 다음 결과를 검증합니다.
```

## Evidence and lineage

Rules come from a July 2026 research pass: upstream repository audits, an
ecosystem sweep of writing skills, academic work on AI-text markers
(KatFishNet at ACL 2025, lexical-overuse and rewrite-drift studies), and
Korean translation-ese scholarship. [docs/redesign-plan.md](docs/redesign-plan.md)
holds the design and trigger boundaries; [docs/merge-notes.md](docs/merge-notes.md)
the lineage; [docs/eval-prompts.md](docs/eval-prompts.md) lightweight trigger
and preservation checks.

## Package layout

```text
clear-writing/
├── README.md
├── README.ko.md
├── docs/                   # design record, not installed
└── clear-writing/          # the installable skill
    ├── SKILL.md
    └── references/         # 16 files, loaded per job
```

The package follows the [Agent Skills format](https://agentskills.io/) and is
distributed with the [Skills CLI](https://github.com/vercel-labs/skills); the
repository keeps no per-agent install adapters.

## Local development

```bash
npx --yes skills add . --list --full-depth
```

Before publishing a change: the listing reports exactly `clear-writing`, the
`SKILL.md` name matches its folder, every referenced path exists, and this
README stays aligned with `README.ko.md`.
