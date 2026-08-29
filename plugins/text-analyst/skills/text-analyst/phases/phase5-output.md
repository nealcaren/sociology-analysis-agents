# Phase 5: Output & Interpretation

You are executing Phase 5 of a computational text analysis. Your goal is to produce publication-ready outputs and write a careful, appropriately caveated interpretation of findings.

## Why This Phase Matters

Text analysis results require careful interpretation. Overclaimingundermines credibility. This phase produces polished outputs and ensures the narrative matches what the evidence supports.

## Technique Guides

**Consult visualization guides** for your language:
- R: `text-r-techniques/06_visualization.md`
- Python: `text-python-techniques/06_visualization.md`

## Your Tasks

### 1. Create Publication-Quality Tables

**Topic Model Results Table:**

| Topic | Label | Top Words (FREX) | Prevalence | Example Document |
|-------|-------|------------------|------------|------------------|
| 1 | [Label] | word1, word2, word3, word4, word5 | X% | "Quote..." |
| 2 | [Label] | word1, word2, word3, word4, word5 | X% | "Quote..." |
| ... | | | | |

*Notes: K = [N] topics. FREX words balance frequency and exclusivity. N = [documents].*

**Classification Results Table:**

| Class | Precision | Recall | F1 | Support |
|-------|-----------|--------|----|---------|
| Class 1 | 0.XX | 0.XX | 0.XX | N |
| Class 2 | 0.XX | 0.XX | 0.XX | N |
| ... | | | | |
| **Macro Average** | **0.XX** | **0.XX** | **0.XX** | **N** |

*Notes: 5-fold stratified cross-validation. Features: [description].*

**Dictionary/Sentiment Summary:**

| Group | N | Mean Score | SD | 95% CI |
|-------|---|------------|-----|---------|
| Group 1 | N | X.XX | X.XX | [X.XX, X.XX] |
| Group 2 | N | X.XX | X.XX | [X.XX, X.XX] |
| Difference | | X.XX | | [X.XX, X.XX] |

*Notes: [Dictionary name]. Score range: [X to Y].*

### 2. Create Publication-Quality Figures

**Topic models - required figures:**

1. **Topic prevalence** (bar chart or dot plot)
   - Ordered by prevalence
   - Include uncertainty intervals if available

2. **Topic content** (word clouds or bar charts)
   - Top words per topic
   - Consider FREX for STM

3. **Topic relationships** (if relevant)
   - Topic correlation network
   - Hierarchical clustering

4. **Topic trends** (if temporal)
   - Prevalence over time
   - Confidence bands

**Classification - required figures:**

1. **Confusion matrix** (heatmap)
   - Normalized by row (recall focus) or column (precision focus)
   - Include raw counts

2. **Feature importance** (if interpretable model)
   - Top predictive words per class
   - Coefficients with confidence intervals

**Dictionary/Sentiment - required figures:**

1. **Distribution** (histogram or density)
   - By group if comparing

2. **Time series** (if temporal)
   - Smoothed trends
   - Confidence bands

### 3. Write Results Narrative

Present the results narrative directly in conversation — do not save it to a file. These are intermediate outputs intended to feed into writing skills (e.g., `quant-findings-writer`, `qual-findings-writer`), not standalone documents.

Structure the narrative:

**Opening:**
- Remind reader of the research question
- Briefly state the approach

**Main findings:**
- Present results without overstating
- Use hedged language appropriately
- Connect to tables and figures

**Validation summary:**
- Briefly note validation approach
- Report key diagnostics

**Limitations:**
- Acknowledge methodological limitations
- Note what the analysis cannot show

#### Language Guidelines

**Avoid:**
- "The topic model discovered..."
- "The algorithm found that..."
- "This proves..."
- "Clearly..."
- "Obviously..."

**Prefer:**
- "The analysis suggests..."
- "Patterns in the data indicate..."
- "One interpretation is..."
- "This is consistent with..."
- "The evidence supports..."

**Topic model language:**
- Topics are "characterized by" words, not "about" concepts
- Topics "tend to appear in" documents, not "represent" ideas
- Prevalence is "estimated" with uncertainty

**Classification language:**
- "The classifier achieved X accuracy on held-out data"
- "Misclassifications tended to occur when..."
- Performance is on "this corpus," not "in general"

**Dictionary language:**
- "Documents mentioning X words..."
- Coverage and limitations should be noted
- "According to this measure..."

### 4. Write Limitations Section

