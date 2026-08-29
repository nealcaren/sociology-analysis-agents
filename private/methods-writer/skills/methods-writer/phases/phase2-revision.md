# Phase 2: Revision

You are executing Phase 2 of methods-writer. Your goal is to calibrate the draft against benchmarks, verify component coverage, and polish the prose to publication quality.

## Why This Phase Matters

Methods sections are scrutinized by reviewers for both completeness and concision. Under-documentation raises credibility concerns; over-documentation wastes precious word count. This phase ensures your Methods section matches field norms and accomplishes its goals efficiently.

---

## Your Tasks

### 1. Word Count Calibration

Compare actual word count to pathway targets:

| Pathway | Target | Acceptable Range |
|---------|--------|------------------|
| Efficient | 700 | 600-900 |
| Standard | 1,350 | 1,200-1,500 |
| Detailed | 2,500 | 2,000-3,000 |

**If over target**:
- [ ] Cut method-justification language ("Interviews are appropriate because...")
- [ ] Move prose demographics to table
- [ ] Compress recruitment channel descriptions
- [ ] Remove intercoder reliability if not required
- [ ] Shorten analysis process description

**If under target**:
- [ ] Add recruitment channel specifics
- [ ] Expand analysis process (coding rounds, software)
- [ ] Add location and compensation details
- [ ] Consider adding sample question from interview guide
- [ ] Add duration median if only range provided

### 2. Component Verification

Check all required components are present:

#### All Pathways
- [ ] Sample N stated clearly
- [ ] Population described
- [ ] Recruitment approach named
- [ ] Duration reported (range minimum)
- [ ] Analysis approach named with citation

#### Efficient Pathway
- [ ] Demographics in prose (no table)
- [ ] No extensive case justification
- [ ] No positionality (unless essential)
- [ ] Confidentiality statement present

#### Standard Pathway
- [ ] Table reference if table used
- [ ] Software mentioned
- [ ] Recording/transcription noted
- [ ] Compensation mentioned
- [ ] Positionality included IF triggers apply

#### Detailed Pathway
- [ ] Demographic table present
- [ ] Response/refusal rates if relevant
- [ ] Ethical considerations if vulnerable population
- [ ] Positionality discussion present
- [ ] Specific codes listed in analysis
- [ ] Subsection headers used

### 3. Opening Move Check

Verify opening follows study-led pattern (88% of corpus):

**Good openings**:
- "I draw from X interviews with [population]."
- "This study draws on X interviews conducted with..."
- "We analyze X in-depth interviews from..."

**Problematic openings** (revise if present):
- "Qualitative methods are appropriate because..."
- "Interviews allow researchers to..."
- "To understand [topic], I used interviews..."

### 4. Saturation Check

Verify no unwarranted saturation claims (only 4% of corpus):

**If saturation claimed**, consider replacing with:
- "Continued until key themes emerged across subgroups"
- "Sample size reflects comparative adequacy"
- "Recruitment continued until [pragmatic bound]"

**Acceptable saturation mentions** (rare):
- When genuinely using theoretical sampling with documented saturation
- When explicitly discussing sampling strategy literature

### 5. Positionality Check

Verify positionality is handled appropriately (only 17% include):

**Include positionality when**:
- [ ] Notable interviewer-respondent identity mismatch
- [ ] Vulnerable population where identity affects disclosure
- [ ] Researcher identity shaped access or rapport
- [ ] Topic is sensitive and researcher position matters

**Omit positionality when**:
- No significant identity mismatch
- Population is not vulnerable
- Access was straightforward
- Routine study with matched interviewers

### 6. Prose Quality Check

Review for common issues:

**Transitions**:
- [ ] Each component flows naturally to the next
- [ ] No abrupt topic shifts
- [ ] Final sentence sets up findings section (if applicable)

**Verb tense**:
- [ ] Past tense for data collection procedures
- [ ] Present tense for ongoing analysis insights (rare)

**Passive vs. active**:
- [ ] "I interviewed" or "We conducted" (active) preferred over "Interviews were conducted" (passive)
- [ ] First person acceptable in methods

