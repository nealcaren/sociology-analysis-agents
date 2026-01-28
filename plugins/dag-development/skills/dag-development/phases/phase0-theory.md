# Phase 0: Theory → DAG Translation

You are helping the user turn their current thinking into a **DAG blueprint** that can be rendered later. This phase is about *conceptual translation*, not statistical adjustment decisions.

## Why This Phase Matters

A DAG is an explicit statement of causal assumptions. It forces clarity about **what causes what**, **what is measured**, **what is conditioned on**, and **where selection or observation processes might bias interpretation**. This is useful in both quantitative and qualitative research because it makes implicit causal claims visible and testable.

## Inputs to Request

Primary path (recommended):
- **One core paper** (full text or PDF) the user wants translated into a DAG.

Alternative inputs if no paper is available:
- **Research notes** (bullets, memos, fieldnotes, or a theory summary)
- **Draft outline** or **methods section**
- **Concept map** or **variable list**

Always ask for:
- **Causal question**: What is the effect of X on Y, and over what time horizon?
- **Unit of analysis**: Individual, organization, neighborhood, field, event.
- **Treatment definition**: What does “X” actually mean? Is it a policy, exposure, practice, event, or status? Are there multiple versions of X?
- **Outcome definition**: What counts as Y? How is it measured or observed?
- **Key context**: Setting, time period, institutions, constraints.
- **Selection/visibility**: Who enters the data, and who becomes visible to the researcher?

## Translation Workflow (Expanded)

### 1. Clarify the causal question and estimand
- Define **exposure (X)**, **outcome (Y)**, and **contrast** (e.g., higher vs lower X).
- State the **causal estimand** in plain language (total effect vs. direct effect; short‑term vs long‑term).
- Specify **time ordering** (t0, t1, t2). Treat time‑stamped variables as distinct nodes when needed (X_t0, X_t1).

### 2. Extract claims from the core paper (if provided)
If the user provided a core paper, do this first:
- Scan **abstract, theory, methods, results, discussion** for causal claims.
- Extract each claim into a **claim table** (below).
- Prioritize claims that explicitly use causal language (cause, effect, influence, leads to).

### 3. Define the treatment and outcome precisely
- If “X” has **multiple versions**, represent as separate nodes or note as an assumption.
- If “Y” is a **constructed measure**, add a **measurement node** (M_Y) and note what determines observation.

### 4. Decompose the narrative into mechanisms
Ask: “If X changes, *through what processes* would Y change?”
- Convert each mechanism into a **mediator** node.
- Use short, concrete labels (e.g., “resource access,” “network tie,” “policy enforcement”).

### 5. Identify common causes (confounding structure)
Ask: “What prior factors shape both X and Y?”
- Add these as **parents** of X and Y.
- If a common cause is not measured, mark as **U** (unobserved) and note it in assumptions.

### 6. Identify selection and observation processes
For both quant and qual work, selection matters.
- **Selection into sample**: Who is observed and why? Add **S** (selection) node.
- **Observation/measurement**: What affects whether X or Y is recorded? Add **M_X** and **M_Y** if needed.
- Draw arrows into **S** from factors that affect inclusion; note that conditioning on S can induce collider bias.

### 7. Check for colliders and post‑treatment variables
- If a node is a **common effect** of two causes, it is a collider.
- Avoid conditioning on descendants of X when the goal is the total effect (unless explicitly estimating mediated effects).
- If X influences a confounder later in time, mark as **time‑varying confounding**.

### 8. Build the first‑pass DAG blueprint
Create a list of:
- Nodes with short labels
- Directed edges (A -> B)
- **Assumptions log**: why each edge exists, and what is omitted
- **Uncertain edges**: edges that are plausible but contested

### 9. Create alternative DAGs if needed
If more than one theory fits the data:
- Draft 2–3 competing DAGs
- Note which edges differ and what evidence would adjudicate between them

## Claim Table Template (Paper‑First Workflow)

Use this table to translate paper text into DAG edges:

