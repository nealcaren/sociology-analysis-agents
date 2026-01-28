# OpenAlex API Reference

This guide covers the OpenAlex API features used in the literature review skill.

## Overview

OpenAlex is a free, open catalog of scholarly works with:
- 250M+ works (articles, books, datasets)
- Citation networks
- Open access links
- Author and institution data
- Concepts/topics taxonomy

**Base URL**: `https://api.openalex.org`

**No authentication required** for basic use (but use `mailto` parameter for polite pool).

## Core Endpoints

### Works (Papers)

```
GET /works
```

Query parameters:
- `search` - Full-text search across title and abstract
- `filter` - Structured filters (see below)
- `sort` - Sort order
- `per_page` - Results per page (max 200)
- `cursor` - Pagination cursor

### Authors

```
GET /authors
```

Find author profiles and their works.

### Sources (Journals)

```
GET /sources
```

Information about journals, repositories.

### Concepts

```
GET /concepts
```

OpenAlex's topic taxonomy.

## Search Syntax

### Basic Search

```
/works?search=educational inequality
```

Searches title, abstract, and full text (when indexed).

### Phrase Search

```
/works?search="collective action"
```

Use quotes for exact phrases.

### Boolean Operators

```
/works?search=inequality AND education
/works?search=neighborhood OR context
/works?search=education NOT psychology
```

## Filters

Filters use the format: `filter=field:value`

Multiple filters use commas: `filter=field1:value1,field2:value2`

### Date Filters

```python
# Papers from 2020 onward
filter = "from_publication_date:2020-01-01"

# Papers before 2024
filter = "to_publication_date:2023-12-31"

# Date range
filter = "from_publication_date:2010-01-01,to_publication_date:2024-12-31"
```

### Document Type

```python
# Journal articles only
filter = "type:journal-article"

# Multiple types
filter = "type:journal-article|book-chapter"

# Available types:
# journal-article, book, book-chapter, dataset, dissertation
# paratext, peer-review, reference-entry, report, standard, other
```

### Language

```python
# English only
filter = "language:en"

# Multiple languages
filter = "language:en|es|fr"
```

### Open Access

```python
# Only OA papers
filter = "is_oa:true"

# Specific OA type
filter = "oa_status:gold"  # gold, green, bronze, hybrid
```

### Journal/Source

```python
# Papers from specific journal
filter = "primary_location.source.id:S123456789"

# By journal name (need to look up ID first)
# Better: use concepts or search
```

### Citation Filters

```python
# Papers citing a specific work
filter = "cites:W123456789"

# Papers with minimum citations
filter = "cited_by_count:>10"

# Highly cited
filter = "cited_by_count:>100"
```

### Concept Filters

```python
# Papers tagged with a concept
filter = "concepts.id:C123456789"

# Find concept ID first:
# GET /concepts?search=educational inequality
```

### Author Filters

```python
# Papers by specific author
filter = "authorships.author.id:A123456789"
```

## Sorting

```python
# Most cited first
sort = "cited_by_count:desc"

# Most recent first
sort = "publication_date:desc"

# Relevance (for searches)
sort = "relevance:desc"

# By title alphabetically
sort = "display_name:asc"
```

## Pagination

OpenAlex uses cursor-based pagination:

```python
# First page
/works?search=inequality&per_page=100

# Response includes:
{
    "meta": {
        "count": 1234,
        "next_cursor": "abc123..."
    },
    "results": [...]
}

# Next page
/works?search=inequality&per_page=100&cursor=abc123...
```

## Response Format

### Work Object

```json
{
    "id": "https://openalex.org/W123456789",
    "doi": "https://doi.org/10.1234/example",
    "title": "Paper Title",
    "publication_year": 2023,
    "publication_date": "2023-06-15",

    "primary_location": {
        "source": {
            "id": "https://openalex.org/S123",
            "display_name": "American Sociological Review",
            "type": "journal"
        },
        "pdf_url": "https://...",
        "landing_page_url": "https://..."
    },

    "authorships": [
        {
            "author_position": "first",
            "author": {
                "id": "https://openalex.org/A123",
                "display_name": "Jane Smith",
                "orcid": "https://orcid.org/0000-0001-2345-6789"
            },
            "institutions": [...]
        }
    ],

    "cited_by_count": 45,
    "cited_by_api_url": "https://api.openalex.org/works?filter=cites:W123456789",

    "referenced_works": [
        "https://openalex.org/W111",
        "https://openalex.org/W222"
    ],

    "abstract_inverted_index": {
        "This": [0],
        "study": [1],
        "examines": [2]
    },

    "concepts": [
        {
            "id": "https://openalex.org/C123",
            "display_name": "Social movement",
            "level": 2,
            "score": 0.89
        }
    ],

    "open_access": {
        "is_oa": true,
        "oa_status": "gold",
        "oa_url": "https://..."
    }
}
```

