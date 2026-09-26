# Experiments, results, and terminology

Use this guide for experimental setup, main comparisons, ablations, qualitative results, and efficiency studies. Adapt the questions to the paper; do not require every category or propose new experiments during a wording-only task.

## Setup: define what the numbers mean

Give readers the information needed to interpret the reported experiment. Distinguish dataset, split, task setting, training data, evaluation protocol, and reference system. Define metrics, direction of improvement, units, and aggregation where needed. Confirm units from the actual benchmark or implementation rather than assuming a familiar acronym always has the same unit.

Keep hardware, software, precision, batch size, seeds, optimizer settings, and training duration in the appropriate setup or reproducibility section. Repetition in every result paragraph is unnecessary. A statement about evaluation hardware does not establish the training hardware.

For a dataset or benchmark contribution, explain collection, annotation, split construction, task coverage, and what the evaluation can discriminate. Report data leakage or contamination controls that were actually performed. For a systems contribution, specify the relevant workload and measurement regime. Do not force either paper type into a model-component ablation story.

Keep the unit of replication, number of runs, aggregation, and uncertainty reporting explicit when supplied. Do not invent error bars, confidence intervals, significance tests, or an unreported random-seed protocol during writing. Whether additional statistics are necessary depends on the claim and available evidence, not a universal checklist.

When abbreviations or metric names appear in prose, use the manuscript's consistent capitalization. Acronyms remain uppercase where appropriate; their expanded common-noun names do not need title case merely because an acronym follows. Do not present this editorial preference as a conference rule.

## Reference systems and fair interpretation

Distinguish published results, reproduced results, an adapted baseline, and an internal controlled reference. Give each a consistent name and record the configuration differences that affect interpretation.

For a published model and an internally configured dense baseline, check data, backbone, training, inputs, evaluation, and measurement conditions only as relevant to the comparison claim. If the manuscript already explains their different roles, recognize that explanation. Do not manufacture a flaw by treating the two names as synonyms.

An internal ablation often controls the setup to isolate a mechanism. A broad state-of-the-art table may compare systems with different configurations. Describe which question each comparison answers instead of silently assuming all tables are controlled experiments.

If display names are shortened or unified, retain material distinctions, such as a data-aggregation variant, in an accessible caption or first definition. A name change must not change which measurements are attributed to which system. A borrowed result needs a traceable source even when the method's origin is cited elsewhere.

## Main results

A useful result paragraph connects the comparison, the main observation, and its meaning. The table can carry the complete numeric record; prose should select evidence that explains the contribution.

- State the relevant reference system before a gain.
- Check every percentage against the correct table cell or underlying value.
- Name the split or aggregation when it changes the meaning.
- Distinguish “highest mean across splits” from “highest on every split.”
- Restrict “lowest cost” to the configurations and metrics actually measured.
- Treat an efficiency-performance tradeoff as such; do not hide a worse metric.
- Use “significant” statistically only when the corresponding analysis supports it.

For rates expressed as percentages, absolute change is measured in percentage points. Relative change is 100 × (new − reference) / reference. For a cost reduction, use 100 × (reference − new) / reference. If the reference is zero, do not produce an undefined relative change. Rounding can explain small differences, but inspect raw precision before claiming that it does.

Prefer present tense for the displayed findings when following a manuscript written that way: “achieves,” “increases,” “reduces.” A global tense replacement must not change descriptions of past experiments or cited historical events.

## Ablations: isolate the question

Do not narrate rows as an experiment diary. Identify what is varied, what remains comparable, and what conclusion the observed difference can support.

| Study | Question to answer | Avoid conflating |
|---|---|---|
| Component | What does each component contribute under the stated setup? | One module's effect and a simultaneous training change |
| Supervision or teacher | What changes when the learning signal changes? | Removing distillation and removing the student architecture |
| Selection or ranking | What does the ranking rule add at the stated budget? | Better ranking and a larger token count |
| Fixed-budget sweep | How does performance change with the resource budget? | A per-step constant and a dynamic average |
| Adaptive-budget comparison | What is gained at the reported cost distribution? | Approximately comparable cost and exactly matched cost |
| Constraint removal | What happens without the specified retention or coverage rule? | Removing the rule and changing unrelated safeguards |

