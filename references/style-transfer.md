# Style Transfer

## Core Signature

The target style is not decorative. It is a reviewer-facing argument machine:

`real constraint -> structural mismatch -> diagnostic observation -> mechanism -> secondary bottleneck -> remedy -> claim-grounded evidence`

Write as if each paragraph must reduce reviewer uncertainty. Avoid broad promises. Make the reader feel that the method is forced by the problem structure.

## Style Transfer Sheet

Fill this before drafting from a new project:

| Slot | Question | Output |
| --- | --- | --- |
| Field value | What capability or deployment need makes the topic matter? | one concrete sentence |
| Practical bottleneck | What blocks use: latency, bias, error, memory, supervision, instability, mismatch? | one measurable constraint if possible |
| Prior mismatch | What common assumption makes prior work insufficient? | grouped by paradigm, not by paper |
| Diagnostic observation | What fact changes the design space? | figure/table/profiling/analysis target |
| Primary mechanism | What design directly exploits the observation? | named module or paradigm |
| Secondary bottleneck | What breaks when the primary idea is applied naively? | overhead, error propagation, static schedule, weak signal, scalability |
| Remedy | What second design makes the primary mechanism practical? | scheduler, criterion, loss, pipeline, buffer, solver, training signal |
| Evidence | Which experiments support each claim? | main result, hard case, ablation, qualitative/profiling |

Do not draft the Introduction until every slot has a concrete answer or an explicit `missing evidence` marker.

## Abstract Style

Use 5-7 sentences with this pressure curve:

1. Capability plus practical blocker.
2. Existing paradigm and why it structurally fails in this setting.
3. Proposed method as a named mechanism, not a vague framework.
4. Key observation or diagnosis.
5. Primary design that operationalizes the observation.
6. Secondary design that resolves a hidden failure mode or overhead.
7. Evidence with paired metrics: quality plus cost, robustness, stability, or generality.

Preferred sentence moves:

- `[Field] has demonstrated [capability], but [bottleneck] makes it impractical for [deployment].`
- `Existing [paradigm] relies on [assumption], which fails under [setting].`
- `To operationalize this insight, we design [module] to [mechanism].`
- `However, directly applying [idea] introduces [failure]. To mitigate this, we [remedy].`

## Introduction Style

Use a 6-paragraph arc:

1. `Need`: area value, adoption, and real-world constraint with a number or concrete example.
2. `Gap`: prior methods grouped into 1-2 paradigms, ending with the shared structural mismatch.
3. `Observation`: diagnostic figure/table/profiling result, phrased as 1-2 explicit observations.
4. `Method`: proposed paradigm and what workflow it changes.
5. `Mechanisms`: primary mechanism, then secondary bottleneck and remedy.
6. `Evidence`: benchmark scope, headline paired metrics, contribution bullets.

The Introduction should contain at least one early figure or diagnostic reference before the method details. The figure should justify the method, not merely illustrate it.

## Method Style

Open with a roadmap that names the modules and their roles:

`In this section, we introduce [method], a [role] designed to [goal]. It consists of [A] and [B]. We first formulate [minimal unit], then describe [A], and finally integrate [B] into the full pipeline.`

Then follow this rhythm:

- define the minimal unit or process before proposing changes;
- turn the method into 2-3 named modules;
- start each module with a motivation or question;
- present a naive/direct solution and its failure when useful;
- introduce the mechanism;
- formalize only after the reader knows why the equation exists;
- end by stating the practical advantage or link to an ablation.

Good module logic:

`Motivated by [observation], we seek [goal]. A naive idea is [baseline], but [failure]. To overcome this limitation, we [mechanism].`

## Experiment Style

Organize experiments by claims, not by tables:

1. setup: benchmarks, baselines, metrics, implementation;
2. main trade-off: performance plus efficiency/cost;
3. hard cases: extreme noise, difficult tasks, real-world or long-horizon settings;
4. generality: additional models, samplers, datasets, or domains;
5. mechanism ablations: one ablation per design module;
6. internal behavior: visualization, profiling, qualitative cases, failure modes.

Result paragraphs should state the takeaway first, then the numbers, then the reason:

`[Method] achieves [headline result] under [setting]. Compared with [baseline], it [specific improvement]. We attribute this gain to [mechanism], which [causal explanation].`

## Contribution Style

Use 3-4 bullets. Each bullet should be claim-like, not feature-like:

- observation or paradigm;
- primary mechanism;
- secondary mechanism, theory, pipeline, or objective;
- experiments with headline paired metrics.

Avoid bullets that merely list modules. A contribution should say what uncertainty it resolves for the reader.

## Paragraph Moves

Use these moves to transfer the style:

- `Capability -> constraint`: establish why the field matters and why the current system fails in practice.
- `Prior grouping -> mismatch`: compress related work into paradigms, then expose the shared assumption.
- `Observation -> design`: make one empirical/theoretical fact motivate the method.
- `Naive extension -> failure`: show why the obvious version is insufficient.
- `Mechanism -> advantage`: explain what the design changes and why it helps.
- `Result -> attribution`: report numbers and immediately connect them back to the mechanism.

## Language Profile

Prefer concrete verbs:

`identify`, `reformulate`, `allocate`, `condition`, `truncate`, `mitigate`, `reuse`, `decompose`, `decouple`, `overlap`, `supervise`, `adapt`, `preserve`, `recover`.

Prefer connective phrases:

- `Despite this necessity, ...`
- `To examine this limitation, ...`
- `Motivated by this observation, ...`
- `The key to [method] lies in ...`
- `This raises two bottlenecks: ...`
- `To address the first bottleneck, ...`
- `To overcome the second bottleneck, ...`
- `We attribute this failure/gain to ...`

Use adjectives only when anchored:

- good: `training-free`, `sample-wise`, `block-specific`, `rollout-adaptive`, `parameter-efficient`, `inference-efficient`, `lossless`.
- weak unless supported: `novel`, `powerful`, `significant`, `effective`, `robust`.

## Style Review Checklist

Before returning a rewrite, check:

- Does the first paragraph include a concrete deployment or learning constraint?
- Is prior work grouped by shared failure rather than listed?
- Is there a figure-backed observation or planned diagnostic?
- Does each method module answer one bottleneck?
- Is there a secondary bottleneck after the primary idea?
- Are experiments mapped to claims rather than presented as table narration?
- Are strong adjectives supported by mechanisms or numbers?
- Are LaTeX commands, citations, labels, equations, and macros preserved?
