# deslop-doc-writer

Draft skill repo for a writing skill that combines two jobs that are usually split apart:

- remove AI-sounding prose and abstraction-heavy phrasing
- produce documents that are readable on their own, with enough context and clear structure

The current draft merges two source lines:

- external anti-slop reference work from `stop-slop`
- existing internal document-composition ideas from `human-readable-doc-composer`

`humanize` is treated here as the user's own adjacent skill, not as an external source to borrow from blindly. It is a nearby internal precedent, not the reference baseline for this draft.

## Goal

Build one skill that can handle both:

1. "make this sound less AI-generated"
2. "rewrite this into a document people can actually read and use"

The working assumption is that these are usually the same problem from two angles:

- sentence-level problem: vague labels, placeholders, false agency, metronomic rhythm
- document-level problem: weak flow, missing context, unstable terminology, over-compressed reasoning

## Repo layout

```text
deslop-doc-writer/
  SKILL.md
  references/
    anti-slop-patterns.md
    document-modes.md
    output-contract.md
    readability-gates.md
docs/
  merge-notes.md
```

## Current scope

- Correction mode: rewrite an existing draft without changing facts
- Compose mode: turn messy notes or partial drafts into a readable standalone document
- Hybrid mode: default for most medium/long docs, where both correction and restructuring are needed

## Not in scope

- Fact-checking or web verification
- Translation
- Pure grammar fixing with no readability issue
- Domain expertise substitution

## Next draft questions

- Should this remain one skill or split into `deslop` + `doc-compose` later?
- How much repo-specific terminology policy should live in the skill vs references?
- Should short-form outputs like DM/email use a narrower sub-workflow?
