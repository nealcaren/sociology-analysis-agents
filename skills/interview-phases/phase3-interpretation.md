# Phase 3: Interpretation & Explanation

You are executing Phase 3 of a pragmatic qualitative analysis. Your goal is to move from **description to explanation**—to develop accounts of why patterns take the form they do.

## The Logic of Interpretation

Phases 1 and 2 established what's in the data. Phase 3 asks: **Why?**

As Gerson & Damaske emphasize, the goal is not to take participant accounts at face value, nor to dismiss them as "false consciousness." Instead: "understand how and why people develop their particular views and take the actions they do." This requires distinguishing between:

- **Accounts**: What participants say and how they make sense of their experiences
- **Explanations**: The factors, mechanisms, and processes that explain why things happen as they do

Participants are experts on their own experience but may not see the larger patterns, structural forces, or hidden dynamics that shape their lives. Your job is to identify these while respecting participants' perspectives.

## Inputs

Before starting, read:
1. `/analysis/phase1-reports/` - Interview memos and observations
2. `/analysis/phase2-reports/` - Codebook, coded excerpts, coding memo
3. Original transcripts in `/interviews/` as needed

**Track A (Theory-Informed)**: Also have `/analysis/phase0-reports/theory-reference-sheet.md` available for connecting patterns to theoretical frameworks.

**Track B (Data-First)**: This is the phase where you begin engaging theoretical literature. Based on emerging patterns, identify relevant frameworks that might help explain what you're seeing. (You may use web search or ask the user for relevant literature.)

## Your Tasks

### 1. Analyze Patterns Across Interviews

Working from coded data, identify and analyze key patterns:

**For each significant pattern**:
- What is the pattern? (Describe it precisely)
- How prevalent is it? (How many/which participants?)
- What variation exists within it?
- What conditions seem associated with it?

**Cross-cutting analysis**:
- How do patterns relate to each other?
- What combinations occur together?
- What sequences or trajectories appear?

### 2. Distinguish Accounts from Explanations

Participants offer **accounts**—their interpretations of their experiences. These are data, not conclusions.

For key phenomena, document:
- **What participants say**: How do they explain/justify/make sense of X?
- **Patterns in accounts**: Do participants tell similar stories? Different ones?
- **What accounts might obscure**: What might participants not see or acknowledge?
- **Possible explanations**: What factors might explain the pattern beyond what participants identify?

**Example**:
```markdown
### Phenomenon: High commitment despite significant personal costs

**Participant accounts**:
Most participants frame continued involvement despite costs as "just who I am"
or "I couldn't live with myself otherwise"—identity-based explanations.

**What accounts might obscure**:
- The social relationships that would be lost by leaving
- Sunk costs and escalating commitment dynamics
- Lack of perceived alternatives

**Possible explanations beyond participant accounts**:
- Identity commitment mechanisms (once publicly identified, hard to exit)
- Network embeddedness (leaving means losing valued relationships)
- Meaning-making (involvement provides purpose that alternatives don't)
```

### 3. Identify Trajectories, Transitions, and Turning Points

Many interview studies examine processes over time. Analyze:

**Trajectories**: What paths do participants follow? Are there distinct types?

**Transitions**: What moves people from one state to another? What enables or triggers change?

**Turning points**: What moments do participants (or you) identify as pivotal? What makes them pivotal?

**Sequences**: Does order matter? Do certain things need to happen before others?

### 4. Examine Variation

Variation is analytically powerful. Ask:

- **What varies?** Outcomes, pathways, interpretations, experiences?
- **Among whom?** Are there subgroups with different patterns?
- **Why?** What conditions, characteristics, or contexts explain differences?

**Create comparison matrices**:
```markdown
| Participant | Outcome | Key Factor A | Key Factor B | Notes |
|-------------|---------|--------------|--------------|-------|
| P01         | High    | Present      | Absent       | ...   |
| P02         | Low     | Absent       | Present      | ...   |
```

Look for combinations that predict outcomes.

### 5. Develop Explanatory Propositions

Based on your analysis, formulate tentative explanations:

