# Phase 4: Skill Generation

You are executing Phase 4 of the genre-skill-builder workflow. Your goal is to generate all the files for the new skill—transforming your analysis findings into a functional plugin.

## Why This Phase Matters

This is where analysis becomes product. The cluster profiles, benchmarks, and exemplars from Phases 1-3 now become actionable writing guidance. Template-based generation ensures the new skill follows repository conventions.

## Inputs

Before starting, read:
1. `/analysis/phase0-scope/scope-definition.md` - Skill name, description, target section
2. `/analysis/phase0-scope/model-skill-summary.md` - Model skill structure
3. `/analysis/phase3-clusters/cluster-profiles.md` - Final cluster definitions
4. `/analysis/phase3-clusters/cluster-benchmarks.json` - Quantitative data
5. `/analysis/phase3-clusters/decision-tree.md` - Cluster identification guide
6. Template files in this skill's `templates/` folder

## Your Tasks

### 1. Create Directory Structure

Set up the output skill directory:

```
output/plugins/[skill-name]/
├── plugin.json
└── skills/[skill-name]/
    ├── SKILL.md
    ├── phases/
    │   ├── phase0-[name].md
    │   ├── phase1-[name].md
    │   ├── phase2-[name].md
    │   └── phase3-[name].md (optional)
    ├── clusters/
    │   ├── [cluster-1].md
    │   ├── [cluster-2].md
    │   └── ...
    └── techniques/
        ├── [technique-1].md
        ├── [technique-2].md
        └── ...
```

### 2. Generate plugin.json

Use scope definition data:

```json
{
  "name": "[skill-name]",
  "version": "1.0.0",
  "description": "[Description from Phase 0]",
  "skills": "./skills/"
}
```

### 3. Generate SKILL.md

Apply the skill template with your findings:

**Required sections**:
- YAML frontmatter (name, description)
- Introduction (what the skill does)
- When to use (prerequisites, inputs needed)
- Connection to other skills (if applicable)
- Core principles (from genre analysis)
- Key statistics/benchmarks (from Phase 1-2)
- The cluster system (brief overview)
- Workflow phases (from model skill, adapted)
- Cluster decision tree (from Phase 3)
- Technique guides (list)
- Invoking phase agents (Task tool instructions)
- Model recommendations (Sonnet/Opus per phase)
- Starting the process (initial user questions)
- Key reminders (genre-specific guidance)

**Use template placeholders**:
```markdown
---
name: {{skill_name}}
description: {{description}}
---

# {{Skill Title}}

You help {{target_audience}} write **{{target_section}}** for {{article_type}}. Your guidance is grounded in systematic analysis of {{corpus_size}} articles from {{venues}}.

## Core Principles (from Genre Analysis)

Based on analysis of {{corpus_size}} {{section_type}} sections:

### 1. {{Principle 1 Name}}
{{Principle 1 content—derived from your findings}}

### 2. {{Principle 2 Name}}
{{Principle 2 content}}

[Continue with 3-5 principles...]

## Key Statistics

| Metric | Median | Target Range (IQR) |
|--------|--------|-------------------|
| Word count | {{median_words}} | {{word_iqr}} |
| Paragraphs | {{median_paras}} | {{para_iqr}} |
| [other metrics...] | ... | ... |

## The {{n}} Clusters

{{section_type}} cluster into {{n}} recognizable styles:

| Cluster | Prevalence | Key Feature |
|---------|------------|-------------|
| **{{Cluster 1}}** | {{%}} | {{key feature}} |
| **{{Cluster 2}}** | {{%}} | {{key feature}} |
[Continue...]

See `clusters/` directory for detailed profiles.

[Continue with remaining sections...]
```

### 4. Generate Phase Files

Create 3-4 phase files based on section type:

**For Introduction/Conclusion skills** (like interview-bookends):
- Phase 0: Intake & Assessment (identify cluster)
- Phase 1: Drafting (write the section)
- Phase 2: Coherence Check (verify alignment)

**For Theory/Methods skills** (like lit-writeup):
- Phase 0: Assessment (identify cluster, contribution type)
- Phase 1: Architecture (plan structure)
- Phase 2: Drafting (write paragraphs)
- Phase 3: Revision (calibrate to norms)

**Each phase file must include**:
- Goal statement
- Process steps (numbered)
- Input requirements
- Output files
- Guiding principles
- When You're Done (summary for orchestrator)

### 5. Generate Cluster Profiles

Create one file per cluster in `clusters/`:

Use the cluster template:

```markdown
# Cluster: {{Cluster Name}}

**Prevalence**: {{%}} of corpus

**Contribution logic**: "{{One-sentence description of what articles in this cluster do}}"

---

## Identifying {{Cluster Name}} Articles

Your article is {{Cluster Name}} if:
- {{Criterion 1}}
- {{Criterion 2}}
- {{Criterion 3}}

---

## Key Statistics

| Feature | Typical Value |
|---------|---------------|
| Word count | {{range}} |
| Paragraphs | {{range}} |
| {{Feature 3}} | {{value}} |
| {{Feature 4}} | {{value}} |

---

## Signature Moves (Do This)

### 1. {{Move 1}}
{{Description}}
> "{{Example quote from corpus}}"

### 2. {{Move 2}}
{{Description}}
> "{{Example quote}}"

### 3. {{Move 3}}
{{Description}}

---

## Prohibited Moves (Don't Do This)

- **{{Move 1}}**: {{Why to avoid}}
- **{{Move 2}}**: {{Why to avoid}}

---

## Exemplar

**{{Article identifier}}**

- **Key features**: {{What makes this exemplary}}
- **Notable techniques**: {{Specific craft elements}}

---

## Writing Checklist

- [ ] {{Checkpoint 1}}
- [ ] {{Checkpoint 2}}
- [ ] {{Checkpoint 3}}
- [ ] {{Checkpoint 4}}
```

### 6. Generate Technique Guides

Create 2-4 technique guides based on section type:

**Common technique guides**:
- `opening-moves.md` - Types of openings with examples
- `sentence-toolbox.md` - Sentence-level patterns (if applicable)
- `[section-specific].md` - Techniques specific to this section type

Use the technique template:

```markdown
# {{Technique Guide Title}}

{{Brief description of what this guide covers}}

---

## {{Category 1}}

### {{Type 1.1}}
**When to use**: {{context}}
**Signature patterns**:
- {{pattern}}
- {{pattern}}

**Examples from corpus**:
> "{{quote}}"
> "{{quote}}"

### {{Type 1.2}}
[Continue...]

---

## {{Category 2}}

[Continue with categories...]

---

## Quick Reference

| {{Column 1}} | {{Column 2}} | {{Column 3}} |
|--------------|--------------|--------------|
| {{data}} | {{data}} | {{data}} |
```

### 7. Prepare Marketplace Entry

Draft the entry for `.claude-plugin/marketplace.json`:

```json
{
  "name": "{{skill-name}}",
  "source": "./plugins/{{skill-name}}",
  "description": "{{Full description}}",
  "version": "1.0.0",
  "author": {
    "name": "{{Author Name}}"
  },
  "license": "MIT",
  "keywords": [
    "{{keyword1}}",
    "{{keyword2}}",
    "{{keyword3}}"
  ],
  "strict": true
}
```

### 8. Update CLAUDE.md Documentation

Draft additions to CLAUDE.md:
- Add to plugin installation command list
- Add to Available Skills table
- Add phase table if workflow differs from existing

## Output Files to Create

Save all outputs to `/output/plugins/[skill-name]/`:

1. **plugin.json** - Plugin metadata

2. **skills/[skill-name]/SKILL.md** - Main skill file

3. **skills/[skill-name]/phases/** - Phase files:
   - `phase0-[name].md`
   - `phase1-[name].md`
   - `phase2-[name].md`
   - `phase3-[name].md` (if applicable)

4. **skills/[skill-name]/clusters/** - Cluster profiles:
   - `[cluster-1-slug].md`
   - `[cluster-2-slug].md`
   - etc.

5. **skills/[skill-name]/techniques/** - Technique guides:
   - `opening-moves.md`
   - `[other-techniques].md`

Also save to `/analysis/phase4-generation/`:

6. **marketplace-entry.json** - Ready-to-add marketplace entry

7. **claudemd-additions.md** - Documentation updates for CLAUDE.md

8. **generation-log.md** - Record of what was generated and any decisions made

## Quality Checks

Before finishing, verify:

- [ ] All files use consistent skill name
- [ ] Benchmarks match Phase 1-2 data
- [ ] Cluster names match Phase 3 definitions
- [ ] Phase files follow repository conventions
- [ ] Technique guides have corpus examples (not invented ones)
- [ ] Decision tree matches cluster definitions
- [ ] Model recommendations are appropriate
- [ ] YAML frontmatter is valid
- [ ] JSON files are valid

## Guiding Principles

1. **Templates constrain**: Follow the template structure; don't invent novel formats.

2. **Data drives content**: Every benchmark, percentage, and example should trace to analysis.

3. **Consistency over creativity**: Match existing skill conventions for user familiarity.

4. **Examples from corpus**: Use real quotes from analyzed articles, not invented examples.

5. **Appropriate scope**: Generate what the model skill has; don't add extra components.

## When You're Done

Return a summary to the orchestrator that includes:
1. Files generated (complete list)
2. Skill structure (number of phases, clusters, techniques)
3. Key benchmarks included
4. Any adaptation decisions (where you deviated from model skill)
5. Files ready for review (SKILL.md, cluster profiles)
6. Marketplace entry ready
7. CLAUDE.md updates drafted
8. Recommendation to proceed to Phase 5 (validation)
