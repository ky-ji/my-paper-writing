# Section Playbooks

## Global Rule

Every section should answer one reviewer question.

| Section | Reviewer question |
| --- | --- |
| Abstract | What is the problem, why is it hard, what is the mechanism, and what is proven? |
| Introduction | Why must this paper exist, and why is this method the natural answer? |
| Related Work | Which assumptions in prior paradigms does this paper challenge? |
| Method | How does each design choice solve a specific bottleneck? |
| Experiments | Which claims are supported, and where might they fail? |
| Figures | What should the reader learn before reading the text? |
| Conclusion | What was resolved, and what remains bounded? |

If a section only lists content, rewrite it around the question it must answer.

## Abstract

### Purpose

Compress the whole paper into a causal chain. The abstract should not sound like a component list.

### 6-Sentence Default

1. `Capability + constraint`: state the field capability and the practical or learning bottleneck.
2. `Prior mismatch`: explain why existing methods fail structurally in this setting.
3. `Method`: introduce the method as a named mechanism or paradigm.
4. `Observation`: state the empirical, theoretical, or profiling fact that justifies the method.
5. `Designs`: describe the primary mechanism and the secondary remedy.
6. `Evidence`: report benchmarks plus paired metrics.

Use 7 sentences only when the secondary bottleneck needs its own sentence.

### Required Checks

- The first sentence contains both value and constraint.
- The method sentence uses an active mechanism verb: `reformulate`, `allocate`, `condition`, `decompose`, `reuse`, `decouple`, `supervise`, `truncate`.
- The evidence sentence reports at least one quality metric and one cost, robustness, stability, or generality metric.
- No claim appears in the abstract unless it is supported by an experiment, analysis, or figure.

### Repair Moves

- If the abstract starts too broadly, replace the first sentence with a concrete deployment, training, or evaluation bottleneck.
- If it lists modules, insert the observation that forces those modules to exist.
- If the contribution sounds incremental, add the naive failure or prior assumption before the method.
- If the final sentence only says "extensive experiments", add the actual trade-off.

## Introduction

### Purpose

Make the method feel inevitable. The Introduction should move from need to mismatch to observation to mechanism.

### 6-Paragraph Arc

1. `Need`: field value, adoption, and the concrete constraint that blocks use.
2. `Gap`: prior paradigms grouped by shared assumptions and limitations.
3. `Observation`: a diagnostic figure, profiling result, theoretical property, or failure case that changes the design space.
4. `Method`: the proposed paradigm and what workflow, assumption, or unit it changes.
5. `Mechanisms`: the primary design, then the secondary bottleneck created by applying it naively, then the remedy.
6. `Evidence`: benchmark scope, headline paired metrics, and contribution bullets.

### Paragraph-Level Details

`Need` paragraph:
- Start from a capability the community already values.
- Narrow quickly to a concrete blocker: latency, memory, noise, bias, annotation cost, instability, distribution shift, weak supervision, scalability.
- Use a number or concrete scenario when available.

`Gap` paragraph:
- Group prior work into 1-2 paradigms.
- End with the common structural mismatch, not with "few works study this".
- Prefer: `However, these methods rely on [assumption], which is mismatched with [setting].`

`Observation` paragraph:
- Mention a planned figure/table/profiling result early.
- State 1-2 observations explicitly.
- End with the design implication.

`Method` paragraph:
- Name the method only after the observation is clear.
- State the changed workflow: update-then-reuse, prune-then-reuse, sample-wise selection, rollout-adaptive allocation, objective reformulation, etc.
- Avoid dumping all modules in one long sentence.

`Mechanisms` paragraph:
- Use a two-step rhythm: `To address the first bottleneck... However... To mitigate this...`
- Make the secondary mechanism solve a real hidden failure: overhead, error propagation, weak signal, static schedule, poor gradients, memory growth.

`Evidence` paragraph:
- Report the benchmark family, hard settings, and headline numbers.
- Contributions should be 3-4 bullets: paradigm or observation, primary mechanism, secondary mechanism, experiments.

### Common Failures

- Broad first paragraph with no concrete blocker.
- Related work written as citation inventory.
- Method introduced before the observation.
- Contributions that only list modules.
- No explicit bridge from figure to method.

## Related Work

### Purpose

Position the paper by assumptions, not by citation count.

### Structure

Use 2-3 short paragraphs or named mini-sections:

1. `Background paradigm`: what the area usually does and why it works.
2. `Closest paradigm`: what the strongest related methods assume.
3. `Difference`: why those assumptions fail in this paper's setting.

