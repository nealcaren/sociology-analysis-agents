# Phase 4: Bibliography Generation

## Why This Phase Matters

This is the deliverable phase. All the extraction, matching, and review work culminates in a properly formatted bibliography ready for the manuscript.

## Your Tasks

### 1. Retrieve Full Metadata

For each matched citation, get complete bibliographic data from Zotero:
- All authors (full names)
- Publication year
- Title
- Journal/Book/Source
- Volume, issue, pages
- DOI or URL
- Item type (article, book, chapter, etc.)

Use `mcp__zotero-mcp__zotero_get_item_metadata` with each Zotero key.

### 2. Format According to Style

Apply the requested citation style (confirmed in Phase 0).

#### APA 7th Edition

**Journal Article:**
```
Author, A. A., & Author, B. B. (Year). Title of article in sentence case.
    *Journal Name in Title Case*, *Volume*(Issue), Page–Page.
    https://doi.org/xxxxx
```

**Book:**
```
Author, A. A. (Year). *Title of book in sentence case* (Edition ed.).
    Publisher.
```

**Chapter in Edited Book:**
```
Author, A. A. (Year). Title of chapter. In E. E. Editor (Ed.), *Title of book*
    (pp. xx–xx). Publisher.
```

**Key APA rules:**
- Use "&" before last author
- Sentence case for article/chapter titles
- Title case for journal names
- Italicize journal name and volume
- Include DOI as hyperlink when available

#### ASA (American Sociological Association)

**Journal Article:**
```
Author, First A. and First B. Author. Year. "Title of Article in Title Case."
    *Journal Name* Volume(Issue):Page–Page.
```

**Book:**
```
Author, First A. Year. *Title of Book in Title Case*. Place: Publisher.
```

**Key ASA rules:**
- Use "and" before last author
- Title case for all titles
- Quotation marks around article titles
- No DOI in standard format
- Include publisher location

#### Chicago Author-Date

**Journal Article:**
```
Author, First A., and First B. Author. Year. "Title of Article in Title Case."
    *Journal Name* Volume (Issue): Page–Page. https://doi.org/xxxxx.
```

**Book:**
```
Author, First A. Year. *Title of Book in Title Case*. Place: Publisher.
```

**Key Chicago rules:**
- Use "and" before last author
- Title case for all titles
- Spaces around issue number in parentheses
- En-dash for page ranges
- DOI at end with period

### 3. Handle Special Cases

**Multiple works, same author, same year:**
- Add letter suffix: 2020a, 2020b
- Order alphabetically by title

**6+ authors:**
- APA: First 19 authors, then "..." and last author
- ASA: First 3 authors, then "et al."
- Chicago: First 10 authors, then "et al."

**Organizations as authors:**
- Use full name first time
- Note any abbreviation for in-text use

**No author:**
- Begin with title
- Alphabetize by first significant word

**No date:**
- APA: (n.d.)
- ASA: N.d.
- Chicago: n.d.

### 4. Sort Bibliography

Alphabetical by first author's last name, then:
1. Single-author works before multi-author
2. Two-author before three-author
3. Chronologically within same author(s)
4. Alphabetically by title for same author + year

### 5. Format Output

Generate clean markdown:

```markdown
# References

Abbott, Andrew. 2014. *The System of Professions: An Essay on the
    Division of Expert Labor*. Chicago: University of Chicago Press.

Bearman, Peter and Paolo Parigi. 2004. "Cloning Headless Frogs and
    Other Important Matters: Conversation Topics and Network Structure."
    *Social Forces* 83(2):535–57.

Smith, Jane A., John B. Jones, and Mary C. Williams. 2020. "Movement
    Dynamics in Contemporary Activism." *American Sociological Review*
    85(3):456–78. https://doi.org/10.1177/0003122420912345.
```

Use hanging indent (4 spaces) for continuation lines.

## Output: Final Bibliography

Create `bibliography.md`:

```markdown
# References

[Formatted bibliography entries, sorted alphabetically]

---

## Generation Notes

- **Total references**: [X]
- **Format**: [APA 7th / ASA / Chicago]
- **Generated**: [Date]
- **Skipped citations**: [X] (listed in issues-report.md)
```

## Quality Checks

Before delivering, verify:

1. **All matched citations included** - Cross-check against Phase 2 matches
2. **Alphabetical order correct** - Check sorting, especially for names with particles (de, van, etc.)
3. **Formatting consistent** - Italics, punctuation, capitalization
4. **DOIs working** - If included, verify format
5. **No duplicates** - Each work appears once
6. **Year suffixes applied** - Where same author has multiple works in same year

## Delivery

Present the bibliography to the user with:
1. The formatted bibliography file
2. Summary of what was included/excluded
3. Any notes about formatting decisions
4. Reminder to verify against their specific journal requirements

---

## Bibliography Complete

The bibliography is now ready for inclusion in the manuscript. User should:
1. Review for any remaining issues
2. Check against target journal's specific requirements
3. Verify all in-text citations have corresponding references
4. Add any missing items that were skipped
