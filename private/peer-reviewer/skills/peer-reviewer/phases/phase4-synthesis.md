# Phase 4: Synthesis & Response Strategy

## Why This Phase Matters

Multiple reviews generate multiple perspectives—some convergent, some divergent. This phase aggregates feedback, identifies patterns, classifies the work required, and helps the author develop a strategic response. Not all feedback is equal; some concerns are fundamental while others are preferences. This phase helps authors prioritize.

---

## Your Tasks

### 1. Catalog All Feedback

Create a comprehensive inventory of all concerns and recommendations:

```markdown
## Feedback Inventory

### Major Concerns

| ID | Reviewer | Section | Concern | Recommendation |
|----|----------|---------|---------|----------------|
| M1 | Lareau | Theory | Concept application unclear | Specify how cultural capital operates in this context |
| M2 | Methods | Methods | Sampling strategy | Clarify theoretical saturation assessment |
| M3 | Methods | Findings | Analytic transparency | Add coding examples |
| M4 | Critical | Theory | Missing structural analysis | Engage macro-level constraints |

### Minor Concerns

| ID | Reviewer | Section | Concern | Recommendation |
|----|----------|---------|---------|----------------|
| m1 | Lareau | Theory | Citation format | Update Lareau 2011 citation |
| m2 | Methods | Methods | Interview protocol | Clarify probe questions |
| m3 | Critical | Findings | Case selection | Justify excluded cases |
```

### 2. Identify Convergent Concerns

Find concerns raised by multiple reviewers:

```markdown
## Convergent Concerns

### CC1: [Concern Title]
**Raised by**: Reviewer 1, Reviewer 2
**Core issue**: [What multiple reviewers agree is problematic]
**Why it matters**: [The shared reasoning]
**Implication**: [This is likely a real issue that needs addressing]

### CC2: [Concern Title]
**Raised by**: Reviewer 1, Reviewer 3
**Core issue**: [What multiple reviewers agree is problematic]
**Why it matters**: [The shared reasoning]
**Implication**: [This is likely a real issue that needs addressing]
```

Convergent concerns are higher priority—if multiple perspectives flag the same issue, it's likely a genuine weakness.

### 3. Identify Divergent Concerns

Find concerns specific to one perspective:

```markdown
## Divergent Concerns

### DC1: [Concern Title]
**Raised by**: Reviewer 2 only
**Core issue**: [The specific concern]
**Perspective-specific because**: [Why only this reviewer raises it]
**Assessment**: [Is this a valid concern for this manuscript, or a preference specific to this tradition?]

### DC2: [Concern Title]
**Raised by**: Reviewer 3 only
**Core issue**: [The specific concern]
**Perspective-specific because**: [Why only this reviewer raises it]
**Assessment**: [Valid concern vs. perspective preference]
```

Divergent concerns require judgment: some reflect real blind spots, others reflect preferences that don't apply to this project's goals.

### 4. Classify Response Types

For each concern, classify the appropriate response:

```markdown
## Response Classification

### Quick Fixes (Can address immediately)
| ID | Concern | Action Required | Time |
|----|---------|-----------------|------|
| m1 | Citation format | Update citation | 5 min |
| m2 | Probe questions | Add sentence to methods | 10 min |

### Minor Revisions (Require some rewriting)
| ID | Concern | Action Required | Sections Affected |
|----|---------|-----------------|-------------------|
| M1 | Concept application | Expand theory paragraph | Theory |
| m3 | Case selection | Add justification paragraph | Methods |

### Major Revisions (Require structural changes)
| ID | Concern | Action Required | Scope |
|----|---------|-----------------|-------|
| M2 | Sampling strategy | Rewrite methods section | Methods (full) |
| M3 | Analytic transparency | Add coding appendix + revise findings | Findings + Appendix |

### Acknowledge but Decline
| ID | Concern | Reason to Decline | Response |
|----|---------|-------------------|----------|
| M4 | Missing structural analysis | Outside project scope; would require different study | Acknowledge as limitation, explain scope |
```

### 5. Assess Overall Revision Scope

Determine the overall level of revision needed:

```markdown
## Revision Scope Assessment

### Quantitative Summary
- **Quick fixes**: [N]
- **Minor revisions**: [N]
- **Major revisions**: [N]
- **Acknowledge/decline**: [N]

### Most Affected Sections
1. [Section]: [N concerns, including M major]
2. [Section]: [N concerns, including M major]
3. [Section]: [N concerns, including M major]

### Overall Assessment
**Revision level**: [Minor / Moderate / Major / Fundamental]

**Rationale**: [Why this level]

**Feasibility**: [Can be addressed in single revision round / May require multiple rounds]
```

