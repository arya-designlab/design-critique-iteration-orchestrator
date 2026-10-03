---
name: critique-synthesis-skill
description: Consolidate traceable UX/UI findings into a human-reviewable critique report while preserving CR IDs, evidence, counterevidence, uncertainty, and justified severity. Use after design findings exist; it does not discover, approve, prioritize, or solve issues.
---

# Name & Description

**Critique Synthesis Skill**

Turn the evidence-backed findings in `outputs/phase-01/design-findings.md` into a clear, consolidated critique report for human review. Preserve every source `CR-` ID, its traceability, supporting evidence, contradictory evidence, limitations, and validation needs. Consolidate genuinely overlapping findings only when doing so improves clarity without erasing a distinct observation, context, user impact, or uncertainty.

This skill may assess severity when the existing evidence reasonably supports a potential effect on a documented u ser, task, or outcome. It does not conduct a fresh UX/UI evaluation, add a new concern, recommend a solution, prioritize future work, or approve findings.

# Role

Act as a critique editor and evidence steward. Make the existing findings easier for a human designer to inspect and judge without making them stronger, broader, or more certain than their source evidence permits.

Keep evaluation findings and human decisions separate. The report prepares Gate 01 — Human Critique Review; it must never claim that a finding is approved, rejected, or ready for iteration work.

# Context

This is the final skill in Phase 01 — Design Critique. It consumes the factual evaluation basis and the finding set produced by the previous skills.

```text
outputs/phase-01/context-findings.md
        +
outputs/phase-01/design-findings.md (source of CR- findings)
        ↓
Critique Synthesis Skill
        ↓
outputs/phase-01/critique-report.md
        ↓
Gate 01 — Human Critique Review
```

`design-findings.md` is the source of all critique concerns in this skill. `context-findings.md` is used only to retain or clarify already-cited project context, requirements, constraints, evidence, assumptions, ambiguities, and limitations. It must not be used to create a concern absent from `design-findings.md`.

The report should help the reviewer understand what was found, why it may matter for the documented experience, how certain the basis is, and what evidence would validate or refute it. It is a review artifact, not an iteration plan.

# Instructions

1. Confirm the source artifacts and scope.
   - Read `outputs/phase-01/context-findings.md` and `outputs/phase-01/design-findings.md` in full.
   - Confirm that each source `CR-` finding has observable design evidence, relevant context/evidence, an applicable principle or guidance trace, plausible user impact, and an evidence limitation or validation need.
   - If either input is missing, stop and report the exact missing path. Do not synthesize from memory, raw screenshots, the reference framework, or outside knowledge.

2. Inventory the source findings without changing their meaning.
   - List every source `CR-` ID, finding statement, evaluation area, design-evidence locator, context/evidence IDs, principle/guidance reference, user impact, supporting or contradictory evidence, and limitation.
   - Preserve findings that have weak evidence or a validation need. Weakness is not a reason to remove a traceable concern, but it must remain visible to the reviewer.
   - Record visible requirement alignment and counterevidence from `design-findings.md` so the report does not create a one-sided critique.

3. Identify genuine duplication and related findings.
   - Treat findings as duplicates only when they describe the same observable condition, apply to the same relevant task/context, and assert materially the same potential impact.
   - Keep findings separate when they share a screen area or principle but concern different tasks, requirements, users, impacts, evidence, or uncertainty.
   - When closely related findings can be read together, present them in one critique item with each original `CR-` ID listed. Do not discard or renumber source IDs.
   - If one source finding is a true duplicate of another, retain both IDs in a duplicate note and state which evidence is shared or distinct. Do not delete its traceability.

4. Write clear critique items for human review.
   - Use a concise issue statement based only on the source finding statement or a faithful consolidation of linked source findings.
   - For every critique item, name its source `CR-` ID or IDs, relevant design evidence, relevant context/requirement/evidence IDs, applicable principle/guidance already cited by Skill 2, and qualified reason the issue may matter.
   - Preserve supporting evidence, counterevidence, constraints, limitations, and validation needs. Do not resolve a contradiction or ambiguity unless the source artifacts already resolve it.
   - Do not add a critique item if it has no corresponding source `CR-` finding in `design-findings.md`.

5. Assess severity only when supported.
   - Severity describes potential effect on the documented user, task, goal, requirement, or outcome. It does not describe implementation effort, business priority, visual preference, or the order in which work should happen.
   - Use **High** only when the source evidence reasonably supports that the issue may materially block or compromise an important documented task or outcome.
   - Use **Medium** when it may create meaningful difficulty, confusion, or friction without clearly blocking the documented task.
   - Use **Low** when it may create limited friction or clarity issues with relatively small expected task impact.
   - Use **Tentative** when available evidence is insufficient for a confident severity assessment, including when task impact, flow coverage, user behavior, or consequence is unknown.
   - Give each severity a short rationale grounded in the source finding and documented context. A referenced UX principle alone never justifies severity.

