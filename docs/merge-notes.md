# Design and Lineage Notes

This repository's skill has two merge generations. The 2026-03 generation
built `humanize-doc` from an external anti-slop line and an internal
document-composition line. The 2026-07 generation built `clear-writing` by
consolidating six writing skills into one. These notes record both; they are
not an installation path.

## Generation 2 (2026-07): clear-writing

`clear-writing` absorbs six sources:

| Source | What it contributed |
| --- | --- |
| `humanize-doc` (this repo) | two-axis diagnosis (abstraction + reader context), revision workflow, medium calibration, readability gates |
| `engineering-docs` (agent-skills pack) | repository-grounded authoring: document jobs, zoom levels, templates, patterns, delivery checklist |
| `terminology-review` (agent-skills pack) | evidence-scaled term judgment, real-system name anchoring, watch list and verification procedure |
| company `im-not-ai` snapshot + upstream `epoko77-ai/im-not-ai` v2.3 | Korean sentence-level taxonomy with pattern IDs, surgical diff-evidence editing discipline |
| company `anti-ai-slop-terminology`, `dev-doc-style` | superseded ancestors of the two agent-skills sources; dropped as direct sources |
| 2026-07 research pass (5 lanes) | voice-preservation rules (rewrite-drift research), evidence ledger, change-rate guard, editor-slop self-check, myth exclusions |
| `petergyang/no-ai-slop` (2026-07 one-time port) | rhetorical-pattern additions to `anti-slop-core.md` (colon reveals, lone-expert framing, rhetorical setups, dramatic fragmentation, throat-clearing openers, verb inflation, synonym cycling, kicker-deletion rule), review-mode quote contract, pre-edit voice-signal note; its outright word bans and universal em-dash caps were not adopted — they conflict with the evidence ledger (marker lists decay per model generation; hard bans reject valid domain language) |

Key decisions, in order of how hard they would be to reverse:

- **One skill, not a pack.** The consolidation exists to shrink the trigger
  surface: one request should have one firing candidate. Fallback recorded in
  `redesign-plan.md`: split authoring/revision only if over-triggering is
  observed in practice.
- **Two-tier system.** The skill is the on-demand deep tier. An always-on core
  (14 Korean answer rules) lives as a draft in
  `clear-writing/references/core-rules.md`; installing it into always-on agent
  layers is a deferred decision tracked in that file.
- **Evidence ledger over flat rules.** Every Korean rule carries its
  justification type: measured AI discriminator, Korean style evidence,
  observation-only, or house style. Upstream's 2026-07 corpus study rejected
  two popular rules (A-2 "~를 통해", I-1 "것이다" — humans use both more than
  AI); they are kept only as conditioned style rules. This revises Generation
  1's "one language-neutral core" decision: Korean earned a dedicated
  reference layer inside the same skill, synced to upstream pattern IDs with a
  quarterly delta check.
- **House style became a profile.** The company line's em-dash prohibition and
  workplace-slang rules are a selectable strict profile, not a separate
  company build and not an AI-detection claim.
- **Upstream relationship changed.** Generation 1 treated `im-not-ai`'s
  `humanize-korean` as an unrelated package. Generation 2 treats it as the
  evidence-synced source for `korean-tells.md` — content is re-derived, never
  vendored wholesale, because the company's frozen v2.0 snapshot had already
  gone stale against upstream's own rule rejections.

## Generation 1 (2026-03): humanize-doc

### From `stop-slop`

Pulled forward: anti-slop framing as a first-class task; sentence-level
pattern detection; false-agency cleanup; rhythm and filler checks; a gating
mindset before delivery. Not copied: hard bans too rigid for every medium and
phrase-level prohibitions overfit to one author's taste. (By 2026-07 the
upstream repo had been inactive for four months; its named patterns — false
agency, negative listing, narrator-from-a-distance — were carried into
`anti-slop-core.md` as a one-time port.)

### From `human-readable-doc-composer`

An internal skill from the local `brain` repo (added 2026-03-02, archived
2026-03-19). Pulled forward: standalone readability as a requirement,
result-first delivery, explicit handling of facts and assumptions, terminology
consistency. Not copied: repo-local terminology files and mode names tied to
that repository's workflow.

### Why one merged skill (Generation 1 rationale, still valid)

"Make this less AI-sounding" and "make this document usable" are usually the
same request. Kept separate, one pass fixes tone but leaves weak structure,
the other fixes structure but keeps synthetic phrasing, and the user has to
know which to invoke first. Generation 2 extends the same argument from two
concerns to six skills.

## Standing maintenance decisions

- Publish and update through `npx skills` from this repository's `main`
  branch. No manual per-agent copies, symlinks, or install adapters.
- No banned-phrase lint script: whether wording is synthetic depends on
  context, and a deterministic ban rejects valid domain language.
- Short-form writing stays in the skill; medium calibration prevents chat and
  email from turning into formal documents.
- Quarterly: diff upstream `epoko77-ai/im-not-ai` taxonomy and
  empirical-validation notes against `korean-tells.md`; carry over ID-level
  changes only. Rules are removed when evidence turns against them — a rule
  that is merely popular is not protected.
