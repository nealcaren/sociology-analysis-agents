# Phase 4: Review & Refinement

You are executing Phase 4 of the lecture design process. Your goal is to ensure the lecture is deliverable, has backup plans, and all materials are ready for the instructor.

## Why This Phase Matters

A beautifully designed lecture means nothing if it can't be delivered. This phase catches timing problems, prepares for technology failures, and compiles everything the instructor needs into a usable package.

## Inputs

Before starting, review all previous outputs:
1. Phase 0: Learning outcomes, context
2. Phase 1: Narrative arc, chunk map
3. Phase 2: Activities, polls, ConcepTests
4. Phase 3: Slide deck

## Your Tasks

### 1. Temporal Audit

Verify the timing adds up:

**Create a minute-by-minute timeline:**
```markdown
| Time | Activity | Duration | Cumulative |
|------|----------|----------|------------|
| 0:00 | Hook + baseline poll | 5 min | 5 min |
| 0:05 | Chunk 1 lecture | 15 min | 20 min |
| 0:20 | ConcepTest + PI | 5 min | 25 min |
| ... | ... | ... | ... |
| 1:15 | END | - | 75 min |
```

**Check for problems:**
- Does it add up to the available time?
- Is there buffer for running over?
- What can be cut if running late?
- What can be added if running fast?

### 2. Cognitive Load Audit

Review each section for overload risks:

**Slide check:**
- Any slide with more than 6 bullets?
- Any slide requiring more than 2 minutes to explain?
- Any dense diagrams that need progressive reveal?

**Concept density check:**
- Are there back-to-back heavy concepts without a break?
- Is the hardest material placed strategically (not at minute 60)?

**Activity check:**
- Is there an active break every 12-18 minutes?
- Are activities varied (not all polls)?

### 3. Failure Mode Planning

Create backup plans for common failures:

**Technology Failures:**
| Failure | Backup Plan |
|---------|-------------|
| Polling system down | Show of hands, paper cards |
| Projector fails | Verbal lecture with whiteboard |
| Audio dies | Move closer, speak louder |
| WiFi fails | Pre-downloaded slides, local backup |
| Clicker batteries die | Call on volunteers |

**Timing Failures:**
| Scenario | Action |
|----------|--------|
| Running 10 min late | Cut [specific section] |
| Running 10 min early | Add [specific activity] |
| Students confused (need more time) | Cut Chunk 3, extend Chunk 2 |
| Fire drill / interruption | Priority content = [list] |

**Student Engagement Failures:**
| Scenario | Response |
|----------|----------|
| <30% correct on ConcepTest | Stop, re-teach, don't peer discuss |
| No one talking in pairs | Assign pairs explicitly |
| Students disengaged | Call a break, change modality |

### 4. Create Instructor Guide

Compile a single document the instructor can use during delivery:

**Include:**
1. **Overview**
   - Learning outcomes
   - Total time and structure
   - Key messages

2. **Minute-by-minute timeline**
   - What happens when
   - Cue for each activity
   - Transition language

3. **Activity protocols**
   - Poll questions and correct answers
   - Peer Instruction workflow
   - Expected response distributions

4. **Delivery notes**
   - Stage movement suggestions
   - Voice modulation cues
   - Where to pause for effect

5. **Backup plans**
   - Technology failures
   - Timing adjustments
   - Engagement issues

6. **Post-class follow-up**
   - What to post (slides, recap)
   - How to use muddiest point data
   - Preview of next lecture

### 5. Final Materials Check

Verify all files are complete and organized:

```
lecture/
├── slides.qmd                    ✓
├── slides.html (rendered)        ✓
├── lecture-plan.md               ✓
├── activities.md                 ✓
├── instructor-guide.md           ✓
├── backup-plans.md               ✓
└── assets/
    ├── images/                   ✓
    └── polls/                    ✓
```

### 6. Pre-Flight Checklist

Create a checklist the instructor can use before class:

**Day Before:**
- [ ] Review slides and speaker notes
- [ ] Test technology (polling, projector, clicker)
- [ ] Print backup materials
- [ ] Review timing and backup plans

**30 Minutes Before:**
- [ ] Arrive early, test A/V
- [ ] Load slides, check display
- [ ] Log into polling system
- [ ] Verify WiFi

**5 Minutes Before:**
- [ ] Take a breath
- [ ] Review opening hook
- [ ] Stand in position
- [ ] Start on time

## Output Files to Create

1. **temporal-audit.md** - Minute-by-minute timeline with buffer analysis

2. **cognitive-load-audit.md** - Section-by-section load assessment with recommendations

3. **backup-plans.md** - Complete failure mode protocols

4. **instructor-guide.md** - All-in-one delivery document

5. **preflight-checklist.md** - Before-class checklist

6. **phase4-report.md** - Executive summary including:
   - Confirmation all materials are ready
   - Any remaining concerns
   - Suggested rehearsal focus
   - Post-delivery follow-up recommendations

## Guiding Principles

1. **Murphy's Law is real**: If technology can fail, plan for it.

2. **Time is your enemy**: Build in buffer; you'll need it.

3. **The instructor guide is the product**: Make it usable under pressure.

4. **Rehearsal matters**: Recommend the instructor do a dry run.

5. **First time is hardest**: The lecture will improve with iteration.

## When You're Done

Return a summary to the orchestrator that includes:
1. Confirmation that all files were created
2. Total timing and any buffer/cuts needed
3. Key backup plans
4. Remaining action items for instructor
5. Recommendation for next steps (rehearsal, first delivery)
