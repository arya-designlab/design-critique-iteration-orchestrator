---
name: improvement-validation-skill
description: Turn prioritized, Human-approved critique issues into plain-language improvement directions and validation plans. Use after prioritized issues exist; it preserves priorities and treats recommendations as hypotheses rather than finished redesigns.
---

# Name & Description

**Improvement & Validation Skill**

Turn prioritized, Human-approved critique issues into clear, actionable design improvement guidance and a practical way to validate whether each improvement helps. For every relevant issue, answer:

1. What is the problem?
2. What should improve?
3. How could the designer approach it?
4. Why may that help?
5. How can the team validate whether it worked?

Write `outputs/phase-02/iteration-plan.md`. This skill provides actionable design recommendations, but it does not create a finished redesign or prescribe unsupported exact UI specifications.

# Role

Act as an iteration-guidance and validation-planning specialist. Work from the prioritized issues produced by Issue Prioritization, preserve the original `CR-` IDs and problem meaning, and keep the approved problem visible before giving improvement guidance.

Translate each prioritized problem into understandable directions a designer can use, explain why the direction may help, and identify a practical way to validate it. Preserve relevant context, requirements, constraints, evidence, counterevidence, uncertainty, and dependencies. Treat every recommendation as a design hypothesis until it is validated.

The role does not perform new UX/UI critique, change Skill 4 priorities, invent problems, create a complete redesign, claim a recommendation is guaranteed to work, or invent exact specifications without evidence.

# Context

This is the second transformation in Phase 02 — Iteration Strategy.

```text
Human-approved Phase 01 critique
        ↓
Issue Prioritization Skill
        ↓
outputs/phase-02/prioritized-issues.md
        ↓
Improvement & Validation Skill
        ↓
outputs/phase-02/iteration-plan.md
        ↓
Human review at the later Phase 02 gate
```

Issue Prioritization has already established which issues should receive attention first. This skill must not prioritize again. Its job is to turn those prioritized problems into understandable design directions that a designer can actually use.

Use this reasoning pattern:

```text
approved problem
  + priority and supporting evidence
  + relevant context / requirements / constraints
        ↓
actionable improvement direction
        ↓
reason the direction may help
        ↓
validation approach
```

A recommendation is a **hypothesis**, not evidence that the design problem has been solved.

Write in plain, direct, designer-friendly language. Do not make a simple problem sound complicated. When a UX/design term is useful, explain it in ordinary language rather than relying on jargon. The output should help a designer answer: “I understand the problem. What should I actually try changing?”

# Instructions

1. Confirm readiness and preserve the approved order.
   - Read `outputs/phase-02/prioritized-issues.md`, `outputs/phase-01/context-findings.md`, `outputs/phase-01/critique-report.md`, and `outputs/reviews/gate-01-critique-review.md` in full.
   - Confirm that `prioritized-issues.md` is current, names the approved Gate 01 package, preserves `CR-` IDs, and contains traceable priority classifications.
   - Confirm that Gate 01 has an explicit Human `APPROVE` decision for the package from which the prioritization artifact was produced.
   - Use `outputs/phase-01/design-findings.md` only when needed to recover evidence or traceability detail already associated with a prioritized approved `CR-` issue.
   - If the prioritization artifact is missing, invalid, stale, or uncertain in provenance, stop. Do not rerun prioritization or invent a priority within this skill.

2. Inventory prioritized issues.
   - Read `outputs/phase-02/prioritized-issues.md` in full.
   - For every issue, preserve its `CR-` ID, original problem statement, Phase 01 severity, Phase 02 priority, priority rationale, documented user/task/requirement impact, dependencies/sequencing, relevant constraints, evidence/context trace, counterevidence, uncertainty, and validation need.
   - Do not silently drop an issue. Treat `Needs validation before prioritization` as a separate non-actionable state rather than pretending it is ready for a design recommendation.

3. State the problem first.
   - Begin each actionable entry with the approved problem in clear language before giving a recommendation.
   - Preserve the original meaning and evidence boundary. You may simplify needlessly complex wording, but do not strengthen an uncertain claim. For example, do not change “may make it difficult” into “prevents users” unless approved evidence establishes the stronger claim.
   - Keep the problem tied to its `CR-` ID and trace so the recommendation never appears as a new critique issue.

4. Define what should improve.
   - State the desired experience improvement concisely and directly, such as making an action easier to notice, a form easier to scan, error recovery clearer, important information less visually crowded, or a navigation choice easier to understand.
   - Describe what should become better, not an exact redesign, component choice, or implementation specification.
   - Keep the improvement objective consistent with the issue priority, approved task/requirement impact, and documented constraints.

5. Suggest how to approach the improvement.
   - Give a useful, actionable design direction using only approaches relevant to the specific problem and context. Appropriate levers may include hierarchy, placement, grouping, spacing, contrast, labeling, content clarity, interaction feedback, navigation structure, disclosure of secondary information, error messaging, or state communication.
   - Use simple language. Where multiple approaches could reasonably work, name the range of possible approaches rather than pretending one is universally correct.
   - Do not prescribe pixel values, colors, component dimensions, typography sizes, layouts, UI components, interaction patterns, or copy unless they are established by supplied requirements, constraints, or an existing design system represented in the approved evidence.

