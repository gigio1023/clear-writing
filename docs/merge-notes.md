# Merge Notes

This draft merges an external anti-slop reference line with an internal document-composition line.

## From `stop-slop`

Pulled forward:

- anti-slop framing as a first-class task
- sentence-level pattern detection
- false agency cleanup
- rhythm and filler checks
- scoring/gating mindset before delivery

Not copied as-is:

- hard bans that are too rigid for every medium
- phrase-level prohibitions that would overfit this draft to one author's taste

## From `human-readable-doc-composer`

Repository history note:

- local `brain` repo history shows the skill was added and evolved under `gigio1023 <relilau00@gmail.com>`
- first addition in current history appears at commit `06082bd` on 2026-03-02
- later archived at commit `049a34a` on 2026-03-19

Pulled forward:

- standalone readability as a first-class requirement
- result-first delivery
- explicit handling of facts, assumptions, and open questions
- terminology consistency and reader-context discipline

Not copied as-is:

- repo-local terminology files
- mode names tied to the original repository workflow

## About `humanize`

`humanize` is not treated as the external source reference for this draft.

Reason:

- it is the user's own internal skill
- it already reflects local iteration and preferences
- this draft should distinguish between external grounding and internal prior art

Practical use:

- `humanize` remains a useful comparison point when checking overlap
- its local examples can still inform later tuning if the user wants convergence
- but provenance notes for this repo should point to `stop-slop` for the anti-slop lineage

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
