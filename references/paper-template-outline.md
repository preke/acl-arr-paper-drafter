# Paper Template Outline

This outline is extracted from the user's `Research Paper.xmind` file. Use it as the default narrative structure for the first draft.

## Abstract

- Treat the abstract as a concise summary of the introduction.

## Introduction

### Background

- Explain what problem is being studied.
- Add a toy example when it helps make the problem concrete.
- Explain why the problem matters now.
- Add statistics or trend evidence when available.
- Explain likely applications or downstream impact.

### Motivation

- Judge whether existing work already solves the problem well.
- Surface unresolved challenges or shortcomings.
- Break limitations into challenge 1, challenge 2, challenge 3, and so on.

### Intuition and Method

- Introduce the proposed method and the intended effect.
- Explain how the method addresses each challenge.

### Experiment Preview

- Preview the experimental design.
- Mention public datasets or benchmarks.
- Mention comparison with strong baselines.
- Mention ablations.

### Contributions

- State the important problem tackled.
- State the solution proposed.
- State how experiments validate the method.
- State what ablations reveal.
- Mention code or data release if applicable.

## Related Work

- Organize prior work into two major groups by default unless the topic needs a better taxonomy.
- For each group:
  - summarize representative papers
  - explain strengths
  - explain limitations
- End with a synthesis paragraph connecting the unresolved limitation to the proposed method.

## Methods

- Present an overview of the full pipeline or model.
- Include a problem definition subsection with:
  - inputs
  - outputs
  - assumptions or constraints
- Then describe subsection 1, subsection 2, subsection 3, or renamed modules that fit the actual method.

## Experiment Settings

### Experimental Setup

- datasets
- baseline models
- evaluation aspects
- metrics for each aspect

### Run Settings

- hardware or external APIs
- hyperparameters
- repeated runs, averages, standard deviations, or error bars when applicable

## Result Analysis

Organize the analysis around research questions.

### RQ1

- Does the proposed method solve the target problem effectively
- Main comparison table across datasets and baselines
- Analysis of strongest and weakest gains and likely causes

### RQ2

- Why does the method work
- Ablation tables
- Module importance analysis

### RQ3

- How does the method behave in realistic cases
- Qualitative cases, figures, or tables
- Success analysis and failure analysis

## Conclusion

- Rewrite the contribution summary in concise form.
- Restate the practical or scientific takeaway.
