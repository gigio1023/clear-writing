# Multilingual Writing Skill Plan

## Goals

- **R1:** Keep one portable writing skill while separating language-neutral
  judgment from language-specific prose guidance.
- **R2:** Preserve verified English and Korean material, and add bounded
  Italian and Chinese support from primary or authoritative sources.
- **R3:** Make evidence, cold-reader completeness, claim force, and author
  voice outrank surface anti-slop cleanup.
- **R4:** Reduce duplicate or stale instructions without weakening existing
  authoring, revision, terminology, or Korean workflows.
- **R5:** Keep the package discoverable in Codex and Claude Code under the
  maintainer-selected `slop-aware-writing` handle.
- **R6:** Make AI-slop diagnosis the primary contract, rely on frontier-model
  fluency for ordinary language knowledge, and prevent language overlays from
  becoming grammar encyclopedias.

## Tasks

| ID | Files | Action | Acceptance | Verification |
| --- | --- | --- | --- | --- |
| T1 | `slop-aware-writing/`, `docs/`, `README*` | Audit the current router, every direct reference, source register, and packaging contract. | Every retained rule has a clear common or language-specific home; conflicts and duplication are recorded. | Direct read-through and inventory. |
| T2 | research only | Review current English/common, Italian, and Chinese primary or authoritative sources in independent lanes. | Each proposed language rule includes scope, keep test, and evidence limit; detector claims remain diagnostic only. | Source URLs, versions, and caveats inspected by the lead. |
| T3 | `slop-aware-writing/SKILL.md`, language references | Add language routing and common/English/Korean/Italian/Chinese layers. | English evidence is retained as English guidance; Korean stays grounded in Korean sources; Italian and Chinese do not inherit English surface rules by translation. | All direct links exist and the normal path remains under the skill size target. |
| T4 | terminology and anti-slop references | Remove duplicate catalogs and make cluster-based, meaning-preserving cleanup canonical. | No conflicting replacement tables; unsupported specificity is never inserted. | Diff review and package validation. |
| T5 | `docs/sources-and-inspiration.md`, `README*` | Record new sources, adoption limits, multilingual coverage, and naming candidates. | README matches the actual tree and states the supported language boundaries. | Link/path checks and complete README/SKILL reread. |
| T6 | whole repo | Run packaging, portability, Markdown, and fresh-context integration checks. | One installable skill is found; validation passes; no material unresolved review finding remains. | `validate_skill.sh`, `npx skills add . --list --full-depth`, `git diff --check`, targeted link checks. |
| T7 | router and common core | Define AI slop by reader-visible function and add semantic diagnosis tests. | The skill distinguishes slop from grammar errors and authorship detection. | Direct contract read-through. |
| T8 | language references | Convert English, Korean, Italian, and Chinese files from mandatory language passes to optional diagnostic overlays. | Ordinary fluency stays model-native; overlays load only for a language-specific candidate or locale risk. | Router-to-reference alignment check. |
| T9 | revision, gates, README, lineage | Add the correction floor, document the new purpose, and record current model-guidance rationale. | Obvious local errors remain fixable without expanding the trigger to grammar-only proofreading. | README/SKILL/gates reread and source-register check. |
| T10 | whole repo and PR #4 | Re-run package checks and publish the focused follow-up. | Validation passes, one skill is found, and the existing Draft PR describes the model-native anti-slop contract. | Validator, package listing, link check, diff check, PR inspection. |
| T11 | package, README, current docs, and PR #4 | Rename the installable skill to `slop-aware-writing` while preserving the repository slug and the deployed Korean-core marker. | Folder and frontmatter match; install and update commands use the new handle; historical records remain identifiable; the Draft PR explains the rename. | Validator, package listing, current-path search, link check, diff check, PR inspection. |

## Status

- T1: completed
- T2: completed
- T3: completed
- T4: completed
- T5: completed
- T6: completed
- T7: completed
- T8: completed
- T9: completed
- T10: completed
- T11: completed

## Verification record

- Rename verification (2026-08-03):
  `validate_skill.sh slop-aware-writing` passed at 7,897 bytes and 148 lines;
  both Skills CLI listing commands found exactly one installable skill named
  `slop-aware-writing`; all 19 direct references exist; repository-relative
  Markdown links resolve; the portable body contains no harness-specific paths
  or invocation syntax; `git diff --cached --check` passed.
- `validate_skill.sh clear-writing`: passed at 7,786 bytes and 147 lines after
  the model-native anti-slop revision.
- `npx --yes skills add . --list --full-depth`: found exactly one installable
  skill, `clear-writing`.
- `git diff --check`: passed.
- Local Markdown target check: all repository-relative links resolve.
- Router reference check: all 19 unique direct reference files exist.
- Fresh-context reviews: English/common, Italian, and Chinese reviewers found
  no material issue after targeted repairs and rechecks.
- Model-native follow-up: router and reference read-through confirmed that
  language overlays are conditional, grammar-only proofreading is excluded,
  and every supported language retains a correction floor and meaning gate.
- Not verified: no harness-specific model-behavior benchmark or representative
  human-reader study was run. The existing eval prompts remain prompts, not
  measured results.
