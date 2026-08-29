# Phase 0: Assessment

## Why This Phase Matters

The single most important decision in Theory section writing is **cluster selection**. The cluster determines your structure, paragraph sequence, citation patterns, and calibration targets. Getting this wrong means writing a section that doesn't match your contribution—confusing readers and undermining your argument.

This phase ensures you make a deliberate, informed choice about which style fits your project.

---

## Your Tasks

### 1. Gather Project Information

Collect from the user:

**Required**:
- Research question(s)
- Main argument or contribution claim
- Key literatures to engage (2-4 traditions)
- Available materials (lit-search outputs, existing notes)

**Helpful**:
- Target journal (if known)
- Existing drafts (if revising)
- Theoretical framework (if applicable)

### 2. Apply the Cluster Decision Tree

Work through this diagnostic to recommend a cluster:

```
What is the primary contribution?

├── Empirical insight about understudied population/phenomenon?
│   └── No new theoretical framework or terminology?
│       └── CLUSTER 1: Gap-Filler
│
├── Applying an established framework to a new domain?
│   └── Named theorist/framework central to analysis?
│   └── Not modifying the framework, just extending it?
│       └── CLUSTER 2: Theory-Extender
│
├── Introducing new terminology, typology, or conceptual framework?
│   └── Existing concepts inadequate?
│   └── New term will be used in findings?
│       └── CLUSTER 3: Concept-Builder
│
├── Connecting previously separate literatures?
│   └── Multiple traditions brought together?
│   └── Not coining new terms?
│       └── CLUSTER 4: Synthesis Integrator
│
└── Adjudicating a debate OR documenting for policy?
    ├── Two competing positions to adjudicate?
    │   └── CLUSTER 5a: Problem-Driven (Debate)
    └── Heavy empirical/policy context, light theory?
        └── CLUSTER 5b: Problem-Driven (Empirical)
```

### 3. Review Cluster Profile

Once you have a candidate cluster, read the detailed profile:
- `clusters/gap-filler.md`
- `clusters/theory-extender.md`
- `clusters/concept-builder.md`
- `clusters/synthesis-integrator.md`
- `clusters/problem-driven.md`

Verify the profile matches the user's project.

### 4. Assess Materials

If user has lit-search outputs:
- Review `synthesis.md` for literature landscape
- Review `gaps.md` for identified opportunities
- Check citation inventory against cluster needs

If no lit-search:
- Ask user to describe key literatures
- Identify which traditions need engagement
- Note any gaps in coverage

### 5. Write Assessment Memo

Create `assessment-memo.md` with:

```markdown
# Theory Section Assessment

## Project Summary
- Research question: [summarize]
- Main argument: [summarize]
- Key literatures: [list]

## Contribution Type Analysis
- [Walk through decision tree logic]
- [Note any ambiguities]

## Recommended Cluster
**Cluster [N]: [Name]**

### Rationale
- [Why this cluster fits]
- [What the cluster predicts about structure]

### Alternative Considered
- [If applicable: why rejected alternative]

## Cluster Implications
- Expected word count: [range]
- Subsection structure: [description]
- Literature balance: [theory-heavy/balanced/substantive]
- Turn placement: [early/middle/late]

## Literature Readiness
- [Assessment of available materials]
- [Any gaps to fill before drafting]

## Questions for User
- [Any clarifying questions needed before architecture]
```

### 6. Present Recommendation

Present to user:
- Your recommended cluster with clear rationale
- What this means for structure and approach
- Any questions you have before proceeding

---

## Guiding Principles

### Cluster Selection is Not Permanent
You can revise as you learn more during architecture. But starting with the right cluster prevents structural rewrites.

### When in Doubt, Choose Gap-Filler
It's the most common (27.5%) and safest approach. You can always add theoretical ambition; it's harder to remove it.

### Theory-Extension vs. Synthesis
- **Extension**: One framework, applied to new domain
- **Synthesis**: Multiple frameworks, integrated without new terminology

### Concept-Building is High-Risk
Only choose Cluster 3 if the new concept genuinely does work existing concepts cannot. Failed concept-building looks like jargon.

### Problem-Driven Requires Genuine Debate
If your "debate" is really one established view and your extension of it, you're a Theory-Extender. True Problem-Driven (Debate) presents two genuinely competing positions.

---

## Output Files to Create

1. **assessment-memo.md** - Full assessment with cluster recommendation
2. (Optional) **questions-for-user.md** - If clarification needed

---

## When You're Done

Report to the orchestrator:
- Recommended cluster
- Key rationale (2-3 sentences)
- Any outstanding questions
- Readiness assessment for Phase 1

Example summary:
> "I recommend **Cluster 1: Gap-Filler** for this project. The user is studying how guest mothers manage identity in doubled-up households—an understudied population with no novel theoretical framework. The contribution is primarily empirical. The user has solid literature from lit-search covering housing, family, and identity literatures. Ready for Phase 1: Architecture."
