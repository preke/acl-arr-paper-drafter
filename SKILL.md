---
name: acl-arr-paper-drafter
description: Draft an ACL ARR or EMNLP-submittable research paper in LaTeX from a user-provided topic plus supporting materials such as PDF, Word, Markdown, notes, local files, and links. Use when Codex needs to read mixed research materials, perform deep web research when needed, map evidence into the built-in paper template derived from the user's XMind outline, and produce a credible first draft that follows the official ACL style files and ARR submission requirements without inventing unsupported results or citations.
---

# ACL ARR Paper Drafter

Use this skill to generate a first-pass research paper in LaTeX for ACL ARR style workflows and conference commitments such as EMNLP. The draft must stay faithful to the available evidence, follow the user's XMind-derived paper outline, use the official ACL style files conventions, and honor ARR submission constraints described in [acl-arr-latex-guide.md](references/acl-arr-latex-guide.md).

## Workflow

1. Read the request and identify:
   - the topic, working title, or problem statement
   - whether the paper is a completed study, an in-progress project, a proposal-like draft, or a literature-grounded concept paper
   - which materials are available: PDFs, Word files, Markdown, notes, links, repos, datasets, benchmark pages, or prior drafts
   - whether the user explicitly wants deep web research
2. Build a source inventory before writing.
   - Record each source and what it can support: background, motivation, method, experiment design, results, case studies, or citations.
   - Separate direct evidence from assumptions.
3. Read [paper-template-outline.md](references/paper-template-outline.md) and map the evidence into each paper section.
4. Read [acl-arr-latex-guide.md](references/acl-arr-latex-guide.md) and prepare the LaTeX output shape accordingly.
5. If the topic needs recent related work, benchmark information, or factual background, perform deep research:
   - plan focused search queries around task, method family, datasets, benchmarks, and strongest baselines
   - gather primary sources first
   - extract only claims that can be traced back to sources
   - keep a compact citation ledger for the draft
6. Draft the paper in LaTeX section order:
   - preamble and metadata
   - abstract
   - introduction
   - related work
   - method
   - experiment settings
   - result analysis
   - conclusion
   - limitations
7. End with a short gap block in LaTeX comments if evidence is missing.
   - Example: `% TODO: add numeric comparison table once experiment logs are available`

## Input Handling

Accept mixed source packages:

- local files such as `.pdf`, `.docx`, `.md`, `.txt`, images, and extracted notes
- links to papers, datasets, repos, benchmarks, docs, and project pages
- raw bullet points or partially formed outlines
- user instructions for additional deep research

Inspect local files before drafting. For long materials, extract structured notes first instead of copying raw passages into the paper.

## Deep Research Mode

Use deep research whenever the user asks for web research, when the area is fast-moving, or when the materials do not sufficiently support related work and benchmark claims.

Deep research should produce:

- a short search plan
- a source inventory with venue, year, and relevance
- a distilled related-work taxonomy
- citations or citation placeholders attached to concrete claims

Prefer this order of evidence:

1. Official papers or publisher pages
2. Official project, benchmark, or dataset pages
3. Official repositories
4. Other credible secondary summaries

Do not let deep research turn into an ungrounded literature dump. Keep only the sources that materially strengthen the draft.

## Drafting Rules

- Follow the section logic in [paper-template-outline.md](references/paper-template-outline.md) unless the user explicitly requests a different venue structure.
- Emit LaTeX, not Markdown, as the primary output.
- Use ACL-style sectioning and preamble conventions from [acl-arr-latex-guide.md](references/acl-arr-latex-guide.md).
- Follow the official `acl-org/acl-style-files` template conventions rather than an improvised ACL-like preamble.
- Default to anonymous review format with `\\usepackage[review]{acl}` unless the user explicitly asks for a camera-ready or non-anonymous draft.
- Respect ARR length expectations:
  - long paper: up to 8 pages of main content
  - short paper: up to 4 pages of main content
  - unlimited references
  - limitations section required after the conclusion material
- Preserve the user's terminology for task setting, method name, and key concepts unless it is clearly inconsistent.
- Distinguish completed findings from planned evaluation.
- If results exist, phrase claims conservatively and ground them in the provided evidence.
- If results do not exist, write experiment sections as evaluation design or intended analysis, not as completed achievements.
- Do not fabricate citations, numbers, baselines, datasets, ablations, or case-study outcomes.
- If specific citations are unavailable, insert explicit placeholders such as `\\cite{TODO}` or LaTeX comments only when the user prefers placeholders over prose notes.
- Preserve two-way anonymization:
  - omit author names and affiliations by default
  - avoid self-references that reveal identity
  - avoid deanonymizing repository links or supplemental references
- Include a `Limitations` section by default because ARR submission requirements make it mandatory.

## Web Research Rules

Browse when:

- the user asks for deep research or web search
- the topic depends on recent literature or rapidly changing baselines
- a related-work claim needs source attribution
- a provided link, benchmark, dataset, or model must be verified

When browsing:

- prefer primary sources such as official project pages, arXiv pages, publisher pages, benchmark pages, and official repositories
- compare multiple recent sources before making SOTA-style claims
- mark inferences that are not directly stated by a source
- keep claim strength proportional to source quality
- prefer refereed versions over preprints when a preprint has been superseded

## Output Format

Return a compilable LaTeX draft skeleton with:

1. `\\documentclass[11pt]{article}`
2. `\\usepackage[review]{acl}` unless the user requests a different submission mode
3. ACL-style package usage and basic preamble aligned with the official style files
4. anonymous title and author block placeholders when author data is missing
5. `abstract` environment
5. `\\section{Introduction}`
6. `\\section{Related Work}`
7. `\\section{Method}`
8. `\\section{Experimental Setup}`
9. `\\section{Results and Analysis}`
10. `\\section{Conclusion}`
11. `\\section{Limitations}`
12. bibliography placeholders or comments when references are incomplete

If the user wants only paper body text, still organize the content so it can be pasted directly into the ACL template.

## Evidence Discipline

Before finalizing, verify:

- every major section is drafted or explicitly marked pending
- no factual claim exceeds the evidence
- no numerical result appears without support
- the introduction covers problem, importance, limitations of prior work, intuition, and contributions
- the result-analysis section clearly distinguishes real results from planned analyses
- the LaTeX structure matches the official ACL style files closely enough to drop into an ARR workflow
- the draft is anonymized unless the user asked otherwise
- a limitations section is present
- the paper length target is consistent with long or short submission mode

## References

Always consult:

- [paper-template-outline.md](references/paper-template-outline.md) for the XMind-derived paper logic
- [acl-arr-latex-guide.md](references/acl-arr-latex-guide.md) for ACL-style LaTeX conventions
