# Delivery Gates

Run before delivering any authored or revised document. Apply to the changed
scope, not mechanically to every page. The bar is these gates plus fact
preservation, not "it reads natural to me."

## Contents

- Cold reader, purpose, and relevance
- Source, claim, and fact integrity
- Language quality
- Change-rate guard
- Editor-slop test
- Verification actions
- Report format

## Gate 1 — Cold reader, purpose, and relevance

- The intended reader and the page's primary job are clear from the top.
- The opening matches that job: decision or finding for analysis, first useful
  action for a procedure, lookup scope for reference, or necessary context for
  architecture and history.
- From the document alone, a new reader can recover the subject and, as the
  genre requires, current state, problem or decision, evidence, constraints,
  and next action. Local shorthand is explained at first use.
- No phrase points only into the drafting session or hidden worktree:
  "as discussed", "this task", an unexplained task ID, branch-only shorthand,
  or a numbered option whose definition is absent.
- Every section, example, statistic, table, chart, and diagram serves the
  reader job, necessary context, a supported claim, or a reader action.
  Interesting but orphaned material is removed.
- Ordinary docs describe the current subject. Diff narration remains only
  when change is the reader job, such as changelogs, release notes, migration
  guides, ADRs, histories, and retrospectives.

## Gate 2 — Source, claim, and fact integrity (hard gate)

- The evidence boundary is explicit enough to audit. Material external or
  mixed claims pass `source-grounding.md`; model memory, snippets, generated
  summaries, and copied aggregations are leads rather than proof.
- Consequential sources match the claim's actor, mechanism, scope, conditions,
  and time. Authorship, publication or update date, version, and currentness
  were checked where they can change the conclusion.
- In decision and analysis documents, each material claim has a reason or
  evidence, visible connective logic where needed, and material limits. Claims
  without support are labeled as inference, assumption, or unverified; evidence
  without a claim, necessary context, or reader action is removed.
- Reference and procedural docs were checked against current behavior,
  prerequisites, constraints, actions, and observable verification instead of
  being forced into an argument shape.
- Commands, paths, identifiers, numbers, units, dates, versions, links, and
  quotations match the source or repository evidence.
- Conditions survived: no "when/may/optional/unit/version limit" silently
  dropped; requirement level (must/should/may) unchanged.
- Nothing was invented: new facts, examples, citations, metaphors, opinions,
  or quotations all stay inside the evidence boundary.
- Genuine uncertainty is still visible; a style edit did not silently resolve
  a factual conflict.

## Gate 3 — Language quality

- Label-heavy and placeholder phrasing reduced where the source allows
  (`anti-slop-core.md`).
- Structure inflation cleared without deleting WHY anchors or guide-section
  tone (`structure-anti-patterns.md`).
- Korean documents: measured-priority patterns checked with their evidence
  limits and keep tests
  (`korean-tells.md`); English documents: durable signals
  checked. Terminology stayed stable once chosen.

## Gate 4 — Change-rate guard

Estimate the changed share of word-units against the original (revision work
only):

- **> 30%**: warn in the report; re-verify Gate 2 span by span.
- **> 50%**: stop. Do not deliver a silent full rewrite — either the request
  authorized a rewrite (say so explicitly) or return to the user with the
  reason the text needs more than editing.

Never present change volume, pattern counts, or a letter grade as a quality
score in either direction.

## Gate 5 — Editor-slop test (self-check on OWN output)

Read your rewrite and your report as if told "an LLM wrote this":

- Does the rewrite now carry tells the original lacked (stock transitions,
  symmetric contrasts, upgraded vocabulary, formulaic wrap-up)?
- Voice drift check (`voice-preservation.md`):
  contractions/first-person/causal chains preserved? Word length and
  punctuation elaboration not inflated?
- Is the report itself free of the patterns this skill removes?

Any failure: fix before delivery, not after.

## Gate 6 — Verification actions

- Re-read the complete changed page top to bottom, as its intended reader.
- For a new or materially rebuilt document, use an isolated fresh-context
  reader when available: provide only the document and intended reader role,
  then test 3-5 realistic questions plus hidden assumptions, ambiguous
  references, and contradictions. With no isolated context, perform the same
  cold read sequentially. This tests comprehension, not factual accuracy.
- Inspect the diff for unrelated churn and accidental deletions of scope,
  prerequisites, exceptions, or ownership.
- Search inbound references before renaming headings or anchors.
- Run the repository's docs checks (formatter, link checker, build) when
  available and proportionate; `git diff --check` where applicable.
- Distinguish in the report: checks run, inspected-only, unavailable.

## Report format

Lead with the deliverable (or highest-impact findings for review mode).
Review-mode findings quote the offending line, name the pattern, and give the
fix in a few words — a quoted pattern is evidence the user can check; scores
and authorship guesses are not. Then,
briefly: files touched, major patterns fixed or structural decisions, checks
run with results, and spans left unchanged because meaning could not be
proven preserved. No grades, no change-rate percentages as scores, no process
narration.
