# Phase 0: Scope Definition & Model Selection

You are executing Phase 0 of the genre-skill-builder workflow. Your goal is to establish what skill you're building and what existing skill to learn from.

## Why This Phase Matters

Scope definition prevents wasted effort. A clear target section, appropriate model skill, and confirmed corpus determine everything that follows. Ambiguity here cascades into confusion later.

## Inputs

Before starting, gather from the user:
1. **Target section**: What article section will the skill help write?
2. **Corpus location**: Where are the articles to analyze?
3. **Model skill preference**: Which existing skill to use as template?
4. **Output skill name**: What should the new skill be called?

## Your Tasks

### 1. Confirm Target Section

Get clarity on what the skill will help users write:

- **Introduction**: Opening section that frames the article
- **Conclusion/Discussion**: Closing section that interprets findings
- **Theory/Literature Review**: Background section positioning contribution
- **Methods**: Section describing research design and data
- **Findings/Results**: Section presenting empirical patterns
- **Abstract**: Condensed summary of entire article
- **Other**: User-specified section type

Document:
- Section name (as it appears in target journals)
- Alternative names (e.g., "Background" vs. "Literature Review")
- Typical location in article structure
- Key rhetorical functions

### 2. Assess Corpus

Review the corpus to confirm viability:

```markdown
## Corpus Assessment

**Location**: [path to corpus]
**Article count**: [number]
**Format**: [txt/md/pdf]

**Viability check**:
- [ ] 30+ articles (recommended for stable clusters)
- [ ] All same section type (not mixed sections)
- [ ] From comparable venues (similar genre expectations)
- [ ] Text is extractable (not image-only PDFs)

**Venue distribution** (if known):
- [Journal 1]: X articles
- [Journal 2]: Y articles
```

If corpus has fewer than 30 articles, note this as a limitation but proceed—clusters will be less stable.

### 3. Select Model Skill

Review available model skills and select the most appropriate:

| Skill | Best For | Key Features |
|-------|----------|--------------|
| `lit-writeup` | Theory/Lit Review sections | 5 clusters, paragraph functions, citation patterns |
| `interview-bookends` | Intro/Conclusion pairs | Coherence checking, callbacks, opening moves |
| `interview-writeup` | Methods/Findings | Quote integration, anchor/echo patterns |

For each candidate, identify what to extract:
- Phase structure (how many phases, what each does)
- Cluster categories (how clusters are defined)
- Benchmark types (what statistics to track)
- Technique guides (what writing tools to include)

**Selection criteria**:
- Match section type if possible (lit-writeup for theory sections)
- Match rhetorical function (interview-bookends for framing sections)
- Consider complexity (simpler model for first skill)

### 4. Review Model Skill Structure

Read the selected model skill and extract its structure:

```markdown
## Model Skill: [name]

### Phase Structure
| Phase | Goal | Outputs |
|-------|------|---------|
| 0 | [goal] | [outputs] |
| 1 | [goal] | [outputs] |
| ... | ... | ... |

### Cluster Categories
- **[Cluster 1]**: [description, prevalence]
- **[Cluster 2]**: [description, prevalence]
- ...

### Benchmarks Tracked
- [Metric 1]: [typical value]
- [Metric 2]: [typical value]
- ...

### Technique Guides
- [Guide 1]: [purpose]
- [Guide 2]: [purpose]
- ...
```

### 5. Define Code Categories

Based on the model skill, list the genre features you'll code in Phase 2:

**Structural features to code**:
- [ ] Word count
- [ ] Paragraph count
- [ ] Subsection presence/count
- [ ] [other structural features from model]

**Rhetorical moves to code**:
- [ ] Opening move type
- [ ] [move 2 from model]
- [ ] [move 3 from model]
- ...

**Citation/linguistic features to code**:
- [ ] Citation density
- [ ] [other features from model]

### 6. Confirm Output Skill Name

Get user confirmation on:
- **Skill name**: (e.g., `discussion-writer`, `methods-guide`)
- **Description**: One-sentence summary for plugin.json
- **Keywords**: 3-5 tags for discoverability

## Output Files to Create

Save all outputs to `/analysis/phase0-scope/`:

1. **scope-definition.md** - Core scope document:
   ```markdown
   # Scope Definition: [Skill Name]

   ## Target Section
   **Section type**: [name]
   **Alternative names**: [...]
   **Key functions**: [what this section does rhetorically]

   ## Corpus
   **Location**: [path]
   **Article count**: [n]
   **Venues**: [list]
   **Date range**: [if known]

   ## Model Skill
   **Selected model**: [skill name]
   **Rationale**: [why this model]

   ## Output Skill
   **Name**: [skill-name]
   **Description**: [one sentence]
   **Keywords**: [tags]

   ## Code Categories
   [list of features to code]
   ```

2. **model-skill-summary.md** - Extracted structure from model skill

3. **corpus-manifest.md** - List of all articles in corpus with file paths

## Guiding Principles

1. **Specificity over breadth**: A skill for "Discussion sections in qualitative sociology articles" is better than "Discussion sections."

2. **Model match matters**: Choosing an appropriate model skill saves significant adaptation work.

3. **Corpus quality over quantity**: 40 well-matched articles beat 80 mixed ones.

4. **Name for users**: Skill names should be immediately clear (e.g., `abstract-writer` not `text-generator`).

## When You're Done

Return a summary to the orchestrator that includes:
1. Confirmation that scope is defined
2. Target section and its key functions
3. Corpus size and source venues
4. Selected model skill and rationale
5. Planned code categories (high-level list)
6. Output skill name and description
7. Any concerns or limitations noted
8. Recommendation to proceed to Phase 1

**Critical**: Get user confirmation before proceeding. Scope changes mid-analysis are costly.
