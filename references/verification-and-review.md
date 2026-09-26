# Venue verification, consistency, and reviewer-style assessment

## Match verification to the request

Do not convert a small grammar question into a full submission audit. For a broad manuscript audit, inspect research claims, technical definitions, results, citations, and presentation as separate evidence layers. For a venue-format question, focus on the current requirements and document properties.

Keep findings in three categories:
- **Confirmed problem:** the supplied material or authoritative source demonstrates an error or contradiction.
- **Unresolved question:** required evidence is missing or inconsistent; state exactly what would resolve it.
- **Optional improvement:** clarity, organization, style, or aesthetics that could help but is not required for correctness.

Do not label an optional table-name shortening, tense preference, or paragraph rewrite as mandatory.

## Current conference rules

Verify the named venue, year, and submission stage against official author instructions and style files. Submission, rebuttal, and camera-ready constraints may differ. Record the source and relevant rule when making a compliance claim; do not embed one year's page limit, deadline, or required statements as permanent skill policy.

When necessary, check main-text page counting, excluded sections, appendix location, template identity, anonymity, supplementary packaging, and required statements. Only inspect or edit unrelated declarations when the task actually includes them.

Published PDFs can demonstrate stylistic examples, but they do not override official rules. To answer “do other papers do this,” inspect the exact passages or pages and give a bounded answer such as “these examples use subsection-level appendix references.” To answer “is it common,” use a meaningful comparable sample and explain its limits. Do not infer prevalence from one convenient paper or from search snippets.

Do not claim that ICLR, NeurIPS, ICML, CVPR, ACL, or another venue mandates a particular paragraph subject, tense, best-value convention, or appendix table of contents without evidence. A short appendix may need no contents page; a long, deeply nested supplement may benefit from one.

If official rules are unavailable or ambiguous, identify that uncertainty. Offer a concrete interpretation based on available evidence rather than inventing a rule.

## Main-text and appendix consistency

Map every main-text promise to the precise appendix section that fulfills it. Check:
- definitions and coefficients both exist when both are promised;
- a timing reference actually contains the measurement protocol;
- training references distinguish stages or configurations;
- a reference to a removed section has been repaired;
- section-level versus subsection-level references match the scope.

Using “Appendix A” is appropriate for content distributed across its subsections; “Appendix A.1” can be more useful when the promised information lives entirely there. Repeated appendix references are reasonable when each occurs at a different point of need. Remove uninformative circular references, not useful navigation.

Read names, metrics, units, data splits, sample counts, operating conditions, and baseline definitions across abstract, introduction, method, result tables, captions, appendix, and conclusion. Distinguish a true discrepancy from intentional differences between training/evaluation, main results/ablations, or external/internal baselines.

## Code-to-paper verification

Find the actual relevant implementation and configuration. Use a symbol, operation, parameter name, or prior source pointer to narrow the search; do not stop at the first report mentioning a filename. Search applicable source archives or supplied attachments when the workspace contains only generated prose.

Trace the active path: defaults can be overridden, an unused function is not evidence of the executed method, and a stored report is not a fresh execution. Inspect the caller/configuration when it could change the answer.

For index construction or fixed arithmetic, independently reconstruct the result when helpful. For performance or hardware claims, static code usually cannot verify an actual experimental run. Name what each piece of evidence establishes.

If the implementation is missing, say that only manuscript consistency was checked and identify the needed file or configuration. Do not say “the code confirms” based on a LaTeX equation or an earlier agent's conclusion.

## Final-document checks

Read the compiled artifact, not only the source, for:
- title and method-name rendering;
- page boundaries and counting under the relevant rules;
- equation placement, font changes, numbering, and references;
- table width, caption association, units, and highlighting;
- bibliography completeness and appendix presence.

A successful build does not prove mathematical correctness; an attractive page does not prove template compliance. State the checks actually performed and residual uncertainty proportionately.

If asked whether a submission succeeded, distinguish choosing a file, uploading it, saving the revision, and a persisted submission with a PDF link. An existing submission number may predate the full-paper upload. A screenshot can establish only what it displays. Opening the persisted PDF and checking its pages gives stronger evidence that the intended main text and appendix were received. Do not submit or modify the live form merely because the user asks how it works.

## Reviewer-style report

When explicitly asked to act as a reviewer, use the target venue's current form and rating anchors if available. Report a research assessment rather than a formatting audit disguised as peer review.

Read the full manuscript and relevant appendix before asserting an omission. Start by summarizing the contribution accurately. Assess:
- novelty relative to the closest relevant work;
- technical soundness and assumptions;
- whether experiments or proofs support the central claims;
- importance and likely value to the field;
- clarity and reproducibility where they affect understanding or trust.

Separate strengths, substantive weaknesses, clarifying questions, and minor presentation issues when the form benefits from that structure. A major concern should identify the claim affected, the evidence or missing evidence, and why that changes the conclusion. Do not elevate ordinary wording choices or already explained baseline differences into acceptance-critical concerns.

Request new experiments only when they address a concrete unresolved central claim, not as a generic wish list. If no blocking concern is found, do not manufacture one. Conversely, do not suppress a real correctness or validity issue to sound favorable.

When asked to score, provide a justified score on the actual scale, confidence, and the main uncertainty. Do not invent reviewer consensus, acceptance probability, or an official decision. If independent reviewers are requested, keep their initial assessments independent before synthesis.

## After a correction

Revisit the affected claim and remove stale conclusions from the updated report or comparison notes. A corrected intermediate rewrite is not an independent error in the author's original draft. Preserve a requested audit history separately, without presenting superseded diagnoses as current findings.
