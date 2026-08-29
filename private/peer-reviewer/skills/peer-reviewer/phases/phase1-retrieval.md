# Phase 1: Literature Retrieval

## Why This Phase Matters

Reviewer personas must be grounded in actual texts, not stereotypes. This phase retrieves full texts from Zotero for each confirmed reviewer perspective. The quality of the simulated review depends entirely on having substantive sources to read—we're building personas from what these scholars actually wrote, not from secondhand summaries.

---

## Your Tasks

### 1. Confirm Reviewer List

Start with the user-confirmed reviewer list from Phase 0. For each reviewer:

```markdown
## Confirmed Reviewers

1. **[Reviewer 1 Name/Perspective]**
   - Type: [Specific scholar / Theoretical camp]
   - Review focus: [Theory + Findings] OR [Methods + Findings]

2. **[Reviewer 2 Name/Perspective]**
   - Type: [Specific scholar / Theoretical camp]
   - Review focus: [Theory + Findings] OR [Methods + Findings]

3. **[Reviewer 3 Name/Perspective]** (if applicable)
   - Type: [Specific scholar / Theoretical camp]
   - Review focus: [Theory + Findings] OR [Methods + Findings]
```

### 2. Retrieve Sources for Each Reviewer

For each confirmed reviewer, use Zotero MCP to retrieve relevant sources.

**Search strategies**:

```
# For specific scholars:
mcp__zotero-mcp__zotero_search_items: "author:Lareau"
mcp__zotero-mcp__zotero_search_items: "author:Bourdieu"

# For theoretical traditions:
mcp__zotero-mcp__zotero_search_by_tag: "cultural capital"
mcp__zotero-mcp__zotero_search_by_tag: "field theory"

# For collections:
mcp__zotero-mcp__zotero_get_collection_items: [collection_key]
```

**Prioritize sources**:
1. **Foundational works** - The canonical text(s) that define the perspective
2. **Methodological statements** - Where they explain how to do research their way
3. **Recent work** - Shows current thinking and evolution
4. **Critiques of others** - Reveals what they value and what they reject

### 3. Retrieve Full Texts

For each identified source, attempt to retrieve full text:

```
mcp__zotero-mcp__zotero_get_item_fulltext: [item_key]
```

Track retrieval status:

```markdown
## Source Retrieval: [Reviewer Perspective]

| Item Key | Author(s) | Year | Title | Full Text? | Priority |
|----------|-----------|------|-------|------------|----------|
| ABC123 | Lareau | 2003 | Unequal Childhoods | Yes | Foundational |
| DEF456 | Lareau | 2011 | Unequal Childhoods 2nd ed | Yes | Recent |
| GHI789 | Lareau & Weininger | 2003 | Cultural capital in educational research | Yes | Methodological |
| JKL012 | Lareau | 2015 | Cultural knowledge and social inequality | No | Recent |
```

### 4. Assess Source Quality

For each reviewer, evaluate whether retrieved sources are sufficient:

**Strong foundation** (proceed confidently):
- 3+ full texts available
- Includes at least one foundational work
- Covers theoretical AND methodological/empirical dimensions

**Adequate foundation** (proceed with caution):
- 2 full texts available
- At least one substantive theoretical piece
- May need to note limitations in persona

**Weak foundation** (flag for user):
- 0-1 full texts available
- Missing foundational works
- User should add sources or reconsider perspective

```markdown
## Source Quality Assessment

| Reviewer | Full Texts | Foundational? | Methodological? | Assessment |
|----------|------------|---------------|-----------------|------------|
| Lareau | 4 | Yes | Yes | Strong |
| Interview methods | 2 | Yes | Yes | Adequate |
| Critical education | 1 | No | No | Weak - flag |
```

### 5. Organize Sources by Reviewer

Create a structured source list for each reviewer:

```markdown
## Sources for Reviewer: [Name/Perspective]

### Foundational Works
1. **[Title]** ([Year])
   - Zotero key: [key]
   - Relevance: [Why this is foundational for this perspective]

### Methodological/Theoretical Statements
2. **[Title]** ([Year])
   - Zotero key: [key]
   - Relevance: [What this reveals about their approach]

### Recent/Applied Work
3. **[Title]** ([Year])
   - Zotero key: [key]
   - Relevance: [How this shows current thinking]

### Total: [N] sources with full text
```

### 6. Note Gaps and Limitations

Document any limitations for Phase 2:

```markdown
## Retrieval Limitations

### Reviewer: [Name]
- **Gap**: [Missing type of source]
- **Impact**: [How this affects persona construction]
- **Mitigation**: [How we'll handle this]

### Overall Assessment
[Summary of retrieval quality across all reviewers]
```

---

## Output Files to Create

Save to project analysis folder:

1. **retrieval-log.md** - Complete log of Zotero queries and results
2. **sources-reviewer1.md** - Organized sources for first reviewer
3. **sources-reviewer2.md** - Organized sources for second reviewer
4. **sources-reviewer3.md** - Organized sources for third reviewer (if applicable)
5. **retrieval-summary.md** - Overall assessment and any flags for user

---

## Zotero MCP Reference

Key tools for this phase:

| Tool | Purpose |
|------|---------|
| `zotero_search_items` | Search by author, title, keyword |
| `zotero_search_by_tag` | Search by tag (theoretical traditions) |
| `zotero_get_collection_items` | Get all items in a collection |
| `zotero_get_item_metadata` | Get bibliographic details |
| `zotero_get_item_fulltext` | Retrieve full text content |
| `zotero_get_annotations` | Get user highlights/notes |
| `zotero_get_notes` | Get attached notes |

---

## Guiding Principles

### Full Text Is Essential
Metadata alone isn't enough. We need to read what they actually wrote to build an informed persona.

### Quality Over Quantity
3 deeply relevant sources beat 10 tangentially related ones.

### Foundational Works Matter Most
The canonical texts define the perspective; recent work shows evolution.

### Note What's Missing
If a key work isn't available, flag it. The user may be able to add it.

### Annotations Are Valuable
If the user has highlighted or annotated sources, these reveal what they found important.

---

## When You're Done

Report to the orchestrator:
- Sources retrieved for each reviewer
- Full text availability summary
- Any weak foundations flagged
- Ready for user review of source lists

Example summary:
> "**Retrieval complete**. Reviewer 1 (Lareau): 4 sources with full text, strong foundation. Reviewer 2 (Interview methods): 3 sources with full text, adequate foundation. Reviewer 3 (Critical education): Only 1 source with full text—flagging for user. May need to add Bowles & Gintis or similar, or reconsider this perspective. Sources organized and ready for user review before persona construction."
