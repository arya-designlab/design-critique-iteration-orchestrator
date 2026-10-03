---
name: ux-ui-evaluation-skill
description: Evaluate submitted design evidence against supplied context and the controlled design-evaluation framework to produce traceable, evidence-backed UX/UI findings. Use after context findings exist; it does not synthesize, prioritize, or solve findings.
---

# Name & Description

**UX/UI Evaluation Skill**

Evaluate a submitted UI/UX design in its documented product, user, task, requirement, and constraint context. Use observable design evidence, `outputs/phase-01/context-findings.md`, and `references/design-evaluation-framework.md` to identify defensible UX/UI findings. Every finding must connect an observation to relevant context, an applicable principle or clearly labelled general guidance, and a plausible user impact.

This skill creates a structured finding set for later critique synthesis. It does not decide the final critique, prioritize work, prescribe a redesign, or create new project requirements.

# Role

Act as an evidence-conscious UX/UI evaluator. Inspect only the submitted design scope and assess only the evaluation areas relevant to the documented task and context. Make findings useful to a designer by explaining the observed basis, the contextual reason it may matter, and the evidence still needed to validate the concern.

Treat established principles as contextual evaluation lenses, not universal pass/fail rules. Preserve evidence that supports the submitted design or contradicts an apparent concern; do not force a negative finding.

# Context

This is the second transformation in Phase 01 — Design Critique. It follows Context & Requirement Evaluation and precedes Critique Synthesis.

```text
Submitted design evidence + supplied project materials
        ↓
outputs/phase-01/context-findings.md
        ↓
UX/UI Evaluation Skill + references/design-evaluation-framework.md
        ↓
outputs/phase-01/design-findings.md
        ↓
Critique Synthesis Skill
```

`context-findings.md` is the source of truth for what the supplied materials establish about the product, users, tasks, goals, explicit requirements, constraints, feedback, research, assumptions, ambiguities, and missing information. The reference framework is the controlled knowledge source for evaluation principles and their limitations. Neither source authorizes an evaluator to invent evidence that is absent from the design or project materials.

Relevant areas may include usability; discoverability and comprehension; system feedback; consistency; user control; error prevention and recovery; interaction clarity; information and visual hierarchy; grouping; typography and readability; cognitive load; and observable accessibility concerns. Do not force coverage of every area when the submitted scope or evidence does not make it relevant.

# Instructions

1. Confirm inputs and evaluation boundaries.
   - Read `outputs/phase-01/context-findings.md` and `references/design-evaluation-framework.md` in full before evaluating the design.
   - Read the submitted screenshots, walkthrough recordings, and any source material identified as relevant in `context-findings.md`.
   - Confirm that the context artifact identifies usable submitted design evidence and a usable design brief, requirements document, or project-context source.
   - If the context artifact, framework, or required design evidence is missing or unusable, stop and report the exact missing path or limitation. Do not evaluate from memory or substitute outside knowledge.

2. Establish the evaluation scope and coverage plan.
   - Identify the documented users, tasks, goals, explicit requirements, constraints, supplied evidence, ambiguities, and evaluation boundaries that apply to the submitted design scope.
   - Inventory the meaningful visible regions, sections, and components actually present in the supplied design. Derive the inventory from the evidence; do not assume a universal page structure or require a header, cards, form, CTA, footer, or any other component that is not supplied.
   - For every evaluation area supported by `references/design-evaluation-framework.md`, determine whether it is `Applicable and evaluated`, `Not applicable to supplied design`, or `Cannot determine from supplied evidence`.
   - For every `Applicable and evaluated` area, identify the relevant visible regions/components to inspect. Do not mark an area as covered merely because another area or an early part of the design was reviewed.
   - For every `Cannot determine from supplied evidence` area, name the missing design, interaction, implementation, user, or project evidence needed. Do not convert the absence into a design problem.
   - Carry forward the source limitations from `context-findings.md`, including where a screenshot, recording, feedback item, or research source can establish only limited evidence.

3. Perform a systematic evaluation coverage pass.
   - Inspect every inventoried meaningful visible region/component in the supplied design, including regions that are later in a long page, lower in a capture, or less visually prominent.
   - Apply each `Applicable and evaluated` framework area to the relevant visible portions of the design, rather than treating the category as covered by a general impression.
   - Record a concise coverage outcome for every inspected region/component and evaluation area. When no meaningful concern is established, use `Reviewed — no material concern established from supplied evidence` rather than manufacturing a finding.
   - During the coverage pass, identify candidate concerns and relevant counterevidence. A candidate is an observation to test, not a `CR-` finding.

