# Specialization: embodied AI, visual decision making, and adaptive computation

Use only for papers in which these concepts apply. The general chapter guides remain authoritative; this file does not impose a navigation or two-stage compression story on other fields.

## A domain-specific argument

For a perception-action system, connect the computational bottleneck to the task: the agent receives observations, acts, and changes the observations available next. Explain why the proposed use of state, history, representation, or resource allocation addresses a specific limitation.

Closed-loop context is not itself proof of novelty. Distinguish what is new in the decision rule, representation, feedback path, training signal, or evaluation. Avoid claiming that all visual compression methods are static or context-free without a literature basis.

For complementary stages, identify the computation each stage changes. Representation extraction and downstream sequence processing may address different costs; state their relationship without assuming the sum of isolated latency savings equals the joint saving.

## Inputs, tokens, and sequence construction

Keep image resolution, patch size, token-grid size, concatenated view layout, feature width, and language-model sequence length distinct. Removing a class token or register tokens changes sequence composition; it does not change a patch grid's spatial dimensions.

Describe the actual selected encoders. Replace vague “any prefix tokens” wording with a concrete statement when the checkpoint and output path are known. Conditional wording remains valid for a genuinely generic implementation. A pretrained dataset identifies the checkpoint's training provenance, not necessarily the authors' task-specific training.

Explain whether two views share a composed grid, are separately encoded, or are concatenated as sequences. Do not infer semantic coordinates from row indices alone.

## Distillation and adaptation

State teacher/student roles, branch dimensions, translator behavior, frozen/trainable modules, and which path remains at inference. Separate teacher pretraining, student initialization, representation distillation, and downstream policy adaptation.

For token losses, identify matching axes, normalization, feature scales, and whether relation matching compares token-token or sample-sample structure. A citation to a loss family does not establish an exact custom objective.

## Dynamic token allocation

Distinguish:
- a dense visual-token grid;
- a candidate set with a scoring cue;
- an initial reserve;
- quotas or additional selection stages;
- the final retained set and its ordering;
- the per-step budget and the statistic reported in a table.

A score equal to one at every anchor candidate does not mean every candidate is reserved. Check loops, duplicates, indexing, top-k, quotas, and capacity before explaining the count. State row/column intersections explicitly when natural language could imply entire rows or columns.

Check where allocation happens relative to the projector and backbone. Dense operations before selection remain dense. Padded batches may execute at the largest retained count in the batch; masked padding prevents unwanted attention contributions but does not automatically yield ragged-compute savings.

For masking, verify what positions are masked as keys/values, what padded-query outputs are ignored, and how the loss or output path treats padding. Do not infer a complete implementation from a generic sentence about an attention mask.

## Sequential execution

Differentiate history features, temporal scores, previous actions, decoder caches, and environment state. A cache inside one autoregressive call does not imply reuse across successive observations or control steps.

If a mode raises the budget, distinguish its trigger, its requested minimum, and the final count after caps or other rules. An observed trace without activation is not evidence that the trigger is unnecessary or defective. Explain only the mechanism needed to interpret the plotted case.

## Baselines and resources

An external model result and an internal dense control can legitimately use different configurations. Document their roles and interpret each comparison accordingly. An ablation should not be compared against a different baseline merely because their names sound similar.

Keep task success, path quality, FLOPs, latency, memory, energy, and deployment rate distinct. Simulated evaluation does not alone establish real-world flight performance. FLOP savings do not numerically imply the same latency reduction.

A complete control loop may include rendering, sensing, transfer, state initialization, and action application beyond neural inference. Define the timer boundaries actually used; do not label a partial pipeline as an entire real-world control cycle.
