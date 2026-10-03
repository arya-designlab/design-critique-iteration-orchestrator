---
phase: 2
name: Iteration Strategy
entry_from:
  - gates/gate-01-critique-review.md
trigger: An explicit Human `APPROVE` decision for the current Phase 01 critique package is recorded in `outputs/reviews/gate-01-critique-review.md`
gate: gates/gate-02-iteration-review.md
team:
  lead: agents/design-iteration-agent.md
agents:
  - agents/design-iteration-agent.md
skills_invoked:
  - skills/issue-prioritization-skill.md
  - skills/improvement-validation-skill.md
inputs:
  - outputs/phase-01/context-findings.md
  - outputs/phase-01/design-findings.md
  - outputs/phase-01/critique-report.md
  - outputs/reviews/gate-01-critique-review.md
outputs:
  - outputs/phase-02/prioritized-issues.md
  - outputs/phase-02/iteration-plan.md
exports:
  - outputs/phase-02/prioritized-issues.md
  - outputs/phase-02/iteration-plan.md
  - outputs/reviews/gate-02-iteration-review.md when an explicit Human decision is recorded
exit_to: Final V1 Design Critique → Iteration workflow completion after an explicit Human Gate 02 APPROVE
---

# P2 — Iteration Strategy

Phase 02 turns the explicitly Human-approved Phase 01 critique package into a traceable priority order and actionable, plain-language improvement and validation guidance. It preserves stable `CR-` IDs, Phase 01 severity, evidence, context, requirements, constraints, dependencies, counterevidence, uncertainty, and validation needs.

This phase does not critique the design again, create new critique findings, convert severity automatically into priority, create a finished redesign, or make a Human approval decision.

## Agent Team

| Role | Agent | Outputs produced |
|---|---|---|
| Iteration Strategy lead | `agents/design-iteration-agent.md` | Validated `outputs/phase-02/prioritized-issues.md`; validated `outputs/phase-02/iteration-plan.md`; Gate 02 review package |
| Human reviewer | Gate 02 — Human Iteration Review | One overall `APPROVE`, `REVISE`, or `REJECT` decision for the complete Phase 02 package |

The Design Iteration Agent enforces Phase 02 readiness, coordinates the skills, validates their outputs, preserves traceability, routes revisions, and stops at Human review. The skills perform the substantive transformations. The Human reviewer alone owns Gate 02 approval, revision, or rejection.

## Execution Sequence

| Step | Who | Skills | Input | Output | Gate |
|---|---|---|---|---|---|
| 1. Read operating definitions | `agents/design-iteration-agent.md` | — | Phase 02 runbook; agent definition; both Phase 02 skills; `gates/gate-01-critique-review.md`; `gates/gate-02-iteration-review.md` | Loaded execution, validation, gate, lineage, and recovery rules | Definitions must be readable before work begins |
| 2. Confirm Gate 01 entry | `agents/design-iteration-agent.md` | — | Current Phase 01 package; `outputs/reviews/gate-01-critique-review.md` | Explicit-Human-approval and package-currency assessment | Current explicit Gate 01 `APPROVE` is required |
| 3. Validate Phase 02 inputs | `agents/design-iteration-agent.md` | — | Approved Phase 01 artifacts and Gate 01 record | Readability, `CR-` lineage, evidence, constraint, uncertainty, and dependency status | Must pass before Step 4 |
| 4. Prioritize approved issues | `agents/design-iteration-agent.md` | `skills/issue-prioritization-skill.md` | Explicitly approved current Phase 01 package | `outputs/phase-02/prioritized-issues.md` | Prioritized issues complete |
| 5. Validate prioritized issues | `agents/design-iteration-agent.md` | `skills/issue-prioritization-skill.md` | Prioritized issues and approved upstream package | Current, traceable `outputs/phase-02/prioritized-issues.md` | Must pass before Step 6 |
| 6. Create improvement and validation guidance | `agents/design-iteration-agent.md` | `skills/improvement-validation-skill.md` | Validated prioritized issues and approved Phase 01 package | `outputs/phase-02/iteration-plan.md` | Iteration plan complete |
| 7. Validate iteration plan | `agents/design-iteration-agent.md` | `skills/improvement-validation-skill.md` | Iteration plan, prioritized issues, and approved upstream package | Current, reviewable `outputs/phase-02/iteration-plan.md` | Must pass before Gate 02 |
| 8. Present complete Phase 02 package | `agents/design-iteration-agent.md` | — | The two validated Phase 02 artifacts and supporting Phase 01 traceability | Ordered Gate 02 review package | Gate 02 opens |
| 9. Review and decide | Human reviewer | — | Complete Phase 02 package and Phase 01 evidence when needed | One overall `APPROVE`, `REVISE`, or `REJECT` decision | Only explicit `APPROVE` completes V1 |

