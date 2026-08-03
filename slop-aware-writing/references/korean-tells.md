# Korean Sentence-Level Patterns (한국어 문장 단위 패턴)

Load this evidence ledger only when a Korean-specific slop candidate survives
the common diagnosis. It is not a Korean grammar syllabus or a required
sentence-by-sentence scan. Use the model's ordinary Korean fluency for an
obvious local correction, then use only the relevant pattern family here to
test whether a repeated form is a slop defect, valid Korean, or the writer's
voice.

Pattern IDs stay aligned with upstream `epoko77-ai/im-not-ai`
`humanize-korean`. Inspected 2026-07-31:
upstream `main` was `53e24e8`, and v2.3.0 points to `82137e8`. Changes after
the tag affect social-preview assets and their build script, not the writing
taxonomy used here. Quarterly maintenance: diff upstream
`references/ai-tell-taxonomy.md` and `empirical-validation.md` against this
file and carry over only ID-level changes.

Every rule carries an evidence ledger tag:

- `[AI]` group-level difference measured in an inspectable external study;
  never proof from one span or one document
- `[self]` upstream self-study without a public corpus or reproduction scripts
- `[KO]` Korean style or translation-ese evidence. Kim Jeong-woo's
  ["The Reality of Translationese in Modern Korean"](https://www.korean.go.kr/nkview/nklife/2012_1/22_0104.pdf)
  and Kim Sun-young's
  ["Translationese Sentences in English-Korean Translation"](https://www.korean.go.kr/nkview/nklife/2012_1/22_0105.pdf)
  document recurring translation patterns and context-sensitive alternatives;
  they do not establish universal bans or AI authorship
- `[obs]` observation-only diagnostic; never a rewrite instruction

Severity is review order, not a quality score: S1 = check first; one occurrence
may merit a style review but never an authorship inference. S2 = fix when
repeated (3+ or clustered); S3 = adjust only when stacked with other problems.
Never traverse every ID merely because the text is Korean, and never grade a
document by pattern counts or change ratio.

Upstream's v2.3 self-study compared 60 LLM documents with 60 human documents.
The topics were not paired, and the human side consisted of edited prose
published before 2022. The public repository records the method and results
but does not include the reproduction corpus or scripts. Treat its figures as
bounded evidence for those models and genres, not universal human/AI rates.

## Contents

- [Do-NOT list](#do-not-list) · [Measured priorities](#measured-priorities)
- [A 번역투](#a-번역투-s1s2) · [B 영어 인용](#b-영어-인용-s2) ·
  [C 구조](#c-구조-패턴) · [D 관용구](#d-ai-관용구-s1) ·
  [E 리듬](#e-리듬-s2) · [F 수식](#f-수식-중복-s2) ·
  [G hedging](#g-hedging-s2) · [H 접속사](#h-접속사-s1s2) ·
  [I 형식명사](#i-형식명사-s1s2)
- [Observation-only diagnostics](#observation-only-diagnostics)
- [Rewrite examples](#rewrite-examples) · [Self-check](#self-check)

## Do-NOT list

Never touch: code blocks, commands, file paths, URLs, API fields, environment
variables, numbers, dates, versions, direct quotations, standard English
acronyms (`HTTP`, `JSON`, `API`, `LLM`, `SDK`, `MCP`, `GPU`), proper nouns,
product and model names. House-style rules (em-dash prohibition, workplace
slang) live in `profiles.md`, not here.

## Measured priorities

Check these four early. The tags and limits determine how far each finding can
travel.

| ID | Pattern | Evidence |
|---|---|---|
| C-8 | 부정 대구 "A가 아니라 B", "A인가 B인가" | `[self]` upstream reports 9.2× vs published prose, 18× vs blogs, G²=41.7 across 3 model families. Use only as a bounded review priority and apply the keep test below. |
| C-11 | 연결어미(-고/-며/-지만/-면서/-아서/-어서) 뒤 쉼표 | `[AI]` KatFish essay-level group rate: human 4.10% vs LLM 19.83%. This is not a single-span threshold. Under the Korean style baseline, remove an unnecessary comma but preserve quoted text and meaning-bearing punctuation. The 94.88% AUC belongs to the complete punctuation feature set. |
| E-5/C-12 | 문장당 쉼표 과다 | `[self]` upstream reports AI 1.5× (G²=25.5). Treat repetition as a review cue; split a long clause only when meaning survives. |
| E-1' | 장문 결핍 (100자+ 문장 부재) | `[self]` upstream reports an 11× deficit (G²=60.9). If rhythm is genuinely monotonous, join adjacent sentences without adding content. |

C-8 판정 테스트: 부정절을 지웠을 때 주장이 그대로 남으면 수사적 대구다 —
지운다. 부정절을 지우면 무엇을 바로잡는 말인지 사라지면 재정의 문장이다 —
보존한다("X는 형식이 아니라 정책이다"처럼 기존 통념을 정정하는 진술). 측정
근거는 논설·블로그 산문 기준이라, 정의를 다시 세우는 기술 문서에서는 같은
표면형이 정보를 나른다. 재정의라도 같은 몰드가 3회 이상 반복되면 일부는
결론형으로 바꿔 몰드를 흩는다.

## A. 번역투 (S1~S2)

All `[KO]` unless noted. They are contextual revision cues, not a promise that
applying every row improves every Korean document.

| ID | Pattern | Sev | Fix |
|---|---|---|---|
| A-1 | "~에 대해(서)" | S1 | 목적격 직결: "X에 대해 설명" → "X를 설명" |
| A-2 | "~를 통해" 남발 | S2 | `[KO][self]` **조건화(2026-07 기각 반영)**: 문서 내 반복(3회+)만 억제, 1~2회는 보존. 상류 표본에서 사람이 LLM보다 2배 더 쓴다 — AI-tell 아님 |
| A-3 | "~에 있어(서)" | S1 | "~에서", "~을 볼 때" |
| A-7 | "가지고 있다", have/make/take 직역 | S1 | 형용사·동사 환원: "강점을 가지고 있다" → "강점이 있다" |
| A-8 | 이중 피동 "되어진다" | S1 | 단일 피동 또는 능동 |
| A-9 | "~에 의해" 피동 | S2 | 행위자를 주어로: "AI에 의해 생성" → "AI가 만든" |
| A-10 | "~할 수 있다" 남발 | S2 | 검증된 절차를 불필요하게 가능형으로 완곡한 경우에만 평서·명령형으로 바꾼다. 실제 능력, 허용, 가능성, 불확실성은 보존 |
| A-12 | "이루어지다/만들어지다" | S2 | 능동: "합의가 이루어졌다" → "합의했다" |
| A-13 | 명사 나열(조사 생략) | S2 | 조사 복원 |
| A-15 | 추상 주어 + 만능 동사("X가 Y를 보여준다") | S2 | 행위자 주어로 환원, 인지 동사는 "~에 따르면"으로 분리 |
| A-16 | 대명사 직역(그/그녀/그것/그들) | S1 | `[KO][self]` **번역 맥락 한정** — 영어 원문이 있는 글에서만 발동. 자생 한국어 산문에서는 발동 금지(상류 표본에서 사람 1.9 vs LLM 0.0/1000어절) |
| A-18 | 긴 좌향 관형절 중첩 | S2 | 문장 분리 또는 후치 동격절 |
| A-19 | 이중 조사("~에서의/~으로의") | S2 | 절로 풀기 |

A-4~A-6, A-11, A-14: 반복될 때만 같은 원리로 처리(상세는 upstream taxonomy).
A-17('-들' 기계 부착)은 upstream이 hold — 탐지 보조로만.

## B. 영어 인용 (S2)

- B-1: 괄호 영어 병기는 첫 등장만, 이후 한글만.
- B-2: 인용부호 안이나 본문에 들어간 영어는 문서의 언어, 하우스 스타일,
  독자의 이해를 해칠 때만 고친다. 직역 가능한 영어(`leverage`, `seamless`,
  `robust`)는 한국어를 검토하고 독자가 더 익숙한 업계 표준어(`pipeline`,
  `endpoint`, `runtime`)는 유지한다. 한 문서에서는 영/한 표기를 통일한다.

## C. 구조 패턴

- C-1 기계적 열거(S2): **논설·에세이 장르에서만 AI 신호**. 학술·매뉴얼·설명문의
  열거는 정상 — 기본 보존.
- C-4 문단 첫 문장 요약 공식(S2): 일부 문단을 사례·수치·질문으로 시작.
- C-5 이모지(S1): 기술 문서면 전부 삭제.
- C-7 "먼저/반면/결국" 3단 공식(S2): 접속사를 줄이거나 본문에 녹인다.
- C-8, C-11: [Measured priorities](#measured-priorities) 참조.
- C-9 숫자 괄호 인덱싱 "(1)(2)(3)"(S2): 본문에 녹이거나 줄바꿈.
- C-10 콜론 부제 헤딩 "X: Y" 반복(S2): 평서 헤딩으로.

문서 구조 단위 장황함(헤딩·표 인플레이션, 자기 설명 도입부 등)은
`structure-anti-patterns.md`가 정본이다.

## D. AI 관용구 (S1)

Delete-only category — **removal only, never insert** replacement clichés.

- D-1 결산 피벗("결론적으로", "정리하면", "이를 통해"): 논리를 더하지 않으면 삭제.
- D-2 "시사하는 바가 크다", "주목할 만하다": 삭제 또는 구체 결론.
- D-3 "본질적으로", "핵심적으로": 삭제. 열거 도입("크게 세 가지로") 도 삭제 후 바로 항목.
- D-4 hype 어휘(혁신적, 획기적, 강력한, 압도적): 근거가 있으면 구체 사실로, 없으면 삭제.
- D-5 의인화 추상 주어("기술이 묻는다"): 사람·기관 주어로.
- D-6 결말 공식("~할 때다"): 평서로 닫거나 삭제.

## E. 리듬 (S2)

- E-1' 장문 결핍: [Measured priorities](#measured-priorities). 인접한 짧은 문장을
  연결어미("-며/-고/-는데")로 잇는다. 내용을 지어내지 않는다.
- E-2 동일 종결어미 연속 + "~한다" 편중 `[self]` (upstream: 1.8×, G²=9.5): 3문장 이상
  같은 어미가 이어지면 명사 종결·단문을 섞는다. "~고 있다"는 단순 시제로
  환원 가능하면 환원.
- E-3 문단 길이 균일: 1문장 문단과 긴 문단을 의도적으로 섞는다.
- E-4 단문 일변도: 인접 단문을 복문화. 단문은 강조에만.
- E-7 경어법 혼용: 한 문서 한 격식. 기존 문서가 존댓말이면 유지.

## F. 수식 중복 (S2)

정도부사("매우/정말"), 동의어 이중 수식("중요하고 핵심적인"), "-성/-적/-화"
누적, "~적 N" 추상 체인 — 하나만 남기거나 동사·형용사로 푼다.

## G. Hedging (S2)

"~것이다" 미래 단정, "~로 보인다" 추정, 안전 균형("양쪽 모두", "신중하게")은
**명세·정의 섹션에서만** 강하게 적용한다. 가이드·추천 섹션의 humble 표현
("참고해보시면 좋을 것 같습니다")은 사람 글의 특징이므로 보존한다.

## H. 접속사 (S1~S2)

문두 접속사("또한/따라서/즉/나아가") 반복은 논리를 더하지 않으면 삭제(S1).
"하지만/그러나"가 문단마다 나오면 절반 이상 삭제(S2). 메타 진입("이는/이
점에서") 반복은 본문에 녹인다(S1).

## I. 형식명사 (S1~S2)

- I-1 "~것이다" 결말 `[KO][self]`: **조건화(2026-07 기각 반영)** — 연속 3회+ 남발일 때만
  일부 평서화. 상류 표본에서 사람이 LLM보다 2배 더 쓴다(LLM 20.4 vs 사람 43.0/1000문장) —
  AI-tell 아님.
- I-2 "X는 ~라는 점에 있다"(S2): "X는 ~다" 직설로.
- I-4 권고형 결말 기계 반복(S2): 의무 조건은 보존, 설명문은 평서로.
- I-5 "~이 필요하다"(주체 모호, S2): 주어와 동사로 구체화.

## Observation-only diagnostics

`[obs]` marks look-closer cues only. Report the wording problem, never infer
authorship or fabricate a fix:

- `[self][obs]` 직접 인용 결핍 (upstream: LLM 0.0 vs 인간 8.7/1k,
  G²=96.4) — 없는 인용을 만들지 않는다
- `[self][obs]` 괄호 결핍 (upstream: G²=69.5) — 장식 괄호를
  삽입하지 않는다
- `[self][obs]` 과거형 회피 (잠정, 장르 교란 가능)
- `[AI][obs]` 띄어쓰기 특징군 (KatFishNet 에세이 평균 AUC 79.51%) — 단일 규칙의
  성능이 아니며 일부러 틀린 띄어쓰기를 추가하지 않는다

## Rewrite examples

```diff
- 데이터를 정제하고, 모델을 학습시킨 다음, 결과를 검증합니다.        (C-11)
+ 데이터를 정제하고 모델을 학습시킨 다음 결과를 검증합니다.

- 경쟁력을 가지고 있다                                               (A-7)
+ 경쟁력이 있다

- **결론적으로**, ADK는 도구 루프를 자동화합니다.                     (D-1)
+ ADK는 도구 루프를 자동화합니다.
```

## Self-check

After editing: (1) 불변 정보 보존 — 명령어·경로·수치·인용·조건을 원문과 대조,
(2) 각 수정의 의미 보존을 diff로 입증, (3) 장르·격식 유지, (4) 저장소 용어
일관성, (5) 새 사실·비유·예시를 추가하지 않았는지, (6) AI slop 수정이 일반
맞춤법 검사로 번지지 않았는지. 위반한 수정은 되돌린다.
