---
name: clear-writing
description: >
  Use when creating, restructuring, rewriting, humanizing, or reviewing prose
  documents in English or Korean: README, guides, specs, API references, ADRs,
  memos, wiki pages, blog drafts. Covers de-AI-ifying tone ("humanize",
  "deslop", "AI 티 빼줘"), turning notes into standalone docs ("이 메모를
  문서로"), surgical Korean polishing ("윤문해줘"), terminology review ("용어
  이상한지 봐줘", "term check"), and repository-grounded doc authoring ("README
  작성", "문서 정리해줘", "스펙 작성"). NOT for Python docstrings, prompt
  coaching, diagrams, PR/commit/issue copy, translation, or implementation
  changes.
---

# Clear Writing

One skill for prose-document work: author repository-grounded docs, revise
existing text, and run focused passes (terminology, Korean patterns). Chat
answers do not need this skill; the always-on core rules govern those.

## Intake

Establish before touching text:

1. **Deliverable and audience** — what document, for whom, doing what job.
2. **Language** — Korean work additionally loads
   [korean-tells.md](references/korean-tells.md).
3. **Grounding** — repository-based (claims must match code/config) vs
   standalone text (claims must match the source text).
4. **Authority** — "review/진단/check/피드백" returns findings without edits
   (quote the line, name the pattern, state the fix);
   "다듬어줘/고쳐줘/써줘/적용해줘" authorizes edits within the given scope.
   Multi-file or repo-wide requests: confirm the target list first, then
   process sequentially under the same discipline. Publishing, commits, PRs,
   or posting need a separate explicit request.
5. **Profile** — default, or strict per
   [profiles.md](references/profiles.md). Repo style rules outrank profiles.
6. **Voice sample** — if the user's own writing is available, it outranks
   every style rule ([voice-preservation.md](references/voice-preservation.md)).

## Job selection

| Job | When | Primary reference |
|---|---|---|
| **Authoring** | new or materially updated repo-grounded docs | [authoring.md](references/authoring.md) |
| **Revision** | existing text: humanize, restructure, compose notes into a doc | [revision.md](references/revision.md) |
| **Pass** | single-concern check: terminology, or Korean 윤문 only | [terminology.md](references/terminology.md) / [korean-tells.md](references/korean-tells.md) |

Mixed requests are normal: "README 정리해줘" with stale facts = authoring
grounding + revision prose work. Passes also run as sub-steps inside the other
two jobs; fold their findings into the main report.

## Invariants (every job)

- Preserve facts, numbers, commands, paths, quotations, conditions,
  requirement levels, and visible uncertainty. Style cleanup never resolves a
  factual conflict silently.
- **Removal only.** Never insert stock transitions, invented facts, examples,
  citations, or replacement clichés.
- Voice wins over rules: when a pattern rule fires on the author's deliberate,
  repeated choice, report it instead of applying it.
- No terminology replacement without domain grounds; never alter identifiers,
  schema fields, commands, or quoted text without explicit request.
- Never claim text is AI-authored; report the wording problem itself.
- [core-rules.md](references/core-rules.md) is the generation baseline for
  everything this skill writes, including its own reports.

## Delivery

Every deliverable passes [gates.md](references/gates.md): reader/purpose,
fact preservation, language quality, change-rate guard (30% warn / 50% stop),
editor-slop self-check on your own rewrite, and verification actions. Lead
the response with the deliverable; keep the report to files touched, major
decisions, checks run, and unresolved spans. No grades, no change-rate
percentages as scores.

## Reference files

| File | Load when |
|---|---|
| [core-rules.md](references/core-rules.md) | always-on baseline; D4 install decision pending |
| [authoring.md](references/authoring.md) | authoring job |
| [templates.md](references/templates.md) | a page shape would save time (menu, not mandate) |
| [doc-patterns.md](references/doc-patterns.md) | technical-doc content problems need worked repairs |
| [style-zoom-rules.md](references/style-zoom-rules.md) | choosing a structural repair level |
| [revision.md](references/revision.md) | revision job |
| [anti-slop-core.md](references/anti-slop-core.md) | any humanize/deslop work, all languages |
| [structure-anti-patterns.md](references/structure-anti-patterns.md) | structural verbosity, doc-shape cleanup |
| [voice-preservation.md](references/voice-preservation.md) | any rewrite of someone's text |
| [korean-tells.md](references/korean-tells.md) | Korean documents |
| [terminology.md](references/terminology.md) | terminology pass |
| [known-slop-terms.md](references/known-slop-terms.md) | broad terminology scan |
| [replacement-patterns.md](references/replacement-patterns.md) | drafting term alternatives |
| [verification-procedure.md](references/verification-procedure.md) | a term decision needs external evidence |
| [profiles.md](references/profiles.md) | strict house style requested or implied by repo policy |
| [gates.md](references/gates.md) | before every delivery |

## Gotchas

- Phrase swapping is not humanizing; genericness is the real defect. Add
  concrete, checkable detail or the text stays hollow.
- Compression is not clarity; keep the connective reasoning readers need.
- Do not reformat chat/DM/email into formal documents.
- "Professional" is not the goal; natural, precise, and credible is.
- Do not grade documents by pattern counts or change ratio, in either
  direction.
- Stop and ask instead of guessing when: the target text or scope is missing;
  repository rules conflict; a style fix cannot resolve a factual error or
  ambiguity; you cannot tell duplicated filler from essential context; edits
  would collide with a user's uncommitted changes.
