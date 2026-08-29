# Sociology Analysis Agents for Claude Code

A Claude Code plugin marketplace with skills for rigorous quantitative and qualitative analysis in sociology and related social sciences. These skills guide you through systematic, publication-ready research workflows, each with mandatory pauses between phases for user review.

## Installation

```bash
# Add this marketplace to Claude Code
/plugin marketplace add nealcaren/social-data-analysis

# Install only the plugins you need
/plugin install r-analyst@social-data-analysis
/plugin install stata-analyst@social-data-analysis
/plugin install interview-analyst@social-data-analysis
/plugin install abductive-analyst@social-data-analysis
/plugin install text-analyst@social-data-analysis
/plugin install dag-development@social-data-analysis
/plugin install lit-search@social-data-analysis
```

## Available Plugins

Each plugin provides a single focused **analysis** skill. Install only what you need:

| Skill | Invocation | Description |
|-------|------------|-------------|
| **R Statistical Analyst** | `/r-analyst` | Phased quantitative analysis workflow using R (DiD, IV, matching, etc.) |
| **Stata Statistical Analyst** | `/stata-analyst` | Phased quantitative analysis workflow using Stata |
| **Interview Analyst** | `/interview-analyst` | Pragmatic qualitative analysis for interview data |
| **Abductive Analyst** | `/abductive-analyst` | Abductive analysis (Timmermans & Tavory) for theory-generating qualitative research |
| **Text Analyst** | `/text-analyst` | Computational text analysis with R and Python (topic models, sentiment, classification) |
| **DAG Development** | `/dag-development` | Develop causal diagrams and render publication-ready figures (Mermaid, R, Python) |
| **Lit Search** | `/lit-search` | Build systematic literature databases via OpenAlex |

Each skill uses a **phased workflow** with mandatory pauses between phases for user review and decision-making.

