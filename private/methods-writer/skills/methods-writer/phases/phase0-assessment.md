# Phase 0: Assessment

You are executing Phase 0 of methods-writer. Your goal is to gather study information and select the appropriate pathway for the Methods section.

## Why This Phase Matters

Methods sections follow predictable patterns based on study complexity and population characteristics. Selecting the wrong pathway leads to either under-documentation (risking reviewer pushback) or over-documentation (wasting precious word count). This phase ensures deliberate pathway selection based on your study's actual needs.

---

## Your Tasks

### 1. Gather Study Information

Collect from the user:

**Required**:
- Sample size (N)
- Population description
- Recruitment approach
- Interview format and duration
- Analysis approach
- Data collection dates and location

**For Pathway Selection**:
- Is the population vulnerable or marginalized?
- Is the design complex (multi-site, comparative, longitudinal)?
- Are there access challenges or gatekeeper relationships?
- Are there journal word limits or space constraints?

### 2. Apply the Pathway Decision Tree

Work through this diagnostic:

```
PATHWAY DECISION TREE

1. Is the population VULNERABLE or MARGINALIZED?
   - Incarcerated, detained, legally precarious (e.g., undocumented)
   - Survivors of violence, abuse, or trauma
   - Sex workers, gang members, or other stigmatized groups
   - Anyone whose participation requires extra ethical safeguards

   → YES to any: DETAILED PATHWAY

2. Is the design COMPLEX?
   - Multi-site (2+ locations or organizations)
   - Comparative (systematic comparison across groups)
   - Longitudinal (repeated interviews over time)
   - Large sample (100+ interviews)
   - Merged data sources (interviews + survey + archival)
   - Significant access challenges requiring documentation

   → YES to any: DETAILED PATHWAY

3. Are there SPACE CONSTRAINTS or is METHODS SECONDARY?
   - Strict journal word limits (methods capped at 500-700 words)
   - Theory-building article where methods are routine
   - Very straightforward design (convenience sample, standard protocol)
   - Pilot study with limited claims

   → YES: EFFICIENT PATHWAY

4. None of the above apply?

   → STANDARD PATHWAY (DEFAULT)
```

### 3. Review Pathway Profile

Once you have a candidate pathway, consult the detailed profile:
- `pathways/efficient.md` (600-900 words)
- `pathways/standard.md` (1,200-1,500 words)
- `pathways/detailed.md` (2,000-3,000 words)

Verify the profile matches the user's study characteristics.

### 4. Assess Optional Components

Based on study characteristics, determine whether to include:

**Positionality** (17% of corpus):
- [ ] Notable interviewer-respondent identity mismatch
- [ ] Vulnerable population where identity affects disclosure
- [ ] Researcher identity shaped access or rapport
- [ ] Topic is sensitive and researcher position matters

**Ethical Considerations Paragraph** (for vulnerable populations):
- [ ] Non-standard consent (verbal, waived)
- [ ] Information security measures
- [ ] Topics deliberately not asked
- [ ] Protections for legally precarious participants

**Response/Refusal Rates**:
- [ ] Significant refusal rate that affects sample interpretation
- [ ] Institutional recruitment with documented response

### 5. Write Assessment Memo

Create a summary with:

```markdown
# Methods Section Assessment

## Study Summary
- **Sample**: [N] interviews with [population]
- **Recruitment**: [approach]
- **Protocol**: [format], [duration range]
- **Analysis**: [approach with citation]
- **Dates/Location**: [when and where]

## Pathway Selection Analysis
- [Walk through decision tree logic]
- [Note which triggers apply or don't apply]

## Recommended Pathway
**[Efficient/Standard/Detailed]**

### Rationale
- [Why this pathway fits]
- [What characteristics drove the selection]

### Alternative Considered (if applicable)
- [Why rejected alternative]

## Pathway Implications
- **Target word count**: [range]
- **Table**: [Required/Recommended/Omit]
- **Subsections**: [recommendation]
- **Positionality**: [Include/Omit with rationale]

## Optional Components to Include
- [ ] Positionality
- [ ] Ethical considerations paragraph
- [ ] Response/refusal rates
- [ ] Population comparison
- [ ] Specific codes listed

## Questions for User
- [Any clarifying questions needed before drafting]
```

### 6. Present Recommendation

Present to user:
- Recommended pathway with clear rationale
- Target word count and structural expectations
- Optional components to include
- Any questions before proceeding

---

## Guiding Principles

### Standard Is the Default
When in doubt, choose Standard. It's the most common pathway (61%) and fits most interview studies. Efficient and Detailed are for specific circumstances.

### Vulnerability Trumps Everything
If the population is vulnerable, use Detailed regardless of other factors. Ethical transparency is non-negotiable.

### Space Constraints Are Real
If the journal caps methods at 700 words, Efficient isn't optional—it's required. Don't fight the format.

### Complexity Deserves Documentation
Multi-site, comparative, and longitudinal designs require explanation. Readers need to understand your case selection logic and timing.

### Positionality Is Not Mandatory
Only 17% of corpus articles include positionality. Include it when specific triggers apply, not by default.

---

## Output Files to Create

1. **assessment-memo.md** - Full assessment with pathway recommendation
2. (Optional) **questions-for-user.md** - If clarification needed

---

## When You're Done

Report to the orchestrator:
- Recommended pathway
- Key rationale (2-3 sentences)
- Any outstanding questions
- Readiness assessment for Phase 1

Example summary:
> "I recommend **Standard pathway** (1,200-1,500 words) for this study of 47 middle-class parents. The population is not vulnerable, the design is straightforward (single-site, snowball sampling), and there are no unusual space constraints. I recommend including a demographic table but omitting positionality since the interviewer-respondent characteristics are aligned. Ready for Phase 1: Drafting."
