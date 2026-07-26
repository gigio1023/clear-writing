# Revision Workflow

For improving existing text: humanizing, restructuring, or turning fragments
into a standalone document. Creation of repository-grounded docs from scratch
belongs to `authoring.md`.

## Core diagnosis

Most bad AI-flavored writing fails on two axes at once:

1. **Abstraction too high** — labels stand in for what happened; placeholders
   stand in for real actors, scope, quantities.
2. **Reader context too thin** — the draft assumes chat history or internal
   shorthand; reasoning, evidence, or terminology is missing where the reader
   needs it.

Fixing only phrasing leaves a hollow structure; fixing only structure leaves
synthetic sentences. Diagnose both axes before editing, then intervene at the
smallest scope that solves the reader's problem:

- **Sentence-level pass** — structure already works; the prose sounds
  synthetic, vague, or inflated. Default for a plain "humanize/다듬어줘"
  request.
- **Compose** — the source is notes, bullets, fragments, or a context-light
  draft; the reader could not use it standalone. Build the document.
- **Full revision** — both problems, common in long drafts. Structure first,
  then sentences.

## Rewrite priorities (in order)

1. Solve the main reader problem first.
2. Replace labels with mechanism or observable detail
   (`anti-slop-core.md`).
3. Name actors; kill false agency.
4. Remove invented terminology and consultant framing unless it is
   established domain language (route real terminology doubts to
   `terminology.md`).
5. Rebuild structure so the document stands without the conversation that
   produced it (`structure-anti-patterns.md`).
6. Keep terminology stable once chosen.
7. Cut filler — but never the reasoning the reader needs to trust the
   conclusion. Compression is not clarity.

## Standalone-document shape (compose work)

Default order unless the medium demands otherwise: result or thesis → short
context recap → evidence and reasoning → implications, open questions, next
steps. Keep verified facts visually distinct from assumptions and
recommendations where the difference matters. If the source is too thin to
support a standalone document, say what is missing instead of inventing
connective tissue.

## Medium calibration

Match intervention strength to the medium; do not reformat short-form writing
into a mini-report.

| Strength | Media | Notes |
|---|---|---|
| Strong | resumes, portfolios, strategy docs, public docs | full gates, structural rebuild allowed |
| Medium | research notes, internal memos, project updates | keep the author's structure where it works |
| Light | email, chat, short status updates | no memo-ification, no ceremonial open/close, bullets acceptable |

## Editing discipline

- Before editing, note the invariants: facts, conditions, exceptions,
  prohibitions, commands, numbers, quotations, register, repo-specific terms.
  Ambiguous source meaning stays ambiguous — style cleanup must not resolve it.
- Edit surgically. Delete information-free sentences first; when prose, table,
  and list repeat one fact, keep the clearest single form.
- Removal only — never insert clichés, facts, examples, or citations
  (`voice-preservation.md` bounds every edit).
- Korean text: apply `korean-tells.md`; all languages:
  respect the active profile (`profiles.md`).
- Deliver through `gates.md` — including the change-rate guard and
  the editor-slop self-check.

## Output

Return the rewritten text first, in the source's format unless a new shape was
requested. No diagnosis preamble, no edit-by-edit narration. Add a short note
after the text only when a factual ambiguity, missing source, or unresolved
choice materially affects trust.
