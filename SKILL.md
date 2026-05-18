---
name: my-paper-writing
description: Use when drafting, reviewing, proofreading, or polishing ML/robotics/AI research papers in Kangye Ji's established top-conference style, especially Abstract, Introduction, Related Work, Method, Experiments, Conclusion, rebuttal text, figure captions, contribution lists, and claim-evidence alignment.
---

# My Paper Writing

## Overview

Use this skill to make a paper read like Kangye Ji's accepted top-conference work: bottleneck-first, observation-centered, mechanism-driven, and evidence-tight.
Prioritize reviewer-facing clarity over decorative prose.

## Core Workflow

1. Identify the target section and the paper's core story.
2. Load only the needed reference:
   - Full style: `references/style-principles.md`
   - Section drafting: `references/section-playbooks.md`
   - Editing/review: `references/revision-checklists.md`
   - Sentence patterns: `references/phrase-bank.md`
3. Diagnose before rewriting:
   - What practical bottleneck matters?
   - What existing paradigm fails, and why?
   - What observation justifies the new method?
   - Which design choices operationalize the observation?
   - Which experiments prove the performance-efficiency trade-off?
4. Rewrite in the local style, keeping every claim supported by evidence supplied by the user.
5. End with a compact reviewer-risk report unless the user only asks for direct proofreading.

## Core Paper Arc

Most sections should preserve this causal chain:

`value -> bottleneck -> prior limitation -> observation -> mechanism -> evidence`

Do not present the method as a bag of modules. Present it as a sequence of necessary answers to specific obstacles.

## Output Modes

Use the mode implied by the user request:

- `diagnose`: list story gaps, unsupported claims, weak transitions, and missing evidence.
- `rewrite`: provide polished prose plus a short note on what changed.
- `line edit`: keep structure and tighten grammar, terms, transitions, and reviewer-facing precision.
- `review`: lead with major risks, then minor edits, then suggested rewrites.
- `latex edit`: preserve LaTeX commands, labels, citations, math, and macros.

For nontrivial rewrites, return:

1. A one-sentence story diagnosis.
2. Revised text.
3. A claim-evidence map.
4. Remaining reviewer risks.

## Hard Rules

- Keep one paragraph to one message.
- Make the first sentence of each paragraph state its role.
- Use concrete agents and mechanisms: "the pruner predicts", "the scheduler allocates", "the strategy truncates".
- Quantify bottlenecks and results when numbers are available.
- Prefer "However", "To address this", "Specifically", "Motivated by this observation", and "To operationalize this insight" only when the logical relation is real.
- Do not invent observations, metrics, benchmarks, or ablations.
- Do not overclaim novelty. Let the bottleneck, observation, and evidence imply novelty.
- Remove generic praise words such as "powerful", "significant", "remarkable", and "novel" unless immediately backed by a concrete mechanism or result.
- Keep terminology stable across title, abstract, contribution list, figures, method, and experiments.
- If evidence is missing, weaken the claim or mark it as needing evidence.

## Common Repair Moves

- Vague problem -> add the real operational bottleneck and a number.
- Broad prior-work complaint -> split methods into 2-3 categories and state the shared failure mode.
- Method appears ad hoc -> insert the key observation before the module list.
- Module list feels flat -> make each module answer a named bottleneck.
- Abstract is crowded -> compress to problem, limitation, method, two mechanisms, result.
- Introduction is weak -> add an early observation figure or quantified leave-one-out/profiling result.
- Experiments feel like reporting -> group them by claims: effectiveness, efficiency, ablation, compatibility, qualitative behavior.
- Caption is descriptive only -> rewrite it to state the takeaway and experimental context.

## Source Basis

This skill was distilled from four accepted or top-conference-targeted papers by Kangye Ji:

- Jump-teaching: temporal disagreement for noisy-label sample selection.
- Block-wise Adaptive Caching: training-free acceleration for Diffusion Policy.
- Sparse ActionGen: rollout-adaptive sparse action generation.
- Test-time Sparsity: parallelized pruning and omnidirectional reuse for action diffusion.

Use these as style anchors, not as text to copy.
