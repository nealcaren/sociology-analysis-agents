# Phase 1: Corpus Preparation & Exploration

You are executing Phase 1 of a computational text analysis. Your goal is to load, clean, explore, and understand the corpus before running any models.

## Why This Phase Matters

You cannot interpret text analysis results without knowing your corpus. This phase reveals data quality issues, informs preprocessing decisions, and establishes baseline understanding. Skipping exploration leads to garbage-in, garbage-out.

## Technique Guides

**Consult the appropriate technique guides** based on chosen language:

**For R** (in `text-r-techniques/`):
- `01_preprocessing.md` - tidytext and quanteda workflows

**For Python** (in `text-python-techniques/`):
- `01_preprocessing.md` - nltk, spaCy, sklearn pipelines

## Your Tasks

### 1. Load and Inspect the Corpus

**Initial inspection:**
```
- Number of documents
- Document length distribution (words per document)
- Total tokens
- Date range (if temporal)
- Missing values in text or metadata
- Duplicate documents
```

**Create basic statistics table:**

| Metric | Value |
|--------|-------|
| Total documents | N |
| Mean doc length (words) | X |
| Median doc length | X |
| Min / Max length | X / X |
| Empty documents | N |
| Duplicate documents | N |
| Date range | YYYY-MM-DD to YYYY-MM-DD |

### 2. Assess Data Quality

**Check for:**
- Empty or near-empty documents
- Duplicate texts (exact and near-duplicate)
- OCR errors (if digitized)
- Encoding issues (UTF-8 problems)
- Boilerplate text (headers, footers, signatures)
- Non-text content (URLs, HTML, code)

**Document any exclusions:**
```markdown
## Data Quality Issues

### Excluded Documents
- X documents excluded for: [reason]
- Y documents excluded for: [reason]

### Cleaning Applied
- [Cleaning step 1]
- [Cleaning step 2]
```

### 3. Make Preprocessing Decisions

For each decision, document the choice and rationale:

| Decision | Options | Your Choice | Rationale |
|----------|---------|-------------|-----------|
| **Case** | Lower / preserve | | |
| **Tokenization** | Word / sentence / n-gram | | |
| **Stopwords** | None / standard / custom | | |
| **Stemming** | None / Porter / Snowball | | |
| **Lemmatization** | None / spaCy / WordNet | | |
| **Numbers** | Keep / remove / normalize | | |
| **Punctuation** | Keep / remove | | |
| **Min doc frequency** | N | | |
| **Max doc frequency** | % | | |

**Preprocessing guidance:**
- **Topic models**: Usually lowercase, remove stopwords, no stemming (interpretability)
- **Classification**: Often minimal preprocessing; let model learn
- **Dictionary**: Match preprocessing to dictionary expectations
- **Embeddings**: Minimal preprocessing; models trained on raw text

### 4. Create Document-Term Matrix / Embeddings

**For bag-of-words approaches:**
- Create document-term matrix (DTM)
- Document vocabulary size before/after pruning
- Show most frequent terms
- Show terms removed by thresholds

**For embedding approaches:**
- Generate document embeddings
- Verify dimensions and coverage
- Check for OOV (out-of-vocabulary) rate

### 5. Generate Descriptive Visualizations

Create at minimum:

1. **Document length distribution**
   - Histogram of words per document
   - Identify outliers

2. **Term frequency distribution**
   - Top 50 most frequent terms
   - Zipf's law plot (optional)

3. **Temporal patterns** (if dated)
   - Documents over time
   - Word frequency trends

4. **Metadata distributions**
   - By source, author, category
   - Check balance across groups

### 6. Explore Corpus Content

**Sample reading:**
- Read 10-20 random documents
- Note themes, style, quality
- Identify potential issues

**Keyword-in-context (KWIC):**
- Search for key terms
- Understand usage patterns
- Refine dictionary terms if applicable

### 7. Check for Known Issues

