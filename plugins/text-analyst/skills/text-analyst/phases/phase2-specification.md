# Phase 2: Method Specification

You are executing Phase 2 of a computational text analysis. Your goal is to fully specify all model parameters and preprocessing decisions before running any models.

## Why This Phase Matters

Specification decisions shape results. Choosing K=20 topics vs K=50 is a research decision, not a tuning parameter. Documenting choices before seeing results prevents p-hacking and specification searching in text analysis.

## Technique Guides

**Consult the appropriate guides** based on method and language:

**Conceptual** (in `text-concepts/`):
| Method | Guide |
|--------|-------|
| Dictionary | `01_dictionary_methods.md` |
| Topic models | `02_topic_models.md` |
| Classification | `03_supervised_classification.md` |
| Embeddings | `04_embeddings.md` |
| Sentiment | `05_sentiment_analysis.md` |

**Implementation** (in `text-r-techniques/` or `text-python-techniques/`):
- `02_dictionary_sentiment.md` for dictionary/sentiment code
- `03_topic_models.md` for LDA/STM/BERTopic code
- `04_supervised.md` for classification code
- `05_embeddings.md` for embedding code

## Your Tasks

### 1. Document Final Preprocessing Pipeline

Finalize all preprocessing decisions from Phase 1:

```markdown
## Preprocessing Pipeline

1. **Text cleaning**
   - [Cleaning steps in order]

2. **Tokenization**
   - Method: [word/sentence/n-gram]
   - Parameters: [any options]

3. **Normalization**
   - Case: [lowercase/preserve]
   - Stemming: [none/Porter/Snowball]
   - Lemmatization: [none/spaCy/WordNet]

4. **Vocabulary pruning**
   - Min document frequency: [N or %]
   - Max document frequency: [N or %]
   - Min term length: [N]

5. **Stopwords**
   - Base list: [none/SMART/English/custom]
   - Added terms: [list]
   - Removed terms: [list if domain-specific kept]

6. **Final vocabulary size**: [N terms]
```

### 2. Specify Model Parameters

#### For Topic Models (LDA, STM)

| Parameter | Value | Rationale |
|-----------|-------|-----------|
| Number of topics (K) | | See guidance below |
| Alpha prior | | Typically use default |
| Beta/eta prior | | Typically use default |
| Iterations | | Until convergence |
| Random seed | | For reproducibility |
| Covariates (STM) | | Which metadata affects topics |

**Choosing K:**
- K is NOT a tuning parameter to optimize
- K is a research decision about granularity
- Multiple valid K values often exist
- Err toward interpretability over metrics

**K guidance:**
- Start with theory: How many themes are plausible?
- Small corpus (< 1000): K = 5-15
- Medium corpus (1000-10000): K = 10-30
- Large corpus (> 10000): K = 20-50+
- Plan to run multiple K values for robustness

#### For BERTopic

| Parameter | Value | Rationale |
|-----------|-------|-----------|
| Embedding model | | sentence-transformers model |
| UMAP n_neighbors | | Typically 15 |
| UMAP n_components | | Typically 5 |
| HDBSCAN min_cluster_size | | Affects number of topics |
| HDBSCAN min_samples | | Affects outlier handling |
| Top n words | | For topic representation |

#### For Supervised Classification

| Parameter | Value | Rationale |
|-----------|-------|-----------|
| Model type | | SVM, LogReg, BERT, etc. |
| Features | | TF-IDF, embeddings, etc. |
| Train/test split | | Typically 80/20 |
| Validation approach | | k-fold, stratified |
| Class weights | | If imbalanced |
| Hyperparameters | | Grid search range |
| Random seed | | For reproducibility |

#### For Dictionary/Sentiment

| Parameter | Value | Rationale |
|-----------|-------|-----------|
| Dictionary name | | LIWC, VADER, custom |
| Aggregation | | Count, proportion, weighted |
| Negation handling | | How to handle "not good" |
| Missing words | | How to handle OOV |
| Normalization | | By document length? |

### 3. Pre-specify Validation Approach

**Before running models**, document how you'll validate:

