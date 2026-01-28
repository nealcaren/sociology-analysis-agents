# Phase 3: Snowballing

You are expanding the corpus through citation networks. Your goal is to find important papers that keyword searches missed.

## Why This Phase Matters

Citation networks reveal the intellectual structure of a field. Backward snowballing finds foundational works; forward snowballing finds recent developments. Some of the most important papers won't match keyword searches.

## Prerequisites

- Load `data/screened/included.json`
- Read `memos/scope.md` for inclusion criteria

## Your Tasks

### 1. Backward Snowballing (References)

For each included paper, retrieve its references:

```python
import requests
from time import sleep

def get_references(openalex_id, max_refs=50):
    """Get papers cited by this work."""
    # OpenAlex includes referenced_works in the work object
    work_url = f"https://api.openalex.org/works/{openalex_id}"
    response = requests.get(work_url, params={"mailto": "your@email.com"})
    work = response.json()

    ref_ids = work.get("referenced_works", [])[:max_refs]

    # Fetch metadata for each reference
    references = []
    for ref_id in ref_ids:
        ref_url = f"https://api.openalex.org/works/{ref_id.split('/')[-1]}"
        try:
            ref_response = requests.get(ref_url, params={"mailto": "your@email.com"})
            if ref_response.status_code == 200:
                references.append(ref_response.json())
            sleep(0.1)
        except:
            continue

    return references
```

### 2. Forward Snowballing (Citations)

For each included paper, retrieve works that cite it:

```python
def get_citations(openalex_id, max_citations=50):
    """Get papers that cite this work."""
    base_url = "https://api.openalex.org/works"
    params = {
        "filter": f"cites:{openalex_id}",
        "per_page": max_citations,
        "sort": "cited_by_count:desc",
        "mailto": "your@email.com"
    }

    response = requests.get(base_url, params=params)
    return response.json().get("results", [])
```

### 3. Identify High-Value Candidates

Prioritize papers that appear multiple times in citation networks:

```python
from collections import Counter

def identify_candidates(included_papers):
    """Find papers that appear frequently in references/citations."""
    all_refs = []
    all_citations = []

    for paper in included_papers:
        refs = get_references(paper["openalex_id"])
        cites = get_citations(paper["openalex_id"])

        all_refs.extend([r["id"] for r in refs])
        all_citations.extend([c["id"] for c in cites])

    # Count occurrences
    ref_counts = Counter(all_refs)
    cite_counts = Counter(all_citations)

    # Papers appearing 3+ times are high priority
    frequent_refs = {id: count for id, count in ref_counts.items() if count >= 3}
    frequent_cites = {id: count for id, count in cite_counts.items() if count >= 3}

    return frequent_refs, frequent_cites
```

### 4. Screen Snowball Candidates

Apply the same screening logic as Phase 2:

```python
def screen_snowball_candidates(candidates, existing_ids, criteria):
    """Screen new papers found through snowballing."""
    new_papers = []

    for paper_id, appearance_count in candidates.items():
        # Skip if already in corpus
        if paper_id in existing_ids:
            continue

        # Fetch metadata
        paper = fetch_paper(paper_id)
        if not paper:
            continue

        # Apply screening
        decision, rationale = screen_paper(paper, criteria)

        new_papers.append({
            "paper": paper,
            "decision": decision,
            "rationale": rationale,
            "snowball_type": "backward" if paper_id in ref_counts else "forward",
            "appearance_count": appearance_count
        })

    return new_papers
```

### 5. Present Snowball Additions

Show the user what snowballing found:

```markdown
## Snowball Candidates

### Highly Cited References (Backward Snowballing)
Papers cited by 3+ included works:

| Title | Year | Cited By | Appearances | Decision |
|-------|------|----------|-------------|----------|
| [Foundational paper 1] | 2008 | 450 | 12/156 | Include? |
| [Foundational paper 2] | 2005 | 380 | 9/156 | Include? |

### Recent Citing Works (Forward Snowballing)
Papers citing 3+ included works:

| Title | Year | Citations | Appearances | Decision |
|-------|------|-----------|-------------|----------|
| [Recent paper 1] | 2024 | 5 | 4/156 | Include? |
| [Recent paper 2] | 2023 | 12 | 3/156 | Include? |

### Foundational Works Outside Date Range
These pre-date your range but are heavily referenced:

| Title | Year | Why Consider |
|-------|------|--------------|
| [Classic 1] | 1995 | Cited by 45% of corpus |
| [Classic 2] | 2001 | Foundational methods paper |

**Question**: Should we include foundational works that pre-date your date range?
```

### 6. Update Corpus

After user approval, merge snowball additions:

```python
def merge_snowball(original_corpus, snowball_additions):
    """Add approved snowball papers to corpus."""
    approved = [p for p in snowball_additions if p["user_decision"] == "include"]

    merged = {
        "original_count": len(original_corpus),
        "snowball_additions": len(approved),
        "total": len(original_corpus) + len(approved),
        "papers": original_corpus + [p["paper"] for p in approved]
    }

    return merged
```

### 7. Generate Citation Network Visualization

Create a simple network summary:

```markdown
## Citation Network Summary

**Core papers** (cited by 5+ included works):
1. [Paper A] - hub for theoretical framework
2. [Paper B] - key methods reference

**Bridge papers** (connect different clusters):
1. [Paper C] - links quantitative and qualitative traditions

**Emerging work** (2023-2024, already accumulating citations):
1. [Paper D] - 15 citations in first year
```

## Output Files

Save to `data/screened/included_with_snowball.json`:

```python
output = {
    "snowball_metadata": {
        "date": "2024-01-15",
        "backward_candidates_found": 89,
        "forward_candidates_found": 124,
        "approved_additions": 23
    },
    "papers": merged_corpus
}
```

Also update `memos/screening_log.md` with snowball decisions.

## Guiding Principles

- **Trust the network**: Papers cited by many included works are likely relevant
- **Catch recent work**: Forward snowballing finds papers too new for keyword indexing
- **Respect the scope**: Foundational works may warrant exception to date range
- **Document provenance**: Track how each paper entered the corpus

## When You're Done

Tell the orchestrator:
> "Phase 3 complete. Snowballing found N backward and M forward candidates. X approved additions merged. Expanded corpus now contains Y papers. Ready for full text acquisition."

**Do not proceed to Phase 4 until the user approves snowball additions.**
