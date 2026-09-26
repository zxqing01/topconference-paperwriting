# Top Conference Paper Writing

[English](README.md) · [简体中文](README.zh-CN.md)

A Codex skill for drafting, revising, and checking research papers in machine learning, computer vision, NLP, robotics, and related fields. It connects the research question, contribution, method, and evidence while respecting the scope of each request—from a full manuscript to one citation or one sentence.

**Skill name:** `topconference-paperwriting`

**Invoke in Codex:** `$topconference-paperwriting`

## What it covers

[SKILL.md](SKILL.md) is the entry point. It establishes scope, evidence handling, writing principles, and delivery checks, then routes the agent to the chapters needed for the task. The guides cover empirical, theoretical, systems, and benchmark papers without imposing one paper structure or one conference's prose style.

| Task | Support |
|---|---|
| Draft a paper or section | Organize supplied notes and results into a problem, gap, contribution, and supporting argument. |
| Revise opening and closing sections | Align the title, abstract, introduction, contributions, and conclusion with the demonstrated findings. |
| Improve methods and appendices | Clarify symbols, operator scope, training versus inference, assumptions, algorithms, and appendix references. |
| Explain experiments | Distinguish baselines, interpret main results and ablations, check units and percentage changes, and define efficiency measurements. |
| Add or verify citations | Match sources to specific claims, preserve attribution, deduplicate bibliography entries, and support citation-only edits. |
| Refine LaTeX and delivery | Work on tables, captions, equations, layout, and requested bilingual comparison HTML or PDF updates. |
| Audit or review a manuscript | Check cross-section consistency, consult current venue instructions, and prepare evidence-grounded reviewer-style assessments. |

An optional specialization addresses embodied AI, visual decision making, and adaptive computation. It is used only when relevant to the paper.

## Install

Install Git and use a Codex environment that supports local skills. Clone this repository into your user skills directory. These commands use `CODEX_HOME` when it is set; otherwise they use `~/.codex` on macOS/Linux or `%USERPROFILE%\.codex` on Windows.

**macOS / Linux — Bash**

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
git clone https://github.com/zxqing01/topconference-paperwriting.git \
  "${CODEX_HOME:-$HOME/.codex}/skills/topconference-paperwriting"
```

**Windows — PowerShell**

```powershell
$skillRoot = if ($env:CODEX_HOME) {
    Join-Path $env:CODEX_HOME 'skills'
} else {
    Join-Path $env:USERPROFILE '.codex\skills'
}
New-Item -ItemType Directory -Force -Path $skillRoot | Out-Null
git clone https://github.com/zxqing01/topconference-paperwriting.git `
    (Join-Path $skillRoot 'topconference-paperwriting')
