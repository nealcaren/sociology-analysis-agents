# Bibliography Builder

You help researchers **build bibliographies** from manuscript citations by extracting in-text citations, matching them against a Zotero library, identifying issues, and generating a formatted reference list.

## What This Skill Does

This is a **utility skill** that automates bibliography creation:

1. **Extract** all in-text citations from a document (Author Year format)
2. **Match** each citation against the user's Zotero library via MCP
3. **Review** for issues: missing items, ambiguous matches, duplicates
4. **Generate** a properly formatted bibliography in the requested style

## When to Use This Skill

Use this skill when you have:
- A **manuscript with in-text citations** in Author-Year format (e.g., "Smith 2020", "Jones and Lee 2019")
- Access to the **Zotero MCP** with your library connected
- A need for a **formatted bibliography** (APA, ASA, Chicago, etc.)

## Requirements

This skill requires the **Zotero MCP server** to be configured. The MCP provides access to:
- `zotero_search_items` - Search library by author/title
- `zotero_get_item_metadata` - Get full citation details
- Citation formatting capabilities

## Workflow Phases

### Phase 0: Intake
**Goal**: Read the document and confirm citation style.

**Process**:
- Read the manuscript file
- Identify citation format (Author Year, Author-Year with comma, etc.)
- Count approximate citations
- Confirm output format (APA, ASA, Chicago Author-Date, etc.)

**Output**: Citation inventory with format confirmation.

> **Pause**: User confirms citation style and desired output format.

---

### Phase 1: Citation Extraction
**Goal**: Parse all in-text citations from the document.

**Process**:
- Use regex patterns to find Author-Year citations
- Handle variations:
  - Single author: `(Smith 2020)`
  - Two authors: `(Smith and Jones 2020)` or `(Smith & Jones 2020)`
  - Multiple authors: `(Smith et al. 2020)`
  - Multiple citations: `(Smith 2020; Jones 2019)`
  - Page numbers: `(Smith 2020, p. 45)` or `(Smith 2020: 45)`
  - Narrative citations: `Smith (2020) argues...`
- Deduplicate and sort alphabetically
- Create citation list with frequency counts
- **Verify with grep**: Run shell commands to independently confirm extraction caught all citations (catches edge cases like McAdam, hyphenated names, accented characters)

**Output**: `citations-extracted.md` with all unique citations + grep verification.

> **Pause**: User reviews extracted citations for accuracy.

---

### Phase 2: Zotero Matching
**Goal**: Find each citation in the Zotero library.

**Process**:
- For each extracted citation:
  - Parse author name(s) and year
  - Search Zotero using `zotero_search_items`
  - If multiple matches, retrieve metadata to disambiguate
  - Record match status: Found, Ambiguous, Not Found
- Build match table with Zotero item keys

**Output**: `citation-matches.md` with match status for each citation.

> **Pause**: User reviews matches, especially ambiguous/missing items.

---

### Phase 3: Issue Review
**Goal**: Identify and resolve problems.

**Process**:
- Flag issues:
  - **Missing**: Citations not found in Zotero
  - **Ambiguous**: Multiple possible matches (same author, year)
  - **Year mismatch**: Author found but year differs
  - **Name variations**: "Smith" vs "Smith, J." vs "Smith, John"
- Generate issue report with suggested actions
- User provides resolutions for ambiguous cases

**Output**: `issues-report.md` with flagged problems and resolutions.

> **Pause**: User resolves any remaining issues.

---

### Phase 4: Bibliography Generation
**Goal**: Produce the formatted bibliography.

**Process**:
- Retrieve full metadata for all matched items
- Format according to requested style:
  - APA 7th Edition
  - ASA (American Sociological Association)
  - Chicago Author-Date
  - Other styles as requested
- Sort alphabetically by first author
- Handle special cases (edited volumes, translations, etc.)
- Output as markdown or plain text

**Output**: `bibliography.md` with formatted references.

---

## Citation Pattern Reference

### Patterns Extracted

| Pattern | Example | Regex |
|---------|---------|-------|
| Single author | `(Smith 2020)` | `\(([A-Z][a-z]+)\s+(\d{4})\)` |
| Two authors | `(Smith and Jones 2020)` | `\(([A-Z][a-z]+)\s+(?:and|&)\s+([A-Z][a-z]+)\s+(\d{4})\)` |
| Et al. | `(Smith et al. 2020)` | `\(([A-Z][a-z]+)\s+et\s+al\.?\s+(\d{4})\)` |
| Multiple citations | `(Smith 2020; Jones 2019)` | Split on `;\s*` then parse each |
| With page | `(Smith 2020, p. 45)` | `\(([A-Z][a-z]+)\s+(\d{4}),?\s*p?p?\.?\s*\d+\)` |
| Narrative | `Smith (2020)` | `([A-Z][a-z]+)\s+\((\d{4})\)` |

### Edge Cases

- **Hyphenated names**: `(García-López 2020)` - include hyphen in author pattern
- **Particles**: `(van der Berg 2020)` - lowercase particles before surname
- **Organizations**: `(WHO 2020)` - all-caps or mixed case organizations
- **No date**: `(Smith n.d.)` - handle "n.d." as year placeholder
- **Forthcoming**: `(Smith forthcoming)` - handle non-numeric years

## Output Formats

### APA 7th Edition
```
Smith, J. A., & Jones, B. C. (2020). Article title in sentence case.
    *Journal Name*, *45*(2), 123-145. https://doi.org/10.xxxx
```

### ASA (American Sociological Association)
```
Smith, John A. and Beth C. Jones. 2020. "Article Title in Title Case."
    *Journal Name* 45(2):123-45.
```

### Chicago Author-Date
```
Smith, John A., and Beth C. Jones. 2020. "Article Title in Title Case."
    *Journal Name* 45 (2): 123–45.
```

## File Structure

```
project/
├── manuscript.md           # Input: document with citations
├── bibliography/
│   ├── citations-extracted.md   # Phase 1 output
│   ├── citation-matches.md      # Phase 2 output
│   ├── issues-report.md         # Phase 3 output
│   └── bibliography.md          # Phase 4 output (final)
```

## Zotero MCP Tools Used

| Tool | Purpose |
|------|---------|
| `zotero_search_items` | Find items by author/title/year |
| `zotero_get_item_metadata` | Get full bibliographic data |
| `zotero_get_collections` | Browse library structure |

## Key Reminders

- **Zotero must be running** with the MCP server active
- **Author names vary**: Search flexibly (last name + year first, then refine)
- **Multiple matches are common**: Same author publishes multiple works per year
- **Missing items**: User may need to add items to Zotero before proceeding
- **Format matters**: Confirm desired style before generating bibliography

## Starting the Process

When the user is ready to begin:

1. **Ask for the manuscript**:
   > "Please share the path to your manuscript file (markdown, .docx, or .txt)."

2. **Confirm citation style**:
   > "I'll extract Author-Year citations. What bibliography format do you need? (APA, ASA, Chicago, other)"

3. **Check Zotero access**:
   > "Let me verify I can connect to your Zotero library via MCP."

4. **Proceed with Phase 0** to read the document and inventory citations.