4. Record observable design evidence before making an evaluative claim.
   - For each candidate concern, identify what is directly visible in a screenshot or directly demonstrated in a walkthrough recording.
   - Cite a precise locator: screenshot filename plus screen/frame description, or recording filename plus time range. Cite text, annotations, developer tools, accessibility-tree output, or assistive-technology output only when directly shown.
   - Keep a direct observation separate from any inference about usability, behavior, comprehension, accessibility, or impact.

5. Test candidate findings against context and the framework.
   - Link the observation to the relevant `CTX-`, `USR-`, `TASK-`, `GOAL-`, `REQ-`, `EVD-`, `ASM-`, or `AMB-` item in `context-findings.md`.
   - Select a principle or general-guidance area from `references/design-evaluation-framework.md` that is relevant to that documented context.
   - State a plausible user impact using qualified wording such as `may`, `could`, or `requires validation` unless supplied evidence directly establishes the outcome.
   - Inspect relevant counterevidence before promoting a candidate. Promote it to a `CR-` finding only when observable design evidence + relevant product/user/task context + applicable principle/guidance + plausible user impact form a defensible chain.
   - Do not raise a finding if the only basis is personal preference, an unspecified convention, a trend, a framework principle without contextual relevance and plausible impact, or missing evidence.

6. Create only defensible findings.
   - Give every substantive finding a stable ID in sequence: `CR-01`, `CR-02`, and so on.
   - Use a concise, single-claim finding statement. Split unrelated observations or impacts into separate findings.
   - Record the applicable evaluation area, direct observation, context/evidence trace, framework trace, plausible impact, supporting or contradictory evidence, and evidence limitations.
   - State what would validate, narrow, or refute the finding when the available materials cannot establish it fully.

7. Preserve requirement alignment and counterevidence.
   - Record when the submitted design visibly supports an important explicit requirement, but do not treat visual presence alone as proof that the requirement works in use.
   - If supplied feedback, research, a walkthrough recording, or a stated constraint contradicts an apparent concern, preserve that information in the relevant finding or alignment note.
   - Do not create a negative finding merely to cover a framework category. An area with no defensible concern should remain a coverage note, not a manufactured critique item.

8. Handle accessibility within the available evidence.
   - Raise a visible accessibility item only as an observable concern or validation need unless the supplied evidence is sufficient for the relevant requirement.
   - A screenshot alone cannot establish semantic structure, programmatic names or roles, text alternatives, keyboard operation, focus order, reflow, assistive-technology behavior, or WCAG conformance.
   - A recording can establish only the accessibility behavior directly demonstrated at its cited time range. Do not generalize it to unshown states, devices, inputs, or assistive technologies.

9. Complete the full-scope review before finalizing the finding set.
   - Confirm every meaningful supplied design region/component was inspected and represented in the coverage record.
   - Confirm every framework area is recorded as `Applicable and evaluated`, `Not applicable to supplied design`, or `Cannot determine from supplied evidence`; confirm every applicable area was actually considered in its relevant visible region/component.
   - Confirm findings reflect evidence across the reviewed scope rather than only the first, largest, or most obvious region. Do not make distribution a target or a reason to create a finding.
   - Confirm that every promoted `CR-` finding survived the candidate test and that ungrounded candidates remain coverage notes, counterevidence, or evidence limitations rather than findings.
   - Confirm that no finding was invented to demonstrate coverage and that counterevidence and uncertainty remain preserved.
   - Confirm that each `CR-` finding has all four required links: observable evidence, relevant context, applicable principle/guidance, and plausible impact.
   - Confirm that requirements, user behavior, accessibility failures, design standards, laws, benchmarks, and best practices have not been invented.
   - Remove duplicate findings, unsupported claims, solution language, final prioritization, and critique-report synthesis.
   - Write only the final finding set to `outputs/phase-01/design-findings.md`.

# Input / Output Contract

## Input

Read these required artifacts:

```text
projects/design_critique_iteration_orchestrator/input/
  - Submitted design screenshot(s) and any available walkthrough video(s) or screen recording(s)
  - Design brief, requirements, or project-context material

outputs/phase-01/context-findings.md
references/design-evaluation-framework.md
```

Use optional stakeholder/user feedback, usability-test findings, research, and product/business/technical constraints only when `context-findings.md` identifies them as supplied and relevant. Preserve their source scope and limitations.

If `outputs/phase-01/context-findings.md` is missing, stop and report exactly:

