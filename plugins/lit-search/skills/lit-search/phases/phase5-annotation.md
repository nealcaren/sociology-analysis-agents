# Phase 5: Annotation

You are extracting structured information from each paper. Your goal is to create a queryable database of findings, methods, and contributions.

## Why This Phase Matters

A literature database is only as useful as its annotations. This phase transforms raw papers into structured knowledge that can be searched, filtered, and synthesized.

## Prerequisites

- Load `data/screened/included_with_snowball.json`
- Check `data/fulltext_status.json` for available full texts
- Full text PDFs should be in `fulltext/` directory

## Your Tasks

### 1. Define Annotation Schema

Create a consistent extraction template:

```python
annotation_schema = {
    # Bibliographic
    "openalex_id": "",
    "title": "",
    "authors": [],
    "year": 0,
    "journal": "",
    "doi": "",

    # Annotation source
    "annotation_source": "",  # "full_text" or "abstract_only"

    # Core content
    "research_question": "",
    "theoretical_framework": "",
    "hypotheses": [],

    # Methods
    "methods": {
        "design": "",           # cross-sectional, longitudinal, experimental, qualitative
        "data_source": "",      # survey name, interview sample, archival
        "sample": "",           # who, N, sampling method
        "geographic_scope": "", # country/region
        "time_period": "",      # when data collected
        "key_variables": {
            "dependent": [],
            "independent": [],
            "controls": []
        },
        "analysis_technique": ""  # regression, SEM, thematic analysis, etc.
    },

    # Findings
    "key_findings": [],         # List of main results
    "effect_sizes": [],         # If reported
    "mechanisms": "",           # Proposed causal mechanisms
    "boundary_conditions": "",  # When effects hold/don't hold

    # Contribution
    "theoretical_contribution": "",
    "empirical_contribution": "",
    "limitations_noted": [],
    "future_directions": [],

    # User annotations
    "relevance_to_project": "",    # How this relates to user's research
    "quality_assessment": "",      # User's assessment of rigor
    "key_quotes": [],              # Notable passages
    "tags": [],                    # User-defined tags
    "notes": ""                    # Free-form notes
}
```

### 2. Prioritize Annotation Order

Start with highest-value papers:

```python
def prioritize_papers(papers):
    """Order papers for annotation priority."""
    scored = []
    for paper in papers:
        score = 0
        score += paper.get("cited_by_count", 0) / 100  # Citation weight
        score += 10 if paper.get("fulltext_obtained") else 0  # Full text bonus
        score += 5 if paper["publication_year"] >= 2020 else 0  # Recency
        scored.append((score, paper))

    return [p for _, p in sorted(scored, reverse=True)]
```

### 3. Extract from Full Text

For papers with full text:

```python
def annotate_from_fulltext(paper, pdf_path):
    """Extract structured information from PDF."""
    # Read PDF content (using appropriate library)
    text = extract_text_from_pdf(pdf_path)

    # Section-based extraction
    sections = identify_sections(text)

    annotation = {
        "annotation_source": "full_text",
        "research_question": extract_research_question(sections.get("introduction")),
        "theoretical_framework": extract_theory(sections.get("theory") or sections.get("introduction")),
        "methods": extract_methods(sections.get("methods") or sections.get("data")),
        "key_findings": extract_findings(sections.get("results") or sections.get("findings")),
        "limitations_noted": extract_limitations(sections.get("discussion") or sections.get("conclusion")),
        # ... continue for other fields
    }

    return annotation
```

### 4. Extract from Abstract

For papers without full text:

```python
def annotate_from_abstract(paper):
    """Extract what we can from abstract only."""
    abstract = paper.get("abstract", "")

    annotation = {
        "annotation_source": "abstract_only",
        "research_question": infer_research_question(abstract),
        "methods": {
            "design": infer_design(abstract),
            "sample": infer_sample(abstract),
            # Many fields will be empty or uncertain
        },
        "key_findings": extract_findings_from_abstract(abstract),
        "limitations_noted": ["Full text not available for detailed assessment"]
    }

    return annotation
```

### 5. Present Annotations for User Review

Show each annotation for validation:

```markdown
## Annotation Review: Paper 1 of 179

**Title**: Neighborhood Disadvantage and Educational Attainment
**Authors**: [Author A] & [Author B]
**Year**: 2019
**Annotation source**: Full text

### Research Question
> "How does neighborhood disadvantage shape educational attainment over the life course?"

### Theoretical Framework
> Life course perspective; extends cumulative disadvantage framework

### Methods
| Aspect | Extracted |
|--------|-----------|
| Design | Longitudinal panel (3 waves) |
| Data | Longitudinal household survey |
| Sample | N=1,200 adolescents, tracked 2000-2015 |
| Geography | United States (multi-site) |
| DV | Educational attainment |
| IVs | Neighborhood disadvantage, school quality, family resources |

### Key Findings
1. Neighborhood disadvantage predicts lower attainment (β=-.28)
2. School quality mediates part of the association
3. Family resources buffer disadvantage effects

### Relevance to Your Project
This paper provides key operationalizations of neighborhood disadvantage and tests mechanisms you're engaging with.

---

**Please review and correct any errors, then add your notes:**

- [ ] Annotations accurate
- Your relevance notes:
- Your quality assessment (high/medium/low):
- Tags:
- Additional notes:
```

### 6. Batch Annotation for Efficiency

For larger corpora, batch similar papers:

```python
def batch_annotate(papers, batch_size=10):
    """Process papers in batches with user review points."""
    batches = [papers[i:i+batch_size] for i in range(0, len(papers), batch_size)]

    for i, batch in enumerate(batches):
        # Annotate batch
        annotations = [annotate_paper(p) for p in batch]

        # Present batch summary for user review
        present_batch_summary(i+1, len(batches), annotations)

        # Get user feedback
        # Pause for user review

        # Continue to next batch
```

### 7. Save Annotated Database

```python
def save_annotations(annotations, output_path="data/annotated/database.json"):
    """Save complete annotated database."""
    database = {
        "metadata": {
            "created": "2024-01-15",
            "total_papers": len(annotations),
            "fulltext_annotated": sum(1 for a in annotations if a["annotation_source"] == "full_text"),
            "abstract_only": sum(1 for a in annotations if a["annotation_source"] == "abstract_only")
        },
        "papers": annotations
    }

    with open(output_path, "w") as f:
        json.dump(database, f, indent=2)
```

## Annotation Quality Guidelines

### Research Question
- State as a question or clear statement of inquiry
- Should be specific and falsifiable
- If multiple RQs, list all

### Theoretical Framework
- Name the theory/theories used
- Note how the paper extends or challenges existing theory
- Include key theoretical concepts

### Methods Assessment
- Capture enough detail to evaluate and replicate
- Note any methodological innovations
- Flag potential limitations (sample size, selection, etc.)

### Findings Extraction
- Focus on main findings, not all results
- Include effect sizes and significance when reported
- Note null findings and boundary conditions

## Output Files

- `data/annotated/database.json` - Complete structured database
- `memos/annotation_notes.md` - User's notes and observations during annotation

## Guiding Principles

- **Full text > abstract**: Note annotation source for each paper
- **User validates**: LLM extraction needs human verification
- **Consistent schema**: Same fields for every paper enables querying
- **Flag uncertainty**: Mark fields where extraction was uncertain

## When You're Done

Tell the orchestrator:
> "Phase 5 complete. Annotated X papers (Y from full text, Z from abstract). Database saved to data/annotated/database.json. Ready for synthesis."

**Do not proceed to Phase 6 until the user has reviewed annotations for at least the core papers.**
