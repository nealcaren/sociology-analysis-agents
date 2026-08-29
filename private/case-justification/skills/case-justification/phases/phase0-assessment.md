# Phase 0: Assessment

You are executing Phase 0 of case-justification. Your goal is to gather study information and select the appropriate cluster for the case justification section.

## Why This Phase Matters

Case justification sections follow predictable patterns based on study characteristics. Selecting the wrong cluster leads to mismatched content (e.g., writing a Deep Historical section when Standard would suffice) or structural errors (e.g., positioning Policy-Driven content after theory). This phase ensures deliberate cluster selection based on your study's actual needs.

---

## Your Tasks

### 1. Gather Case Information

Collect from the user:

**Required**:
- Site name and location
- Population studied
- Key contextual features (geographic, historical, policy, institutional)
- How the case relates to the theoretical framework

**For Cluster Selection**:
- Single site or multiple sites?
- Is historical development central to the case?
- Does policy/institutional context need to precede theory?
- Is the site well-known or does it require extensive introduction?
- Are there space constraints?

### 2. Apply the Cluster Decision Tree

Work through this diagnostic:

```
CLUSTER DECISION TREE

1. Does your case context need to PRECEDE your theoretical framework?
   - Is the policy/law/institution ITSELF the phenomenon you theorize about?
   - Must readers understand "what" before "why"?
   - Does the institutional context motivate the theory?

   --> YES: POLICY-DRIVEN CLUSTER
       Position: BEFORE theory
       Target: 650-900 words

2. Do you have MULTIPLE RESEARCH SITES that you will compare?
   - Two or more distinct locations or organizations
   - Parallel data collection across sites
   - Site differences provide analytical leverage

   --> YES: COMPARATIVE CLUSTER
       Parallel structure, usually with table
       Target: 1,000-1,500 words

3. Is HISTORICAL DEVELOPMENT central to your case?
   - Social movement tracking protest cycles
   - Policy tracing reform trajectories over time
   - Multiple named episodes or periods
   - "How we got here" matters analytically

   --> YES: DEEP HISTORICAL CLUSTER
       Chronological organization, multiple subsections
       Target: 1,500-2,500 words

4. Is your case WELL-KNOWN and requires MINIMAL introduction?
   - Site is famous/familiar (major city, well-known institution)
   - Mixed-methods design where qualitative follows quantitative
   - Phenomenon matters more than site specifics
   - Severe space constraints
   - Access-driven case selection

   --> YES: MINIMAL CONTEXT CLUSTER
       Brief, 1-3 paragraphs
       Target: 300-500 words

5. None of the above apply?

   --> STANDARD CONTEXT CLUSTER (DEFAULT)
       Balanced single-site context
       Target: 700-1,000 words
```

### 3. Review Cluster Profile

Once you have a candidate cluster, consult the detailed profile:
- `clusters/minimal.md` (300-500 words)
- `clusters/standard.md` (700-1,000 words)
- `clusters/historical.md` (1,500-2,500 words)
- `clusters/comparative.md` (1,000-1,500 words)
- `clusters/policy.md` (650-900 words)

Verify the profile matches the user's study characteristics.

### 4. Assess Components to Include

Based on the cluster and study characteristics, determine which components to include:

**Geographic Context**:
- [ ] Location and regional characteristics
- [ ] Urban/rural features
- [ ] Relevant geography

**Historical Background**:
- [ ] Key historical developments
- [ ] How we got to the present
- [ ] Named periods or episodes (Deep Historical)

**Policy/Legal Context**:
- [ ] Relevant laws or policies
- [ ] Institutional arrangements
- [ ] Political environment

**Demographic Profile**:
- [ ] Population statistics
- [ ] Racial/ethnic composition
- [ ] Socioeconomic characteristics

**Institutional Description**:
- [ ] Organizations involved
- [ ] Institutional features
- [ ] Structural characteristics

**Sampling Rationale**:
- [ ] Why this case?
- [ ] Theoretical fit argument
- [ ] Intrinsic interest argument

### 5. Determine Position

**CRITICAL**: Only Policy-Driven sections go BEFORE theory. All other clusters position AFTER theory.

If user indicates the case must precede theory but doesn't fit Policy-Driven triggers, discuss whether:
- The case section should actually go after theory
- The study actually IS Policy-Driven
- There's a mismatch in how the article is structured

### 6. Write Assessment Memo

Create a summary with:

```markdown
# Case Justification Assessment

## Case Summary
- **Site**: [Name and location]
- **Population**: [Who was studied]
- **Key Features**: [Geographic, historical, policy, institutional]
- **Relationship to Theory**: [How case connects to framework]

## Cluster Selection Analysis

### Decision Tree Walk-Through
1. Policy context must precede theory? [YES/NO - reasoning]
2. Multiple sites compared? [YES/NO - reasoning]
3. Historical development central? [YES/NO - reasoning]
4. Well-known, minimal intro needed? [YES/NO - reasoning]

## Recommended Cluster
**[Minimal/Standard/Deep Historical/Comparative/Policy-Driven]**

### Rationale
- [Why this cluster fits]
- [What characteristics drove the selection]

### Alternative Considered (if applicable)
- [Why rejected alternative]

## Cluster Implications
- **Target word count**: [range]
- **Position**: [BEFORE/AFTER theory]
- **Subsections**: [number expected]
- **Table**: [Required/Recommended/Omit]

## Components to Include
- [ ] Geographic Context
- [ ] Historical Background
- [ ] Policy/Legal Context
- [ ] Demographic Profile
- [ ] Institutional Description
- [ ] Sampling Rationale

## Recommended Opening Move
[Phenomenon-Site-Link / Geographic-Introduction / Historical-Periodization / Institutional-Description / Research-Setting]

## Recommended Justification Strategy
[Intrinsic-Interest / Theoretical-Fit / Empirical-Extremity / Variation-Leverage / Access-Driven]

## Questions for User
- [Any clarifying questions needed before drafting]
```

### 7. Present Recommendation

Present to user:
- Recommended cluster with clear rationale
- Target word count and structural expectations
- Position (before or after theory)
- Components to include
- Any questions before proceeding

---

## Guiding Principles

### Standard Is the Default
When in doubt, choose Standard Context. It's the most common cluster (34%) and fits most single-site interview studies. Other clusters are for specific circumstances.

### Position Is Non-Negotiable
Policy-Driven goes BEFORE theory. All others go AFTER. This is not a stylistic choice; it reflects the logical relationship between case and theory.

### Historical Complexity Requires Space
If the case involves named episodes, chronological development, or movement history, it probably needs Deep Historical treatment. Don't compress this into Standard.

### Comparison Requires Parallel Structure
If studying multiple sites, each must receive comparable coverage. The variation-leverage statement ("By comparing X and Y, we can...") is essential.

### Tables Signal Comparison
If you have demographic or characteristic data to compare across sites or pre/post, use a table. Tables belong almost exclusively in Comparative sections.

---

## Output Files to Create

1. **assessment-memo.md** - Full assessment with cluster recommendation
2. (Optional) **questions-for-user.md** - If clarification needed

---

## When You're Done

Report to the orchestrator:
- Recommended cluster
- Key rationale (2-3 sentences)
- Any outstanding questions
- Readiness assessment for Phase 1

Example summary:
> "I recommend **Standard Context** (700-1,000 words, positioned after theory) for this study of Latino immigration experiences in Kansas. The site is not widely known, the design is single-site, and historical development is background rather than central. I recommend including geographic context, brief historical background, policy environment, and demographic statistics. Ready for Phase 1: Drafting."
