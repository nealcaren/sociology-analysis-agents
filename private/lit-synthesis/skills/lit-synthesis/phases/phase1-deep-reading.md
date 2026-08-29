# Phase 1: Deep Reading

## Why This Phase Matters

Deep reading is where understanding happens. Abstracts tell you *what* papers argue; full text reveals *how* they argue it—how theory is deployed, what evidence is marshaled, what assumptions underlie claims. This phase creates the raw material for theoretical mapping and debate identification.

---

## Your Tasks

### 1. Prepare Reading Environment

For each priority paper:
- Confirm PDF is in Zotero
- Check for existing annotations (from user's prior reading)
- Note if paper has supplementary materials

Use Zotero MCP to access:
```
Use zotero_get_item_metadata for [paper identifier]
Use zotero_get_annotations for [paper identifier]
```

### 2. Read with Purpose

For each paper, read for:

**Argument Structure**
- What is the central claim?
- How is it structured (inductive, deductive, abductive)?
- What's the contribution claim?

**Theoretical Framework**
- Which tradition(s) does it draw on?
- Who are the key theorists cited?
- Is theory used descriptively, extended, or critiqued?

**Conceptual Work**
- What key concepts are used?
- Are any new concepts introduced?
- How are concepts operationalized?

**Empirical Strategy**
- What data? What methods?
- How is theory connected to evidence?
- What are the acknowledged limitations?

**Position in Field**
- Who does this paper cite approvingly?
- Who does it critique or position against?
- Where does it claim to contribute?

### 3. Create Reading Notes

For each paper, create a note file using the template in SKILL.md:

```
reading-notes/
├── author2020-short-title.md
├── author2019-short-title.md
└── ...
```

**Essential sections**:
- Core argument (1-2 sentences)
- Theoretical framework (tradition, key concepts)
- How theory is deployed (description vs. extension vs. critique)
- Key findings (bulleted)
- Contribution claim
- Key quotes (with page numbers)
- Your analytical notes

### 4. Flag Connections

As you read, note:
- Papers that cite each other
- Papers that contradict each other
- Papers using the same concepts differently
- Papers that seem to be in conversation

Add tags to notes:
- `[cites: Author2019]`
- `[contradicts: Author2018]`
- `[same-concept-as: Author2020]`

### 5. Extract Key Quotes

For each paper, capture 3-5 quotes that:
- Define key concepts
- State the argument clearly
- Could be used in your own writing
- Reveal assumptions or limitations

Always include page numbers.

### 6. Compile Reading Summary

After all priority papers are read, create a summary:

```markdown
# Reading Notes Summary

## Papers Read
- [N] papers deep-read
- [Date range]

## Emergent Patterns

### Theoretical Traditions Identified
1. **[Tradition 1]**: [which papers, key ideas]
2. **[Tradition 2]**: [which papers, key ideas]

### Recurring Concepts
- **[Concept A]**: Used by [papers], defined as [summary]
- **[Concept B]**: Used by [papers], defined as [summary]

### Methodological Patterns
- [Dominant approach]
- [Variations]

### Preliminary Tensions Noted
- [Tension 1]: [Paper A] vs [Paper B] on [issue]
- [Tension 2]: [description]

## Papers That Stand Out
- **Most cited within corpus**: [papers]
- **Most theoretically ambitious**: [papers]
- **Most methodologically innovative**: [papers]
- **Most relevant to user's project**: [papers]

## Gaps Emerging
- [What's missing from the conversation]

## Questions for Next Phases
- [What to investigate in theoretical mapping]
- [What to investigate in debate mapping]
```

---

## Using Zotero MCP Effectively

### Retrieving Full Text
```
Use zotero_get_item_metadata with the item key to get full text if available
```

### Getting Annotations
If user has already highlighted:
```
Use zotero_get_annotations for [item key]
```

This returns highlights and notes, accelerating your reading.

### Semantic Search for Connections
```
Use zotero_semantic_search with a concept to find related papers
```

---

## Guiding Principles

### Read the Whole Paper
Don't just skim. For priority papers, read introduction, theory, methods, findings, AND conclusion. The conclusion often reveals assumptions.

### Theory Sections Are Gold
Pay special attention to how authors construct their Theory sections—this feeds directly into lit-writeup.

### Note How, Not Just What
Anyone can summarize findings. Note *how* the argument is constructed, *how* theory is deployed, *how* evidence is marshaled.

### Quotes Need Context
A quote without page number is useless. A quote without noting *why* it matters is nearly as bad.

### Your Notes Are for Future You
Write notes that will make sense when you return to them in Phase 3-4. Be explicit about connections and questions.

---

## Output Files to Create

1. **reading-notes/*.md** - One file per paper
2. **reading-summary.md** - Compiled patterns and observations

---

## When You're Done

Report to the orchestrator:
- Number of papers deep-read
- Theoretical traditions identified
- Preliminary tensions noted
- Key papers for theoretical mapping

Example summary:
> "Deep reading complete. **15 papers** read in full. Three theoretical traditions identified: legal consciousness (6 papers), neighborhood effects (5 papers), recognition theory (4 papers). Preliminary tension noted between structural vs. cultural explanations for police-calling behavior. Kirk & Papachristos (2011) and Desmond (2016) emerge as most-cited anchors. Ready for Phase 2: Theoretical Mapping."
