# Phase 6: Synthesis

You are generating the final literature database and identifying patterns across the corpus. Your goal is to produce usable outputs and insights.

## Why This Phase Matters

The value of a literature review is in the synthesis. This phase transforms individual paper annotations into a coherent understanding of the field, identifying themes, debates, and gaps.

## Prerequisites

- Load `data/database.json`
- Review the Phase 5 section in `memos/search-memo.md` for annotation notes

## Your Tasks

### 1. Generate Annotated Bibliography

Create a human-readable bibliography in `output/bibliography.md`:

```markdown
# Annotated Bibliography: Social Movement Participation

**Generated**: 2024-01-15
**Total papers**: 179
**Date range**: 2010-2024

---

## Core Theoretical Works

### McAdam, D. & Paulsen, R. (2018). Biographical availability revisited.
*American Sociological Review*, 83(4), 701-728.

**Research Question**: What factors predict sustained vs. initial movement participation?

**Key Findings**:
- Social ties strongest predictor of initial participation
- Biographical availability effects fade over time
- Ideological commitment predicts sustained engagement

**Methods**: Longitudinal panel, N=245, Freedom Summer participants

**Relevance**: Foundational operationalization of participation; challenges single-timepoint designs.

**Tags**: #participation #longitudinal #socialnetworks

---

### [Continue for each paper, organized thematically]

## Empirical Studies

### [Papers grouped by method or topic]

## Methodological Contributions

### [Methods papers]
```

### 2. Export BibTeX

Create citation manager compatible export:

```python
def generate_bibtex(papers, output_path="output/references.bib"):
    """Generate BibTeX file for citation managers."""
    bibtex_entries = []

    for paper in papers:
        # Use citation_key from database (generated in Phase 1)
        cite_key = paper.get("citation_key", f"{paper['authors'][0].split()[-1] if paper['authors'] else 'Unknown'}{paper['year']}")

        entry = f"""@article{{{cite_key},
  author = {{{" and ".join(paper["authors"])}}},
  title = {{{paper["title"]}}},
  journal = {{{paper.get("journal", "")}}},
  year = {{{paper["year"]}}},
  doi = {{{paper.get("doi", "").replace("https://doi.org/", "")}}},
  pdf_path = {{}},
  md_path = {{}}
}}
"""
        bibtex_entries.append(entry)

    with open(output_path, "w") as f:
        f.write("\n".join(bibtex_entries))
```

### Ingest PDFs into the Local BibTeX Pipeline

After generating `output/references.bib`, run `ingest.py` to register PDFs and convert them to markdown. This populates the `pdf_path` and `md_path` fields in each entry so downstream skills can locate full text by citation key:

```bash
python ingest.py --bib output/references.bib --pdf-dir fulltext/
```

`ingest.py` will:
1. Match each PDF filename (or DOI-derived name) to its BibTeX entry by citation key
2. Convert the PDF to a markdown file alongside it
3. Write the resolved `pdf_path` and `md_path` back into `output/references.bib`

Once ingested, `[@citationKey]` references in downstream writing skills resolve to the correct local files via `references.bib`.

### 3. Thematic Analysis

Identify major themes across the corpus:

```markdown
## Thematic Summary

### Theme 1: The Role of Social Networks
**Papers**: 34/179 (19%)
**Key insight**: Network position consistently predicts participation; debate over mechanism (information, identity, pressure)

**Representative works**:
- McAdam & Paulsen (2018): Tie strength effects
- Lim (2008): Network diversity matters
- [...]

**Unresolved questions**:
- Do online networks function like offline?
- Threshold effects in network activation

---

### Theme 2: Biographical Availability vs. Biographical Consequences
**Papers**: 28/179 (16%)
**Key insight**: Traditional availability model (free time, no constraints) being challenged by studies showing activism shapes biography

**Debates**:
- Selection vs. causation
- Short vs. long-term effects

---

### Theme 3: [Continue for other major themes]
```

### 4. Identify Research Gaps

Analyze what's missing:

