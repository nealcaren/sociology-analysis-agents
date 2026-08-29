# Phase 3: Pattern Interpretation & Cluster Discovery

You are executing Phase 3 of the genre-skill-builder workflow. Your goal is to move from coding data to stable cluster definitions—interpreting patterns, refining boundaries, and creating the profiles that will guide the generated skill.

## Why This Phase Matters

Clusters are the heart of genre-based writing guidance. This phase transforms preliminary groupings into robust categories with distinctive benchmarks, signature moves, and clear guidance. The quality of cluster discovery determines the usefulness of the final skill.

## Inputs

Before starting, read:
1. `/analysis/phase0-scope/scope-definition.md` - Scope and model skill
2. `/analysis/phase1-immersion/corpus-statistics.json` - Quantitative data
3. `/analysis/phase2-coding/article-codes.json` - All article codes
4. `/analysis/phase2-coding/preliminary-clusters.md` - Initial cluster assignments
5. `/analysis/phase2-coding/co-occurrence-analysis.md` - Code patterns
6. `/analysis/phase2-coding/coding-memo.md` - Coding insights

## Your Tasks

### 1. Validate Preliminary Clusters

Test each preliminary cluster for coherence:

**Cluster coherence criteria**:
- [ ] At least 3 articles (or 10% of corpus)
- [ ] Shared signature codes (not just one feature)
- [ ] Distinctive from other clusters (not a subset)
- [ ] Internally consistent (members are more similar to each other than to other clusters)

```markdown
## Cluster Validation: [Cluster Name]

### Member Articles
[List all articles assigned to this cluster]

### Signature Codes
- **Primary defining features**: [codes that appear in 80%+ of cluster]
- **Secondary features**: [codes that appear in 50-80%]
- **Distinguishing from other clusters**: [what this cluster has that others don't]

### Internal Consistency
- Articles that clearly fit: [list]
- Articles that are borderline: [list]
- Articles to reassign: [list, with rationale]

### Verdict
[Keep / Merge with X / Split into X and Y / Dissolve]
```

### 2. Refine Cluster Boundaries

Based on validation, adjust clusters:

**Operations to consider**:
- **Merge**: If two clusters share most signature codes, combine them
- **Split**: If a cluster has two distinct sub-patterns, separate them
- **Dissolve**: If a cluster has too few members or no clear signature, redistribute
- **Rename**: If the working name doesn't capture the essence, revise

```markdown
## Cluster Refinement Decisions

### Merges
- Merged [Cluster A] and [Cluster B] → [New Name]
- Rationale: [why they belong together]

### Splits
- Split [Cluster C] into [C1] and [C2]
- Rationale: [distinctive patterns that justify separation]

### Dissolutions
- Dissolved [Cluster D], reassigned articles to [X, Y, Z]
- Rationale: [why it wasn't a coherent cluster]

### Final Cluster Count: [n]
```

### 3. Calculate Cluster Benchmarks

For each final cluster, compute distinctive statistics:

```markdown
## Cluster Benchmarks: [Cluster Name]

### Size
- **Articles**: [n] ([%] of corpus)

### Word Count
- **Median**: [n]
- **IQR**: [Q1]-[Q3]
- **Comparison to corpus median**: [higher/lower/similar]

### Paragraph Count
- **Median**: [n]
- **IQR**: [Q1]-[Q3]

### Structural Features
- **% with subsections**: [n]%
- **% with roadmap**: [n]%
- **% with [other feature]**: [n]%

### Opening Move Distribution
| Move | Count | % |
|------|-------|---|
| Phenomenon | X | X% |
| Stakes | X | X% |
| Theory | X | X% |
| Other | X | X% |

### Citation Density
- **Median per paragraph**: [n]
- **Dominant style**: [parenthetical/author-subject/mixed]

### Distinctive vs. Corpus
[What makes this cluster's benchmarks different from overall corpus?]
```

### 4. Define Signature and Prohibited Moves

For each cluster, specify what's characteristic and what's avoided:

```markdown
## Cluster Profile: [Cluster Name]

### Signature Moves (do this)
1. **[Move 1]**: [description, with example from corpus]
   > "Example quote from article X"
2. **[Move 2]**: [description, with example]
3. **[Move 3]**: [description, with example]

### Typical Pattern
[Describe the characteristic paragraph sequence or structure]

### Prohibited Moves (don't do this)
1. **[Move 1]**: [what to avoid and why]
2. **[Move 2]**: [what to avoid and why]

### Edge Cases
[When might someone in this cluster deviate from signature moves?]
```

### 5. Select Cluster Exemplars

Identify 1-2 articles per cluster that best represent the pattern:

```markdown
## Exemplar: [Article Filename]

**Cluster**: [Cluster Name]
**Why exemplary**: [What makes this article a good model]

### Key Features Demonstrated
- [Feature 1]: How this article does it
- [Feature 2]: How this article does it
- [Feature 3]: How this article does it

### Notable Quotes
> "[Quote that exemplifies a signature move]"

> "[Another illustrative quote]"

### Would use this to teach
- [Specific technique this article demonstrates well]
```

