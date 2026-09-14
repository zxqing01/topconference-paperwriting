# Ablation and terminology reference

Use this reference for machine-learning, computer-vision, VLA, robotics, and embodied-AI papers. The labels below are examples; replace them with the method's actual mechanisms and keep the comparison logic.

## Ablation story

### Component contributions

Open with the comparison purpose rather than a long list of controls. Explain that the table isolates the main components under a common setup, then report:

- what each component changes;
- how the combined system compares with the reference system;
- the measured navigation, accuracy, efficiency, or latency changes;
- why the components are complementary.

Move backbone, data, observation, action, and evaluation details to the experimental setup when repeating them would make the paragraph list-like.

### Teacher or representation distillation

When a paper compares teacher supervision, keep row names short and define them once:

| Table label | What the caption or first mention should define |
|---|---|
| `No distillation` | A student or compressed encoder is used without teacher supervision. |
| `Teacher A` | Distillation uses the first teacher or knowledge source only. |
| `Teacher B` | Distillation uses the second teacher or knowledge source only. |
| `Dual teachers (ours)` | The complete objective uses both knowledge sources. |

Use different labels when the paper has different supervision types. The principle is to keep the table scannable and explain implementation details in prose or the caption.

### Token selection, budget, and retention

Separate the questions instead of mixing all ablations into one paragraph:

1. Does the proposed ranking or selection rule beat a random or dense reference at a fixed compute budget?
2. How does changing the fixed budget affect the task metrics?
3. Does an adaptive budget improve over a constant reference at a comparable reported cost?
4. Does a role, view, safety, or coverage constraint help relative to removing that constraint?

For a step-dependent quantity, write a symbol such as `K_t` for the value at step `t`; write a fixed value such as `K=K_0` for the constant comparison. If the adaptive setting reports a mean, call it the mean budget or mean compute, not a fixed budget. Use "at this fixed budget" for a fixed comparison and "compared with a fixed budget of ..." for an adaptive comparison.

Report the observed pattern directly: name the relevant split or task, give the measured difference, and state the simplest mechanism interpretation. Remove a sentence that only announces what the comparison tests when the setup is already clear. Keep a short synthesis sentence if it connects the components to the central contribution.

## Preferred vocabulary

- Name the actual mechanism: `evidence scoring`, `uncertainty-based allocation`, `adaptive budgeting`, `role-aware retention`, `coverage constraints`, or the paper's own term.
- Use `Configuration` for a neutral first-column heading when rows are complete settings.
- Use `Variant` only when the paper genuinely studies variants of one method and the label improves clarity.
- Keep `baseline` for a named reference system; omit `configuration` when the reference is already unambiguous.
- Use short labels such as `No distillation`, `Teacher A`, and `Full model` only after defining what is included or omitted.
- Distinguish `fixed budget`, `mean budget`, `per-step budget`, `compute`, `FLOPs`, and `latency` rather than treating them as synonyms.

For Chinese comparison notes, use direct descriptions of the operation. Prefer phrases such as "selection based on multi-cue evidence scoring" or "the allocator without this constraint" when they are more precise than an abstract label. Avoid calling a configuration a "variant" when a direct name is clearer. Add a summary marker such as "overall" only when the sentence provides a genuine synthesis.

## Bilingual consistency checklist

The revised English and revised Chinese should agree on:

- the comparison direction and reference condition;
- task splits, metrics, units, and statistical summaries;
- whether a resource number is fixed, per-step, or a reported mean;
- teacher, student, expert, or module roles;
- equation symbols, citation keys, table and figure references;
- the final interpretation, without adding a stronger claim in Chinese.
