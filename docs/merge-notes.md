# Merge Notes

This draft merges two prior skill ideas with different strengths.

## From `humanize`

Pulled forward:

- abstraction-level diagnosis
- sentence-level anti-slop detection
- false agency and placeholder cleanup
- medium-aware caution for short-form writing

Not copied as-is:

- language-specific kill lists
- repo-specific correction examples

Those can be added later if this skill proves useful outside one repo.

## From `human-readable-doc-composer`

Pulled forward:

- standalone readability as a first-class requirement
- result-first delivery
- explicit handling of facts, assumptions, and open questions
- terminology consistency and reader-context discipline

Not copied as-is:

- repo-local terminology files
- mode names tied to the original repository workflow

## Why one merged skill

In practice, "make this less AI-sounding" and "make this document usable" are often the same request.

If they stay separate, the usual failure modes are:

- one pass fixes tone but leaves weak structure
- another pass fixes structure but keeps synthetic phrasing
- the user has to know which skill to invoke first

The merged draft assumes a single workflow with three modes:

- correction
- compose
- hybrid

## Open questions

- Should the skill eventually split out language-specific reference packs?
- Should short-form writing become a separate companion skill?
- Should there be a deterministic lint script for banned phrases, or is LLM-native review enough?
