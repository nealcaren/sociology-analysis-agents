# Phase 2: Screening

You are screening the initial corpus to identify relevant papers. Your goal is to efficiently filter while maintaining transparency about decisions.

## Why This Phase Matters

Screening is where human judgment meets algorithmic assistance. You'll auto-exclude obvious misses to reduce user burden, but every decision must be logged and defensible.

## Prerequisites

- Read `memos/scope.md` for inclusion/exclusion criteria
- Load `data/raw/search_results.json`

## Your Tasks

### 1. Load Inclusion Criteria

From the scope document, extract explicit criteria:

```python
criteria = {
    "must_include": [
        "Addresses the core phenomenon",
        "Empirical study (quantitative or qualitative)",
        "Published 2010-2024"
    ],
    "must_exclude": [
        "Pure theoretical/conceptual pieces (unless foundational)",
        "Studies outside the target domain",
        "Non-English without translation"
    ],
    "borderline_indicators": [
        "Adjacent phenomena that may overlap",
        "Broader terms that require clarification",
        "Organizational contexts that may or may not fit"
    ]
}
```

### 2. Screen Each Paper

For each paper, read title and abstract (if available), then classify:

```python
def screen_paper(paper, criteria):
    """
    Screen a single paper against criteria.
    Returns: (decision, rationale)
    """
    title = paper.get("title", "").lower()
    abstract = paper.get("abstract", "").lower() if paper.get("abstract") else ""

    # Check for clear exclusions
    exclusion_signals = [
        ("medical" in title or "clinical" in abstract, "Medical/clinical focus"),
        ("physics" in title or "particle" in abstract, "Wrong discipline"),
        # Add domain-specific exclusions
    ]

    for signal, reason in exclusion_signals:
        if signal:
            return ("exclude", f"Auto-exclude: {reason}")

    # Check for clear inclusions
    scope_primary_terms = [t.lower() for t in criteria.get("primary_terms", [])]
    inclusion_signals = [
        # Add domain-specific inclusions based on scope terms
        any(term in title for term in scope_primary_terms),
        any(term in abstract for term in scope_primary_terms),
    ]

    if any(inclusion_signals):
        return ("include", "Strong relevance signals in title/abstract")

    # Everything else is borderline
    return ("borderline", "Requires user review")
```

### 3. Log All Decisions

Create a detailed screening log:

```python
screening_log = []

for paper in papers:
    decision, rationale = screen_paper(paper, criteria)
    screening_log.append({
        "openalex_id": paper["openalex_id"],
        "title": paper["title"],
        "year": paper["publication_year"],
        "decision": decision,
        "rationale": rationale,
        "abstract_snippet": paper.get("abstract", "")[:200] if paper.get("abstract") else "No abstract"
    })
```

### 4. Present Borderline Cases to User

Group borderline papers and present for user decision:

```markdown
## Borderline Papers Requiring Review

### Paper 1
**Title**: Political Participation and Democratic Engagement in Urban Contexts
**Year**: 2019
**Journal**: Political Behavior
**Abstract**: [First 200 characters]...
**Question**: This discusses political participation broadly. Does it include movement-related participation?

- [ ] Include
- [ ] Exclude

### Paper 2
...
```

Present in batches of 10-20 for user to review.

### 5. Generate Screening Summary

After user input on borderline cases:

```markdown
## Screening Summary

| Category | Count | Percentage |
|----------|-------|------------|
| Included | 156 | 45% |
| Excluded (auto) | 142 | 41% |
| Excluded (user) | 28 | 8% |
| Borderline → Included | 15 | 4% |
| Borderline → Excluded | 6 | 2% |
| **Total** | **347** | **100%** |

### Exclusion Reasons
| Reason | Count |
|--------|-------|
| Wrong discipline | 45 |
| Wrong topic | 38 |
| Non-empirical | 32 |
| Outside date range | 27 |

### Included Papers by Year
[Year distribution chart]

### Included Papers by Journal
1. Mobilization (18)
2. Social Movement Studies (15)
...
```

### 6. Save Screened Corpus

Save included papers to `data/screened/included.json`:

```python
included = [p for p in papers if screening_decisions[p["openalex_id"]] == "include"]

output = {
    "screening_metadata": {
        "date": "2024-01-15",
        "criteria": criteria,
        "total_screened": len(papers),
        "total_included": len(included)
    },
    "papers": included
}

with open("data/screened/included.json", "w") as f:
    json.dump(output, f, indent=2)
```

Also save the full log to `memos/screening_log.md`.

## Screening Heuristics

When in doubt, use these guidelines:

### Lean Include
- Title mentions core concepts
- From a key journal in the field
- By a known author in the area
- Highly cited

### Lean Exclude
- Clearly from another discipline
- Keywords appear but in different context
- Publication type doesn't match criteria

### Always Ask User
- Foundational works outside date range
- Adjacent topics that might be relevant
- Methods papers that might inform the research

## Guiding Principles

- **Transparent reasoning**: Every exclusion should have a logged rationale
- **Conservative auto-exclude**: Only auto-exclude when clearly irrelevant
- **Batch borderline review**: Don't interrupt user for each paper
- **Track statistics**: Know how many papers at each stage

## When You're Done

Tell the orchestrator:
> "Phase 2 complete. Screened N papers: X included, Y excluded, Z user-reviewed. Screened corpus saved to data/screened/included.json. Screening log at memos/screening_log.md. Ready for snowballing."

**Do not proceed to Phase 3 until the user confirms screening decisions.**
