# Revision Checklists

## Story Diagnosis

Before editing, answer:

- What is the real bottleneck?
- What exact prior paradigm fails?
- What observation makes the new direction plausible?
- What does each module solve?
- What evidence supports each major claim?
- What would a skeptical reviewer attack first?

If any answer is missing, do not polish around the gap. Mark it and propose the missing sentence, figure, or experiment.

## Claim-Evidence Map

For each major claim, produce:

`Claim: ... | Evidence: ... | Status: supported / needs evidence / overclaimed`

Common evidence types:

- profiling numbers: latency, FLOPs, memory, throughput.
- observation figures: similarity, disagreement, fixed-schedule failure, error propagation.
- main benchmark tables: success rate, accuracy, speedup, frequency.
- ablations: each module removed or replaced.
- compatibility tests: samplers, VLA models, real-world settings, noise types.
- qualitative plots: masks, schedules, behavior, failure modes.

## Abstract Review

Check:

- Sentence 1 states the field value and practical bottleneck.
- Existing methods fail for a structural reason.
- The method is introduced after the gap.
- The key observation is explicit.
- Each module is tied to a bottleneck.
- The final result pairs efficiency with quality.
- There is no unsupported "novel", "significant", or "powerful".

## Introduction Review

Check:

- The first paragraph includes a concrete number or real deployment constraint.
- Prior work is grouped by limitation, not listed chronologically.
- The central observation appears before detailed module descriptions.
- Figure 1 or the first figure is a story figure, not a decoration.
- The method paragraph explains what changes in the workflow.
- Contribution bullets are not redundant with the abstract.
- Headline numbers match the experiments.

## Method Review

Check:

- The section starts with a roadmap.
- Preliminaries define only what the method needs.
- Each subsection starts from a question, bottleneck, or failure mode.
- Equations define variables before reuse.
- Algorithms are introduced after the mechanism is clear.
- The pipeline paragraph explains how modules interact.
- Claims about overhead are backed by complexity, implementation, or latency results.

## Experiment Review

Check:

- The setup names models, benchmarks, baselines, metrics, and hardware where needed.
- Metrics include both task quality and efficiency.
- Baselines are fair and comparable.
- Main results are interpreted, not merely reported.
- Hard tasks and failure cases are discussed.
- Ablations align with modules and observations.
- Sensitivity/compatibility tests cover likely reviewer concerns.
- Captions state takeaways.

## Sentence-Level Polish

Prefer:

- `This raises two bottlenecks: ...`
- `To address the first bottleneck, ...`
- `To overcome the second bottleneck, ...`
- `We attribute this failure to ...`
- `This suggests ...`
- `These results demonstrate ...`

Avoid:

- `It is worth noting that...`
- `There are many works...`
- `This method is very effective...`
- `We can see that...`
- `The results are good...`
- `Novel and efficient...` without mechanism and number.

## Reviewer-Risk Questions

Ask these before finalizing:

- Why cannot a static, uniform, or dataset-wise baseline solve this?
- Is the observation specific enough to justify the method?
- Does the method add overhead that cancels its benefit?
- Is the method robust under hard tasks, extreme settings, or real-world data?
- Are the ablations enough to isolate each design?
- Are all claimed speedups measured wall-clock or only FLOPs?
- Does any claim rely on an appendix-only result that should move to the main paper?
- Are limitations acknowledged without weakening the main contribution?