### 6. Name Clusters Meaningfully

Finalize cluster names that communicate their essence:

**Naming principles**:
- Name by **strategy**, not prevalence ("Gap-Filler" not "Common Type")
- Name by **contribution type** when possible ("Theory-Extension" not "Framework-Heavy")
- Use **compound names** if needed ("Problem-Driven Pragmatist")
- Avoid **jargon** that won't be clear to users

```markdown
## Final Cluster Names

| Working Name | Final Name | Rationale |
|--------------|------------|-----------|
| Cluster A | Gap-Filler Minimalist | Fills empirical gaps with efficient structure |
| Cluster B | Theory-Extension | Applies named framework to new domain |
| ... | ... | ... |
```

### 7. Create Cluster Decision Tree

Help users identify which cluster their article inhabits:

```markdown
## Cluster Decision Tree

To identify your cluster, answer these questions:

1. **What is your primary contribution?**
   - Empirical documentation of understudied phenomenon → likely Gap-Filler
   - Application of established theory → likely Theory-Extension
   - Introduction of new concept/term → likely Concept-Builder
   - Integration of separate literatures → likely Synthesis
   - Resolution of debate or policy focus → likely Problem-Driven

2. **[Follow-up question based on answer 1]**
   - ...

3. **[Confirmation question]**
   - ...

### Quick Indicators

| If you see this... | Consider this cluster... |
|--------------------|--------------------------|
| Named theorist in first paragraph | Theory-Extension |
| Data mentioned in first 3 paragraphs | Gap-Filler |
| New terminology defined | Concept-Builder |
| Multiple theoretical traditions | Synthesis |
| Policy implications emphasized | Problem-Driven |
```

### 8. Document Interpretation Process

Write an interpretation memo:

```markdown
## Interpretation Memo

### How Clusters Emerged
[Narrative of the discovery process—what patterns became clear, what required judgment]

### Key Distinctions
[The 2-3 most important features that differentiate clusters]

### Uncertainty and Ambiguity
[Where are cluster boundaries fuzzy? Which articles could go either way?]

### Comparison to Model Skill
[How do your clusters compare to the model skill's clusters?]
- Similar clusters: [list]
- Different clusters: [list]
- Novel findings: [what your corpus revealed that the model didn't have]

### Confidence Assessment
[How stable are these clusters? Would another coder find the same groupings?]
```

## Output Files to Create

Save all outputs to `/analysis/phase3-clusters/`:

1. **phase3-interpretation.md** - Main interpretation report:
   - Cluster validation results
   - Refinement decisions
   - Final cluster definitions
   - Interpretation memo

2. **cluster-profiles.md** - Consolidated cluster profiles:
   - One section per cluster
   - Benchmarks, signature moves, exemplars
   - Decision tree for identification

3. **cluster-benchmarks.json** - Structured benchmark data:
   ```json
   {
     "clusters": [
       {
         "name": "Gap-Filler Minimalist",
         "prevalence": 0.388,
         "benchmarks": {
           "word_count": {"median": 695, "iqr": [612, 756]},
           "paragraph_count": {"median": 5, "iqr": [4, 6]},
           "opening_move": {"phenomenon": 0.77, "stakes": 0.13, "theory": 0.06}
         },
         "signature_moves": ["phenomenon_opening", "early_data_mention", "modest_claims"],
         "prohibited_moves": ["theory_led_opening", "extensive_roadmap"]
       }
     ]
   }
   ```

4. **exemplars/** folder with detailed exemplar analyses:
   - `exemplar-gap-filler.md`
   - `exemplar-theory-extension.md`
   - etc.

5. **decision-tree.md** - Standalone cluster identification guide

## Guiding Principles

1. **Clusters are analytical tools**: They simplify variation to enable guidance. Perfect boundaries don't exist.

2. **3-6 clusters is the sweet spot**: Fewer misses variation; more creates confusion.

3. **Names matter**: Users will think with cluster names. Make them intuitive.

4. **Exemplars do heavy lifting**: Well-chosen exemplars communicate more than definitions.

5. **Benchmarks are descriptive**: They describe what successful articles do, not what all articles must do.

6. **Uncertainty is honest**: Acknowledge fuzzy boundaries rather than forcing false precision.

## When You're Done

Return a summary to the orchestrator that includes:
1. Final cluster count and names
2. Cluster sizes (n and % for each)
3. Key distinguishing features between clusters
4. Exemplars selected (1-2 per cluster)
5. Decision tree summary (how users identify their cluster)
6. Confidence assessment (how stable are the clusters?)
7. Comparison to model skill clusters
8. Questions for the user about cluster definitions
9. Recommendation to proceed to Phase 4 (skill generation)
