# Phase 4: Python Rendering (uv + networkx)

You are rendering a DAG using Python with inline dependencies via `uv`. This is good for scriptable, cross‑platform outputs.

## Input

Use the confirmed node/edge list from Phase 0.

## Python Script Template (Verified)

Create `dag_py.py`:

```python
import networkx as nx
import matplotlib.pyplot as plt

G = nx.DiGraph()
G.add_edges_from([
    ('Z','X'),
    ('X','M'),
    ('M','Y'),
    ('X','Y'),
    ('Z','Y'),
])

pos = nx.spring_layout(G, seed=7)

plt.figure(figsize=(4,3))
ax = plt.gca()
nx.draw_networkx_nodes(G, pos, node_color='#E6F2FF', edgecolors='#1F4E79', node_size=1200, ax=ax)
nx.draw_networkx_labels(G, pos, font_size=10, ax=ax)
nx.draw_networkx_edges(G, pos, arrows=True, arrowstyle='-|>', arrowsize=16, width=1.5, ax=ax)
plt.axis('off')
plt.tight_layout()
plt.savefig('dag_py.png', dpi=150)
print('wrote dag_py.png')
```

## Run with uv (Verified)

```
uv run --with networkx --with matplotlib python dag_py.py
```

## Output

Provide:
- `dag_py.py`
- `dag_py.png`

## When You’re Done

Return a short summary of the files created and any layout adjustments made.
