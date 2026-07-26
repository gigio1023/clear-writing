# Delivery Gates

Run before delivering any authored or revised document. Apply to the changed
scope, not mechanically to every page. The bar is these gates plus fact
preservation — never "it reads natural to me" (human judgment of AI-ish text
is near chance).

## Gate 1 — Reader and purpose

- The intended reader and the page's primary job are clear from the top.
- The main problem, decision, or command appears before background.
- A new reader can follow the document without the chat history that produced
  it; local shorthand is explained at first use.

## Gate 2 — Fact preservation (hard gate)

- Commands, paths, identifiers, numbers, units, dates, versions, links, and
  quotations match the source or repository evidence.
- Conditions survived: no "when/may/optional/unit/version limit" silently
  dropped; requirement level (must/should/may) unchanged.
- Nothing was invented: no new facts, examples, citations, metaphors, or
  quotations that the source does not support.
- Genuine uncertainty is still visible; a style edit did not silently resolve
  a factual conflict.

## Gate 3 — Language quality

- Label-heavy and placeholder phrasing reduced where the source allows
  (`anti-slop-core.md`).
- Structure inflation cleared without deleting WHY anchors or guide-section
  tone (`structure-anti-patterns.md`).
- Korean documents: strongest-signal patterns checked
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
