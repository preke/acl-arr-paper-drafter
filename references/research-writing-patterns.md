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

## 10. ACL / EMNLP Paper Story Pattern

For strong empirical NLP papers, prefer this story shape:

- a meaningful blind spot, overlooked failure mode, or under-specified capability
- a benchmark, protocol, taxonomy, or analysis framework that makes the issue measurable
- a systematic evaluation across models, settings, or populations
- a small set of robust findings
- an optional simple mitigation if the evidence supports it

This pattern is often stronger than a generic "new framework" story because it gives reviewers a crisp problem, a measurable setup, and concrete takeaways.

Do not force every paper into this mold. Use it when the paper is fundamentally diagnostic, evaluative, safety-oriented, socially grounded, or benchmark-driven.

## 11. Title Patterns

Prefer titles that combine a memorable observation with a precise technical subtitle.

Reusable title forms:

- `Not All X Do Y: On the [Failure Mode] in [Models]`
- `[Short Memorable Phrase]: Evaluating [Capability] of [Models] via [Protocol]`
- `[BenchmarkName]: Measuring [Phenomenon] in [Models]`
- `[Actionable Claim]: Improving [Capability] in [Models] via [Method]`
- `Can [Models] [Do X]? Benchmarking [Capability] with [BenchmarkName]`

Guidelines:

- the first half should create recall, usually by naming an observation, conflict, or tension
- the second half should state the exact object, task, and framing
- avoid vague titles that only say "A Framework for..." unless the framework is already grounded by the problem

## 12. Abstract Skeleton

Default abstract order:

1. broad capability or trend
2. exact gap in existing evaluation or methods
3. what the paper proposes
4. scale of the study with concrete numbers
5. main empirical finding
6. secondary finding or failure pattern
7. optional mitigation result
8. why the finding matters

Compact template:

```text
[Models] have shown strong performance on [broad area].
However, existing work mainly focuses on [mainstream setting], leaving an important gap in [blind spot].
To address this issue, we propose [benchmark / framework / dataset / method], which evaluates [exact capability] through [task design].
Our study covers [N models], [N settings], and [N examples / dimensions / languages].
Results show that [finding 1].
We further find that [finding 2].
Finally, [simple intervention] improves / mitigates [issue] by [result], highlighting [takeaway].
```

Abstract rules:

- include at least one hard number when available
- distinguish findings from interpretation
- avoid hype words if the evidence is mostly diagnostic
- if experiments are incomplete, explicitly frame the evidence as planned rather than completed

## 13. Introduction Skeleton

A reliable five-paragraph introduction:

1. why the broader capability or risk matters now
2. what exact gap remains in prior work
3. why this gap is non-trivial to study
4. what benchmark / method / framing the paper introduces
5. what the paper finds and contributes

Useful paragraph roles:

- `Background`: establish stakes without overexplaining the field
- `Gap`: narrow from broad importance to the specific missing evaluation, failure mode, or limitation
- `Challenge`: explain why the gap survives despite strong prior work
- `Approach`: define the paper's operationalization of the problem
- `Contributions`: list only concrete deliverables and findings

## 14. Contribution Template

Keep contributions specific and evidence-facing:

- `We identify a previously under-examined issue: [phenomenon].`
- `We operationalize this issue with [dataset / protocol / rubric / taxonomy].`
- `We conduct a large-scale evaluation across [models / tasks / languages / groups].`
- `We uncover several robust findings, including [finding 1] and [finding 2].`
- `We further show that [simple method] can mitigate [issue].`

Avoid generic contribution bullets such as "we provide insights" without specifying what was learned.

## 15. Experiment Narrative Pattern

For empirical papers, a stable section order is:

1. experimental setup
2. main results
3. fine-grained analysis
4. case studies or qualitative evidence
5. mitigation or ablation results
6. discussion

Within results sections:

- answer the main research question before showing ablations
- separate observations from explanations
- use subgroup analysis to expose systematic behavior, not just to add tables
- keep mitigation claims proportional to the diagnosis

## 16. Result Language

Prefer finding-oriented wording:

- `We find that even frontier models struggle with ...`
- `Performance varies substantially across ...`
- `The gap is especially pronounced in ...`
- `A simple intervention already yields noticeable gains, suggesting that ...`

Prefer cautious language when appropriate:

- `suggests`
- `indicates`
- `highlights`
- `reveals`

Avoid inflated phrasing such as:

- `solves a long-standing challenge`
- `demonstrates unprecedented capability`
- `significantly outperforms all prior work` unless this is directly established
