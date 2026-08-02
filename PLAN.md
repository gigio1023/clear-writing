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
- **R5:** Keep the package discoverable in Codex and Claude Code and propose a
  distinctive replacement name without breaking the current package before
  the maintainer chooses it.

## Tasks

| ID | Files | Action | Acceptance | Verification |
| --- | --- | --- | --- | --- |
| T1 | `clear-writing/`, `docs/`, `README*` | Audit the current router, every direct reference, source register, and packaging contract. | Every retained rule has a clear common or language-specific home; conflicts and duplication are recorded. | Direct read-through and inventory. |
| T2 | research only | Review current English/common, Italian, and Chinese primary or authoritative sources in independent lanes. | Each proposed language rule includes scope, keep test, and evidence limit; detector claims remain diagnostic only. | Source URLs, versions, and caveats inspected by the lead. |
| T3 | `clear-writing/SKILL.md`, language references | Add language routing and common/English/Korean/Italian/Chinese layers. | English evidence is retained as English guidance; Korean stays grounded in Korean sources; Italian and Chinese do not inherit English surface rules by translation. | All direct links exist and the normal path remains under the skill size target. |
| T4 | terminology and anti-slop references | Remove duplicate catalogs and make cluster-based, meaning-preserving cleanup canonical. | No conflicting replacement tables; unsupported specificity is never inserted. | Diff review and package validation. |
| T5 | `docs/sources-and-inspiration.md`, `README*` | Record new sources, adoption limits, multilingual coverage, and naming candidates. | README matches the actual tree and states the supported language boundaries. | Link/path checks and complete README/SKILL reread. |
| T6 | whole repo | Run packaging, portability, Markdown, and fresh-context integration checks. | One installable skill is found; validation passes; no material unresolved review finding remains. | `validate_skill.sh`, `npx skills add . --list --full-depth`, `git diff --check`, targeted link checks. |

## Status

- T1: completed
- T2: completed
- T3: completed
- T4: completed
- T5: completed
- T6: completed

## Verification record

- `validate_skill.sh clear-writing`: passed at 8,114 bytes and 145 lines.
- `npx --yes skills add . --list --full-depth`: found exactly one installable
  skill, `clear-writing`.
- `git diff --check`: passed.
- Local Markdown target check: all repository-relative links resolve.
- Router reference check: all 19 unique direct reference files exist.
- Fresh-context reviews: English/common, Italian, and Chinese reviewers found
  no material issue after targeted repairs and rechecks.
- Not verified: no harness-specific model-behavior benchmark or representative
  human-reader study was run. The existing eval prompts remain prompts, not
  measured results.
