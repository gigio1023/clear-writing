# Sources and Inspiration

This register records what informed `slop-aware-writing`, what the repository
actually adopted, and what it rejected. It is a provenance record, not a claim
that every source is equally authoritative. Research findings, official
guidance, open-source skills, and a maintainer-supplied social post carry
different evidentiary weight.

Unless an entry says otherwise, `Inspected` means 2026-07-31. `Adopted` means
the maintainers restated an idea independently and fitted it to this skill's
scope. It does not mean that source prose, examples, tables, or code were
copied. `Rejected` records tempting ideas that should not return without new
evidence.

## Register map

- Korean: `im-not-ai`, KatFishNet, and National Institute of Korean Language
  translationese studies
- English and common: anti-slop skills, documentation workflows, source and
  argument guidance, plain-language guidance, voice and assisted-revision
  research, Pilcrow, local research notes, and frontier-model prompting guidance
- Italian: institutional plain-language guidance, grammar and information-flow
  scholarship, and generated-text research
- Chinese: `zh-CN`, `zh-TW`, and `zh-HK` standards and manuals, translation
  corpora, multidimensional writing research, and detector limitations
- Maintainer material: the supplied business-writing social post and the
  explicit adoption and rejection record

## epoko77-ai/im-not-ai

- **Title and URL:** [`im-not-ai`](https://github.com/epoko77-ai/im-not-ai)
- **Responsible:** epoko77-ai; current head authored by Liam Lee.
- **Version:** release `v2.3.0`; `main` also inspected for later changes.
- **Commit:** release `82137e858763dadb99561f194c5c00465735017b`;
  inspected `main` at `53e24e8f92cf344efcb812103f7c2b203e7efffc`
  (2026-07-22). The post-release changes affected social assets and a build
  script, not the writing taxonomy used here.
- **Inspected:** 2026-08-02; local clone, tag history, rules, evidence notes,
  and license.
- **License/status:** MIT, copyright 2026 epoko77-ai. Active upstream.
- **Adopted:** stable Korean pattern IDs, evidence labels, surgical edits,
  diff-based reporting, and periodic upstream delta checks.
- **Rejected:** vendoring the source, treating its small self-study as a
  universal detector, treating its synthesized Korean background report as a
  primary source, making company house style universal, and reviving rules
  that its own evidence downgraded. The public repository provides neither the
  self-study corpus nor reproduction scripts, so its measurements are labeled
  unreproduced.

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

## National Institute of Korean Language: translationese studies

- **Title and URL:** Kim Jeong-woo, [*현대 국어 번역문의
  실태*](https://www.korean.go.kr/nkview/nklife/2012_1/22_0104.pdf), and
  Kim Sun-young, [*영한 번역에 나타난 번역투
  문장*](https://www.korean.go.kr/nkview/nklife/2012_1/22_0105.pdf).
- **Responsible:** Kim Jeong-woo and Kim Sun-young; published by the National
  Institute of Korean Language.
- **Version:** *Sae Gugeo Saenghwal* 22(1), spring 2012.
- **Commit:** not applicable to these journal PDFs.
- **Inspected:** 2026-08-02; article PDFs and the
  [issue page](https://www.korean.go.kr/nkview/nklife/2012_1.html).
- **License/status:** reuse terms were not established from the inspected
  pages. The articles are cited only; no article prose or worked examples are
  redistributed.
- **Adopted:** contextual review cues for passive constructions, pronouns,
  `가지다`, and preposition-shaped phrases such as `~에 의해` and
  `~에 관하여` in English-Korean translation.
- **Rejected:** universal bans, applying a translation-corpus observation to
  native Korean without context, or treating translationese as AI authorship
  evidence. Both articles discuss scope limits and context-sensitive choices.

## petergyang/no-ai-slop

- **Title and URL:** [`no-ai-slop`](https://github.com/petergyang/no-ai-slop)
- **Responsible:** Peter Yang.
- **Version:** `v1.0.6`.
- **Commit:** `f2b25e603800dfc01ba93f1092056724eb93059e`
  (2026-08-01).
- **Inspected:** 2026-08-02; tagged repository, skill instructions, pattern
  descriptions, and license. Changes after v1.0.4 affected plugin metadata,
  imagery, and README promotion, not the patterns adopted here.
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
  worded checks for responsibility-hiding agency, delayed conclusions, and
  narration from a distance.
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
- **Responsible:** National Institute of Standards and Technology. The
  publication acknowledgments name Chloe Autio, Jesse Dunietz, Patrick Hall,
  Shomik Jain, Kamie Roberts, Reva Schwartz, Martin Stanley, and Elham
  Tabassi.
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
- **Version:** the canonical filename contains `09042025`, but the PDF has no
  printed publication date. Its metadata records author Garrett Ivan Colon and
  creation/modification on 2025-09-19.
- **Commit:** not applicable; no public source commit is exposed.
- **Inspected:** 2026-08-02; the official teaching resource, PDF metadata, and
  Purdue copyright notice.
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
- **Version:** live framework and repository state inspected 2026-08-02.
- **Commit:** `0c9022ecbd82f8cd42069886faae40cd91eb8995`
  (2026-08-01).
- **Inspected:** 2026-08-02; current framework overview, repository history,
  and license. Changes after the prior inspection affected translations and
  spelling lists, not the framework adopted here.
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
  punctuation complexity. In the reported English narrative sample, the
  voice-preserving condition reduced mean effect magnitude by 32%, direction
  agreement was 85%, and two markers reversed. Preserve the author's sample
  and causal chain, and audit drift after revision.
- **Rejected:** extending findings from 300 personal narratives to every
  register, treating any one marker as authorship proof, or claiming that a
  "preserve voice" prompt eliminates drift. The preprint's English narrative
  scope does not establish the same rates or directions in Korean or other
  genres.

## English technical and public-language guidance

- **Titles and URLs:** Google Developer Documentation Style Guide on
  [active voice](https://developers.google.com/style/voice),
  [anthropomorphism](https://developers.google.com/style/anthropomorphism), and
  [voice and tone](https://developers.google.com/style/tone);
  [Digital.gov Plain Language Guide](https://digital.gov/guides/plain-language)
  and [paraphrase testing](https://digital.gov/guides/plain-language/test/paraphrase-testing);
  W3C [*Making Content Usable for People with Cognitive and Learning
  Disabilities*](https://www.w3.org/TR/2021/NOTE-coga-usable-20210429/); and
  [RFC 8174](https://www.rfc-editor.org/info/rfc8174/).
- **Responsible:** Google developer-documentation maintainers; the US General
  Services Administration; the W3C Cognitive and Learning Disabilities
  Accessibility Task Force; and the Internet Engineering Task Force.
- **Version:** Google pages updated 2024-10-15 and 2026-05-27; Digital.gov live
  pages inspected 2026-08-02; W3C Working Group Note dated 2021-04-29; RFC 8174,
  BCP 14, May 2017.
- **Inspected:** 2026-08-02; official pages and normative-status labels.
- **License/status:** Google documentation is CC BY 4.0 under its site notice;
  Digital.gov is an official US government service with page-specific rights;
  the W3C document is a non-normative Working Group Note; RFC 8174 is an IETF
  Best Current Practice. All are independently
  paraphrased rather than copied.
- **Adopted:** active voice is useful when responsibility matters, while
  passive voice remains valid when the actor is unknown, unimportant, or
  intentionally backgrounded; prioritize the reader's task; test important
  prose with representative readers; and preserve normative requirement words
  and capitalization where the governing standard assigns them special force.
- **Rejected:** banning inanimate grammatical subjects, forcing active voice or
  present tense in every genre, treating an LLM cold read as equivalent to
  user testing, and applying BCP 14 capitalization outside documents that
  invoke it.

## Official terminology anchors

- **Titles and URLs:** Pact's [consumer and provider
  model](https://docs.pact.io/getting_started/how_pact_works), SonarQube
  [quality gates](https://docs.sonarsource.com/sonarqube-server/quality-standards-administration/managing-quality-gates/introduction-to-quality-gates),
  Unity's [vertical slice](https://learn.unity.com/course/practical-game-accessibility/unit/welcome-to-the-course/tutorial/explore-out-of-circulation),
  [RFC 7519 claims](https://www.rfc-editor.org/rfc/rfc7519.html#section-4),
  GitHub Actions [workflow artifacts](https://docs.github.com/en/actions/concepts/workflows-and-actions/workflow-artifacts),
  [OpenAPI 3.2.0](https://spec.openapis.org/oas/v3.2.0.html#openapi-description-structure),
  Kubernetes [API surfaces](https://kubernetes.io/blog/2026/02/12/sig-architecture-api-spotlight/),
  Microsoft Kiota [public API surface](https://learn.microsoft.com/en-us/openapi/kiota/support),
  OpenTelemetry [instrumentation scope](https://opentelemetry.io/docs/specs/otel/common/instrumentation-scope/),
  and NIST's engineering statistics [response surface
  model](https://www.itl.nist.gov/div898/handbook/glossary.htm).
- **Responsible:** the named standards bodies and official project or product
  documentation maintainers.
- **Version:** RFC 7519, May 2015; OpenAPI 3.2.0; Kubernetes article dated
  2026-02-12; other live official pages inspected in their current form.
- **Inspected:** 2026-08-02; defining sections, product scope, and the concrete
  relation or mechanism each term names.
- **License/status:** mixed official specifications and product documentation,
  cited only. Live pages without immutable versions must be rechecked before a
  consequential terminology decision.
- **Adopted:** a technical-looking term is useful when its governing source and
  target domain share the same actors, relation, mechanism, and consequence.
  Contextual questions for `contract`, `gate`, `slice`, `claim`, `artifact`,
  `surface`, and `scope` come from these distinctions.
- **Rejected:** treating the examples as an allowlist, replacing one system's
  official field with another system's vocabulary, and using a page hit as
  proof that a term fits the sentence under review.

## English marker and assisted-revision research

- **Titles and URLs:** Kobak et al., [*Delving into LLM-assisted writing in
  biomedical publications through excess vocabulary*](https://arxiv.org/abs/2406.07016),
  published in *Science Advances* in 2025; Baumler et al., [*Can You Make It
  Sound Like You? Post-Editing LLM-Generated Text for Personal
  Style*](https://aclanthology.org/2026.acl-long.2030/); and Abdulhai et al.,
  [*How LLMs Distort Our Written Language*](https://arxiv.org/abs/2603.18161).
- **Responsible:** Dmitry Kobak and coauthors; Baumler and coauthors; and
  Marwa Abdulhai and coauthors.
- **Version:** Kobak arXiv `2406.07016v5`, 2025-07-03, paired with the
  peer-reviewed 2025 publication; Baumler et al., ACL 2026 long paper, DOI
  `10.18653/v1/2026.acl-long.2030`; Abdulhai et al., arXiv
  `2603.18161v1`, submitted 2026-03-18.
- **Inspected:** 2026-08-02; papers, metadata, methods, and stated limitations.
- **License/status:** Kobak's journal article and Abdulhai's preprint are cited
  research; Baumler et al. is an ACL 2026 paper. No corpora, tables, examples,
  or paper prose are redistributed.
- **Adopted:** English marker words can shift at corpus scale, so they are
  density prompts rather than passage-level verdicts. In Baumler et al.'s
  preregistered study of 81 English-proficient participants, post-editing moved
  model drafts toward participants' measured style but did not restore the
  distribution of independently written text. Correction-oriented assistance
  can also change stance and meaning, so even narrow polish jobs pass semantic
  verification.
- **Rejected:** classifying one passage from an excess word, generalizing
  biomedical abstracts or personal-writing tasks to every genre and language,
  optimizing for a style detector, and claiming that post-editing restores
  authorship identity.

## Pilcrow and local research notes

- **Title and URL:** [Pilcrow](https://github.com/SamGalanakis/pilcrow), plus
  maintainer-local `brain/clips` and `brain/research` notes that index
  `no-ai-slop`, Longreads, Slop Guard, `im-not-ai`, and a personal academic
  English vocabulary observation.
- **Responsible:** Sam Galanakis for Pilcrow; Eric Tramel for
  [Slop Guard](https://eric-tramel.github.io/blog/2026-02-18-slop-guard/);
  the local notes retain their own source metadata.
- **Version:** Pilcrow `v0.17.2`, commit
  `55f49409c7035c05d31545a0e3052ae04b825884` (2026-05-26); local notes inspected
  at their recorded capture dates and again on 2026-08-02.
- **Inspected:** 2026-08-02; current Pilcrow source and the complete relevant
  local notes, then the original public sources where they supplied one.
- **License/status:** Pilcrow is MIT. The local clips are private secondary
  notes, not independent authorities and not redistributed. Slop Guard is a
  blog and tool-design report rather than a peer-reviewed validation.
- **Adopted:** note voice before editing, quote the offending span in review
  mode, inspect the editor's own output, distinguish genre, and look for
  concentrated patterns rather than treating one phrase as dispositive. A
  personal academic-English note reinforced the already independent rule to
  preserve claim strength and logical relations.
- **Rejected:** prose scores, regex thresholds, a fixed skeptical-reader
  persona, detector gaming, reinforcement-learning rewards from a slop score,
  treating Longreads as a style authority, and using a local summary in place
  of its cited paper or repository.

## Frontier-model prompting guidance

- **Titles and URLs:** OpenAI [Model guidance for
  GPT-5.6](https://developers.openai.com/api/docs/guides/latest-model) and
  Anthropic [Prompting Claude Fable
  5](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-fable-5).
- **Responsible:** OpenAI and Anthropic.
- **Version:** live official documentation inspected 2026-08-02. These pages
  can change and do not define a permanent model contract.
- **Inspected:** 2026-08-02; prompt-size, instruction-following, migration, and
  skill-scaffolding guidance relevant to this package.
- **License/status:** official product documentation cited for design rationale;
  no prompt blocks or model-specific configuration are redistributed.
- **Adopted:** remove repeated generic language instruction, state the outcome
  and hard boundaries once, and let a capable model perform ordinary contextual
  language judgment. Preserve direct verification for facts, artifacts, and
  meaning-sensitive edits.
- **Rejected:** naming a current model in the portable writing contract,
  hard-coding effort or harness features, assuming leaner is always better, and
  treating vendor evaluation ranges as evidence that this skill improved.

## Italian official and institutional guidance

- **Titles and URLs:** [UNI ISO 24495-1:2024](https://store.uni.com/uni-iso-24495-1-2024);
  the European Commission's [*Scrivere
  chiaro*](https://op.europa.eu/it/publication-detail/-/publication/725b7eb0-d92e-11e5-8fea-01aa75ed71a1/language-it);
  Designers Italia on [language](https://designers.italia.it/design-system/fondamenti/linguaggio/)
  and [content](https://designers.italia.it/design-system/fondamenti/contenuti/);
  the 2002 [public-administration simplification
  directive](https://www.gazzettaufficiale.it/atto/serie_generale/caricaArticoloDefault/originario?atto.codiceRedazionale=02A07864&atto.dataPubblicazioneGazzetta=2002-06-18&atto.tipoProvvedimento=DIRETTIVA);
  and the CNR and Accademia della Crusca [administrative drafting
  guide](https://www.ittig.cnr.it/Ricerca/Testi/GuidaAttiAmministrativi.pdf).
- **Responsible:** UNI and ISO; European Commission; Designers Italia; Italian
  Department of Public Administration; CNR and Accademia della Crusca.
- **Version:** UNI adoption effective 2024-02-01; Commission 2015 edition,
  released on the website 2016-02-19, DOI `10.2782/478661`; Designers Italia
  pages updated 2025-04-14 and 2025-09-05; directive dated 2002-05-08;
  administrative guide, first edition, February 2011.
- **Inspected:** 2026-08-02; official records, scopes, dates, and reuse notices.
- **License/status:** the ISO standard is paid and not reproduced; Designers
  Italia material is CC BY-SA 4.0; the 2011 guide is CC BY-ND 2.5 Italy. Other
  items are cited institutional guidance. No worked examples or source
  structure are copied.
- **Adopted:** write for a defined reader, expose action and responsibility when
  useful, explain necessary abbreviations, reduce empty support-verb and
  administrative phrasing, and judge lists and headings by the public-service
  task in their original scope.
- **Rejected:** universal sentence-word limits, banning borrowings, applying
  public-service web quotas to essays or developer docs, and using an
  international plain-language standard as Italian grammar evidence.

## Italian grammar, information flow, and generated-text research

- **Titles and URLs:** Accademia della Crusca on
  [punctuation](https://accademiadellacrusca.it/it/consulenza/la-punteggiatura/143),
  [gerund attachment](https://accademiadellacrusca.it/it/consulenza/dubbi-sul-gerundio/26332),
  [gerund subjects](https://accademiadellacrusca.it/it/consulenza/uso-del-gerundio-con-soggetto-diverso-da-quello-della-frase-reggente/268),
  and [`piuttosto che`](https://accademiadellacrusca.it/it/consulenza/uso-di-piuttosto-che-con-valore-disgiuntivo/11);
  Angela Ferrari on [syntactic simplicity and information
  flow](https://accademiadellacrusca.it/it/contenuti/la-semplicit-sintattica-in-prospettiva-testuale-riflessioni-a-partire-dalla-guida-alla-redazione-deg/9234);
  Brunato et al. on [Italian text
  simplification](https://doi.org/10.3389/fpsyg.2022.707630);
  [READ-IT](https://aclanthology.org/W11-2308/); Musacchio on
  [information distribution in translated scientific
  Italian](https://www.openstarts.units.it/bitstreams/e4471a57-bb5c-4e38-8d37-57c589a0719f/download);
  Tavosanis on [evaluating generated Italian](https://doi.org/10.62408/ai-ling.v1i1.14);
  Palermo on [AI-generated
  texts](https://accademiadellacrusca.it/it/contenuti/titolo/46422); and
  Sciandra et al. on [Italian essay
  detection](https://doi.org/10.1038/s41598-026-51613-9).
- **Responsible:** Accademia della Crusca authors; Angela Ferrari; Dominique
  Brunato and coauthors; Dell'Orletta and coauthors; Maria Teresa Musacchio;
  Mirko Tavosanis; Massimo Palermo; Sciandra and coauthors.
| Source | Publication record and scope |
|---|---|
| Accademia della Crusca, punctuation | 2004-07-16; punctuation and syntactic attachment |
| Accademia della Crusca, gerund attachment | 2023-05-12; gerund function and attachment |
| Accademia della Crusca, separate gerund subject | 2010-04-09; explicit and understood subjects |
| Accademia della Crusca, `piuttosto che` | *La Crusca per voi* 24, April 2002; preference and disjunction |
| Ferrari | 2021-03-19; syntactic simplicity in textual and information-flow perspective |
| Brunato et al. | 2022-03-08, *Frontiers in Psychology* 13; Italian text simplification |
| READ-IT | SLPAT 2011, ACL Anthology `W11-2308`; Italian readability assessment |
| Musacchio | 2004, *Rivista internazionale di tecnica della traduzione* 8, pp. 89-105; translated scientific Italian |
| Tavosanis | 2024-08-08, *AI-Linguistica* 1(1); generated Italian evaluation |
| Palermo | 2026-05-20; linguistic observations on AI-generated text |
| Sciandra et al. | published 2026-05-02; version of record 2026-07-10; Italian essay detection |
- **Inspected:** 2026-08-02; official language pages, papers, metadata, samples,
  and limits.
- **License/status:** mixed cited scholarship and official consultation pages.
  No source examples or taxonomies are redistributed.
- **Adopted:** commas can change relative-clause scope; a gerund's understood
  subject and logical attachment must be recoverable; SVO and main-clause-first
  order are options rather than universal defaults; `piuttosto che` should not
  erase preference; and translated prose should be judged by Italian
  information flow. Generated-text findings remain observation-only.
- **Rejected:** banning gerunds, passive or impersonal constructions, scoring
  readability from length, turning 2024 GPT-3.5 student essays into a durable
  AI-tell list, and adding detector-confusing words or sentence joins.

## Chinese regional standards and official manuals

- **Titles and URLs:** PRC [GB/T 15834-2011 punctuation](https://openstd.samr.gov.cn/bzgk/std/newGbInfo?hcno=22EA6D162E4110E752259661E1A0D0A8&refer=outter),
  [GB/T 9704-2012 official-document format](https://openstd.samr.gov.cn/bzgk/std/newGbInfo?hcno=F3CC9BEF482524C895FDA7A08BB4A70E),
  [Regulations on Party and Government Official Document
  Processing](https://www.mem.gov.cn/xw/ztzl/2018/cyzd/lxyz/201207/t20120708_228323.shtml),
  [Ministry of Education Official Document Processing
  Rules](https://www.moe.gov.cn/srcsite/A01/s7048/201309/t20130927_171853.html),
  [General Standard Chinese Characters](https://www.moe.gov.cn/jyb_sjzl/ziliao/A19/201306/t20130601_186002.html),
  and [TermOnline](https://www.termonline.cn/about); Taiwan MOE
  [Revised Handbook of Punctuation](https://language.moe.gov.tw/001/upload/files/site_content/m0001/hau/c2.htm),
  [standard-character resources](https://language.moe.gov.tw/material/list?page=2&u=9fd3b76d-d663-4508-bad1-a61d34e68850),
  [Lexicon](https://terms.naer.edu.tw/), and the Executive Yuan
  [Document Processing Manual](https://www.ey.gov.tw/Page/F0CD366C64B5A15C/ecb75289-a85d-45be-9fb0-0fa64c302b54);
  Hong Kong's [Official Chinese Writing Handbook, third
  edition](https://www.csb.gov.hk/english/publications_stat/publication/files/general_principles_3ed.pdf),
  [Common Chinese Character Forms](https://www.edb.gov.hk/attachment/tc/curriculum-development/kla/chi-edu/resources/primary/lang/curriculum-materials/ziXingBiao_jianJie_TC.pdf),
  and [government glossary](https://www.csb.gov.hk/hkgcsb/glossary/expnote.html);
  W3C [Chinese Layout Requirements](https://www.w3.org/TR/2026/DNOTE-clreq-20260703/).
- **Responsible:** PRC State Administration for Market Regulation, Ministry of
  Education, General Office of the CPC Central Committee, and General Office of
  the State Council; Taiwan Ministry of Education, National Academy for
  Educational Research, and Executive Yuan; Hong Kong Civil Service Bureau and
  Education Bureau; W3C Chinese Layout Task Force.

| Source | Version or date inspected |
|---|---|
| GB/T 15834-2011 | published 2011-12-30, effective 2012-06-01, status `现行` |
| GB/T 9704-2012 | published 2012-06-29, effective 2012-07-01, status `现行` |
| Party and government processing regulations | `中办发〔2012〕14号`, dated 2012-04-16, effective 2012-07-01 |
| Ministry of Education processing rules | `教办〔2013〕7号`, dated 2013-09-18, posted 2013-09-27 |
| General Standard Chinese Characters | State Council publication 2013-08-19, 8,105 characters |
| TermOnline | launched 2016-05; version 2.0 trial launched 2020-09; live database |
| Taiwan punctuation handbook | formal edition 2008-12 after the 2008-08 trial edition |
| Taiwan Executive Yuan manual | ROC 112-09 edition, September 2023 |
| Taiwan common-character standard | announced 1982-09-01, 4,808 characters; resource site updated 2025-01-10 |
| Taiwan Lexicon | live National Academy for Educational Research database |
| Hong Kong writing handbook | third edition, May 2019 |
| Hong Kong common character forms | original 1986; revisions through the 2012 annotated edition, 4,762 characters |
| Hong Kong government glossary | live database, about 115,000 entries in 23 categories |
| W3C CLReq | Group Note Draft, 2026-07-03 |

- **Inspected:** 2026-08-02; official records, current-status fields, manuals,
  live databases, and draft status.
- **License/status:** standards and government manuals carry source-specific
  rights and are cited only. Taiwan's punctuation handbook is CC BY-NC-ND 2.5
  Taiwan. CLReq is a work-in-progress W3C Group Note Draft, not an endorsed or
  binding national standard. Live terminology databases have no immutable
  snapshot.
- **Adopted:** choose `zh-CN`, `zh-TW`, or `zh-HK` before normalization; region
  can matter more than Simplified versus Traditional script; protect official
  names and product literals; use locale punctuation and terminology; and
  route line-breaking and punctuation placement to the renderer when they are
  layout problems.
- **Rejected:** treating Traditional Chinese as Taiwan Chinese, Mainland rules
  as all `zh-Hans`, automatic character conversion as complete localization,
  and importing government page formats into general technical prose.

## Chinese translation and generated-text research

- **Titles and URLs:** Hu, Li, and Kübler on [syntactic features of translated
  Chinese](https://aclanthology.org/W18-1603/); Gong, Wang, and Ren on
  [prepositions in translated Chinese](https://journal.bisu.edu.cn/article/2019/1003-6539/1003-6539-41-1-56.shtml);
  Zhang, Kotze, and Fang on [pronoun explicitation](https://doi.org/10.1080/0907676X.2019.1689276);
  Zhu et al. on [AI-generated and human Chinese](https://aclanthology.org/2023.ccl-1.46/);
  Wang et al., [LLM-Detector](https://arxiv.org/abs/2402.01158);
  Li and Zhang on [AI and human Weibo comments](https://aclanthology.org/2025.ccl-1.64/);
  Feng et al., [HoWToBench](https://aclanthology.org/2026.acl-long.317/); and
  [MAGE](https://aclanthology.org/2024.acl-long.3/).
- **Responsible:** the named paper authors and their ACL, CCL, journal, or
  preprint venues.

| Source | Publication record and scope |
|---|---|
| Hu, Li, and Kübler | Style-Var 2018, pp. 20-28, DOI `10.18653/v1/W18-1603`; translated-Chinese syntax distributions |
| Gong, Wang, and Ren | 2019, 41(1):56-66, online 2019-02-15, DOI `10.12002/j.bisu.192`; translated-Chinese prepositions |
| Zhang, Kotze, and Fang | early online 2019, issue 2020-09-02, DOI `10.1080/0907676X.2019.1689276`; English-to-Chinese children's literature |
| Zhu et al. | CCL 2023, pp. 523-534; early ChatGPT open-domain answers |
| Wang et al. | arXiv `2402.01158v1`, submitted 2024-02-02; detector preprint with mixed-text limits |
| Li and Zhang | CCL 2025, pp. 842-851, CC BY 4.0; Weibo comment data |
| Feng et al. | ACL 2026 long paper, DOI `10.18653/v1/2026.acl-long.317`; twelve Chinese writing genres |
| MAGE | ACL 2024 long paper, DOI `10.18653/v1/2024.acl-long.3`; English benchmark used only for detector limitations |

- **Inspected:** 2026-08-02; papers, dataset descriptions, domains, dates, and
  stated detector limits.
- **License/status:** mixed cited scholarship. Li and Zhang's CCL 2025 paper is
  CC BY 4.0; no paper text, data, or examples are redistributed.
- **Adopted:** group-level distributions of selected prepositions, explicit or
  personal pronouns, and `NP+的` modifiers prompt contextual review. The edit
  is independently triggered by ambiguity or redundancy in the target sentence,
  not the corpus difference. Chinese writing quality is multidimensional across
  genres, and detector performance degrades with mixed human and model text.
- **Rejected:** deleting pronouns or prepositions from counts, treating low
  typo rates or regular punctuation as AI evidence, importing an English
  detector benchmark as Chinese style guidance, and applying corpus-level
  classifier accuracy to one passage.

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
