# Section Playbooks

## Abstract

Use 5-7 sentences. Keep the abstract causal and compressed.

Template:

1. Field value plus bottleneck.
2. Existing methods and structural limitation.
3. Proposed method and core goal.
4. Key observation or paradigm.
5. First design that operationalizes the insight.
6. Second design that resolves the remaining bottleneck.
7. Experimental result with performance-efficiency pair.

Checklist:

- Does sentence 1 contain both value and pain?
- Does sentence 2 explain why current methods fail, not just that they fail?
- Does the method name arrive after the gap is clear?
- Are module names connected to their jobs?
- Does the final sentence include benchmark scope and numbers?

## Introduction

Use the Kangye six-move structure:

1. Importance and real constraint.
2. Prior work categories and shared failure.
3. Observation figure and central insight.
4. Proposed method and main mechanism.
5. Secondary bottleneck and remedy.
6. Evaluation scope and contribution bullets.

Paragraph roles:

- `Opening`: field value, adoption, real deployment bottleneck, number.
- `Gap`: existing methods grouped by paradigm, with a structural mismatch.
- `Insight`: observation, figure, why it changes the design space.
- `Method`: method name, high-level mechanism, how it departs from prior workflow.
- `Design`: specific bottlenecks and modules.
- `Evidence`: benchmark scope, headline numbers, contribution list.

Contribution bullets:

- Bullet 1: method or paradigm.
- Bullet 2: first key mechanism or observation.
- Bullet 3: second key mechanism, theory, or analysis.
- Bullet 4: experiments, speed/accuracy/memory scope.

Use 3 bullets when the method has one central design plus evidence. Use 4 bullets when there are two substantial technical designs.

## Related Work

Do not write a survey. Write a positioning argument.

Paragraph template:

`[Area]. Existing methods fall into [categories]. [Category A] does [benefit] but [limitation]. [Category B] does [benefit] but [limitation]. These limitations motivate [the axis your method changes].`

End each paragraph with the gap your method exploits:

- computational overhead
- static schedule
- missing rollout-level adaptation
- coarse granularity
- dataset-wise cost
- weak disagreement
- image-specific assumptions

## Method

Begin with a roadmap:

`In this section, we introduce [method], a [role] designed to [goal]. [Method] consists of [module A] and [module B]. We first [preliminaries/formulation], then [module A], and finally [module B/pipeline].`

Preferred method subsection pattern:

1. Motivation or question.
2. Naive solution and why it fails.
3. Proposed mechanism.
4. Formal definition or algorithm.
5. Practical advantage.
6. Link to figure, algorithm, or ablation.

Use preliminaries when they help the reader understand the minimal unit of action:

- rollout-level, denoising-level, block-level.
- model update, sample selection, error flow.
- update step vs reuse step.
- computation unit, cache, mask, schedule.

Use theory sparingly but decisively. A proposition should explain a failure mode or justify a design choice.

## Experiments

Open with a roadmap:

`We first outline the experimental setup, covering [benchmarks], [baselines], [metrics], and [implementation]. Following that, we evaluate [main claim]. We then present ablations of [key modules]. Finally, we provide qualitative analysis of [internal behavior].`

Experimental setup order:

1. Benchmarks and task types.
2. Baselines and why they are fair.
3. Metrics, including both quality and efficiency.
4. Implementation details that affect reproducibility.

Main results should be claim-driven:

- Effectiveness: Does it match or improve the full model?
- Efficiency: Does it reduce latency/FLOPs/memory or increase throughput?
- Hard cases: Where do baselines fail and your method remains stable?
- Generality: Does it work across samplers, models, datasets, noise types, real-world settings, or VLA models?

Ablations should map one-to-one to modules. Do not include an ablation without saying which claim it tests.

## Figure Captions

Captions should teach the claim.

Pattern:

`[Bold takeaway or object]. [Experimental setting]. [What the reader should observe]. [Why it supports the method].`

Examples of caption jobs:

- show fixed schedules fail across rollout iterations.
- show similarities vary by timestep and block.
- show error surge and its source.
- show pipeline reduces non-decoder latency.
- show predicted sparsity changes with rollout dynamics.

Avoid captions that only name the plot.

## Conclusion

Keep the conclusion compact.

Template:

`[Real constraint or problem] motivates [method class]. In this work, we propose [method]. [Method] addresses [problem] through [design 1] and [design 2]. Extensive experiments show [headline result] under [scope].`

Do not introduce new evidence or claims.
