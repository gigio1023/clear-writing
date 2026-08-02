# Implementation Notes

Use this file for deviations that affect later review.

## 2026-08-02

- Plan: rename the skill while making the multilingual change.
- Reality: the maintainer rejected the first proposed name but has not selected
  a replacement. Renaming the folder and frontmatter would break the installed
  handle, skills.sh path, README badges, and the optional always-on marker.
- Conservative choice: keep `clear-writing` during implementation, research
  distinctive candidates, and present a rename-ready recommendation. Apply the
  hard rename only after the maintainer selects the handle.
- Revisit: before merging PR #4 if the maintainer chooses a name.

### Replacement-name review

Scored on immediate meaning, natural phrasing, distinction, likely search
terms, and durability. Exact GitHub repository-name searches on 2026-08-02
returned zero results for `grounded-and-readable`, `context-complete-writing`,
and `evidence-to-reader`. Exact skills.sh web searches found no skill page for
those handles. Search uniqueness is a checked snapshot, not a permanent
guarantee.

| Candidate | Meaning | Natural | Distinct | Search | Durable | Note |
|---|---:|---:|---:|---:|---:|---|
| `grounded-and-readable` | 2 | 2 | 2 | 2 | 2 | Recommended: names the two outcomes without claiming truth or detecting authorship. |
| `evidence-to-reader` | 2 | 1 | 2 | 2 | 2 | Captures the workflow, but sounds more like a pipeline than an editing skill. |
| `context-complete-writing` | 2 | 1 | 2 | 2 | 2 | Strong on standalone documents, weaker on evidence and voice. |

`sourcebound`, `readerbound`, and `proseproof` were rejected after search:
existing products or sites already use those names. `source-to-reader` is a
natural phrase, but it is less distinctive in technical communication and
publishing search results.

### Final verification

- Plan: finish only after package, reference, source-metadata, and fresh-reader
  checks pass.
- Reality: the validator passed at 8,114 bytes and 145 lines; the Skills CLI
  found one skill; all 19 unique direct references and repository-relative
  Markdown targets exist; `git diff --check` passed. Independent English/common,
  Italian, and Chinese reviewers rechecked every material finding after repair.
- Conservative choice: report the change as statically validated. Do not claim
  measured writing-quality improvement because no cross-harness model run or
  representative-reader benchmark was executed.
- Revisit: add behavior fixtures only in a separately scoped evaluation change,
  so packaging and guidance changes remain reviewable here.

### Model-native anti-slop correction

- Plan: make multilingual coverage robust by adding bounded language guidance.
- Reality: requiring a matching language layer for every span still pushed the
  package toward a grammar encyclopedia. Current frontier models already carry
  broad grammar, spelling, syntax, and idiom knowledge. More tables would add
  exceptions, conflicts, and context cost without defining AI slop better.
- Conservative choice: define slop by four reader-visible failures, make the
  common semantic tests the normal path, and load language files only for a
  language-specific candidate or locale risk. Keep an unambiguous local
  correction floor inside authorized rewrites, while excluding grammar-only
  proofreading from the trigger.
- Revisit: expand a language overlay only after a recurring deslop failure is
  observed and the new rule adds evidence or a meaning-preservation boundary
  beyond ordinary model fluency.

- Verification: `validate_skill.sh clear-writing` passed at 7,786 bytes and
  147 lines; the Skills CLI found one installable skill; all 19 direct
  references and repository-relative Markdown links resolve; `git diff
  --check` passed. No cross-harness behavior run or representative-reader
  study was performed.
