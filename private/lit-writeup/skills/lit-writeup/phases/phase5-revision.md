# Phase 5: Revision

## Why This Phase Matters

Good writing is rewriting. The draft from Phase 3 and the refined turn from Phase 4 need polishing: checking calibration against norms, smoothing transitions, ensuring consistency, and achieving prose quality worthy of publication. This phase transforms a competent draft into a compelling Theory section.

---

## Your Tasks

### 1. Calibration Check

Compare draft against benchmarks from `techniques/calibration-norms.md`:

| Metric | Target (IQR) | Your Draft | Status |
|--------|-------------|------------|--------|
| Word count | 1,145-1,744 | [actual] | [ ] OK / [ ] Adjust |
| Paragraphs | 7-12 | [actual] | [ ] OK / [ ] Adjust |
| Citations | 26-43 | [actual] | [ ] OK / [ ] Adjust |
| Citations/paragraph | 2.4-5.0 | [actual] | [ ] OK / [ ] Adjust |
| Subsections | 1-3 | [actual] | [ ] OK / [ ] Adjust |

**If outside target range**:
- Under word count: Expand synthesis or add context
- Over word count: Cut redundancy, tighten prose
- Under-cited: Add supporting sources
- Over-cited: Combine into strings, cut peripheral sources

### 2. Paragraph Function Audit

For each paragraph, verify:

1. **Clear function**: Can you identify what this paragraph is doing (CONTEXT, THEORY, SYNTHESIZE, etc.)?
2. **Topic sentence signals function**: Does the opening make the function clear?
3. **Function fits position**: Is this function appropriate for this location in the sequence?
4. **Function matches cluster**: Is this function used appropriately for your cluster?

Flag any paragraph where function is unclear or misaligned.

### 3. Transition Check

Between every paragraph pair, verify:

- **Logical connection**: Does paragraph N+1 follow from paragraph N?
- **Explicit transition**: Is there a transition marker or connecting phrase?
- **No abrupt shifts**: Reader shouldn't feel whiplash

Common transitions to add:
- Additive: "Building on this work," "Moreover," "Similarly"
- Contrastive: "However," "Yet," "In contrast"
- Sequential: "A second body of scholarship," "Additionally"
- Consequential: "Thus," "As a result," "Given this"

### 4. Citation Pattern Audit

Review citation integration across the section:

- **Variety**: Are you using multiple patterns (parenthetical, author-subject, string)?
- **Author-subject for canonicals**: Are foundational theorists given prominence?
- **Efficient strings**: Is consensus established without excessive strings?
- **Quotes only for definitions**: Are you quoting only when language precision matters?
- **No orphan citations**: Every citation should be integrated into prose, not just listed

### 5. Hedging Calibration

Review hedging across claim types:

| Claim Type | Expected Hedging | Check Draft |
|------------|------------------|-------------|
| Reporting prior literature | Low-moderate ("demonstrates," "shows") | [ ] |
| Defining concepts | None ("is," "refers to") | [ ] |
| Gap claims | Assertive ("we know little") | [ ] |
| Research questions | None (state directly) | [ ] |
| Mechanism predictions | Moderate ("may," "might") | [ ] |
| Generalizations | Moderate-high ("suggests," "tends to") | [ ] |

Flag any over-hedged definitions or under-hedged mechanism claims.

### 6. Cluster Style Consistency

Verify prose style matches cluster throughout:

| Cluster | Style Check |
|---------|-------------|
| **Gap-Filler** | Is it lean? No unnecessary elaboration? |
| **Theory-Extender** | Is the framework prominent? Named theorist central? |
| **Concept-Builder** | Are definitions confident? Is the new term used consistently? |
| **Synthesis** | Are both traditions treated evenly? Is there a clear bridge? |
| **Problem-Driven** | Is the debate presented fairly? Or is context sufficient? |

### 7. Prose Polish

Read the entire section for prose quality:

- **Sentence variety**: Mix long and short sentences
- **Active voice**: Prefer active constructions where appropriate
- **Concrete language**: Avoid vague abstractions
- **Jargon check**: Is technical terminology necessary and defined?
- **Read aloud**: Does it flow when spoken?

### 8. Compile Citation List & Zotero Lookup

Transform the citation tracking from Phase 3 into final outputs.

**Step 1: Deduplicate citations**
Combine `citations-tracking.json` into a unique list of sources:

```json
{
  "citations": [
    {
      "author": "Kirk and Papachristos",
      "year": "2011",
      "count": 3,
      "zotero_key": null,
      "full_citation": null
    }
  ]
}
```

**Step 2: Zotero lookup (if MCP available)**
If the Zotero MCP is configured, look up each citation to get:
- Zotero item key
- Full bibliographic metadata
- Formatted citation

Use `mcp__zotero-mcp__zotero_search_items` with author + year queries:

```
For each citation:
1. Search: "{author} {year}"
2. If match found: record zotero_key and full metadata
3. If no match: flag for manual resolution
```

**Step 3: Generate outputs**

Create `citations-final.json`:
```json
{
  "section": "Theory",
  "total_citations": 37,
  "unique_sources": 35,
  "citations": [
    {
      "author": "Kirk and Papachristos",
      "year": "2011",
      "title": "Legal Cynicism and Collective Efficacy",
      "zotero_key": "ABC12345",
      "count_in_section": 3
    }
  ],
  "unmatched": [
    {
      "author": "Smith",
      "year": "2020",
      "note": "Not found in Zotero library"
    }
  ]
}
```

