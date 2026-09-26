# Method and appendix writing

Use this guide for method sections, implementation details, mathematical definitions, and text appendices in research papers.
The objective is a readable, reproducible account of the actual work, with the main idea visible before its details.
Apply the relevant checks to the requested scope; an ordinary wording edit does not require a full implementation audit.

## Establish the evidence and scope

- Identify the authoritative manuscript version, implementation revision, configuration, and reported experiment when available.
- Keep the manuscript's current claims and numbers unless the task authorizes changing them or a verified error requires correction.
- Separate an explanation of existing behavior from a proposed change to the method.
- When asked to verify implementation, inspect the code path and configuration that actually produce the reported behavior.
- A paper paragraph, translation, generated HTML page, or repeated formula is manuscript evidence, not independent code evidence.
- Record concrete locations supporting a finding: source file and function, configuration key, equation label, or PDF section.
- If implementation is unavailable, report the manuscript checks completed and the remaining implementation uncertainty directly.
- Resolve discrepancies before rewriting them into a confident technical claim; do not silently choose whichever source sounds plausible.

## Main-method structure

Begin with the task input, output, and design idea; explain why the major operations address the stated problem.
Then describe operations in their execution or dependency order, using the same names in the overview, equations, and figure.
Introduce training objectives after defining the representations or predictions they compare.
Place implementation settings in the appendix when they would interrupt the conceptual explanation.
Keep an essential assumption, information dependency, or comparison condition in the main text if omitting it changes the claim.

For an unfamiliar but technically capable reader, each module should answer:

1. What information enters it, and when is that information available?
2. What transformation or decision does it perform?
3. What quantity, representation, or action does it return?
4. Which later operation consumes that output?

Do not imply that an inference module uses a training-only target, privileged state, or future observation.
Describe how a method works before presenting every setting used to instantiate it.

## Symbols, dimensions, and values

Maintain a small working symbol ledger when revising a mathematically dense section.
For each introduced quantity, record its meaning, domain or dimension, indexing convention, definition location, and value source if applicable.
The ledger is a drafting aid; include it in the paper only when a notation table improves navigation.

| Information | What the reader needs |
|---|---|
| Meaning | What the quantity represents in this method |
| Dimension or domain | Whether it is a scalar, index, vector, matrix, set, probability, or discrete choice |
| Definition | The equation, construction, or reference that determines it |
| Instantiation | A numerical setting or model-dependent value used in the reported experiment |
| Provenance | Whether the setting comes from the implementation, a cited method, or an explicit design choice |

Do not substitute one category for another: saying a hidden width equals an output dimension defines a relationship, not its numerical value.
Such a relationship is sufficient if the output dimension is already explicit and unambiguous in the paper's model specification.
If reproduction requires a concrete value that cannot be recovered from the specified model, provide the verified value in the settings table.
Keep a shared notation such as `r_b = d_b` when it covers several branches clearly; do not invent branch-specific aliases solely to fill a table.
Define an index before, or immediately after, its first substantive use and state what it ranges over.
Distinguish a branch index from a batch index, a feature dimension from a token count, and a spatial coordinate from a flattened index.
Reuse a definition from the main text through a precise reference; do not redefine the same symbol with a different meaning in the appendix.

## Operators and their scope

For a nontrivial operator, explain its input, output, axis of operation, and boundary behavior.
“Normalization” alone may leave feature normalization, token-score normalization, and batch normalization indistinguishable.
Specify whether statistics are computed per sample, frame, token, channel, batch, or complete sequence.
For a score vector `x = (x_1, ..., x_N)`, distinguish output index `i` from the reduction index `j` used in its extrema.
For pooled representations, give the input grid, pooling rule, output shape, flattening order when relevant, and normalization order.
For a pairwise-relation matrix, state which entities form rows and columns and why the loss reduction has its stated denominator.

Explain a stabilizing threshold through the behavior it changes, such as mapping a nearly constant score vector to zero.
Distinguish an additive denominator stabilizer, a norm floor, a transition threshold, and a learned coefficient.
Do not describe every small constant as “epsilon” if the implementation gives it a different role.
Give the value and source of a fixed threshold when needed to reproduce a decision; do not invent a derivation for an empirical choice.
Specify rounding, clipping, tie-breaking, or ordering rules when they can change discrete outputs.
Avoid uncertain phrases such as “remove any prefix tokens” when the selected encoder's actual token structure is known.
For genuinely variable interfaces, state the condition under which an operation applies instead of implying uncertainty about the implementation.

## Sets, coordinates, and selection

Distinguish the candidate set, the scored set, a mandatory reserve, and the final retained set.
Give a cardinality for the set being discussed; a candidate count is not necessarily the retained count.
When sets are combined, check overlap before adding their sizes and check whether duplicates are removed.
State zero-based or one-based coordinates separately from the convention for mathematical token indices.
Provide the flattening map when both two-dimensional coordinates and linear indices appear.
Describe Cartesian-product intersections explicitly; “positions in these rows and columns” can instead suggest entire rows or columns.