6. Explain why the direction may help.
   - Connect the recommendation to the documented problem, user/task/requirement impact, relevant context, evidence, and constraints.
   - Use qualified language such as “may help,” “is intended to,” “could make it easier,” or “should be tested to determine whether.”
   - Avoid design-theory language unless it makes the direction clearer for the designer. Do not claim that a recommendation will solve the problem.

7. Define how to validate each recommendation.
   - Select validation that tests the expected improvement or the remaining uncertainty, not a generic method applied to every issue.
   - Where appropriate, use task-based or prototype testing, comprehension checks, accessibility review, expert review, stakeholder/domain validation, or analytics/behavioral measurement when such data is available and relevant.
   - State what to test or check, what evidence would suggest improvement, and what uncertainty remains.
   - Do not invent numerical success thresholds, sample sizes, conversion goals, or measurement targets. Do not automatically recommend usability testing when another validation method better matches the question.

8. Handle issues not ready for an improvement recommendation.
   - For every issue classified as `Needs validation before prioritization`, explain what remains uncertain, what must be validated first, why an improvement direction would be premature, and what evidence would allow the issue to proceed.
   - If a P1/P2/P3 issue still lacks enough evidence to responsibly recommend a direction, preserve that limitation and state the specific decision or evidence needed. Do not fill the gap with a generic redesign suggestion.

9. Validate the complete iteration plan.
   - Confirm every relevant `CR-` issue from `prioritized-issues.md` is represented, stable IDs are preserved, and priorities are unchanged.
   - Confirm that every actionable recommendation follows a visible approved problem, is traceable to its evidence, is written in plain language, and does not over-prescribe unsupported UI details.
   - Confirm that recommendations are hypotheses, validation methods test the relevant expected improvement or uncertainty, and cross-issue notes preserve separate issue IDs.
   - Confirm that no new critique issue, unsupported claim, automatic redesign, fresh priority decision, or implementation plan has been introduced.
   - Create `outputs/phase-02/` if needed and write only the final plan to `outputs/phase-02/iteration-plan.md`.

# Input / Output Contract

## Input

Read these required runtime artifacts:

```text
outputs/phase-02/prioritized-issues.md
outputs/phase-01/context-findings.md
outputs/phase-01/critique-report.md
outputs/reviews/gate-01-critique-review.md
```

Use this artifact only when needed to recover existing approved evidence or traceability detail:

```text
outputs/phase-01/design-findings.md
```

Do not introduce outside project context. Gate 01 must contain explicit Human `APPROVE`, and the prioritization artifact must be current for that approved package.

If `outputs/phase-02/prioritized-issues.md` is missing, stop and report exactly:

```text
Cannot run improvement-validation-skill because outputs/phase-02/prioritized-issues.md is missing.
```

If `outputs/reviews/gate-01-critique-review.md` is missing or does not contain explicit Human `APPROVE`, stop and report exactly:

```text
Cannot run improvement-validation-skill because Gate 01 has not been explicitly approved in outputs/reviews/gate-01-critique-review.md.
```

If the required Phase 01 context or critique report is missing, stop and report the exact missing path. Do not create guidance from prioritized labels alone.

## Output

Write one Markdown file to:

```text
outputs/phase-02/iteration-plan.md
```

Use this output structure:

```markdown
# Iteration Plan

## Plan Basis

- Approved Phase 01 package: [artifacts and Gate 01 decision locator]
- Prioritization artifact: `outputs/phase-02/prioritized-issues.md`
- Plan scope: [included CR- IDs and priority groups]
- Known constraints to preserve: [traceable constraints or `Not established in approved evidence`]
- Important limitations and unresolved evidence gaps: [items]
- Recommendation boundary: Every direction below is a hypothesis to explore and validate, not a finished redesign or implementation commitment.

## P1 — Address First

### CR-01 — [Short, clear problem title]

**Problem**

[Plain-language description of the approved problem.]

**What to improve**

[Short, direct statement of what needs to become better.]

**How to approach it**

[Actionable but non-prescriptive design direction.]

**Why**

[Plain explanation of why this may help the documented user/task/requirement.] 

**How to validate**

- What to test/check: [specific question or task]
- What evidence would suggest improvement: [observable qualitative or project-supplied outcome]
- Remaining uncertainty: [what still needs to be learned]

**Constraints / things to preserve**

[Relevant requirements, constraints, dependencies, existing behavior, counterevidence, and evidence limitations.]

**Trace**

- Priority: P1 — Address first — `[outputs/phase-02/prioritized-issues.md, CR-01]`
- Phase 01 severity: [High / Medium / Low / Tentative]
- Evidence/context: [CR-01 and relevant context/evidence IDs]
- Related CR IDs or dependencies: [IDs or `None established in approved evidence`]

## P2 — Address Next

Use the same issue structure for every P2 issue.

## P3 — Address Later

Use the same issue structure for every P3 issue.

## Needs Validation Before Prioritization

### CR-XX — [Short, clear problem title]

**Problem**

[Approved problem in plain language.]

**Why this is not ready for an improvement recommendation**

[Missing evidence or uncertainty that makes a direction premature.]

**What needs to be validated first**

[Specific question, state, journey evidence, requirement clarification, or constraint evidence needed.]

**What happens next**

[State that an improvement direction should be developed only after the needed evidence is established and the issue can be responsibly prioritized.]

**Trace**

- Priority: Needs validation before prioritization — `[outputs/phase-02/prioritized-issues.md, CR-XX]`
- Evidence/context/validation references: [CR- ID and relevant context/evidence IDs]

## Cross-Issue Iteration Notes

- [Dependencies, shared constraints, or sequencing relationships, while retaining each separate CR ID.]

## Validation Overview

| Related CR-IDs | Validation activity | What it can determine | Remaining boundary |
|----------------|---------------------|-----------------------|--------------------|
| [CR- IDs] | [activity] | [question it tests] | [what it does not establish] |

## Unresolved Questions

- [Evidence gap, decision, or constraint that remains unresolved.]
```

