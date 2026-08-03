# Common Integrity and Anti-Slop Core

Use this layer for every deslop job. It defines AI slop by what the prose does
to a reader, never by who or what wrote it. The same defects can occur in human
drafts and can survive translation. Language overlays hold a small number of
evidence-backed cues that this common diagnosis may miss.

## Contents

- Working definition
- LLM-native diagnosis
- Firing rule
- Substance and evidence
- Reader and relevance
- Prose and structure
- Surface signals
- Keep list
- Never encode

## Working definition

AI slop is prose whose plausible, complete-looking surface substitutes for the
selection, evidence, and point of view the document needs. It usually appears
as one or more of four reader-visible failures, regardless of authorship:

1. **Generic completion:** claims, benefits, actors, examples, or conclusions
   could be transferred to an unrelated document with little change.
2. **Performed reasoning:** citations, transitions, contrasts, or confident
   synthesis imitate an argument whose relation the source never establishes.
3. **Reader displacement:** template sections, process narration, hidden chat
   context, and exhaustive side paths occupy space needed for the reader's job.
4. **Voice flattening:** repeated safe phrasing, uniform cadence, synonym
   display, and prestige vocabulary erase the writer's stable choices.

Grammatical correctness does not cure these failures. A grammatical sentence
can still be empty, irrelevant, or unsupported. A nonstandard sentence can
still be exact, purposeful, and recognizably the writer's.

## LLM-native diagnosis

Use contextual language understanding instead of expanding a lint catalog:

1. Read the complete relevant scope and identify its reader job, supported
   point, evidence boundary, and recurring voice.
2. Form one short working hypothesis about the dominant slop failure in this
   document. Do not expose private reasoning or force every category to fire.
3. Test candidate spans semantically:
   - **transfer test:** could this span fit an unrelated product or topic?
   - **support test:** what source or nearby reasoning licenses the claim and
     relation?
   - **reader test:** what decision, understanding, or action does it enable?
   - **deletion test:** what fact, condition, relation, or voice is lost if it
     disappears?
   - **voice test:** does the rewrite move toward the writer's repeated choices
     or toward generic polished prose?
4. Fix the dominant cluster first with the smallest edit that passes those
   tests. Re-read the paragraph or section because a locally fluent rewrite can
   still damage long-range meaning.

The model already knows ordinary syntax, idiom, and spelling across many
languages. Use that competence to understand and revise context. Add a written
rule only for a recurring slop failure, an evidence boundary, or a meaning-risk
that general fluency does not reliably protect.

## Firing rule

Diagnose function before surface form. One familiar word or construction is
rarely a defect. Act when a direct reader harm is clear or when a pattern
clusters through a paragraph or section. Preserve a deliberate voice choice.
If the only finding is a debatable grammar preference, this layer does not fire.

## Substance and evidence

**Generic claim.** The sentence could fit any product, team, or event. Replace
it with a supported mechanism, actor, constraint, or result. If none exists,
bound the claim or remove it. Never invent a number or example to make prose
look concrete.

**Unsupported authority.** Phrases equivalent to "experts agree" or "research
shows" borrow credibility without a traceable source. Cite evidence that
actually supports the claim or state the claim at the strength the evidence
allows.

**Evidence theatre.** A citation can still be irrelevant, stale, circular, or
derived from another generated summary. Inspect the underlying source and
check claim fit, date, scope, and provenance. More citations do not repair a
bad evidence chain.

**Claim-force drift.** Revision turns "may", "in this sample", or "the author
reports" into a general fact. Restore modality, population, timeframe, and
attribution. Preserve distinctions such as cause versus correlation,
observation versus recommendation, and absence of evidence versus evidence of
absence.

**Invented connective logic.** Smooth transitions can manufacture causality,
priority, sequence, consensus, or contrast. Add a relation only when the
source establishes it. Otherwise keep the statements separate or mark the
relation as an inference.

## Reader and relevance

**Session dependence.** References such as "as discussed above", "the latest
change", "our earlier conversation", or unexplained task IDs assume hidden
context when no recoverable in-document referent exists. Keep a clear internal
cross-reference. Otherwise name the subject, current state, decision, and owner
that the intended reader actually needs.

**Wrong center of gravity.** The document spends more space on an incidental
tool, edge case, implementation detour, or source anecdote than on its reader
job. Keep a detail only when it supports a claim, supplies necessary context,
changes a decision, or enables an action.

**Missing warrant.** A claim and a fact appear together without saying why the
fact supports the claim. Add the shortest supported relation a cold reader
needs. Do not merely place a table under a headline and make the reader infer
the argument.

**Template completion.** Sections exist because a familiar template suggested
them, not because readers need them. Remove empty background, benefits, future
outlook, and conclusion sections. A template is a question set, not a quota.

## Prose and structure

**Abstraction inflation.** Labels replace observable action. Name what changed,
who or what changed it, and the supported consequence. Keep established domain
abstractions when they are the precise term.

**Placeholder actor.** Terms equivalent to "various teams" or "stakeholders"
hide who acts or decides. Use the named actor from the evidence, define the
group, or keep the limit explicit.

**Synonym cycling.** One referent receives new names merely to avoid repetition.
Repeat the stable term. Route genuine naming uncertainty to the terminology
pass.

**Restatement loops.** The heading, opening sentence, bullets, and closing
sentence repeat the same point at different levels of formality. Keep the
version that best serves the reader and use the saved space for evidence or
necessary action.

**Manufactured emphasis.** Repeated fragments, binary contrasts, rhetorical
questions, dramatic reveals, and ceremonial conclusions can make the form
louder than the claim. Flatten them when they delay or inflate the point.
Preserve a meaning-bearing correction, contrast, or established author voice.

**Unsupported ending.** A confident takeaway, promise, aphorism, or call to
action goes beyond the evidence. End on the last supported conclusion or next
step. Do not replace one empty kicker with another.

## Surface signals

Word lists, punctuation habits, sentence-length variance, and vendor-specific
formatting decay across models, regions, and genres. Let the model recognize
them in context, then use them only as look-closer prompts inside a matching
language overlay. Never turn them into authorship evidence or automatic
replacements. Remove literal generation artifacts and broken markup when they
do not belong in the target format.

## Keep list

Keep accurate domain terms, required repetition, safety language, quotations,
intentional dialect or non-native voice, genuine uncertainty, useful metaphor,
and genre-required structure. A text can be polished and still sound like its
writer. It does not need to approximate one prestige dialect or one corporate
register.

## Never encode

- authorship verdicts from style
- universal banned-word lists
- perplexity, burstiness, or sentence variance as quality scores
- mandatory active voice, short sentences, headings, bullets, charts, or
  conclusion-first structure across genres and languages
- specificity invented during cleanup