### 6. Develop Response Strategy

Create a prioritized action plan:

```markdown
## Response Strategy

### Priority 1: Convergent Concerns (Address First)
These concerns are raised by multiple reviewers and represent genuine weaknesses.

1. **[CC1 Title]**
   - Action: [Specific action]
   - Sections: [Affected sections]
   - Approach: [How to address]

2. **[CC2 Title]**
   - Action: [Specific action]
   - Sections: [Affected sections]
   - Approach: [How to address]

### Priority 2: High-Impact Divergent Concerns
These are raised by one reviewer but represent valid improvements.

1. **[DC Title]**
   - Action: [Specific action]
   - Rationale: [Why address despite being divergent]

### Priority 3: Minor Revisions
Address after major concerns are resolved.

[List minor revisions in order]

### Priority 4: Quick Fixes
Address during final polish.

[List quick fixes]

### Acknowledge but Decline
Prepare responses for these concerns.

[List with response drafts]
```

### 7. Draft Response Notes

For concerns being declined or partially addressed, draft response language:

```markdown
## Response Drafts

### For [Declined Concern]

**Reviewer concern**: [Summarize]

**Draft response**:
> "We thank the reviewer for raising the importance of [X]. While we agree that [X] is valuable, our study was designed to [Y], which required [Z] approach. We have added a sentence in the limitations section acknowledging this scope boundary. Future research could productively explore [X]."

### For [Partially Addressed Concern]

**Reviewer concern**: [Summarize]

**What we're doing**: [Partial response]

**What we're not doing**: [What's declined]

**Draft response**:
> "We appreciate this suggestion and have [action taken]. However, [reason for partial response]."
```

### 8. Create and Save Synthesis Memo

**IMPORTANT**: The synthesis memo MUST be saved to a markdown file, not just displayed in conversation. Users need these documents for reference.

Compile everything into a user-facing synthesis and save it:

```markdown
# Review Synthesis Memo

## Overview

**Reviewers**: [List]
**Total concerns**: [N major, N minor]
**Convergent concerns**: [N]
**Overall revision level**: [Assessment]

## Key Takeaways

### What's Working
[Summary of strengths across reviews]

### What Needs Work
[Summary of convergent and high-priority concerns]

### Strategic Decisions Needed
[Any decisions where user input is required]

## Recommended Response Strategy

[Summary of prioritized approach]

## Next Steps

1. [ ] User confirms response strategy
2. [ ] Begin Phase 5 revision support (if requested)
3. [ ] Address concerns in priority order
```

---

## Output Files to Create

**MANDATORY**: All synthesis outputs must be saved as markdown files. Do not skip file creation.

Save to project analysis folder (same folder as Phase 3 reviews):

1. **synthesis-memo.md** - User-facing summary (REQUIRED - save this first)
2. **feedback-inventory.md** - Complete catalog of all concerns
3. **convergent-concerns.md** - Analysis of shared concerns
4. **divergent-concerns.md** - Analysis of perspective-specific concerns
5. **response-classification.md** - Classification of response types
6. **response-strategy.md** - Prioritized action plan
7. **response-drafts.md** - Draft language for declined concerns

At minimum, **synthesis-memo.md** must always be created. Other files can be combined into the synthesis memo if the review scope is modest.

---

## Guiding Principles

### Convergence Signals Validity
If multiple perspectives flag the same issue, it's probably real. Prioritize these.

### Divergence Requires Judgment
One reviewer's concern may be valid or may be a perspective-specific preference. Help the user decide.

### Not All Feedback Is Equal
Some concerns are fundamental; others are stylistic. Help the user distinguish.

### Decline Thoughtfully
It's okay to not address everything, but provide reasoned responses.

### Author Retains Control
The user decides which concerns to address and how. This is guidance, not mandate.

---

## When You're Done

Report to the orchestrator:
- Synthesis complete
- Convergent concerns identified: [N]
- Divergent concerns identified: [N]
- Recommended revision level: [Level]
- Response strategy drafted
- Ready for user confirmation

Example summary:
> "**Synthesis complete**. 4 major concerns, 5 minor concerns across 3 reviewers. 2 convergent concerns (both re: theoretical application and analytic transparency). 2 divergent concerns (structural analysis from Critical reviewer—recommend acknowledge/decline; methods detail from Interview reviewer—recommend minor revision). **Recommended revision level: Moderate**. Main work: expand theory application (Priority 1), add coding examples (Priority 1), clarify sampling (Priority 2). Ready for user to confirm strategy before revision support."
