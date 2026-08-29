# Phase 0: Corpus Audit

## Why This Phase Matters

Before deep reading, you need to know what you have. A corpus audit reveals the shape of your literature: temporal coverage, theoretical breadth, methodological diversity, and gaps. This shapes your reading priorities and prevents wasted effort on peripheral papers.

---

## Your Tasks

### 1. Assess Corpus Source

Determine where the papers come from:

**From lit-search**:
- Load the `database.json` from lit-search output
- Papers should already be screened and annotated
- Check the `synthesis.md` for initial thematic groupings

**From existing Zotero library**:
- Identify the relevant collection(s)
- May need initial screening if not pre-filtered

**From user's ad-hoc collection**:
- Gather all papers into one location
- May need more extensive organization

### 2. Generate Corpus Statistics

Using Zotero MCP, compile:

```markdown
## Corpus Overview

- **Total papers**: [N]
- **Date range**: [earliest] - [latest]
- **Peak years**: [years with most papers]

## By Journal
| Journal | Count |
|---------|-------|
| [Journal 1] | [N] |
| [Journal 2] | [N] |
...

## By Author (top 10)
| Author | Papers |
|--------|--------|
| [Author 1] | [N] |
...

## By Decade
| Period | Count |
|--------|-------|
| 2020s | [N] |
| 2010s | [N] |
| 2000s | [N] |
| Pre-2000 | [N] |
```

### 3. Preliminary Theoretical Scan

Skim abstracts and keywords to identify:
- Which theoretical traditions appear? (e.g., Bourdieusian, institutionalist, interactionist)
- Any named frameworks? (e.g., "legal consciousness," "gendered organizations")
- Dominant methodological approaches?

### 4. Identify Coverage Gaps

Based on statistics and skim:
- **Temporal gaps**: Missing recent work? Missing foundational papers?
- **Theoretical gaps**: One tradition over-represented?
- **Empirical gaps**: Missing key populations or settings?
- **Geographic gaps**: All US-based? Missing comparative work?

### 5. Set Reading Priorities

Categorize papers into:

| Priority | Criteria | Target |
|----------|----------|--------|
| **Must Read** | Central to your topic; highly cited; foundational | Deep read (Phase 1) |
| **Should Read** | Relevant but not central; supports arguments | Careful skim |
| **May Skim** | Peripheral; useful for breadth | Quick skim or skip |

Use these criteria for "Must Read":
- Highly cited within the corpus
- Directly addresses your research question
- Foundational text others cite
- Introduces key concepts you'll use
- Recent and relevant (last 3-5 years)

### 6. Write Corpus Audit Memo

Create `corpus-audit.md`:

```markdown
# Corpus Audit

## Corpus Summary
- Source: [lit-search / Zotero collection / ad-hoc]
- Total papers: [N]
- Date range: [years]

## Statistics
[Tables from Task 2]

## Preliminary Theoretical Landscape
- Dominant traditions: [list]
- Named frameworks: [list]
- Methodological approaches: [list]

## Coverage Assessment

### Strengths
- [What's well covered]

### Gaps Identified
- [Gap 1]: [description and significance]
- [Gap 2]: [description and significance]

### Recommendations
- [Any papers to add before proceeding]
- [Any papers to exclude]

## Reading Priorities

### Must Read (Deep Reading - Phase 1)
1. [Author Year] - [Reason]
2. [Author Year] - [Reason]
3. [Author Year] - [Reason]
... [aim for 10-20 papers]

### Should Read (Careful Skim)
- [List]

### May Skim
- [List or "remainder"]

## Questions for User
- [Any clarifying questions]
```

---

## Guiding Principles

### 15-20 Deep Reads Is Plenty
You can't deeply read 80 papers. Prioritize ruthlessly. The "Must Read" list should be 10-20 papers maximum.

### Foundational > Recent
Don't skip classics just because they're old. Foundational texts shape how everyone else thinks about the topic.

### Gaps Are Data
Finding that your corpus lacks X is valuable information—it may reveal your contribution space.

### User Knows Their Field
You can suggest priorities, but the user knows which papers matter most for their specific project.

---

## Output Files to Create

1. **corpus-audit.md** - Full audit with statistics and priorities

---

## When You're Done

Report to the orchestrator:
- Corpus size and date range
- Number of papers prioritized for deep reading
- Key gaps identified
- Any recommendations before proceeding

Example summary:
> "Corpus audit complete. **47 papers** spanning 2008-2024, concentrated in *Social Problems* and *American Sociological Review*. Theoretical landscape dominated by legal consciousness and neighborhood effects traditions. **15 papers** prioritized for deep reading; notable gap in comparative/non-US work. Recommend adding 2-3 foundational neighborhood effects papers before Phase 1. Ready for user review."
