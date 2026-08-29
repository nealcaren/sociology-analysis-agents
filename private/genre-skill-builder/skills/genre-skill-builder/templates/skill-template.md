# SKILL.md Template

Use this template when generating the main SKILL.md file for a new writing skill. Replace all `{{placeholders}}` with actual values from the analysis.

---

```markdown
---
name: {{skill_name}}
description: {{description}}
---

# {{Skill Title}}

You help {{target_audience}} write **{{target_section}}** for {{article_type}}. Your guidance is grounded in systematic analysis of {{corpus_size}} articles from {{venues}}.

## When to Use This Skill

Use this skill when users want to:
- {{Use case 1}}
- {{Use case 2}}
- {{Use case 3}}

This skill assumes {{prerequisites}}.

## Connection to Other Skills

| Skill | Purpose | Key Output |
|-------|---------|------------|
| **{{Related Skill 1}}** | {{Purpose}} | {{Output}} |
| **{{Related Skill 2}}** | {{Purpose}} | {{Output}} |

## Core Principles (from Genre Analysis)

Based on systematic analysis of {{corpus_size}} {{section_type}} sections:

### 1. {{Principle 1 Name}}
{{Principle 1 description—derived from analysis findings}}

### 2. {{Principle 2 Name}}
{{Principle 2 description}}

### 3. {{Principle 3 Name}}
{{Principle 3 description}}

### 4. {{Principle 4 Name}}
{{Principle 4 description}}

## Key Statistics (Benchmarks)

### {{Section Type}} Benchmarks

| Feature | Typical Value |
|---------|---------------|
| Word count | {{word_range}} |
| Paragraphs | {{para_range}} |
| {{Feature 3}} | {{value}} |
| {{Feature 4}} | {{value}} |
| {{Feature 5}} | {{value}} |

## The {{n}} Clusters

{{Section type}} sections cluster into {{n}} recognizable styles based on {{distinguishing criteria}}:

| Cluster | Prevalence | Key Feature | When to Use |
|---------|------------|-------------|-------------|
| **{{Cluster 1}}** | {{%}} | {{feature}} | {{when}} |
| **{{Cluster 2}}** | {{%}} | {{feature}} | {{when}} |
| **{{Cluster 3}}** | {{%}} | {{feature}} | {{when}} |
{{#if more clusters}}
| **{{Cluster 4}}** | {{%}} | {{feature}} | {{when}} |
| **{{Cluster 5}}** | {{%}} | {{feature}} | {{when}} |
{{/if}}

See `clusters/` directory for detailed profiles with benchmarks, signature moves, and exemplars.

## Workflow Phases

### Phase 0: {{Phase 0 Name}}
**Goal**: {{Phase 0 goal}}

**Process**:
- {{Step 1}}
- {{Step 2}}
- {{Step 3}}

**Output**: {{Phase 0 outputs}}

> **Pause**: {{What user confirms}}

---

### Phase 1: {{Phase 1 Name}}
**Goal**: {{Phase 1 goal}}

**Process**:
- {{Step 1}}
- {{Step 2}}
- {{Step 3}}

**Guides**:
- `phases/phase1-{{name}}.md` (main workflow)
- `clusters/` (cluster-specific guidance)

**Output**: {{Phase 1 outputs}}

> **Pause**: {{What user reviews}}

---

### Phase 2: {{Phase 2 Name}}
**Goal**: {{Phase 2 goal}}

**Process**:
- {{Step 1}}
- {{Step 2}}
- {{Step 3}}

**Guide**: `phases/phase2-{{name}}.md`

**Output**: {{Phase 2 outputs}}

{{#if phase3}}
> **Pause**: {{What user reviews}}

---

### Phase 3: {{Phase 3 Name}}
**Goal**: {{Phase 3 goal}}

**Process**:
- {{Step 1}}
- {{Step 2}}
- {{Step 3}}

**Guide**: `phases/phase3-{{name}}.md`

**Output**: {{Phase 3 outputs}}
{{/if}}

---

## Cluster Decision Tree

To identify which cluster your article inhabits:

1. **{{Question 1}}**
   - {{Answer A}} → likely {{Cluster X}}
   - {{Answer B}} → likely {{Cluster Y}}
   - {{Answer C}} → go to question 2

2. **{{Question 2}}**
   - {{Answer A}} → {{Cluster X}}
   - {{Answer B}} → {{Cluster Y}}

### Quick Indicators

| If you see this... | Consider this cluster... |
|--------------------|--------------------------|
| {{Indicator 1}} | {{Cluster}} |
| {{Indicator 2}} | {{Cluster}} |
| {{Indicator 3}} | {{Cluster}} |

## Cluster Profiles

Reference these guides for cluster-specific writing:

| Guide | Cluster |
|-------|---------|
| `clusters/{{cluster-1-slug}}.md` | {{Cluster 1}} ({{%}}) |
| `clusters/{{cluster-2-slug}}.md` | {{Cluster 2}} ({{%}}) |
| `clusters/{{cluster-3-slug}}.md` | {{Cluster 3}} ({{%}}) |

## Technique Guides

| Guide | Purpose |
|-------|---------|
| `techniques/{{technique-1}}.md` | {{Purpose}} |
| `techniques/{{technique-2}}.md` | {{Purpose}} |
| `techniques/{{technique-3}}.md` | {{Purpose}} |

## Prohibited Moves

### In {{Section Type}}
- {{Prohibited move 1}}
- {{Prohibited move 2}}
- {{Prohibited move 3}}

## Output Expectations

Provide the user with:
- {{Output 1}}
- {{Output 2}}
- {{Output 3}}

## Invoking Phase Agents

Use the Task tool for each phase:

```
Task: Phase 1 {{Phase 1 Name}}
subagent_type: general-purpose
model: {{recommended_model}}
prompt: Read phases/phase1-{{name}}.md and the relevant cluster guide, then {{task description}}. User's {{input type}} is provided.
```

**Model recommendations**:
- Phase 0 ({{name}}): {{Model}}
- Phase 1 ({{name}}): {{Model}}
- Phase 2 ({{name}}): {{Model}}
{{#if phase3}}
- Phase 3 ({{name}}): {{Model}}
{{/if}}

## Starting the Process

When the user is ready to begin:

1. **Ask about the project**:
   > "{{Opening question 1}}"

2. **Ask about inputs**:
   > "{{Opening question 2}}"

3. **Identify cluster**:
   > Based on your answers, apply the decision tree and recommend a cluster.

4. **Proceed with Phase 0**.

## Key Reminders

- {{Reminder 1}}
- {{Reminder 2}}
- {{Reminder 3}}
- {{Reminder 4}}
- {{Reminder 5}}
```

---

## Template Variables Reference

| Variable | Source | Example |
|----------|--------|---------|
| `{{skill_name}}` | Phase 0 user input | `discussion-writer` |
| `{{description}}` | Phase 0 user input | "Write discussion sections for..." |
| `{{target_section}}` | Phase 0 user input | "discussion sections" |
| `{{target_audience}}` | Infer from context | "sociologists" |
| `{{article_type}}` | Phase 0 user input | "qualitative interview articles" |
| `{{corpus_size}}` | Phase 1 data | "80" |
| `{{venues}}` | Phase 0 corpus info | "*Social Problems* and *Social Forces*" |
| `{{Cluster N}}` | Phase 3 names | "Gap-Filler Minimalist" |
| `{{word_range}}` | Phase 1 statistics | "600-950 words" |
| `{{para_range}}` | Phase 1 statistics | "4-8" |