```text
Cannot run ux-ui-evaluation-skill because outputs/phase-01/context-findings.md is missing.
```

If `references/design-evaluation-framework.md` is missing, stop and report exactly:

```text
Cannot run ux-ui-evaluation-skill because references/design-evaluation-framework.md is missing.
```

## Output

Write one Markdown file to:

```text
outputs/phase-01/design-findings.md
```

Use this output structure:

```markdown
# Design Findings

## Evaluation Basis

- Primary context input: `outputs/phase-01/context-findings.md`
- Evaluation framework: `references/design-evaluation-framework.md`
- Submitted design evidence evaluated: [screenshot and recording paths with screen/frame/time-range scope]
- Relevant context, task, and requirements: [applicable CTX-/USR-/TASK-/GOAL-/REQ- IDs]
- Evidence limitations carried forward: [limitations from context findings]

## Supplied Design Coverage

| Visible region / component | Evidence locator | Inspection outcome | Evaluation areas considered |
|----------------------------|------------------|--------------------|----------------------------|
| [region/component derived from supplied design] | [screenshot/frame or recording time range] | Reviewed — no material concern established from supplied evidence / Candidate promoted to CR-XX / Cannot determine | [applicable framework areas considered and material limitation, if any] |

Include every meaningful visible region/component in the submitted design. This is an inspection record, not a requirement that every row produce a finding.

## Evaluation-Area Coverage

| Area | Status | Scope or reason |
|------|--------|-----------------|
| [framework area from `references/design-evaluation-framework.md`] | Applicable and evaluated / Not applicable to supplied design / Cannot determine from supplied evidence | [relevant inspected region/component and CR- ID or `Reviewed — no material concern established from supplied evidence`; or reason/missing evidence] |

## Findings

### CR-01: [Concise, single-claim finding statement]

**Evaluation area:** [for example, visibility of system status]

**Observable design evidence:**
- [What is directly visible or demonstrated] — `[screenshot/frame or recording time range]`

**Relevant context and evidence:**
- [Relevant documented user, task, goal, requirement, constraint, or evidence statement] — `[outputs/phase-01/context-findings.md, ID]`

**Applicable principle or guidance:**
- [Principle/guidance name and its contextual relevance] — `[references/design-evaluation-framework.md, section]`

**Finding rationale:**
- [How the observation, context, and principle connect; do not prescribe a solution.]

**Plausible user impact:**
- [Qualified impact on the documented task or user, such as `may make it harder to ...`]

**Supporting or contradictory evidence:**
- [Relevant EVD-/REQ-/constraint evidence, or `None supplied`]

**Evidence limitation and validation need:**
- [What screenshots, recordings, feedback, testing, or implementation evidence cannot establish and what would validate the concern]

## Requirement Alignment and Counterevidence

| Context ID | Observation | Status | Evidence limitation |
|------------|-------------|--------|---------------------|
| REQ-01 | [visible or demonstrated alignment, or counterevidence] | Appears supported / Contradicts apparent concern / Cannot determine | [what remains unproven] |

## Unresolved Evaluation Limits

- [Framework area, design state, interaction, user evidence, or implementation evidence that could not be evaluated]

## Coverage Completion Check

- Meaningful supplied design regions/components inspected: [region/component list or reference to **Supplied Design Coverage**]
- Framework areas applicable and evaluated: [areas and relevant regions/components]
- Reviewed with no material concern established: [areas/regions]
- Cannot determine from supplied evidence: [areas/regions and missing evidence]
- Candidate concerns not promoted: [brief reason, such as insufficient context, counterevidence, or missing evidence]
- Coverage boundary: Broad inspection does not require a finding count. `CR-` findings remain limited to candidates that meet the evidence standard.

## Handoff to Critique Synthesis

- Findings available for consolidation: [CR- IDs]
- Potential duplicates or related findings: [CR- IDs, if any]
- Evidence limitations and counterevidence that must be preserved: [items]
- This artifact identifies findings only; it does not assign severity, make approval decisions, prioritize iteration work, or recommend design changes.
```

If no defensible UX/UI finding can be raised, write that outcome plainly, retain the evaluation coverage and unresolved limits, and do not invent a `CR-` item. If an important requirement appears visibly supported, record it in **Requirement Alignment and Counterevidence** rather than converting it into a positive UX conclusion.

# Rules & Guardrails