**Human validation:**
- [ ] Sample size: N documents to manually review
- [ ] Sampling strategy: [random, stratified, purposive]
- [ ] Who codes: [researcher, RAs, domain experts]
- [ ] Inter-rater reliability: [measure to use]

**Computational diagnostics:**

For topic models:
- [ ] Coherence metric: [UMass, C_V, NPMI]
- [ ] Exclusivity (for STM)
- [ ] Held-out likelihood
- [ ] Semantic intrusion test (optional)

For classifiers:
- [ ] Primary metric: [accuracy, F1, macro-F1]
- [ ] Confusion matrix
- [ ] Per-class metrics
- [ ] Cross-validation folds: K

For dictionaries:
- [ ] Coverage: % of documents with matches
- [ ] Face validity: sample KWIC examples
- [ ] Convergent validity: correlation with other measures

**Robustness checks:**
- [ ] Alternative preprocessing (e.g., with/without stemming)
- [ ] Different K values (for topic models)
- [ ] Different random seeds
- [ ] Subset analysis (by time, source)

### 4. Plan Output Specifications

Document what outputs to produce:

**Tables:**
- Top words per topic (N words)
- Topic prevalence
- Classification metrics
- Dictionary coverage

**Figures:**
- Topic proportions over time
- Topic correlation network
- Confusion matrix
- Word clouds (if appropriate)

**Replication:**
- Seed value(s)
- Package versions
- Full preprocessing code
- Model object saved

### 5. Create Specification Memo

Append a `## Phase 2: Method Specification` section to `memos/analysis-memo.md`:

```markdown
## Phase 2: Method Specification

## Preprocessing Pipeline

[Full pipeline documented above]

## Model Specification

### Primary Model: [Model Name]

| Parameter | Value | Rationale |
|-----------|-------|-----------|
| [param1] | [value] | [why] |
| [param2] | [value] | [why] |
| ... | | |

### Random Seed
Seed: [value]

### Package Versions
- R: [version]
- [package1]: [version]
- [package2]: [version]

## Validation Plan

### Human Validation
- Sample: N documents, [sampling strategy]
- Coders: [who]
- Reliability: [metric]

### Computational Diagnostics
- [Metric 1]: [threshold for concern]
- [Metric 2]: [threshold for concern]

### Robustness Checks
1. [Check 1]: [what varies]
2. [Check 2]: [what varies]
3. [Check 3]: [what varies]

## Planned Outputs

### Tables
1. [Table 1 description]
2. [Table 2 description]

### Figures
1. [Figure 1 description]
2. [Figure 2 description]

## Code Template

```[r or python]
# Package versions
# [package]: [version]

# Set seed
set.seed([seed])  # or random.seed([seed])

# Load preprocessed data
# ...

# Fit model
# [model code template]

# Diagnostics
# [diagnostic code template]
```

## Questions for User
- [Any remaining decisions]
```

## Common Specification Decisions

### Topic Model K Selection Strategy

**DO NOT** just run multiple K and pick "best" coherence.

**DO** use multiple criteria:
1. Theoretical plausibility
2. Interpretability (can you label topics?)
3. Coherence as one input (not the only one)
4. Exclusivity for STM
5. Robustness (do topics persist across K?)

### Train/Test Split for Classification

- Hold out test set before ANY model selection
- Use separate validation set for hyperparameter tuning
- Stratify by class label
- Consider temporal split if data is time-ordered

### Dictionary Validation Requirements

Before trusting dictionary results:
1. Check coverage (what % of docs have any matches?)
2. Review KWIC examples (are matches valid?)
3. Check for domain-specific meanings
4. Consider false positives and negatives

## When You're Done

Commit the memo: `git add memos/analysis-memo.md && git commit -m "text-analyst: Phase 2 complete"`

Return a summary to the orchestrator that includes:
1. Final preprocessing pipeline
2. All model parameters and their rationale
3. Validation plan with specific metrics
4. Planned robustness checks
5. Any questions requiring user input

**Do not proceed to Phase 3 until the user approves the specification.**
