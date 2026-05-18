---
name: my-paper-writing
description: Use when building an AI/ML/robotics paper from scratch, from a GitHub codebase, or from rough notes; drafting paper outlines, Abstract, Introduction, Method, Experiments, captions, and contribution lists; polishing language; or reviewing and strengthening paragraph-level storytelling, claim-evidence alignment, and reviewer-facing narrative.
---

# My Paper Writing

## Purpose

Use this skill as a compact paper-building engine: turn code, experiments, notes, or rough prose into a clear top-conference paper story.
The default style is bottleneck-first, observation-driven, mechanism-centered, and evidence-tight.

## Fast Workflow

1. Choose the task mode:
   - `build`: create a paper frame from code/notes.
   - `draft`: write a section from a validated story.
   - `polish`: tighten language while preserving claims.
   - `review`: diagnose and strengthen paragraph or section narrative.
2. Load only the needed reference:
   - From code to paper: `references/code-to-paper.md`
   - Section frames: `references/section-frames.md`
   - Revision and polishing: `references/revision.md`
3. Always identify the story spine:
   `need -> bottleneck -> prior failure -> observation -> mechanism -> evidence`
4. Return an artifact that saves time:
   - for `build`: title candidates, core claim, outline, figure plan, experiment plan.
   - for `draft`: section outline plus polished paragraphs.
   - for `polish`: revised text plus key wording changes.
   - for `review`: issues first, then stronger rewrite options.

## Code-To-Paper Rule

When a repository is provided, read it as a source of paper evidence:

- entrypoints reveal user workflow and evaluation claims.
- wrappers, schedulers, gates, caches, losses, buffers, and state variables reveal mechanisms.
- configs reveal controllable knobs and ablations.
- scripts reveal benchmark scope and reproducibility.
- logging and metrics reveal what can become tables and claims.

Do not describe the code file-by-file. Convert implementation choices into research questions, observations, modules, ablations, and figures.

## Writing Rules

- One paragraph, one message.
- First sentence states the paragraph role.
- Every module answers a bottleneck.
- Every strong claim has evidence or is weakened.
- Pair efficiency with quality: speedup/FLOPs/latency/memory plus success/accuracy/fidelity.
- Prefer concrete mechanism verbs: predict, allocate, schedule, reuse, truncate, decompose, overlap, cache, gate, supervise.
- Preserve LaTeX commands, citations, labels, equations, and macros during edits.
- Remove generic praise unless supported by a number or mechanism.

## Default Output Contract

For substantial tasks, return:

1. `Story spine`: one compact causal chain.
2. `Draft or rewrite`: the requested artifact.
3. `Claim-evidence map`: major claims and support.
4. `Reviewer risks`: missing evidence, weak transitions, unclear novelty, or overclaims.

For quick language edits, return only the revised text plus 2-4 terse notes.