Short row names are useful when their contents are defined. “Configuration,” “Method,” or “Variant” can all be appropriate depending on the table. Do not mandate one heading universally.

For example, “Distillation only” must specify which representation pathway remains and whether token selection is active. “No distillation” does not inherently mean no student, no teacher, or no projection. Define the actual condition.

When a component combination is strongest, report that observation. Do not call it a proven synergy or complementary mechanism solely because its score is highest. Keep a concise mechanism interpretation if both the architecture and comparison support it. Remove empty conclusions such as “These results support combining the components” when the surrounding text already makes the point.

## Qualitative examples

Read the actual figure, axes, legend, and trace before describing an example. Check initial values, transitions, step ordering, labels, and terminal events. Do not infer that a token budget starts at its maximum because it reaches that value later.

Explain what the example illustrates about behavior. A short description of a salient difference is more useful than a transcription of every point. If a case does not activate a terminal or other mode, distinguish observed inactivity from an explanation of its cause. Give a causal explanation only when conditions, logs, or code establish it.

Mention inactivity or a failure only when it helps interpret the displayed evidence. Do not add speculative failure analysis to satisfy imagined reviewer objections. Do not generalize a small set of chosen examples into a population-level claim.

## Computational efficiency

Compare costs instead of only listing them. Start with the mechanism that changes the cost and identify which computation remains unchanged.

For a Transformer with depth D, hidden width d, fixed feed-forward expansion, and n input tokens, a typical dense input-processing cost scales as O(D(nd² + n²d)). The nd² term includes token-wise projections and feed-forward work; n²d represents attention interactions. State the relevant assumptions if using this model. Architecture, sparsity, caching, and implementation can alter it.

If n = L + N becomes L + K after visual selection, explain both linear-in-length and quadratic-in-length terms when relevant. An attention-only O(n²) statement is acceptable if explicitly scoped to attention; it is not a bound on every component or a measured latency ratio. A shorter author-chosen analysis need not be expanded into a full systems derivation unless needed for correctness.

Clarify “prefill” when introduced: processing the input sequence before autoregressive output generation. Distinguish it from cached decoding within the same call and from a fresh control step. Do not assume nonvisual inputs are recomputed or reused across steps without checking the implementation.

Distinguish:
- encoder cost and translator cost;
- projection before or after selection;
- scoring/selection overhead and downstream backbone savings;
- asymptotic work, profiled operations, and measured end-to-end latency.

Drop lower-order terms only under stated scaling assumptions. Call overhead empirically negligible only with measurement or a justified bound relative to the reported regime. Small modules are not automatically negligible, and a smaller parameter count alone does not prove a strict cost inequality. A large claimed separation such as C_S ≪ C_T needs corresponding evidence.

## Timing protocol

Describe the measurement boundary as a process, not necessarily a long list. Preserve enough information to determine which work is inside the timer: start/end representation, preprocessing, transfers, model processing, output decoding, and any persistent-state initialization as applicable.

A concise form might be: “We time each decision from decoded input images to decoded policy actions, including preprocessing and transfer to the device. Scene rendering and history initialization occur outside the timed interval.” Use it only if these boundaries match the implementation.

Do not replace “disk reads are excluded” with “I/O is excluded” when device transfers are included. Removing “RGB” can be harmless if the input modality is already established; removing “decoded” can shift the apparent start boundary. Preserve hardware, precision, batch size, warm-up, synchronization, aggregation, and sampling details wherever they materially define the measurement.

## Terminology ledger

For substantial edits, track the method name, component names, reference systems, dataset versions/splits, metrics, units, and aggregation. In adaptive computation, distinguish fixed budget, per-step budget, mean budget, and measured compute. Do not call two budgets “matched” unless the stated matching criterion holds.

Propagate a label change to its caption, body mentions, figure legend, and requested Chinese counterpart. Rename only where authorized. See [LaTeX and delivery](latex-and-delivery.md) for table emphasis and artifact consistency.
