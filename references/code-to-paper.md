# Code To Paper

## Goal

Convert any AI/ML/robotics repository into a paper story. Do not summarize files. Connect implementation artifacts to research claims.

## Abstraction Ladder

Use these mappings where relevant.

| Repository evidence | Paper abstraction |
| --- | --- |
| README, demo, examples, scripts | task setting, user workflow, evaluation scope |
| data pipeline, preprocessing, simulator, collector | problem assumptions and deployment constraints |
| model, policy, optimizer, sampler, controller | intervention point |
| objective, loss, rule, planner, search, memory, state | mechanism |
| profiling, error logs, failure cases, oracle labels | bottleneck or observation |
| config flags, thresholds, budgets, schedules, seeds | ablation axes |
| metrics, logs, checkpoints, output artifacts | evidence for claims |

If the code only reveals an implementation detail, ask: what assumption makes this detail necessary, what bottleneck does it address, and what would fail without it?

## Repository Reading Guide

1. `README`, project page, scripts: what problem the repository claims to solve.
2. Entrypoints: what a user actually runs and which workflow is changed.
3. Data and environment code: what distribution, task, or deployment constraint defines the problem.
4. Core model/training/inference modules: where the proposed intervention enters the pipeline.
5. Objectives, controllers, memory/state, constraints, and decision rules: mechanisms that can become method sections.
6. Configs, tests, evaluation scripts, and logs: ablation knobs, metrics, baselines, and reproducibility claims.

## General Story Archetypes

These examples can help interpret the repository. Use the reasoning that fits the project rather than assigning it a mandatory archetype.

### Efficiency Or Systems

Signs: profiling, caching, pruning, batching, scheduling, approximation, compiler/runtime changes, memory reuse.

Story: a standard pipeline wastes compute, memory, or wall-clock time because it treats all instances, steps, or modules uniformly. The method identifies structure or redundancy, then uses a mechanism that allocates computation selectively while preserving quality.

Evidence: latency, throughput, FLOPs, memory, quality metric, overhead breakdown, compatibility with larger settings.

### Robustness Or Data Quality

Signs: filtering, reweighting, curriculum, uncertainty, disagreement, clean/noisy labels, outliers, adversarial or shifted data.

Story: training or inference fails because the data or environment violates a common assumption. The method detects reliability, uncertainty, or difficulty and changes how samples, labels, states, or losses influence learning.

Evidence: corrupted/noisy/shifted benchmarks, hard subsets, sensitivity curves, ablations on the reliability signal.

### Adaptation Or Control

Signs: policies, planners, closed-loop evaluation, online decisions, state-conditioned modules, robot/environment feedback.

Story: a fixed policy or static design fails because the optimal behavior depends on context. The method uses observations, histories, or constraints to adapt decisions while maintaining stability and sample efficiency.

Evidence: rollout success, recovery cases, generalization to new tasks, policy diagnostics, real-time cost.

### Representation Or Architecture

Signs: new encoder/decoder, attention pattern, graph, latent variable, tokenization, modular network, cross-modal fusion.

Story: the existing representation hides or entangles a structure needed by the task. The method exposes that structure through an architectural or representational change, making learning, reasoning, or transfer easier.

Evidence: main metrics, probing/visualization, module ablations, transfer or scaling behavior.

### Optimization Or Objective

Signs: new loss, regularizer, constraint, estimator, relaxation, search objective, training schedule.

Story: the default objective optimizes the wrong proxy, has poor gradients, or ignores a constraint. The method reformulates the objective so the desired behavior is optimized more directly or stably.

Evidence: convergence, stability, final performance, objective-component ablations, sensitivity to hyperparameters.

### Evaluation Or Benchmark

Signs: new dataset, metric, protocol, simulator, task suite, annotation pipeline, diagnostic split.

Story: current evaluation misses an important capability or failure mode. The contribution is a measurement frame plus evidence that existing methods behave differently under it.

Evidence: benchmark construction, metric validity, baseline coverage, diagnostic findings, reproducibility artifacts.

## Build The Initial Paper Frame

When asked to build from code, identify the core thesis, essential insight, actual mechanisms, and evidence needed to establish the claim. Propose an outline, figures, comparisons, and title candidates at the level of detail useful for the request.

Connect the implementation to the research question before listing components. The number of modules, figures, titles, or narrative stages should follow the project. Use [Style Transfer](style-transfer.md) to develop the argument and [Section Playbooks](section-frames.md) to draft sections.

## Evidence And Mechanism Accuracy

Check inputs, conditioning, representations, objectives, and operation order against the selected code and configuration. A smoother sentence must not change what the method actually does.

Treat code as evidence for implementation, not as proof of empirical gains or novelty. Support research claims with the relevant experiments or analysis, and attach citations to statements those sources actually support. Keep proposed evidence distinct from completed results.

Describe the insight and intervention rather than files, classes, head counts, or hidden-state lists. Promote an implementation choice to a contribution only when its research significance is explained and supported.

Report overhead, assumptions, and failure cases when they affect interpretation. Keep the explanation specific to the claim rather than appending stock reviewer-risk commentary.
