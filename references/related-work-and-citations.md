# Related work and citation editing

## Organize by research questions

Group prior work around the problem, design alternatives, or comparison axes needed to understand the contribution. Explain how each group relates to this work. Avoid a chronological list of titles, a catalogue of unrelated applications, or a forced criticism at the end of every paragraph.

Credit the nearest alternatives, foundational concepts that are actually used, and the origin of reused methods, data, and protocols. A newer application paper is not automatically a better citation for an established operator. An old source is not dispensable merely because of its date.

Distinguish the original method, its later adaptation, and the source of a reused result. These can require different citations. A comparison paper's bibliography does not establish the correct origin of one of its baselines: inspect the original source and the relevant implementation when attribution is disputed.

## Verify sources before editing

For a proposed citation, record the exact manuscript claim, source passage or location, type of support, and bibliographic identity. Use primary papers, official datasets, or official documentation as appropriate. Search snippets, another paper's citation, and an old generated audit are leads rather than final evidence.

Check that a source supports the actual level of claim. A distillation reference may support knowledge transfer generally without supporting the paper's particular multi-teacher design. A token-pruning paper may support computational motivation without demonstrating closed-loop behavior.

Do not fabricate citation keys, venues, authors, publication years, or quoted passages. Verify whether a preprint and its conference version are the same work before adding another entry. Cite a document's actual version rather than guessing from the year in a filename.

For each addition, an author-facing justification can be short:

| Location | Claim being supported | Source and evidence | Reason to add |
|---|---|---|---|
| Existing background sentence | A specific known mechanism | Verified original passage | Supplies missing conceptual or empirical attribution |
| Borrowed component name | A named algorithm | Its original paper | Identifies a concrete dependency |
| Existing result provenance sentence | Published baseline numbers | Relevant table and protocol | Establishes where the reported results came from |

Do not put this audit table into the manuscript unless requested.

## Preserve contribution ownership

Attach a citation as closely as possible to the borrowed idea it supports. Avoid placing a broad foundational citation after a sentence that introduces the authors' entire novel contribution.

Example: a sentence announcing “Stage I transfers complementary representations into our student” describes this paper's design. A citation to general knowledge distillation does not establish that design. Better locations include an existing related-work sentence on distillation or an explicit borrowed operation. If no suitable location exists under a citation-only constraint, omit that proposed addition and explain the conflict outside the manuscript.

Do not remove credit for a genuinely reused method to make the work look more novel. Clear attribution and a clear description of the new contribution are compatible.

## Citation-only workflow

1. Identify the active full source and bibliography; separate previously cited keys from bibliography entries that are present but unused.
2. Find unsupported existing statements that can receive meaningful references without adding prose.
3. Verify the proposed sources and choose precise insertion points.
4. Add only citation commands and necessary bibliography records. Preserve the original prose, math, numbers, and table data.
5. Check a diff or equivalent text comparison showing that no prose was rewritten. Compile when the available project supports it.

Report counts by category rather than treating them as interchangeable:

- citation locations or commands added;
- previously unused existing bibliography entries now cited;
- genuinely new bibliography entries added;
- unique works cited before and after.

For instance, four existing uncited entries plus six new entries can raise a 30-work bibliography to 40 cited works while requiring only six new BibTeX records. Verify the actual counts; do not use this example as a target.

If the user asks for “only the new BibTeX,” deliver only genuinely new, deduplicated entries. Do not include the entire bibliography or an already existing key under a second name.

## Count and remove citations carefully

Count key occurrences inside actual citation commands after handling comments and included source files. Support grouped keys and relevant citation variants; do not count a substring in a bibliography record, a commented sentence, or a label as a citation. Explain whether the count is occurrences, locations, or unique works. Disclose parser limits for custom citation macros.

A work cited once is not necessarily expendable. Before removing a reference to improve pagination, inspect its sole context: it may be the only source for a dataset, baseline, theorem, or borrowed algorithm. Prefer redundant background support when removal is justified, and recompile to check the real page effect. Do not promise that removing one bibliography entry removes exactly one line or page.

Do not add references merely to reach a typical count. When comparing citation volume with published papers, use comparable topics, paper types, venues, and years; report the small sample and counting method. Quantity alone is not a quality target.

## Main text and appendix

Use the active bibliography mechanism to verify whether appendix citations feed the same bibliography. In a single LaTeX document they can ordinarily share it, even when the bibliography appears before the appendix; a separate supplement or bibliography package can change that behavior. Check compiled output and venue instructions before asserting what this project does.

Do not delete baseline-result provenance simply because a method is already cited elsewhere. A method's origin and the source of its tabulated measurements are different facts. Compress or relocate a source statement if useful, while preserving traceability somewhere readers can find it.
