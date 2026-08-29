# Phase 2: Planning

## Why This Phase Matters

Before drafting prose, you need a paragraph-by-paragraph plan that specifies what each paragraph will accomplish, how it will open, and what citations it will deploy. This planning prevents the common problem of aimless literature cataloging and ensures each paragraph drives the argument forward.

---

## Your Tasks

### 1. Assign Paragraph Functions

For each paragraph in the outline, assign a function from `techniques/paragraph-functions.md`:

| Function | Purpose |
|----------|---------|
| **PROVIDE_CONTEXT** | Establish phenomenon, population, setting |
| **DESCRIBE_THEORY** | Explicate framework or concept |
| **SYNTHESIZE** | Summarize patterns across studies |
| **CONTRAST** | Present competing positions |
| **CRITIQUE** | Identify limitations |
| **IDENTIFY_GAP** | Mark what's unknown (the turn) |
| **BRIDGE** | Connect literatures or show framework fit |
| **STATE_QUESTIONS** | Articulate research questions |
| **PREVIEW** | Summarize coming argument |

### 2. Draft Topic Sentences

For each paragraph, write a topic sentence that:
- Signals the paragraph's function
- Uses appropriate opening type (from `techniques/sentence-toolbox.md`)
- Sets up the paragraph's work

**Example topic sentences by function**:

| Function | Topic Sentence |
|----------|----------------|
| PROVIDE_CONTEXT | "As housing costs have outpaced wage growth, many parents face difficulty housing their families." |
| DESCRIBE_THEORY | "The concept of 'recognition' draws on several conceptual traditions." |
| SYNTHESIZE | "A growing body of research examines how residents of high-crime neighborhoods interact with police." |
| CONTRAST | "Others, however, argue that secondary labor market entry traps immigrants in dead-end jobs." |
| IDENTIFY_GAP | "Yet we know little about how guest mothers maintain maternal identity when authority is constrained." |
| STATE_QUESTIONS | "This study examines how mothers in doubled-up households negotiate identity and dignity." |

### 3. Plan Citation Deployment

For each paragraph, specify:
- How many citations (target 2.4-5.0 per paragraph)
- Citation pattern (parenthetical, author-subject, string, quote)
- Key sources to include

Use this template:

```markdown
## Paragraph 3: SYNTHESIZE

**Topic sentence**: "Research on legal cynicism demonstrates that distrust is patterned by neighborhood context and prior police contact."

**Citations (5)**:
- Kirk and Papachristos 2011 (author-subject for definition)
- Sampson and Bartusch 1998 (parenthetical)
- Desmond et al. 2016 (parenthetical)
- Gau and Brunson 2010 (parenthetical)
- Tyler 2006 (parenthetical in string)

**Pattern**: Mix of author-subject for foundational work + parenthetical string for synthesis
```

### 4. Sequence for Flow

Review the paragraph sequence to ensure:

**Logical progression**:
- Context → Theory → Synthesis → Gap → Questions
- Each paragraph builds on what precedes

**Smooth transitions**:
- What transition marker will open each paragraph?
- How does each paragraph connect to the previous?

**Turn positioning**:
- Is the turn in the right place?
- Does adequate synthesis precede it?
- Do questions follow naturally?

### 5. Check Cluster Alignment

Verify the paragraph sequence matches cluster expectations:

| Cluster | Expected Sequence |
|---------|------------------|
| **Gap-Filler** | CONTEXT → SYNTHESIZE → SYNTHESIZE → GAP → QUESTIONS |
| **Theory-Extender** | CONTEXT → DESCRIBE → SYNTHESIZE → GAP → BRIDGE → QUESTIONS |
| **Concept-Builder** | CONTEXT → DESCRIBE → CRITIQUE → DESCRIBE → SYNTHESIZE+INTRO → DESCRIBE (new) → QUESTIONS |
| **Synthesis** | DESCRIBE(A) → SYNTHESIZE(A) → DESCRIBE(B) → SYNTHESIZE(B) → BRIDGE → QUESTIONS |
| **Problem-Driven** | DESCRIBE(1) → CONTRAST(2) → CRITIQUE → QUESTIONS |

### 6. Write Paragraph Map

Create `paragraph-map.md`:

```markdown
# Paragraph Map

## Overview
- Total paragraphs: [N]
- Total target citations: [N]
- Turn location: Paragraph [N]

---

## Paragraph 1
**Function**: PROVIDE_CONTEXT
**Subsection**: [if applicable]
**Topic sentence**: "[Draft opening]"
**Content notes**: [What this paragraph covers]
**Citations (N)**:
- [Source 1] (pattern)
- [Source 2] (pattern)
**Transition to next**: [How it connects to P2]

---

## Paragraph 2
**Function**: [...]
...

[Continue for all paragraphs]

---

## Paragraph [N]: THE TURN
**Function**: IDENTIFY_GAP
**Topic sentence**: "[Draft turn sentence]"
**Turn structure**:
1. Acknowledge: [what we know]
2. Pivot: [contrastive marker]
3. Gap: [specific gap claim]
4. Connect: [link to your study]
**Citations (N)**:
- [Sources supporting the gap claim]

---

## Summary Table

| P# | Function | Subsection | Citations | Key Sources |
|----|----------|------------|-----------|-------------|
| 1 | CONTEXT | — | 3 | [list] |
| 2 | SYNTHESIZE | — | 5 | [list] |
...
```

### 7. Pre-Draft Checklist

Before moving to drafting, verify:

- [ ] Every paragraph has an assigned function
- [ ] Topic sentences drafted for all paragraphs
- [ ] Citations planned (2.4-5.0 per paragraph)
- [ ] Total citations in target range for cluster
- [ ] Turn sentence drafted
- [ ] Sequence flows logically
- [ ] Transitions planned
- [ ] Cluster sequence alignment checked

---

## Guiding Principles

### Topic Sentences Do the Heavy Lifting
A reader should be able to understand the section by reading only the topic sentences. If they can't, your structure isn't clear.

### Citation Deployment is Strategic
Don't just sprinkle citations randomly. Plan which sources do which work.

### The Paragraph Map is Your Drafting Guide
In Phase 3, you'll draft one paragraph at a time following this map. The better the map, the smoother the drafting.

### Leave Room for Discovery
You may discover during drafting that a paragraph needs to split, or two should merge. That's fine—the map is a guide, not a prison.

---

## Output Files to Create

1. **paragraph-map.md** - Full paragraph-by-paragraph plan
2. **citation-plan.md** - Citation inventory with deployment strategy

---

## When You're Done

Report to the orchestrator:
- Number of planned paragraphs
- Turn placement (paragraph number)
- Total planned citations
- Any concerns about coverage or sequence

Example summary:
> "Paragraph map complete. **10 paragraphs** planned: 2 context, 3 framework, 2 synthesis, 1 gap (turn at P6), 2 contribution. **38 citations** distributed across paragraphs (avg 3.8/paragraph). Turn drafts specific gap about guest mother identity in doubled-up households. Ready for Phase 3: Drafting."
