---
name: topconference-paperwriting
description: Draft, revise, and check conference research papers in machine learning, computer vision, NLP, robotics, and related fields. Use for manuscripts or individual sections, citation-only edits, method and appendix clarity, experimental narration, LaTeX layout, bilingual revision comparisons, and evidence-grounded submission or reviewer-style checks. Adapt to the author's language, target venue, and year.
---

# Top Conference Paper Writing

One integrated skill for a whole paper or a local edit. Build an accurate, persuasive publication argument: a consequential problem, a specific gap, an identifiable contribution, and evidence that supports it. Adapt the structure to empirical, theoretical, systems, or benchmark work. A venue does not have one mandatory prose style.

## 1. Establish the task without expanding it

Use the conversation and supplied artifacts to identify the active version, requested section, permitted operation, and target venue/year. Do not require a questionnaire when these are already clear.

| Request | Scope of work |
|---|---|
| Explain / assess / compare alternatives | Read and answer; do not silently edit files. |
| Draft or substantially revise | Organize the argument within the available evidence; mark missing inputs in author notes. |
| Only necessary changes | Correct factual errors, contradictions, undefined notation, broken references, or meaning-blocking ambiguity. Keep optional style changes separate. |
| Only add citations | Add citation commands and necessary bibliography entries; preserve all existing prose, numbers, and equations. |
| Change tense / delete one sentence / shorten a line | Make the smallest requested edit and check its immediate dependencies. |
| Update HTML / LaTeX / PDF | Identify the authoritative text and synchronize the requested artifacts using the delivery guide. |
| Review as a referee | Evaluate the research from the supplied evidence, using the review guide; do not automatically rewrite it. |

Treat restrictions as local to their stated scope: a main-text minimal-edit instruction does not automatically prohibit fuller appendix clarification. Later instructions supersede earlier ones. A comparison page's proposed revision is not evidence that the author accepted every change. Do not restore a rejected paragraph or change settled wording as a side effect of regeneration.

Preserve original comparison panels and user-authored material. Do not remove comments, appendices, declarations, files, or references merely because a generic cleanup rule suggests doing so. An appendix-only assignment does not authorize unrelated declaration changes. Required dependent repairs, such as resolving references to a deleted section, remain within scope.

### When drafting a new paper from notes

Separate established work from proposed experiments and ideas. Build an outline around the central question and map each intended claim to available evidence. Use the paper type to choose sections rather than filling a fixed template. Draft the method or theoretical argument and the evidence-bearing sections precisely, then align the introduction, abstract, and conclusion with what they establish. An outline is a working aid, not a mandatory approval gate. Ask for missing facts only when they prevent a sound draft; keep unknown settings and results in explicit author notes rather than fabricating them in publishable prose.

## 2. Route to the relevant chapter

Read only what the task needs. For a full manuscript, read the applicable guides in manuscript order rather than loading every specialized topic at once.

| Section or operation | Detailed guidance |
|---|---|
| Title, abstract, introduction, contribution structure | [Opening sections](references/opening-sections.md) |
| Related work, source verification, citation-only edits, BibTeX | [Related work and citations](references/related-work-and-citations.md) |
| Method, mathematical notation, algorithms, theory details, appendix, main-text cross-references | [Method and appendix](references/method-and-appendix.md) |
| Setup, baselines, main results, ablations, qualitative examples, efficiency, terminology | [Experiments and results](references/ablation_and_terminology.md) |
| Conclusion, limitations, statements | [Closing sections](references/closing-sections.md) |
| Tables, captions, equations, layout compression, bilingual HTML, artifact updates | [LaTeX and delivery](references/latex-and-delivery.md) |
| Venue/year rules, published-paper examples, full consistency checks, referee reports | [Verification and review](references/verification-and-review.md) |
| VLA, navigation, robot control, visual compression, adaptive computation | [Embodied-AI specialization](references/embodied_ai_writing_patterns.md) |
| Optional author preferences for language, editing scope, and delivery | [Author preferences](references/author-defaults.md) |

## 3. Keep evidence and writing synchronized

For a substantial revision, maintain a compact working ledger, not a compulsory deliverable. Track:

- **Claims:** what is asserted; supporting result, derivation, source, or implementation; relevant condition.
- **Terminology and quantities:** canonical names, baselines, splits, units, aggregation, fixed versus adaptive values.
- **Notation and references:** symbol meaning, first definition, dimensions, labels, and the exact section an outgoing reference promises.
- **Versions and decisions:** authoritative source, accepted changes, local constraints, generated artifacts.

Use the latest supplied manuscript unless the user designates another authority. Existing audit reports and generated HTML help locate evidence; they do not replace raw code, tables, or original sources. If code and manuscript conflict, identify the concrete conflict before changing either. Distinguish source inspection, recalculation, execution, compilation, and visual verification; claim only what was done.

Never invent an experimental setting, run, metric unit, statistic, citation, theorem, or implementation detail. Preserve verified numbers and claims through stylistic edits. A demonstrated error may be corrected when within the requested scope, with the correction made explicit. Do not conceal uncertainty by fluent rewriting.

## 4. Write with a clear research voice

Lead with the substantive point. Prefer concrete operations and results to module catalogues, repeated setup lists, and generic praise. A paragraph can end on a result; do not append a compulsory sentence such as “These results support our method.” Add an interpretation only if it contributes information and the evidence supports it.

Choose the subject for the sentence's function: **we** for an author action; a **method or component** for its behavior; a **figure or table** for displayed evidence. Do not force every paragraph to begin with one form. Use present tense for method descriptions and reported table/figure findings when that fits the manuscript; past tense remains appropriate for completed procedures or historical work. Uniformity must preserve temporal meaning.

Keep contribution ownership clear while crediting borrowed components. Avoid defensive digressions and speculative objections in paper prose, but preserve actual assumptions, meaningful limitations, null results, and measured uncertainty. Do not turn “preserves” into “improves,” “mean best” into “best on every split,” or an observed association into a proven mechanism without evidence.

When the user asks to follow another paper, inspect the relevant passage. Explain which stylistic choice transfers and which factual or mathematical distinctions still apply. Published precedent is evidence of usage, not proof of correctness or a venue requirement.

## 5. Deliver the requested change and verify proportionately

A sentence edit usually needs a semantic and grammar check, not a full paper audit. Equations, statistics, source attribution, or artifact changes need the corresponding targeted checks. A full-paper assignment needs the cross-section review in [Verification and review](references/verification-and-review.md).

For bilingual output, align claims, conditions, scope, quantities, citations, and equations. For before/after HTML, the default is original on the left, revision on the right, English above Chinese. Keep the clean reading version free of internal review notes.

For file work, finish the authorized changes, validate the affected artifacts, and provide the actual updated files with concise status. Do not say a PDF was compiled or a layout fixed when only its source changed. If required inputs or tools are unavailable, deliver the useful verified portion and identify the exact missing check. Optional polishing must not delay a small completed edit.
