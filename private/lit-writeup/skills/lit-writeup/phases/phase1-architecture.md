# Phase 1: Architecture

## Why This Phase Matters

Architecture is the blueprint for your Theory section. Before writing paragraphs, you need to know: How many subsections? What arc? Where does the turn fall? What literatures get space?

Poor architecture leads to sections that feel disorganized, where the turn arrives too late (or too early), or where the structure doesn't match the contribution. This phase ensures structural coherence before drafting begins.

---

## Your Tasks

### 1. Select Arc Structure

Choose the arc that matches your cluster:

| Arc | Description | Best For |
|-----|-------------|----------|
| **Funnel** | Broad → narrow → gap → questions | Gap-Filler, Theory-Extender |
| **Building-Blocks** | Component → Component → Integration | Concept-Builder, Synthesis |
| **Dialogue** | Position A ↔ Position B → Resolution | Problem-Driven (Debate), Synthesis |
| **Problem-Response** | Puzzle → Attempts → Limitations → Your approach | Problem-Driven, Concept-Builder |
| **Narrative-Historical** | Chronological development → Current moment | Problem-Driven (Historical) |

### 2. Plan Subsection Structure

Based on cluster:

| Cluster | Typical Subsections |
|---------|-------------------|
| **Gap-Filler** | 0-2 (often none; if any: "Background" / "This Study") |
| **Theory-Extender** | 1-3 (e.g., "[Framework]" / "Prior Applications" / "This Study") |
| **Concept-Builder** | 3-5+ (e.g., one per tradition + new concept + application) |
| **Synthesis** | 2-4 (e.g., "Tradition A" / "Tradition B" / "Integration") |
| **Problem-Driven** | 0-3 (variable; may use "Context" / "The Debate" / "This Study") |

### 3. Identify Key Literatures

Map the 3-5 literatures that will receive space:

For each literature:
- What does it contribute to your argument?
- How many paragraphs will it need?
- What's the key citation cluster?

Example for a Gap-Filler:
```
1. Housing instability literature (2 paragraphs)
   - Key: Desmond, Pattillo
   - Function: Context + synthesis

2. Family identity literature (2 paragraphs)
   - Key: Lareau, Hays
   - Function: Theoretical lens

3. Doubled-up households specifically (1 paragraph)
   - Key: Pilkauskas
   - Function: Direct predecessor → gap
```

### 4. Place the Turn

Determine where the turn falls:

| Cluster | Turn Placement | Paragraph Location |
|---------|----------------|-------------------|
| Gap-Filler | Middle | Around paragraph 3-4 of ~6 |
| Theory-Extender | Middle, sometimes early | After framework (paragraph 4-5 of ~8) |
| Concept-Builder | Middle | After critique, before new concept |
| Synthesis | Middle | After both traditions |
| Problem-Driven | Variable | Early for debate, late for empirical |

### 5. Draft Section Outline

Create detailed outline with:
- Subsection titles (if using)
- Paragraph-level breakdown
- Function assigned to each paragraph (from `techniques/paragraph-functions.md`)
- Approximate citation counts per section

Example outline for Theory-Extender:

```markdown
# Theory Section Outline

## Overall Arc: Funnel
## Target Length: 1,500 words (10 paragraphs)

### Introduction (no subsection)
- P1: PROVIDE_CONTEXT - Housing precarity context [3 citations]
- P2: SYNTHESIZE - Literature on housing instability [5 citations]

### [Framework Name] (subsection)
- P3: DESCRIBE_THEORY - Introduce framework [3-4 citations]
- P4: DESCRIBE_THEORY - Elaborate dimensions [3 citations]
- P5: SYNTHESIZE - Prior applications [6 citations]

### Extending to [Domain]
- P6: IDENTIFY_GAP - Framework not applied to X [2 citations] ← TURN
- P7: BRIDGE - Why framework fits this domain [3 citations]

### This Study
- P8: STATE_QUESTIONS - Research questions [1-2 citations]
- P9: PREVIEW - Argument preview [0 citations]
```

### 6. Estimate Calibration Targets

Based on cluster, set targets:

```markdown
## Calibration Targets

- Word count: [range based on cluster]
- Paragraph count: [range]
- Citation count: [range]
- Subsection count: [number]
- Literature balance: [theory-heavy / balanced / substantive]
```

### 7. Write Architecture Memo

Create `architecture-memo.md`:

```markdown
# Theory Section Architecture

## Cluster: [Name]
## Arc: [Type]

## Structure Overview

[Describe the overall flow in prose]

## Subsection Plan

### [Subsection 1 Title]
- Function: [what this section accomplishes]
- Paragraphs: [number]
- Key literatures: [list]

### [Subsection 2 Title]
...

## Turn Placement

The turn will occur in [paragraph N], after [what precedes] and before [what follows].

Turn strategy: [describe the pivot approach]

## Literature Allocation

| Literature | Paragraphs | Function |
|------------|------------|----------|
| [Lit 1] | [N] | [role] |
| [Lit 2] | [N] | [role] |
...

## Calibration Targets

| Metric | Target |
|--------|--------|
| Words | [range] |
| Paragraphs | [range] |
| Citations | [range] |
| Subsections | [number] |

## Outline

[Full paragraph-level outline with functions]

## Notes for Drafting

[Any special considerations, challenges, or decisions for Phase 3]
```

---

## Guiding Principles

### Structure Signals Ambition
- No subsections = streamlined empirical contribution
- 1-2 subsections = organized review
- 3-4 subsections = multiple theoretical components
- 5+ subsections = building theoretical apparatus

Don't add subsections for organizational convenience if they don't reflect genuine theoretical divisions.

### Each Subsection Should Have a Clear Purpose
If you can't articulate what a subsection accomplishes, you don't need it.

### The Turn is the Structural Center
Everything before builds toward it; everything after flows from it. Design around the turn.

### Leave Room for Discovery
This is a blueprint, not a prison. Drafting may reveal the need for adjustments.

---

## Output Files to Create

1. **architecture-memo.md** - Full architecture plan with outline
2. **section-outline.md** - Clean outline for quick reference during drafting

---

## When You're Done

Report to the orchestrator:
- Arc structure selected
- Subsection plan (number and titles)
- Turn placement
- Calibration targets
- Any concerns about literature coverage

Example summary:
> "Architecture complete. Using **Funnel arc** with **3 subsections**: 'Housing Precarity' (context), 'Bodies Out of Place' (framework), and 'This Study' (contribution). Turn placed at end of framework section (paragraph 6). Target: 1,500 words, 10 paragraphs, 35 citations. Ready for Phase 2: Planning."
