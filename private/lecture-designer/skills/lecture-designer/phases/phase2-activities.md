# Phase 2: Active Learning Design

You are executing Phase 2 of the lecture design process. Your goal is to design the polls, ConcepTests, and active learning activities that will reset attention, promote deep processing, and provide real-time feedback.

## Why This Phase Matters

In a large lecture, individual dialogue is impossible. Active learning systems solve this by enabling collective dialogue. But the technology is only as effective as the pedagogy behind it.

Research consistently shows that passive listening leads to attention decay after 12-18 minutes. Active breaks don't interrupt learning—they enable it by resetting the vigilance timer and forcing students to process information rather than just receive it.

## Inputs

Before starting, read:
1. Phase 0 outputs (learning outcomes, context)
2. Phase 1 outputs (chunk map, narrative arc)
3. The original chapter material

## Your Tasks

### 1. Design the Poll Set

For a 75-minute lecture, design 5-6 polls at strategic moments:

| Poll | Timing | Purpose | Type |
|------|--------|---------|------|
| **Poll 1** | 0-3 min | Prediction/baseline | Multiple choice or word cloud |
| **Poll 2** | ~20 min | ConcepTest for Chunk 1 | Multiple choice (Peer Instruction) |
| **Poll 3** | ~40 min | ConcepTest for Chunk 2 | Multiple choice (Peer Instruction) |
| **Poll 4** | ~55 min | Transfer/application | Multiple choice or ranking |
| **Poll 5** | ~72 min | Muddiest point | Open-ended |

**For each poll, specify:**
- Question text
- Answer options (for MC)
- Correct answer
- Why each distractor is wrong
- What misconception each distractor represents
- Follow-up explanation

### 2. Design ConcepTests (Peer Instruction)

ConcepTests are the heart of active learning. They must be *conceptual*, not factual.

**What makes a good ConcepTest:**
- Tests understanding of a mechanism, not recall of a term
- Has plausible wrong answers based on real misconceptions
- Targets the 30-70% correct range (ideal for peer discussion)
- Can be discussed productively with a neighbor

**Template:**
```markdown
## ConcepTest: [Topic]

**Stem:** [Describe a situation or scenario]

A) [Distractor 1 - common misconception]
B) [Correct answer]
C) [Distractor 2 - different misconception]
D) [Distractor 3 - surface-level error]

**Correct:** B

**Why B is correct:** [Explanation]

**Why A is wrong:** [Misconception it represents]
**Why C is wrong:** [Misconception it represents]
**Why D is wrong:** [Error it represents]

**Target outcome:** [Which learning outcome this tests]
**Expected distribution:** [e.g., "Expect ~50% correct initially"]
```

**Bad ConcepTest (factual recall):**
> "What year did X happen?"

**Good ConcepTest (conceptual):**
> "Given that X happened and Y was true, what should we expect to observe? Why?"

### 3. Design the Peer Instruction Protocol

For each ConcepTest, plan the full Peer Instruction cycle:

1. **Concept presentation** (7-10 min): Lecture on the topic
2. **Question posed** (1 min): Display the ConcepTest
3. **Individual vote** (1 min): Silent, no discussion. Enforced.
4. **Data check** (instructor only):
   - <30% correct → Re-teach, don't discuss (misconceptions will spread)
   - 30-70% correct → Proceed to peer discussion
   - >70% correct → Brief explanation, move on
5. **Peer discussion** (2-4 min): "Find someone with a different answer. Convince them."
6. **Re-vote** (1 min): Vote again
7. **Explanation** (2 min): Reveal results, explain correct answer AND common errors

### 4. Design State Change Activities

Not every break needs to be a poll. Design non-digital state changes:

**Options:**
- **Sketch it**: "Draw the process we just discussed"
- **Explain to neighbor**: "Explain concept X to your neighbor in 30 seconds"
- **Physical movement**: "Stand if you think A, stay seated if you think B"
- **Quick write**: "Write one sentence summarizing the main point"
- **Video clip**: Short (<3 min) relevant video
- **Demonstration**: Live demo or simulation

### 5. Design Opening and Closing Activities

**Opening Activity (aligned with hook):**
- Baseline prediction poll
- "What do you think explains this phenomenon?"
- Captures pre-instruction mental models

**Closing Activity:**
- Muddiest point: "What was most confusing today?"
- One-minute paper: "What's the main takeaway?"
- Exit ticket: One application question

### 6. Plan for Technology Failure

What happens if the polling system fails?
- Backup: Show of hands
- Backup: "Turn to your neighbor and discuss"
- Backup: Paper response cards (A/B/C/D)

## Output Files to Create

1. **poll-set.md** - Complete poll questions with:
   - Question text and options
   - Correct answers and explanations
   - Misconception mapping
   - Timing and placement

2. **conceptests.md** - Full ConcepTests with:
   - Stem and options
   - Correct answer and rationale
   - Distractor analysis
   - Expected distribution
   - Peer Instruction protocol notes

3. **activities.md** - Non-poll activities:
   - State change activities for each break
   - Opening prediction activity
   - Closing reflection activity
   - Time estimates

4. **backup-plans.md** - Technology failure protocols

5. **phase2-report.md** - Executive summary including:
   - Complete activity timeline
   - Alignment with learning outcomes
   - Expected engagement patterns
   - Questions for instructor about preferences

## Guiding Principles

1. **Anonymity enables honesty**: Anonymous responses let students admit confusion.

2. **Distractors are diagnostic**: Good wrong answers reveal specific misconceptions.

3. **30-70% is the sweet spot**: Too easy = no discussion; too hard = reinforced confusion.

4. **Silence before discussion**: Individual commitment prevents groupthink.

5. **Explain the wrong answers**: Students learn as much from why A is wrong as why B is right.

6. **Variety matters**: Mix poll types, use non-digital activities, change modalities.

## When You're Done

Return a summary to the orchestrator that includes:
1. Confirmation that all files were created
2. The complete poll/activity sequence with timing
3. Which learning outcomes each activity assesses
4. Any concerns about timing or difficulty
5. Questions for the instructor about activity preferences
