---
name: my-paper-writing
description: Use when building or revising an AI/ML/robotics paper in a bottleneck-first, observation-driven style; drafting from rough ideas or code repositories; polishing Abstract, Introduction, Method, Experiments, captions, and contribution lists; or reviewing paragraph flow, claim-evidence alignment, overclaims, and reviewer-facing narrative.
---

# My Paper Writing

## Purpose

Use this skill as a compact style-transfer engine: turn code, experiments, notes, or rough prose into a clear top-conference paper story in the target writing style.
The default style is bottleneck-first, observation-driven, mechanism-centered, and evidence-tight.

## Fast Workflow

1. Choose the task mode:
   - `build`: create a paper frame from code/notes.
   - `draft`: write a section from a validated story.
   - `polish`: tighten language while preserving claims.
   - `review`: diagnose and strengthen paragraph or section narrative.
2. Load only the needed reference:
   - Style transfer: `references/style-transfer.md`
   - From code to paper: `references/code-to-paper.md`
   - Section playbooks: `references/section-frames.md`
   - Revision and polishing: `references/revision.md`
3. For substantial drafting or rewriting, apply the style transfer sheet before writing.
4. Always identify the story spine:
   `need -> bottleneck -> prior failure -> observation -> mechanism -> evidence`
5. Return an artifact that saves time:
   - for `build`: title candidates, core claim, outline, figure plan, experiment plan.
   - for `draft`: section outline plus polished paragraphs.
   - for `polish`: revised text plus key wording changes.
   - for `review`: issues first, then stronger rewrite options.

## Style-Transfer Rule

Before polishing sentences, recover the paper's argumentative machine:

- practical constraint first, not broad motivation.
- prior work grouped by structural mismatch, not listed by citation.
- one figure-backed observation that changes the design space.
- one primary mechanism and one secondary mechanism that handles overhead, error, stability, or scalability.
- experiments organized by claims: main trade-off, hard cases, module ablations, and internal behavior.

If a draft lacks one of these parts, mark the missing part as a story gap instead of smoothing the prose.

## Code-To-Paper Rule

When a repository is provided, read it as a source of paper evidence:

- README, scripts, and configs reveal the intended task, setting, and benchmark scope.
- data, model, training, and inference pipelines reveal assumptions and intervention points.
- objectives, controllers, memory/state, constraints, and decision rules reveal mechanisms.
- logging, metrics, tests, and output artifacts reveal evidence that can support claims.

Do not describe the code file-by-file. Convert implementation choices into research questions, observations, modules, ablations, and figures.

## Writing Rules

- One paragraph, one message.
- First sentence states the paragraph role.
- Every module answers a bottleneck.
- Every strong claim has evidence or is weakened.
- Pair each claimed gain with the right counterpart metric: quality, cost, robustness, stability, generality, or interpretability.
- Prefer concrete mechanism verbs: identify, predict, allocate, select, reformulate, constrain, supervise, adapt, retrieve, reuse, decompose.
- Preserve LaTeX commands, citations, labels, equations, and macros during edits.
- Remove generic praise unless supported by a number or mechanism.

## Default Output Contract

For substantial tasks, return:

1. `Story spine`: one compact causal chain.
2. `Draft or rewrite`: the requested artifact.
3. `Style transfer notes`: which style moves were applied or are missing.
4. `Claim-evidence map`: major claims and support.
5. `Reviewer risks`: missing evidence, weak transitions, unclear novelty, or overclaims.

For quick language edits, return only the revised text plus 2-4 terse notes.
