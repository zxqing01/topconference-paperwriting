# Title, abstract, and introduction

## Before composing

Recover four facts from the supplied material: the research problem, the specific unresolved obstacle, the proposed idea, and the strongest evidence. For theory, evidence may be a theorem with conditions; for systems, a measured operating regime; for a benchmark, a new evaluation capability rather than a model improvement. Do not impose a two-stage architecture or a compression narrative on unrelated work.

If essential results are absent, draft the supported problem and method portions and place the missing evidence in an author note. Do not fill numerical slots with plausible values. For sentence-level requests, use the surrounding paragraph rather than reconstructing the whole paper.

## Title

A title should identify the contribution and task clearly enough to distinguish the paper. A method name plus a descriptive phrase is one option, not a required formula. Check acronym expansion, capitalization, mathematical superscripts, and consistency across PDF, source, and submission metadata.

Prefer a precise scope over a string of favorable adjectives. “Efficient,” “robust,” or “general” needs corresponding evidence in the paper. A claim about inference efficiency should not silently become one about training efficiency. Do not change a user-approved title during a local body edit.

## Abstract

Use a connected argument, with length set by venue and content rather than a fixed sentence count:

1. Establish the task and consequential problem.
2. Explain the specific obstacle that the new idea addresses.
3. Introduce the contribution and enough mechanism to make its distinction intelligible.
4. State the strongest verified result or theoretical guarantee with its reference condition.
5. Include an implication only if it adds to the result.

Keep the method's identity stronger than its list of modules. Explain what a component contributes instead of enumerating every loss, cue, threshold, and safeguard. Avoid an abstract that assumes the reader already knows an internal baseline or an undefined acronym.

When reporting a gain, verify all of the following together:

- which reference system produced the denominator or starting value;
- whether the reported value is from one split, an aggregate, or a best run;
- whether a change is absolute or relative;
- whether resource reductions use the same benchmark and measurement conditions as the cited table.

For example, a rate increasing from 40% to 44% gains **4 percentage points**, or **10% relative**. It is not a 4% relative gain. If short notation is needed, report the endpoints or explicitly name an absolute gain. Another paper's loose notation is not a reason to change the arithmetic meaning.

Do not add citations to a venue's abstract automatically. Inspect the target instructions and the role of the citation. Definitions or named borrowed methods can often be supported at first use in the body.

## Introduction

Let the opening explain why the problem matters, then narrow to the obstacle that motivates this paper. Describe prior approaches accurately before identifying the unresolved issue. Avoid universal assertions such as “all existing methods ignore history” unless the source coverage supports them.

A useful progression is task pressure → specific bottleneck → gap in the relevant alternatives → central idea → evidence and contributions. It is a flexible sequence: theory, dataset, and systems papers may need a different opening to make the question intelligible.

Explain the idea before implementation details. For multiple components, give each a reason to exist and explain their relationship; do not merely repeat their names. Keep detailed training schedules, thresholds, and operator definitions in the method or appendix unless needed to understand the idea.

Separate three kinds of sentence:

| Sentence function | Appropriate support |
|---|---|
| Prior fact or known limitation | A source that actually supports the claim |
| New design or contribution | The authors' explanation, with attribution only for borrowed ingredients |
| Claimed empirical advantage | The paper's result and its stated comparison condition |

Do not attach a foundational citation to the end of a sentence announcing an entire new mechanism if that makes its ownership ambiguous. Move the citation to an existing background clause where possible; a citation-only task cannot authorize rewriting the sentence to make room.

## Contributions

Use a short paragraph or a list when it helps readers distinguish contributions. Do not impose exactly three bullets or force each bullet to start with “We.” Each contribution should be more than an implementation step: identify the idea, capability, resource, or finding, and how the paper establishes it.

Map each contribution to a method section, theorem, dataset, or experiment. A component ablation can support a design choice; it does not by itself prove every causal explanation. Avoid inflated novelty language or priority claims without a defensible literature search.

## Common local revisions

- If asked to change only tense, change the finite verbs and necessary agreement; preserve numbers, comparison targets, and paragraph organization.
- If asked for a “We” opening, an author-action formulation such as “We examine … in Figure …” is acceptable. If that preference is later withdrawn, choose the subject that best fits the passage.
- If asked to remove a word for layout, first remove dispensable framing such as “Here,” not a condition, unit, or comparison target.
- If asked for Chinese comparison, translate the complete revised passage without adding justification inside the translation.

## Opening-section check

Read title, abstract, final introduction paragraph, main result caption, and conclusion together. They should identify the same method, problem, comparison baseline, and contribution scope. Similar purpose does not require identical sentences. Correct a contradiction; do not mechanically repeat the abstract in every section.
