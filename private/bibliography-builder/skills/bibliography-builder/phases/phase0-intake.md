# Phase 0: Intake

## Why This Phase Matters

Before extracting citations, you need to understand the document's citation conventions. Author-Year formats vary: some use "and," others use "&"; some include page numbers, others don't. Confirming these patterns upfront prevents extraction errors.

## Your Tasks

### 1. Read the Document

Read the manuscript file provided by the user. Note:
- File format (markdown, docx, txt)
- Approximate length (word count, page count)
- Subject matter (helps disambiguate common author names)

### 2. Identify Citation Patterns

Scan for in-text citations and identify:

**Connector style:**
- "and" → `(Smith and Jones 2020)`
- "&" → `(Smith & Jones 2020)`

**Page number format:**
- `p. 45` or `pp. 45-50`
- `: 45` (colon separator)
- `, 45` (comma only)
- No page numbers

**Multiple citation separator:**
- Semicolon: `(Smith 2020; Jones 2019)`
- Comma: `(Smith 2020, Jones 2019)`

**Narrative vs. parenthetical ratio:**
- Mostly `(Author Year)` parenthetical?
- Mixed with `Author (Year)` narrative?

### 3. Count Citations

Provide approximate count:
- Total citation instances (including duplicates)
- Estimated unique citations

### 4. Confirm Output Format

Ask user to confirm desired bibliography format:
- **APA 7th** - Psychology, social sciences
- **ASA** - Sociology journals
- **Chicago Author-Date** - General humanities/social sciences
- **Other** - Specify

### 5. Verify Zotero Access

Test the Zotero MCP connection:
```
Use ToolSearch to load: mcp__zotero-mcp__zotero_search_items
Then run a test search for a known author
```

If Zotero is not accessible, inform the user before proceeding.

## Output: Intake Report

Create a brief report:

```markdown
# Bibliography Builder: Intake Report

## Document
- **File**: [path]
- **Format**: [md/docx/txt]
- **Word count**: ~[X]

## Citation Style Detected
- **Format**: Author-Year (parenthetical + narrative)
- **Connector**: [and / &]
- **Page numbers**: [yes/no, format]
- **Multi-citation separator**: [semicolon]

## Counts
- **Citation instances**: ~[X]
- **Estimated unique**: ~[X]

## Output Format Requested
- **Style**: [APA 7th / ASA / Chicago / Other]

## Zotero Status
- **Connection**: [Active / Not available]
- **Test search**: [Successful / Failed]
```

## Pause Point

Present the intake report to the user. Confirm:
1. Citation patterns detected correctly?
2. Output format confirmed?
3. Zotero connection working?

Once confirmed, proceed to Phase 1: Citation Extraction.
