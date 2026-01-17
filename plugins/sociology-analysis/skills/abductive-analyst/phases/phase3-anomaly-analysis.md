# Phase 3: Anomaly & Variation Analysis

You are executing Phase 3 of an abductive analysis. Your goal is to systematically identify and analyze contradictions, anomalies, and variation across the interview data. In abductive analysis, these "surprises" are the raw material for theoretical innovation.

## The Logic of Anomaly Analysis

Abduction begins with surprise—observations that don't fit what existing frameworks would predict. Phase 3 systematically catalogs and analyzes these surprises:

- **Contradictions**: Where accounts conflict
- **Anomalies**: What doesn't fit expected patterns
- **Variation**: How and why participants differ
- **Negative cases**: Instances that contradict emerging patterns
- **Stubborn variation**: Same structural position, opposite responses

## Inputs

Before starting, read:
1. `/analysis/phase1-reports/` - All Phase 1 outputs
2. `/analysis/phase2-reports/` - All Phase 2 outputs, especially `theoretical-gaps.md`
3. Original interviews in `/interviews/` for reference

## Your Tasks

### 1. Cross-Interview Contradiction Analysis

Systematically compare how different participants discuss the same topics:

**For each major topic/theme from Phase 1**:
- How do different participants describe it?
- Where do accounts contradict each other?
- What explains the contradiction? (Position, experience, stakes, etc.)
- Is the contradiction superficial or deep?

Document contradictions with:
- Participant A's account (with excerpt)
- Participant B's contradicting account (with excerpt)
- Nature of the contradiction
- Possible explanations (without resolving prematurely)

### 2. Within-Interview Contradiction Analysis

Look for internal contradictions within individual interviews:
- Where does a participant contradict themselves?
- Where do they express ambivalence or tension?
- Where does their stated position conflict with their described actions?
- Where do they hedge, qualify, or backtrack?

These internal contradictions often reveal:
- Competing logics the participant navigates
- Tensions in the social world they inhabit
- Areas of genuine uncertainty or change

### 3. Theory-Data Anomalies

Drawing on Phase 2's theoretical casings:
- Which excerpts resisted all theoretical frameworks?
- What do these resistant excerpts have in common?
- What would a theory need to include to account for them?
- Are there patterns in what existing theories miss?

### 4. Variation Analysis

Map the variation across participants:

**Create a variation matrix**:
- Rows: Key themes/phenomena
- Columns: Different participant positions/responses
- Cells: Who falls where and why

**For significant variation, analyze**:
- What participant characteristics correlate with different positions?
- Is variation explained by: demographics? experience? role? timing? context?
- Is there variation that participant characteristics DON'T explain?

### 5. Negative Case Identification

Identify cases that contradict emerging patterns:
- If most participants do X, who doesn't? Why?
- If a pattern seems strong, what are the exceptions?
- What would make the negative cases make sense?

Negative cases are crucial because they:
- Prevent overgeneralization
- Reveal boundary conditions of emerging theory
- Often point to missing variables or mechanisms

### 6. Stubborn Variation (High-Priority Puzzles)

Identify instances where two participants with the **same structural position** (e.g., same role, same demographics, same entry pathway) responded in **opposite ways**. These are your highest-priority puzzles.

**For each instance of stubborn variation:**
- Name the two (or more) participants
- Describe their shared structural position
- Document their opposite responses/trajectories
- Frame the puzzle clearly: "Given that A and B share [structural position], why did A do X while B did Y?"

**IMPORTANT:** Do NOT resolve these puzzles. Simply frame them precisely. The resolution comes in Phase 4.

Examples of what to look for:
- Two movement veterans with similar backgrounds who took opposite positions on inside/outside strategy
- Two POC members with similar demographics who had opposite experiences in caucuses
- Two professionals who contributed skills but had opposite trajectories in the organization

### 7. Anomaly Clustering

Group anomalies by type:
- Do certain kinds of contradictions cluster together?
- Are there "families" of surprises that might have a common explanation?
- What would it mean if these anomalies are connected?

## Output Files to Create

Save all outputs to `/analysis/phase3-reports/`:

1. **cross-interview-contradictions.md** - Documented contradictions between participants
2. **within-interview-contradictions.md** - Internal contradictions and ambivalences
3. **theory-data-anomalies.md** - Where data exceeds theoretical frameworks
4. **variation-analysis.md** - Mapping and explaining variation
5. **negative-cases.md** - Cases that contradict emerging patterns
6. **stubborn-variation.md** - High-priority puzzles where same position led to opposite outcomes
7. **anomaly-clusters.md** - Grouped anomalies and their potential connections
8. **phase3-report.md** - Executive summary including:
   - Most significant contradictions identified
   - Patterns in the anomalies
   - Key negative cases and what they suggest
   - Variation that remains unexplained
   - The "puzzle" taking shape: What needs to be explained?
   - Recommendations for Phase 4 theory development

## Example Contradiction Documentation

```markdown
## Contradiction #4: Role of [X] in [Process]

### Participant A (Interview 3)
> "Quote showing position A..."

**Context**: A is [background/position] discussing [situation]

**Position**: [Summarize their stance]

---

### Participant B (Interview 7)
> "Quote showing contradicting position..."

**Context**: B is [background/position] discussing [situation]

**Position**: [Summarize their contradicting stance]

---

### Analysis

**Nature of contradiction**: [Surface-level disagreement? Fundamentally different worldviews? Different experiences of same phenomenon?]

**What might explain it**:
1. A and B occupy different positions (A is [X], B is [Y])
2. They may be discussing different time periods
3. Their stakes in the matter differ: A has [X] while B has [Y]

**What this contradiction reveals**:
- The phenomenon is not uniform—it depends on [factors]
- There may be competing logics or scripts at play
- [Other theoretical implications]

**Questions raised**:
- Is this a matter of perspective or are they describing different realities?
- What would we need to know to adjudicate?
- Does existing theory account for this variation?
```

## Example Variation Matrix

```markdown
## Variation Matrix: Responses to [Phenomenon X]

| Participant | Response Type | Key Features | Background |
|-------------|---------------|--------------|------------|
| P1 | Acceptance | Embraces fully, sees as opportunity | Long tenure, senior position |
| P2 | Resistance | Active opposition | Newcomer, alternative background |
| P3 | Ambivalence | Mixed feelings, strategic compliance | Middle position, competing loyalties |
| P4 | Acceptance | Embraces but differently than P1 | Long tenure but different role |
| P5 | Resistance | But different rationale than P2 | Similar to P2 background |

**Patterns**:
- Tenure seems to matter, but...
- Position/role may be more important because...
- Notable exception: P4 has long tenure but [differs from P1 in X way]

**Unexplained variation**:
- P3 and P6 have similar backgrounds but opposite responses
- What else might explain this?
```

## Guiding Principles

1. **Contradictions are data, not problems**: Don't try to resolve contradictions by deciding who's "right." The contradiction itself is the phenomenon.

2. **Variation needs explanation, not averaging**: Don't seek the "typical" response. Explain why responses differ.

3. **Negative cases are valuable**: One clear exception is more analytically useful than ten confirming cases.

4. **Resist premature explanation**: Document anomalies fully before theorizing. Phase 4 is for theory development.

5. **Look for patterns in the anomalies**: Individual surprises become powerful when they cluster or connect.

## When You're Done

Return a summary to the orchestrator that includes:
1. Confirmation that all files were created
2. Number and types of contradictions documented
3. The most significant anomaly patterns identified
4. Key negative cases and their implications
5. The emerging "puzzle": What needs theoretical explanation?
6. Recommended focus for Phase 4 theory development
