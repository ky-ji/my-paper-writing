# Code To Paper

## Goal

Convert a repository into a paper story. Do not summarize files. Extract the research argument hidden in the implementation.

## Repository Reading Order

1. `README`, project page text, scripts: external promise, usage path, benchmark scope.
2. Entrypoints and wrappers: the core workflow the method changes.
3. Modules named scheduler, pruner, cache, loss, criterion, analyzer, evaluator: paper mechanisms.
4. Configs and shell scripts: ablation knobs and reproducibility details.
5. Metrics/logging/output names: table columns and headline claims.

## Story Extraction

Fill this table before drafting:

| Code evidence | Paper meaning |
| --- | --- |
| repeated loop, slow path, full forward, dual network, dataset pass | bottleneck |
| cache, gate, mask, clean flag, table, buffer, schedule | mechanism state |
| similarity, disagreement, error, latency, sparsity, loss curve | observation |
| scheduler, pruner, criterion, union, pipeline, wrapper | named module |
| config flag, pruning rate, cache steps, threshold, target ratio | ablation axis |
| benchmark script, eval entrypoint, collected trajectories | experiment scope |

## Four Proven Code-To-Story Patterns

### Stateful Training Becomes Bias Control

Implementation signs: persistent `clean_flags`, label hash codes, warmup, old selections used for training, variance-based filtering.

Paper story:

- Bottleneck: sample selection compounds bias or costs extra networks/passes.
- Observation: temporal disagreement can replace cross-network disagreement.
- Mechanism: delayed state/table update separates selection from training.
- Second mechanism: single-sample loss decomposition gives a local criterion.
- Evidence: robustness, extreme settings, throughput, memory.

### Offline Analysis Becomes Adaptive Scheduling

Implementation signs: activation collection, similarity matrices, dynamic programming, per-block step files, cache wrapper.

Paper story:

- Bottleneck: uniform/static caching ignores non-uniform feature dynamics.
- Observation: similarity differs across timesteps and blocks.
- Mechanism: scheduler optimizes update timesteps under a budget.
- Failure mode: block-wise extension causes error propagation.
- Remedy: union upstream updates before risky downstream blocks.
- Evidence: speedup without task degradation, ablations on scheduler/remedy.

### Learned Gates Become Rollout Adaptation

Implementation signs: observation-conditioned pruner, timestep/block embeddings, global gates, shared cache, sparsity loss, consistency loss.

Paper story:

- Bottleneck: fixed schedules cannot follow robot-environment dynamics.
- Observation: optimal sparsity patterns change by rollout state.
- Mechanism: pruner predicts a timestep-by-block mask from observation.
- Efficiency design: one forward predicts the global graph.
- Reuse design: shared cache reuses activations across timesteps and blocks.
- Evidence: pruning ratio, speedup, hard-task stability, ablations.

### Systems Optimization Becomes Practical Test-Time Sparsity

Implementation signs: batched all-step encoding, CUDA streams, async pruner, multiple cache directions, rollout cache, trajectory data.

Paper story:

- Bottleneck: dynamic pruning overhead can erase sparse-compute gains.
- Observation: non-decoder latency and feature reuse direction limit speed.
- Mechanism 1: parallelize/overlap encoding, pruning, and decoder execution.
- Mechanism 2: choose among current-forward, timestep, and rollout caches.
- Training: trajectory-level supervision teaches rollout-level reuse.
- Evidence: wall-clock latency, FLOPs, inference frequency, fidelity.

## From Code To Initial Paper Frame

Produce this when asked to build from code:

1. `One-line thesis`: method + bottleneck + evidence target.
2. `Title candidates`: 3-5 names, each tied to a mechanism.
3. `Abstract skeleton`: 6 sentences.
4. `Introduction outline`: 5-6 paragraph roles.
5. `Method modules`: each module with motivation, mechanism, and expected figure.
6. `Experiment matrix`: claim -> metric -> benchmark -> ablation.
7. `Reviewer risks`: what evidence is missing from the code or notes.

## Do Not Do

- Do not turn README features into contribution bullets directly.
- Do not write "we implement" when the paper needs "we formulate", "we observe", or "we design".
- Do not claim novelty from file names.
- Do not hide system overhead; make it a bottleneck and solve it.
