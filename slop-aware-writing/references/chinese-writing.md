# Chinese Writing Layer

Load this file only when a Chinese-specific slop candidate or locale risk
survives the common diagnosis, or when the user requests intra-Chinese
normalization. It is not a Chinese grammar guide. Use ordinary model fluency
for well-formedness. Choose locale before changing script, punctuation, or
terminology because `zh-CN`, `zh-TW`, and `zh-HK` are not interchangeable.

This is a prose and intra-Chinese consistency layer, including script and
locale normalization. It does not translate between languages or detect
authorship.

## Contents

- Evidence and precedence
- Locale intake
- Protected spans
- Locale safety when normalization is in scope
- Terminology by locale
- Corpus-based review cues
- Bureaucratic scaffolding
- AI-related evidence boundary
- Self-check

## Evidence and precedence

Use this order: explicit user instruction, governing repository or publisher
style, official entity and product spelling, supplied reference, locale source,
then this file's defaults. Regional standards outrank cross-region synthesis
for their locale. Corpus findings below are review cues with keep tests, not
errors or AI signals.

## Locale intake

| Locale | Default sources | Boundary |
|---|---|---|
| `zh-CN` | Simplified script, GB/T 15834 punctuation, PRC standard characters and terminology | Do not extend Mainland choices to Singapore, Malaysia, or region-unknown `zh-Hans`. |
| `zh-TW` | Traditional script, Taiwan MOE punctuation and glyph sources, Taiwan terminology | Horizontal prose commonly uses `「」` and `『』`; publisher style may override. |
| `zh-HK` | Traditional script, Hong Kong glyph and government-language sources | Do not silently Taiwan-localize wording or punctuation. |
| `zh-Hans` or `zh-Hant`, region unknown | Preserve the document's dominant convention | Script does not prove region. Ask only when the unresolved choice materially changes delivery. |

Macau, Singapore, and Malaysia are not separately grounded in this version.
Preserve house style and name the locale gap when it matters.

## Protected spans

Do not normalize code, commands, URLs, regular expressions, Markdown syntax,
schema fields, API signatures, product literals, trademarks, official entity
names, or quotations. Change an official name or UI string only after verifying
the target locale's canonical form.

## Locale safety when normalization is in scope

For an ordinary deslop pass, preserve the document's established script and
punctuation unless inconsistency participates in the diagnosed failure. Do not
turn revision into full localization without that authority.

**Conversion can become localization.** Simplified and Traditional conversion must
review vocabulary, regional terms, glyphs, punctuation, proper names, legal
titles, UI strings, and quotations. Automatic locale conversion can also
substitute regional vocabulary. That is a lexical edit, not character
conversion alone.

**Quotation marks.** `zh-CN` horizontal prose normally follows GB/T 15834 with
`“”` and `‘’`. `zh-TW` horizontal prose follows Taiwan MOE guidance with `「」`
and `『』`. `zh-HK` preserves the publisher or repository convention; Traditional
script alone does not imply Taiwan punctuation. Quoted source punctuation and
explicit house style take precedence.

**Renderer boundary.** Forbidden line starts and ends, punctuation compression,
hanging punctuation, vertical placement, and unbreakable marks usually belong
to CSS, a typesetter, or a fixed-layout export. Do not insert manual spaces or
line breaks in Markdown to simulate typography. Edit source layout only when
the requested artifact has fixed pages or lines.

## Terminology by locale

When a slop or normalization edit touches terminology, resolve it from the
repository or product glossary, official entity or UI spelling, supplied
reference, then a locale terminology source. Do not batch-replace pairs such as
`软件/軟體`, `信息/資訊`, or `用户/使用者`; they encode region and audience, not
script alone.

## Chinese-specific slop lenses

Corpus distributions prompted the editorial heuristics below, but the studies
did not measure stacking, repetition, nesting, or reader harm directly. Apply
an edit only when the target sentence itself is ambiguous, repetitive, or
harder to follow.

**Potentially redundant prepositional framing.** Review `在……方面/情况下`,
`对于/关于`, `通过/经由`, and `由/被`, especially when several frames obscure
the main relation and an English source exists. Keep them when they carry
location, legal scope, time, cause, agent, recipient, or contrast.
`在系统发生故障的情况下` may become `系统故障时`; `关于退款的规定` stays when it
names the regulation's scope.

**Explicit subject and personal pronouns.** Corpus frequencies can prompt a
context check, not deletion. Merge or remove a repeated pronoun only when the
actor remains unambiguous. Keep pronouns for contrast, emphasis, accessibility,
quoted voice, or multiple plausible antecedents.

**Dense `NP+的` modification.** A corpus difference does not prove that a given
chain is wrong. Verbalize or split it only when attachment is hard to parse.
Preserve official names and stable technical noun phrases. Confirm the
attachment before rewriting; do not merely delete every second `的`.

**Parallel inflation.** Reduce strings such as `全面、系统、深入地` or repeated
synonymous clauses only when they add no separate requirement. Keep distinct
test dimensions, procedural stages, taxonomies, and quoted rhetoric.

## Bureaucratic scaffolding

Cut vague purpose frames, ceremonial transitions, stale clichés, and support
verbs when they add no legal, administrative, evidentiary, status, or deference
function. Preserve genuine conditions and authority. A phrase like
`为了达到提高稳定性的目的` can often become `为提高稳定性`, but the source must
still support the stated purpose.

Official-document overlays activate only for their genre: GB/T 9704 and PRC
regulations for Mainland Party or government documents, the Executive Yuan
manual for Taiwan official documents, and the Civil Service Bureau handbook
for Hong Kong government documents. Do not import their page formats,
ceremonial formulas, or section names into READMEs, API docs, blogs, or product
copy.

## AI-related evidence boundary

Chinese LLM studies are conditioned by model generation, prompts, genre, date,
source-language mix, and human editing. They support multidimensional review,
not a durable phrase list. None of the following proves authorship or quality:

- pronoun, conjunction, preposition, or parallel-phrase counts
- long or similarly sized sentences
- correct punctuation or low typo frequency
- a classifier's aggregate accuracy applied to one passage
- a translationese feature treated as an error by itself

Do not add slang, rare words, errors, emotional language, or punctuation noise
to appear human. Fix the reader-visible defect and never infer who wrote the
text.

## Self-check

- Was locale resolved from evidence rather than script alone?
- Are punctuation, terminology, and glyph choices consistent with that locale
  or the explicit publication style?
- Were protected literals, quotations, proper names, UI strings, conditions,
  and requirement groupings preserved?
- Did every corpus cue pass its ambiguity or reader-harm keep test?
- Were line-layout problems left to the renderer when source editing cannot
  solve them safely?
- Did the pass stop before becoming general Chinese proofreading or
  unrequested localization?
