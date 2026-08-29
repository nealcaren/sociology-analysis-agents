# Phase 3: Simulated Reviews

## Why This Phase Matters

This is where the personas come alive. Each constructed reviewer now reads the manuscript through their lens and writes a focused review. The goal is not to predict what an actual reviewer would say, but to surface concerns and perspectives that the author should consider. Honest, grounded feedback—even when critical—helps strengthen the manuscript.

---

## Your Tasks

### 1. Review Setup

For each reviewer, prepare the review context:

```markdown
## Review Assignment: [Reviewer Name]

**Persona file**: [path to persona profile]
**Focus sections**: [Theory + Findings] OR [Methods + Findings]
**Manuscript sections to read**: [List specific sections]
**Key questions to address**:
- Is my perspective/work represented?
- Is it represented accurately?
- Does the theoretical framework hold?
- Are the methods appropriate?
- Do the findings support the claims?
```

### 2. Conduct Each Review

For each reviewer, inhabit the persona and read the assigned sections carefully.

**Reading protocol**:

1. **First pass**: Read for overall argument and contribution
   - What is the author trying to do?
   - How does this relate to my perspective?

2. **Second pass**: Read for engagement with my work
   - Am I cited? Where and how?
   - Is my work represented accurately?
   - Are key concepts used correctly?

3. **Third pass**: Read for strengths and concerns
   - What does this manuscript do well?
   - Where are the gaps, errors, or missed opportunities?
   - What would strengthen this from my perspective?

### 3. Write the Review

**IMPORTANT**: Name reviewers for theoretical perspectives, not individual scholars. Even when sources come from one author, use the perspective name (e.g., "Emotions in Movements Perspective" not "Deborah Gould").

Use this template for each review:

```markdown
# Review from [Theoretical Perspective Name]

**Perspective**: [Brief description of this theoretical/methodological tradition]
**Reviewer focus**: [Theory + Findings] OR [Methods + Findings]
**Sections reviewed**: [List]
**Date**: [Date]

---

## Summary

[2-3 paragraphs summarizing the manuscript from this perspective. What is the author attempting? How does it relate to the literature this perspective cares about? What is the overall impression?]

---

## Strengths

### 1. [Strength Title]
[Specific strength with reference to manuscript. Quote or cite specific passages.]

### 2. [Strength Title]
[Specific strength with reference to manuscript.]

### 3. [Strength Title]
[Specific strength with reference to manuscript.]

---

## Concerns

### Major Concerns

#### 1. [Major Concern Title]
**Location**: [Section/paragraph reference]
**Issue**: [Clear statement of the problem]
**From my perspective**: [Why this matters given my theoretical/methodological commitments]
**Suggestion**: [What would address this concern]

#### 2. [Major Concern Title]
**Location**: [Section/paragraph reference]
**Issue**: [Clear statement of the problem]
**From my perspective**: [Why this matters]
**Suggestion**: [What would address this concern]

### Minor Concerns

#### 1. [Minor Concern Title]
**Location**: [Section/paragraph reference]
**Issue**: [Brief statement]
**Suggestion**: [Brief suggestion]

#### 2. [Minor Concern Title]
**Location**: [Section/paragraph reference]
**Issue**: [Brief statement]
**Suggestion**: [Brief suggestion]

---

## Representation Check

### Is Key Work from This Perspective Cited?
[Yes/No. If yes, which works? If no, should it be?]

### Is It Represented Accurately?
[Assessment of how this perspective's work is characterized in the manuscript]

### Suggested Corrections
[If any misrepresentations, provide specific corrections]

### Missing Engagement
[Work or concepts from this perspective that should be engaged but aren't]

---

## Specific Recommendations

1. **[Recommendation 1]**
   [Actionable recommendation with rationale]

2. **[Recommendation 2]**
   [Actionable recommendation with rationale]

3. **[Recommendation 3]**
   [Actionable recommendation with rationale]

---

## Overall Assessment

[1-2 paragraphs giving constructive overall assessment. What would make this manuscript stronger from this perspective? What is the path forward?]

**Disposition** (if this were an actual review):
- [ ] Accept
- [ ] Minor revisions
- [ ] Major revisions
- [ ] Revise and resubmit
- [ ] Reject

**Confidence**: [High / Medium / Low] — based on how well my persona sources inform this review
```

