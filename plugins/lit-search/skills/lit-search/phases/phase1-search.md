# Phase 1: Initial Search

You are executing the literature search using the OpenAlex API. Your goal is to build an initial corpus of potentially relevant papers.

## Why This Phase Matters

This phase translates the scope document into actual data. Good API queries maximize recall (finding relevant papers) while keeping the corpus manageable for screening.

## Prerequisites

- Read `memos/scope.md` for search terms and filters
- Read `api/openalex-reference.md` for API syntax

## Your Tasks

### 1. Execute Primary Searches

Run the planned queries against OpenAlex. Use Python with the `requests` library:

```python
import requests
import json
from time import sleep

def search_openalex(query, filters, max_results=500):
    """
    Search OpenAlex with pagination.
    """
    base_url = "https://api.openalex.org/works"
    results = []
    cursor = "*"

    while len(results) < max_results:
        params = {
            "search": query,
            "filter": filters,
            "per_page": 100,
            "cursor": cursor,
            "mailto": "your@email.com"  # Polite pool for faster responses
        }

        response = requests.get(base_url, params=params)
        data = response.json()

        if "results" not in data or not data["results"]:
            break

        results.extend(data["results"])
        cursor = data["meta"].get("next_cursor")

        if not cursor:
            break

        sleep(0.1)  # Rate limiting

    return results[:max_results]

# Example usage
results = search_openalex(
    query="[primary term 1] [primary term 2]",
    filters="from_publication_date:2010-01-01,type:journal-article,language:en",
    max_results=500
)
```

### 2. Extract Key Metadata

For each paper, extract and store:

```python
def extract_metadata(work):
    """Extract relevant fields from OpenAlex work."""
    return {
        "openalex_id": work.get("id"),
        "doi": work.get("doi"),
        "title": work.get("title"),
        "publication_year": work.get("publication_year"),
        "abstract": work.get("abstract_inverted_index"),  # Needs reconstruction
        "authors": [a.get("author", {}).get("display_name") for a in work.get("authorships", [])],
        "journal": work.get("primary_location", {}).get("source", {}).get("display_name"),
        "cited_by_count": work.get("cited_by_count"),
        "concepts": [c.get("display_name") for c in work.get("concepts", [])[:5]],
        "open_access": work.get("open_access", {}).get("is_oa"),
        "oa_url": work.get("open_access", {}).get("oa_url"),
        "referenced_works": work.get("referenced_works", []),
        "cited_by_api_url": work.get("cited_by_api_url")
    }

def reconstruct_abstract(inverted_index):
    """Reconstruct abstract from OpenAlex inverted index format."""
    if not inverted_index:
        return None
    word_positions = []
    for word, positions in inverted_index.items():
        for pos in positions:
            word_positions.append((pos, word))
    word_positions.sort()
    return " ".join(word for pos, word in word_positions)
```

### 3. Deduplicate Results

Papers may appear in multiple queries. Deduplicate by DOI and OpenAlex ID:

```python
def deduplicate(results):
    """Remove duplicate papers."""
    seen_ids = set()
    unique = []
    for paper in results:
        paper_id = paper.get("doi") or paper.get("openalex_id")
        if paper_id and paper_id not in seen_ids:
            seen_ids.add(paper_id)
            unique.append(paper)
    return unique
```

### 4. Generate Corpus Statistics

Create summary statistics to help the user assess the search:

```python
from collections import Counter

def corpus_stats(papers):
    """Generate descriptive statistics."""
    years = Counter(p["publication_year"] for p in papers if p["publication_year"])
    journals = Counter(p["journal"] for p in papers if p["journal"])

    stats = {
        "total_papers": len(papers),
        "year_range": f"{min(years.keys())}-{max(years.keys())}",
        "year_distribution": dict(sorted(years.items())),
        "top_journals": journals.most_common(10),
        "papers_with_abstracts": sum(1 for p in papers if p.get("abstract")),
        "open_access_count": sum(1 for p in papers if p.get("open_access")),
        "median_citations": sorted([p["cited_by_count"] for p in papers])[len(papers)//2]
    }
    return stats
```

### 5. Save Raw Results

Save to `data/raw/search_results.json`:

```python
output = {
    "search_metadata": {
        "date": "2024-01-15",
        "queries": ["query1", "query2"],
        "filters": "from_publication_date:2010-01-01,..."
    },
    "statistics": corpus_stats(papers),
    "papers": papers
}

with open("data/raw/search_results.json", "w") as f:
    json.dump(output, f, indent=2)
```

## Output Summary

Present to the user:

```markdown
## Initial Search Results

**Total papers found**: 347 (after deduplication)

### Year Distribution
| Year | Count |
|------|-------|
| 2024 | 28    |
| 2023 | 45    |
| ...  | ...   |

### Top Journals
1. Mobilization (23 papers)
2. Social Movement Studies (19 papers)
3. American Sociological Review (12 papers)
...

### Corpus Characteristics
- Papers with abstracts: 341/347 (98%)
- Open access available: 156/347 (45%)
- Median citations: 12

### Sample Titles (most cited)
1. [Title 1] (2018) - 245 citations
2. [Title 2] (2015) - 198 citations
...
```

## Guiding Principles

- **Cast a wide net**: Include papers you're unsure about; screening comes next
- **Check coverage**: If key papers you expected are missing, refine queries
- **Mind the API**: Use polite pool (mailto) and rate limiting
- **Save raw data**: Never modify raw results; work from copies

## When You're Done

Tell the orchestrator:
> "Phase 1 complete. Initial corpus of N papers saved to data/raw/search_results.json. Statistics and sample titles presented. Ready for user review before screening."

**Do not proceed to Phase 2 until the user reviews the corpus composition.**
