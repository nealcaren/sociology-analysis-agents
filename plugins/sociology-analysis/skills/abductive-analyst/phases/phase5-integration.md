# Phase 5: Integration & Testing

You are executing Phase 5 of an abductive analysis. Your goal is to rigorously test the emerging theoretical framework against the full dataset, refine claims based on negative cases, and produce an integrated synthesis that articulates the theoretical contribution.

## The Logic of Integration & Testing

Abduction generates theoretical hypotheses; those hypotheses must then be tested through both inductive verification (does the pattern hold across cases?) and deductive testing (what would we expect to find if the theory is true?). Phase 5 completes the cycle by:

1. Testing propositions against all available data
2. Actively seeking disconfirmation
3. Refining theory based on negative cases
4. Producing an integrated theoretical framework
5. Articulating contribution and limitations

## Inputs

Before starting, read ALL prior phase outputs:
1. `/analysis/phase1-reports/` - Full dataset coding and summaries
2. `/analysis/phase2-reports/` - Theoretical casings
3. `/analysis/phase3-reports/` - Anomalies and variation
4. `/analysis/phase4-reports/` - Theoretical propositions and memos
5. `/theory/` - User-provided theoretical resources
6. Original interviews in `/interviews/` for re-analysis

## Your Tasks

### 1. Systematic Proposition Testing

For EACH theoretical proposition from Phase 4:

**a) Verification sweep**:
- Review every interview for evidence relevant to this proposition
- Document supporting instances
- Note the strength of support (strong, moderate, weak)

**b) Falsification attempt**:
- Actively search for evidence that would disconfirm the proposition
- Look for cases where the predicted pattern doesn't hold
- Examine cases where conditions are met but outcomes differ

**c) Alternative explanation check**:
- For each piece of supporting evidence, consider: could this be explained by an alternative theory?
- What evidence would distinguish between explanations?

### 2. Negative Case Analysis

For each negative case identified:

**Analysis framework**:
- Describe the case and how it contradicts the proposition
- Is this a true exception or a misunderstanding of the proposition?
- What is different about this case? (conditions, context, participant characteristics)
- Does this require:
  - Rejecting the proposition?
  - Modifying the proposition (adding scope conditions)?
  - Developing a new concept to account for the exception?
  - Recognizing multiple pathways/types?

**Outcome**: Revise propositions based on negative case analysis

### 3. Scope Condition Specification

For the refined theoretical framework, specify:
- **Where it applies**: What types of cases, contexts, populations?
- **Where it doesn't apply**: Boundary conditions, exclusions
- **What it explains**: Which phenomena fall within its scope?
- **What it doesn't explain**: What questions does it leave open?

Be specific and honest about limitations.

### 4. Internal Coherence Check

Examine the theoretical framework as a whole:
- Do the propositions fit together logically?
- Are there contradictions between propositions?
- Does the framework tell a coherent story?
- Are concepts defined consistently throughout?
- Is the level of abstraction appropriate and consistent?

### 5. Produce Integrated Synthesis

Write a comprehensive synthesis document that:

**a) States the theoretical argument**:
- What is the central theoretical claim?
- What are the key concepts?
- What mechanisms are proposed?
- What phenomena does this explain?

**b) Presents the evidence**:
- Strongest supporting evidence (with excerpts)
- How the framework accounts for variation
- How negative cases informed refinement

**c) Locates the contribution**:
- What's new compared to existing theory?
- What conversations does this enter?
- What scholars is this in dialogue with?
- Why does this matter?

**d) Names the Silent Dialogue (REQUIRED)**:
Explicitly identify who you are arguing with. If this framework is true, which existing theoretical perspective is revealed to be **incomplete or incorrect**?

Be specific:
- Name the specific scholar(s) or theoretical tradition
- Identify their specific claim that your framework challenges
- Explain precisely HOW your framework reveals their limitation
- This is not just "extending" prior work—identify where prior work was WRONG or BLIND

Example: "If crisis-forged collectivity is the mechanism of solidarity formation in ACT UP, then Polletta's (2002) account of collective identity formation through shared characteristics is incomplete. It cannot explain how ACT UP formed intense solidarity across radical differences in identity, ideology, and social position. Her framework assumes similarity as the basis for collective identity; our framework shows that shared orientation to crisis can substitute for—and perhaps exceed—similarity-based solidarity."

**e) Acknowledges limitations**:
- Scope conditions
- Remaining puzzles
- Questions for future research
- Data limitations

### 6. Create Theoretical Summary

Produce a concise (1-2 page) summary of the theoretical contribution suitable for:
- Abstract writing
- Discussing with colleagues
- Framing a paper

## Output Files to Create

Save all outputs to `/analysis/phase5-reports/`:

