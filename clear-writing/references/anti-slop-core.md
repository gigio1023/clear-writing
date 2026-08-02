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
When the evidence boundary already supplies a name, number, case, or mechanism,
use it. Otherwise delete or bound the empty claim, or report the missing fact;
never invent specificity during humanize or surface cleanup. "created a robust
framework" raises the questions: what exists now, who uses it, and how? This is
the deepest tell; surface fixes without substance make low-quality text harder
to spot, not better.

**Abstraction inflation.** Labels stand in for actions ("협업 기반을 구축했다",
"enabled synergies"). Rewrite with the actual mechanism or observable result.
Watch verbs: 구축했다/확보했다/달성했다, enabled/established/facilitated.

**Placeholder actors.** "various teams", "stakeholders", "여러 팀". Name the
actor if the source names it; otherwise bound or quantify the group.

**Verb inflation.** "serves as a centralized hub", "acts as", "functions as",
"made a decision", "has the ability to". Prefer the plain verb — is, has,
tracks, decided, can. A plain "is" beats a fake-strong verb; the inflation
runs both ways (puffed linking verbs and padded verb phrases). (no-ai-slop
lineage.)

**False agency.** Abstractions performing human actions: "the decision
emerged", "the roadmap identified", "a complaint becomes a fix". Name the
person, team, or process. (stop-slop lineage.)

**Unearned authority.** "experts agree", "studies show", "industry reports
suggest" with no citation. Either cite the real source or drop the appeal.

**Lone-expert framing.** "What nobody tells you", "the part everyone misses",
"what most people get wrong" — flatters the writer as the sole insider. Cut
the setup and let the claim stand on its own. (no-ai-slop lineage.)

**Undue significance.** "stands as a testament", "plays a crucial/pivotal
role", "underscores the importance", "시사하는 바가 크다" — importance
inflation applicable to any subject. Delete it, or use a concrete consequence
already established inside the evidence boundary.

**Negative listing.** "It's not just X. Not Y either. It's Z." — rhetorical
striptease withholding the point. State Z. (stop-slop lineage.)

**Colon reveals.** Noun phrase, colon, dramatic payoff: "The best part: it
learns." Rewrite as a plain sentence; reserve colons for lists, labels, and
quotes. (no-ai-slop lineage.)

**Rhetorical setups.** "What if I told you...", "Plot twist:", "Think about
it:", and self-answered "Question? Answer." pairs. Drop the setup and make
the point. (no-ai-slop lineage.)

**Dramatic fragmentation.** "X. And Y. And Z.", "That's it. That's the whole
thing." — stacked punchy fragments as manufactured emphasis. Use complete
sentences; keep a fragment only when it is the author's own established
voice. (no-ai-slop lineage.)

**Narrator-from-a-distance.** "Nobody designed this", "There's something
profound about..." — detached voiceover replacing an embedded speaker. Restore
the direct claim: who did what. (stop-slop lineage.)

**Throat-clearing openers.** "Here's the thing", "Let me be clear", "I'll be
honest", "The uncomfortable truth is" — delay dressed as candor. Cut and
state the point; keep a personal aside that genuinely adds context or
character. (no-ai-slop lineage.)

**Formulaic wrap-ups.** "In conclusion", "결론적으로", a "Future Outlook"
section, or a closing paragraph that re-summarizes the page. The last body
paragraph is the conclusion. Same family: the fake-profound kicker — a
closing aphorism, metaphor, or mic-drop line. Delete it; do not rewrite it
into a better metaphor. End on the last concrete sentence the draft already
has, adding a plain takeaway or next action only when closure is genuinely
missing and authoring, compose, or full-revision evidence already supports it.
Humanize and surface cleanup stop at the last supported sentence.
(no-ai-slop lineage.)

**Present-participle pseudo-analysis.** "...ing" clauses tacked on for fake
depth: "...highlighting the tradition", "...ensuring continuity". Cut or turn
into a real causal sentence.

**Symmetric contrast formulas.** "not X but Y", "A인가, B인가", chiasmus and
tricolon cadence repeated across paragraphs. If deleting the negative side
does not erase a meaning-bearing correction, state the conclusion once.
Otherwise preserve the redefinition. (The 9.2× Korean figure comes from an
unreproduced upstream self-study; see `korean-tells.md` C-8.)

**Synonym cycling.** One referent rotated through synonyms for style — "the
agent reviews... the assistant scores... the tool suggests". If the clear
word is right, repeat it; route genuine naming doubts to `terminology.md`.
(no-ai-slop lineage.)

**Empty modifiers.** robust, seamless, significant, innovative, strategic,
effectively — cut unless carrying real scope, or replace only with a fact that
the evidence boundary already establishes.

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
- **"Reads natural to me" = pass.** A gut read does not verify facts, sources,
  reader context, or voice preservation. Use the delivery gates (`gates.md`)
  and check facts against the evidence boundary.
- **AI-sounding = AI-authored.** Never claim authorship; report the wording
  problem itself. Heuristic "sounds AI" judgments systematically misfire on
  authentic non-standard voices.
