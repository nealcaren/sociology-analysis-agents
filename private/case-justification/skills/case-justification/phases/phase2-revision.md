# Phase 2: Revision

You are executing Phase 2 of case-justification. Your goal is to calibrate the draft against cluster benchmarks and polish the prose.

## Why This Phase Matters

Case justification sections follow predictable patterns in length, structure, and component coverage. Reviewers notice sections that deviate significantly from genre norms. This phase ensures your draft matches the conventions of *Social Problems* and *Social Forces*.

---

## Inputs

Before starting, gather:
1. Draft case justification section from Phase 1
2. Assessment memo from Phase 0 (cluster selection, components)
3. Cluster profile from `clusters/[cluster].md`
4. Benchmarks summary from analysis

---

## Your Tasks

### 1. Word Count Calibration

Check draft against cluster targets:

| Cluster | Target | Acceptable | Too Short | Too Long |
|---------|--------|------------|-----------|----------|
| Minimal | 300-500 | 264-550 | < 250 | > 550 |
| Standard | 700-1,000 | 600-1,200 | < 600 | > 1,200 |
| Deep Historical | 1,500-2,500 | 1,200-3,000 | < 1,200 | > 3,000 |
| Comparative | 1,000-1,500 | 800-1,800 | < 800 | > 1,800 |
| Policy-Driven | 650-900 | 600-1,000 | < 600 | > 1,000 |

**If too short**:
- Add geographic context
- Expand historical background
- Include demographic statistics with citations
- Add policy/institutional detail

**If too long**:
- Compress geographic description
- Reduce historical detail (unless Deep Historical)
- Move demographics to Methods table
- Cut redundant policy context

**If significantly off-target**:
Consider whether the cluster assignment is correct. A 500-word section trying to be Standard may actually be Minimal. A 1,400-word Standard may need to be Deep Historical.

### 2. Component Verification

Check that required components are present for the cluster:

#### Minimal Context (must have)
- [ ] Site identification
- [ ] One or two key features
- [ ] Transition to methods

#### Standard Context (must have at least 2 of 3)
- [ ] Geographic context OR
- [ ] Historical background OR
- [ ] Policy/legal context
- [ ] Case significance (why this case)

#### Deep Historical (must have)
- [ ] Chronological narrative
- [ ] Named episodes or periods
- [ ] Multiple subsections (2+)
- [ ] Scholarly positioning citations

#### Comparative (must have)
- [ ] Parallel site descriptions
- [ ] Variation-leverage statement
- [ ] Site selection rationale
- [ ] Table (strongly recommended - 71% have)

#### Policy-Driven (must have)
- [ ] Policy/legal description (detailed)
- [ ] BEFORE THEORY position
- [ ] Stakes establishment

### 3. Citation Density Check

Verify citation density matches cluster norms:

| Cluster | Citations per 100 words | Typical Total |
|---------|------------------------|---------------|
| Minimal | 0.7 | 3 |
| Standard | 1.3 | 10 |
| Deep Historical | 1.5 | 23 |
| Comparative | 1.1 | 12 |
| Policy-Driven | 1.8 | 14 |

**If under-cited**:
- Add citations for demographic statistics (Census, institute reports)
- Add scholarly citations for prior research on site
- Add citations for policy/legislation claims

**If over-cited**:
- Generally not a problem
- Consider whether section is bloated with excessive sourcing

### 4. Opening Move Assessment

Verify the opening matches cluster conventions:

| Cluster | Preferred Openings |
|---------|-------------------|
| Minimal | Research-Setting (40%), Phenomenon-Site-Link (40%) |
| Standard | Phenomenon-Site-Link (45%), Geographic-Introduction (27%) |
| Deep Historical | Phenomenon-Site-Link (60%), Historical-Periodization (40%) |
| Comparative | Phenomenon-Site-Link (43%), Institutional-Description (29%) |
| Policy-Driven | Phenomenon-Site-Link (75%), Historical-Periodization (25%) |

**Prohibited openings across all clusters**:
- "In this section, I will describe..."
- "My research setting is..."
- "The purpose of this section is to..."
- "As mentioned above..."

### 5. Transition Assessment

Verify the transition matches cluster norms:

