# Phase 3: R Rendering (ggdag)

You are rendering a DAG using R with `ggdag` (built on ggplot2). This is good for publication‑quality figures.

## Input

Use the confirmed node/edge list from Phase 0.

## R Script Template (Verified)

Create `dag_r.R`:

```r
library(ggdag)

# Define a simple DAG
x <- dagitty::dagitty('dag { X -> M -> Y; X -> Y; Z -> X; Z -> Y }')

# Plot and save
p <- ggdag(x, layout = 'circle') + ggplot2::theme_void()

ggplot2::ggsave('dag_r.png', p, width = 5, height = 4, dpi = 150)
```

## Run

```
Rscript dag_r.R
```

## Output

Provide:
- `dag_r.R`
- `dag_r.png`

## When You’re Done

Return a short summary of the files created and any layout adjustments made.
