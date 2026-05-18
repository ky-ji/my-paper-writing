# Style Principles

## Core Identity

Kangye's paper style is technical, efficient, and reviewer-aware. It works by making the reader believe that the method is not merely a new module, but the inevitable result of a measured bottleneck and a precise observation.

The stable story arc is:

`practical need -> computational/statistical bottleneck -> why existing paradigms fail -> empirical/theoretical observation -> named mechanism -> quantified result`

## Distilled Patterns

### 1. Start from a real constraint

Open with why the field cares, then immediately state the constraint that blocks deployment or robustness.

Good shape:

`[Model/paradigm] has become important because [capability]. However, [specific cost/failure] prevents [real use case]. For example, [number] makes [requirement] unattainable.`

Use numbers early when available: Hz, milliseconds, FLOPs, speedup, memory, success rate, noise ratio, or number of denoising steps.

### 2. Make prior work fail for a structural reason

Do not say existing work is weak in general. Explain the structural mismatch:

- Static schedules cannot adapt to rollout dynamics.
- Dataset-wise selection reduces bias but adds full-dataset passes.
- Dual-network disagreement mitigates bias but doubles cost.
- Image/video diffusion caching does not transfer because action diffusion has different data dynamics and architecture.

This makes the gap feel necessary rather than opportunistic.

### 3. Use an observation as the hinge

The method should pivot on a compact observation, ideally tied to a figure:

- selected sets disagree more across iterations than across networks.
- feature similarities vary non-uniformly across timesteps.
- blocks exhibit different temporal patterns.
- fixed schedules perform inconsistently across rollout iterations.
- cached features from multiple directions are aligned but complementary.

After the observation, write: `Motivated by this observation, we propose...`

### 4. Turn each bottleneck into one design

Kangye-style design exposition is modular but causal. Each module answers a named bottleneck.

Bad:

`Our method has module A and module B.`

Good:

`However, this paradigm raises two bottlenecks: [bottleneck 1] and [bottleneck 2]. To address the first bottleneck, we design [module A]. To overcome the second bottleneck, we introduce [module B].`

### 5. Favor mechanism verbs

Use verbs that expose the mechanism:

- identifies, allocates, predicts, reuses, updates, truncates, mitigates, decomposes, conditions, overlaps, schedules, parameterizes, reformulates, regularizes, quantifies.

Avoid vague verbs:

- improves, enhances, leverages, utilizes, explores, handles, boosts.

Use vague verbs only when followed by the mechanism.

### 6. Keep efficiency and fidelity paired

The style rarely reports speed alone. It pairs acceleration with preserved performance:

- `without performance degradation`
- `while maintaining comparable performance`
- `lossless acceleration`
- `at negligible additional cost`
- `without updating the original model`

When polishing, always check whether efficiency claims include the corresponding quality metric.

### 7. Use named artifacts

Name the method and its key modules clearly. Names should map to roles:

- Jump-update Strategy -> debiased update.
- Single-loss Criterion -> sample-wise selection.
- Adaptive Caching Scheduler -> update timestep allocation.
- Bubbling Union Algorithm -> error propagation truncation.
- Real-time Diffusion Pruner -> environment-aware schedule prediction.
- One-for-All Reusing -> cross-block and cross-timestep reuse.
- Parallelized Inference Pipeline -> non-decoder delay reduction.
- Omnidirectional Reusing -> multi-direction historical feature reuse.

For a new paper, ensure the names are not decorative. Each name should answer a bottleneck.

### 8. End the introduction with evidence, not excitement

The final pre-contribution paragraph should establish scope and measured benefit:

`To assess effectiveness, we evaluate [method] on [benchmarks]. [Method] achieves [primary result] while [quality/efficiency constraint]. In summary, our contributions are as follows:`

Contribution bullets should be concrete:

1. Method-level contribution.
2. Key design or theoretical/empirical insight.
3. Experimental result and scope.

Avoid bullets that only restate "we propose a novel method".

## Voice

Use clear academic English with controlled contrast. The prose can be assertive, but every assertion should be tied to a mechanism or result.

Preferred sentence rhythm:

- Short topic sentence.
- One or two explanatory sentences.
- Concrete consequence.

Preferred logical connectors:

- `However, ...`
- `To address this, ...`
- `Specifically, ...`
- `Motivated by this observation, ...`
- `To operationalize this insight, ...`
- `In contrast, ...`
- `As shown in ..., ...`

Do not stack multiple connectors if the paragraph already has a clear flow.

## Red Flags

- The method appears before the observation.
- A module is introduced without a failure mode.
- A result claims "significant" without a number.
- Related work is a bibliography rather than a gap analysis.
- Abstract contains too many module names without explaining the bottleneck.
- Experiments list tables without tying them to claims.
- Captions do not state what the reader should learn.
- The same concept has multiple names across sections.