```markdown
### Proposition: [Clear statement of the claim]

**What it explains**: [What pattern or puzzle does this address?]

**The mechanism**: [How/why does this work?]

**Supporting evidence**:
- [Evidence from coded data]
- [Quotes that illustrate]

**Complicating evidence**:
- [Cases that don't fit or complicate the picture]

**Conditions/scope**: [When does this hold? When might it not?]
```

Aim for propositions that are:
- **Grounded**: Clearly connected to evidence
- **Specific**: Not so general as to be unfalsifiable
- **Mechanistic**: Explaining how, not just that

### 6. Connect to Theoretical Literature

**Track A**: Return to Phase 0 frameworks. How do your findings:
- Confirm theoretical expectations?
- Extend or modify existing frameworks?
- Challenge or contradict theory?
- Fill gaps between frameworks?

**Track B**: Based on emerging patterns, identify relevant theoretical conversations:
- What literatures address similar phenomena?
- What concepts from existing work help name what you're seeing?
- Where do your findings fit in ongoing debates?

(For Track B, you may search for relevant literature or ask the user for resources.)

### 7. Identify What Remains Unexplained

Be honest about gaps:
- What patterns can't you explain yet?
- What negative cases challenge your propositions?
- What would you need to know to resolve puzzles?

## Output Files to Create

Save all outputs to `/analysis/phase3-reports/`:

1. **pattern-analysis.md** - Systematic analysis of key patterns
2. **accounts-vs-explanations.md** - Distinguishing participant accounts from analytic explanations
3. **trajectories-and-turning-points.md** - Analysis of temporal dynamics
4. **variation-analysis.md** - Examination of differences and what explains them
5. **explanatory-propositions.md** - Tentative explanatory claims
6. **theoretical-connections.md** - Links to relevant literature
7. **remaining-puzzles.md** - What remains unexplained
8. **phase3-report.md** - Executive summary including:
   - Key patterns identified
   - Central explanatory propositions
   - Most important theoretical connections
   - Negative cases and complications
   - Remaining puzzles
   - Questions for the user
   - Recommendations for Phase 4

Also save key memos to `/analysis/memos/` for reference.

## Guiding Principles

1. **Explanation requires distance**: You must step back from participant accounts to see patterns they can't see.

2. **But respect participant knowledge**: They know their experience. You're adding a different kind of knowledge, not replacing theirs.

3. **Mechanisms matter**: "X is associated with Y" is weaker than "X produces Y through Z mechanism."

4. **Negative cases are valuable**: Cases that don't fit force you to refine explanations.

5. **Stay grounded**: Every claim should connect to specific evidence.

6. **Maintain humility**: These are tentative explanations, not final truths.

## Example Explanatory Proposition

```markdown
### Proposition: Relational embedding predicts sustained involvement
more than ideological commitment

**What it explains**: Why some highly committed participants eventually
leave while others with weaker stated commitments persist.

**The mechanism**: Involvement creates valued relationships. Over time,
the relational stakes of participation (friendships, community belonging,
mutual support) come to outweigh the original ideological motivation.
Leaving means losing these relationships, which creates independent
motivation to stay regardless of belief intensity.

**Supporting evidence**:
- 11 of 14 long-term participants emphasized relationships when
  discussing what keeps them involved (vs. 3 of 8 short-term)
- P07: "The people keep me coming back. The cause matters, but if it
  wasn't for [names members], I don't know if I'd still be doing this."
- P15: "I've tried to leave twice. Both times I came back because I
  missed the people."
- Coding shows "relationship-centered accounts" strongly associated
  with duration of involvement

**Complicating evidence**:
- P02 and P09 show high commitment with low relational emphasis
  (both are relatively isolated members who work independently)
- Some relationship-centered participants DID leave (P04, P18)—
  suggests relationships are important but not sufficient

**Conditions/scope**:
- Strongest where organization provides opportunities for relationship
  formation (regular meetings, social events, collaborative work)
- May not hold for online/distributed participation
- Likely interacts with alternatives—relationship retention matters
  more when participants lack other sources of community
```

## When You're Done

Return a summary to the orchestrator that includes:
1. Confirmation that all files were created
2. Number of patterns analyzed
3. Key explanatory propositions (3-5 main claims)
4. Most important theoretical connections
5. Most challenging negative cases
6. Remaining puzzles
7. Questions for the user about interpretation or direction
