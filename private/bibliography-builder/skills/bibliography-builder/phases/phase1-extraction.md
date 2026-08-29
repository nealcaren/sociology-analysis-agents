# Phase 1: Citation Extraction

## Why This Phase Matters

Accurate extraction is the foundation. Missing a citation means an incomplete bibliography; mis-parsing a name means a failed Zotero match. This phase uses pattern matching to find all citations and normalize them for lookup.

## Your Tasks

### 1. Extract All Citations

Use regex patterns to find citations. Handle these patterns:

**Parenthetical citations:**
```python
# Single author
r'\(([A-Z][a-zà-ÿ\-\']+)\s+(\d{4}[a-z]?)\)'
# Example: (Smith 2020), (García 2019a)

# Two authors with "and"
r'\(([A-Z][a-zà-ÿ\-\']+)\s+and\s+([A-Z][a-zà-ÿ\-\']+)\s+(\d{4}[a-z]?)\)'
# Example: (Smith and Jones 2020)

# Two authors with "&"
r'\(([A-Z][a-zà-ÿ\-\']+)\s+&\s+([A-Z][a-zà-ÿ\-\']+)\s+(\d{4}[a-z]?)\)'
# Example: (Smith & Jones 2020)

# Et al.
r'\(([A-Z][a-zà-ÿ\-\']+)\s+et\s+al\.?\s+(\d{4}[a-z]?)\)'
# Example: (Smith et al. 2020)

# With page numbers
r'\(([A-Z][a-zà-ÿ\-\']+(?:\s+(?:and|&)\s+[A-Z][a-zà-ÿ\-\']+)?(?:\s+et\s+al\.?)?)\s+(\d{4}[a-z]?)[,:]?\s*(?:pp?\.?\s*)?\d+(?:[-–]\d+)?\)'
```

**Narrative citations:**
```python
# Author (Year)
r'([A-Z][a-zà-ÿ\-\']+(?:\s+(?:and|&)\s+[A-Z][a-zà-ÿ\-\']+)?(?:\s+et\s+al\.?)?)\s+\((\d{4}[a-z]?)\)'
# Example: Smith (2020), Smith and Jones (2020)
```

**Multiple citations in one parenthetical:**
```python
# Split on semicolon first, then parse each
r'\(([^)]+;\s*[^)]+)\)'
# Then split contents on '; ' and parse individually
```

### 2. Normalize Each Citation

For each extracted citation, create a normalized record:

| Field | Description |
|-------|-------------|
| `raw` | Original text as found |
| `first_author` | Last name of first author |
| `second_author` | Last name of second author (if any) |
| `et_al` | Boolean: true if "et al." present |
| `year` | Publication year |
| `year_suffix` | Letter suffix if present (a, b, c) |
| `page` | Page number(s) if present |

### 3. Deduplicate

- Combine identical citations (same author(s) + year)
- Track frequency (how many times each appears)
- Note variations (same work cited with/without pages)

### 4. Sort Alphabetically

Sort by:
1. First author last name
2. Year
3. Year suffix (a, b, c)

### 5. Flag Potential Issues

Mark citations that may cause problems:
- **Ambiguous names**: Common surnames (Smith, Lee, etc.)
- **Et al. citations**: Will need full author list from Zotero
- **Year suffixes**: May indicate multiple works by same author
- **Unusual formats**: Anything that didn't match standard patterns

### 6. Verify Extraction with Grep

**Critical step**: Use shell commands to independently verify the extraction caught everything. This catches citations that may have been missed by the initial regex patterns.

**Run these verification commands:**

```bash
# Find all parenthetical citations
grep -oE '\([A-Z][a-zA-Z-]+[^)]*[0-9]{4}[a-z]?\)' document.md | sort | uniq -c | sort -rn

# Find narrative citations (Author (Year) and Author's (Year))
grep -oE "[A-Z][a-zA-Z-]+[''']?s? \([0-9]{4}[a-z]?\)" document.md | sort | uniq

# Find all multi-citation parentheticals (contain semicolons)
grep -oE '\([^)]+;[^)]+\)' document.md | sort | uniq

# List all years mentioned (to cross-check against citations)
grep -oE '\b(19[89][0-9]|20[0-2][0-9])[a-z]?\b' document.md | sort | uniq -c | sort -rn
```

**Compare results:**
1. Count unique citations from grep output
2. Compare against your extracted list
3. Investigate any discrepancies:
   - Years in document that aren't citations (historical dates, sample info)
   - Citations grep found that regex missed
   - Edge cases (hyphenated names, accented characters, possessives)

**Common issues to check:**
- Names with internal capitals (McAdam, DeMichele, van Stekelenburg)
- Possessive forms (McAdam's (1989))
- Accented characters (García, Eklöf)
- Hyphenated names (Corrigall-Brown, Cohen-Eick)
- Three+ author citations with commas

If grep finds citations not in your list, add them before proceeding.

## Output: Citations Extracted

Create `citations-extracted.md`:

```markdown
# Extracted Citations

**Document**: [filename]
**Total instances**: [X]
**Unique citations**: [X]

## Citation List

| # | Citation | First Author | Year | Frequency | Notes |
|---|----------|--------------|------|-----------|-------|
| 1 | Smith 2020 | Smith | 2020 | 5 | |
| 2 | Smith and Jones 2019 | Smith | 2019 | 2 | Two authors |
| 3 | García et al. 2021 | García | 2021 | 3 | Et al. - need full list |
| 4 | Lee 2020a | Lee | 2020a | 1 | Year suffix |
| ... | ... | ... | ... | ... | ... |

## Potential Issues

- **Common names**: Smith (3 different years), Lee (2 different works 2020)
- **Et al. citations**: 5 citations need full author lists
- **Unusual patterns**: [any that needed manual parsing]

## Grep Verification

**Parenthetical citations found:**
```
[paste grep output here]
```

**Narrative citations found:**
```
[paste grep output here]
```

**Verification result:** [X] citations extracted, [X] confirmed by grep. [Match/Discrepancies noted]

## Raw Extraction Log

[Optional: list of all raw matches for verification]
```

## Pause Point

Present the extracted citations to the user. Ask:
1. Are all citations captured?
2. Any obvious misses or misparsings?
3. Ready to proceed to Zotero matching?

Once confirmed, proceed to Phase 2: Zotero Matching.
