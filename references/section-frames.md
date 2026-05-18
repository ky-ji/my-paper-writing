# Section Frames

## Abstract Frame

Use 5-7 sentences:

1. Field value and practical bottleneck.
2. Why existing methods fail structurally.
3. Proposed method and core paradigm.
4. Key observation or diagnosis.
5. Main mechanism.
6. Secondary mechanism or efficiency design.
7. Evidence: benchmarks plus quality-efficiency result.

## Introduction Frame

Use six moves:

1. `Need`: why the area matters and what real constraint blocks use.
2. `Gap`: prior paradigms grouped by their shared failure.
3. `Observation`: a figure-backed fact that changes the design space.
4. `Method`: what workflow the method changes.
5. `Mechanisms`: each design answers one bottleneck.
6. `Evidence`: benchmark scope, headline numbers, contribution list.

Contribution bullets should be concrete:

- method or paradigm;
- key observation or mechanism;
- second mechanism, theory, or systems design;
- experiments and headline result.

## Method Frame

Open with a roadmap:

`In this section, we introduce [method], a [role] designed to [goal]. It consists of [A] and [B]. We first formulate [minimal unit], then describe [A], and finally integrate [B] into the full pipeline.`

Subsection structure:

1. Motivation or question.
2. Naive solution and failure.
3. Mechanism.
4. Formalization or algorithm.
5. Practical advantage.
6. Link to figure or ablation.

## Experiment Frame

Open with setup and claims:

`We first describe benchmarks, baselines, metrics, and implementation. We then evaluate [main claim], ablate [modules], and visualize [internal behavior].`

Organize by claim:

- effectiveness: quality metric vs dense/full/standard baseline.
- efficiency: speedup, latency, FLOPs, memory, throughput.
- robustness: hard tasks, extreme settings, real-world data.
- mechanism: ablations for each module.
- generality: other samplers, models, datasets, or deployment settings.

## Caption Frame

Captions should say what the reader learns:

`[Takeaway]. [Setting]. [Observed pattern]. [Implication for the method].`

Bad: `Results on different tasks.`

Good: `Fixed schedules fail across rollout iterations. Each schedule is applied to one iteration while the rest uses full computation. The best schedule changes with rollout state, motivating rollout-adaptive pruning.`
