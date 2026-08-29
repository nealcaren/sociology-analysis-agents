# Phase 4: Validation & Robustness

You are executing Phase 4 of a computational text analysis. Your goal is to validate findings through human assessment and computational diagnostics, and test robustness to analytical choices.

## Why This Phase Matters

Algorithmic output is not ground truth. Topic models find patterns—but are they meaningful patterns? Classifiers achieve accuracy—but do they capture what you intend? This phase establishes that results are valid and robust, not artifacts of method choices.

## Technique Guides

**Consult validation guide** in `text-concepts/`:
- `06_validation_strategies.md` - comprehensive validation approaches

**Implementation guides** for diagnostics:
- R: `text-r-techniques/03_topic_models.md` (coherence, exclusivity)
- Python: `text-python-techniques/03_topic_models.md` (coherence, c_v)

## Your Tasks

### 1. Human Validation

**For topic models - Topic Intrusion Test:**

Select N topics. For each topic:
1. Show top 10-15 words
2. Add one "intruder" word from another topic
3. Ask human coders to identify the intruder
4. High accuracy = coherent topics

**For topic models - Document Reading:**

For each topic:
1. Sample 5-10 highest-probability documents
2. Read documents
3. Assess: Does topic label fit these documents?
4. Note: Are there false positives? Missing themes?

```markdown
## Topic Validation: Topic 3 "Economic Policy"

### Top Words
tax, economy, budget, spending, fiscal, growth...

### Sample Documents Reviewed
| Doc ID | Topic Prob | Label Fits? | Notes |
|--------|------------|-------------|-------|
| 1234 | 0.85 | Yes | Clearly about tax policy |
| 2345 | 0.72 | Partially | Mixed with healthcare |
| 3456 | 0.68 | Yes | Budget discussion |
| ... | | | |

### Assessment
- Label accuracy: X/N documents
- Refinements needed: [suggestions]
```

**For classification - Error Analysis:**

1. Sample misclassified documents
2. For each error:
   - Why did the model fail?
   - Is the gold label correct?
   - Is this a systematic error?

```markdown
## Error Analysis

### False Positives (predicted [Class], actual [Other])
| Doc ID | Predicted | Actual | Why Misclassified |
|--------|-----------|--------|-------------------|
| 1234 | Class A | Class B | Shared vocabulary |
| ... | | | |

### False Negatives (predicted [Other], actual [Class])
| Doc ID | Predicted | Actual | Why Missed |
|--------|-----------|--------|------------|
| 5678 | Class B | Class A | Subtle example |
| ... | | | |

### Systematic Patterns
- [Pattern 1]
- [Pattern 2]
```

**For dictionary - KWIC Validation:**

For key terms in dictionary:
1. Sample uses in corpus
2. Assess: Is this the intended meaning?
3. Note domain-specific usages

```markdown
## Dictionary Term Validation: "positive"

### Sample Uses
| Doc ID | Context | Valid? |
|--------|---------|--------|
| 1234 | "...test came back positive..." | No (medical) |
| 2345 | "...positive economic outlook..." | Yes |
| 3456 | "...positive feedback loop..." | No (technical) |

### Validity Rate: X/N valid uses
### Action: [Keep / Remove / Add to exceptions]
```

### 2. Computational Diagnostics

**Topic Model Diagnostics:**

| Metric | Value | Interpretation |
|--------|-------|----------------|
| Mean coherence (C_V) | | > 0.5 generally good |
| Mean coherence (UMass) | | Less negative is better |
| Mean exclusivity (STM) | | Higher = more distinct |
| Perplexity (held-out) | | Lower is better fit |

```r
# R example for STM
exclusivity <- exclusivity(stm_model)
coherence <- semanticCoherence(stm_model, out$documents)

# Plot coherence vs exclusivity
plot(coherence, exclusivity,
     xlab = "Semantic Coherence",
     ylab = "Exclusivity")
```

```python
# Python example for gensim
from gensim.models import CoherenceModel

coherence_model = CoherenceModel(
    model=lda_model,
    texts=tokenized_docs,
    coherence='c_v'
)
coherence_score = coherence_model.get_coherence()
```

**Classification Diagnostics:**

