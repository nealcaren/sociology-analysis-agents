# Phase 3: Main Analysis

You are executing Phase 3 of a computational text analysis. Your goal is to run the specified models and produce initial results for review.

## Why This Phase Matters

This phase executes the pre-specified analysis. The key discipline is: run what was specified, not what looks best after seeing results. Document any deviations.

## Technique Guides

**Consult implementation guides** for your language:

**R** (in `text-r-techniques/`):
| Method | Guide |
|--------|-------|
| Dictionary/sentiment | `02_dictionary_sentiment.md` |
| Topic models (LDA, STM) | `03_topic_models.md` |
| Supervised classification | `04_supervised.md` |
| Embeddings | `05_embeddings.md` |
| Visualization | `06_visualization.md` |

**Python** (in `text-python-techniques/`):
| Method | Guide |
|--------|-------|
| Dictionary/sentiment | `02_dictionary_sentiment.md` |
| Topic models (gensim, BERTopic) | `03_topic_models.md` |
| Supervised classification | `04_supervised.md` |
| Embeddings | `05_embeddings.md` |
| Visualization | `06_visualization.md` |

## Your Tasks

### 1. Run Primary Models

Execute the pre-specified model with documented parameters:

**Topic Models:**
```r
# R example with STM
library(stm)
set.seed(SPECIFIED_SEED)

stm_model <- stm(
  documents = out$documents,
  vocab = out$vocab,
  K = SPECIFIED_K,
  prevalence = ~ covariate1 + covariate2,
  data = out$meta,
  init.type = "Spectral"
)
```

```python
# Python example with BERTopic
from bertopic import BERTopic
import random
random.seed(SPECIFIED_SEED)

topic_model = BERTopic(
    embedding_model="all-MiniLM-L6-v2",
    min_topic_size=SPECIFIED_MIN_SIZE,
    nr_topics=SPECIFIED_K  # or "auto"
)
topics, probs = topic_model.fit_transform(documents)
```

**Classification:**
```python
# Python example
from sklearn.model_selection import cross_val_score
from sklearn.svm import SVC

model = SVC(C=SPECIFIED_C, kernel=SPECIFIED_KERNEL)
scores = cross_val_score(model, X_train, y_train, cv=SPECIFIED_CV)
```

**Dictionary:**
```r
# R example with tidytext
library(tidytext)

sentiment_scores <- tokens %>%
  inner_join(get_sentiments("SPECIFIED_LEXICON")) %>%
  group_by(doc_id) %>%
  summarise(sentiment = sum(value))
```

### 2. Assess Convergence and Fit

**Topic models:**
- Did the model converge?
- Check convergence diagnostics
- Compare log-likelihood across iterations
- Check for degenerate topics (empty or dominant)

**Classification:**
- Training accuracy (should be high)
- Gap between training and validation (overfitting?)
- Learning curves if applicable

**Dictionary:**
- Coverage: What proportion of documents have matches?
- Proportion of terms matched vs. total

### 3. Extract and Label Results

**For topic models - create topic labels:**

| Topic | Top Words | Proposed Label | Confidence |
|-------|-----------|----------------|------------|
| 1 | word1, word2, word3... | [Label] | High/Medium/Low |
| 2 | word1, word2, word3... | [Label] | High/Medium/Low |
| ... | | | |

**Labeling guidance:**
- Base labels on top 10-20 words
- Read representative documents (highest topic probability)
- Use FREX words for STM (frequent AND exclusive)
- Mark unclear topics explicitly

**For classification - create performance summary:**

| Class | Precision | Recall | F1 | Support |
|-------|-----------|--------|----|------------|
| Class1 | | | | N |
| Class2 | | | | N |
| Macro avg | | | | |
| Weighted avg | | | | |

**For dictionary - create coverage summary:**

| Document Group | N Docs | % With Match | Mean Score | SD |
|---------------|--------|--------------|------------|-----|
| All | N | % | X | X |
| [Subgroup1] | N | % | X | X |
| [Subgroup2] | N | % | X | X |

### 4. Create Initial Visualizations

**Topic models:**
- Topic proportions (bar chart)
- Topic correlations (network or heatmap)
- Topic prevalence over time (if temporal)
- Representative documents per topic

**Classification:**
- Confusion matrix
- ROC curves (if applicable)
- Feature importance (top predictive terms)

**Dictionary:**
- Score distributions (histogram)
- Scores over time (if temporal)
- Scores by group (if comparing)

### 5. Document Deviations

If ANY changes were made from the specification:

```markdown
## Deviations from Specification

### Deviation 1
- **Specified**: [what was planned]
- **Actual**: [what was done]
- **Reason**: [why changed]
- **Impact**: [how this affects interpretation]

### Deviation 2
...
```

Changes requiring documentation:
- Different K than specified
- Modified preprocessing
- Changed model parameters
- Different random seed
- Excluded documents

### 6. Initial Interpretation

Provide preliminary interpretation with appropriate caveats:

**For topic models:**
- Are topics coherent and interpretable?
- Do topic prevalences match expectations?
- Any surprising patterns?
- Which topics need more investigation?

**For classification:**
- Is performance adequate for the research question?
- Which classes are confused?
- Are errors systematic?

**For dictionary:**
- Does the distribution make sense?
- Are there ceiling/floor effects?
- Do group differences align with expectations?

## Output: Results Summary

Append a `## Phase 3: Main Analysis` section to `memos/analysis-memo.md`:

```markdown
## Phase 3: Main Analysis

## Model Fit

### Convergence
- [Converged: Yes/No]
- [Iterations: N]
- [Final likelihood/loss: X]

### Diagnostics
- [Metric 1]: [value]
- [Metric 2]: [value]

## Primary Results

### [Topic Labels / Classification Performance / Dictionary Scores]

[Results table from above]

### Key Findings
1. [Finding 1]
2. [Finding 2]
3. [Finding 3]

## Visualizations

[Reference to saved figures]
- Figure 1: [description] (`output/figures/...`)
- Figure 2: [description] (`output/figures/...`)

## Deviations from Specification

[None / List of changes]

## Preliminary Interpretation

[2-3 paragraphs of initial interpretation with caveats]

## Concerns / Questions

- [Concern 1]
- [Concern 2]

## Next Steps for Validation

Based on these results, validation should focus on:
1. [Validation priority 1]
2. [Validation priority 2]
```

## Quality Checks Before Proceeding

Before declaring Phase 3 complete:

- [ ] Model converged appropriately
- [ ] Results saved with version info
- [ ] Random seed documented and used
- [ ] All deviations documented
- [ ] Initial visualizations created
- [ ] Topic labels proposed (if applicable)
- [ ] No obvious errors or artifacts

## When You're Done

Commit progress: `git add memos/analysis-memo.md output/ code/ && git commit -m "text-analyst: Phase 3 complete"`

Return a summary to the orchestrator that includes:
1. Model fit assessment (did it work?)
2. Key results summary (topics, performance, distributions)
3. Any deviations from specification
4. Preliminary interpretation
5. Concerns requiring attention in validation

**Do not proceed to Phase 4 until the user reviews these results.**