- Use `context-findings.md` as the source of truth for supplied facts, requirements, users, tasks, goals, constraints, feedback, research evidence, assumptions, ambiguities, and missing information.
- Use `references/design-evaluation-framework.md` as the controlled UX/UI knowledge source. Do not add external heuristics, UX laws, trends, competitor conventions, benchmarks, numerical thresholds, or unprovided standards.
- Raise a finding only when observable design evidence, relevant context, applicable principle/guidance, and plausible impact form a defensible chain.
- Complete the systematic coverage pass before finalizing. Inspect the full supplied design scope, including later or less prominent meaningful regions, and record what was reviewed even when no finding results.
- Comprehensive evaluation does not mean maximum criticism. Do not target a minimum, maximum, or distribution of `CR-` findings; a design with few evidence-supported concerns should produce few findings.
- A coverage record, candidate observation, framework area, or visible deviation is not itself a finding. Do not promote it without the required evidence chain and relevant counterevidence review.
- Do not treat a principle, common convention, platform pattern, or personal preference as a universal pass/fail rule.
- Do not invent user behavior, usability evidence, design requirements, constraints, standards, accessibility failures, technical details, business priorities, or “best practices.”
- Preserve uncertainty. Use qualified impact language when the source does not directly establish the outcome, and name the validation evidence required.
- Distinguish visible accessibility concerns from WCAG conformance. Do not claim WCAG compliance or failure unless the supplied evidence supports the applicable success criterion.
- Do not infer unshown interactions, responsive states, system feedback, error handling, semantics, implementation behavior, or assistive-technology behavior from a static screenshot. Do not generalize a demonstrated recording path beyond its cited scope.
- Do not make redesign recommendations, name UI components as solutions, prescribe visual changes, or prioritize findings. Those activities belong to later skills.
- Do not modify `outputs/phase-01/context-findings.md`, `references/design-evaluation-framework.md`, source inputs, or any other artifact. Write only `outputs/phase-01/design-findings.md` when this skill is executed.

# References & Examples

## References

Use these required artifacts together:

- `outputs/phase-01/context-findings.md` for project-specific facts, requirements, evidence, and limitations.
- `references/design-evaluation-framework.md` for controlled usability, visual-organization, interaction-clarity, and accessibility evaluation guidance.

Do not use a framework section merely because it exists. Apply it only when the submitted design scope and documented context make it relevant.

## Example

Assume the context artifact contains these scoped items:

- `TASK-01`: Returning customers are expected to complete checkout on mobile.
- `GOAL-01`: Checkout should be completed quickly.
- `EVD-01`: In one usability session, a participant looked for delivery cost before confirming an order; the evidence does not establish prevalence or whether the submitted screen caused difficulty.

The submitted evidence contains `checkout-screen.png`, which visibly shows a primary confirmation action, and no screenshot or recording that shows delivery cost, a selected delivery method, or a post-confirmation state.

An acceptable excerpt from `outputs/phase-01/design-findings.md` is:

```markdown
### CR-01: Delivery-cost information is not visible in the submitted checkout state despite its relevance to the documented confirmation task

**Evaluation area:** Discoverability and comprehension

**Observable design evidence:**
- The submitted checkout state shows an order summary and a primary confirmation action; no delivery-cost information is visible in this submitted state — `[projects/design_critique_iteration_orchestrator/input/checkout-screen.png, checkout screen]`

**Relevant context and evidence:**
- Returning customers are expected to complete checkout on mobile — `[outputs/phase-01/context-findings.md, TASK-01]`
- Checkout should be completed quickly — `[outputs/phase-01/context-findings.md, GOAL-01]`
- One participant looked for delivery cost before confirmation — `[outputs/phase-01/context-findings.md, EVD-01]`

**Applicable principle or guidance:**
- Discoverability, comprehension, and recognition rather than recall — `[references/design-evaluation-framework.md, Discoverability, comprehension, and recognition rather than recall]`

**Finding rationale:**
- The submitted state presents the confirmation action without showing delivery cost. Given the documented confirmation task and the supplied participant report, the cost may be task-relevant information that users need to recognize before acting.

**Plausible user impact:**
- Some users may hesitate before confirmation or proceed without information they consider relevant to the purchase decision.

**Supporting or contradictory evidence:**
- The participant report supports relevance for one observed session. No supplied evidence establishes whether delivery cost appears earlier in the flow or is intentionally excluded from this order type.

**Evidence limitation and validation need:**
- The submitted state does not establish the full checkout flow, delivery-method behavior, or prevalence of the concern. Review the preceding checkout state and test whether intended users can find and understand delivery cost before confirmation.
```

This example identifies a qualified concern from the submitted state and source-backed context. It does not claim that every user is confused, that the product violates a standard, or which interface change should be made.
