# LaTeX, tables, layout, and artifact delivery

## Work from the active source

Identify the file the author actually uses. Generated HTML, an old PDF, and a suggested revision may differ from it. Record accepted edits before rebuilding. Preserve original panels in a comparison document: an updated final version must not rewrite the historical original.

For an explicit file update, edit the authoritative source or its generating data, not only rendered browser text. Synchronize the requested LaTeX, comparison page, clean reading page, and compiled PDF through the existing workflow where applicable. Do not promise that a screenshot or preview changed when only a file was saved.

Make narrowly scoped backups or use version control for substantial multi-artifact changes. Keep historical copies outside active deliverables to avoid reopening the wrong version.

## Tables and captions

A caption should identify the experiment, explain otherwise ambiguous conditions, and define units or formatting not clear from the table. It need not repeat a complete methods section. Keep the source of published comparison values accessible in the caption or surrounding text.

Define highlighting consistently:
- If bold means best in a column, mark all tied best values consistently.
- If underlining means second best, define and apply a consistent ranking policy, including ties.
- If bold identifies the authors' method, make that purpose distinct from a best-result convention.
- If rounded values tie but higher precision differs, avoid an unexplained visually inconsistent ranking; use an explicit precision or reporting policy.

Do not selectively bold an author's tied number under a “best in each column” caption. Published examples of inconsistent styling do not justify a misleading table.

Use metric directions and units appropriate to the actual evaluation. Human references or oracle rows may belong to a separate comparison group; describe which rows participate in the best/second-best convention.

Keep row names concise but identifiable. If a table changes “Visual distillation only” to “Distillation only,” synchronize body terminology only if the shortening is adopted. A shorter label is generally an optional readability edit, not a data correction.

## Equation typography and syntax

Treat a display as part of its surrounding sentence. Two consistent patterns are:

~~~latex
The translator is defined as
\begin{equation}
G_b(z)=W_{b,2}\,\sigma(W_{b,1}z+b_{b,1})+b_{b,2},
\end{equation}
where the weights and biases ...
~~~

~~~latex
The translator is defined as
\begin{equation}
G_b(z)=W_{b,2}\,\sigma(W_{b,1}z+b_{b,1})+b_{b,2}.
\end{equation}
Here, the weights and biases ...
~~~

Do not leave a full stop before a lowercase continuing “where,” or a comma before an independent “Here” sentence. A colon before a display is a stylistic choice when the lead-in is complete; do not label every colon an error.

For piecewise formulas, put sentence punctuation after the complete expression when that makes the construction clearer; keep condition punctuation distinct from equation punctuation. Check copied text for damaged backslashes, asterisks, underscores, and escaped percent signs.

Use symbolic labels and reference commands instead of hard-coded display numbers. Split independently referable definitions when useful or requested; keep a derivation aligned under one number when it is one mathematical statement. If the author names specific old equation numbers to split, map those to labels first and split only those equations.

A theorem environment may intentionally italicize a statement; explanatory prose need not inherit that style. For unintended appendix italics, inspect environment boundaries, theorem style, and font commands. Fix the cause locally without flattening mathematical italics throughout the paper.

## Small wording edits for a stranded word

If the user requests deleting one or two words, provide one minimal candidate that preserves meaning. Remove dispensable framing or redundancy before technical content. Do not add filler merely to push a word onto another line.

For example, removing “Here,” is usually less risky than deleting an article that changes the construction. Avoid awkward suspended compounds when a concise ordinary phrase conveys the same meaning; optimizer betas can be described as “moment decay rates” if that is unambiguous in context.

When a list is too dense, organize it by process boundaries or purpose rather than disguising the same list with semicolons. Keep inclusions, exclusions, and technical distinctions intact.

A text edit is only a proposed layout fix until the actual font, column width, and template are rendered. If compilation is unavailable, state that line wrapping remains unverified.

## Compress layout in a controlled order

Inspect the affected page first. Determine whether the problem is a long phrase, caption, oversized float, whitespace, float queue, page break, or unnecessary paragraph.

Prefer:
1. Removing low-information words and repeated prose.
2. Improving local sentence or caption structure without dropping conditions.
3. Adjusting figure/table dimensions, column definitions, or float placement within the official style.
4. Modest local spacing changes only when permitted and verified visually.

Keep readability and template constraints intact. Never shrink global fonts or margins to conceal a page-limit violation. Do not delete methodological explanations merely to fit a table.

A request to put three tables on one page requires measuring their combined height, captions, headings, and allowable spacing. It may be impossible without a larger layout change; report that honestly rather than claiming success from a source edit.

### Spacing

LaTeX uses typesetting lengths such as pt and em; displayed screen pixels depend on zoom and resolution. A text line is related to the active \baselineskip, not a universal pixel count. A length such as -\baselineskip can remove roughly one current baseline interval, but may be too aggressive around floats and may be disallowed by the venue. Check the actual template and rendered page.

Negative \vspace is neither automatically compliant nor automatically a violation. Its magnitude, placement, resulting layout, and current venue instructions determine whether it is appropriate. Do not present it as a reliable universal solution.

### Floats and page breaks

In a two-column document, figure* and table* typically span columns and have different placement constraints. Ordinary figure/table normally occupy one column. In a one-column document, width differences may be absent, but placement behavior remains class/package-dependent. Inspect the actual class and output before proposing a global star removal.

“After the references” describes document order; it does not by itself specify a new page. Check the current venue instructions and template for appendix placement. Do not infer a mandatory \clearpage from a small sample of published PDFs, nor remove an existing page break without checking the float queue.

### Comments and bibliography

Remove obsolete commented-out drafts only when requested or included in the agreed cleanup. Preserve escaped percentages and syntactic line-continuation percent signs. Do not run a blind “delete everything after %” transformation.

Use the project's bibliography engine and required compilation sequence. Fix unresolved citations and references; bibliography shortening by deleting a source requires an intellectual justification as well as a layout check.

## Bilingual comparison HTML

For requested revision comparison, use this layout unless the author specifies another:

| Upper row | |
|---|---|
| Original English, left | Revised English, right |
| Original Chinese, left | Revised Chinese, right |

Align corresponding sections or paragraphs. Preserve equations, numbered references, citations, and table content. Render formulas with the page's established math engine, and retain copyable source where needed. Long equations or tables may scroll within their panel rather than overflow the whole page.

Give a clean reading view when requested. Keep explanations for edits separate from publishable text. Label necessary corrections versus optional improvements accurately; a later correction must not leave a stale note claiming the old rationale is still valid.

## Proportionate delivery checks

For a source edit, check the local diff and dependent references. For generated artifacts, verify that the requested text appears in the correct revised panel, the original remains intact, and the linked final version agrees.

When complete source and tools are available, compile after structural or layout edits. Inspect affected pages and any later pages shifted by floats or numbering. Check for missing equations, unresolved references, clipped tables, unreadable spacing, unexpected italics, and stray headings. Expand verification only when the change can affect more of the document.

Deliver the files actually updated, and distinguish “source checked,” “compiled,” and “visually inspected.” Do not state universal compliance or publication readiness from a successful compilation alone.
