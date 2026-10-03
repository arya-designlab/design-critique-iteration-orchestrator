# Project Orchestrator

## Scope and path rules

- The project root is `/Users/airfi/Documents/Codex/week_3_assignment`.
- All paths in this orchestrator are relative to that project root unless an absolute path is shown.
- The workflow has exactly two phases, in order: Phase 1 — Design Critique (`workflow/run-phase-01.md`) and Phase 2 — Iteration Strategy (`workflow/run-phase-02.md`). There is no Phase 3.
- Phase 1 is coordinated by `agents/design-critic-agent.md`, uses `skills/context-requirement-evaluation-skill.md`, `skills/ux-ui-evaluation-skill.md`, and `skills/critique-synthesis-skill.md`, and ends at `gates/gate-01-critique-review.md`.
- Phase 2 is coordinated by `agents/design-iteration-agent.md`, uses `skills/issue-prioritization-skill.md` and `skills/improvement-validation-skill.md`, and ends at `gates/gate-02-iteration-review.md`.
- The controlled evaluation reference is `references/design-evaluation-framework.md`.
- Runtime project inputs belong in `projects/design_critique_iteration_orchestrator/input/`. Phase 1 writes to `outputs/phase-01/`; Phase 2 writes to `outputs/phase-02/`; explicit Human review records belong in `outputs/reviews/`.
- Phase 1 runtime outputs are `outputs/phase-01/context-findings.md`, `outputs/phase-01/design-findings.md`, and `outputs/phase-01/critique-report.md`. The declared G1 review record is `outputs/reviews/gate-01-critique-review.md`.
- Phase 2 runtime outputs are `outputs/phase-02/prioritized-issues.md` and `outputs/phase-02/iteration-plan.md`. The declared G2 review record is `outputs/reviews/gate-02-iteration-review.md`.
- No project-state file is defined. Determine progress from actual inputs, artifacts, their traceability and currency, and explicit Human decisions.
- Do not invent missing phases, agents, skills, gates, outputs, review records, reference frameworks, or state files.

## First action

1. Read this orchestrator.
2. Read both phase runbooks: `workflow/run-phase-01.md` and `workflow/run-phase-02.md`.
3. Read the active phase's agent, declared skills, and gate definition.
4. Inspect actual project inputs, outputs, review records, and current artifacts. Do not infer state from an expected file that is absent or present.
5. Determine the current phase or blocked gate from actual artifact validity, lineage, and explicit Human decisions.
6. If Human approval is required, present the declared review artifacts in order and stop.

## State and routing

