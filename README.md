# Sociology Analysis Agents for Claude Code

A collection of Claude Code skills for rigorous quantitative and qualitative analysis in sociology and related social sciences. These skills guide you through systematic, publication-ready research workflows.

## Available Skills

| Skill | Description |
|-------|-------------|
| **R Statistical Analyst** | Phased quantitative analysis workflow using R (DiD, IV, matching, etc.) |
| **Stata Statistical Analyst** | Phased quantitative analysis workflow using Stata |
| **Interview Analyst** | Pragmatic qualitative analysis for interview data |

Each skill uses a **phased workflow** with mandatory pauses between phases for user review and decision-making.

## Installation

### Option 1: Add as a skill directory (Recommended)

1. Clone this repo:
   ```bash
   git clone https://github.com/YOUR_USERNAME/sociology-analysis-agents.git
   ```

2. Add the skills to your Claude Code configuration. Edit `~/.claude/settings.json`:
   ```json
   {
     "skills": {
       "sociology": "/path/to/sociology-analysis-agents/skills"
     }
   }
   ```

3. Use in Claude Code:
   ```
   /sociology:r-analyst
   /sociology:stata-analyst
   /sociology:interview-analyst
   ```

### Option 2: Copy to your project

Copy the `skills/` folder into your project directory, then reference in your project's `.claude/settings.json`:
```json
{
  "skills": {
    "local": "./skills"
  }
}
```

### Option 3: Direct file reference

Point Claude Code directly to a skill file:
```
Read skills/r-analyst.md and follow the workflow for my analysis
```

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

## What's Included

```
skills/
├── r-analyst.md                 # R orchestrator
├── r-phases/                    # R phase agents
│   ├── phase0-design.md
│   ├── phase1-data.md
│   ├── phase2-specification.md
│   ├── phase3-analysis.md
│   ├── phase4-robustness.md
│   └── phase5-output.md
├── r-statistical-techniques/    # R code reference guides
│   ├── 01_core_econometrics.md  # DiD, IV, matching, etc.
│   ├── 02_survey_resampling.md
│   ├── 03_text_ml.md
│   ├── 04_synthetic_control.md
│   ├── 05_bayesian_sensitivity.md
│   ├── 06_visualization.md
│   ├── 07_best_practices.md
│   └── 08_nonlinear_models.md
├── stata-analyst.md             # Stata orchestrator
├── stata-phases/                # Stata phase agents
├── stata-statistical-techniques/ # Stata code reference guides
├── interview-analyst.md         # Interview orchestrator
└── interview-phases/            # Interview phase agents
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

## Requirements

- [Claude Code CLI](https://claude.ai/code)
- R (for R skills) or Stata (for Stata skills)
- Interview transcripts (for interview skill)

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
