# Press-conference principle and defensive-writing review

Treat a paper as an academic press conference. Find the work's strongest established contribution and build the most persuasive argument the evidence supports. Organize the reader's understanding around that contribution rather than distributing attention evenly across everything the authors tried.

Use these principles throughout manuscript drafting, revision, compression, and experimental organization. For a local edit, apply them to the requested passage. A request to inspect writing calls for findings and suggested revisions, not automatic file changes. A referee report still evaluates the research independently under [Verification and review](verification-and-review.md).

## Nine writing principles

1. **Build around the strongest advantage.** Identify what makes the work worth publishing, such as a new capability, problem, mechanism, perspective, useful operating regime, lower cost, or better tradeoff. Make this the organizing contribution. Keep supporting contributions when they help establish it; avoid treating every implementation detail as an equally important achievement.

2. **Present the argument rather than the development history.** Explain why the problem matters, what is missing, how the idea addresses it, and what establishes its value. Omit a chronology of attempted designs, debugging, and unsuccessful trials unless a particular observation is necessary evidence for the research claim. Organize experiments by the questions they answer.

3. **Remove needless self-undermining language.** Flag apology-like framing and broad negative judgments such as “unfortunately,” “only,” “still substantially behind,” “limited effectiveness,” “遗憾的是,” “仅,” “仍明显落后,” or “效果有限” when they weaken a statement without adding precision. Do not summarize weaknesses on an imagined reviewer's behalf or turn a local observation into a verdict against the whole method. These are contextual cues, not forbidden words: “uses only 64 tokens,” for example, may state the central efficiency advantage accurately.

4. **Choose comparisons that test the actual contribution.** A paper about efficiency, a new capability, or a constrained application need not compete primarily for an unrelated accuracy record. Use task-relevant dimensions, resource constraints, operating conditions, or comparison scopes that reveal the work's value. Explain why they matter. Keep comparison conditions transparent and retain the measurements needed to interpret the claim; changing the narrative focus does not justify altering a protocol after seeing its results or concealing a material metric.

5. **Explain outcomes through the actual objective and supported tradeoffs.** For a nonleading result, first decide whether prose discussion is needed to interpret the evidence. If it is, state the relevant objective, constraints, or measured tradeoff concretely. Narrow an overbroad claim instead of attaching an apology. Avoid language that treats one metric as a defeat of the entire approach. Do not invent an objective, causal explanation, or favorable tradeoff that the study does not establish.

6. **State the advantage explicitly.** Tell readers what improves, relative to which reference, under what conditions, and why the difference matters. Do not expect them to infer the contribution from a table. Explain a mechanism when the evidence supports it; otherwise distinguish the observed benefit from its proposed explanation. Claim strength comes from the specific result, not promotional adjectives.

7. **Give every experiment an argumentative role.** Each included study should establish the central result, isolate a relevant design or mechanism, demonstrate value in the target setting, test scope or a meaningful tradeoff, or address a plausible alternative explanation. Identify its question and what the result supports. When authorized to organize the paper, remove, compress, relocate, or redesign material that has no useful role. A result that challenges the central claim still has an evidential role and must not be discarded merely because it is unfavorable. Do not delete experiments during a wording-only task.

8. **Open with the problem, gap, idea, and strongest evidence.** Abstracts and introductions should establish these facts early, with enough context for the contribution to be understood. Avoid opening with implementation inventories, a long research history, or defensive qualifications before the contribution has been explained. Adapt the progression to the paper type and available evidence using [Opening sections](opening-sections.md).

9. **End by reinforcing the established contribution.** The conclusion should leave readers with what the work addresses, the central idea, the strongest supported outcome, and its significance. Do not introduce a new self-negating verdict or unexpectedly enlarge the limitations in the closing sentence. Put material scope conditions and required limitations in the section where they help readers interpret the result, following [Closing sections](closing-sections.md).

## When the evidence does not support the original story

Within the authorized revision scope, use the following order of decisions:

1. Remove prose unrelated to the central research claim.
2. Narrow the claim to what the evidence actually establishes.
3. Identify a task-relevant evaluation dimension or constraint that expresses the contribution more clearly.
4. Explain supported differences in goals or measured tradeoffs.
5. Reorder the evidence so the strongest result and its supporting studies are easy to see.
6. Rebuild the title, abstract, introduction, and experimental argument when a substantial rewrite is authorized and the established contribution differs from the original plan.

The narrative may change; verified numbers, comparison conditions, material uncertainty, and evidence affecting validity retain their meaning. State a necessary qualification once, precisely, where it belongs. This principle improves how an honest research argument is presented.

## Diagnose defensive writing passage by passage

Use this procedure when the author asks to find defensive writing, self-undermining expressions, or unnecessary reviewer-facing explanations.

1. Read the supplied passage and enough surrounding material to identify its claim, evidence, and purpose. Cover the whole supplied scope without inventing missing results.
2. Locate each passage containing an unnecessary disclaimer, repeated hedge, apology, negative topic sentence, premature limitation, speculative reviewer objection, or unsupported generalization from a local weakness. Also check whether procedural narration, an irrelevant competitive claim, or an experiment without a clear question obscures the contribution.
3. Distinguish a removable expression from a necessary scope condition, genuine uncertainty, factual comparison, or material limitation. Diagnose the function rather than replacing words mechanically. Preserve necessary information and revise its placement or phrasing when that helps.
4. For each actual issue, give the location, original wording, why it weakens or distracts from the argument, and a concrete revision. A table is useful for multiple findings:

   | Location | Original wording | Issue and reason | Suggested revision |
   |---|---|---|---|

5. Make the smallest revision that advances the claim accurately. Delete empty framing, state a positive scope, quantify an established advantage or tradeoff, or narrow an unsupported claim. If a truthful rewrite needs missing information, identify that specific fact outside the proposed paper text.
6. When several sentences share one structural problem, explain it once and show how each affected passage changes. Return a complete revised paragraph when requested. If the supplied text has no unnecessary defensive writing, say so without manufacturing findings.

For Chinese discussion of an English manuscript, explain findings in Chinese and give revisions in English unless the author requests another format. Keep diagnostic comments outside publishable prose.

## Revision examples

The figures below are illustrative. Use such wording only when the manuscript's own evidence supports it.

| Defensive or distracting wording | More useful revision |
|---|---|
| Unfortunately, our method still falls behind the strongest baseline in accuracy. | At half the inference cost, the method achieves 79.8% accuracy, compared with 80.4% for the baseline. |
| We only evaluate on urban routes, so the results may have limited generality. | We evaluate navigation on urban routes spanning the reported scene and route conditions. |
| We first tried several allocation strategies and then added the memory module. | The ablation measures how temporal memory changes allocation at a fixed token budget. |

The second example fits a descriptive scope statement; it cannot replace a substantive applicability limitation when that limitation changes the paper's claim. Necessary numeric comparisons and relevant limitations remain available to the reader.

## Final narrative check

- Is the strongest supported contribution clear, including why it matters?
- Does each section and experiment advance a named part of the argument?
- Does any sentence answer a hypothetical objection without adding useful evidence, scope, or explanation?
- Has a local weakness become an unnecessarily broad negative judgment?
- Do the opening and conclusion emphasize the same established contribution?
