# Authoring Workflow

For creating or materially updating evidence-grounded documentation: README,
CONTRIBUTING, setup and how-to guides, API references, architecture docs,
ADRs, specifications, reports, and decision memos. Improving prose that
already exists without new facts belongs to `revision.md`; the two combine
when a rewrite also needs fresh repository or external evidence.

## Contents

- Ground rules
- Document jobs
- Document spine
- Five zoom levels
- Form selection
- Coverage and currentness
- Scope
- Delivery

## Ground rules

- Select the evidence boundary from `SKILL.md`. Ground technical claims in
  inspected code, configuration, scripts, tests, schemas, or accepted specs.
  Claims that depend on external or mixed sources follow
  `source-grounding.md`.
- Never present an unrun command or invented example as verified; placeholders
  are realistic but visibly fake.
- Read repository instructions and neighboring pages first; they set language,
  terminology, renderer, and navigation conventions that outrank this skill's
  preferences.
- State (to yourself) the intended audience and the page's one primary reader
  job before drafting. A documentation request never authorizes
  implementation changes.

## Document jobs

| Reader job | Include when applicable |
|---|---|
| Start or onboard | prerequisites, supported setup path, commands, success signal |
| Perform a task | preconditions, ordered actions, observable verification, evidenced recovery |
| Look up an API or option | names, types, required/default behavior, constraints, examples, errors |
| Understand architecture | context, current design, boundaries/data flow, rationale, trade-offs |
| Record a decision | status, context, decision, alternatives, consequences |
| Decide or approve | head message, request or recommendation, reasons and evidence, risks, owner and timing |
| Report status | objective, current state, material variance, evidence, next action, owner and timing |
| Contribute changes | supported setup, checks, conventions, submission flow |

Do not omit a necessary fact merely to shorten the page. When decisive
evidence is missing or contradictory, find a governing source, state the
bounded gap and its consequence, or omit the unsupported claim. When code and
a normative spec disagree, surface the conflict: code shows current behavior;
the spec may intentionally describe the target.

`templates.md` offers page shapes as a menu, never a mandatory
skeleton. `doc-patterns.md` collects worked repairs for
common technical-documentation problems.

## Document spine

Match the opening to the reader job:

- Decision and analysis documents lead with the decision, request,
  recommendation, or finding the reader must evaluate.
- Procedures lead with the task, prerequisites, and first useful action.
- Reference pages lead with the lookup scope and current behavior.
- Architecture and decision records may need context before the conclusion
  when chronology or rationale is the reader's job.

For argument-bearing documents, make an internal map:

```text
claim -> reason or evidence -> warrant (why the support fits) -> limit
```

Every material claim must have direct support or an explicit status such as
inference, assumption, or unverified. Every source, statistic, chart, and
example must serve a claim, necessary context, or reader action. Remove
material that is merely interesting. Do not force a thesis onto API reference,
lookup, or procedural pages; verify their statements against current behavior
instead.

## Five zoom levels

Apply the smallest level that fixes the reader's problem
(details and worked examples: `style-zoom-rules.md`):

| Level | Desired result |
|---|---|
| Sentence | one visible main assertion, qualifiers intact |
| Bullet | parallel, scannable items; nesting = real hierarchy |
| Section | heading and opening establish the section's job |
| Page | one primary reader job |
| Cross-page | volatile facts have one maintained owner |

These are decision rules, not lint: long prose can be precise, and a short
rewrite that drops a condition is wrong.

## Form selection

Prose for reasoning; numbered steps for order-dependent work; bullets for
independent items; tables for repeated fields or comparisons; code blocks for
copyable input; charts for consequential trends; diagrams only when
relationships beat short prose. Text states the takeaway and material caveats
that a visual alone would hide. Match the target renderer before using
callouts, tabs, or MDX components. Search inbound references before renaming
headings or anchors.

## Coverage and currentness

For a large documentation audit or a major feature page, check both
directions:

1. **Docs to implementation:** commands, paths, versions, configuration, and
   described behavior match the repository.
2. **Implementation to docs:** recent high-signal changes and user-visible
   behavior do not expose a material documentation gap.

Keep this proportional. A sentence edit does not authorize a repository-wide
audit. External and time-sensitive claims use the freshness and stop rules in
`source-grounding.md`.

## Scope

- Edit only requested pages plus closely coupled navigation/anchors.
- No new site-wide conventions, file splits, or neighbor rewrites without that
  scope in the request.
- Preserve unrelated user edits and the project's intentional vocabulary;
  don't mix broad wording cleanup into documenting one feature.
- Add troubleshooting only for failures supported by code, tests, issues, or
  user-provided evidence.

## Delivery

Draft only the sections that serve the reader job, then deliver through
`gates.md`. For authoring, Gate 1 (cold-reader completeness and relevance),
Gate 2 (source and claim integrity), and Gate 6 (links, anchors, commands,
renderer syntax, docs checks) carry the most weight.