### 4. Ground Reviews in Persona

Throughout the review, ensure claims connect to the persona:

- Reference specific sources that inform your perspective
- Use language consistent with the persona's voice
- Focus on concerns that genuinely arise from this theoretical/methodological position
- Avoid generic critiques that any reviewer might make (unless they're also specific to this persona)

### 5. Calibrate Severity

Reviews should be:

- **Honest**: Don't soften genuine concerns to be nice
- **Constructive**: Frame critiques as paths to improvement
- **Specific**: Point to exact locations and provide actionable suggestions
- **Grounded**: Distinguish persona-specific concerns from general observations

**Severity calibration**:
- **Major concern**: Would significantly affect the argument's validity or contribution
- **Minor concern**: Worth addressing but doesn't undermine the core contribution

### 6. Save and Present Reviews to User

**IMPORTANT**: After completing each review, you MUST save it to a markdown file before presenting it to the user. Do not just display reviews in the conversation—they must be persisted as files.

**For each review**:
1. Save the review to `[analysis-folder]/review-[reviewer-name].md`
2. Then present a summary to the user
3. Wait for user acknowledgment before proceeding to the next reviewer

This allows the user to:
- Access reviews as reference documents later
- See how each perspective reads the manuscript
- Note any mischaracterizations of the persona
- Ask clarifying questions
- Adjust expectations for synthesis

---

## Output Files to Create

**MANDATORY**: All reviews must be saved as markdown files. Do not skip file creation.

Save to project analysis folder (create if needed):

1. **review-[perspective].md** - Complete review from first reviewer (use theoretical perspective name, not person name)
2. **review-[perspective].md** - Complete review from second reviewer
3. **review-[perspective].md** - Complete review from third reviewer (if applicable)
4. **review-summary.md** - Brief summary of all reviews for user

**Use theory-based file names** (not person names):
- `review-disengagement-typology.md` (not `review-corrigall-brown.md`)
- `review-emotions-movements.md` (not `review-gould.md`)
- `review-activist-careers.md` (not `review-fillieule.md`)

---

## Guiding Principles

### Inhabit, Don't Imitate
You're thinking from this perspective, not doing an impression. Use their concepts and concerns genuinely.

### Specific Over General
"The sampling strategy is unclear" is weak. "The sampling strategy doesn't clarify how theoretical saturation was assessed, which matters because..." is strong.

### Constructive Criticism
Every concern should come with a path forward. The goal is manuscript improvement.

### Acknowledge Persona Limits
If a concern is outside the persona's expertise, note that. Don't pretend certainty you don't have.

### Honest Dispositions
If the persona would genuinely recommend major revisions, say so. Don't inflate or deflate to be diplomatic.

---

## Common Review Pitfalls to Avoid

| Pitfall | Problem | Solution |
|---------|---------|----------|
| Generic critique | Concerns any reviewer might raise | Ground in persona-specific values |
| Strawman concerns | Critiques the persona wouldn't actually make | Return to sources, verify concern is authentic |
| All negative | Demoralizing and unhelpful | Find genuine strengths too |
| Vague suggestions | "Needs more theory" | Specify what theory, where, how |
| Persona drift | Review stops sounding like the persona | Re-read persona profile, use their language |

---

## When You're Done

After each review, report briefly:
- Review complete for [Reviewer Name]
- Major concerns: [count]
- Minor concerns: [count]
- Disposition: [assessment]
- Ready for user to read before next review

After all reviews:
- All reviews complete
- Summary of convergent/divergent concerns
- Ready for Phase 4 synthesis

Example summary:
> "**Reviews complete**. Reviewer 1 (Cultural Capital in Education): Generally supportive, 1 major concern (concept application), 3 minor concerns, disposition = minor revisions. Reviewer 2 (Interview Validity): More critical, 2 major concerns (sampling, analytic transparency), 2 minor concerns, disposition = major revisions. Reviewer 3 (Critical Education): Mixed, 1 major concern (structural analysis missing), 1 minor concern, disposition = revise and resubmit. **Convergent concerns**: All three note insufficient engagement with class-based mechanisms. Ready for synthesis."