Create `bibliography.md`:
```markdown
# Bibliography for Theory Section

## Sources Cited (35 unique)

Kirk, David S. and Andrew V. Papachristos. 2011. "Cultural Mechanisms and the Persistence of Neighborhood Violence." *American Journal of Sociology* 116(4):1190-1233.

[Continue for all sources...]

## Unmatched Citations (require manual lookup)

- Smith (2020) - Not found in Zotero library
```

**If Zotero MCP is not available**:
- Output the deduplicated citation list without Zotero keys
- Note that manual bibliography creation is needed
- The list still saves significant time vs. parsing the document

### 9. Final Checklist

Before completion, verify:

- [ ] Word count in target range
- [ ] Citation count in target range
- [ ] Each paragraph has clear function
- [ ] Topic sentences signal function
- [ ] Transitions between all paragraphs
- [ ] Turn is specific and well-placed
- [ ] Gap directly motivates research questions
- [ ] Hedging calibrated by claim type
- [ ] Citation patterns varied
- [ ] Cluster style consistent throughout
- [ ] Prose reads smoothly
- [ ] Citation list compiled (citations-final.json)
- [ ] Bibliography generated (bibliography.md)
- [ ] Unmatched citations flagged for user

### 10. Write Quality Memo

Create `quality-memo.md`:

```markdown
# Theory Section Quality Assessment

## Calibration Results

| Metric | Target | Actual | Status |
|--------|--------|--------|--------|
| Word count | 1,145-1,744 | [N] | ✓/needs adjustment |
| Paragraphs | 7-12 | [N] | ✓/needs adjustment |
| Citations | 26-43 | [N] | ✓/needs adjustment |
| Citations/paragraph | 2.4-5.0 | [N] | ✓/needs adjustment |
| Subsections | 1-3 | [N] | ✓/needs adjustment |

## Structural Assessment

### Paragraph Functions
[Assessment of function clarity and sequencing]

### Transitions
[Assessment of flow between paragraphs]

### Turn Quality
[Assessment of turn specificity and placement]

## Style Assessment

### Citation Patterns
[Assessment of citation variety and integration]

### Hedging Calibration
[Assessment of hedging by claim type]

### Cluster Alignment
[Assessment of style consistency with cluster]

## Prose Quality

### Strengths
- [List strong aspects]

### Areas Addressed in Revision
- [List what was improved]

### Remaining Considerations
- [Any remaining issues or judgment calls]

## Final Section Statistics

- Word count: [N]
- Paragraph count: [N]
- Citation count: [N]
- Subsection count: [N]
- Cluster: [Name]

## Confidence Assessment
[High/Medium/Low confidence that section is publication-ready]
```

---

## Guiding Principles

### Revision Is Not Line-Editing
This phase is about structural integrity, calibration, and coherence—not comma placement.

### When in Doubt, Cut
If a sentence doesn't advance the argument, remove it.

### Consistency Trumps Perfection
A consistently good section beats one with brilliant moments and weak transitions.

### The Section Should Stand Alone
A reader should understand your contribution from the Theory section alone, without reading the rest of the paper.

---

## Common Revision Issues

| Issue | Symptom | Solution |
|-------|---------|----------|
| **Bloat** | Over word count | Cut redundant synthesis, tighten paragraphs |
| **Thin** | Under word count | Expand underdeveloped literature, add context |
| **Choppy** | Abrupt shifts | Add transitions, smooth connections |
| **Monotonous** | Same citation pattern throughout | Vary integration patterns |
| **Over-hedged** | "May" and "might" everywhere | Assert established findings, definitions |
| **Under-hedged** | Strong claims about mechanisms | Add appropriate caution |
| **Buried turn** | Hard to find the gap | Move turn to paragraph opening |
| **Misaligned structure** | Doesn't match cluster | Restructure to cluster norms |

---

## Output Files to Create

1. **theory-section-final.md** - Final polished Theory section
2. **quality-memo.md** - Full quality assessment
3. **revision-log.md** - Record of changes made
4. **citations-final.json** - Complete citation list with Zotero keys (if available)
5. **bibliography.md** - Formatted bibliography ready for reference section

---

## When You're Done

Report to the orchestrator:
- Final word count
- Final citation count
- Calibration status (in range / deviations explained)
- Confidence assessment (High/Medium/Low)
- Citation outputs generated (citations-final.json, bibliography.md)
- Zotero matches found / unmatched citations
- Any remaining concerns

Example summary:
> "**Revision complete**. Final section: 1,523 words (target 1,145-1,744 ✓), 37 citations (target 26-43 ✓), 10 paragraphs, 2 subsections. All calibration metrics in range. Turn confirmed specific and well-placed at P6. Transitions smoothed throughout. Hedging calibrated. **High confidence** section is publication-ready.
>
> **Citation outputs**: `citations-final.json` with 35 unique sources. Zotero lookup: 32 matched, 3 unmatched (flagged in bibliography.md). `bibliography.md` ready for reference section.
>
> Minor consideration: paragraph 8 bridge could be strengthened if user wants to emphasize theoretical contribution more."