**Topic modeling specific:**
- Very short documents (< 50 words) may be problematic
- Very long documents may need segmentation
- Highly technical vocabulary may need custom stopwords

**Classification specific:**
- Class imbalance in training data
- Label quality and consistency
- Sufficient examples per class

**Sentiment specific:**
- Domain-specific language (sarcasm, jargon)
- Negation handling
- Intensity modifiers

## Output: Corpus Report

Append a `## Phase 1: Corpus Preparation` section to `memos/analysis-memo.md`:

```markdown
## Phase 1: Corpus Preparation

## Corpus Overview

| Metric | Value |
|--------|-------|
| Total documents | N |
| After cleaning | N |
| Mean length (words) | X |
| Vocabulary size | X |
| Date range | YYYY to YYYY |

## Data Quality

### Issues Found
- [Issue 1]: [How addressed]
- [Issue 2]: [How addressed]

### Exclusions
- N documents excluded for [reason]

## Preprocessing Decisions

| Decision | Choice | Rationale |
|----------|--------|-----------|
| Case | lowercase | Standard for topic models |
| Stopwords | SMART + custom | Removed domain terms: [list] |
| ... | | |

## Vocabulary

### Most Frequent Terms (post-preprocessing)
| Term | Frequency | Document Frequency |
|------|-----------|-------------------|
| term1 | N | N% |
| ... | | |

### Custom Stopwords Added
- [term1]: [why removed]
- [term2]: [why removed]

## Visualizations

[Include or reference figures]
- Figure 1: Document length distribution (`output/figures/fig1_doc_lengths.pdf`)
- Figure 2: Top terms frequency (`output/figures/fig2_top_terms.pdf`)
- Figure 3: Documents over time (`output/figures/fig3_docs_over_time.pdf`)

## Sample Documents

### Representative Examples
[2-3 example documents with notes]

### Unusual Documents
[Documents that may need attention]

## Preliminary Observations
- [Observation 1]
- [Observation 2]
- [Potential concerns]

## Ready for Analysis?
- [ ] Data quality acceptable
- [ ] Preprocessing documented
- [ ] Vocabulary reasonable
- [ ] No major concerns
```

## Code Skeleton

### R (tidytext)
```r
library(tidyverse)
library(tidytext)
library(quanteda)

# Load data
corpus <- read_csv("data/raw/corpus.csv")

# Basic stats
corpus %>%
  mutate(n_words = str_count(text, "\\w+")) %>%
  summarise(
    n_docs = n(),
    mean_words = mean(n_words),
    median_words = median(n_words),
    min_words = min(n_words),
    max_words = max(n_words)
  )

# Tokenize
tokens <- corpus %>%
  unnest_tokens(word, text) %>%
  anti_join(stop_words)

# Top terms
tokens %>%
  count(word, sort = TRUE) %>%
  head(50)
```

### Python
```python
import pandas as pd
from collections import Counter
import nltk
from nltk.corpus import stopwords

# Load data
corpus = pd.read_csv("data/raw/corpus.csv")

# Basic stats
corpus['n_words'] = corpus['text'].str.split().str.len()
print(corpus['n_words'].describe())

# Tokenize and count
stop_words = set(stopwords.words('english'))
all_words = []
for text in corpus['text']:
    words = [w.lower() for w in text.split() if w.lower() not in stop_words]
    all_words.extend(words)

# Top terms
word_counts = Counter(all_words)
print(word_counts.most_common(50))
```

## When You're Done

Commit progress: `git add memos/analysis-memo.md output/figures/ && git commit -m "text-analyst: Phase 1 complete"`

Return a summary to the orchestrator that includes:
1. Corpus size (documents, tokens, vocabulary)
2. Any data quality issues found and how addressed
3. Key preprocessing decisions and rationale
4. Preliminary observations about corpus content
5. Any concerns for the user to consider

**Do not proceed to Phase 2 until the user confirms preprocessing decisions.**