| Condition | Current position | Required action |
|---|---|---|
| Required design screenshot(s), or design brief/requirements/project context, are missing, inaccessible, unreadable, corrupt, or unusable under `projects/design_critique_iteration_orchestrator/input/` | Phase 1 readiness | Follow `workflow/run-phase-01.md` and `agents/design-critic-agent.md`; report the exact missing or affected input and stop. Optional feedback, usability findings, research, constraints, walkthrough videos, and screen recordings are not blockers merely because they are absent. |
| Inputs are ready, but `outputs/phase-01/context-findings.md` is missing, invalid, or stale | Phase 1 — Context & Requirement Evaluation | Route through the Design Critic Agent to `skills/context-requirement-evaluation-skill.md`, then validate the result before any UX/UI evaluation. |
| Valid context findings exist, but `outputs/phase-01/design-findings.md` is missing, invalid, or stale | Phase 1 — UX/UI Evaluation | Route through the Design Critic Agent to `skills/ux-ui-evaluation-skill.md`, then validate the result before critique synthesis. |
| Valid design findings exist, but `outputs/phase-01/critique-report.md` is missing, invalid, or stale | Phase 1 — Critique Synthesis | Route through the Design Critic Agent to `skills/critique-synthesis-skill.md`, then validate the report. |
| All valid Phase 1 artifacts exist, but G1 has no explicit Human decision | G1 — Human Critique Review | Present `context-findings.md`, `design-findings.md`, then `critique-report.md`; stop for one overall Human decision. |
| G1 returns `REVISE` | Phase 1 revision | Follow G1 and Phase 1 dependency logic: rerun the earliest affected Phase 1 step and all downstream dependencies, then return the complete package to G1. |
| G1 returns `REJECT` | Phase 1 stopped | Do not begin Phase 2. Follow Gate 1 recovery logic until the underlying evidence, scope, or artifact issue is resolved. |
| G1 explicitly returns `APPROVE` for the current Phase 1 package | Phase 2 readiness | Confirm approval currency, then route to `workflow/run-phase-02.md`. Do not infer this decision from file presence, silence, automated checks, agent validation, or a request to continue. |
| G1 is current and approved, but `outputs/phase-02/prioritized-issues.md` is missing, invalid, or stale | Phase 2 — Issue Prioritization | Route through the Design Iteration Agent to `skills/issue-prioritization-skill.md`, then validate the result. |
| Valid prioritized issues exist, but `outputs/phase-02/iteration-plan.md` is missing, invalid, or stale | Phase 2 — Improvement & Validation | Route through the Design Iteration Agent to `skills/improvement-validation-skill.md`, then validate the result. |
| Both valid Phase 2 artifacts exist, but G2 has no explicit Human decision | G2 — Human Iteration Review | Present `prioritized-issues.md`, then `iteration-plan.md`; stop for one overall Human decision. |
| G2 returns `REVISE` | Phase 2 revision | Follow G2 and Phase 2 dependency logic: rerun the earliest affected Phase 2 step and all downstream dependencies, then return the complete package to G2. |
| G2 returns `REJECT` | Workflow completion stopped | Do not claim completion. Follow Gate 2 recovery logic until the underlying evidence, scope, or artifact issue is resolved. |
| G2 explicitly returns `APPROVE` for the current Phase 2 package | V1 complete | Mark the V1 workflow `WORKFLOW_COMPLETE`. |

## Phase routing

### Phase 1 — Design Critique

- Runbook: `workflow/run-phase-01.md`
- Agent: `agents/design-critic-agent.md`
- Inputs: required and available project evidence from `projects/design_critique_iteration_orchestrator/input/`
- Outputs: `outputs/phase-01/context-findings.md`, then `outputs/phase-01/design-findings.md`, then `outputs/phase-01/critique-report.md`
- Gate: `gates/gate-01-critique-review.md`

Read the runbook, agent, three declared skills, and gate before dispatching work. Dispatch through the Phase 1 runner and Design Critic Agent; the orchestrator must not perform critique itself.

The declared sequence is:

```text
Context & Requirement Evaluation
        ↓
UX/UI Evaluation
        ↓
Critique Synthesis
        ↓
G1
```

When all Phase 1 artifacts are valid, route to G1. Do not enter Phase 2 until an explicit Human `APPROVE` applies to the current Phase 1 package.

### Phase 2 — Iteration Strategy

- Runbook: `workflow/run-phase-02.md`
- Agent: `agents/design-iteration-agent.md`
- Inputs: current G1-approved Phase 1 package
- Outputs: `outputs/phase-02/prioritized-issues.md`, then `outputs/phase-02/iteration-plan.md`
- Gate: `gates/gate-02-iteration-review.md`

Read the runbook, agent, two declared skills, and gate before dispatching work. Dispatch through the Phase 2 runner and Design Iteration Agent; the orchestrator must not prioritize issues or create recommendations itself.

The declared sequence is:

```text
Issue Prioritization
        ↓
Improvement & Validation
        ↓
G2
```

When both Phase 2 artifacts are valid, route to G2 and stop for Human review.

## Gate routing

### G1 — Human Critique Review

- Gate: `gates/gate-01-critique-review.md`
- Required review artifacts, in order: `outputs/phase-01/context-findings.md`, `outputs/phase-01/design-findings.md`, then `outputs/phase-01/critique-report.md`
- Decision record: `outputs/reviews/gate-01-critique-review.md`
- Human decision: `APPROVE`, `REVISE`, or `REJECT`

G1 is one overall decision for the complete Phase 1 package. Do not introduce per-`CR-` approval. `APPROVE` permits Phase 2 only when it applies to the current package. `REVISE` routes through G1 dependency logic. `REJECT` stops progression until the underlying issue is resolved. The Design Critic Agent may prepare or revise artifacts but cannot approve G1.

