# Revision

## Story Check

Before rewriting, answer:

- What is the bottleneck?
- What prior assumption fails?
- What observation justifies the method?
- Which module solves which bottleneck?
- Which experiments support each claim?
- What will a skeptical reviewer attack?

If one answer is missing, mark it as a story gap before polishing.

## Paragraph Repair

Use this order:

1. State the paragraph role in the first sentence.
2. Define key nouns before reusing them.
3. Ensure each sentence follows by cause, contrast, consequence, example, or refinement.
4. Remove claims that do not map to evidence.
5. End with the implication for the next paragraph.

For style transfer, also check whether the paragraph performs one recognizable move:

- capability -> constraint;
- prior grouping -> mismatch;
- observation -> design;
- naive extension -> failure;
- mechanism -> advantage;
- result -> attribution.

If the move is unclear, rewrite the topic sentence before polishing local wording.

## Claim-Evidence Map

Use:

`Claim: ... | Evidence: ... | Status: supported / needs evidence / overclaimed`

Evidence can be:

- profiling or latency numbers;
- observation figures;
- main benchmark tables;
- ablations;
- compatibility tests;
- qualitative visualizations;
- theoretical analysis.

## Language Tightening

Prefer:

- `This raises two bottlenecks: ...`
- `To address the first bottleneck, ...`
- `To operationalize this insight, ...`
- `We attribute this failure to ...`
- `These results verify ...`
- `Motivated by this observation, ...`
- `The key to [method] lies in ...`
- `Compared with [baseline], [method] ...`

Avoid:

- `very`, `powerful`, `significant`, `novel`, `effective` without evidence.
- `we can see`, `it is worth noting`, `many works`.
- long module lists before the problem is clear.
- contribution bullets that only list components.

## Strengthening Moves

- Vague motivation -> add a real deployment constraint or number.
- Flat method list -> insert bottleneck-to-module mapping.
- Weak novelty -> add an observation or failure mode.
- Weak experiment section -> group by claims instead of tables.
- Weak caption -> state the takeaway first.
- Overclaim -> weaken or request missing evidence.
