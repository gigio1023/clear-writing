# Style Profiles

House-style overlays applied on top of the skill's base rules. A profile is a
formatting policy choice, **not** an AI-detection claim — em-dash frequency,
for example, is a decaying, vendor-dependent signal as a detector, but a
legitimate house rule as style. Keeping the two justifications separate is
what lets profile rules change without touching evidence-backed rules.

## Selecting a profile

1. Explicit user request wins ("엄격하게", "회사 문서 스타일로", "strict").
2. Repository policy next: AGENTS.md / CLAUDE.md / style-guide files that
   state formatting rules adopt those rules verbatim (they outrank both
   profiles).
3. Otherwise **default**. Never select by who the author works for; profiles
   are chosen per document context, not per affiliation.

A user-supplied writing sample still outranks profile style rules
(`voice-preservation.md`).

## default

- No forced punctuation bans. Follow the document's existing conventions.
- Emoji: remove from technical documents (korean-tells C-5); tolerate in chat
  and informal notes.
- Hedging: spec/definition sections assertive; guides may keep a
  conversational register.

## strict

For technical documents that may be shared externally, onboard new readers, or
enter formal review. Adds, on top of default:

**Punctuation (zero-tolerance set)**

- Em-dash (—), en-dash used as clause break, middle-dot (·), and decorative
  bullet characters (•) in body text: 0 occurrences. Replacement priority:
  label/definition split → colon; clause split → comma; sentence split →
  period; if none fits, rewrite as two sentences.
- Decorative quotation marks for emphasis: remove; keep genuine quotations and
  term definitions.

**Workplace vocabulary (Korean)**

Documents must survive external sharing; conversational slang left over from
chat drafts is replaced with precise verbs:

| Slang | Replace with |
|---|---|
| 복붙 | 복사, 그대로 복사 |
| 박다 (값을 박음) | 명시, 등록, 고정 — the exact verb |
| 한 방에 | 한 번에, 한 채널에서 |
| 뚝딱, 후딱, 휙 | drop, or 즉시 |
| 굴리다, 돌리다 | 실행한다, 동작시킨다 |
| 찍다 (로그를 찍다) | 기록한다, 발행한다 |
| 맞장구, 헐, 와우 등 감탄 | delete |
| 어쨌든, 아무튼 | delete, or 즉/결국 |

**Register**

- Bold emphasis in body text: near-zero; table headers and genuinely critical
  warnings only.
- One formality register per document (existing register wins).

## Adding a profile

A new profile earns its place only when a real document set needs rules that
would be wrong elsewhere. Record for each rule: what it forces, and why it is
style policy rather than evidence (or cite the evidence). Keep profiles small;
anything that is simply good writing belongs in the base rules, not a profile.
