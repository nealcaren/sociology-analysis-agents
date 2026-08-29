# Phase 3: Issue Review

## Why This Phase Matters

Even after matching, issues may remain. This phase provides a systematic review before generating the final bibliography, catching problems that would otherwise appear in the output.

## Your Tasks

### 1. Compile Issue Summary

Aggregate all issues from previous phases:

**Missing Items:**
- Citations not found in Zotero
- Decision: Skip, add to Zotero, or mark as "[citation needed]"

**Ambiguous Matches:**
- Multiple candidates for same citation
- User decisions from Phase 2

**Year Discrepancies:**
- Author found but year differs from citation
- May indicate typo in manuscript or Zotero

**Et Al. Verification:**
- All "et al." citations should now have full author lists
- Verify these match the manuscript's usage

### 2. Cross-Check for Consistency

**Same author, multiple works:**
- If "Smith 2020" and "Smith 2021" both cited, are they the same Smith?
- If "Smith 2020a" and "Smith 2020b" cited, are both in Zotero?

**Name consistency:**
- Is "García" always spelled the same way?
- Are co-authors consistent? (Smith and Jones vs. Smith and Brown)

**Citation/reference match:**
- Every in-text citation should have a reference
- Are there Zotero items that were matched but perhaps shouldn't be? (false positives)

### 3. Generate Issue Report

Categorize issues by severity:

**Critical (must resolve):**
- Missing references that will leave gaps
- Clear mismatches

**Warning (should review):**
- Name variations
- Possible false positives

**Info (for awareness):**
- Et al. expansions
- Year suffix assignments

### 4. Get User Resolutions

For each critical issue, document the resolution:

| Issue | Resolution | Action |
|-------|------------|--------|
| Brown 2018 not found | Skip | Omit from bibliography |
| Jones 2019 ambiguous | Use DEF456 | "Organizational theory" article |
| Smith year mismatch (2019 vs 2020) | Manuscript error | Will note; use 2019 from Zotero |

## Output: Issues Report

Create `issues-report.md`:

```markdown
# Issue Review Report

## Summary

| Category | Count |
|----------|-------|
| Citations extracted | [X] |
| Successfully matched | [X] |
| Issues identified | [X] |
| Issues resolved | [X] |
| Remaining unresolved | [X] |

## Critical Issues

### Missing References

| Citation | Decision | Notes |
|----------|----------|-------|
| Brown 2018 | SKIP | Author confirmed not needed |
| Williams 2021 | ADD | User will add to Zotero |

### Resolved Ambiguities

| Citation | Selected Match | Rationale |
|----------|----------------|-----------|
| Jones 2019 | DEF456 | Context indicates organizational theory article |

## Warnings

### Year Discrepancies

| Citation | Manuscript | Zotero | Resolution |
|----------|------------|--------|------------|
| Smith 2020 | 2020 | 2019 | Use Zotero (2019); manuscript has typo |

### Name Variations

| Manuscript Form | Zotero Form | Status |
|-----------------|-------------|--------|
| García | Garcia | Acceptable variation |

## Information

### Et Al. Expansions

| Citation | Full Author List |
|----------|------------------|
| García et al. 2021 | García, M., López, R., & Martín, S. |
| Johnson et al. 2020 | Johnson, A., Williams, B., Davis, C., & Miller, D. |

## Final Citation Count

- **Total unique citations**: [X]
- **With valid Zotero match**: [X]
- **Skipped (unresolved)**: [X]

## Ready for Bibliography Generation

All issues have been reviewed and resolved. Proceeding to Phase 4.
```

## Pause Point

Present the issue report to the user. Confirm:
1. All resolutions are correct?
2. Skipped citations are intentional?
3. Ready to generate the final bibliography?

Once confirmed, proceed to Phase 4: Bibliography Generation.
