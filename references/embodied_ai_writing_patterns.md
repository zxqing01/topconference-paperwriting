# Writing patterns for embodied AI and visual decision papers

This reference generalizes the working pattern behind the skill to a research direction rather than one manuscript. It applies to VLA, vision-language navigation, visual control, robot learning, embodied agents, adaptive visual computation, and related computer-vision systems.

## Core narrative

Use an evidence chain that a reviewer can follow:

1. **Task pressure:** what the agent must perceive, reason about, and control, and what resource or reliability constraint matters;
2. **Closed-loop or interactive difficulty:** how an action changes future observations, state, or available evidence;
3. **Gap:** why static compression, one-shot perception, or a current-step-only heuristic is insufficient;
4. **Method:** the smallest set of mechanisms that addresses the gap;
5. **Evidence:** task performance, efficiency, robustness, and ablations that isolate each mechanism;
6. **Implication:** what the results establish about the design principle.

The introduction should not read as a catalogue of modules. Give each component a role in the causal story and reserve implementation detail for the method section.

## Section-level guidance

### Abstract

Move from problem to method to evidence. Mention the interaction or closed-loop constraint when it is central, then name the main mechanism(s), give one or two verified outcomes, and compare efficiency with a named reference system. Use `baseline` when the reference is a baseline. Do not crowd the abstract with every split or every ablation.

### Introduction

A strong sequence is:

- task and computational or control bottleneck;
- why future observations, action feedback, or long-horizon reasoning makes the problem harder;
- the precise gap in existing methods;
- the proposed idea and how its stages address the gap;
- concise contributions tied to measurable evidence.

Start contribution paragraphs with “We” when reporting the authors' design or analysis. Avoid a first sentence that lists many controlled variables; summarize the purpose first.

### Related work

Organize by the limitation the new method addresses: efficient representation learning, visual token compression, adaptive computation, visual distillation, embodied decision making, or closed-loop control. Do not list papers without a comparison axis. End each related-work group with the unresolved issue relevant to the method.

### Method

Define inputs, outputs, symbols, and the control-time index before describing modules. Explain what is trained, frozen, or deterministic. If a selection or allocator has no trainable parameters, state that as a property of the design and explain how scores, budgets, and constraints produce the retained set. Keep equations adjacent to the variables they define.

### Experiments

Separate the questions answered by the main table, qualitative examples, component ablations, supervision ablations, compute studies, and robustness or budget studies. Each paragraph should state the comparison condition, the result, and the interpretation. Do not repeat the complete experimental setup in every paragraph.

### Conclusion

Restate the design principle and the strongest verified outcomes. End with the contribution's significance for the target task or research direction. Avoid generic praise, deployment guarantees, or a new claim that was not evaluated.

## Style and reviewer-facing discipline

Write confidently without overstating. Remove unnecessary “we evaluate whether”, “these results support”, and “it is worth noting” phrases when the result itself is sufficient. Avoid apology-like limitations, speculative reviewer objections, and defensive descriptions of ordinary design choices. Preserve necessary scope statements, uncertainty, and reproducibility information.

Prefer:

- concrete operations over abstractions;
- active voice over passive chains;
- one claim per sentence when the paragraph is dense;
- a measured direction and magnitude over “improves performance” alone;
- a mechanism interpretation tied to the observed comparison.

Avoid:

- AI-like parallel lists in the opening sentence;
- headings that contain redundant implementation detail;
- unexplained shorthand in table rows;
- a conclusion that merely repeats the experiment setup;
- a Chinese translation that is stronger, vaguer, or more specific than the English.

## Reusable terminology and consistency checks

Build a project-specific ledger before editing. Record the canonical form of:

- the method name and acronym;
- the reference system and baseline wording;
- task and dataset split names;
- metrics, units, and statistical summaries;
- module names and headings;
- fixed, adaptive, mean, per-step, and compute budgets;
- teacher, student, expert, and frozen/trainable components.

When a heading is shortened—for example, from a detailed mechanism name to `Adaptive budget`—check the body, caption, table, and Chinese comparison for wording that now conflicts with the shorter scope.

## Final audit

Before submission or handoff, verify the claim-evidence chain, terminology, numerical consistency, citation coverage, equation references, table labels, and bilingual alignment. If the source is only a LaTeX fragment, run structural checks and say that a full compilation was not performed. Do not silently repair missing data or citations.
