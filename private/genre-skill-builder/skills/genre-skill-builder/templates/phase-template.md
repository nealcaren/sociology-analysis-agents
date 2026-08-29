# Phase File Template

Use this template when generating phase files for a new writing skill. Adapt structure based on the phase's purpose.

---

```markdown
# Phase {{N}}: {{Phase Name}}

You are executing Phase {{N}} of {{skill_name}}. Your goal is to {{goal statement}}.

## Why This Phase Matters

{{1-2 sentences explaining the purpose of this phase in the overall workflow}}

## Inputs

Before starting, {{read/gather}}:
1. {{Input 1 with path}}
2. {{Input 2 with path}}
3. {{Input 3 with path}}

## Your Tasks

### 1. {{Task 1 Name}}

{{Description of what to do}}

{{#if has_example}}
**Example**:
```markdown
{{example content}}
```
{{/if}}

{{#if has_checklist}}
**Checklist**:
- [ ] {{Item 1}}
- [ ] {{Item 2}}
- [ ] {{Item 3}}
{{/if}}

### 2. {{Task 2 Name}}

{{Description of what to do}}

{{#if has_subtasks}}
**Sub-tasks**:
- {{Sub-task a}}
- {{Sub-task b}}
- {{Sub-task c}}
{{/if}}

### 3. {{Task 3 Name}}

{{Description of what to do}}

{{#if needs_cluster_handling}}
**Cluster-specific considerations**:
- **{{Cluster 1}}**: {{special handling}}
- **{{Cluster 2}}**: {{special handling}}
- **{{Cluster 3}}**: {{special handling}}
{{/if}}

### 4. {{Task 4 Name}} (if applicable)

{{Description}}

## Output Files to Create

Save all outputs to `{{output_path}}/`:

1. **{{file1.md}}** - {{description}}
   {{#if has_structure_example}}
   ```markdown
   ## {{Section}}
   {{content structure}}
   ```
   {{/if}}

2. **{{file2.md}}** - {{description}}

3. **{{file3.md}}** - {{description}}

## Guiding Principles

1. **{{Principle 1 name}}**: {{Principle 1 description}}

2. **{{Principle 2 name}}**: {{Principle 2 description}}

3. **{{Principle 3 name}}**: {{Principle 3 description}}

4. **{{Principle 4 name}}**: {{Principle 4 description}}

## {{Section-specific guidance}} (if applicable)

{{Additional guidance relevant to the section type being written}}

## When You're Done

Return a summary to the orchestrator that includes:
1. {{Summary item 1}}
2. {{Summary item 2}}
3. {{Summary item 3}}
4. {{Summary item 4}}
5. Questions for the user about {{topic}}
6. Recommendation to proceed to Phase {{N+1}}
```

---

## Phase Type Templates

### Assessment Phase (Phase 0)

For phases that identify cluster and confirm scope:

**Key tasks**:
- Review user inputs (theory section, findings, etc.)
- Apply decision tree to identify cluster
- Confirm cluster with user
- Note any special considerations

**Key outputs**:
- Cluster identification memo
- Scope confirmation

### Drafting Phase (Phase 1 or 2)

For phases that produce written content:

**Key tasks**:
- Apply cluster-specific guidance
- Follow structural template for section type
- Incorporate benchmarks (word count, paragraph count)
- Use appropriate rhetorical moves

**Key outputs**:
- Draft of section
- Notes on choices made

### Revision/Coherence Phase (Phase 2 or 3)

For phases that review and refine:

**Key tasks**:
- Check against benchmarks
- Verify coherence (with other sections, with cluster norms)
- Identify gaps or issues
- Polish prose

**Key outputs**:
- Revised draft
- Revision memo
- Quality checklist

---

## Variables Reference

| Variable | Source | Example |
|----------|--------|---------|
| `{{N}}` | Phase number | "1" |
| `{{Phase Name}}` | Descriptive name | "Introduction Drafting" |
| `{{skill_name}}` | From SKILL.md | "interview-bookends" |
| `{{goal statement}}` | Phase purpose | "write an introduction that opens the circuit effectively" |
| `{{output_path}}` | Where files go | `/drafts/` or user-specified |
