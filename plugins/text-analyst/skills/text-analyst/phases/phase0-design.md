# Phase 0: Research Design & Method Selection

You are executing Phase 0 of a computational text analysis. Your goal is to establish the research question, select appropriate methods, and choose the best language (R or Python) for the analysis.

## Why This Phase Matters

Text analysis methods answer different questions. Topic models reveal themes; classifiers assign categories; sentiment measures affect. Choosing the wrong method produces meaningless results. This phase ensures alignment between question and method before any analysis.

## Technique Guides

**Consult these conceptual guides** in `text-concepts/` for method selection:

| Guide | Use For |
|-------|---------|
| `01_dictionary_methods.md` | Measuring known concepts with lexicons |
| `02_topic_models.md` | Discovering themes or topics |
| `03_supervised_classification.md` | Categorizing documents with training data |
| `04_embeddings.md` | Semantic similarity, document vectors |
| `05_sentiment_analysis.md` | Measuring sentiment or affect |
| `06_validation_strategies.md` | Planning validation approach |

## Your Tasks

### 1. Clarify the Research Question

Ask the user to articulate:
- **What do you want to learn from the text?**
  - Discover themes? → Topic modeling
  - Measure a known concept? → Dictionary/classification
  - Track sentiment? → Sentiment analysis
  - Find similar documents? → Embeddings
  - Extract entities? → NER

- **Is this exploratory or confirmatory?**
  - Exploratory: Topic models, unsupervised clustering
  - Confirmatory: Dictionary methods, supervised classification

- **What is the unit of analysis?**
  - Document-level (articles, posts, interviews)
  - Sentence-level (for fine-grained analysis)
  - Token-level (for NER, POS tagging)

### 2. Assess the Corpus

Gather corpus characteristics:

| Characteristic | Questions |
|---------------|-----------|
| **Size** | How many documents? Tokens? |
| **Type** | News, social media, interviews, academic? |
| **Language** | English only? Multiple languages? |
| **Structure** | Short (tweets) or long (articles)? |
| **Metadata** | Date, author, source? Covariates? |
| **Quality** | OCR errors? Missing data? Duplicates? |

**Size guidance:**
- < 500 documents: Dictionary methods, qualitative reading
- 500-10,000: LDA, STM work well
- 10,000+: All methods viable; consider sampling for validation
- 100,000+: Neural methods become more attractive

### 3. Select Methods

Based on question and corpus, recommend methods:

| Research Goal | Primary Method | Alternatives |
|--------------|----------------|--------------|
| Discover themes | LDA, STM | BERTopic, clustering |
| Measure known concepts | Dictionary | Supervised classifier |
| Track sentiment | Lexicon (LIWC, VADER) | ML sentiment classifier |
| Classify documents | Supervised (SVM, BERT) | Zero-shot classification |
| Find similar texts | Embeddings (SBERT) | TF-IDF + cosine |
| Extract entities | spaCy NER | Custom NER training |
| Topic change over time | STM with time covariate | Dynamic topic models |

### 4. Choose Language (R or Python)

**Use R when:**
- Topic modeling with covariates (STM is gold standard)
- Dictionary/sentiment with tidytext workflow
- Publication-quality visualizations (ggplot2)
- Integration with quantitative analysis

**Use Python when:**
- Transformer/BERT methods required
- BERTopic for neural topic modeling
- Named entity recognition (spaCy)
- Deep learning classification
- Large-scale processing with GPU

**Decision guide:**

```
Is the primary method topic modeling with covariates?
  → R (stm package)

Is the primary method neural/transformer-based?
  → Python (HuggingFace, BERTopic)

Is the primary method dictionary/sentiment?
  → R (tidytext, more lexicons)

Is NER required?
  → Python (spaCy)

Do you need publication-ready figures?
  → R (ggplot2)

Is the corpus very large (>100K)?
  → Python (better memory management)

No strong preference?
  → R for classical methods, Python for neural
```

### 5. Plan Validation Approach

All text analysis requires validation. Plan:

**Human validation:**
- Sample documents for manual review
- Expert labeling of topics/categories
- Inter-coder reliability for dictionaries

**Computational diagnostics:**
- Topic coherence metrics
- Classification accuracy (precision, recall, F1)
- Holdout validation

**Robustness:**
- Sensitivity to K (number of topics)
- Sensitivity to preprocessing
- Multiple random seeds

### 6. Document Data Requirements

Specify what the analysis needs:
- Text column(s)
- Document identifiers
- Metadata fields (date, source, author)
- Covariates for STM (if applicable)
- Labels for supervised learning (if applicable)
- Sample size for human validation

## Output: Design Memo

Append a `## Phase 0: Research Design` section to `memos/analysis-memo.md` (create the file if it does not exist):

```markdown
## Phase 0: Research Design

## Research Question
[Clear statement of what you want to learn from the text]

## Corpus Description
- **Documents**: [N documents, type]
- **Tokens**: [approximate total]
- **Language**: [language(s)]
- **Time span**: [if temporal]
- **Source**: [where texts come from]

## Selected Methods
- **Primary method**: [method name]
- **Rationale**: [why this method fits the question]
- **Alternatives considered**: [what else could work]

## Language Choice
- **Selected**: [R / Python]
- **Rationale**: [why this language]
- **Key packages**: [main packages to use]

## Validation Plan
- **Human validation**: [sample size, procedure]
- **Computational metrics**: [which metrics]
- **Robustness checks**: [sensitivity analyses]

## Preprocessing Plan (preliminary)
- Tokenization: [word, sentence, n-gram]
- Stopwords: [standard list, custom additions]
- Stemming/lemmatization: [yes/no, which]
- Minimum document frequency: [threshold]

## Questions for User
- [Any clarifications needed before proceeding]
```

## When You're Done

Commit the memo: `git add memos/analysis-memo.md && git commit -m "text-analyst: Phase 0 complete"`

Return a summary to the orchestrator that includes:
1. The research question (one sentence)
2. Selected method and language with rationale
3. Corpus characteristics summary
4. Planned validation approach
5. Any questions or concerns for the user

**Do not proceed to Phase 1 until the user confirms the research design.**