```markdown
## Research Gaps and Opportunities

### Methodological Gaps

1. **Longitudinal designs rare**: Only 12% of studies track participants over time
   - Most participation research is cross-sectional
   - Cannot distinguish selection from socialization

2. **Non-Western contexts underrepresented**: 67% of studies focus on US/Europe
   - Limited work on participation in Global South movements
   - Theories developed in democratic contexts may not travel

3. **Online participation understudied**: Despite growth of digital activism
   - Only 8% explicitly examine online participation
   - No consensus on measurement

### Theoretical Gaps

1. **Emotion largely absent**: Despite emotion turn in sociology
   - Most studies use rational-choice adjacent frameworks
   - Emotional dynamics of participation unexplored

2. **Intersectionality undertheorized**:
   - Race, class, gender treated as controls not mechanisms
   - Limited work on how identities shape participation pathways

### Empirical Gaps

1. **Demobilization understudied**: Focus on why people join, not why they leave
2. **Movement-to-movement dynamics**: How participation in one affects another
```

### 5. Map Debates and Positions

Identify ongoing disagreements:

```markdown
## Scholarly Debates

### Debate 1: Grievances vs. Resources

**Position A** (Resource Mobilization):
Resources and organization matter more than grievances for participation.
- Proponents: McCarthy & Zald tradition
- Evidence: [Papers]

**Position B** (Grievance-Based):
Felt injustice is necessary condition for participation.
- Proponents: [Scholars]
- Evidence: [Papers]

**Current state**: Synthesized models dominate; pure positions rare since 2010.

---

### Debate 2: Individual vs. Structural Explanations
[...]
```

### 6. Generate Field Summary

Create an executive summary:

```markdown
## Field Summary: [Your Topic] (2010-2024)

### State of the Field
The study of [your topic] has matured considerably since 2010. The field has moved beyond early debates toward integrated models that acknowledge multiple mechanisms and pathways.

### Dominant Approaches
1. **Micro-level explanations**: Individual resources, identities, and motivations
2. **Meso-level explanations**: Organizational or network dynamics
3. **Macro-level explanations**: Institutional and contextual conditions

### Emerging Directions
1. Digital or hybrid forms of the phenomenon
2. Cultural and emotional mechanisms
3. Cross-national and comparative work

### Key Methodological Developments
- Longitudinal panel designs
- Mixed methods combining surveys and interviews
- Computational or digital trace approaches

### Major Unresolved Questions
1. How do online and offline dimensions relate?
2. What sustains engagement or outcomes over time?
3. How do macro contexts shape micro-level behavior or outcomes?
```

## Output Files

Create the following in `output/`:

| File | Purpose |
|------|---------|
| `bibliography.md` | Annotated bibliography for reading |
| `references.bib` | BibTeX for citation managers |
| `synthesis.md` | Thematic summary and gaps |

The primary database (`data/database.json`) already exists from earlier phases and does not need to be re-exported.

## Final Package

Present the complete package to the user:

```markdown
## Literature Review Package Complete

Your literature database on "Social Movement Participation" is ready.

### Corpus Summary
- **Total papers**: 179
- **Date range**: 2010-2024
- **Top journals**: Mobilization, Social Movement Studies, ASR
- **Full text obtained**: 124/179 (69%)

### Deliverables
1. **Annotated bibliography** (`output/bibliography.md`)
   - All papers with structured annotations
   - Organized thematically

2. **Citation file** (`output/references.bib`)
   - Ready for Mendeley, LaTeX, or local library pipeline

3. **Synthesis document** (`output/synthesis.md`)
   - Thematic summary
   - Research gaps identified
   - Scholarly debates mapped

4. **Full database** (`data/database.json`)
   - Complete annotated database from all phases
   - Query by theory, method, findings, tags

### Next Steps
- Review the synthesis for accuracy
- Consider whether gaps suggest your contribution
- Use database to locate specific papers as you write
```

## Guiding Principles

- **Multiple formats**: Different outputs for different uses
- **Synthesis over summary**: Identify patterns, not just list papers
- **Honest about gaps**: What you didn't find is as important as what you found
- **Usable outputs**: Bibliography should be directly usable in writing

## When You're Done

Tell the orchestrator:
> "Phase 6 complete. Literature review package generated: annotated bibliography (output/bibliography.md), BibTeX (output/references.bib), and synthesis document (output/synthesis.md). Full annotated database at data/database.json. Review complete."

The user now has a complete, systematic literature database ready for use in their research.
