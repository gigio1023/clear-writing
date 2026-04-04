# Anti-Slop Patterns

Use this file for sentence-level diagnosis.

## Primary pattern: abstraction inflation

Bad AI prose often turns concrete actions into high-level labels.

| Weak pattern | Better target |
| --- | --- |
| label only | mechanism |
| mechanism only | observable detail when available |

Examples:

- "협업 기반을 구축했다" -> what changed in the workflow or interface?
- "created a robust framework" -> what now exists, who uses it, and how?

## Detection checklist

### 1. Labels as the main verb

Watch for verbs like:

- 구축했다
- 확보했다
- 달성했다
- 강화했다
- enabled
- established
- achieved
- facilitated

If the sentence can be rewritten with the actual action, rewrite it.

### 2. Placeholder actors

Watch for:

- various teams
- stakeholders
- users
- external partners
- 내부 조직
- 여러 팀

If the source names the actor, use the actor. If not, quantify or bound the group.

### 3. False agency

Do not let abstractions perform human actions.

Examples:

- "the decision emerged"
- "the roadmap identified"
- "the system understood"

Name the person, team, or concrete process instead.

### 4. AI cadence

Watch for:

- three or more parallel clauses with identical rhythm
- connective chains like "이를 통해", "이를 바탕으로", "based on this", "in order to"
- repeated rhetorical contrasts like "not X, but Y"
- em-dash-heavy summaries

Break the rhythm and say the thing directly.

### 5. Empty modifiers

Cut adjectives/adverbs unless they carry real scope.

Examples:

- robust
- seamless
- significant
- innovative
- strategic
- effectively

## Safe keeps

Do not strip these just because they sound formal:

- established domain terms
- accurate technical terminology
- intentional metaphors that genuinely help comprehension
- explicit uncertainty markers
