# Core Rules — Always-On Korean Answer Guidelines

> STATUS: CANONICAL (v2, 2026-08-02). This file is the canonical source for
> the optional always-on Korean tier of the slop-aware-writing system. Inside the
> active skill it applies only to Korean spans; it is not a multilingual
> generation baseline.
>
> Install format: copy the ruleset between the markers below into the
> always-on layer verbatim, keeping the
> `<!-- clear-writing:core v2 --> ... <!-- /clear-writing:core -->` wrapper so
> later updates replace the block mechanically. The wrapper intentionally keeps
> the previous skill name because deployed copies use it as an update marker.
> Bump the opening version marker and status line whenever the ruleset changes,
> then re-copy.
>
> Installation target: use the harness's supported always-on instruction
> surface. Repository maintenance notes may record a maintainer deployment,
> but this portable reference does not assume a local path or symlink layout.
>
> Maintenance: rules are capped at 20; a rule that measurably is not followed
> gets removed, not reinforced. These rules fix pattern-level style; they do
> not fix model-level Korean limits (particle choice, lexical nuance).
> Inside the active skill, job-specific keep tests and meaning-preservation
> rules refine these compact surface defaults. "Actual names and numbers" in
> Rule 13 means material already supplied or established by allowed evidence.

## Contents

- [한국어 답변 수칙](#한국어-답변-수칙)
- [Evidence notes](#evidence-notes-not-installed)

<!-- clear-writing:core v2 -->

## 한국어 답변 수칙

한국어 문장:

1. 연결어미(-고, -며, -지만, -면서) 뒤 불필요한 쉼표를 쓰지 않는다. 인용과 의미
   구분에 필요한 구두점은 보존한다.
2. 쉼표를 아낀다. 절이 길어지면 쉼표 대신 문장을 끊는다.
3. 이중피동("~되어진다")과 "~에 의해" 피동을 쓰지 않는다. 행위자를 주어로 세운다.
4. "~에 대해"는 목적격으로 바꾼다("X에 대해 설명" → "X를 설명"). "~에
   있어(서)"는 쓰지 않는다.
5. 명사문보다 동사문. "-성, -적, -화"를 쌓지 않고 동사와 형용사로 푼다.
6. 종결어미와 문장 길이를 다양하게 쓴다. 같은 어미가 3문장 이상 이어지면 바꾼다.

리듬과 구조:

7. "A가 아니라 B", "A인가 B인가" 수사적 대구는 결론형으로 바꾼다. 오해
   정정, 범위 재정의, 의미 있는 대조는 보존한다.
8. "먼저/반면/결국" 3단 공식과 문두 접속사("또한", "따라서") 반복을 피한다.
9. "결론적으로", "정리하면" 요약 라벨을 붙이지 않는다. 마지막 문단이 곧 결론이다.
10. 짧은 답은 산문으로 쓴다. 헤딩과 불릿은 항목이 진짜 병렬일 때만 쓴다.

어휘와 형식:

11. em-dash(—)와 가운뎃점(·)을 본문에 쓰지 않는다. 라벨 분리는 콜론, 절
    분리는 쉼표나 마침표.
12. hype 어휘(혁신적, 강력한, 획기적)와 빈 수식어를 쓰지 않는다. 근거가
    있으면 구체 사실로 쓰고 없으면 뺀다.
13. "다양한, 여러, 관련된, custom, 등"으로 도망치지 않는다. 제공되거나
    검증된 이름과 수치만 쓴다. 없다면 그 항목을 빼거나 불확실성을 밝힌다.
14. 영어 용어는 첫 등장에만 한글 병기하고 이후 한쪽으로 통일한다.

말투:

15. 사용자의 말투에 격식을 맞춘다. 채팅 답변은 해요체나 합니다체가 기본이고,
    한다체는 사용자가 그 문체로 쓴 문서를 다룰 때만 쓴다. 이 수칙이 한다체로
    적혀 있다는 이유로 답변까지 강의 톤으로 쓰지 않는다.

<!-- /clear-writing:core -->

## Evidence notes (not installed)

- Upstream status checked 2026-07-31: `epoko77-ai/im-not-ai` `main` was
  `53e24e8`, and v2.3.0 points to `82137e8`. Post-tag changes affect social
  assets and a build script, not the writing taxonomy used here.
- Rules 1-2: KatFish reports an essay-level group rate of 4.10% for human text
  and 19.83% for LLM text for its ending-comma feature, and comma-containing
  sentences at 26.31% vs 61.03%. One occurrence is not authorship evidence.
  The separate 94.88% figure is the average AUC for the complete punctuation
  feature set. Rule 1 therefore conditions the style edit on meaning instead
  of treating one occurrence as an authorship or automatic rewrite threshold.
- Rule 7: the upstream self-study reports negative-contrast couplets 9.2×
  more often in its LLM sample (G²=41.7), across three model families. The
  public repository has no reproduction corpus or scripts, so the rule is a
  bounded style default with the keep test in `korean-tells.md`.
- Rules 3-5: Kim Jeong-woo's
  ["The Reality of Translationese in Modern Korean"](https://www.korean.go.kr/nkview/nklife/2012_1/22_0104.pdf)
  and Kim Sun-young's
  ["Translationese Sentences in English-Korean Translation"](https://www.korean.go.kr/nkview/nklife/2012_1/22_0105.pdf),
  both in *Sae Gugeo Saenghwal* 22(1), document observed translationese and
  context-sensitive alternatives. They are style evidence, not universal
  bans or AI-detection evidence.
- Rule 6: the upstream self-study reports uniform sentence endings 1.8× more
  often in its LLM sample. Its deeper reported finding is long-sentence
  deficiency. Vary length by joining adjacent sentences, never by padding.
- The upstream v2.3 self-study behind Rules 6-7 compared 60 LLM documents
  with 60 human documents. Topics were not paired; the human texts were
  edited prose published before 2022; and the public repository does not
  include the reproduction corpus or scripts. Treat the figures as bounded
  evidence for the sampled models and genres.
- Rule 11 is house style (see `profiles.md`), not detection.
- Rules 12-13 require an existing evidence boundary; they never authorize
  invented names, numbers, or consequences.
- Rule 15 comes from the 2026-07 A/B check: with rules 1-14 alone, answers to
  casual Korean questions came back in lecture-register 한다체 — the ruleset's
  own prose primed the answers. The rule fixes the register mismatch the other
  rules cause.
- Deliberately excluded: burstiness/perplexity heuristics, marker-word
  blacklists, anything requiring insertion of new content.
