# Sentence Revision Rules

## Purpose
- Help a student turn a Chinese or English draft sentence or short paragraph into several publication-ready English options.
- Teach by comparison: explain the main issue briefly, then provide multiple usable rewrites.

## Default Behavior
- Assume the target output is English academic writing unless the user asks otherwise.
- If the source is Chinese, identify the intended technical meaning first, then rewrite instead of translating word by word.
- If the source is English, diagnose the main weakness before rewriting.
- Default to `3` to `5` candidate versions.
- Match the short explanatory wrapper to the user's input language when practical.

## What To Diagnose
- Is the sentence trying to define a problem, describe a challenge, introduce a method, explain a mechanism, report a result, or respond to a reviewer?
- Is the main issue clarity, logic, grammar, tone, precision, redundancy, or mismatch with transportation research style?
- Is the sentence too vague about the object, setting, or mechanism?
- Does it use inflated wording where a common expression would be better?

## Function Routing
Before rewriting, assign the input to the closest function:

- `Background or motivation`
- `Problem definition`
- `Research gap or challenge`
- `Transition or connection sentence`
- `Method overview`
- `Mechanism or technical detail`
- `Comparison with baselines`
- `Result or implication`
- `Limitation statement`
- `Future work`
- `Contribution claim`

If the sentence mixes two functions, choose the dominant one and keep the rewrite focused on that single job.

## Route Out Of This Mode
- Follow the routing rules in [SKILL.md](../SKILL.md). This file assumes the request has already been routed into sentence revision mode.

## Output Format
Use this structure by default for student requests:

`Sentence function:` one short Chinese phrase

`Main issue:` one short Chinese sentence

`Version 1:` the most direct and standard English rewrite

`Version 2:` a slightly more formal English rewrite

`Version 3:` an English rewrite with stronger logic, mechanism, or transportation framing

`Difference:` one short Chinese note comparing the versions

`Recommended version:` one short Chinese sentence stating which version should be used by default and why

Add `Version 4` or `Version 5` only when the user asks for more options or the sentence is important enough to justify them.

## Stable Template
Use the following template by default unless the user explicitly requests another format:

`Sentence function:` ...

`Main issue:` ...

`Version 1:` ...

`Version 2:` ...

`Version 3:` ...

`Difference:` ...

`Recommended version:` ...

When useful, add the detected function in Chinese after `Sentence function`.

If the input language is English-only, the wrapper labels and explanations may also be given in English.

## Function-Specific Templates

### Background Or Motivation
- Goal: explain why the topic matters in transportation, OR, or AI-for-transportation.
- Emphasis:
  - `Version 1`: direct and standard importance statement
  - `Version 2`: smoother and slightly more formal motivation
  - `Version 3`: stronger transportation context or operational relevance
- Avoid generic trend language unless it helps define the application.

### Problem Definition
- Goal: state the exact task, object, setting, or decision clearly.
- Emphasis:
  - define what is estimated, predicted, optimized, detected, or inferred
  - name the data, network, control setting, or task object when known
  - avoid mixing the problem with the solution

### Research Gap Or Challenge
- Goal: contrast the current setting with existing studies and explain why the limitation matters.
- Emphasis:
  - `Version 1`: standard contrast with `However`
  - `Version 2`: clearer logic on why existing assumptions fail
  - `Version 3`: stronger setting-specific challenge in transportation context
- Prefer concrete limitation statements over generic claims of insufficiency.

### Method Overview
- Goal: introduce the method as a targeted response to the challenge.
- Emphasis:
  - connect the method to the challenge with a causal link
  - use patterns such as `To address this challenge, we propose ...`
  - make the core action and core mechanism visible in one sentence

### Transition Or Connection Sentence
- Goal: connect the previous point to the next paragraph or argument step smoothly.
- Emphasis:
  - keep the logical bridge explicit
  - avoid repeating the previous sentence mechanically
  - signal why the next discussion is needed

### Mechanism Or Technical Detail
- Goal: explain how the method works.
- Emphasis:
  - make the mechanism explicit, not just the module name
  - use `Specifically` when listing steps or components
  - connect priors, constraints, graph structure, or optimization decisions to the modeled phenomenon

### Result Or Implication
- Goal: report what the results show and why that matters.
- Emphasis:
  - `Version 1`: direct empirical finding
  - `Version 2`: more cautious interpretation
  - `Version 3`: stronger mechanism-based explanation or practical implication
- Avoid overclaiming certainty when the evidence is empirical only.

### Comparison With Baselines
- Goal: state how the proposed method compares with benchmark or baseline methods.
- Emphasis:
  - identify the comparison target
  - say what improves and under what condition
  - avoid vague superiority claims without a comparison object

### Limitation Statement
- Goal: state a real limitation without weakening the paper unnecessarily.
- Emphasis:
  - define the limitation precisely
  - explain its scope
  - keep the tone objective and non-defensive

### Future Work
- Goal: state a concrete next step that follows naturally from the current limitation or scope.
- Emphasis:
  - connect future work to a specific unresolved issue
  - avoid generic promises
  - keep the sentence compatible with conclusion or rebuttal contexts

### Contribution Claim
- Goal: state the contribution in a bounded and defensible way.
- Emphasis:
  - identify the artifact, purpose, and payoff
  - avoid saying only `novel` or `innovative`
  - separate problem, methodological, and practical contributions when useful

