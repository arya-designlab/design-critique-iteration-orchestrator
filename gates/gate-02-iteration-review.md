---
gate: G2
name: Human Iteration Review
phase: Phase 02 — Iteration Strategy
reviewer: Human reviewer
artifacts:
  - outputs/phase-02/prioritized-issues.md
  - outputs/phase-02/iteration-plan.md
source_evidence:
  - outputs/phase-01/context-findings.md
  - outputs/phase-01/design-findings.md
  - outputs/phase-01/critique-report.md
  - outputs/reviews/gate-01-critique-review.md
decision_record: outputs/reviews/gate-02-iteration-review.md
approve_to: Final V1 Design Critique → Iteration Strategy output
---

# Gate G2 — Human Iteration Review

## Purpose and Authority

G2 is the mandatory final Human approval gate for Phase 02 — Iteration Strategy. The Human reviewer reviews the complete Phase 02 iteration-strategy package before it is considered approved as the final V1 workflow output.

The `design-iteration-agent` may prepare, present, explain, validate, and revise the Phase 02 artifacts. It must never approve G2, record approval on a Human reviewer's behalf, or bypass this final Human checkpoint.

Silence, agent validation, automated checks, artifact existence, or a request to continue is not approval. Only one explicit overall Human decision for the complete Phase 02 package clears or routes G2. This gate does not require separate `APPROVE`, `REVISE`, or `REJECT` decisions for individual `CR-` issues, priorities, recommendations, validation activities, tasks, or sections.

## Review Inputs and Order

The Human reviewer must review these artifacts in order:

1. `outputs/phase-02/prioritized-issues.md`
2. `outputs/phase-02/iteration-plan.md`

The reviewer may consult the approved Phase 01 package when traceability, rationale, constraints, uncertainty, or evidence boundaries need confirmation:

- `outputs/phase-01/context-findings.md`
- `outputs/phase-01/design-findings.md`
- `outputs/phase-01/critique-report.md`
- `outputs/reviews/gate-01-critique-review.md`

Phase 01 is supporting evidence for checking lineage and reasoning. The reviewer is not required to review Phase 01 from scratch.

## Review Checklist

### 1. Prioritized Issues

- [ ] Every approved `CR-` issue is represented and stable `CR-` IDs are preserved.
- [ ] Phase 01 severity is preserved and has not simply been converted into Phase 02 priority.
- [ ] Each priority has an understandable, traceable reason grounded in approved evidence, context, requirements, dependencies, constraints, certainty, or validation need.
- [ ] Dependencies and sequencing relationships are represented where relevant.
- [ ] Counterevidence, uncertainty, limitations, and validation needs remain visible.
- [ ] Issues without enough evidence to establish relative order remain `Needs validation before prioritization`.
- [ ] No unsupported effort, feasibility, business value, revenue, conversion, deadline, or strategic assumption has been invented.
- [ ] No new critique issue or reopened Phase 01 evaluation has been introduced.

### 2. Iteration Plan

- [ ] The approved problem remains clear before each recommendation and corresponds to the relevant prioritized `CR-` issue.
- [ ] Skill 4 priority classifications remain unchanged.
- [ ] Recommendations explain what should improve and what the designer could try changing.
- [ ] Recommendations are understandable, actionable, plain, direct, and designer-friendly; simple problems are not made complicated with UX jargon.
- [ ] Recommendations leave room for design exploration and do not over-prescribe unsupported exact UI specifications.
- [ ] Recommendations are presented as hypotheses to explore and validate, not guaranteed solutions.
- [ ] Relevant constraints, evidence boundaries, counterevidence, uncertainty, and unresolved questions are preserved.
- [ ] Each validation approach tests the expected improvement or remaining uncertainty, rather than applying a generic activity without a relevant question.
- [ ] Issues requiring more evidence are not given fabricated solutions.
- [ ] No new critique issue, finished redesign, wireframe, mockup, prototype, or implementation specification has been introduced.

### 3. Complete Package

- [ ] The two Phase 02 artifacts are consistent with each other and with the approved Phase 01 package.
- [ ] The reviewer can trace the reasoning without contradiction or unexplained change: approved problem → priority → improvement direction → validation approach.
- [ ] The package remains usable as actionable iteration guidance while retaining its evidence limits and validation boundaries.

## Human Decisions

