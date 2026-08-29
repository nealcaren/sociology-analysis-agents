# Phase 2: Systematic Coding

You are executing Phase 2 of a pragmatic qualitative analysis. Your goal is to transform the rich, complex interview material into organized, analyzable categories through systematic coding.

## The Logic of Coding

Coding is not just labeling—it's **conceptual work**. As Gerson & Damaske explain, "Developing conceptual categories is an interactive and iterative process that involves moving back and forth between the interview transcripts and an evolving list of substantive and theoretical categories."

The goal is **analytic traction**: to organize the data in ways that let you see patterns, make comparisons, and develop explanations.

## Inputs

Before starting, read:
1. `/analysis/phase1-reports/` - All Phase 1 outputs, especially interview memos and emerging observations
2. Original interview transcripts in `/interviews/`
3. **Track A**: Also review `/analysis/phase0-reports/theory-reference-sheet.md` for theoretically-derived categories

## Your Tasks

### 1. Develop Preliminary Codes

Start with a list of codes that reflect:
- The research questions guiding this analysis
- Sections of the interview guide (if available)
- Key observations from Phase 1
- **Track A**: Concepts from theoretical frameworks

These preliminary codes can be quite general. You'll refine them as you work.

**Types of codes to consider**:

**Descriptive codes** (what's happening):
- Actors and roles
- Actions and practices
- Settings and contexts
- Events and sequences
- Temporal markers (before/after, turning points)

**Process codes** (dynamics, using gerunds):
- Becoming, changing, transitioning
- Deciding, choosing, weighing
- Managing, coping, navigating
- Building, maintaining, losing

**Meaning codes** (interpretation and significance):
- How participants understand events
- What things mean to them
- Values and priorities
- Justifications and accounts

**Emotion codes**:
- Feelings expressed or implied
- Affective responses to events
- Emotional dimensions of experiences

**Relationship codes**:
- Key relationships mentioned
- Relationship dynamics
- Social support and conflict

**In-vivo codes** (participants' own language):
- Distinctive phrases or terms
- Metaphors and imagery
- Recurring expressions

### 2. Apply Codes to Transcripts

Work through each transcript, applying codes to relevant segments. As you code:

**Refine as you go**:
- Split overly broad codes into subcategories
- Merge codes that overlap significantly
- Add new codes when you encounter something the current list doesn't capture
- Drop codes that aren't proving useful

**Track variation within codes**:
- Note the different forms a coded phenomenon takes
- Pay attention to who exhibits what variation
- Look for dimensions within categories

**Example of code refinement**:
```
Initial code: "Parental influence"

Refined into:
- Parental influence: explicit encouragement
- Parental influence: modeling behavior
- Parental influence: providing resources
- Parental influence: discouragement/barriers
- Parental influence: absence/non-involvement

Each subcode captures a different way parental influence operates.
```

### 3. Build the Codebook

Create a systematic codebook documenting each code:

```markdown
### Code: [Code Name]

**Definition**: [Clear statement of what this code captures]

**Inclusion criteria**: [When to apply this code]

**Exclusion criteria**: [When NOT to apply this code; distinctions from similar codes]

**Example excerpts**:
> "Quote 1" - Participant X
> "Quote 2" - Participant Y

**Subcodes** (if applicable):
- [Subcode A]: [definition]
- [Subcode B]: [definition]

**Frequency**: Appears in X of Y interviews

**Notes**: [Any observations about this code—variation, questions, connections]
```

### 4. Create Coded Excerpt Files

For each major code, compile the relevant excerpts:

```markdown
# Code: [Code Name]

## Participant 01
> "Excerpt 1" (context: discussing X)
> "Excerpt 2" (context: discussing Y)

## Participant 02
> "Excerpt" (context: discussing Z)

[etc.]
```

This makes it easy to see all instances of a code together.

### 5. Write a Coding Memo

Document your coding process and emerging insights:
- How did codes evolve during the process?
- What patterns are becoming visible?
- What's the relationship between codes?
- What surprised you during coding?
- What remains unclear or puzzling?
- What should Phase 3 focus on?

### 6. Build Participant Profiles

For each participant, create a profile that captures everything needed for later writeup. This is where you preserve the rich, person-level detail that gets lost if you only organize by code.

```markdown
## Participant: [Name or Pseudonym]

**Interview**: #[number]
**Demographics**: [Race/ethnicity], [gender], [age or age range], [other relevant identifiers]
**Role/Position**: [Role in organization, occupation, committee membership, etc.]
**Key trajectory**: [1-sentence summary of their arc relevant to your study]

### Extended Quotes (potential anchors)
Quotes of 3+ sentences that show this person's voice, reasoning, or experience unfolding. These are candidates for deep vignettes in the writeup.

> "[Full quote, preserving the participant's voice and logic]"
> *Context*: [What prompted this—interview question, topic being discussed]
> *Codes*: [Which codes apply]

> "[Another extended quote if available]"
> *Context*: [...]

### Punchy Quotes (potential echoes)
Shorter quotes (1-2 sentences or memorable phrases) that capture something vividly. These work as prevalence indicators or embedded voice in the writeup.

> "[Short quote]"
> "[Another short quote]"
> "[Memorable phrase]"

### In-Vivo Terms
Distinctive language this participant uses—metaphors, recurring phrases, terms of art.
- "[term 1]"
- "[term 2]"

### Emotional Tenor
[How does this participant come across? Angry, resigned, reflective, defiant? What feelings are expressed or implied?]

### What Makes This Participant Distinctive
[Why might this person serve as an anchor case for a particular finding? What do they exemplify clearly? Are they typical or a useful outlier?]

### Codes Heavily Present
- [Code 1]: [brief note on how it manifests]
- [Code 2]: [brief note]
```

**Why this matters for writeup**: The qual-findings-writer skill needs:
- Full demographics for attribution ("Maria, a 34-year-old Puerto Rican lesbian who co-founded the Latino Caucus...")
- Extended quotes for anchor vignettes (3-6 sentences showing voice and reasoning)
- Short quotes for echo patterns (1-2 sentences showing prevalence)
- Sense of who would exemplify which finding

Building this now—while you're deep in each interview—is far easier than reconstructing it later.

## Output Files to Create

Save all outputs to `/analysis/phase2-reports/`:

1. **codebook.md** - Full codebook with all codes documented
2. **coded-excerpts/** folder with files for each major code:
   - `code-[name].md`
3. **participant-profiles/** folder with a file for each participant:
   - `participant-[name].md` - Demographics, trajectory, extended quotes, punchy quotes, in-vivo terms, what makes them distinctive
4. **coding-memo.md** - Reflections on the coding process
5. **code-frequency-matrix.md** - Which codes appear in which interviews
6. **phase2-report.md** - Executive summary including:
   - Overview of coding structure (number of codes, organization)
   - Most prevalent codes
   - Most analytically interesting codes
   - Key patterns visible through coding
   - Remaining puzzles
   - Questions for the user
   - Recommendations for Phase 3

Also save the codebook to `/analysis/codes/codebook.md` for cross-phase reference.

## Guiding Principles

1. **Coding is thinking**: The point isn't to label everything—it's to develop analytic categories that help you see.

2. **Iterate freely**: Return to earlier transcripts when you develop new codes. Recoding is normal.

3. **Balance breadth and depth**: Code comprehensively, but invest most energy in codes that matter for your research questions.

4. **Embrace complexity**: If something fits multiple codes, code it multiple times. Overlap is informative.

5. **Stay close to the data**: Codes should emerge from what participants actually say, not just from theoretical categories.

6. **Track your moves**: Document code changes so you (and others) can follow your reasoning.

## Deductive vs. Inductive Coding

**Deductive** (theory → data):
- Start with theoretically-derived codes
- Apply them to see if/how they fit
- Useful when you have clear theoretical expectations

**Inductive** (data → theory):
- Let codes emerge from the material
- Build categories from the ground up
- Useful when exploring new terrain

**In practice, use both**:
- Start with some deductive codes from research questions or theory
- Remain open to inductive codes that emerge
- Let the two inform each other

## Example Codebook Entry

```markdown
### Code: Turning Point - Recruitment

**Definition**: A specific moment or event that participants identify as
when/how they first became involved or committed.

**Inclusion criteria**: Apply when participant describes a discrete event,
encounter, or realization that marked the beginning of their involvement
or a significant deepening of commitment.

**Exclusion criteria**: Do NOT apply to gradual processes without a
marked moment. Use "Gradual Involvement" for those cases.

**Example excerpts**:
> "I remember exactly when it clicked for me. I was at this rally, and
> someone handed me a flyer, and I just thought—I have to do something."
> - Participant 03

> "My turning point was when my neighbor's kid got sick. That made it
> real for me. Before that it was abstract." - Participant 11

**Subcodes**:
- Turning point - personal experience: triggered by direct personal encounter
- Turning point - vicarious: triggered by witnessing others' experiences
- Turning point - political event: triggered by external political events
- Turning point - invitation: triggered by being asked by someone

**Frequency**: Appears in 14 of 20 interviews

**Notes**: Strong pattern of discrete turning points, but 6 participants
describe more gradual paths. The turning point narratives may be
retrospective constructions—worth exploring in Phase 3.
```

## When You're Done

Return a summary to the orchestrator that includes:
1. Confirmation that all files were created
2. Total number of codes developed (and how organized)
3. Most frequent codes (top 5-7)
4. Most analytically interesting codes (and why)
5. Key patterns visible through coding
6. Notable variation within important codes
7. Puzzles or questions for Phase 3
8. Questions for the user about coding priorities or interpretation
