# Phase 3: Drafting

## Why This Phase Matters

This is where planning becomes prose. The quality of your Theory section depends on sentence-level craft—how you open paragraphs, integrate citations, calibrate hedging, and build toward the turn. This phase transforms the paragraph map into publication-ready prose.

---

## Your Tasks

### 1. Draft by Paragraph

Work through the paragraph map one paragraph at a time. For each:

**Step 1: Open with purpose**
- Use the planned topic sentence (or refine it)
- Match opening type to function (see `techniques/sentence-toolbox.md`)

**Step 2: Build the paragraph**
- 4-7 sentences typical (129-165 words target)
- Each sentence advances the paragraph's function
- Vary sentence length and structure

**Step 3: Integrate citations**
- Follow the planned citation deployment
- Use appropriate patterns (parenthetical, author-subject, string)
- See `techniques/citation-patterns.md`

**Step 4: Calibrate hedging**
- Hedge predictions and mechanism claims
- Assert definitions and gap statements
- See hedging guide in `techniques/sentence-toolbox.md`

**Step 5: Transition out**
- Final sentence should set up the next paragraph
- Use transitional phrases or logical connectors

### 2. Draft by Function

Apply function-specific guidance:

#### PROVIDE_CONTEXT Paragraphs
- Open with phenomena, not scholars
- Use statistics, trends, or historical developments
- Keep citations minimal (2-3)
- Establish stakes or scope

**Example**:
> As housing costs have outpaced wage growth, many parents face difficulty housing their families. Over 3 million households with children doubled up with friends or family in 2019, and doubling-up rates have risen since the Great Recession (Pilkauskas et al. 2020). Low-income and Black families are disproportionately likely to double up, often as a strategy to avoid homelessness or manage poverty (Desmond 2016; Harvey 2018). These arrangements affect household composition, family relationships, and parenting dynamics in ways that remain poorly understood.

#### DESCRIBE_THEORY Paragraphs
- Name the framework/theorist explicitly
- Explain how the concept works
- Include dimensions, mechanisms, or processes
- Use author-subject citations for canonical sources

**Example**:
> The concept of "recognition" draws on several conceptual traditions. According to Honneth (2003), recognition operates through three spheres: love (intimate relationships), rights (legal status), and esteem (social value). When individuals are denied recognition—through disrespect, exclusion, or degradation—they experience psychological harm and may struggle to develop positive self-relations (Taylor 1994). Lamont and colleagues (2016) have extended this framework to examine how low-status groups pursue recognition in everyday life, showing how stigmatized individuals actively resist misrecognition through boundary work and collective claims-making.

#### SYNTHESIZE Paragraphs
- Aggregate findings, don't summarize individual studies
- Use parenthetical strings efficiently
- Build toward a cumulative claim
- End with "what we know" before the gap

**Example**:
> Research on legal cynicism demonstrates that distrust of legal institutions is patterned by neighborhood context, race, and prior contact with police (Kirk and Papachristos 2011; Sampson and Bartusch 1998). Studies consistently find that residents of high-crime neighborhoods express cynicism about police responsiveness and fairness, even as they continue to call 911 for emergencies (Desmond et al. 2016; Gau and Brunson 2010). This literature highlights the coexistence of cynicism and reliance—a paradox that existing frameworks have struggled to explain.

#### IDENTIFY_GAP Paragraphs
- Use the 4-part turn structure (see `techniques/turn-formula.md`)
- Be specific about what's unknown
- Connect directly to your study

**Example**:
> This literature highlights the importance of recognition for understanding how marginalized groups engage with institutions. Yet while research documents the pursuit of recognition in various settings, there is less attention to how recognition-seeking shapes encounters with legal authorities specifically. How do residents of high-crime neighborhoods understand their calls to police as demands for recognition? What meaning-making processes allow them to reconcile cynicism with reliance? These questions remain largely unexplored.

#### STATE_QUESTIONS Paragraphs
- Articulate research questions clearly
- Connect questions to the gap
- Preview methods briefly if appropriate

