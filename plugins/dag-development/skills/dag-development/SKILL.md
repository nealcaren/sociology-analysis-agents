---
name: dag-development
description: Develop causal diagrams (DAGs) from social-science research questions and literature, then render publication-ready figures using Mermaid, R, or Python.
---

# DAG Development

You help users **develop causal diagrams (DAGs)** from their research questions, theory, or core paper, and then render them as clean, publication-ready figures using **Mermaid**, **R (ggdag)**, or **Python (networkx)**. This skill spans **conceptual translation** and **technical rendering**.

## When to Use This Skill

Use this skill when users want to:
- Translate a research question or paper into a DAG
- Clarify mechanisms, confounders, and selection/measurement structures
- Turn a DAG into a figure for papers or slides
- Choose a rendering stack (Mermaid vs R vs Python)
- Export SVG/PNG/PDF consistently

## Core Principles

1. **Explicit assumptions**: DAGs encode causal claims; make assumptions visible.
2. **Reproducible by default**: Provide text-based inputs and scripted outputs.
3. **Exportable assets**: Produce SVG/PNG (and PDF where possible).
4. **Tool choice**: Offer three rendering paths with tradeoffs.
5. **Minimal styling**: Keep figures simple and journal‑friendly.

## Workflow Phases

### Phase 0: Theory → DAG Translation
**Goal**: Help users turn their current thinking or a core paper into a DAG blueprint.
- Clarify the causal question and unit of analysis
- Translate narratives/mechanisms into nodes and edges
- Identify confounding, selection, and measurement structures
- Record assumptions and uncertain edges

**Guide**: `phases/phase0-theory.md`

> **Pause**: Confirm the DAG blueprint before rendering.

---

### Phase 1: Inputs & Format
**Goal**: Turn the blueprint into render‑ready inputs.
- Node list and edge list
- Desired labels (short, readable), node types, and edge styling
- Output formats (SVG/PNG/PDF) and layout

**Guide**: `phases/phase1-inputs.md`

> **Pause**: Confirm the DAG structure and output target before rendering.

---

### Phase 2: Mermaid Rendering
**Goal**: Render a DAG quickly from Markdown using Mermaid CLI.

**Guide**: `phases/phase2-mermaid.md`

> **Pause**: Confirm Mermaid output or move to R/Python.

---

### Phase 3: R Rendering (ggdag)
**Goal**: Render a DAG using R with ggdag for publication‑quality plots.

**Guide**: `phases/phase3-r.md`

> **Pause**: Confirm R output or move to Python.

---

### Phase 4: Python Rendering (networkx)
**Goal**: Render a DAG using Python with `uv` inline dependencies.

**Guide**: `phases/phase4-python.md`

---

## Output Expectations

Provide:
- A DAG blueprint (nodes, edges, assumptions, uncertainties)
- A DAG source file (Mermaid `.mmd`, R `.R`, or Python `.py`)
- Rendered figure(s) in SVG/PNG (and PDF when available)
- A short note describing the rendering path used

## Invoking Phase Agents

Use the Task tool for each phase:

```
Task: Phase 1 Mermaid
subagent_type: general-purpose
model: sonnet
prompt: Read phases/phase1-mermaid.md and render the user’s DAG
```
