# Cluster Profile Template

Use this template when generating cluster profile files for a new writing skill. Each cluster gets its own file in the `clusters/` directory.

---

```markdown
# Cluster {{N}}: {{Cluster Name}}

**Prevalence**: {{percentage}}% of corpus ({{rank: most common / second most common / etc.}})

**Contribution logic**: "{{One-sentence description of what articles in this cluster accomplish}}"

---

## Identifying {{Cluster Name}} Articles

Your article is {{Cluster Name}} if:
- {{Primary criterion—must be true}}
- {{Secondary criterion}}
- {{Tertiary criterion}}

**Key indicators**:
- {{Observable feature 1}}
- {{Observable feature 2}}
- {{Observable feature 3}}

---

## {{Section Type}} Signature

### Key Statistics
| Feature | Typical Value |
|---------|---------------|
| Word count | {{range}} ({{comparison to corpus: shortest/longest/typical}}) |
| Paragraphs | {{range}} |
| {{Feature 3}} | {{value}} |
| {{Feature 4}} | {{value}} |
| {{Feature 5}} | {{value}} |

### Opening Move
**Use {{dominant opening type}}** ({{percentage}}% of {{Cluster Name}} do this).

> "{{Example opening sentence from corpus}}"

{{#if alternative_acceptable}}
Alternative: {{alternative opening type}} is acceptable when {{condition}}.
{{/if}}

### Structure
1. **{{Element 1}}** ({{length guidance}}): {{What it does}}
2. **{{Element 2}}** ({{length guidance}}): {{What it does}}
3. **{{Element 3}}** ({{length guidance}}): {{What it does}}
4. **{{Element 4}}** ({{length guidance}}): {{What it does}}
{{#if more elements}}
5. **{{Element 5}}** ({{length guidance}}): {{What it does}}
{{/if}}

### {{Distinctive Feature}}
{{Description of what makes this cluster's approach distinctive}}

> "{{Example quote demonstrating the feature}}"

### Tone
- {{Tone characteristic 1}}
- {{Tone characteristic 2}}
- {{Tone characteristic 3}}

---

## Signature Moves (Do This)

### 1. {{Move 1 Name}}
{{Description of the move and why it's characteristic}}

> "{{Example from corpus}}"
> — {{Article identifier if appropriate}}

### 2. {{Move 2 Name}}
{{Description of the move}}

> "{{Example from corpus}}"

### 3. {{Move 3 Name}}
{{Description of the move}}

> "{{Example from corpus}}"

{{#if move4}}
### 4. {{Move 4 Name}}
{{Description of the move}}

> "{{Example from corpus}}"
{{/if}}

---

## Prohibited Moves (Don't Do This)

### 1. {{Prohibited Move 1}}
**Why to avoid**: {{Explanation}}

### 2. {{Prohibited Move 2}}
**Why to avoid**: {{Explanation}}

### 3. {{Prohibited Move 3}}
**Why to avoid**: {{Explanation}}

---

## Coherence Pattern (if applicable for intro/conclusion)

### Dominant Type
**{{Coherence type}}** ({{percentage}}%): {{Description of what this means}}

### {{Alternative Type}} Risk
**{{Risk level: Low/Moderate/High}}** ({{percentage}}%): {{When this might happen}}

### {{Another Type}}
**{{Occurrence}}** ({{percentage}}%): {{Description}}

---

## Exemplar

**{{Article identifier or filename}}**

- **{{Section type}}**: {{word count}}, {{key features}}
- **What makes it exemplary**: {{Why this article represents the cluster well}}

**Key techniques demonstrated**:
- {{Technique 1}}
- {{Technique 2}}
- {{Technique 3}}

**Notable quote**:
> "{{Quote that exemplifies the cluster's approach}}"

---

## Writing Checklist

### {{Section Type}}
- [ ] {{Checkpoint 1—opening}}
- [ ] {{Checkpoint 2—structure}}
- [ ] {{Checkpoint 3—content}}
- [ ] {{Checkpoint 4—length}}
- [ ] {{Checkpoint 5—tone}}

{{#if second_section}}
### {{Second Section Type}} (if applicable)
- [ ] {{Checkpoint 1}}
- [ ] {{Checkpoint 2}}
- [ ] {{Checkpoint 3}}
{{/if}}

### Coherence (if applicable)
- [ ] {{Coherence checkpoint 1}}
- [ ] {{Coherence checkpoint 2}}
- [ ] {{Coherence checkpoint 3}}
```

---

## Variables Reference

| Variable | Source | Example |
|----------|--------|---------|
| `{{Cluster Name}}` | Phase 3 naming | "Gap-Filler Minimalist" |
| `{{percentage}}` | Phase 3 calculation | "38.8" |
| `{{Contribution logic}}` | Phase 3 interpretation | "We don't know about X; this study tells us." |
| `{{dominant opening type}}` | Phase 2 coding | "phenomenon-led" |
| `{{range}}` | Phase 1 statistics | "600-750 words" |
| `{{Example from corpus}}` | Actual corpus quote | "Tasked with protecting children..." |

---

## Cluster Naming Conventions

Name clusters by their **primary strategy**:

| Strategy | Example Name |
|----------|--------------|
| Fills empirical gap | Gap-Filler |
| Applies theory | Theory-Extension |
| Creates concept | Concept-Builder |
| Integrates literatures | Synthesis Integrator |
| Resolves debate | Problem-Driven |
| Focuses on policy | Policy-Focused |
| Uses narrative | Narrative-Centered |

Add modifiers for distinctiveness:
- "Gap-Filler **Minimalist**" (efficient structure)
- "Theory-Extension **Framework Applier**" (applies named framework)
- "Problem-Driven **Pragmatist**" (practical orientation)
