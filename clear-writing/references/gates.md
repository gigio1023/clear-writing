# Delivery Gates

Run before delivering any authored or revised document. Apply to the changed
scope, not mechanically to every page. The bar is these gates plus fact
preservation, not "it reads natural to me."

## Contents

- Cold reader, purpose, and relevance
- Source, claim, and fact integrity
- Slop removal and language floor
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
- Chinese localization also spot-checks official names, UI strings, regional
  terminology, punctuation, and protected code or product literals against the
  selected locale. Script conversion alone does not pass this gate.
- Conditions survived: no "when/may/optional/unit/version limit" silently
  dropped; requirement level (must/should/may) unchanged.
- Nothing was invented: new facts, examples, citations, metaphors, opinions,
  or quotations all stay inside the evidence boundary.
- Genuine uncertainty is still visible; a style edit did not silently resolve
  a factual conflict.

## Gate 3 — Slop removal and language floor

- The edit names and repairs a reader-visible failure from the common slop
  definition. It does not merely exchange a flagged phrase for a preferred one.
- The dominant cluster was tested against the reader job, evidence, deletion
  cost, and writer's voice (`anti-slop-core.md`).
- Structure inflation cleared without deleting a needed warrant, condition,
  or guide-section tone (`structure-anti-patterns.md`).
- Ordinary grammar and idiom were handled contextually. An obvious local error
  encountered during revision was fixed only when one correction preserved
  meaning, register, dialect, and voice. No full proofreading pass is implied.
- A language overlay was loaded only when a language-specific candidate or
  locale risk justified it: English (`english-writing.md`), Korean
  (`korean-tells.md`), Italian (`italian-writing.md`), or Chinese
  (`chinese-writing.md`). Its cues were not applied as an exhaustive checklist.
- Mixed-language documents preserved identifiers, quotations, borrowed terms,
  and locale-specific script. Unsupported languages received no invented tell
  list. Terminology stayed stable once chosen.

## Gate 4 — Change-rate guard

Estimate the changed share of word-units against the original (revision work
only):

- **> 30%**: warn in the report; re-verify Gate 2 span by span.
- **> 50%**: stop. Do not deliver a silent full rewrite — either the request
  authorized a rewrite (say so explicitly) or return to the user with the
  reason the text needs more than editing.

Never present change volume, pattern counts, or a letter grade as a quality
score in either direction.

The 30% and 50% thresholds are a conservative repository operating policy, not
an empirically validated quality boundary. A lower change rate can still alter
meaning; an explicitly authorized rebuild can exceed 50% after full source and
voice verification.

## Gate 5 — Editor-slop test (self-check on OWN output)

Read your rewrite and your report as if told "an LLM wrote this":

- Does the rewrite now carry tells the original lacked (stock transitions,
  symmetric contrasts, upgraded vocabulary, formulaic wrap-up)?
- Did correction make the text uniformly polished while erasing a precise,
  unusual, dialectal, or personal choice?
- Voice drift check (`voice-preservation.md`): were stance, causal chains,
  register, recurring choices, and language-specific rhythm preserved?
- Is the report itself free of the patterns this skill removes?

Any failure: fix before delivery, not after.

## Gate 6 — Verification actions

- Re-read the complete changed page top to bottom, as its intended reader.
- For a new or materially rebuilt document, use an isolated fresh-context
  reader when available: provide only the document and intended reader role,
  then test realistic questions, hidden assumptions, ambiguous references, and
  contradictions. With no isolated context, perform the same cold read
  sequentially. An LLM reader is a low-cost self-containment proxy, not a test
  of factual accuracy or actual-user comprehension. Recommend representative
  reader testing when misunderstanding is consequential.
- Inspect the diff for unrelated churn and accidental deletions of scope,
  prerequisites, exceptions, or ownership.
- After script or locale normalization, reread the complete affected scope and
  spot-check proper names, regional vocabulary, punctuation, quotations, and
  protected literals.
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