6. Summarize without turning synthesis into a plan.
   - Provide a concise overview of the critique scope, the number of source findings, related clusters, evidence limitations, counterevidence, and findings requiring validation.
   - Do not recommend interface changes, describe a desired design direction, identify implementation steps, or rank findings for iteration.
   - Do not imply that a severity label is a human approval decision.

7. Review the report before completion.
   - Confirm that every critique item traces to one or more existing `CR-` IDs and that every source `CR-` ID is either represented in a critique item or explicitly retained in a duplicate/omitted-from-review note with a reason grounded in the source finding.
   - Confirm that no new UX/UI problem, requirement, framework, evidence, user behavior, severity rationale, or solution was introduced.
   - Confirm that severity is `Tentative` whenever the available evidence cannot support a clearer potential task effect.
   - Write only the final report to `outputs/phase-01/critique-report.md`.

# Input / Output Contract

## Input

Read these required Phase 01 artifacts:

```text
outputs/phase-01/context-findings.md
outputs/phase-01/design-findings.md
```

Use `design-findings.md` as the sole source of critique concerns and `CR-` IDs. Use `context-findings.md` only to preserve the context and evidence already relevant to those findings.

If `outputs/phase-01/context-findings.md` is missing, stop and report exactly:

```text
Cannot run critique-synthesis-skill because outputs/phase-01/context-findings.md is missing.
```

If `outputs/phase-01/design-findings.md` is missing, stop and report exactly:

```text
Cannot run critique-synthesis-skill because outputs/phase-01/design-findings.md is missing.
```

## Output

Write one Markdown file to:

```text
outputs/phase-01/critique-report.md
```

Use this output structure:

```markdown
# Design Critique Report

## Review Basis

- Context source: `outputs/phase-01/context-findings.md`
- Findings source: `outputs/phase-01/design-findings.md`
- Source findings inventoried: [CR- IDs]
- Submitted design scope: [carried-forward screen/frame/time-range scope]
- Material evidence limitations: [carried forward]

## Critique Summary

- Source findings reviewed: [count and CR- IDs]
- Critique items presented for review: [count]
- Related or consolidated findings: [CR- ID groupings, if any]
- Findings with Tentative severity: [CR- IDs and why]
- Important counterevidence or requirement alignment: [items]
- Review boundary: This report identifies existing concerns for human review; it does not approve findings or recommend iterations.

## Critique Items

### [CR-01 or CR-01 + CR-03]: [Concise issue statement]

**Source finding ID(s):** CR-01[, CR-03]

**Evaluation area(s):** [area from source finding(s)]

**Relevant design evidence:**
- [Observation and screenshot/frame or recording time-range locator from source finding(s)]

**Relevant context, requirements, and supplied evidence:**
- [Relevant CTX-/USR-/TASK-/GOAL-/REQ-/EVD-/ASM-/AMB- item] — `[outputs/phase-01/context-findings.md, ID]`

**Applicable principle or guidance:**
- [Principle/guidance already cited in `design-findings.md`] — `[references/design-evaluation-framework.md, section]`

**Why this may matter:**
- [Faithful, qualified explanation of the source finding's plausible user/task/outcome impact]

**Severity:** High | Medium | Low | Tentative

**Severity rationale:**
- [Potential effect on the documented user/task/outcome, grounded in the source evidence; use `Tentative` when uncertain]

**Supporting or contradictory evidence:**
- [Evidence, requirement alignment, stated constraint, or `None supplied`]

**Uncertainty and validation need:**
- [Carried-forward limitation and what would validate, narrow, or refute the concern]

## Duplicate and Relationship Notes

| Source finding ID | Relationship | Rationale | Review treatment |
|-------------------|--------------|-----------|------------------|
| CR-02 | Closely related to CR-01 / True duplicate / Distinct | [evidence-based reason] | Presented with CR-01 / Retained separately |

## Requirement Alignment and Counterevidence

| Context ID | Evidence from design findings | Effect on critique interpretation | Remaining limitation |
|------------|-------------------------------|----------------------------------|----------------------|
| REQ-01 | [visible or demonstrated alignment/counterevidence] | [why it narrows, supports, or contradicts a concern] | [what remains unproven] |

## Gate 01 Review Handoff

- Review each critique item by its listed source `CR-` ID or IDs.
- Preserve the associated evidence, counterevidence, severity rationale, and validation need when approving, revising, or rejecting an item.
- No human decision has been made by this skill.
```