1. **proposition-tests.md** - Systematic test results for each proposition
2. **negative-case-analysis.md** - Detailed analysis of disconfirming cases
3. **refined-propositions.md** - Updated propositions after testing
4. **scope-conditions.md** - Where the theory applies and doesn't
5. **theoretical-synthesis.md** - Full integrated synthesis (main output)
6. **theoretical-summary.md** - Concise summary of contribution
7. **future-research.md** - Questions and directions for future work
8. **phase5-report.md** - Executive summary including:
   - How propositions fared under testing
   - Key refinements from negative case analysis
   - Final theoretical claims
   - Statement of contribution
   - Limitations and future directions
   - Questions for the user

## Example Proposition Test Format

```markdown
## Testing Proposition 2: [Proposition Statement]

### Verification Sweep

**Supporting Evidence**:

| Interview | Excerpt | Strength | Notes |
|-----------|---------|----------|-------|
| Int 3 | "Quote..." | Strong | Directly states mechanism |
| Int 7 | "Quote..." | Moderate | Implied support |
| Int 12 | "Quote..." | Strong | Clear example |

**Summary**: Proposition finds support in X of Y relevant interviews.

### Falsification Attempt

**Potential Disconfirming Evidence**:

| Interview | Excerpt | Challenge | Assessment |
|-----------|---------|-----------|------------|
| Int 9 | "Quote..." | Seems to contradict claim about X | See negative case analysis |
| Int 14 | "Quote..." | Different mechanism described | Could be alternative pathway |

### Alternative Explanation Check

**Evidence also consistent with**:
- Alternative theory A: Because...
- Alternative theory B: Because...

**Distinguishing evidence**: The data in Interviews 5 and 11 favors our proposition over alternatives because...

### Verdict

**Status**: Supported / Partially supported / Needs modification / Not supported

**Modifications needed**: [If any]

**Confidence level**: High / Medium / Low

**Reasoning**: [Explanation]
```

## Example Negative Case Analysis

```markdown
## Negative Case: Interview 9

### Description
Participant 9 is [description] who, according to Proposition 2, should [expected pattern]. However, they actually [observed pattern that contradicts].

### The Contradiction
- **Expected** (per proposition): [What we'd predict]
- **Observed**: [What we found]
- **Key excerpt**: "Quote showing the contradiction..."

### Analysis

**What's different about this case?**
- P9 differs from supporting cases in that: [differences]
- Contextual factors that may matter: [factors]

**Possible interpretations**:

1. **True exception - revise proposition**: The proposition is wrong about [X]. We should modify it to [revised claim].

2. **Scope condition - add boundaries**: The proposition holds EXCEPT when [condition]. P9 meets this exception condition because [reason].

3. **Alternative pathway - multiple mechanisms**: P9 achieves [same outcome] through a different mechanism, namely [alternative]. This suggests we need to theorize multiple pathways.

4. **Misspecification - refine concepts**: We miscoded or misunderstood P9's situation. On closer reading, [reinterpretation].

### Outcome

**Chosen interpretation**: [Which of the above]

**Revision to theory**: [Specific change made]

**Implication**: This negative case helps us specify that [refined understanding]
```

## Synthesis Document Structure

```markdown
# Theoretical Synthesis: [Title of Framework]

## Introduction
[What puzzle does this address? Why does it matter?]

## Core Theoretical Argument
[1-2 paragraph summary of the central claim]

## Key Concepts
### Concept 1: [Name]
[Definition, boundaries, relationship to existing concepts]

### Concept 2: [Name]
[Definition, etc.]

## Theoretical Propositions

### Proposition 1: [Statement]
[Evidence, mechanism, conditions]

### Proposition 2: [Statement]
[Evidence, mechanism, conditions]

[Continue for all propositions]

## The Framework in Action
[Walk through 1-2 cases showing how the framework explains the data]

## Accounting for Variation
[How the framework explains differences across cases]

## Theoretical Contribution
[What's new? Who is this in dialogue with? Why does it matter?]

## Scope and Limitations
[Where it applies, where it doesn't, what remains unexplained]

## Future Directions
[Questions for future research]

## Conclusion
[Summary of contribution]
```

## Guiding Principles

1. **Seek disconfirmation**: The value of testing is finding where the theory fails, not accumulating support.

2. **Negative cases refine, not defeat**: A negative case usually means the theory needs refinement, not abandonment.

3. **Specify scope honestly**: A theory that claims to explain everything explains nothing.

4. **Integration matters**: The propositions should form a coherent framework, not a list of findings.

5. **Contribution clarity**: Be explicit about what's new and why it matters.

6. **Intellectual humility**: Name limitations clearly. What don't you know?

## When You're Done

Return a summary to the orchestrator that includes:
1. Confirmation that all files were created
2. How propositions fared under testing (how many supported, modified, rejected)
3. Key insights from negative case analysis
4. The central theoretical contribution (2-3 sentences)
5. Most important limitations
6. Whether the user should review and iterate, or if synthesis is ready
7. Any final questions for the user
