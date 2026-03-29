# Research Writing Patterns

This reference distills reusable patterns from the local research-writing skills into a compact checklist for `acl-arr-paper-drafter`.

## 1. Claim-Evidence Matrix

Before drafting, write a compact matrix:

| Claim | Evidence | Status | Where It Appears |
|-------|----------|--------|------------------|
| main claim | main experiment or theorem | supported / partial / planned | intro, results |

Rules:

- Prefer one dominant claim plus at most one supporting claim.
- If a claim is only partially supported, weaken the prose.
- If a claim is not supported, convert it into future work or remove it.

## 2. Section Planning

Before drafting full prose, freeze:

- paper thesis
- paper narrative: problem -> solution -> evidence
- section order
- contribution list
- anti-claim to rule out

This keeps the draft coherent and avoids contribution sprawl.

## 3. Narrative Arc

Treat the paper as a controlled narrative, not a template fill-in exercise.

- Problem: what limitation, failure mode, or unmet need matters
- Solution: what idea, method, or perspective addresses it
- Evidence: what empirical or analytical support justifies the claims

Each major section should serve this arc:

- abstract: compressed whole story
- introduction: motivate the problem and preview the solution
- related work: sharpen the gap the paper actually addresses
- method: make the solution legible
- experiments/results: supply the evidence
- conclusion: restate the contribution at the same claim strength

## 4. Figure and Table Plan

For empirical papers, identify:

- hero figure or overview figure
- main comparison table
- ablation table
- qualitative case-study figure if needed

If the figures do not exist yet, describe them as planned artifacts rather than pretending they are ready.

## 5. Citation Plan

For each section, list:

- must-cite foundational papers
- recent comparison papers
- benchmark or dataset citations

Prefer verified citation sources over memory.

## 6. Honesty Gates

Before finalizing, ask:

- Is this claim directly supported?
- Is this number present in the materials?
- Is this related-work statement broader than the sources justify?
- Is this result completed, or only planned?

If uncertain, downgrade the claim or add a visible placeholder.

## 7. Submission-Aware Drafting

For ARR-style drafts:

- keep the draft anonymous by default
- include a limitations section
- keep the main paper scope compact
- put non-essential detail into appendix planning or TODO comments

## 8. Section-Level Quality Checks

Before finalizing, scan each section:

- abstract: contains task, method idea, and evidence status without hype
- introduction: states why the problem matters and what exact gap remains
- related work: groups prior work into meaningful categories and states the paper's boundary
- method: defines inputs, outputs, assumptions, and what is actually novel
- experimental setup: makes evaluation design reproducible enough for a first draft
- results and analysis: distinguishes observations from interpretation and from future work
- conclusion: does not claim more than the evidence established

## 9. Minimal Deliverables

A strong first draft package usually contains:

1. source inventory
2. claim-evidence matrix
3. citation plan
4. LaTeX draft
5. open gaps list
