---
name: my-paper-writing
description: Build, draft, revise, or review AI/ML/robotics papers and rebuttals from ideas, code, experiments, or existing prose, with clear logic, natural concise language, and accurate evidence.
---

# My Paper Writing

## Purpose

Turn ideas, code, experiments, and rough prose into a coherent research argument. Resolve the logic before polishing the language. Explain the central insight, why it matters, how the method realizes it, and what the evidence establishes.

Choose the narrative that fits the paper. Sentence counts, paragraph counts, module counts, and a primary/secondary mechanism pattern are not requirements.

## Working Approach

Respect the requested edit scope and retain finalized names, terminology, and notation. Preserve LaTeX commands, citations, labels, equations, and macros while editing.

Read only the references relevant to the task.

- [Style transfer](references/style-transfer.md) for the overall argument and writing voice.
- [Code to paper](references/code-to-paper.md) when deriving a paper from a repository or implementation notes.
- [Section playbooks](references/section-frames.md) for abstracts, introductions, methods, experiments, and figures.
- [Revision](references/revision.md) for repairing existing prose or writing a rebuttal.

For substantial writing, understand the research question, prior work, central insight, actual mechanism, and available evidence before drafting. A local wording edit need not repeat this process. Return the requested artifact and only the explanation useful for evaluating it.

## Writing Preferences

- Be concise while preserving meaning, causal relations, contrasts, and necessary evidence.
- Use concrete, natural, formal language. Explain mechanisms through actions and objects rather than abstract labels or implementation lists.
- Give each paragraph a clear purpose and connect sentences through cause, contrast, or consequence.
- Keep mechanisms, claims, citations, and reported results accurate. State necessary conditions without burying the contribution under defensive commentary.
- Prefer sentences connected by clear words over semicolons or dashes. Use colons sparingly, mainly when emphasizing or defining a specific concept. These are preferences, not absolute bans, and do not apply to syntax required by code or LaTeX.
