# Paper Writing Rules

## Core Orientation
- Write for fast comprehension.
- Define the problem before the method.
- Tie every methodological choice to a concrete challenge.
- Prefer standard words and common sentence patterns over decorative language.
- Keep claims measurable, supportable, and academically precise.
- If the source material is rough Chinese or weak English, recover the intended meaning first and then rewrite into natural academic English.
- Make wording-level assumptions only when they do not change the scientific meaning. If the scientific task, setting, comparison target, or intended claim is unclear, ask one concise clarification question before drafting.

## Default Logic Chain
1. State the practical problem and why it matters in transportation or operations.
2. State what existing studies usually assume, observe, or optimize.
3. Explain why that assumption fails in the current setting.
4. State the resulting technical challenge.
5. Introduce the method with a targeted sentence such as `To address this challenge, we propose ...`.
6. Explain the mechanism with `Specifically` and two to four concrete steps.
7. State what the method outputs and how it is validated.

## Distilled Writing Habits
- Use contrast early with `However`, `In contrast`, or `More importantly` only when the contrast is real.
- Use problem-driven connectors instead of rhetorical filler.
- Use `First`, `Second`, and `Moreover` only when the list is real and finite.
- Let each paragraph do one job: problem, gap, method, mechanism, evidence, or implication.
- Keep the subject concrete. Name the data, network, task, decision, or traffic phenomenon directly.
- Replace vague praise with mechanism. Write what the model does, not that it is `advanced` or `powerful`.
- Allow moderately formal and information-dense phrasing when it carries real technical meaning. Do not flatten named mechanisms, decision layers, or structural components just to sound simpler.

## Section Rules

### Abstract
- Follow five moves in order:
  1. problem importance
  2. gap in existing studies
  3. challenge in this setting
  4. proposed method and key mechanism
  5. result or practical implication
- Mention the transportation setting explicitly.
- Mention domain knowledge, structural priors, or physical constraints if they are central to the contribution.

### Introduction
- Start from the application problem, not from a generic trend in AI.
- Separate `why the problem matters` from `why the problem is hard`.
- Distinguish the current setting from nearby tasks when needed, such as:
  - imputation vs estimation
  - short-term vs long-term forecasting
  - fixed-time vs adaptive control
  - homogeneous vs heterogeneous tasks
- When clarifying novelty, use perspective-based contrast:
  - problem perspective
  - methodological perspective
  - practical or deployment perspective
- End the gap discussion with a targeted method sentence, not a vague promise.

### Related Work Or Literature Review
- Organize the literature by problem type, methodological family, data setting, or limitation category rather than by publication year.
- Avoid paragraph structures that only list `X et al. did Y`.
- Let each paragraph end with a clear synthesis, such as the common limitation of the reviewed stream or the remaining gap addressed by the present study.
- Distinguish closely related tasks when that distinction is necessary for your contribution, for example estimation versus prediction, or fixed-time versus adaptive control.
- Keep the review selective and argumentative rather than exhaustive and chronological.

### Contribution Paragraph
- Use two to four clearly sequenced contributions.
- Make each contribution contain:
  - the artifact: model, theorem, algorithm, dataset, or experiment
  - the purpose: which challenge it addresses
  - the payoff: which capability it enables
- Avoid saying `novel` unless the specific difference is named immediately after it.
- When defensible, it is acceptable to position the contribution through transportation-domain fit rather than algorithmic novelty alone, for example by clarifying that the primary contribution lies in the transportation domain.

### Method Section
- Define inputs, outputs, and decision objects early.
- Explain why each module exists before giving equations or algorithm steps.
- Connect model constraints or priors to transportation or OR mechanisms.
- For OR papers, separate objective, constraints, and solution method clearly.
- For AI papers, specify what structural prior, physical rule, graph relation, or spatiotemporal dependency is encoded.
- When the method has multiple layers or mechanisms, name them explicitly and sequence them clearly, for example `implicit structural priors`, `explicit structural priors`, or `two key decisions`.

### Experiment And Discussion
- Report what improves, under what condition, and why.
- Connect improvements back to the mechanism instead of repeating benchmark numbers only.
- Explain limitations objectively when they appear.
- Prefer `These results suggest ...` over overstated certainty when causal proof is limited.

### Figure And Table Description
- Write captions that identify the object, setting, and purpose of the figure or table.
- In the main text, explain what the reader should notice instead of repeating every number or label.
- For figures, highlight the trend, comparison, or mechanism shown by the visual.
- For tables, summarize the most important comparison and note the condition under which it matters.
- Keep descriptions aligned with the argument of the paragraph.
- Useful caption pattern for figures:
  - `Figure X. [What is shown] for [setting or data]. [What the reader should notice].`
- Useful caption pattern for tables:
  - `Table X. [Comparison target] under [conditions]. Bold indicates [criterion].`

### Conclusion
- Restate the problem, the core mechanism, and the validated takeaway.
- Do not repeat the abstract verbatim.
- Mention limitations or future work only when they follow naturally from the study.

## Transportation And OR Framing
- Ground motivation in transportation operations, traffic mechanisms, planning decisions, or deployment constraints.
- If the work uses AI, explain how domain knowledge or structural information is embedded.
- If the work uses OR, make the decision structure and operational tradeoffs explicit.
- Distinguish the target problem from nearby benchmark tasks when that difference supports the contribution.

## Language Preferences
- Prefer common verbs such as `use`, `show`, `estimate`, `identify`, `improve`, `compare`, and `explain`.
- Prefer short declarative clauses when possible.
- Use technical terms when needed, but avoid stacking multiple adjectives before a noun.
- Avoid empty phrases such as `cutting-edge`, `remarkable performance`, or `highly innovative` unless evidence is immediately provided.
- Avoid broad impact claims that are not supported by the study.
- Controlled self-positioning is acceptable only when it is clearly supported by the manuscript context or the user explicitly wants stronger positioning, such as `To the best of our knowledge`, `the first study`, `significantly improves`, or `accurate and robust`. Otherwise prefer neutral wording.

## Reusable Patterns
- Problem and gap:
  - `[Task] is important for [application]. However, existing studies mainly [limitation]. This issue becomes more critical when [setting-specific difficulty].`
- Challenge to method:
  - `To address this challenge, we propose [method], which [core action] by [key mechanism].`
- Mechanism naming:
  - `Specifically, the proposed framework incorporates [mechanism 1], [mechanism 2], and [mechanism 3] to address [sub-challenges].`
- Mechanism unpacking:
  - `Specifically, the proposed approach operates in three steps. First, ... Second, ... Finally, ...`
- Setting contrast:
  - `In contrast to [nearby task], our setting assumes [key difference], which implies that [resulting challenge].`
- Result sentence:
  - `Experiments on [data or instances] show that the proposed approach [main finding], especially when [condition].`

## Mini Example
Input intent:
- Write one literature-review paragraph on sensor-free traffic flow estimation.

Output pattern:
- `Existing studies on traffic flow estimation mainly rely on sensor-equipped networks, where spatiotemporal dependencies can be learned from observations collected across all links. In contrast, traffic flow estimation on sensor-free roads involves persistent missing observations on a subset of links, which makes spatial generalization a central challenge. Although several data-driven methods have shown strong performance in related tasks such as data imputation and traffic prediction, their assumptions do not directly fit this setting. This gap motivates methods that can infer network-wide traffic patterns under partial observability.`

## Paste-Ready Default
- Return final manuscript prose, not commentary, unless the user explicitly asks for an outline or explanation.
- If information is missing, write conservatively and do not invent results, data properties, theorem statements, or implementation details.
