# ACL ARR LaTeX Guide

Use this reference when formatting the draft in ACL-style LaTeX for ARR submission and EMNLP commitment.

## Baseline Template

The official ACL style files repository is:

- https://github.com/acl-org/acl-style-files

The EMNLP 2026 main-conference CFP paper-submission details page points authors to ARR requirements and ACL templates:

- https://2026.emnlp.org/calls/main_conference_papers/#paper-submission-details

The ACL style template commonly starts with:

```tex
\documentclass[11pt]{article}
\usepackage[review]{acl}
\usepackage{times}
\usepackage{latexsym}
\usepackage[T1]{fontenc}
\usepackage[utf8]{inputenc}
\usepackage{microtype}
\usepackage{inconsolata}
\usepackage{graphicx}
```

This is based on the official ACL style files repository and the Overleaf ACL template.

## ARR Submission Constraints To Honor

From the official EMNLP 2026 CFP and ARR CFP:

- long papers: up to 8 pages of main content
- short papers: up to 4 pages of main content
- unlimited references
- a limitations section is required
- submissions must follow two-way anonymized review rules

Treat these as default drafting constraints unless the user explicitly asks for a camera-ready revision rather than a submission draft.

## What To Emit

Default to a draft that includes:

- `\documentclass[11pt]{article}`
- `\usepackage[review]{acl}` for review-style drafts unless the user explicitly wants a non-anonymous or camera-ready variant
- title placeholder
- anonymous author placeholder block
- abstract environment
- major sections for introduction, related work, method, experimental setup, results and analysis, and conclusion
- a `\section{Limitations}`
- bibliography commands or placeholder comments

## Style Constraints

- Keep the output close to ACL style conventions rather than inventing a custom preamble.
- Use standard `\section{}` and `\subsection{}` commands.
- Keep figures and tables as placeholders or commented stubs if the user has not provided them.
- Prefer comments for missing resources over fake figures, fake tables, or fake citations.
- Do not put real author names, affiliations, or deanonymizing acknowledgements in a review draft unless the user explicitly asks for that mode.
- Avoid self-referential wording that reveals identity.

## Missing Information Policy

If author, affiliation, bibliography, or experiment details are missing:

- emit placeholder values that are easy to replace
- or emit LaTeX comments marking the missing fields
- do not invent institution names, email addresses, or results
- do not invent anonymous supplementary links that point to real identity-bearing resources

## Useful Pattern

When evidence is incomplete, a safe structure is:

```tex
% TODO: replace title once finalized
\title{Working Title Placeholder}

\author{Anonymous Author(s)}

\begin{document}
\maketitle

\begin{abstract}
TODO: Write abstract after finalizing introduction and results.
\end{abstract}
```

## Source Notes

Official ACL style references used for this guide:

- Overleaf ACL template page
- ACL style files repository referenced by that template
- EMNLP 2026 CFP paper-submission details page
- ARR CFP and submission requirements page