```
Claim ID | Source (section/page) | Claim (verbatim/paraphrase) | Nodes | Edge | Type | Confidence
---------|------------------------|-----------------------------|-------|------|------|-----------
C1       | Theory p.4             | “X increases Y through M”   | X,M,Y | X->M, M->Y | mediator | High
C2       | Methods p.7            | “Z is controlled because…”  | Z,X,Y | Z->X, Z->Y | confounder | Medium
C3       | Discussion p.12        | “Selection into sample…”    | S,X,Y | X->S, Y->S | selection | Medium
```

Then synthesize the DAG from the union of high‑confidence edges, and flag low‑confidence edges as uncertain or alternative.

## Quantitative Translation Checklist

- Are X and Y defined as **pre/post** with clear temporal order?
- Are there **pre‑treatment confounders** that influence both?
- Are there **post‑treatment mediators** you should not adjust for?
- Is there **selection** (sample inclusion, attrition, missingness) affected by X or Y?
- Are there **time‑varying confounders** (Z_t that both affects later X and is affected by earlier X)?

## Qualitative Translation Checklist

- What is the **narrative mechanism** linking X to Y?
- What **decisions or actions** bridge the link (mediators)?
- Who becomes **visible** or **recorded** (selection/observation nodes)?
- What **contextual conditions** are required for the mechanism (context nodes)?
- Where are **plausible alternative stories** that would change the edges?

## Qualitative-Specific Prompts

Use these to translate interpretive narratives into DAGs:
- “What decisions or actions bridge X to Y?” → mechanisms/mediators
- “Who gets into the story?” → selection node
- “What accounts are more likely to be visible or recorded?” → measurement nodes
- “What conditions make the mechanism possible?” → moderators or context nodes
- “What would have to be different for the mechanism *not* to operate?” → alternative edges

## Quantitative-Specific Prompts

- “What pretreatment factors drive both X and Y?” → confounders
- “Is any variable affected by X and also used for adjustment?” → potential post-treatment bias
- “Is selection into the dataset influenced by X or Y?” → selection node

## Common Pitfalls to Flag

- **Adjusting for mediators** when estimating total effects.
- **Conditioning on colliders** (common effects) and inducing bias.
- **Ignoring selection into data** (who is observed and why).
- **Ambiguous treatment** (multiple versions of X without clarity).
- **Missing time ordering** (treating processes as contemporaneous when they are not).

## Output: DAG Blueprint

Provide a structured blueprint the rendering phases can use:

```
DAG Blueprint

Causal Question:
- Effect of X on Y over [time window]

Nodes:
- X (exposure)
- Y (outcome)
- M1 (mechanism)
- Z1 (confounder)
- S (selection)
- U1 (unobserved)

Edges:
- Z1 -> X
- Z1 -> Y
- X -> M1
- M1 -> Y
- U1 -> X
- U1 -> Y
- X -> S
- Y -> S

Assumptions Log:
- Z1 is prior to X and Y
- M1 is downstream of X
- S represents inclusion into the dataset

Uncertain Edges:
- U1 -> X (low confidence)
- U1 -> Y (medium confidence)
```

## Handoff to Phase 1 (Rendering Inputs)

Before moving on, produce the **render‑ready inputs** Phase 1 needs:
- **Node labels**: short labels for the figure (2–8 words each)
- **Edge list**: clean `A -> B` statements
- **Node types**: observed, unobserved (U), selection (S), measurement (M)
- **Uncertain edges**: mark for dashed/dotted styling
- **Grouping** (optional): context / mechanisms / selection subgraphs

Deliver these as a simple block the user can paste into Phase 1.

## When You’re Done

Return a summary to the orchestrator with:
1. The DAG blueprint (nodes + edges)
2. Assumptions log
3. Uncertain edges and alternative DAGs
4. Any missing inputs to request

## Suggested Readings

- Greenland, Pearl, Robins (1999). Causal diagrams for epidemiologic research.
- Shrier & Platt (2008). Reducing bias through directed acyclic graphs.
- Hernan & Robins (2020, with ongoing updates). Causal Inference: What If.
- Morgan & Winship (2007/2015). Counterfactuals and Causal Inference (causal graphs chapters).
