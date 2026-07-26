# clear-writing

[![skills.sh](https://skills.sh/b/gigio1023/clear-writing)](https://skills.sh/gigio1023/clear-writing)

One Agent Skill for prose-document work in English and Korean: author
repository-grounded docs, rewrite AI-sounding drafts, turn rough notes into
standalone documents, review terminology, and surgically polish Korean
technical writing — all without changing the facts.

The skill follows the [Agent Skills format](https://agentskills.io/) with a
`SKILL.md` router and supporting references beside it. Install it with
[`npx skills`](https://github.com/vercel-labs/skills), then pull later
revisions from the same tracked source.

[Transition status](#transition-from-humanize-doc) ·
[Install](#install-with-npx-skills) · [Update](#keep-the-skill-up-to-date) ·
[What's inside](#whats-inside) · [Examples](#examples) ·
[Evidence and lineage](#evidence-and-lineage) ·
[Local development](#local-development)

## Transition from humanize-doc

This repository was renamed from `gigio1023/humanize-doc` on 2026-07-26 and now
publishes the unified `clear-writing` skill. It consolidates what previously
lived in several places: the `humanize-doc` skill (this repo), the
`terminology-review` and `engineering-docs` skills (from the
`gigio1023/agent-skills` pack), and a Korean surgical-polish rule line kept in
sync with [`epoko77-ai/im-not-ai`](https://github.com/epoko77-ai/im-not-ai).

During the transition:

- The legacy `humanize-doc/` package remains installable from this repository
  until the unified skill passes its evaluation phase, and is removed after
  that.
- Old install sources pointing at `gigio1023/humanize-doc` keep working through
  GitHub's rename redirect, but new installs should use the
  `gigio1023/clear-writing` source below.
- `terminology-review` and `engineering-docs` are still published from
  `agent-skills` and are scheduled for retirement there once this skill
  replaces them. Avoid installing them alongside `clear-writing`; the triggers
  overlap by design.

## Install with `npx skills`

Prerequisite: Node.js 22.20.0 or newer for the current Skills CLI release.

Inspect the published package before installing it:

```bash
npx --yes skills add 'gigio1023/clear-writing#main' --list --full-depth
```

Install it globally for the agents you use:

```bash
npx --yes skills add 'gigio1023/clear-writing#main' \
  --skill clear-writing \
  --agent codex claude-code \
  --global \
  --yes
```

Replace the agent IDs as needed; `cursor`, `gemini-cli`, and `antigravity` are
also supported by the Skills CLI. Omit `--global` for a project-local install.

The quoted `#main` source makes the published branch explicit and gives the CLI
the provenance it needs for later updates. Let the CLI manage each agent's
destination; this repository does not maintain separate `.claude/`, `.codex/`,
`.cursor/`, or `.gemini/` installation adapters.

Verify the installation:

```bash
npx --yes skills list --global
```

## Keep the skill up to date

```bash
npx --yes skills update clear-writing --global --yes
```

Updates are pull-based and use the remote source recorded at installation. If
an older `humanize-doc` install is reported as untracked or keeps updating
from the old source, remove it and reinstall once from the quoted
`gigio1023/clear-writing#main` source above.

## What's inside

`clear-writing/SKILL.md` is a thin router. It establishes the deliverable,
language, grounding, edit authority, style profile, and voice sample, then
selects a job and loads only the references that job needs.

| Job | Covers | Primary reference |
| --- | --- | --- |
| Authoring | README, guides, API references, ADRs, specs grounded in repository evidence | `references/authoring.md` |
| Revision | humanizing, restructuring, composing notes into standalone docs | `references/revision.md` |
| Passes | terminology review; Korean sentence-level polishing | `references/terminology.md`, `references/korean-tells.md` |

Design points worth knowing:

- **Evidence ledger.** Rules are tagged by justification: measured AI-vs-human
  discriminators, Korean style evidence, observation-only diagnostics, and
  house style. Rules rejected by upstream corpus studies are conditioned
  rather than silently kept.
- **Voice preservation.** Rewriting itself homogenizes text, so the skill
  enforces removal-only editing, protects the author's voice markers, and
  treats a user-supplied writing sample as outranking every style rule.
- **Delivery gates.** Every deliverable passes fact-preservation checks, a
  change-rate guard (warn at 30% changed, stop at 50%), and an editor-slop
  self-check applied to the skill's own output.
- **Profiles.** House-style strictness (em-dash prohibition, workplace
  vocabulary) is a selectable profile in `references/profiles.md`, not a fork
  of the skill.
- **Always-on core draft.** `references/core-rules.md` holds a 14-rule Korean
  answer baseline intended for always-on agent layers. Installing it anywhere
  is an explicitly deferred decision, tracked in the file itself.

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

The consolidation and its rules come from a July 2026 research pass: upstream
repository audits, an ecosystem sweep of writing skills, academic work on
AI-text markers (KatFishNet at ACL 2025, lexical-overuse and rewrite-drift
studies), and Korean translation-ese scholarship. See
[docs/redesign-plan.md](docs/redesign-plan.md) for the migration matrix and
trigger boundaries, and [docs/merge-notes.md](docs/merge-notes.md) for the
full lineage. [docs/eval-prompts.md](docs/eval-prompts.md) provides
lightweight trigger and preservation checks.

## Package layout

```text
clear-writing/
├── README.md
├── README.ko.md
├── docs/
│   ├── eval-prompts.md
│   ├── merge-notes.md
│   └── redesign-plan.md
├── clear-writing/          # the installable skill
│   ├── SKILL.md
│   └── references/         # 16 files, loaded per job
└── humanize-doc/           # legacy package, removed after evaluation
```

## Local development

Inspect a checkout without creating an update-tracked install:

```bash
npx --yes skills add . --list --full-depth
```

During the transition the listing reports two packages (`clear-writing` and
the legacy `humanize-doc`); after retirement it must report exactly one.
Before publishing a change, verify that the `SKILL.md` name matches its
folder, every referenced path exists, and this README and `README.ko.md`
describe the same installation and behavior.