### Reconstructing Abstract

OpenAlex stores abstracts as inverted indexes. Reconstruct:

```python
def reconstruct_abstract(inverted_index):
    """Convert inverted index to readable abstract."""
    if not inverted_index:
        return None

    # Build position -> word mapping
    positions = []
    for word, indices in inverted_index.items():
        for idx in indices:
            positions.append((idx, word))

    # Sort by position and join
    positions.sort(key=lambda x: x[0])
    return " ".join(word for _, word in positions)
```

## Rate Limits

- **Polite pool**: 10 requests/second (use `mailto` parameter)
- **Default**: 1 request/second

```python
# Add to all requests for faster access
params = {
    "search": "protest",
    "mailto": "your@email.edu"
}
```

## Common Query Patterns

### Topic Search with Filters

```python
import requests

def search_topic(topic, start_year=2010, max_results=500):
    """Search for papers on a topic."""
    base_url = "https://api.openalex.org/works"

    params = {
        "search": topic,
        "filter": f"from_publication_date:{start_year}-01-01,type:journal-article,language:en",
        "sort": "cited_by_count:desc",
        "per_page": 100,
        "mailto": "your@email.edu"
    }

    results = []
    cursor = "*"

    while len(results) < max_results:
        params["cursor"] = cursor
        response = requests.get(base_url, params=params)
        data = response.json()

        if not data.get("results"):
            break

        results.extend(data["results"])
        cursor = data["meta"].get("next_cursor")

        if not cursor:
            break

    return results[:max_results]
```

### Get Citations for a Paper

```python
def get_citing_works(openalex_id, max_results=100):
    """Get papers that cite this work."""
    # Extract ID if full URL
    work_id = openalex_id.split("/")[-1]

    base_url = "https://api.openalex.org/works"
    params = {
        "filter": f"cites:{work_id}",
        "sort": "cited_by_count:desc",
        "per_page": min(max_results, 200),
        "mailto": "your@email.edu"
    }

    response = requests.get(base_url, params=params)
    return response.json().get("results", [])
```

### Get References from a Paper

```python
def get_references(openalex_id):
    """Get papers cited by this work."""
    work_id = openalex_id.split("/")[-1]

    # First get the work
    work_url = f"https://api.openalex.org/works/{work_id}"
    response = requests.get(work_url, params={"mailto": "your@email.edu"})
    work = response.json()

    # Then fetch each reference
    ref_ids = work.get("referenced_works", [])
    references = []

    for ref_id in ref_ids[:50]:  # Limit for efficiency
        ref_short_id = ref_id.split("/")[-1]
        ref_response = requests.get(
            f"https://api.openalex.org/works/{ref_short_id}",
            params={"mailto": "your@email.edu"}
        )
        if ref_response.status_code == 200:
            references.append(ref_response.json())

    return references
```

### Find Concept ID

```python
def find_concept(term):
    """Look up concept ID for filtering."""
    url = "https://api.openalex.org/concepts"
    params = {
        "search": term,
        "per_page": 5,
        "mailto": "your@email.edu"
    }

    response = requests.get(url, params=params)
    results = response.json().get("results", [])

    for concept in results:
        print(f"{concept['display_name']}: {concept['id']}")
        print(f"  Level: {concept['level']}, Works: {concept['works_count']}")

    return results
```

## Useful Concept IDs for Sociology

Pre-looked-up concept IDs:

| Concept | ID | Level |
|---------|-----|-------|
| Sociology | C144024400 | 0 |
| Social movement | C2779832528 | 2 |
| Political science | C17744445 | 0 |
| Collective action | C2778097702 | 2 |
| Social network | C121332964 | 2 |
| Protest | C2776822296 | 3 |

Use in filter:
```
filter=concepts.id:C2779832528
```

## Error Handling

```python
def safe_request(url, params, max_retries=3):
    """Make request with retry logic."""
    for attempt in range(max_retries):
        try:
            response = requests.get(url, params=params, timeout=30)
            response.raise_for_status()
            return response.json()
        except requests.exceptions.HTTPError as e:
            if response.status_code == 429:  # Rate limit
                time.sleep(2 ** attempt)
                continue
            raise
        except requests.exceptions.Timeout:
            if attempt < max_retries - 1:
                continue
            raise

    return None
```

## Additional Resources

- **API Documentation**: https://docs.openalex.org
- **Data Schema**: https://docs.openalex.org/api-entities/works
- **Filters Reference**: https://docs.openalex.org/how-to-use-the-api/get-lists-of-entities/filter-entity-lists