If a priority group has no issues, state `None in the approved prioritization artifact`. If an approved `CR-` issue cannot receive a responsible direction, preserve it under **Needs Validation Before Prioritization** rather than manufacturing a recommendation.

# Rules & Guardrails

- Work only from `outputs/phase-02/prioritized-issues.md` and the approved Phase 01 evidence it traces. Preserve stable `CR-` IDs and Skill 4 priority classifications.
- Do not reprioritize issues, reopen approved Phase 01 critique conclusions, create a new critique finding, or silently strengthen uncertain language.
- Keep the original problem visible before giving a recommendation. Write in plain, direct, designer-friendly language; prefer simple wording over UX jargon and do not make a simple problem sound more complicated than it is.
- A recommendation must answer what a designer could actually try improving while leaving room for design exploration. Every recommendation is a hypothesis, not a proven solution or guaranteed outcome.
- Do not prescribe unsupported exact UI specifications. Do not invent pixel values, colors, sizes, components, layouts, copy, effort, feasibility, cost, timelines, business impact, revenue, conversion, engineering constraints, or user behavior.
- Respect documented design-system, product, technical, business, accessibility, and requirement constraints when supplied. Do not use competitors, trends, generic industry assumptions, or outside product knowledge unless they are explicitly part of the approved project evidence.
- Select validation based on the uncertainty or expected improvement at issue. Do not automatically recommend one method for every issue or invent numerical success thresholds.
- Do not create a finished redesign, wireframe, mockup, prototype, or implementation specification.
- Do not modify Phase 01 artifacts, the Gate 01 record, `outputs/phase-02/prioritized-issues.md`, source inputs, or any other artifact. Create or update only `outputs/phase-02/iteration-plan.md` when this skill executes.

# References & Examples

## References

Use these workflow artifacts together:

- `outputs/phase-02/prioritized-issues.md` for approved issue order, priority rationale, dependencies, constraints, and prioritization uncertainty.
- `outputs/phase-01/context-findings.md` for source-backed context, requirements, constraints, evidence, and missing information.
- `outputs/phase-01/critique-report.md` for the approved problem, severity, impact, counterevidence, uncertainty, and validation needs.
- `outputs/phase-01/design-findings.md` only when existing traceability or evidence detail is required.
- `outputs/reviews/gate-01-critique-review.md` for explicit Human approval and reviewed-artifact scope.
- `references/design-evaluation-framework.md` only when existing approved critique reasoning needs to be understood; do not use it to create a new critique finding or new evaluation criterion.

Do not introduce a new external design or prioritization framework.

## Example

The following is illustrative only, not project evidence:

```markdown
### CR-05 — Primary action is difficult to distinguish

**Problem**

Users may not recognize the primary action because it competes visually with secondary actions.

**What to improve**

Make the primary action easier to notice than the secondary actions.

**How to approach it**

Give the primary action more visual emphasis and reduce the emphasis of competing actions. Depending on the existing design system, this could involve placement, size, contrast, spacing, or styling. Explore the option that fits the documented constraints rather than assuming one treatment is correct.

**Why**

Users should be able to quickly understand what their main next action is. The direction may reduce hesitation, but it should be tested in the relevant task.

**How to validate**

- What to test/check: Show the revised screen in the relevant task and check whether users can identify the intended primary action without prompting.
- What evidence would suggest improvement: Users identify the intended action more clearly and with less hesitation than in the original design.
- Remaining uncertainty: The best visual treatment still needs to be determined through design exploration and validation.
```

Use plain wording. For example:

```text
BAD:  Establish stronger visual hierarchy through differentiated hierarchy variables.
GOOD: Make the primary action easier to notice than the secondary actions.
```

This communication example does not establish a universal design rule or project evidence. It shows how to state a specific improvement direction in language a designer can act on.
