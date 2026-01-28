# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Purpose

This repository provides a Claude Code plugin marketplace with skills (agents) for rigorous social science research analysis. Each skill guides users through a structured, phased workflow with pauses for user input at each stage.

## Installation

Users can install this plugin marketplace and individual plugins with:

```bash
# Add the marketplace
/plugin marketplace add nealcaren/social-data-analysis

# Install only the plugins you need
/plugin install r-analyst@social-data-analysis
/plugin install stata-analyst@social-data-analysis
/plugin install interview-analyst@social-data-analysis
/plugin install interview-writeup@social-data-analysis
/plugin install dag-development@social-data-analysis
/plugin install abductive-analyst@social-data-analysis
/plugin install text-analyst@social-data-analysis
/plugin install lecture-designer@social-data-analysis
/plugin install lit-review@social-data-analysis
```

## Available Skills

After installation, invoke skills with:

| Skill | Purpose | Invocation |
|-------|---------|------------|
| **R Analyst** | Statistical analysis in R for publication | `/r-analyst` |
| **Stata Analyst** | Statistical analysis in Stata for publication | `/stata-analyst` |
| **Interview Analyst** | Qualitative analysis of interview data | `/interview-analyst` |
| **Interview Write-Up** | Write-up support for interview methods and findings | `/interview-writeup` |
| **DAG Development** | Develop causal diagrams and render publication-ready figures | `/dag-development` |
| **Abductive Analyst** | Abductive analysis (Timmermans & Tavory) | `/abductive-analyst` |
| **Text Analyst** | Computational text analysis (R/Python) | `/text-analyst` |
| **Lecture Designer** | Transform chapters into engaging lectures | `/lecture-designer` |
| **Lit Review** | Build literature databases via OpenAlex | `/lit-review` |

## Unified Phased Architecture

All skills follow the same phased structure with pauses between phases:

### Statistical Analysis (R & Stata)

| Phase | Goal | Pause Point |
|-------|------|-------------|
| **0: Research Design** | Establish identification strategy | User confirms design |
| **1: Data Familiarization** | Understand data before modeling | User reviews descriptives |
| **2: Model Specification** | Fully specify before estimation | User approves specification |
| **3: Main Analysis** | Run primary models | User reviews results |
| **4: Robustness** | Stress-test findings | User assesses robustness |
| **5: Output** | Publication-ready outputs | Analysis complete |

### Interview Analysis

| Phase | Goal | Pause Point |
|-------|------|-------------|
| **0: Theory Synthesis** | Build theoretical sensitivity (Track A only) | User confirms framework |
| **1: Immersion** | Deep familiarity with data | User reviews observations |
| **2: Coding** | Systematic categorization | User reviews coding structure |
| **3: Interpretation** | Move from "what" to "why" | User reviews explanations |
| **4: Quality Check** | Evaluate against quality indicators | User addresses gaps |
| **5: Synthesis** | Integrate into coherent argument | Analysis complete |

### Abductive Analysis (Timmermans & Tavory)

| Phase | Goal | Pause Point |
|-------|------|-------------|
| **0: Theoretical Preparation** | Build theoretical sensitivity | User confirms theoretical map |
| **1: Familiarization** | Open coding, flag surprises | User reviews initial codes |
| **2: Theoretical Casing** | Apply multiple lenses to excerpts | User reviews casings |
| **3: Anomaly Analysis** | Identify contradictions and puzzles | User confirms focus |
| **4: Memo Writing** | Develop tentative theory | User tests interpretations |
| **5: Integration** | Test against full dataset | User reviews synthesis |
| **6: Writing Up** | Rhetorical abduction for publication | Analysis complete |

### Text Analysis (R/Python)

| Phase | Goal | Pause Point |
|-------|------|-------------|
| **0: Research Design** | Method selection, language choice | User confirms design |
| **1: Corpus Preparation** | Load, clean, explore text | User reviews preprocessing |
| **2: Specification** | Document preprocessing, parameters | User approves specification |
| **3: Analysis** | Run topic models, classifiers, etc. | User reviews results |
| **4: Validation** | Human validation, diagnostics | User assesses validity |
| **5: Output** | Publication-ready outputs | Analysis complete |

### Lecture Design

| Phase | Goal | Pause Point |
|-------|------|-------------|
| **0: Context & Outcomes** | Define measurable learning outcomes | Instructor confirms outcomes |
| **1: Content Audit & Narrative** | ABT arc, hook, chunk map | Instructor reviews narrative |
| **2: Active Learning** | Polls, ConcepTests, peer instruction | Instructor reviews activities |
| **3: Slide Development** | Google Slides via MCP with speaker notes | Instructor reviews slides |
| **4: Review & Refinement** | Timing audit, backup plans | Lecture package complete |

