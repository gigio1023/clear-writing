# humanize-doc

[English](README.md) | [한국어](README.ko.md)

Draft skill repo for a writing skill that combines two jobs that are usually split apart:

- remove AI-sounding prose and abstraction-heavy phrasing
- produce documents that are readable on their own, with enough context and clear structure

The current draft merges two source lines:

- external anti-slop reference work from `stop-slop`
- existing internal document-composition ideas from `human-readable-doc-composer`

`humanize` is treated here as the user's own adjacent skill, not as an external source to borrow from blindly. It is a nearby internal precedent, not the reference baseline for this draft.

## Install

This repo is currently private.

- `npx skills add` works if you have GitHub access to `gigio1023/humanize-doc`
- it will not show up in public `skills.sh` search or leaderboard while it stays private

### npx skills

Direct install by repo:

```bash
npx skills add gigio1023/humanize-doc --skill humanize-doc
```

Useful variants:

```bash
npx skills add gigio1023/humanize-doc --skill humanize-doc --agent codex
npx skills add gigio1023/humanize-doc --skill humanize-doc --agent claude-code
npx skills add gigio1023/humanize-doc --skill humanize-doc -g
```

Notes:

- default install is project-local
- use `-g` for a global install
- because the repo is private, direct `add` is the reliable path; public `find`/`skills.sh` discovery is not

### Manual install

<details>
<summary>Claude Code</summary>

Copy the skill folder into `~/.claude/skills/humanize-doc`:

```bash
mkdir -p ~/.claude/skills && \
git clone https://github.com/gigio1023/humanize-doc.git /tmp/humanize-doc && \
cp -r /tmp/humanize-doc/humanize-doc ~/.claude/skills/ && \
rm -rf /tmp/humanize-doc
```
</details>

<details>
<summary>Codex CLI</summary>

Copy the skill folder into `~/.codex/skills/humanize-doc`:

```bash
mkdir -p ~/.codex/skills && \
git clone https://github.com/gigio1023/humanize-doc.git /tmp/humanize-doc && \
cp -r /tmp/humanize-doc/humanize-doc ~/.codex/skills/ && \
rm -rf /tmp/humanize-doc
```
</details>

<details>
<summary>Other agents</summary>

For agents that follow the shared `.agents/skills` convention, copy the skill into `~/.agents/skills/humanize-doc`:

```bash
mkdir -p ~/.agents/skills && \
git clone https://github.com/gigio1023/humanize-doc.git /tmp/humanize-doc && \
cp -r /tmp/humanize-doc/humanize-doc ~/.agents/skills/ && \
rm -rf /tmp/humanize-doc
```
</details>

Manual rule of thumb:

- copy `humanize-doc/`
- keep the folder name as `humanize-doc`
- put it under your agent's skills directory

## Goal

Build one skill that can handle both:

1. "make this sound less AI-generated"
2. "rewrite this into a document people can actually read and use"

The working assumption is that these are usually the same problem from two angles:

- sentence-level problem: vague labels, placeholders, false agency, metronomic rhythm
- document-level problem: weak flow, missing context, unstable terminology, over-compressed reasoning

## Repo layout

```text
humanize-doc/
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

- Should this remain one skill or split into `humanize` + `doc-compose` later?
- How much repo-specific terminology policy should live in the skill vs references?
- Should short-form outputs like DM/email use a narrower sub-workflow?
