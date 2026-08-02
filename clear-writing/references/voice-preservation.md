# Voice Preservation

Rewriting can homogenize voice. A 2026 preprint on 300 English personal
narratives found directional normalization on selected markers. A
voice-preserving prompt reduced mean effect magnitude by 32%; direction
agreement was 85%, with two marker reversals. The study does not establish the
same rates or directions in other languages or genres. Use it as a reason to
audit drift conservatively, not as universal proof.

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

- Contractions and casual function words where the register allows them
  (English: don't/it's; Korean: 구어형 연결, 해요체 in guides).
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
  lengthen words to sound polished — that is the measured direction of
  machine drift.
- **Watch the drift direction while editing**: contractions ↓, first person ↓,
  function words ↓, word length ↑, punctuation elaboration ↑ = you are
  homogenizing. Stop and restore.
- **Batch rule.** When revising multiple documents (or one author's varied
  notes), do not converge them toward one safe middle voice; preserve
  per-document register differences.
- **Uncertainty stays.** Keep hedges that mark genuine doubt; deleting doubt
  to sound decisive falsifies the text.

## Interaction with other references

Slop patterns (`anti-slop-core.md`,
`korean-tells.md`) say what to remove; this file bounds how
far removal may go. When they conflict — a "tell" that is actually the
author's voice — voice wins, and the finding is reported instead of applied.
The editor-slop test in `gates.md` is the enforcement point: rewrites
that stripped voice markers fail delivery.