### G2 — Human Iteration Review

- Gate: `gates/gate-02-iteration-review.md`
- Required review artifacts, in order: `outputs/phase-02/prioritized-issues.md`, then `outputs/phase-02/iteration-plan.md`
- Decision record: `outputs/reviews/gate-02-iteration-review.md`
- Human decision: `APPROVE`, `REVISE`, or `REJECT`

G2 is one overall decision for the complete final Phase 2 package. Do not introduce per-`CR-`, per-priority, per-recommendation, or per-validation-task approval. `APPROVE` for the current package completes V1. `REVISE` routes through G2 dependency logic. `REJECT` stops workflow completion until the underlying issue is resolved. The Design Iteration Agent may prepare or revise artifacts but cannot approve G2.

## Operating rules

- Read the active phase runner, agent, declared skills, and gate before dispatching work.
- Launch work through the named phase runner and agent; do not create phase artifacts directly from the orchestrator.
- Inspect actual state before deciding what to run.
- Never infer Human approval from silence, artifact existence, automated checks, agent validation, or a generic request to continue.
- Preserve stable `CR-` IDs and evidence lineage, including context, requirements, constraints, counterevidence, uncertainty, dependencies, and validation needs.
- Severity is not priority. Recommendations remain hypotheses to explore and validate.
- On `REVISE`, rerun the earliest affected step and all downstream dependencies. If upstream work changes, dependent outputs and approvals may become stale.
- Do not patch downstream work to hide an upstream change, and do not invent missing evidence.
- Do not create Phase 3 or missing architecture components unless explicitly requested.

## User request routing

| User request | Orchestrator response |
|---|---|
| Start / run workflow | Inspect actual state and resume from the earliest incomplete, invalid, stale, or blocked point. Do not automatically restart from Phase 1. |
| Run Phase 1 | Verify required project inputs and route to `workflow/run-phase-01.md`. |
| Approve G1 | Treat as approval only when the Human explicitly gives `APPROVE`; record it according to the G1 contract, confirm package currency, then route to Phase 2. |
| Revise G1 | Collect actionable Human feedback and follow Gate 1 dependency logic. |
| Reject G1 | Stop Phase 2 progression and follow Gate 1 recovery logic. |
| Run Phase 2 | Verify an explicit current G1 approval and route to `workflow/run-phase-02.md`. |
| Approve G2 | Treat as approval only when the Human explicitly gives `APPROVE`; record it according to the G2 contract. If approval applies to the current Phase 2 package, report `WORKFLOW_COMPLETE`. |
| Revise G2 | Collect actionable Human feedback and follow Gate 2 dependency logic. |
| Reject G2 | Stop completion and follow Gate 2 recovery logic. |
| Status / what’s next | Report the current phase or gate, existing current artifacts, gate status, stale or missing dependencies, blockers or evidence limitations, and next required action. |

Staleness routing: a project-input change makes affected Phase 1 outputs stale, which makes G1 approval for the changed package stale; affected Phase 2 outputs and G2 approval then become stale. A Phase 1 output change requires G1 review of the changed package again and regeneration of dependent Phase 2 work. A material `prioritized-issues.md` change makes `iteration-plan.md` stale and requires complete-package G2 review again. An `iteration-plan.md` change makes previous G2 approval stale and requires complete-package G2 review again. Resume from the earliest affected point without rerunning unaffected valid work.

## Completion

Report:

- the current phase or pending gate;
- artifacts created or reviewed;
- the required Human decision, if any;
- blockers, stale dependencies, evidence limitations, or unresolved questions; and
- the next route.

Report `WORKFLOW_COMPLETE` only when the current Phase 1 package has explicit Human G1 `APPROVE`, Phase 2 was generated from that approved package, and the current Phase 2 package has explicit Human G2 `APPROVE`.

Workflow completion does not mean recommendations were implemented, the design was redesigned, validation succeeded, or all uncertainty was resolved. It means the Human-approved Design Critique → Iteration Strategy workflow has completed.