**Example**:
> This study examines how mothers in doubled-up households negotiate identity and dignity in shared living arrangements. Three questions guide the analysis: How do guest mothers understand their position within host households? What strategies do they use to maintain maternal identity when authority is constrained? How do these negotiations vary by the character of the host-guest relationship? I address these questions through in-depth interviews with 47 mothers who doubled up with family or friends in the Chicago metropolitan area.

### 3. Draft Subsection by Subsection

If using subsections:
- Draft complete subsection before moving to next
- Ensure internal coherence within subsection
- Check that subsection accomplishes its architectural purpose

After each subsection, pause for user review if appropriate.

### 4. Maintain Cluster Style

As you draft, ensure prose style matches cluster:

| Cluster | Style Markers |
|---------|---------------|
| **Gap-Filler** | Efficient synthesis, sharp turn, minimal elaboration |
| **Theory-Extender** | Framework exposition, named theorist prominent |
| **Concept-Builder** | Definitional precision, confident terminology |
| **Synthesis** | Even treatment of traditions, bridging language |
| **Problem-Driven** | Even-handed debate presentation OR heavy context |

### 5. Track Progress

As you draft, note:
- Actual word count per paragraph
- Actual citations per paragraph
- Any deviations from the plan
- Paragraphs that need revision

### 6. Track Citations Used

Maintain a running list of every citation as you use it. For each citation, record:

```json
{
  "citations": [
    {
      "author": "Kirk and Papachristos",
      "year": "2011",
      "context": "legal cynicism patterning",
      "paragraph": 3,
      "pattern": "parenthetical"
    },
    {
      "author": "Connell",
      "year": "2005",
      "context": "hegemonic masculinity concept",
      "paragraph": 5,
      "pattern": "author-subject"
    }
  ]
}
```

**Why track citations?**
- Enables bibliography generation without parsing the document
- Allows Zotero ID lookup in Phase 5
- Helps verify citation density during revision
- Creates audit trail of sources used

Save incrementally to `citations-tracking.json` as you draft.

---

## Guiding Principles

### Draft, Don't Perfect
Get prose on the page. Revision comes in Phases 4-5.

### Follow the Map
The paragraph map exists for a reason. Stick to it unless you discover a structural problem.

### Topic Sentences Are Anchors
If you're struggling with a paragraph, return to the topic sentence. What is this paragraph trying to accomplish?

### Vary Citation Integration
Don't use the same pattern throughout. Mix parenthetical, author-subject, and (sparingly) quote-then-cite.

### Read Aloud
Prose that sounds awkward when read aloud needs revision. Academic writing should still flow.

### The Turn Is Sacred
Draft the turn with special care. It's the most important paragraph.

---

## Common Drafting Problems

| Problem | Solution |
|---------|----------|
| Paragraph too long | Split into two; each should have one main function |
| Paragraph too short | Develop the idea more; add supporting material |
| Literature parade | Synthesize, don't list; what do the studies collectively show? |
| Missing topic sentence | Add clear opening that signals function |
| Buried turn | Move turn sentence to start of paragraph; add contrastive marker |
| Hedging definitions | Definitions are assertions; remove "may," "might" |
| Over-asserting mechanisms | Mechanisms are claims; add appropriate hedging |

---

## Output Files to Create

1. **theory-section-draft.md** - Full draft prose organized by subsection
2. **drafting-notes.md** - Notes on deviations, concerns, needs for revision
3. **citations-tracking.json** - Running list of all citations used (author, year, context, paragraph, pattern)

---

## When You're Done

Report to the orchestrator:
- Draft complete (yes/no)
- Word count achieved
- Citation count achieved
- Turn drafted (provide sentence)
- Any structural changes from plan
- Areas flagged for revision

Example summary:
> "**Draft complete**. 1,487 words across 10 paragraphs (target: 1,500). 36 citations (target: 35). Turn at paragraph 6: 'Yet while research documents the pursuit of recognition in various settings, there is less attention to how recognition-seeking shapes encounters with legal authorities specifically.' One deviation: Split planned paragraph 4 into two for clarity. Flagged paragraphs 7-8 for transition smoothing in revision. Ready for Phase 4: Turn refinement."
