# Voice Preservation

Rewriting can homogenize voice and alter meaning even when the task sounds
surface-level. Compare the result with the supplied draft and approved voice
sample; do not assume that post-editing automatically restores ownership or
personal style. English studies below motivate the caution but do not establish
the same markers or effect sizes in Korean, Italian, Chinese, or other genres.

## Contents

- Sample outranks built-in defaults
- Markers to preserve under revision
- Registers with no personal voice
- Anti-homogenization rules
- Interaction with other references
- English evidence and its limits

## Sample outranks built-in defaults

When the request asks to preserve voice, or sets no different target voice, the
user's or repository author's prior writing defines the target and outranks the
skill's profiles and defaults. An explicit current target and governing
repository requirements still bind the rewrite. Derive from the sample:
sentence-length range, formality/어미 register, contraction habits, first- vs
third-person stance, characteristic connectors, and vocabulary register.
Without a sample, aim for the register the document type demands, not a house
style of this skill.

## Markers to preserve under revision

As a conservative editing policy across languages, do not "improve away":

- Language-specific register choices, including English contractions, Korean
  speech level, Italian impersonal style, and Chinese regional usage.
- First-person stance and embedded narration — do not distance the narrator
  ("I chose X because" must not become "X was selected to").
- Explicit causal chains ("because A, so B") — do not compress into abstract
  nominalizations.
- Sentence-length variance the author already has, including genuinely long
  sentences and fragments.
- Idiosyncrasies: recurring phrases, dialect, regional or non-native phrasing,
  humor, mixed feelings. A pattern rule firing on the author's deliberate,
  repeated choice is a category error.

## Registers with no personal voice

Audit memos, technical reviews, specs, and runbooks are often impersonal by
design: no first person, directive endings ("-하라", "must"), and explicit
epistemic status ("확인됨 / 추정 / 미확인", "not confirmed"). The markers above
have little surface to grab there, and their absence is not drift — do not
"restore" a first-person stance the document never had, and do not warm up a
directive register into a conversational one.

What to protect instead, because it is this register's voice:

- Epistemic status marking: confidence labels, "증거 아님" disclaimers,
  falsification conditions. Never flatten a hedged claim into a flat one, or a
  flat one into a hedged one.
- Directive endings where the document's job is issuing decisions.
- Repeated structural formulas that carry an audit convention rather than
  filler (per-item verdict lines, evidence citations).

## Anti-homogenization rules

- **Mode boundary.** Humanize and surface cleanup are removal-first: delete or
  tighten slop, and never insert stock transitions, invented examples, fake
  citations, or replacement clichés. Compose and full revision may restore
  necessary context or reasoning only inside the evidence boundary in
  `source-grounding.md`.
- **No vocabulary upgrades.** Do not swap plain words for rarer synonyms or
  lengthen words merely to sound polished. The bounded English evidence below
  observed that direction in one setting; meaning preservation is the common
  reason for this rule.
- **Watch for unauthorized drift while editing.** Compare stance, information
  order, register, recurring phrases, sentence rhythm, and lexical range with
  the source. Do not use one English study's marker direction as a multilingual
  checklist.
- **Batch rule.** When revising multiple documents (or one author's varied
  notes), do not converge them toward one safe middle voice; preserve
  per-document register differences.
- **Uncertainty stays.** Keep hedges that mark genuine doubt; deleting doubt
  to sound decisive falsifies the text.

## Interaction with other references

The common core and matching English, Korean, Italian, or Chinese layer say
what to review; this file bounds how far removal may go. When they conflict
with a deliberate author choice, voice wins and the finding is reported
instead of applied.
The editor-slop test in `gates.md` is the enforcement point: rewrites
that stripped voice markers fail delivery.

## English evidence and its limits

Van Nuenen's 2026 preprint on 300 English personal narratives found directional
normalization on selected markers. A voice-preserving prompt reduced the mean
effect magnitude by 32%; direction agreement was 85%, with two marker
reversals. In that sample, contractions, first person, and function words often
decreased while lexical and punctuation complexity increased. Treat those
directions as an English personal-narrative audit prompt only.

Baumler and colleagues' preregistered ACL 2026 study asked 81 English-proficient
participants to edit model-drafted personal writing. Editing moved text toward
the participants' measured style, yet the edited text remained closer to model
drafts than independently written text and became more homogeneous across
participants. This supports minimal effective edits and keeping original
human-drafted material when possible. It does not make a style metric an
authorship detector or prove that every assisted draft loses voice.

A 2026 preprint by Abdulhai and colleagues reports meaning and style changes
even in correction-oriented model assistance. Its settings do not justify a
universal effect size, but they reinforce the existing hard gate: after any
grammar or polish pass, recheck facts, stance, conditions, and logical
relations instead of trusting the narrow task label.
