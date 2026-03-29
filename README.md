# ACL ARR Paper Drafter

`acl-arr-paper-drafter` is a Codex skill for drafting anonymized ACL ARR style LaTeX papers from a topic plus mixed supporting materials.

It is designed for research workflows where the user may provide:

- PDFs
- Word documents
- Markdown notes
- local files
- links to papers, benchmarks, datasets, or repositories
- requests for additional deep web research

The skill reads those materials, follows a paper template derived from an XMind outline, applies the official ACL style conventions, and produces a first-pass LaTeX draft without fabricating unsupported results or citations.

It also incorporates claim-driven paper planning patterns inspired by local research-writing skills: claim-evidence mapping, citation planning, submission-aware drafting, explicit open-gap reporting, and a problem -> solution -> evidence narrative arc.

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

## Repository Structure

- `SKILL.md`: core skill instructions and triggering metadata
- `agents/openai.yaml`: UI-facing metadata
- `references/paper-template-outline.md`: XMind-derived paper structure
- `references/acl-arr-latex-guide.md`: ACL ARR formatting guidance
- `references/research-writing-patterns.md`: distilled paper-writing patterns from the local skill library
- `examples/`: minimal working example, `.tex`, and `.bib`

## Install

Install the skill into Codex from a local path:

```bash
npx skills add /path/to/acl-arr-paper-drafter -g -a codex -y
```

Or copy the folder into your global Codex skills directory:

```bash
cp -R acl-arr-paper-drafter ~/.codex/skills/
```

## Use

Example invocation:

```text
Use $acl-arr-paper-drafter to draft an anonymized ACL ARR style LaTeX paper from my topic and materials, using deep research when needed.
```

Example with a concrete topic:

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

You can compile the example locally to generate:

- `examples/personality-in-llm-agents-minimal.pdf`

## Design Notes

This repository is organized similarly to public skill repositories such as `anthropics/skills` and `vercel-labs/agent-skills`: the core skill stays in `SKILL.md`, reusable supporting material lives in `references/`, and examples live in `examples/`.

## References

- [ACL style files](https://github.com/acl-org/acl-style-files)
- [EMNLP 2026 main conference CFP](https://2026.emnlp.org/calls/main_conference_papers/#paper-submission-details)

## License

MIT