### Writing Rules

- Open each paragraph with the paradigm, not an author list.
- Put citations after the claim they support.
- End each paragraph with a limitation that connects to the proposed method.
- Avoid overclaiming that no one has studied the problem. Say the existing assumption is insufficient.

### Useful Endings

- `These methods reduce [cost/error] but rely on [static/offline/local/dataset-level] assumptions.`
- `This design is effective for [setting], but it does not address [new constraint].`
- `In contrast, this work targets [constraint] by [mechanism].`

## Method

### Purpose

Turn the story into mechanisms. Each subsection should answer one bottleneck.

### Opening Roadmap

Use:

`In this section, we introduce [method], a [role] designed to [goal]. It consists of [A] and [B]. We first formulate [minimal unit], then describe [A], and finally integrate [B] into the full pipeline.`

### Recommended Order

1. `Preliminaries`: define only what is needed for the method.
2. `Problem formulation`: identify the minimal unit, decision variable, or workflow to change.
3. `Primary module`: mechanism that exploits the key observation.
4. `Failure analysis`: what breaks under the direct extension or naive version.
5. `Secondary module`: remedy that makes the primary module practical.
6. `Pipeline or algorithm`: how the pieces interact in training and inference.

### Module Subsection Template

1. `Motivation`: what bottleneck this subsection solves.
2. `Naive idea`: what direct solution would be tempting.
3. `Failure`: why the naive idea is insufficient.
4. `Mechanism`: the actual design.
5. `Formalization`: equations, algorithm, objective, or implementation.
6. `Advantage`: what this design changes and which ablation will verify it.

### Equation Rules

- Explain why a quantity matters before defining it.
- Use equations to formalize decisions, objectives, or error mechanisms, not to decorate.
- After an equation, state its role in plain language.
- Keep notation stable across sections.

### Algorithm And Pipeline Rules

- Use algorithms for stateful, iterative, or decision-heavy procedures.
- Use pipeline figures for system coordination, module interaction, or runtime flow.
- Captions should state what the pipeline solves, not only what components exist.

## Experiments

### Purpose

Prove the claims in the same order the paper makes them.

### Opening Paragraph

Use:

`We first describe benchmarks, baselines, metrics, and implementation. We then evaluate [main claim], ablate [modules], and visualize [internal behavior].`

### Setup

Split setup into short bold paragraphs when possible:

- `Benchmarks`: datasets, tasks, domains, difficulty levels.
- `Baselines`: dense/full model, strongest prior methods, simple variants.
- `Metrics`: quality plus cost, robustness, stability, generality, or interpretability.
- `Implementation`: hardware, key hyperparameters, training budget, inference setting.

### Result Order

1. `Main trade-off`: quality vs cost or robustness vs efficiency.
2. `Hard cases`: extreme noise, long-horizon tasks, real-world deployment, large models, shifted data.
3. `Generality`: additional models, samplers, datasets, or settings.
4. `Ablations`: one table or paragraph per mechanism.
5. `Internal behavior`: qualitative visualization, profiling, learned patterns, error analysis.
6. `Failure or limitation`: bounded cases if important for reviewer trust.

### Result Paragraph Template

`[Method] achieves [headline result] under [setting]. Compared with [baseline], it [specific improvement]. This gain is most visible in [hard case]. We attribute the improvement to [mechanism], which [causal explanation].`

### Table And Figure Rules

- Put the takeaway in the caption.
- Do not narrate every number.
- Report the strongest comparison, hard-case behavior, and mechanism attribution.
- If a method is faster but worse, name the trade-off directly.

## Figures And Captions

### Figure Roles

- `Observation figure`: proves the gap or motivates the method.
- `Framework figure`: shows how the method changes the workflow.
- `Result figure/table`: proves the main trade-off.
- `Ablation figure/table`: isolates a mechanism.
- `Diagnostic figure`: explains why the method works or fails.

### Caption Template

`[Takeaway]. [Setting]. [Observed pattern]. [Implication for the method].`

Avoid captions that only say `Results on different tasks`.

## Conclusion

### Purpose

Close the paper by restating the resolved bottleneck and the mechanisms, not by introducing new claims.

### 3-Sentence Default

1. Re-state the practical or learning bottleneck.
2. Summarize the primary and secondary mechanisms.
3. Report the final evidence and bounded takeaway.

If the venue requires ethics, limitations, or reproducibility, keep them factual and scoped.
