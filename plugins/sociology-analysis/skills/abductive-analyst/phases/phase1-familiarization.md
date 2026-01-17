# Phase 1: Familiarization & Open Coding

You are executing Phase 1 of an abductive analysis of interview data. Your goal is to develop deep familiarity with the data and generate initial codes without prematurely imposing theoretical frameworks.

## Your Tasks

### 1. Read All Interviews
- Read every transcript in the `/interviews` folder carefully
- Pay attention to language, tone, emphases, contradictions, and emotional moments
- Note what participants talk about at length vs. briefly
- Attend to what is NOT said as much as what is said

### 2. Generate Interview Summaries
For each interview, produce a summary that includes:
- **Participant identifier** (use pseudonym or ID from filename)
- **Key biographical/contextual details** mentioned
- **Main topics discussed** and participant's stance on each
- **Notable quotes** (2-4 verbatim excerpts that capture something important)
- **Initial surprises** (anything that stood out, puzzled you, or seemed unexpected)
- **Emotional tenor** (how did the participant seem to feel about topics discussed?)

### 3. Open Coding
Generate codes that emerge from the data. Focus on:

**Descriptive codes**:
- Actors (who is mentioned, in what roles)
- Actions (what do people do)
- Contexts (settings, situations, circumstances)
- Temporal markers (before/after, sequences, turning points)

**Process codes** (gerunds - things ending in -ing):
- What processes are described? (e.g., "becoming," "struggling," "negotiating")

**In-vivo codes**:
- Participants' own language and phrases that capture something meaningful
- Pay special attention to metaphors and recurring expressions

**Emotion codes**:
- Emotional states mentioned or expressed
- What evokes strong reactions?

**Values codes**:
- What do participants value, believe, judge?
- What do they present as good/bad, right/wrong?

### 4. Flag Surprises
Create a dedicated section for "surprises"—moments that:
- Contradict what you'd expect based on common assumptions
- Don't fit neatly into obvious categories
- Show internal contradiction within a participant's account
- Differ markedly from other participants
- Seem to carry extra weight or emphasis

For each surprise, note:
- The excerpt
- Why it seems surprising
- What questions it raises

### 5. Create Initial Codebook
Compile all codes into an initial codebook with:
- Code name
- Brief definition
- Example excerpt(s)
- Frequency (how many interviews contain this code)

## Output Files to Create

Save all outputs to `/analysis/phase1-reports/`:

1. **interview-summaries.md** - All interview summaries
2. **initial-codebook.md** - The codebook with all codes
3. **surprises.md** - Catalog of flagged surprises
4. **phase1-report.md** - Executive summary for the user including:
   - Overview of the dataset (number of interviews, participant characteristics)
   - Key themes emerging from open coding
   - Most significant surprises identified
   - Preliminary observations (without forcing theory)
   - Questions for the user
   - Recommendations for Phase 2 focus areas

## Guiding Principles

1. **Stay close to the data**: Use participants' language. Don't translate into theoretical jargon yet.

2. **Be comprehensive**: Code everything that might be relevant. It's easier to drop codes later than to miss something important.

3. **Embrace confusion**: If something doesn't make sense, that's interesting. Flag it rather than explaining it away.

4. **Notice patterns AND exceptions**: Both are valuable.

5. **Preserve context**: When excerpting quotes, include enough context to understand them later.

6. **No premature closure**: Resist the urge to develop a "story" about the data. That comes later.

## Example Interview Summary Format

```markdown
## Interview: [Participant ID]

**Context**: [Age, role, relevant background mentioned]

**Main Topics**:
- Topic 1: [Brief description of their perspective]
- Topic 2: [Brief description of their perspective]

**Notable Quotes**:
> "Exact quote from transcript" (context: discussing X)

> "Another quote" (context: describing Y)

**Initial Surprises**:
- [Something unexpected or puzzling]

**Emotional Tenor**: [Overall sense of how they related to topics]

**Initial Codes Applied**: [List of codes that appeared in this interview]
```

## Example Codebook Entry Format

```markdown
### Code: [Code Name]

**Definition**: [What this code captures]

**Example excerpts**:
> "Quote 1" - Participant X
> "Quote 2" - Participant Y

**Frequency**: Appears in X of Y interviews

**Notes**: [Any observations about this code]
```

## When You're Done

Return a summary to the orchestrator that includes:
1. Confirmation that all files were created
2. Key statistics (number of interviews processed, number of codes generated)
3. The 3-5 most significant surprises identified
4. Suggested focus areas for Phase 2
5. Any questions or concerns for the user
