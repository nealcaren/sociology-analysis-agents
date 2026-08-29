# Phase 2: Zotero Matching

## Why This Phase Matters

The extracted citations are just text strings. To build a bibliography, you need the full bibliographic record from Zotero. This phase matches each citation to its corresponding Zotero item, handling ambiguities and variations.

## Your Tasks

### 1. Load Zotero Tools

Use ToolSearch to load the necessary MCP tools:
```
ToolSearch: "zotero search"
```

Key tools:
- `mcp__zotero-mcp__zotero_search_items` - Search by author/title/year
- `mcp__zotero-mcp__zotero_get_item_metadata` - Get full record

### 2. Search Strategy

For each citation, search in this order:

**Step 1: Author + Year search**
```
Search: author:Smith AND year:2020
```

**Step 2: If multiple results, check title keywords**
- Look for distinctive words from the manuscript context
- Match against Zotero titles

**Step 3: If still ambiguous, get metadata for candidates**
- Compare full author lists
- Check publication venue
- Present options to user if needed

### 3. Handle Different Citation Types

**Single author (Smith 2020):**
- Search: `author:Smith year:2020`
- Usually straightforward

**Two authors (Smith and Jones 2020):**
- Search: `author:Smith author:Jones year:2020`
- Verify both names appear in result

**Et al. (Smith et al. 2020):**
- Search: `author:Smith year:2020`
- May get multiple results - need to verify this is the 3+ author work
- Get full author list from metadata

**Year suffix (Lee 2020a, Lee 2020b):**
- Search: `author:Lee year:2020`
- Will return multiple - user may need to identify which is which
- Use title keywords from context if available

### 4. Record Match Status

For each citation, record:

| Status | Meaning |
|--------|---------|
| **Found** | Single unambiguous match |
| **Ambiguous** | Multiple possible matches |
| **Not Found** | No match in Zotero |
| **Year Mismatch** | Author found but year differs |
| **Name Variation** | Match found with different name form |

### 5. Build Match Table

Create a comprehensive match record:

| Citation | Status | Zotero Key | Title (abbreviated) | Notes |
|----------|--------|------------|---------------------|-------|
| Smith 2020 | Found | ABC123 | "Social movements and..." | |
| Jones 2019 | Ambiguous | DEF456, GHI789 | Two articles same year | User decision needed |
| García et al. 2021 | Found | JKL012 | Full authors: García, López, Martín | |
| Brown 2018 | Not Found | — | — | Not in library |

## Output: Citation Matches

Create `citation-matches.md`:

```markdown
# Citation Matches

**Citations processed**: [X]
**Found**: [X]
**Ambiguous**: [X]
**Not Found**: [X]

## Successful Matches

| Citation | Zotero Key | Full Reference |
|----------|------------|----------------|
| Smith 2020 | ABC123 | Smith, J. (2020). Social movements and change... |
| García et al. 2021 | JKL012 | García, M., López, R., & Martín, S. (2021)... |
| ... | ... | ... |

## Ambiguous Matches (User Decision Needed)

### Jones 2019
**In manuscript**: "(Jones 2019)" appears on p. 5, 12
**Context**: "...organizational dynamics (Jones 2019)..."

**Candidate 1**: DEF456
- Jones, A. B. (2019). Organizational theory and practice. *Journal A*.

**Candidate 2**: GHI789
- Jones, C. D. (2019). Network dynamics in organizations. *Journal B*.

**Which is correct?** [User to specify]

## Not Found

| Citation | Search Attempted | Suggestion |
|----------|------------------|------------|
| Brown 2018 | author:Brown year:2018 | Add to Zotero or check spelling |
| Williams 2021 | author:Williams year:2021 | No results - verify citation |

## Name Variations Noted

| In Manuscript | In Zotero | Status |
|---------------|-----------|--------|
| Smith 2020 | Smith, John A. 2020 | Matched |
| García 2019 | Garcia 2019 (no accent) | Matched with variation |
```

## Pause Point

Present the match results to the user. Ask:
1. For ambiguous matches: Which candidate is correct?
2. For not found: Should we skip these or add to Zotero first?
3. Any name variations need correction?

Once all matches are confirmed, proceed to Phase 3: Issue Review.
