# ACL ARR Paper Drafter

[![Skill](https://img.shields.io/badge/Codex-Skill-blue)](./SKILL.md)
[![LaTeX](https://img.shields.io/badge/output-LaTeX-green)](./examples/personality-in-llm-agents-minimal.tex)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)

`acl-arr-paper-drafter` is a Codex skill for drafting anonymized ACL ARR style LaTeX papers from a topic plus mixed supporting materials.

It is built for research workflows where the input may be messy and heterogeneous: PDFs, Word files, Markdown notes, benchmark pages, code repositories, project links, and partial experimental evidence. The skill preserves a paper structure derived from an XMind outline, aligns the output with official ACL style files, and adds the research-writing discipline needed to produce a credible first draft rather than a generic template fill.

## Why This Skill Exists

Many paper-writing prompts are good at producing prose but weak at controlling claims. This skill is designed to be stricter:

- it freezes the paper story before drafting
- it maps every major claim to evidence
- it performs deep research when related work or benchmark grounding is missing
- it keeps unsupported content as TODOs or scoped placeholders instead of fabricating results

In short, it tries to produce a draft you can actually continue writing from.

## What It Does

- Drafts ACL ARR or EMNLP-submittable LaTeX paper skeletons
- Uses the official `acl-org/acl-style-files` conventions
- Defaults to anonymized review format
- Includes a required `Limitations` section
- Supports deep research for related work and factual grounding
- Builds a claim-evidence matrix before drafting
- Freezes a paper narrative before prose drafting
- Produces a compact citation plan and source inventory
- Keeps unsupported claims as placeholders or TODO comments instead of inventing content

## Core Workflow

The drafting flow is intentionally structured:

1. Build the evidence package from local files, links, and notes.
2. Freeze the paper story:
   - thesis
   - dominant contribution
   - anti-claim
   - problem -> solution -> evidence narrative
3. Map the evidence onto the XMind-derived paper template.
4. Run deep research when the topic needs fresher related work or verified benchmark context.
5. Draft a compilable ACL ARR style LaTeX paper.
6. Return a small drafting package:
   - source inventory
   - claim-evidence matrix
   - citation plan
   - LaTeX draft
   - open gaps

## Repository Structure

- `SKILL.md`: core skill instructions and triggering metadata
- `agents/openai.yaml`: UI-facing metadata
- `references/paper-template-outline.md`: XMind-derived paper structure
- `references/acl-arr-latex-guide.md`: ACL ARR formatting guidance
- `references/research-writing-patterns.md`: distilled paper-writing patterns from the local skill library
- `examples/`: minimal working example and sample output artifacts
- `CHANGELOG.md`: release notes for public versions

## Install

Install the skill into Codex from a local path:

```bash
npx skills add /path/to/acl-arr-paper-drafter -g -a codex -y
```

Or copy the folder into your global Codex skills directory:

```bash
cp -R acl-arr-paper-drafter ~/.codex/skills/
```

## Usage

Basic invocation:

```text
Use $acl-arr-paper-drafter to draft an anonymized ACL ARR style LaTeX paper from my topic and materials, using deep research when needed.
```

Concrete example:

```text
Use $acl-arr-paper-drafter to draft an anonymized ACL ARR style LaTeX paper.

Topic: Personality in LLM agents

Materials:
- ./notes/personality-agent-ideas.md
- ./drafts/related-papers.pdf
- https://arxiv.org/abs/2305.02547
- https://arxiv.org/abs/2402.02896

Requirements:
- use deep research for recent related work
- follow the official ACL style files
- build a claim-evidence matrix before writing
- keep unsupported experimental claims as TODO comments
```

## Example Output

The repository includes a minimal example:

- `examples/personality-in-llm-agents-minimal.tex`
- `examples/personality-in-llm-agents-minimal.bib`
- `examples/personality-in-llm-agents-minimal.pdf`

## Design Notes

This repository is organized similarly to public skill repositories such as `anthropics/skills` and `vercel-labs/agent-skills`: the main behavior lives in `SKILL.md`, reusable supporting knowledge lives in `references/`, and example artifacts live in `examples/`.

The main design choice is to preserve the user's paper framework while improving writing quality through explicit planning layers. That means the skill does not replace the outline with a generic paper structure; it strengthens the outline with evidence discipline, citation discipline, and submission-aware storytelling.

## References

- [ACL style files](https://github.com/acl-org/acl-style-files)
- [EMNLP 2026 main conference CFP](https://2026.emnlp.org/calls/main_conference_papers/#paper-submission-details)
- [academic-writing-cs skill example](https://www.skill-gallery.jp/skills/SipengXie2024/academic-writing-cs)

## License

MIT
