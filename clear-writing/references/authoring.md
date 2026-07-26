# Authoring Workflow

For creating or materially updating repository-grounded documentation: README,
CONTRIBUTING, setup and how-to guides, API references, architecture docs,
ADRs, specifications. Improving prose that already exists without new facts
belongs to `revision.md`; the two combine when a rewrite also
needs fresh repository evidence.

## Ground rules

- Ground every technical claim in the repository: code, configuration,
  scripts, tests, schemas, accepted specs. Never present an unrun command or
  invented example as verified; placeholders are realistic but visibly fake.
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
| Contribute changes | supported setup, checks, conventions, submission flow |

Do not omit a necessary fact merely to shorten the page. When decisive
evidence is missing or contradictory, name the gap and its consequence instead
of guessing. When code and a normative spec disagree, surface the conflict —
code shows current behavior; the spec may intentionally describe the target.

`templates.md` offers page shapes as a menu, never a mandatory
skeleton. `doc-patterns.md` collects worked repairs for
common technical-documentation problems.

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
copyable input; diagrams only when relationships beat short prose. Match the
target renderer before using callouts, tabs, or MDX components. Search inbound
references before renaming headings or anchors.

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
`gates.md` — for authoring, Gate 2 (facts vs repository evidence)
and Gate 6 (links, anchors, commands, renderer syntax, docs checks) carry the
most weight.
