![logo_ironhack_blue 7](https://user-images.githubusercontent.com/23629340/40541063-a07a0a8a-601a-11e8-91b5-2f13e4e6b441.png)

# Lab | Statistical Story Dashboard

## Overview

Numbers alone rarely convince anyone. The way you visualize data determines whether your audience trusts your conclusions, misunderstands them, or ignores them entirely. In this lab you will sharpen the skill that separates a competent analyst from a great one: turning statistical evidence into clear, honest, and compelling visual narratives.

You will start by deconstructing three intentionally misleading charts — the kind you encounter in news articles, slide decks, and dashboards every day. After diagnosing what makes each chart deceptive, you will redesign them so the same data tells an accurate story. From there, you will build your own three-panel visual report that answers specific questions from a dataset, layer in uncertainty indicators such as error bars and confidence bands, and annotate your plots so they stand on their own without a presenter walking through them.

The lab wraps up with a peer review exercise where you apply a structured checklist to evaluate another team's visualizations. By the end, you will have a portfolio-ready dashboard and a sharper eye for both creating and critiquing data graphics.

## Learning Goals

By the end of this lab, you should be able to:

- Identify common chart deception techniques (truncated axes, misleading scales, cherry-picked ranges) and explain why they distort the message.
- Redesign a misleading chart so that the same data is presented accurately and effectively.
- Build a multi-panel figure in Matplotlib/Seaborn that answers a set of related data questions in a single view.
- Add error bars, confidence bands, and shaded uncertainty regions to plots using standard Python libraries.
- Write concise, informative annotations and titles that guide the reader through statistical findings.
- Apply a peer review checklist to give constructive, criteria-based feedback on data visualizations.

## Setup and Context

This lab uses a pre-loaded dataset provided in the starter notebook. The dataset contains enough variety (continuous variables, categorical groups, time-based observations) to support the different visualization tasks below.

You will work in a single Jupyter notebook and produce all your figures inline. Think of the notebook itself as a draft dashboard — each section should read top-to-bottom as a coherent story.

## Requirements

- Fork this repo and clone it to your local machine.
- Open the notebook `m3-11-statistical-story-dashboard.ipynb`.
- Make sure the following Python packages are available (install any that are missing):

```bash
pip install pandas numpy matplotlib seaborn scipy
```

## Getting Started

1. Fork and clone the repository.
2. Open the notebook and run the setup cell to load the dataset and helper functions.
3. Read through each task section before writing code — several tasks build on earlier outputs.
4. Save your figures inside the notebook (inline). No separate image exports are required unless you want them for your portfolio.

## Tasks

### Task 1: Chart Critique — Spot the Deception

The notebook provides three intentionally misleading charts (generated for you in the starter cells). For each chart:

1. **Identify the deception technique** being used (e.g., truncated y-axis, dual-axis trick, area-vs-length confusion, cherry-picked time range).
2. **Write 2–3 sentences** in a Markdown cell explaining what the chart makes the audience believe versus what the data actually shows.
3. **Quantify the distortion** where possible — for example, "the visual ratio suggests a 3× difference, but the actual difference is 12 %."

Deliverable: three Markdown cells (one per chart), each with the deception type, a plain-language explanation, and a distortion estimate.

### Task 2: Chart Redesign — Fix the Story

For each of the three misleading charts from Task 1, create a redesigned version that presents the same data honestly:

1. Use an appropriate chart type and axis range.
2. Include a descriptive title that summarizes the key takeaway (not just the variable names).
3. Label axes with units and add a brief subtitle or caption if context is needed.
4. Use color intentionally — highlight comparisons, don't just decorate.

Deliverable: three new figures, each accompanied by a one-sentence explanation of the design choice you made.

### Task 3: Three-Panel Visual Report

Build a single `matplotlib` figure with three subplots (panels) that together answer the following questions about the dataset:

1. **Distribution panel**: How is the primary outcome variable distributed, and where do key subgroups sit within that distribution?
2. **Comparison panel**: Do the group means differ, and how much do they overlap?
3. **Trend panel**: How has the outcome changed over time (or across an ordered variable), and is the trend consistent across groups?

Requirements for each panel:
- A clear, specific title (not "Plot 1").
- Axis labels with units.
- A legend if multiple groups are shown.
- Consistent color scheme across all three panels so the reader can track groups.

Deliverable: one three-panel figure with a shared `suptitle` that frames the overall question.

### Task 4: Uncertainty Indicators

Go back to the comparison and trend panels from Task 3 and enhance them with uncertainty information:

1. **Comparison panel**: add 95 % confidence interval error bars to each group mean (bootstrap or analytical — your choice).
2. **Trend panel**: add a shaded confidence band around each group's trend line using `fill_between`.
3. For at least one panel, add a brief annotation (using `ax.annotate` or `ax.text`) that states the key statistical finding in plain language — for example, "Group A's mean is 4.2 points higher (95 % CI: 1.8–6.6)."

Deliverable: updated two-panel figure (or the full three-panel figure) with error bars, bands, and at least one in-plot annotation.

### Task 5: Annotated Statistical Storytelling

Create one final "hero" chart — a single, polished figure that could appear in a stakeholder presentation. This chart should:

1. Combine data, uncertainty, and annotation into one view.
2. Use `ax.annotate` with arrows to call out at least two specific data points or regions of interest.
3. Include a text box (`ax.text` with `bbox`) summarizing the statistical conclusion.
4. Follow best practices: high contrast, no chart junk, readable font sizes, and an informative title.

Deliverable: one publication-quality figure with annotations and a summary text box.

### Task 6: Peer Review Checklist

Use the checklist below to evaluate either your own dashboard (Tasks 1–5) or a classmate's. Fill in the checklist as a Markdown table in your notebook:

| Criterion | Yes / No | Notes |
|---|---|---|
| Axes start at zero (or truncation is justified and labeled) | | |
| Chart type matches the data type (categorical → bar, continuous → histogram/density, time → line) | | |
| Titles describe the insight, not just the variable | | |
| Uncertainty is shown where applicable | | |
| Color encodes information, not decoration | | |
| Annotations are concise and non-redundant | | |
| The dashboard tells a coherent top-to-bottom story | | |

Write a short paragraph (3–5 sentences) summarizing the strengths of the dashboard and one concrete suggestion for improvement.

Deliverable: completed checklist table and a summary paragraph.

## Submission

### What to submit

- Your completed Jupyter notebook (`m3-11-statistical-story-dashboard.ipynb`) with all tasks, figures, and Markdown responses.

### Definition of done

- [ ] Three chart critiques with identified deception techniques and distortion estimates (Task 1).
- [ ] Three redesigned charts with honest, clearly labeled presentations (Task 2).
- [ ] One three-panel visual report answering the three specified questions (Task 3).
- [ ] Uncertainty indicators (error bars, confidence bands, annotations) added to at least two panels (Task 4).
- [ ] One polished "hero" chart with annotations and a statistical summary text box (Task 5).
- [ ] Completed peer review checklist and summary paragraph (Task 6).
- [ ] All cells run without errors from top to bottom.

### How to submit

```bash
git add .
git commit -m "lab: complete statistical story dashboard"
git push origin main
```

Upload your file to the learning platform when finished.