| Cluster | Preferred Transition |
|---------|---------------------|
| Minimal | Implicit (60%) or Data-Preview (20%) |
| Standard | Implicit (73%) |
| Deep Historical | Implicit (80%) |
| Comparative | Implicit (43%) or Integrated (43%) |
| Policy-Driven | Implicit (75%) or Bridge-Statement (25%) |

**Note**: Implicit transitions (section simply ends) are the norm. Don't add explicit transitions unless the cluster calls for it.

### 6. Position Verification

**CRITICAL**: Confirm correct position:
- **Policy-Driven**: Section appears BEFORE theory section
- **All other clusters**: Section appears AFTER theory section

If the draft is Policy-Driven but positioned after theory, or vice versa, flag this for user review.

### 7. Parallel Structure Check (Comparative Only)

For Comparative sections, verify:
- [ ] Site A and Site B receive comparable coverage
- [ ] Same dimensions are addressed for each site
- [ ] Variation-leverage statement explains what comparison enables
- [ ] Table compares sites across relevant dimensions

### 8. Chronological Logic Check (Deep Historical Only)

For Deep Historical sections, verify:
- [ ] Clear temporal progression
- [ ] Episodes are named and dated
- [ ] Transitions between periods are explicit
- [ ] Summary paragraph connects arc to analysis

### 9. Prose Polish

Check for common issues:

**Remove metadiscourse**:
- "It is important to note that..." --> Just state the fact
- "As described above..." --> Remove entirely
- "In this section, I..." --> Remove entirely

**Strengthen verbs**:
- "There was an increase in..." --> "X increased..."
- "It can be seen that..." --> Remove and state directly

**Check parallel construction**:
- Lists should have parallel structure
- Site descriptions in Comparative should mirror each other

**Verify citations are formatted**:
- Check journal citation style
- Verify all facts have sources

### 10. Final Checklist

#### All Clusters
- [ ] Word count within acceptable range
- [ ] Required components present
- [ ] Citation density appropriate
- [ ] Opening matches cluster conventions
- [ ] No prohibited metadiscourse
- [ ] Transition present (usually implicit)

#### Cluster-Specific

**Minimal**:
- [ ] No tables
- [ ] No extended historical narrative
- [ ] Under 500 words

**Standard**:
- [ ] Single subsection
- [ ] No comparison tables
- [ ] Positioned after theory

**Deep Historical**:
- [ ] 2+ subsections
- [ ] Chronological organization
- [ ] Named episodes/periods
- [ ] Summary paragraph

**Comparative**:
- [ ] Parallel site structure
- [ ] Variation-leverage statement
- [ ] Table present (recommended)

**Policy-Driven**:
- [ ] BEFORE theory position
- [ ] Dense policy content
- [ ] Specific legislation named

---

## Output

Create a revision memo with:

```markdown
# Case Justification Revision Report

## Word Count
- **Draft**: [X] words
- **Target**: [Y-Z] words
- **Status**: [Within range / Adjusted]

## Component Coverage
- [Component]: [Present/Added/Omitted] - [rationale if omitted]
- ...

## Citation Density
- **Density**: [X] per 100 words
- **Total**: [N] citations
- **Target**: [Y] citations
- **Status**: [Appropriate / Adjusted]

## Structural Elements
- **Opening**: [Type] - [Appropriate / Changed to X]
- **Transition**: [Type] - [Appropriate / Changed to X]
- **Position**: [BEFORE/AFTER theory] - [Correct / ERROR]
- **Subsections**: [N] - [Appropriate / Adjusted]
- **Table**: [Present/Absent] - [Appropriate / Added / N/A]

## Prose Revisions
- [List specific prose improvements made]

## Remaining Issues
- [Any issues user should address]

## Quality Assessment
- **Cluster match**: [Good / Marginal / Reconsider cluster]
- **Calibration**: [Matches norms / Minor deviations / Significant deviations]
- **Ready for submission**: [Yes / Needs further work]
```

---

## When You're Done

Report to the orchestrator:
- Final word count vs. target
- Any structural changes made
- Quality assessment
- Any remaining issues for user

Example summary:
> "**Revision complete**. Final: 847 words (target: 700-1,000). Standard Context calibrated correctly. Added two demographic citations (Census data) to improve citation density from 0.9 to 1.2 per 100 words. Opening (Phenomenon-Site-Link) and transition (Implicit) match cluster norms. All required components present. Ready for user review."
