# Phase 1: Inputs & Format

You are collecting the minimum required inputs to render a DAG figure.

## Required Inputs

Ask for:
- **Nodes**: Short labels (2–8 words max). If longer names are needed, define a legend.
- **Edges**: Directed edges in `A -> B` format.
- **Node types**: observed, unobserved (U), selection (S), measurement (M).
- **Uncertain edges**: list any edges to be styled as dashed/dotted.
- **Output**: Preferred format(s): SVG, PNG, PDF.
- **Tool preference**: Mermaid, R, Python, or “show options”.

If Phase 0 produced a DAG blueprint, extract the above directly from it.

## Optional Rendering Choices

Offer (do not require):
- **Layout**: left‑to‑right (LR), top‑down (TD), or circular.
- **Grouping**: subgraphs like *context*, *mechanisms*, *selection*.
- **Styling**: color for observed vs unobserved; dashed for uncertain edges; dotted for selection/measurement paths.
- **Target use**: paper, slide, appendix (affects size and format).

## Example Input Format

```
Nodes:
- Z (confounder)
- X (exposure)
- M (mediator)
- Y (outcome)
 - U1 (unobserved)
 - S (selection)

Edges:
- Z -> X
- Z -> Y
- X -> M
- M -> Y
- X -> Y
 - U1 -> X
 - U1 -> Y
 - X -> S
 - Y -> S

Uncertain edges:
- U1 -> X
- U1 -> Y

Node types:
- observed: Z, X, M, Y
- unobserved: U1
- selection: S

Output: SVG + PNG
Tool: Mermaid
Layout: LR
Target: paper
```

## If the User Only Has a Sketch

Offer to translate:
- Hand‑drawn DAG → node/edge list
- Equation models → DAG edges

## Output

Summarize:
- Confirmed node list and node types
- Confirmed edge list + uncertain edges
- Chosen rendering tool, output formats, and layout

## When You’re Done

Return a short intake memo to the orchestrator with the inputs above.