> **Scope**: This marketplace publishes *analysis* skills only. Writing and manuscript-drafting skills (theory sections, methods write-ups, introductions/conclusions, revision coordination, etc.) are maintained separately in the [`sociology-skillset`](https://github.com/nealcaren/sociology-skillset) marketplace.

## Workflow Overview

### Quantitative Analysis (R/Stata)

```
Phase 0: Research Design → Establish identification strategy
    ↓ [User Review]
Phase 1: Data Familiarization → Descriptives, quality checks
    ↓ [User Review]
Phase 2: Model Specification → Pre-specify models before estimation
    ↓ [User Review]
Phase 3: Main Analysis → Run models, interpret results
    ↓ [User Review]
Phase 4: Robustness → Sensitivity analysis, placebo tests
    ↓ [User Review]
Phase 5: Output → Publication-ready tables, figures, narrative
```

### Qualitative Analysis (Interviews)

```
Phase 0: Theory Preparation → Sensitizing concepts (optional)
    ↓ [User Review]
Phase 1: Immersion → Read transcripts, create memos
    ↓ [User Review]
Phase 2: Coding → Develop codebook, apply codes
    ↓ [User Review]
Phase 3: Interpretation → Identify patterns, develop explanations
    ↓ [User Review]
Phase 4: Quality Check → Assess against 5 quality indicators
    ↓ [User Review]
Phase 5: Synthesis → Integrate into a coherent argument
    ↓ [User Review]
Phase 6: Methods → Draft a methods section from analytic decisions
```

### Abductive Analysis (Timmermans & Tavory)

```
Phase 0: Theoretical Preparation → Build theoretical sensitivity
    ↓ [User Review]
Phase 1: Familiarization → Open coding, flag surprises
    ↓ [User Review]
Phase 2: Theoretical Casing → Apply multiple theoretical lenses
    ↓ [User Review]
Phase 3: Anomaly Analysis → Identify contradictions and puzzles
    ↓ [User Review]
Phase 4: Memo Writing → Develop tentative theory
    ↓ [User Review]
Phase 5: Integration → Test theory against full dataset
    ↓ [User Review]
Phase 6: Writing Up → Rhetorical abduction for publication
```

### Computational Text Analysis (R/Python)

```
Phase 0: Research Design → Method selection, language choice (R or Python)
    ↓ [User Review]
Phase 1: Corpus Preparation → Load, clean, explore text data
    ↓ [User Review]
Phase 2: Specification → Document preprocessing, specify parameters
    ↓ [User Review]
Phase 3: Analysis → Run topic models, classifiers, sentiment
    ↓ [User Review]
Phase 4: Validation → Human validation, diagnostics, robustness
    ↓ [User Review]
Phase 5: Output → Publication-ready tables, figures, replication
```

### Literature Search (OpenAlex)

```
Phase 0: Scope Definition → Topic, search terms, criteria
    ↓ [User Review]
Phase 1: Initial Search → Query OpenAlex, build corpus
    ↓ [User Review]
Phase 2: Screening → Filter with LLM assistance
    ↓ [User Review]
Phase 3: Snowballing → Expand via citation networks
    ↓ [User Review]
Phase 4: Full Text → Identify OA sources, download checklist
    ↓ [User Review]
Phase 5: Annotation → Extract structured information
    ↓ [User Review]
Phase 6: Synthesis → Generate database, identify gaps
```

## Repository Structure

```
.claude-plugin/
└── marketplace.json              # Plugin marketplace definition (7 plugins)

plugins/
├── r-analyst/
│   └── skills/r-analyst/
│       ├── SKILL.md              # R orchestrator
│       ├── phases/               # Phase agents
│       └── techniques/           # R code reference guides
│
├── stata-analyst/
│   └── skills/stata-analyst/
│       ├── SKILL.md              # Stata orchestrator
│       ├── phases/               # Phase agents
│       └── techniques/           # Stata code reference guides
│
├── interview-analyst/
│   └── skills/interview-analyst/
│       ├── SKILL.md              # Interview orchestrator
│       └── phases/               # Phase agents
│
├── abductive-analyst/
│   └── skills/abductive-analyst/
│       ├── SKILL.md              # Abductive analysis orchestrator
│       └── phases/               # Phase agents (7 phases)
│
├── text-analyst/
│   └── skills/text-analyst/
│       ├── SKILL.md              # Text analysis orchestrator
│       ├── phases/               # Phase agents
│       ├── concepts/             # Method concepts (language-agnostic)
│       ├── r-techniques/         # R text analysis code guides
│       └── python-techniques/    # Python text analysis code guides
│
├── dag-development/
│   └── skills/dag-development/
│       ├── SKILL.md              # DAG development orchestrator
│       └── phases/               # Phase agents
│
└── lit-search/
    └── skills/lit-search/
        ├── SKILL.md              # Literature search orchestrator
        ├── phases/               # Phase agents
        └── api/                  # OpenAlex API reference

private/                          # Writing/drafting skills, not published to the marketplace
```

## Key Features

### Quantitative Skills
- **Identification-first**: Establish research design before estimation
- **Pre-specification**: Document model choices before seeing results
- **Robustness built-in**: Sensitivity analysis, placebo tests, wild bootstrap
- **Nonlinear model interpretation**: AMEs, predicted probabilities, proper diagnostics
- **Missing data handling**: Multiple imputation with adequate m
- **Survey methodology**: Weighting, design effects, response rates
- **Publication checklists**: Minimum, strong, and exemplary standards

### Qualitative Skills
- **Theory-informed or data-first**: Choose your approach
- **Systematic coding**: Codebook development with examples
- **Quality indicators**: Cognitive empathy, heterogeneity, palpability, follow-up, self-awareness
- **Evidence selection**: Luminous exemplars, not just typical quotes

### Abductive Analysis Skills
- **Theory-first approach**: Build theoretical sensitivity before data engagement
- **Map and compass theories**: Both substantive and grammatical frameworks
- **Anomaly detection**: Systematic identification of contradictions and puzzles
- **Theoretical casing**: View data through multiple theoretical lenses
- **Rhetorical abduction**: Structure writing as what we knew → surprise → new theory

### Text Analysis Skills
- **Dual-language support**: R for topic models/STM; Python for transformers/BERTopic
- **Method selection guidance**: Match methods to research questions
- **Validation required**: Human validation, coherence metrics, robustness checks
- **Topic modeling**: LDA, STM (R), BERTopic (Python) with K selection guidance
- **Sentiment analysis**: VADER, lexicon-based, and ML approaches
- **Supervised classification**: Traditional ML and transformer fine-tuning
- **Reproducibility**: Documented preprocessing, seeds, package versions

### Methods Skills
- **DAG development**: Build causal diagrams from theory and render figures in Mermaid, R, or Python

### Literature Search Skills
- **OpenAlex-powered**: Systematic search, screening, and snowballing
- **Structured annotation**: Extract consistent information across a corpus
- **Database output**: Reusable literature database with gap identification

## Requirements

- [Claude Code CLI](https://claude.ai/code)
- R (for R skills) or Stata (for Stata skills)
- Interview transcripts (for interview skill)
- R and/or Python (for text analysis skill)

## Contributing

Contributions welcome! Please:
1. Fork the repo
2. Create a feature branch
3. Submit a pull request

## License

MIT License - see LICENSE file

## Acknowledgments

These skills draw on methodological guidance from:
- Gerson & Damaske, *The Science and Art of Interviewing*
- Small & Calarco, *Qualitative Literacy*
- Long & Mustillo (2017), Mize (2019) on nonlinear model interpretation
- Various *Social Forces* editorial guidelines
