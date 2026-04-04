---
name: deslop-doc-writer
description: >
  Rewrite drafts, notes, and documents so they read like competent human writing rather than
  AI output. Use when the user asks to humanize prose, deslop text, rewrite for readability,
  organize messy notes into a standalone document, or make documentation clearer without losing
  facts. Triggers include "humanize", "deslop", "AI스럽게 쓰지 말고", "이 문서 읽기 좋게 고쳐줘",
  "rewrite this doc", "organize these notes", and "make this readable". Not for translation,
  fact-checking, or grammar-only edits.
---

# Deslop Doc Writer

## Quick Start

Pick one mode first:

- `correction`: the structure mostly works, but the prose sounds synthetic, vague, or inflated
- `compose`: the source is fragmented, context-light, or hard to follow as a standalone doc
- `hybrid`: both are true; this should be the default for most substantial documents

The core rule is simple:

- fix the sentence-level slop
- fix the document-level readability
- preserve facts, uncertainty, and intended tone

## Core Diagnosis

Most bad AI writing has two failures at once:

1. **Abstraction too high**
   - labels stand in for what actually happened
   - placeholders stand in for real actors, scope, or quantities
2. **Reader context too thin**
   - the draft assumes chat history or internal shorthand
   - reasoning, evidence, or terminology is missing where the reader needs it

If you only swap phrases, the document still feels fake.
If you only reorganize sections, the sentences still feel fake.
This skill fixes both layers together.

## Workflow

1. Read the target text and identify the deliverable type.
2. Choose the mode using `references/document-modes.md`.
3. Load `references/anti-slop-patterns.md`.
4. Load `references/output-contract.md`.
5. Load `references/readability-gates.md`.
6. Diagnose the draft on two axes:
   - sentence quality: labels, placeholders, false agency, cadence, filler
   - document quality: purpose, flow, evidence, terminology, standalone readability
7. Rewrite at the lowest abstraction level that still fits the medium.
8. Preserve verified facts and clearly keep assumptions or open questions visible.
9. Run the readability gates before delivering.

## Rewrite Priorities

Apply these in order:

1. Solve the main reader problem first.
2. Replace labels with mechanism or observable detail.
3. Name the actor instead of letting objects or abstractions "do" things.
4. Remove invented terminology and consultant-style framing unless it is truly established domain language.
5. Rebuild structure so the document is understandable without prior chat context.
6. Keep terminology stable once chosen.
7. Cut filler, but do not cut reasoning that the reader needs.

## Mode Guide

### Correction mode

Use when:

- the document already has the right sections
- the main issue is voice, cadence, vagueness, or AI smell

Deliver:

- either direct edits or categorized before/after corrections
- light structural edits only when they unblock readability

### Compose mode

Use when:

- the source is notes, bullets, fragments, or a weak first draft
- the reader would not understand the document without extra context

Deliver:

- a standalone document
- result-first flow
- enough context, evidence, and scope markers to make the document durable

### Hybrid mode

Use when:

- the draft is both unreadable and AI-sounding
- the user wants one pass that improves quality, flow, and human tone together

Deliver:

- a full rewrite
- structure and sentence changes together
- explicit preservation of facts and uncertainty

## Medium Calibration

Use strong intervention for:

- resumes
- portfolios
- strategy docs
- public-facing documentation

Use medium intervention for:

- research notes
- internal memos
- project updates

Use light intervention for:

- email
- chat messages
- short status updates

Short-form writing should not be reformatted into a mini-report.

## Non-Negotiables

- Never change the factual meaning without instruction.
- Never invent citations, evidence, or consensus.
- Never replace specific technical terms just because they "sound AI".
- Never keep vague abstraction if the source provides a more concrete form.
- Never assume the reader saw the prior conversation.

## Gotchas

- Phrase swapping is not enough. Lower the abstraction level.
- Compression is not the same as clarity. Keep the missing connective tissue when the reader needs it.
- "Professional" is not the goal. Natural, precise, and credible is the goal.
- Do not turn DM/email outputs into formal documents.
- Do not erase uncertainty to make the writing sound decisive.
- Do not preserve repeated scaffolding phrases just because they are grammatically fine.

## Reference Files

| File | When to load | Purpose |
| --- | --- | --- |
| `references/document-modes.md` | First | Choose correction, compose, or hybrid |
| `references/anti-slop-patterns.md` | Every rewrite | Detect sentence-level AI patterns |
| `references/output-contract.md` | Medium/long docs | Keep standalone readability and evidence shape |
| `references/readability-gates.md` | Before delivery | Final quality gate |

## Safety

- Preserve facts, dates, scope, and uncertainty.
- Keep factual claims separate from inference or recommendation when the distinction matters.
- If the source is too thin to support a standalone document, say what is missing instead of inventing connective tissue as fake certainty.

## Eval

The rewrite is not done until all of these are true:

1. The main user task is easier to understand after the rewrite.
2. Label-heavy and placeholder-heavy phrasing has been reduced or removed.
3. The document can be read without hidden chat context.
4. The terminology is consistent enough not to distract the reader.
5. Facts are preserved, and uncertainty remains visible where needed.
