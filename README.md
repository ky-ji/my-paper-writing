# my-paper-writing

A compact agent skill for transferring my writing style to new projects from rough ideas, experiments, notes, or code repositories.

The skill is designed for early paper construction and revision loops. It helps turn implementation details into a coherent research argument, draft section scaffolds in the target style, tighten language, and diagnose weak paragraph structure.

## Core Uses

- Build an initial paper frame from scratch, notes, experiments, or a code repository.
- Transfer the target writing style to new projects through reusable narrative moves.
- Convert code artifacts into research abstractions: task, bottleneck, assumption, intervention, mechanism, evidence.
- Draft Abstract, Introduction, Method, Experiments, captions, and contribution lists.
- Polish language while preserving LaTeX commands, citations, equations, labels, and claims.
- Review paragraphs or sections for story flow, claim-evidence alignment, overclaims, and evidence accuracy.

## Quick Start

Invoke the skill in a compatible writing agent:

```text
Use $my-paper-writing to build a paper outline from this repository.
```

Useful prompts:

```text
Use $my-paper-writing to rewrite this Introduction in the target style: clear in logic, natural and concise in language, and accurate in evidence.
```

```text
Use $my-paper-writing to turn this codebase into a paper story: core thesis, story spine, method modules, figure plan, and experiment matrix.
```

```text
Use $my-paper-writing to review this Introduction for paragraph logic, missing evidence, weak novelty, and overclaims.
```

```text
Use $my-paper-writing to polish this Method section while preserving LaTeX macros, citations, equations, and labels.
```

## Modes

| Mode | Use it for | Expected output |
| --- | --- | --- |
| `build` | Starting from code, notes, or rough ideas | a paper frame with titles, outline, figures, and experiments as needed |
| `draft` | Writing a section from a validated story | requested section, with an outline when useful |
| `polish` | Tightening existing prose | revised text, with useful notes on substantive changes |
| `review` | Checking narrative quality | important issues and suitable rewrite options |

## Style Transfer

The skill prioritizes logic before wording, a clear central insight, faithful mechanism descriptions, and claims supported by the actual evidence. It preserves meaning and contrasts while shortening prose.

Narrative shape follows the paper. There is no required sentence count, paragraph count, module count, or primary/secondary mechanism pattern. Section guidance also covers natural abstract scope, problem-driven experiments, figure roles, and direct, sincere rebuttal responses.

## Code-To-Paper Workflow

When a repository is provided, the skill reads code as paper evidence rather than as files to summarize.

It looks for:

- README, scripts, and configs to infer task setting and benchmark scope.
- data, model, training, and inference pipelines to identify assumptions and intervention points.
- objectives, controllers, memory/state, constraints, and decision rules to extract mechanisms.
- logging, metrics, tests, and output artifacts to identify evidence for claims.

The output should climb from implementation to paper-level narrative:

```text
code artifact -> research abstraction -> claim -> needed evidence -> paper section
```

## Repository Layout

```text
.
|-- SKILL.md
|-- agents/
|   `-- openai.yaml
`-- references/
    |-- code-to-paper.md
    |-- revision.md
    |-- style-transfer.md
    `-- section-frames.md
```

- `SKILL.md`: main trigger, working approach, writing preferences, and reference links.
- `references/code-to-paper.md`: high-level repository-to-paper abstraction framework.
- `references/style-transfer.md`: overall argument, writing voice, and flexible narrative guidance.
- `references/section-frames.md`: section-level playbooks for Abstract, Introduction, Related Work, Method, Experiments, figures, and conclusions.
- `references/revision.md`: meaning-preserving revision, evidence accuracy, and rebuttal guidance.

## Install Or Update

Place the repository in the skills directory used by your writing agent, keeping the folder name:

```text
my-paper-writing
```

To update an existing local install:

```bash
cd path/to/my-paper-writing
git pull
```

## Design Principles

- Resolve the argument before polishing sentences.
- Explain the core insight through concrete mechanisms.
- Preserve the requested edit scope and finalized terminology and notation.
- Match claims, citations, mechanisms, and results to their evidence.
- Keep narrative structure flexible and necessary qualifications proportional.
