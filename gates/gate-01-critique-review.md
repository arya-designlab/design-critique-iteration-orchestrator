---
gate: G1
name: Human Critique Review
phase: Phase 01 — Design Critique
reviewer: Human reviewer
artifacts:
  - outputs/phase-01/context-findings.md
  - outputs/phase-01/design-findings.md
  - outputs/phase-01/critique-report.md
source_evidence: projects/design_critique_iteration_orchestrator/input/
decision_record: outputs/reviews/gate-01-critique-review.md
approve_to: Phase 02 — Iteration Strategy
---

# Gate G1 — Human Critique Review

## Purpose and Authority

G1 is the mandatory human approval gate between Phase 01 — Design Critique and Phase 02 — Iteration Strategy. Phase 02 must not begin until a Human reviewer explicitly returns `APPROVE` for the complete Phase 01 critique package.

The `design-critic-agent` may prepare, explain, validate, and revise the Phase 01 artifacts. It must never approve G1, record approval on a Human reviewer's behalf, or advance the workflow to Phase 02.

Silence, agent validation, automated checks, artifact existence, or a request to continue is not approval. Only one explicit overall Human decision for the Phase 01 package clears or routes G1. This gate does not require separate `APPROVE`, `REVISE`, or `REJECT` decisions for individual `CR-` findings.

## Review Inputs and Order

The Human reviewer must review these artifacts in order:

1. `outputs/phase-01/context-findings.md`
2. `outputs/phase-01/design-findings.md`
3. `outputs/phase-01/critique-report.md`

The reviewer may inspect the underlying project evidence in `projects/design_critique_iteration_orchestrator/input/` whenever a requirement, design observation, source item, assumption, contradiction, limitation, severity rationale, or critique finding needs confirmation.

## Review Checklist

### 1. Context & Requirement Findings

- [ ] Supplied inputs and relevant product/design context are represented accurately and traceably.
- [ ] Requirements, users, tasks, goals, constraints, and supplied evidence retain precise source locators and appropriate scope.
- [ ] Facts, stakeholder assertions, user/research evidence, assumptions, ambiguities, contradictions, and missing information remain distinguished.
- [ ] Screenshot and recording evidence is not generalized beyond the submitted screens, frames, states, or time ranges.
- [ ] No unsupported context, requirement, user need, technical detail, or constraint has been invented.

### 2. UX/UI Design Findings

- [ ] Every `CR-` finding is grounded in observable design evidence with a valid screenshot/frame or recording time-range locator.
- [ ] Each finding is relevant to the documented product, user, task, goal, requirement, or constraint context.
- [ ] Applicable UX/UI principle or guidance remains traceable to the controlled evaluation framework.
- [ ] Plausible user impact is qualified to the evidence rather than presented as an unverified fact.
- [ ] Supporting evidence, counterevidence, uncertainty, limitations, and validation needs are preserved.
- [ ] Findings are not based only on personal preference, a trend, an unspecified convention, or an unsupported best practice.
- [ ] Visible accessibility concerns remain distinct from WCAG conformance claims unless sufficient implementation or interaction evidence is supplied.

### 3. Critique Report

- [ ] The report accurately represents all source `CR-` findings in `outputs/phase-01/design-findings.md`.
- [ ] Consolidation, duplicate treatment, and wording preserve source IDs, material evidence, counterevidence, and traceability.
- [ ] Severity reflects potential effect on a documented user, task, goal, requirement, or outcome—not implementation effort, iteration order, business priority, or personal preference.
- [ ] Severity is `Tentative` wherever the available evidence cannot support a clearer assessment.
- [ ] Uncertainty and validation needs remain visible to the reviewer.
- [ ] No redesign recommendation, iteration priority, approval decision, or unsupported new critique concern has been introduced.

## Human Decisions

| Decision | Meaning | Required action |
|---|---|---|
| `APPROVE` | The Human reviewer accepts the complete Phase 01 critique package as suitable for Iteration Strategy. | Record the explicit overall decision in `outputs/reviews/gate-01-critique-review.md`, then allow handoff to Phase 02 — Iteration Strategy. |
| `REVISE` | One or more Phase 01 artifacts need correction, clarification, stronger traceability, or another revision. | Provide actionable feedback identifying the affected artifact, finding, evidence, severity rationale, or review check. Return work to the appropriate Phase 01 step through `agents/design-critic-agent.md`, apply the dependency logic below, and return to G1. |
| `REJECT` | The Phase 01 critique package is not suitable to proceed on the available evidence or scope. | Stop the workflow at Phase 01 until the underlying issue is resolved. Obtain the needed evidence or scope clarification, regenerate the affected package, and submit it to G1 for a new overall review. |

## Dependency Logic

The required Phase 01 dependency chain is:

```text
outputs/phase-01/context-findings.md
        ↓
outputs/phase-01/design-findings.md
        ↓
outputs/phase-01/critique-report.md
```

- If `outputs/phase-01/context-findings.md` changes, revalidate it and rerun UX/UI Evaluation and Critique Synthesis before returning the package to G1.
- If only `outputs/phase-01/design-findings.md` changes, revalidate it and rerun Critique Synthesis before returning the package to G1.
- If only critique consolidation, wording, duplicate treatment, or severity needs correction, rerun and validate only Critique Synthesis before returning the package to G1.
- If a revision reveals that an earlier artifact contains unsupported information or broken traceability, return to the earliest affected Phase 01 step and rerun every dependent artifact.
- A revision does not clear G1. After revised artifacts are produced, the Human reviewer must issue a new explicit overall decision.
- `REJECT` does not permit a workaround or partial handoff to Phase 02. The package remains blocked until its underlying issue is resolved and it is reviewed again.

## Decision Record

A future Human decision must be recorded in `outputs/reviews/gate-01-critique-review.md`. This gate definition does not create or pre-fill that review record.

The future review record must preserve:

- the overall decision: `APPROVE`, `REVISE`, or `REJECT`;
- the Human reviewer and decision date when supplied;
- the Phase 01 artifacts reviewed and their paths;
- the Human reviewer's feedback or reason;
- requested revisions, affected artifact paths, and relevant `CR-` IDs when applicable; and
- the resulting route: Phase 02 handoff, Phase 01 revision, or Phase 01 stopped.

Until an explicit Human `APPROVE` decision is recorded, G1 remains uncleared and Phase 02 remains blocked.