```

Use the `CODEX_HOME` configured for the Codex instance that will run the skill. If the destination already exists, keep your local changes and update that checkout instead of cloning over it. After installation, invoke the skill by name on your next turn or in a new Codex task.

## Quick start

Provide the active manuscript or passage, relevant evidence, and the requested operation. For venue-specific work, include the conference, year, and submission stage. Specify the desired output, such as revised prose, an edited LaTeX file, a bilingual comparison, or a review report.

```text
$topconference-paperwriting
Revise the abstract in the attached manuscript for clarity and concision.
Use the result tables as the evidence source. Preserve the numbers and
claim scope. Return the revised English abstract and a Chinese translation.
```

A typical workflow is:

1. **Identify the active source and scope.** Name the version to edit and any local restrictions. Supply code or configurations when implementation verification is part of the task.
2. **Use the relevant chapters.** A local edit loads its matching guidance; a full-paper task follows the applicable chapters through the manuscript.
3. **Revise from evidence.** Claims, terminology, quantities, notation, and cross-references stay consistent. Missing facts are raised in author notes rather than filled with invented results.
4. **Check and deliver the requested artifacts.** The agent reports which files changed and which checks actually ran. Required checks depend on the change and the available tools.

You can start with incomplete notes. The skill supports drafting the portions established by the available material and identifying the precise inputs still needed.

## Example requests

**Build a manuscript argument from research notes**

```text
$topconference-paperwriting
Use these research notes, theorem statements, and experiment tables to
propose a paper outline and draft the introduction. Separate established
findings from planned experiments, and identify any missing evidence.
```

**Add citations without rewriting**

```text
$topconference-paperwriting
Only add citations to the related-work section and the necessary BibTeX
entries. Verify each source against the exact claim. Preserve all prose,
numbers, and equations, and return only the newly added bibliography entries
alongside the edited source.
```

**Make a minimal local edit**

```text
$topconference-paperwriting
Shorten this sentence by one or two words to help it fit the line.
Preserve the technical condition and comparison baseline. Give one candidate.
```

**Check the method against implementation**

```text
$topconference-paperwriting
Check the appendix's token-selection description against the supplied code
and configuration. Verify indexing, candidate counts, and retained counts.
Edit only the appendix and any main-text references that depend on it.
```

**Revise experimental narration**

```text
$topconference-paperwriting
Rewrite the ablation discussion using the supplied table. Explain the
question each comparison answers and check absolute versus relative gains.
Keep the measured results and avoid adding unsupported mechanism claims.
```

**Check a submission or prepare a review**

```text
$topconference-paperwriting
Audit this manuscript for [conference] [year] [submission stage]. Consult
the current official instructions. Separate confirmed problems, unresolved
questions, and optional improvements. Do not edit the manuscript yet.
```

## Scope and preferences

Explicit task instructions govern the work. “Only add citations” permits citation commands and necessary bibliography entries while preserving the existing text and mathematics. “Only necessary changes” keeps optional polish separate. A request to explain or assess does not authorize file edits. A sentence-level task should remain a sentence-level task, with only necessary dependent repairs.

[Author preferences](references/author-defaults.md) describes optional configuration for discussion language, manuscript language, revision scope, tense and voice, comparison layout, and deliverables. These are choices for each author or project, not preferences bound to a particular person. Keep recurring choices in a short project note; keep private manuscript details out of the shared skill. Current task instructions override earlier defaults.

For requested English/Chinese revision HTML, the default layout places the original on the left and the revision on the right, with English above the corresponding Chinese. You can request a different layout or English-only output.

## Tools and verification

This repository supplies Markdown instructions. It does not bundle an automatic compiler, a manuscript checker, or a reference database. The running environment must provide the capabilities needed for the requested task:

| Requested work | Needed resources |
|---|---|
| Prose revision | The relevant passage and enough surrounding evidence to preserve its meaning. |
| Citation or venue-rule verification | Network access to primary sources and current official instructions, or supplied authoritative source documents. |
| Implementation verification | The relevant source code, active configuration, and any necessary records of the reported run. |
| LaTeX compilation | Complete project files, the required LaTeX/bibliography tools, and the project's build procedure. |
| PDF layout verification | A compiled PDF and tools for rendering and inspecting its pages. |

**Source inspection, compilation, and visual inspection establish different things.** Editing LaTeX does not establish the resulting line breaks. A successful build does not establish mathematical correctness or venue compliance. The skill instructs the agent to distinguish these checks and report any check that remains unavailable.

Conference requirements must be checked for the named **venue, year, and stage**. Page limits, anonymity rules, appendix placement, and required statements are not permanent defaults in this skill.

## Repository guide

| File | Purpose |
|---|---|
| [SKILL.md](SKILL.md) | Entry point, task boundaries, evidence principles, and chapter routing. |
| [opening-sections.md](references/opening-sections.md) | Title, abstract, introduction, and contributions. |
| [related-work-and-citations.md](references/related-work-and-citations.md) | Related work, source verification, citation-only edits, and BibTeX. |
| [method-and-appendix.md](references/method-and-appendix.md) | Methods, notation, algorithms, theory, and appendix structure. |
| [ablation_and_terminology.md](references/ablation_and_terminology.md) | Setup, results, ablations, qualitative evidence, efficiency, and terminology. |
| [closing-sections.md](references/closing-sections.md) | Conclusion, limitations, reproducibility, and factual declarations. |
| [latex-and-delivery.md](references/latex-and-delivery.md) | Tables, equations, layout, bilingual HTML, and artifact checks. |
| [verification-and-review.md](references/verification-and-review.md) | Current venue rules, manuscript/code consistency, and reviewer-style assessment. |
| [embodied_ai_writing_patterns.md](references/embodied_ai_writing_patterns.md) | Optional embodied-AI and adaptive-computation guidance. |
| [author-defaults.md](references/author-defaults.md) | Optional author and project preferences. |

This is an independent writing skill, not an official product or policy of any conference. It does not guarantee acceptance; research validity, source accuracy, and the final submission remain the authors' responsibility.
