# Anti-Slop Core (Language-Neutral)

Sentence- and tone-level signals that make prose read machine-generated, with
fixes. Ordered by evidence durability: structural and substance signals stay
valid across model generations; surface markers (word lists, punctuation
habits) decay per model release. Weight your effort accordingly.

Firing rule: single occurrences are usually coincidence. Flag clusters — one
sentence with one tell is fine; a paragraph stacking three is not. Removal
only: never insert a replacement cliché, invented fact, or fake citation to
"fix" a pattern.

## Contents

- [Durable signals](#durable-signals-fix-first)
- [Surface signals](#surface-signals-decaying--check-last)
- [Do-not-flag list](#do-not-flag-list)
- [Myths](#myths-do-not-encode)

## Durable signals (fix first)

**Genericness.** The sentence could appear in any document about any subject.
Fix by adding one concrete, checkable detail: a name, a number, a case, a
mechanism. "created a robust framework" → what exists now, who uses it, how?
This is the deepest tell; surface fixes without substance make low-quality
text harder to spot, not better.

**Abstraction inflation.** Labels stand in for actions ("협업 기반을 구축했다",
"enabled synergies"). Rewrite with the actual mechanism or observable result.
Watch verbs: 구축했다/확보했다/달성했다, enabled/established/facilitated.

**Placeholder actors.** "various teams", "stakeholders", "여러 팀". Name the
actor if the source names it; otherwise bound or quantify the group.

**False agency.** Abstractions performing human actions: "the decision
emerged", "the roadmap identified", "a complaint becomes a fix". Name the
person, team, or process. (stop-slop lineage.)

**Unearned authority.** "experts agree", "studies show", "industry reports
suggest" with no citation. Either cite the real source or drop the appeal.

**Undue significance.** "stands as a testament", "plays a crucial/pivotal
role", "underscores the importance", "시사하는 바가 크다" — importance
inflation applicable to any subject. Delete or replace with the concrete
consequence.

**Negative listing.** "It's not just X. Not Y either. It's Z." — rhetorical
striptease withholding the point. State Z. (stop-slop lineage.)

**Narrator-from-a-distance.** "Nobody designed this", "There's something
profound about..." — detached voiceover replacing an embedded speaker. Restore
the direct claim: who did what. (stop-slop lineage.)

**Formulaic wrap-ups.** "In conclusion", "결론적으로", a "Future Outlook"
section, or a closing paragraph that re-summarizes the page. The last body
paragraph is the conclusion.

**Present-participle pseudo-analysis.** "...ing" clauses tacked on for fake
depth: "...highlighting the tradition", "...ensuring continuity". Cut or turn
into a real causal sentence.

**Symmetric contrast formulas.** "not X but Y", "A인가, B인가", chiasmus and
tricolon cadence repeated across paragraphs. State the conclusion once,
plainly. (Korean measurement: 9.2× AI-vs-human — see
`korean-tells.md` C-8.)

**Empty modifiers.** robust, seamless, significant, innovative, strategic,
effectively — cut unless carrying real scope, or replace with the fact that
earned the adjective.

**Hedging overload.** Stacked "typically/might/may/could" avoiding any
commitment. Commit where the source supports it; keep genuine uncertainty
visible and specific.

## Surface signals (decaying — check last)

Treat as look-closer prompts, never as proof or as primary rewrite targets.

- **Marker words** (delve, underscore, boast, intricate, meticulous, pivotal,
  tapestry, showcase...): real but era- and model-specific; lists drift per
  generation. Flag density, not single hits. Single words also misfire on
  regional and non-native English — never treat one word as evidence.
- **Punctuation habits** (em-dash frequency, curly quotes): vendor-dependent
  and steadily patched away. House-style prohibitions live in
  `profiles.md`, not here.
- **Vendor artifacts** (`oaicite`, `contentReference`, `[cite: N]`,
  `grok_card`): definitive when present — always remove.
- **Markdown leakage** into non-Markdown contexts; emoji bullets; title-case
  headings mid-document.

## Do-not-flag list

Preserve these even when a rule seems to match:

- Established domain terms and accurate technical vocabulary — route genuine
  terminology doubts to `terminology.md` instead of swapping
  synonyms.
- Hard-to-fabricate specifics: named incidents, dates, numbers, first-person
  experience.
- Intentional repetition (spec obligations, safety warnings, refrains).
- Deliberate voice: dialect, regional or non-native phrasing, era-bound slang,
  mixed feelings, deliberate fragments. A rule firing on the writer's
  repeated intentional choice is a category error, not a finding.
- Explicit uncertainty markers — do not erase doubt to sound decisive.
- Metaphors that genuinely aid comprehension.

## Myths (do not encode)

- **Burstiness/perplexity as a verdict.** Statistical uniformity checks fail
  on current-generation models. Vary cadence as craft, never as a detector.
- **Marker-word removal = humanized.** Necessary at most; genericness survives
  synonym swaps.
- **"Reads natural to me" = pass.** Human detection accuracy is near chance
  (57-64% in controlled studies). The bar is the delivery gates
  (`gates.md`) plus fact preservation, not a gut read.
- **AI-sounding = AI-authored.** Never claim authorship; report the wording
  problem itself. Heuristic "sounds AI" judgments systematically misfire on
  authentic non-standard voices.
