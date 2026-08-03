# Contextual Terminology Catalog

This catalog narrows questions; it does not map banned words to approved
synonyms. A term is defective only when its normal relation, mechanism, or
audience does not match the sentence. Read the governing spec, project glossary,
and surrounding document before changing it.

## Mechanism questions for technical terms

| Term | Keep when | Question that exposes ornamental use |
|---|---|---|
| `contract` | parties, producers and consumers, or APIs carry testable obligations or compatibility expectations | Who is bound, what must remain compatible, and how is breach detected? |
| `gate` | stated pass criteria block a merge, release, promotion, or stage | What fails, and what progression stops? |
| `boundary` | responsibility, trust, policy, or ownership changes across it | What differs on each side? |
| `surface` | a defined set of observable, callable, configurable, or attackable elements | Who interacts with it, which elements belong, and what changes when it grows? |
| `slice` | a named axis is selected, or a vertical slice crosses layers end to end | What is cut, along which axis, and why is `section`, `subset`, or `sample` insufficient? |
| `claim` | a person or source asserts something contestable, or a governing spec defines the field | What evidence could support or refute it? Is the span instead a finding, requirement, observation, or report? |
| `artifact` | a tool or process produces a stored, transferred, or tracked output | What produces it and how is it consumed? |
| `canonical` | the domain defines canonical form, canonicalization, or a single reference representation | Is this actually official, standard, primary, or merely preferred? |
| `semantic` | the established field matters, as in semantic HTML, semantic versioning, or NLP | What meaning-level distinction does the word add here? |
| `ecosystem` | interacting packages, maintainers, conventions, and users form more than a tool list | What interactions make `tools`, `packages`, or `community` too narrow? |
| `paradigm` | a recognized conceptual or programming model is meant | Would `approach`, `method`, or `model` preserve the meaning? |
| `first-class` | the domain has a defined first-class entity or capability | Which concrete support makes it more than important or well supported? |
| `production-ready` | release criteria, supported environments, tests, and operational limits are named | Ready for which workload and according to which checks? |

The answer can come from surrounding context; do not force every sentence to
repeat a definition. If the question has no answer, choose the plain term that
names the actual relation or rewrite the sentence.

## Cross-language checks

**Self-important naming.** Labels such as "framework", "methodology",
"architecture", `体系`, `框架`, `metodologia`, or `체계` can be exact. When the
text names only a short checklist or one procedure, state what exists instead
of increasing its rank.

**Nominalized process.** A noun may help later reference or carry a legal,
technical, or academic concept. When it only hides an actor and action, restore
the language's natural finite verb. Apply the target language's own rules;
English suffix patterns do not diagnose Korean, Italian, or Chinese prose.

**Borrowing and code-switching.** Keep identifiers, standard API and protocol
names, and borrowed terms the intended community actually searches for. Expand
or gloss them when readers need help. Replace ornamental English or a prestige
borrowing only when the target-language term is equally precise.

**Abbreviation.** Expand at first use when the audience may not know it. Do not
expand universally known domain forms on every page, and never change an
identifier merely to match prose.

**False precision.** A coined category can imply a stable boundary the source
does not establish. Define inclusion and exclusion, cite a governing source, or
use an ordinary descriptive phrase.

## Candidate generation

Generate alternatives from the actual referent:

1. What actor, object, action, relation, or constraint does the term name?
2. What does the governing source call it?
3. What word does the intended community use in comparable real systems?
4. Which alternative preserves searchability, scope, and requirement level?
5. Would rewriting the whole clause be clearer than swapping one word?

Do not create specificity that the evidence boundary does not supply. For
example, replace an unsupported "stakeholders" with a known group only when the
source names that group; otherwise keep the uncertainty or request the name.

## Common false-positive families

Keep these when they are exact:

- legal, scientific, medical, and standards terminology
- protocol fields, code symbols, CLI commands, schema properties, and product
  names
- established software phrases such as trust boundary, data contract, build
  artifact, semantic versioning, vertical slice, and attack surface
- deliberate workplace shorthand defined for the document's audience
- terms required for search, interoperability, compliance, or consistency with
  another authoritative page

Words associated with generated prose, including `robust`, `seamless`,
`holistic`, and their translations, are review prompts only. Remove them when
they carry no scope or consequence. Keep them when the domain defines the term
or the sentence proves the property.

## Decision record

For consequential changes, record:

- original term and location
- keep, replace, rewrite, or uncertain
- governing source or context test
- chosen wording and the distinction it preserves
- variants searched and identifiers deliberately left unchanged
