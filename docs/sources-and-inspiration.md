# Sources and Inspiration

This register records what informed `clear-writing`, what the repository
actually adopted, and what it rejected. It is a provenance record, not a claim
that every source is equally authoritative. Research findings, official
guidance, open-source skills, and a maintainer-supplied social post carry
different evidentiary weight.

Unless an entry says otherwise, `Inspected` means 2026-07-31. `Adopted` means
the maintainers restated an idea independently and fitted it to this skill's
scope. It does not mean that source prose, examples, tables, or code were
copied. `Rejected` records tempting ideas that should not return without new
evidence.

## epoko77-ai/im-not-ai

- **Title and URL:** [`im-not-ai`](https://github.com/epoko77-ai/im-not-ai)
- **Responsible:** epoko77-ai; current head authored by Liam Lee.
- **Version:** release `v2.3.0`; `main` also inspected for later changes.
- **Commit:** release `82137e858763dadb99561f194c5c00465735017b`;
  inspected `main` at `53e24e8f92cf344efcb812103f7c2b203e7efffc`
  (2026-07-22). The post-release changes affected social assets and a build
  script, not the writing taxonomy used here.
- **Inspected:** 2026-07-31; local clone, tag history, rules, evidence notes,
  and license.
- **License/status:** MIT, copyright 2026 epoko77-ai. Active upstream.
- **Adopted:** stable Korean pattern IDs, evidence labels, surgical edits,
  diff-based reporting, and periodic upstream delta checks.
- **Rejected:** vendoring the source, treating its small self-study as a
  universal detector, making company house style universal, and reviving rules
  that its own evidence downgraded.

## KatFishNet

- **Title and URL:** [*KatFishNet: Detecting LLM-Generated Korean Text through
  Linguistic Feature Analysis*](https://aclanthology.org/2025.acl-long.1030/)
  and its [research repository](https://github.com/Shinwoo-Park/katfishnet).
- **Responsible:** Shinwoo Park, Shubin Kim, Do-Kyung Kim, and Yo-Sub Han;
  published by the Association for Computational Linguistics.
- **Version:** ACL 2025 long paper, DOI
  [`10.18653/v1/2025.acl-long.1030`](https://doi.org/10.18653/v1/2025.acl-long.1030).
- **Commit:** repository inspected at
  `5e3dc89cc31a029be38fb2d871476b0aff7b793c` (2026-04-07).
- **Inspected:** 2026-07-31; paper record, repository README, experiment layout, and
  repository root.
- **License/status:** the repository contains no `LICENSE` file. The paper is
  used as cited research. No paper prose, data, or code is redistributed.
- **Adopted:** bounded evidence that Korean spacing, part-of-speech, and
  punctuation features can differ by source and genre. This supports cautious
  comma and rhythm checks.
- **Rejected:** using a feature as proof of authorship, presenting a complete
  feature-set AUC as the score of one comma rule, deliberate error insertion,
  and generalizing across genres or future models without retesting.

## petergyang/no-ai-slop

- **Title and URL:** [`no-ai-slop`](https://github.com/petergyang/no-ai-slop)
- **Responsible:** Peter Yang.
- **Version:** `v1.0.4`.
- **Commit:** `e81170dcaefa76b4cb2672532e13042f4e132b32`
  (2026-07-26).
- **Inspected:** 2026-07-31; tagged repository, skill instructions, pattern descriptions,
  and license.
- **License/status:** MIT, copyright 2026 Peter Yang. Active at inspection.
- **Adopted:** a one-time, independently worded port of useful rhetorical
  patterns and the requirement that review findings quote the triggering text.
- **Rejected:** flat word bans, a universal dash cap, and portable house rules
  presented as model-independent detection signals.

## blader/humanizer

- **Title and URL:** [`humanizer`](https://github.com/blader/humanizer)
- **Responsible:** Siqi Chen and repository contributors.
- **Version:** released behavior at `v2.9.1`.
- **Commit:** `523374dee72d67c7b2b5f858ea0094ffda49c3ac`
  (2026-07-21).
- **Inspected:** 2026-07-31; tagged skill, license, and open issue proposals
  [#198](https://github.com/blader/humanizer/issues/198) and
  [#199](https://github.com/blader/humanizer/issues/199).
- **License/status:** MIT, copyright 2025 Siqi Chen. Issue #198, "Add a
  pattern for invisible-context defenses," and issue #199, "Catch abrupt idea
  shifts without adding signposting," were open proposals on 2026-07-31. They
  are not released `v2.9.1` behavior.
- **Adopted:** the general need to remove editor-introduced slop while
  preserving the writer's voice.
- **Rejected:** claiming open issues #198 and #199 as implemented upstream,
  phrase bans as authorship tests, and detector-style certainty from surface
  markers.

## hardikpandya/stop-slop

- **Title and URL:** [`stop-slop`](https://github.com/hardikpandya/stop-slop)
- **Responsible:** Hardik Pandya.
- **Version:** no release tag used; repository head inspected.
- **Commit:** `8da1f030185bdfe8471220585162991eaeb970e9`
  (2026-03-18).
- **Inspected:** 2026-07-31; repository skill, pattern set, history, and license.
- **License/status:** MIT, copyright 2025 Hardik Pandya. The inspected head had
  not changed for about four months.
- **Adopted:** anti-slop review as a first-class pass, plus independently
  worded checks for false agency, negative listing, and narration from a
  distance.
- **Rejected:** hard bans that ignore document type and phrase lists that
  encode one writer's taste as a universal rule.

## Anthropic doc-coauthoring skill

- **Title and URL:** [Anthropic `doc-coauthoring`](https://github.com/anthropics/skills/tree/main/skills/doc-coauthoring)
- **Responsible:** Anthropic; the path was introduced by Keith Lazuka.
- **Version:** no per-skill release. The path-level version inspected was the
  file introduced on 2025-12-04.
- **Commit:** path commit `00756142`; repository inspection point
  `b29e7cf65e5cb78a5ac33d582270551bc74a14eb` (2026-07-24).
- **Inspected:** 2026-07-31; skill workflow, path history, repository licensing notes, and
  provider-specific dependencies.
- **License/status:** no license declaration was found in the skill directory.
  The repository applies different terms to different skills, so this entry is
  citation and idea-only use. No distinctive workflow prose was copied.
- **Adopted:** an optional cold-reader pass for new or substantially rewritten
  documents. The reader checks ambiguity, hidden assumptions, contradictions,
  and missing context without access to the authoring conversation.
- **Rejected:** provider-specific connectors and artifacts, a fixed quota of
  brainstorming questions, and appending the private conversation to make the
  document understandable.

## Gemini CLI docs-writer skill

- **Title and URL:** [Gemini CLI `docs-writer`](https://github.com/google-gemini/gemini-cli/tree/main/.gemini/skills/docs-writer)
- **Responsible:** Google and Gemini CLI contributors.
- **Version:** repository skill with no separate release; paired with the
  adjacent `docs-auditing` workflow.
- **Commit:** relevant `docs-writer` change `220888ac2dfd` (2026-04-17),
  `docs-auditing` introduction `f387e456bed7` (2026-04-09), and repository
  inspection point `d55e366f6ab393e024c613d940fead3696d56eac`
  (2026-07-30).
- **Inspected:** 2026-07-31; skill files, path history, repository license, and workflow
  assumptions.
- **License/status:** Apache License 2.0 at repository level.
- **Adopted:** ground documentation in the repository and audit in both
  directions: claims against implementation, then implementation and recent
  changes against documentation. Preserve literal strings and code exactly.
- **Rejected:** Gemini-specific paths and commands, mandatory US English,
  universal 80-column wrapping, and provider house style as a general writing
  rule.

## NIST AI 600-1

- **Title and URL:** [*Artificial Intelligence Risk Management Framework:
  Generative Artificial Intelligence Profile*](https://doi.org/10.6028/NIST.AI.600-1)
- **Responsible:** Chloe Autio, Reva Schwartz, Jesse Dunietz, Shameeka Jain,
  M. Alex Stanley, Elham Tabassi, Patrick Hall, and Kamie Roberts; National
  Institute of Standards and Technology.
- **Version:** NIST AI 600-1, published 2024-07-26. The
  [publication page](https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-generative-artificial-intelligence)
  was updated 2026-04-08.
- **Commit:** not applicable to this publication.
- **Inspected:** 2026-07-31; publication record and sections on confabulation, source
  verification, citation verification, and provenance.
- **License/status:** US federal government publication; generally public
  domain in the United States, subject to any identified third-party material.
- **Adopted:** verify unfamiliar factual claims and citations, preserve source
  dates and versions, and treat generated summaries as leads rather than
  evidence.
- **Rejected:** treating provenance labels or model confidence as proof, and
  importing the full organizational risk framework into a prose-editing skill.

## Google Technical Writing courses

- **Title and URL:** [Audience](https://developers.google.com/tech-writing/one/audience)
  and [Documents](https://developers.google.com/tech-writing/one/documents),
  Google Technical Writing One.
- **Responsible:** Google technical-writing course maintainers.
- **Version:** live pages updated 2025-03-28 and 2025-07-07 respectively.
- **Commit:** the rendered pages do not expose an immutable source commit.
- **Inspected:** 2026-07-31; official audience and document-organization lessons.
- **License/status:** page text is CC BY 4.0; code samples are Apache License
  2.0 under the site notice.
- **Adopted:** identify reader role, proximity, and prior knowledge; state
  scope; remove material outside that scope; answer the reader's essential
  questions before details.
- **Rejected:** copying Google examples or house style wholesale and requiring
  every short document to state an audience section explicitly.

## Purdue OWL: Organizing Your Argument

- **Title and URL:** [*Organizing Your Argument*](https://owl.purdue.edu/owl/resources/teaching_resources/documents/new-organizing-your-argument_-09042025.pdf)
- **Responsible:** Purdue Online Writing Lab, Purdue University.
- **Version:** teaching resource dated 2025-09-04 in its canonical filename.
- **Commit:** not applicable; no public source commit is exposed.
- **Inspected:** 2026-07-31; the official teaching resource and Purdue copyright notice.
- **License/status:** copyright Purdue University, all rights reserved. Used as
  a cited reference only; no slide text or examples were copied.
- **Adopted:** connect a claim to reasons, credible evidence, and an explicit
  warrant that explains why the evidence supports the claim. Record limits or
  counterarguments when they affect the decision.
- **Rejected:** forcing an argumentative thesis onto reference, runbook, or
  procedure documents whose job is not persuasion.

## GitHub Docs style guide

- **Title and URL:** [GitHub Docs style guide, "Expiring
  content"](https://docs.github.com/en/contributing/style-guide-and-content-model/style-guide#expiring-content)
- **Responsible:** GitHub Docs maintainers and contributors.
- **Version:** live documentation inspected against the source repository.
- **Commit:** [`github/docs`](https://github.com/github/docs) at
  `9b1b67eb79d105f900e7f4af9b7f7c5371123bf9` (2026-07-30).
- **Inspected:** 2026-07-31; expiring-content guidance, accessible visual guidance,
  repository license, and source history.
- **License/status:** documentation content is CC BY 4.0; application code is
  MIT under the repository's licensing split.
- **Adopted:** avoid claims that silently expire. When time-sensitive content
  is necessary, record its validity condition and review date. Explain the
  meaning of diagrams and graphs in text.
- **Rejected:** GitHub product terminology, page templates, or visual rules as
  universal documentation defaults.

## Digital Inquiry Group: lateral reading

- **Title and URL:** [*Lateral Reading on the Open
  Internet*](https://cor.inquirygroup.org/research/lateral-reading-on-the-open-internet/)
  and the paper DOI [`10.1037/edu0000740`](https://doi.org/10.1037/edu0000740).
- **Responsible:** Sam Wineburg, Joel Breakstone, Sarah McGrew, Teresa Ortega,
  and Mark Smith; Digital Inquiry Group and the American Psychological
  Association publication venue.
- **Version:** 2022 paper in *Journal of Educational Psychology*, 114(5),
  893-909.
- **Commit:** not applicable to the paper; no immutable commit was used.
- **Inspected:** 2026-07-31; official research summary, paper metadata, and material-level
  licensing statements.
- **License/status:** the journal article is copyrighted by the American
  Psychological Association. Some Digital Inquiry Group teaching materials
  are CC BY 4.0, but that license was not assumed for the paper or whole site.
- **Adopted:** when a source is unfamiliar, leave it to investigate the owner,
  reputation, and independent corroboration. Site polish and an authoritative
  tone do not establish reliability.
- **Rejected:** treating a domain name, logo, popularity, or search rank as
  authority and claiming that a classroom intervention directly proves agent
  behavior.

## UK Office for National Statistics content guidance

- **Title and URL:** [Writing for user
  needs](https://service-manual.ons.gov.uk/content/writing-for-users/user-needs)
  and [Writing main points and
  analysis](https://service-manual.ons.gov.uk/content/writing-for-users/writing-main-points-and-analysis),
  ONS Service Manual.
- **Responsible:** UK Office for National Statistics.
- **Version:** live service-manual pages; no numbered release.
- **Commit:** the rendered manual does not expose an immutable source commit.
- **Inspected:** 2026-07-31; official pages, their current examples, and the site reuse
  notice.
- **License/status:** Open Government Licence v3.0 unless the page identifies
  another rightsholder.
- **Adopted:** derive user needs from evidence, prioritize them, remove material
  that does not serve them, and use charts only when they make the conclusion
  easier to grasp. Text should add context instead of repeating a chart.
- **Rejected:** universal word counts, bullet quotas, and structures designed
  specifically for statistical releases.

## Diataxis

- **Title and URL:** [Diataxis](https://diataxis.fr/) and its
  [documentation repository](https://github.com/evildmp/diataxis-documentation-framework).
- **Responsible:** Daniele Procida.
- **Version:** live framework and repository state inspected 2026-07-31.
- **Commit:** `ea4fc4d85c8747107dc297e894e89d1c7d0d0179`
  (2026-07-17).
- **Inspected:** 2026-07-31; current framework overview, repository history, and license.
- **License/status:** CC BY-SA 4.0.
- **Adopted:** identify whether a document teaches, guides a task, specifies
  facts, or explains a concept. Judge structure and completeness against that
  job instead of forcing one persuasive pattern onto every document.
- **Rejected:** imposing the full four-quadrant information architecture on
  every repository and relying on older Divio presentations after the author
  revised the framework.

## van Nuenen: Voice Under Revision

- **Title and URL:** [*Voice Under Revision: Large Language Models and the
  Normalization of Personal Narrative*](https://arxiv.org/abs/2604.22142)
- **Responsible:** Tom van Nuenen.
- **Version:** arXiv `2604.22142v1`, submitted 2026-04-24; arXiv DOI
  [`10.48550/arXiv.2604.22142`](https://doi.org/10.48550/arXiv.2604.22142).
- **Commit:** not applicable to the paper version.
- **Inspected:** 2026-07-31; arXiv record, abstract, submission history, and license link.
- **License/status:** preprint under CC BY 4.0. It had one arXiv version and
  was not presented here as peer-reviewed.
- **Adopted:** rewriting can normalize personal narrative by reducing function
  words, contractions, and first-person markers while increasing lexical and
  punctuation complexity. Preserve the author's sample and causal chain, and
  audit the direction of drift after revision.
- **Rejected:** extending findings from 300 personal narratives to every
  register, treating any one marker as authorship proof, or claiming that a
  "preserve voice" prompt eliminates drift. The reported average reduction
  was partial and descriptive.

## Maintainer-supplied Threads excerpt

- **Title and URL:** `plusclov_`, "비즈니스 문서 쓸 때 목숨 걸고 지켜야
  할 내용들". No stable Threads URL was included in the supplied excerpt.
- **Responsible:** account `plusclov_`; identity and credentials were not
  independently verified.
- **Version:** maintainer-supplied snapshot with a relative "10 hours" label.
  The exact publication time and later edits are unknown.
- **Commit:** not applicable.
- **Inspected:** 2026-07-31; text pasted by the maintainer, including replies
  and promotional links. The original post was not independently retrieved.
- **License/status:** unverified social-media inspiration with no reuse license.
  It is not an authority for factual or universal claims, and its wording is
  not copied into the skill.
- **Adopted:** questions worth testing: can a cold reader understand the
  document, does it state its main message, and do each claim and its evidence
  support one another? Tables or diagrams may help when they genuinely improve
  comprehension.
- **Rejected:** removing all adjectives and pronouns, writing only in nouns and
  numbers, visualizing everything, applying a 12-point minimum or three-color
  cap to prose, treating six-question reporting as universal, and using
  credentials or course promotion as evidence.

## Licensing and close-copy threshold

This repository adopted ideas after checking sources, then wrote its own
instructions for its own workflow. The current change does not copy
substantial third-party prose, examples, taxonomies, tables, diagrams, or code.
For that reason no third-party notice file was added. This register still names
sources because provenance makes maintenance and challenge easier.

Future contributors must stop before a close copy. A close copy includes a
distinctive sentence, worked example, taxonomy, table, diagram, code fragment,
or source structure whose expression remains recognizable after editing. At
that threshold, inspect the exact material's license rather than assuming the
repository root license applies. Record the version and rightsholder, preserve
required attribution and notices, mark adaptations, obey share-alike terms,
or obtain permission when no reuse license exists. If those obligations do not
fit this repository, keep only the underlying idea and restate it independently
or reject it.