> **Note**: Lecture Designer requires the [Google Docs MCP](https://github.com/nealcaren/google-docs-mcp) to create slides directly in Google Slides.

### Literature Review (OpenAlex)

| Phase | Goal | Pause Point |
|-------|------|-------------|
| **0: Scope Definition** | Define topic, search terms, criteria | User confirms search strategy |
| **1: Initial Search** | Query OpenAlex, build corpus | User reviews corpus composition |
| **2: Screening** | Filter with LLM assistance | User reviews borderline cases |
| **3: Snowballing** | Expand via citation networks | User approves additions |
| **4: Full Text** | Identify OA sources, download checklist | User obtains missing PDFs |
| **5: Annotation** | Extract structured information | User reviews extractions |
| **6: Synthesis** | Generate database, identify gaps | Database complete |

## Repository Structure

```
.claude-plugin/
└── marketplace.json          # Plugin marketplace definition (9 plugins)

plugins/
├── r-analyst/
│   └── skills/r-analyst/
│       ├── SKILL.md          # Main R analyst skill
│       ├── phases/           # Phase agent files
│       └── techniques/       # R method reference guides
│
├── stata-analyst/
│   └── skills/stata-analyst/
│       ├── SKILL.md          # Main Stata analyst skill
│       ├── phases/           # Phase agent files
│       └── techniques/       # Stata method reference guides
│
├── interview-analyst/
│   └── skills/interview-analyst/
│       ├── SKILL.md          # Main interview analyst skill
│       └── phases/           # Phase agent files
│
├── interview-writeup/
│   └── skills/interview-writeup/
│       ├── SKILL.md          # Main interview write-up skill
│       └── phases/           # Phase agent files
│
├── dag-development/
│   └── skills/dag-development/
│       ├── SKILL.md          # Main DAG development skill
│       └── phases/           # Phase agent files
│
├── abductive-analyst/
│   └── skills/abductive-analyst/
│       ├── SKILL.md          # Main abductive analyst skill
│       └── phases/           # Phase agent files (7 phases)
│
├── text-analyst/
│   └── skills/text-analyst/
│       ├── SKILL.md          # Main text analyst skill
│       ├── phases/           # Phase agent files
│       ├── concepts/         # Method concepts (language-agnostic)
│       ├── r-techniques/     # R implementation guides
│       └── python-techniques/ # Python implementation guides
│
├── lecture-designer/
│   └── skills/lecture-designer/
│       ├── SKILL.md          # Main lecture designer skill
│       ├── phases/           # Phase agent files
│       ├── pedagogy/         # Teaching methodology guides
│       ├── mcp/              # Google Docs MCP setup guides
│       └── quarto/           # Quarto reveal.js (alternative)
│
└── lit-review/
    └── skills/lit-review/
        ├── SKILL.md          # Main literature review skill
        ├── phases/           # Phase agent files (7 phases)
        └── api/              # OpenAlex API reference
```

## Key Commands

### Running R Analysis

```bash
Rscript filename.R
which R || which Rscript
Rscript -e "sessionInfo()"
```

### Running Stata Analysis

```bash
stata -e do filename.do
# macOS: /Applications/Stata/StataMP.app/Contents/MacOS/StataMP -e do filename.do
which stata || which StataMP || which StataSE
```

### Running Python for Text Analysis

```bash
python script.py
python -c "import sklearn; print(sklearn.__version__)"
pip install gensim sentence-transformers bertopic
```

## Invoking Phase Agents

Each phase is executed by a sub-agent using the Task tool:

```
Task: Phase 1 Data Familiarization
subagent_type: general-purpose
model: sonnet  # or opus for interpretation phases
prompt: Read phases/phase1-data.md and execute for [user's project]
```

### Model Recommendations

| Phase Type | Model | Examples |
|------------|-------|----------|
| Data processing, coding | **Sonnet** | Phases 0-1 (data), Phase 2-3 (coding) |
| Design, interpretation, writing | **Opus** | Phase 0 (design), Phases 3-5 (interpretation, synthesis) |

## Development Conventions

### Adding New Plugins

1. Create `plugins/[plugin-name]/skills/[skill-name]/SKILL.md` with YAML frontmatter
2. Create `phases/` directory with phase agent files
3. Optionally create `techniques/` for reference guides
4. Add plugin entry to `.claude-plugin/marketplace.json`
5. Follow the pause-between-phases pattern

### SKILL.md Format

```yaml
---
name: skill-name
description: Brief description shown in skill listings
---

# Skill Title

[Skill content...]
```

### Phase Agent Structure

Each phase agent should include:
- **Why This Phase Matters**: Conceptual justification
- **Your Tasks**: Numbered steps with code examples
- **Output Files to Create**: Specific deliverables
- **Guiding Principles**: Key reminders
- **When You're Done**: Summary for orchestrator

### Core Principles Across All Skills

1. **Pauses are mandatory**: Never auto-proceed between phases
2. **User expertise**: The user knows their domain; we provide methodological support
3. **Show, don't tell**: Ground claims in concrete evidence
4. **Variation is data**: Differences and negative cases are analytically valuable
5. **Reproducibility**: Document decisions, use seeds, save intermediate outputs