| Decision | Meaning | Required action |
|---|---|---|
| `APPROVE` | The Human reviewer accepts the complete Phase 02 package as the final V1 iteration-strategy output. | Record the explicit overall decision in `outputs/reviews/gate-02-iteration-review.md`. The accepted package consists of both Phase 02 artifacts; no separate approval is required for individual `CR-` issues, priorities, recommendations, validation activities, or sections. |
| `REVISE` | The overall Phase 02 package needs changes before final approval. | Provide concise actionable feedback identifying the affected artifact, trace, rationale, recommendation, validation approach, or evidence boundary. Return work to the earliest affected Phase 02 artifact through `agents/design-iteration-agent.md`, apply the dependency logic below, and return the complete regenerated package to G2. |
| `REJECT` | The package is not acceptable in its current form, or has a fundamental evidence or scope problem that cannot be handled as a normal revision. | Stop final approval until the underlying issue is resolved. Regenerate the affected artifacts and submit the complete package to G2 for a new overall Human review. |

## Dependency Logic

The required Phase 02 dependency chain is:

```text
Approved Phase 01 package
        ↓
outputs/phase-02/prioritized-issues.md
        ↓
outputs/phase-02/iteration-plan.md
        ↓
Gate 02
```

- If `outputs/phase-02/prioritized-issues.md` needs revision, return to `skills/issue-prioritization-skill.md`. Revalidate the prioritized artifact, rerun `skills/improvement-validation-skill.md`, regenerate and revalidate `outputs/phase-02/iteration-plan.md`, then return the complete updated package to G2.
- If only `outputs/phase-02/iteration-plan.md` needs revision, return to `skills/improvement-validation-skill.md`. Keep the valid prioritization artifact unchanged, regenerate and revalidate the iteration plan, then return the complete package to G2.
- If Human feedback reveals a Phase 01 problem, do not patch it in Phase 02. Return to the earliest affected Phase 01 artifact and follow the existing Phase 01 dependency and Gate 01 logic. Once Phase 01 changes, Gate 01 must explicitly approve the changed package again; then regenerate and revalidate the dependent Phase 02 artifacts before returning the complete package to G2.
- If a revision reveals unsupported information or broken traceability, return to the earliest artifact that introduced it and rerun every dependent artifact. Do not patch a downstream artifact to hide an upstream problem.
- A `REVISE` decision does not clear G2. After even a small revision, the Human reviewer must make one new overall decision on the complete regenerated package.
- `REJECT` does not permit a workaround or partial final approval. The package remains not approved until its underlying issue is resolved and it is reviewed again.

G2 is either **APPROVED** or **NOT APPROVED**. There is no partial Gate 02 approval such as “CR-01 approved,” “recommendation 3 approved,” or “prioritization approved while the iteration plan is pending.”

## Decision Record

A future Human decision must be recorded in `outputs/reviews/gate-02-iteration-review.md`. This gate definition does not create or pre-fill that review record.

The future review record must use this structure:

```markdown
# Gate 02 — Human Iteration Review Decision

**Decision:** APPROVE | REVISE | REJECT

**Reviewed package:**
- `outputs/phase-02/prioritized-issues.md`
- `outputs/phase-02/iteration-plan.md`

**Reviewer feedback:**
[Human feedback or `None`]

**Revision target:**
[Issue Prioritization / Improvement & Validation / Phase 01 / None]

**Decision notes:**
[Optional Human notes]
```

The record may also preserve the Human reviewer and decision date when supplied. It must contain one overall package-level decision only; do not create individual decision fields for `CR-` issues, priorities, recommendations, validation activities, tasks, or sections.

Until an explicit Human `APPROVE` decision is recorded, G2 remains uncleared and the Phase 02 package is not final.

## Final Approval Meaning

Because G2 is the final Human gate for the V1 workflow, explicit `APPROVE` means:

- the Human reviewer accepts the complete Phase 02 iteration-strategy package as the final output of this workflow;
- `outputs/phase-02/prioritized-issues.md` is accepted as the final prioritization artifact; and
- `outputs/phase-02/iteration-plan.md` is accepted as the final actionable iteration and validation guidance.

Approval does not mean that every recommendation is proven to work, every uncertainty has been resolved, the design has been redesigned, recommendations have been implemented, validation has already succeeded, or the Human has individually approved every `CR-` issue or recommendation. Recommendations remain design hypotheses to explore and validate.
