# Phase 5: Field Synthesis

## Why This Phase Matters

This is where everything comes together. You've audited the corpus, read deeply, mapped theories, clustered themes, and identified debates. Now you synthesize this into a coherent understanding of the field that's ready for writing.

The outputs of this phase are the direct inputs to lit-writeup. This is the handoff.

---

## Your Tasks

### 1. Synthesize Across Phases

Pull together key insights from each phase:

| Phase | Key Takeaway for Synthesis |
|-------|---------------------------|
| **Corpus Audit** | What's in the literature? What's missing? |
| **Deep Reading** | How do papers construct arguments? What works? |
| **Theoretical Map** | What traditions? What concepts? What lineages? |
| **Thematic Clusters** | What's studied? What's over/under-represented? |
| **Debate Map** | Where's disagreement? What's unresolved? |

### 2. Articulate the Field's State

Write a narrative synthesis:

```markdown
## The State of the Field

### What the Field Knows
[Summary of established findings, 2-3 paragraphs]

### How the Field Thinks
[Summary of dominant theoretical approaches, 1-2 paragraphs]

### Where the Field Disagrees
[Summary of key debates and tensions, 1-2 paragraphs]

### What the Field Lacks
[Summary of gaps—empirical, theoretical, methodological, 1-2 paragraphs]
```

### 3. Identify Contribution Opportunities

Based on your synthesis, what are the clearest opportunities for contribution?

**Types of contribution**:
- **Empirical gap**: Unstudied population, setting, or phenomenon
- **Theoretical extension**: Framework not yet applied to X
- **Concept building**: Need for new analytical tool
- **Synthesis**: Traditions not yet connected
- **Debate resolution**: Evidence to adjudicate competing claims

For each opportunity:
```markdown
### Opportunity: [Name]

**Type**: [Empirical gap / Extension / Building / Synthesis / Debate]

**Description**: [What's the opportunity?]

**Why it's viable**: [Why can this be done now?]

**Required evidence**: [What would demonstrate this contribution?]

**Fit with user's project**: [How well does this fit?]
```

### 4. Recommend Lit-Writeup Cluster

Based on the synthesis, recommend a cluster for lit-writeup:

| If... | Then Consider... |
|-------|------------------|
| Main contribution is empirical insight about understudied group | **Gap-Filler** |
| Main contribution is showing established framework works in new domain | **Theory-Extender** |
| Main contribution is new concept or typology | **Concept-Builder** |
| Main contribution is connecting previously separate literatures | **Synthesis Integrator** |
| Main contribution is adjudicating a debate | **Problem-Driven (Debate)** |
| Main contribution is documenting understudied phenomenon | **Problem-Driven (Empirical)** |

Provide rationale:
```markdown
## Lit-Writeup Cluster Recommendation

**Recommended**: [Cluster Name]

**Rationale**:
[Why this cluster fits the project's contribution]

**Alternative considered**:
[Another cluster that might fit, and why primary is better]

**Cluster implications**:
- Structure: [Expected subsections]
- Literature balance: [Theory-heavy / Balanced / Substantive]
- Turn strategy: [How to frame the gap]
```

### 5. Plan the Handoff

Specify what lit-writeup will need:

```markdown
## Handoff to Lit-Writeup

### Key Literatures to Engage
1. **[Literature 1]**: [Purpose in section]
2. **[Literature 2]**: [Purpose in section]
3. **[Literature 3]**: [Purpose in section]

### Theoretical Traditions to Reference
- [Tradition 1]: [How it appears in your section]
- [Tradition 2]: [How it appears in your section]

### Concepts Requiring Definition
- **[Concept A]**: Define using [Source]
- **[Concept B]**: Define using [Source]

### Debates to Acknowledge (if any)
- [Debate]: Present as [background / central tension / resolved]

### Suggested Turn Formulation
> "[Draft turn sentence based on identified gap]"

### Key Citations for Each Section
[Map citations to expected subsections]
```

### 6. Write Field Synthesis Document

Create `field-synthesis.md`:

```markdown
# Field Synthesis

## Project
- **Research question**: [From user]
- **Main argument**: [From user]

---

## The State of the Field

[Narrative synthesis from Task 2]

---

## Contribution Opportunities

[Documentation from Task 3]

---

## Recommended Approach

### Lit-Writeup Cluster: [Name]

[Recommendation and rationale from Task 4]

---

## Handoff to Lit-Writeup

[Handoff specification from Task 5]

---

## Key Documents for Reference

| Document | Location | Purpose |
|----------|----------|---------|
| Corpus Audit | `corpus-audit.md` | Coverage and gaps |
| Reading Notes | `reading-notes/` | Deep engagement evidence |
| Theoretical Map | `theoretical-map.md` | Traditions and lineages |
| Thematic Clusters | `thematic-clusters.md` | Empirical landscape |
| Debate Map | `debate-map.md` | Tensions and questions |

---

## Ready for Lit-Writeup

User can now invoke `/lit-writeup` with this synthesis as input.

Recommended prompt:
> "I've completed lit-synthesis. My field-synthesis.md recommends [Cluster] because [reason]. My main argument is [X]. Please begin Phase 0: Assessment."
```

---

## Guiding Principles

### Synthesis ≠ Summary
Don't just repeat what's in other documents. Integrate, interpret, and conclude.

### Be Decisive About Contribution
The field synthesis should make a clear recommendation about the user's contribution type.

### The Turn Is the Payoff
Everything in this synthesis should point toward what gap the user fills.

### Make the Handoff Clean
Lit-writeup should be able to start immediately from your outputs. Don't leave ambiguity.

### The User Has Final Say
Your recommendations are informed suggestions. The user knows their project best.

---

## Output Files to Create

1. **field-synthesis.md** - Comprehensive synthesis and handoff document

---

## When You're Done

Report to the orchestrator:
- Summary of field state (2-3 sentences)
- Primary contribution opportunity identified
- Recommended lit-writeup cluster
- Readiness for handoff

Example summary:
> "Field synthesis complete. The literature on police-calling in disadvantaged neighborhoods is theoretically mature (legal consciousness, recognition) but empirically narrow (focused on residents' perspectives, not meaning-making processes). Primary opportunity: **synthesis** of legal consciousness and recognition traditions to explain the cynicism-reliance paradox. Recommended cluster: **Synthesis Integrator**. Handoff document ready with suggested turn: 'Yet while research documents why residents call police despite cynicism, there is less attention to the cultural scripts through which residents make sense of these encounters.' Ready for lit-writeup."
