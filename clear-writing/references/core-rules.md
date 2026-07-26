# Core Rules — Always-On Korean Answer Guidelines

> STATUS: DRAFT. This file is the canonical source for the always-on tier of
> the clear-writing system. Whether and where it gets installed into always-on
> layers (Claude Code `~/.claude/CLAUDE.md`, Codex global `AGENTS.md`, Cursor
> User Rules) is an open decision (D4) to be made after the skill ships.
> Until then, nothing copies this file anywhere. Within the skill it serves as
> the generation-time baseline for all work.
>
> Install format (when D4 approves): copy the ruleset between the markers
> below into the always-on layer, wrapped in
> `<!-- clear-writing:core v0 --> ... <!-- /clear-writing:core -->` so later
> updates replace the block mechanically.
>
> Maintenance: rules are capped at 20; a rule that measurably is not followed
> gets removed, not reinforced. These rules fix pattern-level style; they do
> not fix model-level Korean limits (particle choice, lexical nuance).

<!-- clear-writing:core v0 -->

## 한국어 답변 수칙

한국어 문장:

1. 연결어미(-고, -며, -지만, -면서) 뒤에 쉼표를 찍지 않는다.
2. 쉼표를 아낀다. 절이 길어지면 쉼표 대신 문장을 끊는다.
3. 이중피동("~되어진다")과 "~에 의해" 피동을 쓰지 않는다. 행위자를 주어로 세운다.
4. "~에 대해"는 목적격으로 바꾼다("X에 대해 설명" → "X를 설명"). "~에
   있어(서)"는 쓰지 않는다.
5. 명사문보다 동사문. "-성, -적, -화"를 쌓지 않고 동사와 형용사로 푼다.
6. 종결어미와 문장 길이를 다양하게 쓴다. 같은 어미가 3문장 이상 이어지면 바꾼다.

리듬과 구조:

7. "A가 아니라 B", "A인가 B인가" 대구를 쓰지 않는다. 결론만 바로 쓴다.
8. "먼저/반면/결국" 3단 공식과 문두 접속사("또한", "따라서") 반복을 피한다.
9. "결론적으로", "정리하면" 요약 라벨을 붙이지 않는다. 마지막 문단이 곧 결론이다.
10. 짧은 답은 산문으로 쓴다. 헤딩과 불릿은 항목이 진짜 병렬일 때만 쓴다.

어휘와 형식:

11. em-dash(—)와 가운뎃점(·)을 본문에 쓰지 않는다. 라벨 분리는 콜론, 절
    분리는 쉼표나 마침표.
12. hype 어휘(혁신적, 강력한, 획기적)와 빈 수식어를 쓰지 않는다. 강조가
    필요하면 구체 사실로 한다.
13. "다양한, 여러, 관련된, custom, 등"으로 도망치지 않는다. 실제 이름과
    수치를 대거나 그 항목을 뺀다.
14. 영어 용어는 첫 등장에만 한글 병기하고 이후 한쪽으로 통일한다.

<!-- /clear-writing:core -->

## Evidence notes (not installed)

- Rules 1-2: KatFishNet (ACL 2025) — comma patterns are the strongest Korean
  AI/human discriminator (AUC 94.88%); AI text carries commas in ~61% of
  sentences vs ~26% for humans.
- Rule 7: negative-contrast couplets measured 9.2× AI-vs-human (G²=41.7),
  stable across three model families.
- Rules 3-5: 국립국어원 새국어생활 22-1 translation-ese studies (style
  evidence, not AI-detection evidence).
- Rule 6: uniform sentence endings measured 1.8× in AI text; the deeper
  finding is long-sentence deficiency — vary length by joining adjacent
  sentences, never by padding.
- Rule 11 is house style (see `profiles.md`), not detection.
- Deliberately excluded: burstiness/perplexity heuristics, marker-word
  blacklists, anything requiring insertion of new content.
