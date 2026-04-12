---
name: acl-arr-paper-drafter
description: Draft an ACL ARR or EMNLP-submittable research paper in LaTeX from a user-provided topic plus supporting materials such as PDF, Word, Markdown, notes, local files, and links. Use when Codex needs to read mixed research materials, perform deep web research when needed, map evidence into the built-in paper template derived from the user's XMind outline, and produce a credible first draft that follows the official ACL style files and ARR submission requirements without inventing unsupported results or citations.
---

# ACL ARR Paper Drafter

Use this skill to turn a research topic and a bundle of evidence into an anonymized ACL ARR style LaTeX first draft. Keep the user's original paper template, but upgrade the workflow with claim-driven planning, citation discipline, submission-aware drafting, and a clear paper narrative.

Always consult:

- [paper-template-outline.md](references/paper-template-outline.md)
- [acl-arr-latex-guide.md](references/acl-arr-latex-guide.md)
- [research-writing-patterns.md](references/research-writing-patterns.md)

## Inputs

Accept any mix of:

- topic, tentative title, or problem statement
- local `.pdf`, `.docx`, `.md`, `.txt`, images, notes, or existing drafts
- links to papers, benchmarks, datasets, code, docs, or project pages
- partial experiment tables, ablation notes, or bullet-point findings
- explicit requests for deep web research

Before drafting, classify the paper as one of:

- result-backed paper
- in-progress paper with incomplete experiments
- proposal-style paper
- literature-grounded concept paper

This choice controls how strongly the draft can state claims.

## Workflow

### Phase 1: Build the Evidence Package

1. Read the request and all supplied materials.
2. Build a compact source inventory:
   - source
   - what it supports
   - confidence level
   - whether it is direct evidence or inference
3. If local files are large, extract structured notes first rather than drafting from raw text.

Default support buckets:

- problem motivation
- method details
- datasets and benchmarks
- baselines
- results
- ablations
- case studies
- citations

### Phase 2: Freeze the Paper Story

Before writing any prose, derive:

- one-sentence paper thesis
- one dominant contribution
- optional supporting contribution
- anti-claim to rule out
- evidence status for each claim
- paper narrative in one line: problem -> solution -> evidence

Then write a compact claim-evidence matrix. Use the format from [research-writing-patterns.md](references/research-writing-patterns.md).

Do not skip this step. It prevents narrative drift and overclaiming.

For ACL ARR / EMNLP style empirical papers, prefer a paper story with this shape:

- identify an important but under-evaluated blind spot, failure mode, or capability gap
- operationalize it with a benchmark, task protocol, taxonomy, or analysis framework
- run systematic evaluation before claiming a fix
- if a mitigation exists, present it as a simple, proportional extension rather than the entire paper identity

Avoid paper stories that are only "we built a framework" or only "we improved a metric" without a sharply defined gap.

### Phase 3: Map the XMind Template to the Current Paper

Follow the paper logic in [paper-template-outline.md](references/paper-template-outline.md), but adapt each section to the actual evidence.

Mandatory section flow:

1. abstract
2. introduction
3. related work
4. method
5. experimental setup
6. results and analysis
7. conclusion
8. limitations

If the paper does not yet have completed results:

- keep `Experimental Setup` concrete
- write `Results and Analysis` as an evaluation plan plus expected analysis structure
- never present planned experiments as finished evidence

### Phase 4: Deep Research When Needed

Use deep research whenever:

- the user explicitly asks for it
- related work is thin or outdated
- benchmark or SOTA claims need grounding
- a provided link or named paper needs verification

Deep research should produce:

- a short search plan
- a source inventory with year, venue, and relevance
- a related-work taxonomy
- concrete citation candidates attached to claims

Evidence priority:

1. official papers and publisher pages
2. official benchmark, dataset, or project pages
3. official repositories
4. credible secondary summaries

Do not let research sprawl. Keep only sources that materially improve the paper.

### Phase 5: Draft in ACL ARR Style

Use the official ACL style conventions from [acl-arr-latex-guide.md](references/acl-arr-latex-guide.md).

Default drafting rules:

- emit LaTeX, not Markdown
- use `\documentclass[11pt]{article}`
- default to `\usepackage[review]{acl}`
- keep the draft anonymous unless the user asks otherwise
- include `\section{Limitations}` by default
- target ARR-style review drafts before camera-ready formatting

For the content itself:

- introduction must cover problem, importance, gap, method intuition, and contributions
- related work must synthesize categories, not just list papers
- method must define inputs, outputs, assumptions, and core modules clearly
- experiment sections must distinguish completed evidence from planned evaluation
- results must stay proportional to the evidence
- every major section should advance the same narrative arc rather than introducing a new story
- for empirical NLP papers, title, abstract, introduction, and experiment order should follow the reusable templates in [research-writing-patterns.md](references/research-writing-patterns.md)

### Phase 6: Produce the Drafting Package

Unless the user asks for only raw body text, produce:

1. a source inventory
2. a claim-evidence matrix
3. a citation plan
4. a compilable LaTeX draft
5. an `Open Gaps` list or LaTeX TODO comments

If the user asks for files, prefer this structure:

```text
paper/
  main.tex
  references.bib
  sections/
```

If the user asks for chat-only output, keep the same logical package in the response.

## Citation Discipline

Never fabricate citations.

When adding references:

- prefer DBLP, Crossref, ACL Anthology, publisher pages, or arXiv pages
- prefer published venue versions over older preprints when appropriate
- attach citations only to claims actually supported by the cited source
- if a citation is still uncertain, use a visible placeholder rather than inventing metadata

## ARR Constraints

Respect these defaults unless the user explicitly requests another mode:

- long paper: up to 8 pages of main content
- short paper: up to 4 pages of main content
- unlimited references
- two-way anonymized review
- limitations section required

## Quality Bar

Before finalizing, verify:

- every major section is drafted or intentionally marked pending
- every core claim maps to evidence
- no numerical result appears without support
- no related-work statement overclaims the literature
- the introduction and conclusion tell the same central story
- the abstract, introduction, method, and conclusion all agree on the same problem -> solution -> evidence arc
- each major section passes the section-level checks in [research-writing-patterns.md](references/research-writing-patterns.md)
- the draft could be pasted into an ACL ARR workflow without major structural fixes

## Failure Modes To Avoid

- generic abstract with no concrete problem or evidence
- related work as a paper list instead of a synthesis
- method section that only renames a module
- results phrased as completed achievements when only plans exist
- deanonymizing self-citations or links
- fake baselines, fake citations, fake numbers, fake ablations

## Output Modes

Pick the smallest mode that satisfies the user:

- `chat-only draft`: return LaTeX in the response
- `single-file draft`: write one `.tex` file
- `paper folder`: write `main.tex`, `references.bib`, and section files

If the user does not specify, default to a single compilable LaTeX draft plus a compact claim-evidence matrix.