Present the limitations section directly in conversation alongside the results narrative — do not save it to a file. It feeds into writing skills alongside the results narrative.

Every text analysis has limitations. Document:

**Method limitations:**
- Topic models: K is a choice, not a truth
- Classification: Performance depends on training data
- Dictionary: Coverage and domain validity

**Data limitations:**
- Corpus scope: Findings apply to this corpus
- Selection: How texts were selected/sampled
- Quality: OCR errors, missing data

**Interpretation limitations:**
- Topics are statistical patterns, not concepts
- High probability ≠ topic is "about" that theme
- Classifiers learn correlations, not causation

### 5. Prepare Replication Materials

Create replication package:

```
replication/
├── README.md           # Instructions
├── requirements.R      # or requirements.txt
├── 01_preprocess.R     # or .py
├── 02_analysis.R       # or .py
├── 03_validation.R     # or .py
├── 04_figures.R        # or .py
└── session_info.txt    # Package versions
```

**README.md for replication:**

```markdown
# Replication Materials

## Requirements
- R version X.X.X (or Python X.X)
- Packages: [list with versions]

## Data
Data files should be placed in `data/raw/`:
- [file1.csv]: [description]
- [file2.csv]: [description]

Note: Original data [is/is not] included due to [access/size/privacy].

## Replication Steps
1. Install requirements: `source("requirements.R")`
2. Preprocess data: `source("01_preprocess.R")`
3. Run analysis: `source("02_analysis.R")`
4. Validate: `source("03_validation.R")`
5. Generate figures: `source("04_figures.R")`

## Random Seed
All analyses use seed: [SEED]

## Expected Output
- [output1]: [description]
- [output2]: [description]

## Contact
[Author contact for questions]
```

### 6. Write Methods Section Draft

Present the methods section draft directly in conversation — do not save it to a file. It is an intermediate output for use with writing skills.

Write methods section following journal conventions:

```markdown
## Text Analysis Methods

### Corpus
The corpus consists of N documents from [source],
spanning [time period]. Documents were [sampling description].

### Preprocessing
Text was preprocessed using [package/tool].
[Specific steps: tokenization, stopword removal, etc.]
Final vocabulary: N terms across N documents.

### Analysis
We used [method] implemented in [package] (version X.X).
[Key parameters: K topics, hyperparameters, etc.]
[Validation approach].

### Validation
[Human validation: sample size, procedure, results]
[Computational diagnostics: metrics, results]
[Robustness checks: what varied, results]
```

## Output: Final Package

Create the following in `output/`:

```
output/
├── tables/
│   ├── table1_topic_summary.csv
│   ├── table2_prevalence.csv
│   └── ...
├── figures/
│   ├── fig1_topic_prevalence.pdf
│   ├── fig2_topic_words.pdf
│   └── ...
└── replication/
    └── [replication package]
```

The results narrative, methods section, and limitations are presented in conversation — they feed directly into writing skills and are not saved as files.

## Final Memo

Append a `## Phase 5: Output & Interpretation` section to `memos/analysis-memo.md`:

```markdown
## Phase 5: Output & Interpretation

## Deliverables

### Tables
1. [Table 1]: [description, location]
2. [Table 2]: [description, location]

### Figures
1. [Figure 1]: [description, location]
2. [Figure 2]: [description, location]

### Replication Materials
[Location, completeness status]

## Key Messages

### Main Findings (1-3 sentences)
[Summary of what the analysis shows]

### Required Caveats
1. [Caveat 1]
2. [Caveat 2]

### Claims Supported by Evidence
- [Claim 1]: [evidence]
- [Claim 2]: [evidence]

### Claims NOT Supported
- [Cannot claim 1]: [why not]
- [Cannot claim 2]: [why not]

## Quality Checklist

- [ ] All tables formatted consistently
- [ ] All figures publication-ready (300 dpi, clear labels)
- [ ] Narrative uses appropriate hedging
- [ ] Limitations section complete
- [ ] Replication package tested
- [ ] Methods section matches actual analysis
- [ ] Random seeds documented throughout
```

## When You're Done

Commit the final state: `git add memos/analysis-memo.md output/ && git commit -m "text-analyst: Phase 5 complete"`

Return a summary to the orchestrator that includes:
1. List of deliverables produced (tables, figures, replication materials)
2. Key findings summary (2-3 sentences)
3. Main limitations to acknowledge
4. Replication package status
5. Any remaining concerns

**Analysis is complete when user accepts the outputs.**
