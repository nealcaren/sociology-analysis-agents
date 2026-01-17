# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Purpose

This repository provides Claude Code skills (agents) for rigorous research analysis. Each skill guides users through a structured, phased workflow with pauses for user input at each stage.

## Available Skills

| Skill | Purpose | Invocation |
|-------|---------|------------|
| **R Analyst** | Statistical analysis in R for publication | `/r-analyst` |
| **Stata Analyst** | Statistical analysis in Stata for publication | `/stata-analyst` |
| **Interview Analyst** | Qualitative analysis of interview data | `/interview-analyst` |

## Unified Phased Architecture

All three skills follow the same phased structure with pauses between phases:

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

## Folder Structure

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
├── r-statistical-techniques/    # R method reference guides
│
├── stata-analyst.md             # Stata orchestrator
├── stata-phases/                # Stata phase agents
│   ├── phase0-design.md
│   ├── phase1-data.md
│   ├── phase2-specification.md
│   ├── phase3-analysis.md
│   ├── phase4-robustness.md
│   └── phase5-output.md
├── stata-statistical-techniques/ # Stata method reference guides
│
├── interview-analyst.md         # Interview orchestrator
└── interview-phases/            # Interview phase agents
    ├── phase0-theory.md
    ├── phase1-immersion.md
    ├── phase2-coding.md
    ├── phase3-interpretation.md
    ├── phase4-quality.md
    └── phase5-synthesis.md
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

## Invoking Phase Agents

Each phase is executed by a sub-agent using the Task tool:

```
Task: Phase 1 Data Familiarization
subagent_type: general-purpose
model: sonnet  # or opus for interpretation phases
prompt: Read [skill]-phases/phase1-[name].md and execute for [user's project]
```

### Model Recommendations

| Phase Type | Model | Examples |
|------------|-------|----------|
| Data processing, coding | **Sonnet** | Phases 0-1 (data), Phase 2-3 (coding) |
| Design, interpretation, writing | **Opus** | Phase 0 (design), Phases 3-5 (interpretation, synthesis) |

## Development Conventions

### Adding New Skills

1. Create `[skill-name]-analyst.md` orchestrator with phased structure
2. Create `[skill-name]-phases/` directory with phase agent files
3. Optionally create `[skill-name]-techniques/` for reference guides
4. Follow the pause-between-phases pattern

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
