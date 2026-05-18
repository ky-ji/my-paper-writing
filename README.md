# my-paper-writing

A compact Codex skill for transferring a bottleneck-first AI/ML/robotics paper writing style to new projects from rough ideas, experiments, notes, or code repositories.

The skill is designed for early paper construction and fast revision loops: it helps turn implementation details into a reviewer-facing narrative, draft section scaffolds in the target style, tighten language, and diagnose weak paragraph structure.

## Core Uses

- Build an initial paper frame from scratch, notes, experiments, or a GitHub codebase.
- Transfer the target writing style to new projects through reusable narrative moves.
- Convert code artifacts into research abstractions: task, bottleneck, assumption, intervention, mechanism, evidence.
- Draft Abstract, Introduction, Method, Experiments, captions, and contribution lists.
- Polish language while preserving LaTeX commands, citations, equations, labels, and claims.
- Review paragraphs or sections for story flow, claim-evidence alignment, overclaims, and reviewer risks.

## Quick Start

Invoke the skill in Codex:

```text
Use $my-paper-writing to build a paper outline from this repository.
```

Useful prompts:

```text
Use $my-paper-writing to rewrite this Introduction in the target style: bottleneck-first, observation-driven, mechanism-centered, and evidence-tight.
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
| `build` | Starting from code, notes, or rough ideas | story spine, title candidates, outline, figure plan, experiment matrix |
| `draft` | Writing a section from a validated story | section outline plus polished paragraphs |
| `polish` | Tightening existing prose | revised text plus terse notes on wording changes |
| `review` | Stress-testing narrative quality | issues first, then stronger rewrite options |

## Style Transfer

The core style is:

```text
real constraint -> structural mismatch -> diagnostic observation -> mechanism -> secondary bottleneck -> remedy -> claim-grounded evidence
```

This keeps new drafts close to the target style without copying old papers. The skill prioritizes:

- practical constraints over broad motivation;
- structural prior-work failures over citation lists;
- figure-backed observations over unsupported novelty claims;
- primary and secondary mechanisms over flat module lists;
- paired evidence over single-axis claims.

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

- `SKILL.md`: main trigger, workflow, writing rules, and output contract.
- `references/code-to-paper.md`: high-level repository-to-paper abstraction framework.
- `references/style-transfer.md`: writing-style signature, transfer sheet, paragraph moves, and style checklist.
- `references/section-frames.md`: section-level scaffolds for Abstract, Introduction, Method, Experiments, and captions.
- `references/revision.md`: paragraph repair, claim-evidence checks, and polishing rules.

## Install Or Update

Place the repository at:

```text
~/.codex/skills/my-paper-writing
```

To update an existing local install:

```bash
cd ~/.codex/skills/my-paper-writing
git pull
```

## Design Principles

- Start with the bottleneck, not the implementation.
- Use observations to justify mechanisms.
- Map every module to a claim.
- Pair each claimed gain with evidence: quality, cost, robustness, stability, generality, or interpretability.
- Keep reviewer risks visible instead of polishing them away.
