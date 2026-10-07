# Section Playbooks

## Abstract

Compress the paper into a clear argument about the problem, essential insight, mechanism, and evidence. Explain the real objective rather than replacing it with an incidental benefit such as throughput.

Keep only advantages prepared by that argument. Describe the insight rather than a list of implementation components. Use `Across ...` to introduce evaluation scope, avoid parenthetical benchmark insertions, report the key supported numbers, and end with their implication for the contribution.

Use the length and sentence structure the argument needs. Pair quality with cost or another metric when the claim is about that trade-off, not as a compulsory pattern for every paper.

## Introduction

Expand the abstract's logic consistently. Establish the significance of the problem, the relevant prior practice and limitation, and the reasoning behind the insight before explaining the method. Give each paragraph a clear task and keep the method overview concise enough to serve the introduction.

Summarize shared assumptions rather than collecting citations or forcing a taxonomy. A figure, concrete scenario, or number can provide the necessary context when available.

Prefer verbal explanations in the introduction. Add a formula only when it has an irreplaceable explanatory role. Put formal definitions in preliminaries or the method when appropriate, and retain finalized equations during edits.

Write contributions as research claims supported by the paper. Choose their number from the actual contributions rather than a preset count.

## Related Work

Position the paper through the closest methods and the assumptions relevant to its question. Use categories only when they clarify the comparison. Represent prior work fairly, attach citations to the claims they support, and explain the difference that motivates this paper.

Avoid unsupported claims that no one has studied the problem. A paragraph need not end with a criticism when background or a complementary result is its purpose.

## Method

Open with an overview of the actual approach and its relationship to the insight. Define the problem and quantities needed to understand the design. Explain mechanisms in an order that makes their dependencies clear.

For each substantive design, explain its purpose, actual operation, and consequence. Include a naive alternative, failure analysis, or additional mechanism when it materially explains the choice. Let the method determine the number of subsections.

### Equations And Pipelines

Explain why a quantity matters before formalizing it and state an equation's role in plain language. Keep notation consistent. Use algorithms for procedures that benefit from explicit steps and pipeline figures for coordination or interactions.

## Experiments

Start from the questions each experiment answers and the claims it can support. Explain benchmarks, baselines, metrics, hardware, training or inference settings, and the sample sizes needed to interpret the comparison. Compression must not remove important settings or sample counts.

Use the main text for decisive comparisons and trends. Place full result matrices and supporting detail in the appendix, with clear references from the text. Retain materially contradictory results and conditions needed to interpret headline findings.

Order results to answer the paper's questions. Include hard cases, generality tests, ablations, or diagnostics when relevant to those claims. Report actual trade-offs. Distinguish observed associations from supported causal explanations.

## Figures And Captions

Understand the method or experiment before drawing. Decide what the reader should learn and make the relationships clear.

- A teaser communicates the central insight and why it matters.
- A method figure explains the mechanism, flow, and important dependencies.
- An observation or diagnostic figure establishes a relevant pattern or explains behavior.
- A result or ablation figure answers a specific empirical question.

Use consistent symbols, readable labels, and arrows with clear meanings. Distinguish training from inference, inputs from outputs, and measured results from conceptual illustrations when relevant. Choose editable or image formats according to the request.

A caption should state the takeaway and the setting needed to interpret it. Define axes, units, sample sizes, and uncertainty when applicable rather than narrating every number.

## Conclusion

Return to the resolved problem, the essential insight, and what the evidence establishes. Add no new unsupported claim. Include factual, relevant limitations or other venue-required material without a stock defensive ending.