The order is mandatory. Issue Prioritization cannot begin until Gate 01 explicitly approves the current Phase 01 package. Improvement & Validation cannot begin until the prioritized issues artifact is current and usable. Gate 02 cannot open until both Phase 02 artifacts pass their validation checks. There is no approval after either skill and no per-`CR-`, per-priority, per-recommendation, or per-validation-activity approval.

## Phase Inputs and Read Rules

### Required inputs

Before Phase 02 begins, read these artifacts in full:

- `outputs/phase-01/context-findings.md`
- `outputs/phase-01/design-findings.md`
- `outputs/phase-01/critique-report.md`
- `outputs/reviews/gate-01-critique-review.md`

Phase 02 requires an explicit Human Gate 01 `APPROVE` for the current Phase 01 package. Confirm the decision record identifies the reviewed artifacts clearly enough to establish that its approval applies to the available package.

### Approval and evidence rules

- Do not infer Gate 01 approval from artifact existence, previous execution, automated checks, agent validation, silence, or a request to continue.
- If any reviewed Phase 01 artifact, approved `CR-` issue set, context, requirement, constraint, evidence, traceability, counterevidence, uncertainty, or validation need changes after approval, treat Gate 01 approval as stale. Stop Phase 02 and return to the appropriate Phase 01 review path.
- Work only from the approved Phase 01 evidence package and the traceable evidence it preserves. Do not introduce new project evidence, external frameworks, or outside assumptions in this runner.
- Preserve Phase 01 severity as a record of potential documented user/task/outcome effect. Treat Phase 02 priority as a separate, traceable iteration-order decision; never map severity to priority automatically.
- Preserve stable `CR-` IDs, requirements, constraints, dependencies, counterevidence, uncertainty, limitations, and validation needs through every downstream artifact. Do not patch downstream work to hide an upstream problem.

## Part A — Issue Prioritization

**Agent:** `agents/design-iteration-agent.md`  
**Skill:** `skills/issue-prioritization-skill.md`  
**Inputs:** Explicitly Human-approved current Phase 01 package: `outputs/phase-01/context-findings.md`; `outputs/phase-01/critique-report.md`; `outputs/reviews/gate-01-critique-review.md`; and `outputs/phase-01/design-findings.md` only when existing traceability detail is needed  
**Output:** `outputs/phase-02/prioritized-issues.md`

### Step A1 — Approved-package readiness check

Read the required Phase 01 artifacts and Gate 01 record in full. Confirm an explicit Human overall `APPROVE`, current reviewed-package scope, readable artifacts, and a traceable approved `CR-` set. Confirm available context, requirements, constraints, evidence, counterevidence, uncertainty, dependencies, and validation needs can be carried forward within their source boundaries.

**Block condition:** If the Gate 01 record is missing, does not contain explicit Human `APPROVE`, is stale, or does not identify the reviewed package clearly enough to establish currency, stop Phase 02. If a required Phase 01 artifact is missing, unreadable, incomplete, or has broken approved `CR-` traceability, return to the earliest affected Phase 01 step or Gate 01 review path. Do not prioritize an uncertain or unapproved package.

### Step A2 — Create a traceable priority order

Run Issue Prioritization only on approved `CR-` issues and traceable approved evidence. The skill determines which issues should receive earlier iteration attention, which can follow, and which must remain `Needs validation before prioritization`.

Priority reasoning may use only documented impact, requirement relevance, dependencies, sequencing, constraints, evidence certainty, and validation dependencies. It must not treat Phase 01 severity as a priority label or invent effort, feasibility, business value, revenue, conversion impact, deadlines, strategy, or another unsupported factor. The runner does not perform prioritization itself.

### Step A3 — Prioritized-artifact validation

Before Part B, confirm:

- [ ] `outputs/phase-02/prioritized-issues.md` exists and is current for the explicitly approved Phase 01 package.
- [ ] Every approved `CR-` issue is represented exactly once as an individual entry, with stable IDs preserved.
- [ ] Phase 01 severity, evidence, context, constraints, dependencies, counterevidence, uncertainty, and validation needs are preserved.
- [ ] Severity has not automatically become priority, and every priority has a concise, traceable reason based only on approved evidence.
- [ ] Unknown factors remain `Not established in approved evidence`; uncertain issues remain `Needs validation before prioritization` rather than being forced into a priority tier.
- [ ] No new critique issue, reopened Phase 01 evaluation, unsupported effort/feasibility/business/revenue/conversion/deadline/strategy assumption, detailed design solution, or iteration plan has been introduced.

