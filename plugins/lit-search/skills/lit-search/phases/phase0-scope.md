# Phase 0: Scope Definition

You are defining the scope of a systematic literature search. Your goal is to help the user develop a clear, reproducible search strategy.

## Why This Phase Matters

A literature review is only as good as its scope. Overly narrow searches miss important work; overly broad searches create unmanageable screening burdens. This phase establishes the boundaries before any API calls.

## Your Tasks

### 1. Clarify the Research Topic

Ask the user to describe their topic in plain language. Then probe for:

- **Core concept**: What is the central phenomenon? (e.g., "educational inequality")
- **Boundaries**: What is NOT included? (e.g., "not K-12 outcomes, not higher education")
- **Level of analysis**: Individual, organizational, field-level?
- **Theoretical tradition**: Does the user work within a specific tradition (resource mobilization, political process, etc.)?

### 2. Develop Search Terms

Work with the user to build a comprehensive term list:

```
Primary terms:
- [primary term 1]
- [primary term 2]
- [primary term 3]

Synonyms and variants:
- [synonym 1]
- [synonym 2]
- [nearby term that may be too broad]

Field-specific vocabulary:
- [concept 1]
- [concept 2]
- [concept 3]
```

Consider:
- Spelling variants (behavior/behaviour)
- Acronyms used in the field
- Terms that have evolved over time
- Boolean combinations (participation AND (protest OR movement))

### 3. Define Filters

Establish explicit criteria:

| Filter | User's Choice | Notes |
|--------|---------------|-------|
| **Date range** | e.g., 2010-2024 | Consider field development |
| **Language** | English only? | May miss important non-English work |
| **Document types** | Journal articles, books, working papers? | |
| **Empirical only?** | Exclude pure theory? | |
| **Peer-reviewed only?** | Exclude dissertations, reports? | |

### 4. Identify Key Sources

Ask about:
- **Key journals**: American Sociological Review, American Journal of Sociology, Social Forces, etc.
- **Key authors**: Who are the major scholars in this area?
- **Foundational works**: Are there must-include classic papers?
- **Known gaps**: Are there subtopics the user already knows are understudied?

### 5. Set Practical Constraints

Discuss:
- **Target corpus size**: How many papers can the user realistically annotate?
- **Time available**: Is this a comprehensive review or targeted search?
- **Use case**: Dissertation lit review? Journal article? Grant proposal?

### 6. Draft OpenAlex Queries

Based on the above, construct initial API queries:

```python
# Example query structure for OpenAlex
base_url = "https://api.openalex.org/works"
params = {
    "search": "[primary term 1] [primary term 2]",
    "filter": "from_publication_date:2010-01-01,to_publication_date:2024-12-31,type:journal-article,language:en",
    "sort": "cited_by_count:desc",
    "per_page": 100
}
```

Create multiple query variants to maximize coverage:
1. Primary term search
2. Abstract search with Boolean terms
3. Concept-based search using OpenAlex concepts

## Output: Scope Document

Create `memos/scope.md` with:

```markdown
# Literature Review Scope

## Research Topic
[User's description]

## Inclusion Criteria
- Date range:
- Document types:
- Language:
- Empirical/theoretical:
- Other:

## Exclusion Criteria
- [List explicit exclusions]

## Search Terms

### Primary
- term1
- term2

### Secondary/Synonyms
- term3
- term4

### Boolean Queries
- (term1 OR term2) AND term3

## Key Sources
- Journals: [list]
- Authors: [list]
- Must-include works: [list]

## OpenAlex Query Strategy
[Document planned queries]

## Target Corpus Size
[Estimated range]
```

## Guiding Principles

- **User knows the field**: They can identify synonyms and boundaries you can't
- **Start broad, narrow later**: Better to screen out than miss
- **Document decisions**: Every scope choice should be recorded for the methods section
- **Iterate**: Initial terms will evolve as you see results

## When You're Done

Tell the orchestrator:
> "Phase 0 complete. Scope document created at memos/scope.md. Ready for user confirmation before API queries."

**Do not proceed to Phase 1 until the user approves the search strategy.**