**Specificity**:
- [ ] Duration is a range, not vague ("approximately an hour")
- [ ] Demographics are percentages or counts, not vague ("most were")
- [ ] Software is named, not generic ("qualitative software")

### 7. Citation Check

Verify citations are appropriate:

**Analysis approach**: Must cite if named
- Abductive (Timmermans and Tavory 2012)
- Grounded theory (Charmaz 2006; Strauss and Corbin 1990)
- Flexible coding (Deterding and Waters 2018)

**Methodological references** (optional but useful):
- Sampling strategy references
- Interview methodology references
- Coding approach extensions

### 8. Table Quality Check (if applicable)

If using a demographic table:

- [ ] Table number referenced in text
- [ ] Columns are meaningful (not just demographics but study-relevant characteristics)
- [ ] Percentages or N provided
- [ ] Categories are mutually exclusive
- [ ] "N" or "Total" row included

**For Detailed pathway**:
- [ ] Consider comparison column (sample vs. population)
- [ ] Note limitations if sample differs from population

---

## Quality Checklist by Pathway

### Efficient Pathway Checklist
- [ ] Under 900 words
- [ ] No table in methods body
- [ ] Study-led opening
- [ ] Recruitment in 1-2 sentences
- [ ] Duration range reported
- [ ] Analysis approach named with citation
- [ ] Confidentiality note at end
- [ ] No positionality (unless essential)
- [ ] No saturation claim

### Standard Pathway Checklist
- [ ] 1,200-1,500 words
- [ ] Table included OR good prose demographics
- [ ] Study-led opening
- [ ] Recruitment channels named
- [ ] Duration with bounds
- [ ] Recording/transcription mentioned
- [ ] Software named
- [ ] Multi-step coding process described
- [ ] Positionality IF triggers apply
- [ ] Confidentiality noted

### Detailed Pathway Checklist
- [ ] 2,000-3,000 words
- [ ] Table required
- [ ] Study-led opening with design framing
- [ ] Case/site justification included
- [ ] Recruitment channels + process
- [ ] Response/refusal rates if significant
- [ ] Duration with range and median
- [ ] Compensation mentioned
- [ ] Ethical considerations paragraph IF vulnerable
- [ ] Positionality discussion included
- [ ] Specific codes listed
- [ ] Subsection headers used

---

## Common Revision Moves

### To Shorten (over word count)

| Cut This | Save ~X Words |
|----------|---------------|
| Method justification opening | 30-50 |
| Redundant recruitment detail | 20-40 |
| Prose demographics (use table) | 100-200 |
| Intercoder reliability detail | 30-50 |
| Coding process elaboration | 50-100 |

### To Lengthen (under word count)

| Add This | Add ~X Words |
|----------|--------------|
| Recruitment channel specifics | 30-50 |
| Sample interview question | 20-40 |
| Location details | 20-30 |
| Compensation information | 15-25 |
| Duration median (not just range) | 10-15 |

---

## Output Files to Create

1. **methods-final.md** - Revised Methods section ready for submission
2. **revision-memo.md** - Notes on changes made and quality assessment

**Revision memo structure**:
```markdown
# Methods Section Revision Memo

## Word Count
- Draft: [X] words
- Target: [Y] words
- Final: [Z] words

## Components Verified
- [List all required components present]

## Changes Made
- [Bullet list of revisions]

## Quality Assessment
- Opening: [study-led / method-justified]
- Saturation: [claimed / alternative / silent]
- Positionality: [included / omitted / not applicable]
- Table: [yes / no / n/a for pathway]

## Remaining Concerns
- [Any issues user should review]
```

---

## When You're Done

Report to the orchestrator:
- Final word count
- All required components present (yes/no)
- Major revisions made
- Quality assessment summary
- Any remaining concerns for user

Example summary:
> "**Revision complete**. Final: 1,347 words (target: 1,350). All Standard pathway components present. Revisions: replaced method-justification opening with study-led opener, added software name, compressed recruitment by 40 words. Quality: study-led opening, no saturation claim, positionality appropriately omitted. No remaining concerns. Methods section ready for submission."
