---
name: top-conference-paper-writing
description: Draft, revise, and audit top-conference papers in machine learning, computer vision, VLA, robotics, and embodied AI, preserving claims, equations, citations, and table values while producing concise, non-defensive English and aligned Chinese comparison notes. Use for experiment narration, ablation organization, terminology consistency, and final manuscript cleanup.
---

# Top Conference Paper Writing

Treat the manuscript as a publication argument. Make the central contribution easy to identify, connect each experiment to a concrete question, and end each result paragraph with the implication supported by the data. Do not turn the paper into a project log or a self-audit.

## Scope and priorities

Use this skill when the user asks to draft, revise, compress, translate, reorganize, or clean a top-conference manuscript, especially an ML, VLA, robotics, embodied-AI, or computer-vision paper. It also applies when the user wants an abstract, introduction, method, results, ablation, conclusion, LaTeX cleanup, or bilingual original/revised comparison.

Keep the author's claims, reported numbers, experimental scope, equation definitions, table values, labels, and citation keys intact unless the user explicitly changes them. Never invent an experiment, metric, result, citation, or implementation detail. If a result is provisional, label it as such in the table or prose instead of silently presenting it as measured.

## Writing workflow

1. **Identify the paper's claim.** State the problem, the bottleneck, the proposed mechanism, and the evidence that establishes its value. Organize paragraphs around a question, setup, result, and interpretation. Remove repeated setup lists when the surrounding context already fixes them.
2. **Strengthen the English.** Prefer direct active sentences, concrete nouns, and short causal links. Use the method's name or “we” when the paragraph reports the authors' analysis. Remove hedging, apology-like language, defensive caveats, and generic claims of significance. Keep methodological limits that are necessary for accuracy.
3. **Make experiments do argumentative work.** Distinguish component, distillation, token-allocation, budget-sensitivity, and role-retention questions. State the comparison condition before the result, report the measured direction and split-level evidence, then give one plain-language interpretation. Do not repeat a conclusion already established by the next sentence.
4. **Maintain a terminology ledger.** Pick one name for each mechanism and use it in headings, tables, captions, prose, and Chinese notes. Keep model names, dataset splits, metrics, and mathematical symbols unchanged. Read [references/ablation_and_terminology.md](references/ablation_and_terminology.md) when the task involves ablations or terminology decisions.
5. **Produce bilingual comparisons when requested.** For every segment, keep the original English, revised English, original Chinese, and revised Chinese aligned. Chinese must express the same claims, conditions, numbers, citations, and equations; it may be more natural syntactically, but it must not add or weaken evidence. Keep LaTeX equations and citation keys in copyable form.

The domain patterns and reusable decisions extracted from this workflow are collected in [references/embodied_ai_writing_patterns.md](references/embodied_ai_writing_patterns.md). Read it when the manuscript concerns VLA, embodied AI, robotics, visual decision making, or adaptive computation, or when the user asks for a comprehensive consistency pass. The reference is a distilled rulebook rather than a transcript; adapt examples to the current method.

## LaTeX and final-manuscript cleanup

When given a final LaTeX source, remove full-line commented-out material. Preserve escaped percentages (`\%`) and syntactic line-continuation markers such as the `%` in `\resizebox{...}{...}{%`; they are not discarded prose. Do not alter active equations, `\label`/`\ref` pairs, table numbers, or numeric cells as a side effect of comment removal.

Before delivery, check:

- no full-line comments from the discarded draft remain;
- every display equation and label is still present and in the intended order;
- table numbers and reported metrics are unchanged;
- every citation key is available in the referenced BibTeX file, or the missing key is reported;
- fixed budgets, adaptive budgets, and reported means are not conflated;
- the bilingual comparison has the same paragraph count and no missing equations.

Compile the manuscript when a complete preamble and bibliography are available. If the user supplied only a body fragment, perform structural and text checks and state that a full compilation was not possible. Deliver the cleaned `.tex` plus the requested comparison artifact (HTML or Markdown) when the workflow calls for it.

## Style decisions from the working pattern

Use a concise, publication-facing table vocabulary. `Configuration` is a suitable first-column heading; avoid unnecessary `Variant` labels and avoid putting implementation explanations into long row names. Put configuration details in the caption or the paragraph when a short row label is unambiguous. For a distillation study, a short row such as `No distillation` can be defined in the caption or first mention rather than expanded into a long table label.

For comparisons involving a dynamic budget, call a constant value a **fixed budget** and call the dynamic setting's reported statistic its **mean budget**. Do not call a fixed reference a “matched budget” unless it truly matches another method's measured average. Name the actual mechanism—such as evidence scoring, adaptive budgeting, or role-aware retention—instead of using a vague umbrella term such as “control-aware selection”.

Keep the final synthesis sentence when it states the paper's contribution, but remove nearby sentences that merely restate that the comparison was performed. End with the evidence-backed mechanism and its navigation or efficiency implication, without adding a new unmeasured claim.