For example, `A x A`, with `A = {0, 3, 7}`, has nine grid positions before additional distinct coordinates are included.
If a ranking keeps six candidates, the final set has six elements even though the candidate set has nine or more.
When a paper lists both coordinate rules and retained indices, recompute membership, uniqueness, bounds, and count from the rules.
Verify how a score, secondary criterion, or tie-breaking rule produces the listed retained set; membership alone does not prove the ranking.

## Training and inference

For each stage, identify trainable modules, frozen modules, supervision, and outputs carried to the next stage.
Differentiate a pretrained initialization from the dataset or objective used for the paper's own training.
Name the pretrained checkpoint precisely enough to recover the architecture and feature interface.
State which modules are removed, retained, or replaced at inference when this determines the claimed behavior or cost.
Explain memory initialization, updates, and resets if the method uses state across steps.
For variable-length batches, verify what is padded, the padding axis, and how masks prevent padded entries from affecting valid outputs or losses.
Do not infer a padding or caching implementation merely because it is conventional in the framework.
Separate within-sequence decoding from a new model invocation at a later environment step; their reuse and computation may differ.
Describe exceptional branches only when they are part of the actual algorithm or necessary to interpret a reported example.

## Equations and their surrounding prose

Order definitions so each equation's inputs are available when the reader reaches it.
A short inline helper definition can precede the main display; several independent objectives may deserve separate displays.
Split an aligned block when independent formulas need separate references or the layout is difficult to read.
Do not split every line mechanically, and honor a request to split only specified equations.
Preserve semantic labels and update cross-references rather than hardcoding the resulting equation numbers.
Explain a formula's role in nearby prose; do not repeat every symbol in a redundant verbal transcription.

Treat a displayed equation as part of its sentence:

- A following lowercase `where` generally continues the sentence, so a comma can follow the display.
- A following `Here, ...` begins a new sentence, so end the preceding mathematical statement with a period.
- Place sentence punctuation outside a cases or aligned structure when it belongs to the whole equation.
- Use either an integrated lead-in or a complete introductory clause; avoid a colon that fragments an otherwise continuous sentence.

Check shape compatibility, summation ranges, averaging factors, and notation consistency before polishing the prose.
Mathematical symbols may be italic while theorem or explanation text may use upright type; inspect unintended italics from environments or commands.

## Algorithms and theoretical analysis

For an algorithm, specify inputs, outputs, state, initialization, update order, and termination where they affect behavior.
Keep pseudocode and equations synchronized; an operation that uses an updated state is different from one that uses its previous value.
Distinguish a deterministic rule from a learned module and a heuristic threshold from a proven consequence.
Use complexity notation only after stating the quantities that grow, the computational regime, and the operations being counted.

For theory, state assumptions and domains before the result and identify exactly what it guarantees.
Separate a definition, an empirical observation, a heuristic argument, and a theorem rather than making the prose interchangeable.
Check quantifiers, norms, constants, dimensions, boundary cases, and dependencies between lemmas and claims.
A local stability result does not by itself establish global convergence, and an asymptotic bound does not establish wall-clock speed.
Keep assumptions necessary to interpret the main result visible in the main text even when the proof is deferred.
In an appendix proof, name the statement being proved, supply the essential intermediate steps, and trace cited results to their conditions.
If a proof step is missing or unsupported, flag that precise gap; do not write a plausible bridge as though it had been verified.
Include optional analysis only when it serves the paper's claims or the author requests it; formal-looking detail is not inherently useful.

## Appendix architecture and links

Group supporting material by reader purpose: full definitions, implementation settings, analysis, evaluation protocol, or additional results.
Choose subsection depth from content complexity, not a presumed universal conference appendix structure.
Keep the appendix readable with the main paper available, without copying the entire method into it.
Add the missing definition or local pointer that resolves a real ambiguity; avoid speculative objections or unrequested new analyses.
When removing a section, update main-text pointers, appendix references, numbering, and any promises of material that no longer exists.

Audit each main-text appendix call as a mapping from a promise to its destination:

| Main-text promise | Appropriate destination |
|---|---|
| Loss definitions and coefficients | The subsection(s) containing both definitions and the settings table |
| Implementation details | The stage, architecture, or training subsection that actually supplies them |
| Evaluation protocol | The subsection defining sampling, metrics, timing, and reporting |

Use a section reference for several related subsections and a subsection reference for one precise item.
If a promise spans two subsections, reference both or their shared parent; do not point only to the first item.
Prefer semantic LaTeX references so numbering remains correct after reordering or removal.
A reciprocal pointer to the main text is useful when it locates specific omitted settings; remove it if it merely sends the reader in a circle.
Preserve a necessary data or baseline source attribution somewhere unambiguous even when compressing appendix prose.

## Completion check

- Can a new reader identify every equation input, index range, operator scope, and output without guessing?
- Are values recoverable from the stated settings or models, and are claims of code verification supported by actual code inspection?
- Do candidate sets, retained sets, coordinates, dimensions, and table values agree across representations?
- Do training, inference, masking, and memory descriptions match the inspected implementation and reported experiment?
- Does every appendix pointer deliver the promised information after the latest edits?
- Do the rendered PDF, LaTeX, and requested bilingual comparison contain the same final technical content?
