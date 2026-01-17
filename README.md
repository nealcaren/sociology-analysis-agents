# Sociology Analysis Agents for Claude Code

A Claude Code plugin marketplace with skills for rigorous quantitative and qualitative analysis in sociology and related social sciences. These skills guide you through systematic, publication-ready research workflows.

## Installation

```bash
# Add this marketplace to Claude Code
/plugin marketplace add nealcaren/sociology-analysis-agents

# Install the sociology-analysis plugin
/plugin install sociology-analysis@sociology-analysis
```

## Available Skills

After installation, invoke any skill:

| Skill | Invocation | Description |
|-------|------------|-------------|
| **R Statistical Analyst** | `/r-analyst` | Phased quantitative analysis workflow using R (DiD, IV, matching, etc.) |
| **Stata Statistical Analyst** | `/stata-analyst` | Phased quantitative analysis workflow using Stata |
| **Interview Analyst** | `/interview-analyst` | Pragmatic qualitative analysis for interview data |
| **Abductive Analyst** | `/abductive-analyst` | Abductive analysis (Timmermans & Tavory) for theory-generating qualitative research |
| **Text Analyst** | `/text-analyst` | Computational text analysis with R and Python (topic models, sentiment, classification) |

Each skill uses a **phased workflow** with mandatory pauses between phases for user review and decision-making.

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
Phase 5: Synthesis → Write publication-ready sections
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

## Repository Structure

```
.claude-plugin/
└── marketplace.json              # Plugin marketplace definition

plugins/sociology-analysis/
└── skills/
    ├── r-analyst/
    │   ├── SKILL.md              # R orchestrator
    │   ├── phases/               # Phase agents
    │   └── techniques/           # R code reference guides
    │
    ├── stata-analyst/
    │   ├── SKILL.md              # Stata orchestrator
    │   ├── phases/               # Phase agents
    │   └── techniques/           # Stata code reference guides
    │
    ├── interview-analyst/
    │   ├── SKILL.md              # Interview orchestrator
    │   └── phases/               # Phase agents
    │
    ├── abductive-analyst/
    │   ├── SKILL.md              # Abductive analysis orchestrator
    │   └── phases/               # Phase agents (7 phases)
    │
    └── text-analyst/
        ├── SKILL.md              # Text analysis orchestrator
        ├── phases/               # Phase agents
        ├── concepts/             # Method concepts (language-agnostic)
        ├── r-techniques/         # R text analysis code guides
        └── python-techniques/    # Python text analysis code guides
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
- **Methods transparency**: Detailed templates for sampling, recruitment, saturation

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