## Revision Principles
- Keep the core meaning unchanged unless the original meaning is clearly flawed or incomplete.
- Prefer common academic verbs and nouns.
- Remove repeated qualifiers and weak filler.
- Make the sentence self-contained enough for manuscript use.
- If the sentence refers to a specific transportation task, name it directly.
- If the sentence introduces a challenge, state why the challenge occurs.
- If the sentence introduces a method, connect the method to the challenge with a direct causal link.

## Useful Differentiation Across Versions
- `Version 1`: safest journal style; best default choice
- `Version 2`: more formal or smoother
- `Version 3`: stronger on logic, mechanism, or domain framing
- `Version 4`: shorter and tighter, if brevity matters
- `Version 5`: more persuasive, if the user is writing an introduction or rebuttal

## Chinese Input Handling
- Recover the intended meaning before drafting.
- Do not mirror Chinese syntax.
- Replace broad phrases such as `important`, `works very well`, or `highly innovative` with concrete academic content.
- When the Chinese sentence is only a fragment or note, complete it into a full English sentence if the intent is clear.
- Ask one concise clarification question instead of guessing when the scientific task, target object, setting, intended claim, or technical meaning is ambiguous.

## English Input Handling
- Fix grammar, but do not stop at grammar.
- Improve logic, subject clarity, and academic tone at the same time.
- If the sentence is already correct but weak, show stronger alternatives rather than only making tiny edits.
- If the sentence contains multiple problems, prioritize clarity first, then logic, then style.

## Transportation Research Preferences
- Use domain nouns such as `traffic flow`, `origin-destination demand`, `signal timing`, `road network`, `fleet configuration`, or `shockwave propagation` when they fit the context.
- Distinguish nearby tasks when needed, such as `estimation` versus `prediction`, or `fixed-time` versus `adaptive`.
- Tie methodological language to transportation mechanisms or OR decisions when possible.
- For gap, method, and result sentences, make the setting-specific transportation constraint visible whenever possible.

## Reusable Prompting Patterns
- `Rewrite this Chinese sentence into 3 paper-ready English versions.`
- `Polish this English sentence and give me 4 alternatives with different emphasis.`
- `Tell me how to revise this sentence for a transportation journal and provide several options.`

## Mini Examples

Note:
- The wrapper language in these examples follows the input language. For Chinese input, keep labels and brief explanations in Chinese by default. For English-only input, English wrappers are also acceptable.

### Example 1
Input:
`现有方法大多依赖完整传感器覆盖，因此难以处理无传感器路段的交通流估计。`

Output:
`Sentence function:` 研究空白

`Main issue:` 这句话需要更清楚地说明现有方法的基本假设、该假设为何失效，以及当前设定为何更难。

`Version 1:` Existing methods typically rely on complete sensor coverage and therefore are not well suited to traffic flow estimation on sensor-free roads.

`Version 2:` However, most existing methods assume full sensor coverage, which limits their applicability to traffic flow estimation on roads without sensors.

`Version 3:` In contrast to conventional settings with full sensor coverage, our problem involves sensor-free roads, where existing methods struggle to estimate traffic flow accurately because the relevant spatiotemporal information is only partially observed.

`Difference:` Version 1 最直接。Version 2 更像标准的 gap 句。Version 3 更清楚地强调了 setting-specific challenge。

`Recommended version:` 推荐 Version 3，因为它把假设失效和由此产生的困难都讲清楚了。

### Example 2
Input:
`Most existing methods rely on complete sensor coverage and therefore are not suitable for traffic flow estimation on sensor-free roads.`

Output:
`Sentence function:` research gap

`Main issue:` The sentence needs a clearer statement of the prevailing assumption, why it fails, and why the current setting is difficult.

`Version 1:` Existing methods typically rely on complete sensor coverage and therefore are not well suited to traffic flow estimation on sensor-free roads.

`Version 2:` However, most existing methods assume full sensor coverage, which limits their applicability to traffic flow estimation on roads without sensors.

`Version 3:` In contrast to conventional settings with full sensor coverage, our problem involves sensor-free roads, where existing methods struggle to estimate traffic flow accurately because the relevant spatiotemporal information is only partially observed.

`Difference:` Version 1 is the most direct. Version 2 sounds more like a standard gap sentence. Version 3 emphasizes the setting-specific challenge more clearly.

`Recommended version:` Version 3, because it makes the assumption failure and the resulting challenge explicit.

### Example 3
Input:
`This method works well.`

Output:
`Sentence function:` result or implication

`Main issue:` The sentence is too vague because it does not say compared with what or in what sense the method performs well.

`Version 1:` The proposed method achieves higher estimation accuracy than the baseline methods.

`Version 2:` The proposed method consistently outperforms the baseline methods in estimation accuracy across all test settings.

`Version 3:` Experimental results show that the proposed method consistently improves estimation accuracy over the baseline methods, especially under sparse-observation settings.

`Difference:` Version 1 is the safest. Version 2 is stronger and more general. Version 3 adds an explicit experimental condition and context.

`Recommended version:` Version 3, because it is specific enough for manuscript use without overstating the claim.

## Do Not
- Do not provide only one polished version unless the user explicitly asks for one.
- Do not over-explain grammar in textbook style.
- Do not produce multiple versions that differ only by one or two words.
- Do not exaggerate the claim beyond what the original sentence supports.
- Do not omit `Recommended version` in the default student-facing format.
- Do not answer an actual reviewer comment in this mode unless the user explicitly asks for sentence-level alternatives only.
