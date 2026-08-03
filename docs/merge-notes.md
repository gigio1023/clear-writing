# Design and Lineage Notes

This repository's skill has five design generations. The 2026-03 generation
built `humanize-doc` from an external anti-slop line and an internal
document-composition line. The 2026-07 generation built `clear-writing` by
consolidating six writing skills into one. The 2026-08 generation separated a
common integrity core from English, Korean, Italian, and Chinese language
layers, recentered them on model-native slop diagnosis, then adopted the
`slop-aware-writing` handle. These notes record the lineage; they are not an
installation path.

## Generation 5 (2026-08): slop-aware-writing

The maintainer selected `slop-aware-writing` after the contract review showed
that source grounding is a conditional guardrail rather than the primary
trigger. The new handle names the domain and the diagnostic lens without
reducing the skill to proofreading or authorship detection. The repository,
installable folder, frontmatter, current documentation, and CLI handle use
`slop-aware-writing`.

The optional Korean always-on block retains the legacy
`clear-writing:core v2` wrapper. That marker is an update interface copied into
external instruction files, so changing it during a package rename would leave
existing deployments undiscoverable by a mechanical replacement.

## Generation 4 (2026-08): model-native anti-slop

The multilingual package still risked becoming a compact grammar encyclopedia.
That duplicated frontier models' ordinary fluency and made every language file
look mandatory. Generation 4 tightened the contract:

- AI slop is a functional failure, not a writing-origin label: generic
  completion, performed reasoning, reader displacement, or voice flattening;
- the model reads the whole relevant scope and uses semantic transfer, support,
  reader, deletion, and voice tests instead of walking every rule;
- basic grammar, spelling, idiom, and syntax rely on model fluency. An obvious
  local error may be fixed during an authorized rewrite, but grammar-only
  proofreading does not trigger the skill;
- English, Korean, Italian, and Chinese files became optional diagnostic
  overlays. They load for a language-specific candidate or locale risk rather
  than for every span;
- current model guidance informed the subtraction, but model names, effort,
  tools, and harness controls stay outside the portable domain skill.

This change preserves the evidence ledger and locale safety material. It
removes their role as exhaustive checklists.

## Generation 3 (2026-08): multilingual integrity layers

The earlier package called its anti-slop file language-neutral while it still
contained English rhetoric and treated Korean always-on rules as the generation
baseline for every document. Generation 3 corrected that boundary:

- the common core now covers evidence, relevance, claim force, reader context,
  repetition, and voice protection that can be diagnosed without English
  grammar or punctuation;
- English keeps English-specific rhetoric, syntax, register, and decaying
  surface markers;
- Korean remains evidence-synced to `im-not-ai`, KatFishNet, and Korean
  translationese scholarship;
- Italian uses Italian institutional guidance and grammar scholarship without
  claiming an AI-tell taxonomy;
- Chinese routes by `zh-CN`, `zh-TW`, or `zh-HK` before script and keeps
  regional punctuation, terminology, and official-document overlays bounded;
- unsupported languages receive the common layer and governing locale or
  publication guidance, never a translated English blacklist.

Two overlapping terminology lists were replaced by one contextual catalog.
It asks what relation a term names instead of mapping suspect words to approved
synonyms. The 30% and 50% change-rate thresholds remain a conservative house
policy rather than empirical quality cutoffs. An isolated model cold read is
now described as a self-containment proxy, not actual-reader testing.

## Generation 2 (2026-07): clear-writing

`clear-writing` combines the source families below:

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
- **Two-tier system.** The skill is the on-demand deep tier. The always-on core
  has 15 Korean answer rules. Its canonical block and portable installation
  procedure live in `slop-aware-writing/references/core-rules.md`. Maintainer
  deployments may copy the current block as `clear-writing:core v2` into a
  harness-supported always-on instruction surface.
- **Evidence ledger over flat rules.** Every Korean rule carries its
  justification type: external group-level measurement, unreproduced upstream
  self-study, Korean style evidence, observation-only, or house style. The
  upstream self-study rejected two popular rules (A-2 "~를 통해", I-1
  "것이다"; humans used both more in its sample), so they remain conditioned
  style rules. This revises Generation 1's "one language-neutral core"
  decision: Korean earned a dedicated reference layer inside the same skill,
  synced to upstream pattern IDs with a quarterly delta check.
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

- Source provenance, inspection dates, adopted ideas, rejected ideas, and
  reuse status live in `sources-and-inspiration.md`.
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
- Recheck Italian and Chinese official sources by locale and date before
  changing a language rule. Do not infer a regional convention from script
  alone or extend one generated-text corpus beyond its model and genre.
