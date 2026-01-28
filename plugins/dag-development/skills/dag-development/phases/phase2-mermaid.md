# Phase 2: Mermaid Rendering

You are rendering a DAG using Mermaid CLI. Mermaid is best for quick, text‑based diagrams that live in Markdown.

## Input

Use the confirmed node/edge list from Phase 0.

## Mermaid Source Template

Create `dag.mmd`:

```
flowchart LR
  Z --> X
  X --> M
  M --> Y
  X --> Y
  Z --> Y
```

Use `LR` (left‑to‑right) for most diagrams. Switch to `TD` (top‑down) if the diagram is tall.

## Render Command (Verified)

```
mmdc -i dag.mmd -o dag.svg
```

You can also render PNG:

```
mmdc -i dag.mmd -o dag.png
```

## Output

Provide:
- `dag.mmd`
- `dag.svg` (and/or `dag.png`)

## When You’re Done

Return a short summary of the files created and any layout adjustments made.