If any check fails, correct `outputs/phase-02/prioritized-issues.md` through the declared skill before starting Part B. Do not manually patch the artifact in this runner.

## Part B — Improvement & Validation

**Agent:** `agents/design-iteration-agent.md`  
**Skill:** `skills/improvement-validation-skill.md`  
**Inputs:** Validated `outputs/phase-02/prioritized-issues.md`; approved Phase 01 context and critique artifacts; explicit Gate 01 approval record; and Phase 01 design findings only when existing traceability detail is needed  
**Output:** `outputs/phase-02/iteration-plan.md`

### Step B1 — Prioritization handoff check

Read the validated prioritized issues artifact in full with the approved Phase 01 package. Confirm its `CR-` IDs, priorities, priority rationale, original problem meaning, Phase 01 severity, documented impact, dependencies, constraints, evidence/context trace, counterevidence, uncertainty, and validation needs are current and usable.

**Block condition:** If `outputs/phase-02/prioritized-issues.md` is missing, invalid, stale, or uncertain in provenance, return to Part A after confirming Gate 01 approval. Do not invent a priority, rerun prioritization inside this skill, or create an iteration plan from priority labels alone.

### Step B2 — Create improvement and validation guidance

Run Improvement & Validation. It must preserve the approved problem before giving guidance, keep Skill 4 priorities unchanged, translate each ready issue into a plain-language improvement hypothesis, and define a validation approach that tests the expected improvement or remaining uncertainty.

Directions must tell the designer what should improve and how they could approach it without prescribing unsupported exact UI specifications or creating a finished redesign. Issues that still need evidence must remain visibly non-actionable rather than receiving fabricated recommendations. The runner does not create or rewrite recommendations itself.

### Step B3 — Iteration-plan validation

Before opening Gate 02, confirm:

- [ ] `outputs/phase-02/iteration-plan.md` exists and is current for the validated prioritized issues and approved Phase 01 package.
- [ ] Every relevant `CR-` issue is represented, stable IDs are preserved, and Skill 4 priority classifications remain unchanged.
- [ ] The approved problem remains visible before every actionable recommendation, and recommendations correspond to the approved problem and evidence.
- [ ] Recommendations explain what should improve and how a designer could approach it in plain, direct, designer-friendly language; simple issues are not made unnecessarily complicated with UX jargon.
- [ ] Recommendations remain actionable but non-prescriptive, do not invent unsupported exact UI specifications, and are framed as hypotheses rather than proven solutions.
- [ ] Relevant constraints, evidence boundaries, counterevidence, uncertainty, dependencies, and validation needs are preserved.
- [ ] Each validation approach tests the expected improvement or uncertainty; issues needing more evidence are not given fabricated solutions.
- [ ] No new critique issue, fresh priority decision, finished redesign, wireframe, mockup, prototype, or implementation specification has been introduced.

If any check fails, correct `outputs/phase-02/iteration-plan.md` through the declared skill before opening Gate 02. Do not manually rewrite recommendations in this runner. If the cause originates in `outputs/phase-02/prioritized-issues.md`, return to Part A, correct the priority artifact, and regenerate all dependent work.

## Gate 02 — Human Iteration Review

Follow [Gate G2 — Human Iteration Review](../gates/gate-02-iteration-review.md) at `gates/gate-02-iteration-review.md`. It is the mandatory final Human gate for the V1 Design Critique → Iteration workflow.

Present the validated Phase 02 artifacts in order:

1. `outputs/phase-02/prioritized-issues.md`
2. `outputs/phase-02/iteration-plan.md`

The Human reviewer gives one overall decision for the complete Phase 02 package: `APPROVE`, `REVISE`, or `REJECT`. Do not require individual decisions for `CR-` issues, priorities, recommendations, validation activities, tasks, or sections.

The Design Iteration Agent may present, explain, validate, and revise the package but cannot approve G2. Silence, artifact existence, automated validation, agent validation, or a generic request to continue is not approval. The future Human decision must be recorded in `outputs/reviews/gate-02-iteration-review.md`; do not create or pre-fill that record while defining or executing the runner unless explicitly authorized to record a Human decision.

### Gate 02 decision behaviour

- **`APPROVE`:** Record the decision according to Gate 02. Treat the complete Phase 02 package as Human-approved and describe the V1 Design Critique → Iteration workflow as complete. Approval accepts the iteration-strategy package; it does not prove, implement, or validate recommendations, and it does not create another phase.
- **`REVISE`:** Use Human feedback to identify the earliest affected artifact. If prioritization changes, rerun and validate Issue Prioritization, then rerun and validate Improvement & Validation. If only iteration guidance changes, rerun and validate Improvement & Validation. If feedback reveals a Phase 01 problem, return to its earliest affected artifact, follow Phase 01 dependency and Gate 01 logic, obtain a new explicit Gate 01 approval, then regenerate affected Phase 02 outputs. Return the complete regenerated package to Gate 02 for one new overall decision.
- **`REJECT`:** Stop final workflow completion, preserve the rejection and Human feedback, identify the earliest affected artifact or evidence/scope problem, and resolve it before the complete package can return for Human review. Do not create a workaround or partial approval.

