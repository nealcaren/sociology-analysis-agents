# Phase 0: Intake & Reviewer Identification

## Why This Phase Matters

The quality of simulated peer review depends on selecting the right perspectives. You need to identify reviewers who would genuinely engage with this manuscript—scholars or theoretical camps whose work the manuscript cites, builds on, or challenges. This phase analyzes the manuscript to find those perspectives and confirms they're viable given what's available in Zotero.

---

## Your Tasks

### 1. Read the Manuscript

Read the full manuscript (or available sections) carefully. Note:

- **Title and abstract**: What is the core contribution?
- **Theoretical framework**: What theories/frameworks are invoked?
- **Key citations**: Who is cited prominently? Whose work is engaged critically?
- **Methods**: What methodological tradition does this follow?
- **Empirical domain**: What substantive area does this address?

Create a manuscript summary:

```markdown
## Manuscript Summary

**Title**: [Title]
**Core argument**: [1-2 sentences]
**Theoretical framework**: [Named theories/concepts]
**Key scholars engaged**: [Names with brief note on how engaged]
**Methodological approach**: [Tradition/method]
**Empirical domain**: [Substantive area]
**Available sections**: [List what was provided]
```

### 2. Identify Candidate Reviewer Perspectives

Based on your reading, identify 4-6 candidate perspectives that could serve as reviewers. Consider:

**Theory-based perspectives**:
- Scholars whose theoretical frameworks are applied or extended
- Theoretical camps whose concepts are borrowed
- Critics who have challenged similar approaches

**Methods-based perspectives**:
- Methodological traditions the manuscript claims to follow
- Scholars known for methodological rigor in this area

**Substantive perspectives**:
- Scholars who study the same empirical domain
- Those whose findings are compared or contrasted

For each candidate, note:
- Why this perspective is relevant
- Whether they're cited in the manuscript
- How they're engaged (built upon, extended, challenged, ignored)
- What their review focus would be (theory+findings or methods+findings)

### 3. Check Zotero Availability

For each candidate perspective, query Zotero to check source availability.

Use `mcp__zotero-mcp__zotero_search_items` to search for:
- Works by specific authors
- Works tagged with relevant theoretical traditions
- Works in relevant collections

For each candidate, assess:
- **Strong availability**: 3+ relevant full texts
- **Moderate availability**: 1-2 relevant full texts
- **Weak availability**: No full texts (must drop or user must add)

```markdown
## Zotero Availability Check

| Perspective | Search Query | Results | Full Texts | Viability |
|-------------|--------------|---------|------------|-----------|
| [Perspective 1] | author:"Smith" | 5 items | 3 | Strong |
| [Perspective 2] | tag:"Bourdieu" | 8 items | 2 | Moderate |
| [Perspective 3] | author:"Jones" | 1 item | 0 | Weak |
```

### 4. Select 2-3 Recommended Reviewers

Based on relevance and availability, recommend 2-3 reviewer perspectives.

**Selection criteria**:
- High relevance to the manuscript's contribution
- Sufficient Zotero sources to build an informed persona
- Complementary focus areas (don't select 3 theory-focused reviewers)
- Diversity of likely feedback (supportive, challenging, methodological)

For each recommended reviewer:

**IMPORTANT**: Name reviewers for theoretical perspectives, not individual scholars. Even if sources come from one author, name the perspective (e.g., "Emotions in Movements" not "Gould"; "Activist Career Approach" not "Fillieule").

```markdown
## Recommended Reviewer: [Theoretical Perspective Name]

**Perspective**: [Name of theoretical/methodological framework]

**Key sources from**: [Author names whose work informs this—for context, not naming]

**Relevance**: [Why this perspective matters for this manuscript]

**Relationship to manuscript**:
- Cited: [Yes/No - how many times, how]
- Engagement: [Built upon / Extended / Challenged / Compared]

**Zotero sources available**:
- [Source 1]: [Title] (full text: yes/no)
- [Source 2]: [Title] (full text: yes/no)
- [Source 3]: [Title] (full text: yes/no)

**Proposed review focus**: [Theory + Findings] OR [Methods + Findings]

**Expected orientation**: [Likely supportive / Likely critical / Mixed]

**Key questions from this perspective**:
- [Question 1]
- [Question 2]
```

### 5. Note Perspectives Considered but Not Recommended

Document perspectives you considered but didn't recommend, with reasons:

```markdown
## Perspectives Not Selected

| Perspective | Reason Not Selected |
|-------------|---------------------|
| [Perspective A] | Insufficient Zotero sources |
| [Perspective B] | Too similar to selected Reviewer 1 |
| [Perspective C] | Tangential to core contribution |
```

### 6. Prepare Intake Memo

Compile findings into a complete intake memo for user review.

---

## Output Files to Create

Save to project analysis folder:

1. **manuscript-summary.md** - Summary of manuscript content and engagement
2. **reviewer-candidates.md** - All candidate perspectives with Zotero availability
3. **recommended-reviewers.md** - 2-3 recommended perspectives with rationale
4. **intake-memo.md** - Complete intake memo for user review

---

## Guiding Principles

### Relevance Over Availability
Don't select a perspective just because sources are available. The perspective must genuinely matter for this manuscript.

### Diversity of Feedback
Aim for complementary perspectives: one more theoretical, one more methodological/empirical if possible.

### Honest Assessment of Engagement
Note whether the manuscript engages perspectives well or poorly—this shapes review focus.

### Flag Gaps
If important perspectives lack Zotero sources, flag this for the user. They may want to add sources before proceeding.

### 2-3 Is the Sweet Spot
More than 3 reviewers creates synthesis challenges. Fewer than 2 misses the value of multiple perspectives.

---

## When You're Done

Report to the orchestrator:
- Manuscript summary complete
- Number of candidate perspectives identified
- Zotero availability assessment
- 2-3 recommended reviewers with rationale
- Any perspectives that need user input (weak availability but high relevance)
- Ready for user confirmation of reviewer selection

Example summary:
> "**Intake complete**. Manuscript engages Bourdieusian cultural capital theory, applies it to educational settings, uses interview methods. Identified 5 candidate perspectives; 3 have strong Zotero availability. **Recommended reviewers**: (1) Cultural Capital in Education [theory + findings, 4 sources from Lareau], (2) Interview Validity Perspective [methods + findings, 3 sources], (3) Critical Education Scholarship [theory + findings, 3 sources]. One high-relevance perspective (class reproduction) has weak availability—user may want to add sources. Ready for user confirmation."