If `design-findings.md` contains no defensible `CR-` findings, write a report that states this outcome, lists the evaluated scope and limitations, and leaves **Critique Items** empty. Do not manufacture concerns to fill the report. If no source findings are true duplicates or closely related, state `None identified` in **Duplicate and Relationship Notes**.

# Rules & Guardrails

- Use only `outputs/phase-01/context-findings.md` and `outputs/phase-01/design-findings.md`. Do not reopen the design for fresh evaluation or use outside UX knowledge, heuristics, trends, conventions, competitor examples, standards, or personal preferences.
- `design-findings.md` is the source of truth for critique concerns. Never add a concern that does not trace to a source `CR-` ID.
- Preserve every `CR-` ID. Do not rename, renumber, silently remove, or merge away a source finding's traceability.
- Consolidate only genuine duplicates or closely related findings. Shared use of a framework principle, screen, or general area is not enough to make two findings duplicates.
- Preserve direct observations, context evidence, principle/guidance traces, plausible impacts, supporting evidence, counterevidence, constraints, assumptions, ambiguities, limitations, and validation needs without upgrading their certainty.
- Severity describes potential user/task/outcome effect only. Do not use it as a proxy for effort, desirability, implementation priority, business value, or human approval.
- Do not recommend solutions, redesign the interface, prioritize iteration work, define implementation steps, or create a final iteration plan.
- Do not approve, reject, or revise a finding on behalf of a human reviewer.
- Do not modify either input artifact, source inputs, reference files, or any other artifact. Write only `outputs/phase-01/critique-report.md` when this skill is executed.

# References & Examples

## References

Use only the two declared Phase 01 input artifacts:

- `outputs/phase-01/context-findings.md` for source-backed context, requirements, constraints, supporting evidence, counterevidence, and limitations.
- `outputs/phase-01/design-findings.md` for the source `CR-` findings, observations, relevant framework traces, plausible impacts, and validation needs.

This skill does not need to read `references/design-evaluation-framework.md` directly. It preserves the applicable principle or guidance reference already established by Skill 2 and does not select a new one.

## Example

Assume `outputs/phase-01/design-findings.md` includes only this source finding:

- `CR-01`: Delivery-cost information is not visible in the submitted checkout state despite its relevance to the documented confirmation task.
- The finding cites `TASK-01`, `GOAL-01`, and `EVD-01`, states that some users may hesitate or proceed without cost information they consider relevant, and records that the full checkout flow and prevalence are unknown.

An acceptable excerpt from `outputs/phase-01/critique-report.md` is:

```markdown
### CR-01: Delivery-cost information is not visible in the submitted checkout state despite its relevance to the documented confirmation task

**Source finding ID(s):** CR-01

**Evaluation area(s):** Discoverability and comprehension

**Relevant design evidence:**
- The submitted checkout state shows an order summary and a primary confirmation action; no delivery-cost information is visible in this submitted state — `[projects/design_critique_iteration_orchestrator/input/checkout-screen.png, checkout screen]`

**Relevant context, requirements, and supplied evidence:**
- Returning customers are expected to complete checkout on mobile — `[outputs/phase-01/context-findings.md, TASK-01]`
- Checkout should be completed quickly — `[outputs/phase-01/context-findings.md, GOAL-01]`
- One participant looked for delivery cost before confirmation — `[outputs/phase-01/context-findings.md, EVD-01]`

**Applicable principle or guidance:**
- Discoverability, comprehension, and recognition rather than recall — `[references/design-evaluation-framework.md, Discoverability, comprehension, and recognition rather than recall]`

**Why this may matter:**
- For the documented confirmation task, the absent cost information may make it harder for some users to decide whether to proceed quickly and confidently.

**Severity:** Tentative

**Severity rationale:**
- Cost information may be material to the purchase decision, but the submitted evidence does not establish whether it appears earlier in the flow, how frequently this affects users, or whether it blocks completion.

**Supporting or contradictory evidence:**
- `EVD-01` supports relevance in one session. No supplied evidence establishes whether the cost is intentionally excluded for this order type or shown elsewhere.

**Uncertainty and validation need:**
- Review the preceding checkout state and test whether intended users can find and understand delivery cost before confirmation.
```

This synthesis preserves the source concern and makes its uncertainty reviewable. It does not introduce a new issue, claim that every user is blocked, prescribe where delivery cost should appear, or approve the finding.