A `REVISE` decision never partially clears G2. Before explicit Gate 02 approval, describe the state only as **Ready for Gate 02 Human review**—not approved, final, accepted, or complete workflow.

## Exceptions

| Failure condition | Recovery action |
|---|---|
| `outputs/reviews/gate-01-critique-review.md` is missing or unreadable | Stop Phase 02, list the exact affected path, and request the required Human Gate 01 decision record. Do not run either Phase 02 skill. |
| Gate 01 has no explicit Human `APPROVE` | Stop Phase 02. Do not infer approval or run Issue Prioritization or Improvement & Validation. |
| Gate 01 approval is stale or cannot be connected to the current Phase 01 package | Return to the appropriate Phase 01 review path and require a new explicit Human decision before resuming Phase 02. |
| A required Phase 01 artifact is missing, unreadable, incomplete, or has broken approved `CR-` traceability | Stop Phase 02 and return to the earliest affected Phase 01 skill or Gate 01 review path. Do not recreate Phase 01 context or critique here. |
| `outputs/phase-02/prioritized-issues.md` is missing, incomplete, stale, or invalid | Return to Part A through `skills/issue-prioritization-skill.md`, then revalidate before Part B can run. |
| Prioritization loses a `CR-` ID, Phase 01 severity, evidence lineage, constraint, dependency, counterevidence, uncertainty, validation need, or supported priority rationale | Return to Issue Prioritization. Correct the earliest responsible artifact and rerun Improvement & Validation if the prioritized artifact changes materially. |
| Prioritization uses unsupported effort, feasibility, business value, revenue, conversion, deadline, strategy, or another invented factor | Return to Issue Prioritization. Remove or mark the factor as not established through the skill; do not replace it with an assumption. |
| `outputs/phase-02/iteration-plan.md` is missing, incomplete, stale, or invalid | Return to Part B through `skills/improvement-validation-skill.md` after validating prioritized issues. Do not rerun Part A unless its artifact caused the problem. |
| Skill 5 changes a Skill 4 priority classification or changes the approved problem meaning | Return to Improvement & Validation. Restore the traceable prioritized state through the skill and revalidate the plan. |
| A recommendation is jargon-heavy, unclear, or violates the plain-language requirement | Return to Improvement & Validation for clearer, direct, designer-friendly language. Do not rewrite it in the runner. |
| A recommendation is unsupported, violates a documented constraint, or introduces an exact UI specification without evidence | Return to Improvement & Validation. Narrow or remove it through the skill; do not substitute a runner-created recommendation. |
| A recommendation is presented as proven rather than hypothetical | Return to Improvement & Validation. Restore qualified language and a relevant validation need through the skill. |
| A validation approach is irrelevant, generic, or does not test the expected improvement or uncertainty | Return to Improvement & Validation. Define the relevant validation question through the skill without inventing thresholds, sample sizes, or outcomes. |
| An upstream revision leaves a downstream artifact stale | Return to the earliest changed artifact, rerun every dependent skill, and revalidate each regenerated output. Do not patch the stale downstream artifact. |
| Gate 02 has no Human decision record | Present the complete validated package and stop at **Ready for Gate 02 Human review**. Do not infer approval or workflow completion. |
| Gate 02 returns `REVISE` | Route feedback to the earliest affected artifact using Gate 02 dependency logic, regenerate and revalidate dependent artifacts, then return the complete package to G2 for one new overall decision. |
| Gate 02 returns `REJECT` | Stop final workflow completion. Resolve the underlying evidence, scope, or artifact problem before the complete package can return to G2; do not create partial approval. |

## Phase Handoff

The Phase 02 handoff to Gate 02 consists of:

- `outputs/phase-02/prioritized-issues.md`
- `outputs/phase-02/iteration-plan.md`

Relevant approved Phase 01 artifacts remain available for traceability: `outputs/phase-01/context-findings.md`, `outputs/phase-01/design-findings.md`, `outputs/phase-01/critique-report.md`, and `outputs/reviews/gate-01-critique-review.md`.

Before explicit Gate 02 approval, the package is **Ready for Gate 02 Human review** only. After explicit Human Gate 02 `APPROVE`, the runner may describe the state as **V1 Design Critique → Iteration workflow complete**. Do not create or hand off to Phase 03.