| Metric | Train | Validation | Test |
|--------|-------|------------|------|
| Accuracy | | | |
| Macro F1 | | | |
| Per-class F1 | | | |

Check for:
- Overfitting (train >> validation)
- Class imbalance effects
- Confidence calibration

**Dictionary Diagnostics:**

| Metric | Value |
|--------|-------|
| Coverage (% docs with ≥1 match) | |
| Mean matches per doc | |
| Correlation with alternative measure | |

### 3. Robustness Checks

Run pre-specified robustness checks from Phase 2:

**Sensitivity to K (topic models):**

| K | Coherence | Exclusivity | Interpretation |
|---|-----------|-------------|----------------|
| K-5 | | | [Do similar topics emerge?] |
| K (main) | | | [Baseline] |
| K+5 | | | [Do topics split sensibly?] |

**Sensitivity to preprocessing:**

| Preprocessing | Result | Compared to Main |
|---------------|--------|------------------|
| With stemming | [result] | [consistent/different] |
| Without stopwords | [result] | [consistent/different] |
| Different threshold | [result] | [consistent/different] |

**Sensitivity to random seed:**

| Seed | Result | Compared to Main |
|------|--------|------------------|
| Seed 1 | [result] | [baseline] |
| Seed 2 | [result] | [consistent/different] |
| Seed 3 | [result] | [consistent/different] |

For topic models: Do the same topics emerge? Check topic alignment.

**Subset analysis:**

| Subset | N | Result | Compared to Full |
|--------|---|--------|------------------|
| Time period 1 | | | |
| Time period 2 | | | |
| Source type A | | | |
| Source type B | | | |

### 4. Alternative Methods (if applicable)

Compare to alternative approaches:

| Method | Primary Result | Alternative Result | Correlation |
|--------|---------------|-------------------|-------------|
| Main method | [result] | N/A | N/A |
| Alternative | N/A | [result] | [r = X] |

Example: Compare dictionary sentiment to ML sentiment.

### 5. Assess Overall Validity

**Validation Summary Table:**

| Validation Type | Result | Concern Level |
|-----------------|--------|---------------|
| Human - topic coherence | X/N intrusion test | Low/Medium/High |
| Human - document reading | X/N fit well | Low/Medium/High |
| Computational - coherence | [score] | Low/Medium/High |
| Robustness - K | [consistent/varies] | Low/Medium/High |
| Robustness - preprocessing | [consistent/varies] | Low/Medium/High |
| Robustness - seed | [consistent/varies] | Low/Medium/High |

**Overall assessment:**
- Are findings valid? [Yes/Partially/Concerns]
- What caveats are needed?
- What cannot be claimed?

## Output: Validation Report

Append a `## Phase 4: Validation & Robustness` section to `memos/analysis-memo.md`:

```markdown
## Phase 4: Validation & Robustness

## Human Validation

### Topic/Category Assessment
[Summary of human coding]

### Inter-rater Reliability
[If multiple coders: Kappa, agreement %]

## Computational Diagnostics

### Model Fit Metrics
| Metric | Value | Assessment |
|--------|-------|------------|
| | | |

### Diagnostic Visualizations
[Reference figures]

## Robustness Analysis

### Sensitivity to K
[Results table and interpretation]

### Sensitivity to Preprocessing
[Results table and interpretation]

### Sensitivity to Random Seed
[Results table and interpretation]

### Subset Analysis
[Results table and interpretation]

## Alternative Methods
[If applicable]

## Validity Assessment

### Strengths
- [Strength 1]
- [Strength 2]

### Limitations
- [Limitation 1]
- [Limitation 2]

### Required Caveats for Interpretation
1. [Caveat 1]
2. [Caveat 2]

### Claims That Cannot Be Made
- [Cannot claim 1]
- [Cannot claim 2]

## Recommendation
[Proceed to output / Revise analysis / Major concerns]
```

## When You're Done

Commit progress: `git add memos/analysis-memo.md output/ && git commit -m "text-analyst: Phase 4 complete"`

Return a summary to the orchestrator that includes:
1. Human validation results (what proportion validated?)
2. Key diagnostic metrics
3. Robustness assessment (are results stable?)
4. Required caveats and limitations
5. Recommendation for proceeding

**Do not proceed to Phase 5 until the user reviews validation results.**
