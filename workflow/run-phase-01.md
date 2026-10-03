---
phase: 1
name: Design Critique
entry_from:
  - A design-critique request with supplied project inputs under `projects/design_critique_iteration_orchestrator/input/`
trigger: The user requests a context-aware UX/UI critique and the required design evidence and project-context inputs are ready
gate: gates/gate-01-critique-review.md
team:
  lead: agents/design-critic-agent.md
agents:
  - agents/design-critic-agent.md
skills_invoked:
  - skills/context-requirement-evaluation-skill.md
  - skills/ux-ui-evaluation-skill.md
  - skills/critique-synthesis-skill.md
inputs:
  - projects/design_critique_iteration_orchestrator/input/
outputs:
  - outputs/phase-01/context-findings.md
  - outputs/phase-01/design-findings.md
  - outputs/phase-01/critique-report.md
exports:
  - outputs/phase-01/context-findings.md
  - outputs/phase-01/design-findings.md
  - outputs/phase-01/critique-report.md
  - outputs/reviews/gate-01-critique-review.md when an explicit Human decision is recorded
exit_to: workflow/run-phase-02.md
---

# P1 — Design Critique

Phase 01 turns supplied design evidence and project context into a traceable, context-aware UX/UI critique package ready for explicit Human review. It preserves source traceability, context and requirements, observable design evidence, supporting and contradictory evidence, uncertainty, limitations, validation needs, and justified severity.

This phase does not create redesign solutions, iteration priorities, Phase 02 recommendations, or a Human approval decision.

## Agent Team

| Role | Agent | Outputs produced |
|---|---|---|
| Design Critique lead | `agents/design-critic-agent.md` | Validated `outputs/phase-01/context-findings.md`; validated `outputs/phase-01/design-findings.md`; validated `outputs/phase-01/critique-report.md`; Gate 01 review package |
| Human reviewer | Gate 01 — Human Critique Review | One overall `APPROVE`, `REVISE`, or `REJECT` decision for the Phase 01 package |

The Design Critic Agent coordinates the skills and validates their readiness. The skills perform the substantive transformations. The Human reviewer alone owns Gate 01 approval, revision, or rejection.

## Execution Sequence

| Step | Who | Skills | Input | Output | Gate |
|---|---|---|---|---|---|
| 1. Read operating definitions | `agents/design-critic-agent.md` | — | Agent definition; all three Phase 01 skills; `gates/gate-01-critique-review.md`; `references/design-evaluation-framework.md` | Loaded execution, validation, evidence, gate, and recovery rules | Definitions must be readable before work begins |
| 2. Inspect and inventory project inputs | `agents/design-critic-agent.md` | — | `projects/design_critique_iteration_orchestrator/input/` and nested supplied files | Required-input readiness assessment; optional-input inventory; readability and limitation status | Usable design screenshot(s) and usable brief/requirements/context are required |
| 3. Establish context and requirements | `agents/design-critic-agent.md` | `skills/context-requirement-evaluation-skill.md` | Inventoried project inputs | `outputs/phase-01/context-findings.md` | Context artifact complete |
| 4. Validate context artifact | `agents/design-critic-agent.md` | `skills/context-requirement-evaluation-skill.md` | Context artifact and supplied inputs | Current, traceable `outputs/phase-01/context-findings.md` | Must pass before Step 5 |
| 5. Evaluate UX/UI design | `agents/design-critic-agent.md` | `skills/ux-ui-evaluation-skill.md` | Submitted design evidence; validated context artifact; `references/design-evaluation-framework.md`; relevant supplied evidence | `outputs/phase-01/design-findings.md` | Design findings complete |
| 6. Validate design findings | `agents/design-critic-agent.md` | `skills/ux-ui-evaluation-skill.md` | Design findings, validated context artifact, submitted design evidence, and reference framework | Current, traceable `outputs/phase-01/design-findings.md` | Must pass before Step 7 |
| 7. Synthesize critique report | `agents/design-critic-agent.md` | `skills/critique-synthesis-skill.md` | Validated context artifact and design findings | `outputs/phase-01/critique-report.md` | Critique report complete |
| 8. Validate critique report | `agents/design-critic-agent.md` | `skills/critique-synthesis-skill.md` | Critique report, context artifact, and design findings | Current, reviewable `outputs/phase-01/critique-report.md` | Must pass before Gate 01 |
| 9. Present critique package | `agents/design-critic-agent.md` | — | The three validated Phase 01 artifacts | Ordered Gate 01 review package | Gate 01 opens |
| 10. Review and decide | Human reviewer | — | Phase 01 package and source evidence when needed | One overall `APPROVE`, `REVISE`, or `REJECT` decision | Only explicit `APPROVE` permits Phase 02 |

The order is mandatory. UX/UI Evaluation cannot begin until the context artifact is current and usable. Critique Synthesis cannot begin until design findings are current and usable. Gate 01 cannot open until all three artifacts pass their validation checks.

## Phase Inputs and Read Rules

### Required inputs

Read supplied materials under `projects/design_critique_iteration_orchestrator/input/`, including nested folders. Phase 01 requires:

- usable design screenshot(s) or equivalent supplied visual design evidence; and
- usable design brief, requirements, or project-context material.

### Optional inputs

When supplied, inventory and use within their source scope:

- walkthrough video(s) or screen recording(s);
- stakeholder or user feedback;
- usability-test findings or reports;
- research findings; and
- known product, business, technical, legal, brand, or platform constraints.

The absence of optional evidence does not automatically block Phase 01 when the required inputs are usable. It must be recorded as a limitation rather than silently ignored.

### Evidence and source rules

- Follow the source inventory, provenance, scope, readability, duplicate, ambiguity, and contradiction rules in `skills/context-requirement-evaluation-skill.md` and `agents/design-critic-agent.md`.
- Screenshots establish only what is visible in their supplied state. Record precise screen/frame/file locators; do not infer hidden interactions, responsive behavior, semantics, implementation details, or user behavior from a static image.
- Walkthrough recordings can establish only interactions, responsive behavior, states, semantic structure, implementation details, or assistive-technology output directly demonstrated at their cited time range. Do not generalize a recorded path to unshown states or flows.
- Treat project briefs, requirements, stakeholder claims, feedback, research, and usability findings according to what they actually establish. Preserve source scope and limitations; do not convert an assertion or plan into validated user behavior.
- Use `references/design-evaluation-framework.md` only through the UX/UI Evaluation skill's controlled, context-aware application. Do not add outside principles, trends, conventions, competitor examples, thresholds, or best practices.
- Preserve facts, assumptions, ambiguities, contradictions, counterevidence, missing information, and validation needs. Do not use outside knowledge to fill project-context gaps.

## Part A — Context & Requirement Evaluation

**Agent:** `agents/design-critic-agent.md`  
**Skill:** `skills/context-requirement-evaluation-skill.md`  
**Input:** Supplied materials under `projects/design_critique_iteration_orchestrator/input/`  
**Output:** `outputs/phase-01/context-findings.md`

### Step A1 — Readiness and input inventory

Confirm that the required design evidence and brief/requirements/project-context materials are accessible and usable. Inventory every accessible required and optional source, including its type, date/version when supplied, readability, duplication status, and scope. Record unreadable, inaccessible, corrupt, ambiguous, or conflicting material.

**Block condition:** If either required input category is missing or unusable, stop substantive work, list the exact affected paths, and request usable material. Do not begin UX/UI evaluation or substitute assumptions.

### Step A2 — Establish the evaluation basis

Run the Context & Requirement Evaluation skill. It must create the factual basis required by later work: submitted-design scope, product/design context, source-supported users/tasks/goals, explicit requirements and constraints, supplied evidence status, assumptions, ambiguities, missing information, and evaluation boundaries.

The skill must not perform UX/UI critique, rate severity, conclude accessibility conformance, or recommend design changes.

### Step A3 — Context artifact validation

Before Part B, confirm:

- [ ] `outputs/phase-01/context-findings.md` exists and is current for the supplied input set.
- [ ] A source inventory identifies required and optional evidence, readability, scope, and limitations.
- [ ] Design screenshots and recordings have precise locators and their observable scope is not overstated.
- [ ] Context, users, tasks, goals, requirements, constraints, and evidence are traceable where supplied.
- [ ] Facts, assertions, assumptions, ambiguities, contradictions, and missing information remain distinct.
- [ ] No UX/UI findings, solutions, severity ratings, or unsupported requirements have been introduced.

If any check fails, correct `outputs/phase-01/context-findings.md` through the declared skill before starting Part B.

## Part B — UX/UI Evaluation

**Agent:** `agents/design-critic-agent.md`  
**Skill:** `skills/ux-ui-evaluation-skill.md`  
**Inputs:** Submitted design evidence; `outputs/phase-01/context-findings.md`; `references/design-evaluation-framework.md`; relevant supplied evidence identified by the context artifact  
**Output:** `outputs/phase-01/design-findings.md`

### Step B1 — Context handoff check

Read the validated context artifact in full and confirm it identifies usable design evidence, relevant project context, and evidence limitations. Read the V1 design-evaluation framework in full. Select only evaluation areas relevant to the supplied design and documented context.

**Block condition:** If `outputs/phase-01/context-findings.md` is missing, invalid, stale, or insufficient for the claimed scope, return to Part A. If `references/design-evaluation-framework.md` is missing, stop and report the missing path. Do not evaluate from memory or introduce another framework.

### Step B2 — Create evidence-backed design findings

Run UX/UI Evaluation using the required evidence chain:

```text
observable design evidence + relevant context + applicable principle/guidance + plausible user impact
```

Each substantive finding must have a stable `CR-` ID, direct design-evidence locator, relevant context/evidence IDs, applicable framework trace, qualified potential impact, supporting or contradictory evidence, and an uncertainty or validation need. Record unevaluated areas and visible requirement alignment rather than manufacturing negative findings.

### Step B3 — Design-finding validation

Before Part C, confirm:

- [ ] `outputs/phase-01/design-findings.md` exists and is current for the accepted context artifact and submitted design scope.
- [ ] Every substantive `CR-` finding has observable evidence, relevant context, applicable principle/guidance, and qualified plausible impact.
- [ ] Every design observation has a precise screenshot/frame or recording time-range locator.
- [ ] Supporting evidence, counterevidence, requirements, constraints, limitations, and validation needs are preserved.
- [ ] Findings are not based only on preference, trends, an unspecified convention, or unsupported UX/UI knowledge.
- [ ] Observable accessibility concerns remain distinct from WCAG compliance or failure unless sufficient evidence supports the applicable conclusion.
- [ ] No solution recommendation, iteration priority, or critique-report synthesis has been added.

If any check fails, correct `outputs/phase-01/design-findings.md` through the declared skill before starting Part C.

## Part C — Critique Synthesis

**Agent:** `agents/design-critic-agent.md`  
**Skill:** `skills/critique-synthesis-skill.md`  
**Inputs:** `outputs/phase-01/context-findings.md`; `outputs/phase-01/design-findings.md`  
**Output:** `outputs/phase-01/critique-report.md`

### Step C1 — Findings handoff check

Read the validated context artifact and design findings in full. Confirm that the current `CR-` set has traceable evidence, context, framework reference, plausible impact, counterevidence where supplied, and validation needs.

**Block condition:** If design findings are missing, invalid, stale, or have broken `CR-` traceability, return to Part B after checking the context artifact. Do not synthesize from screenshots, the reference framework, or outside knowledge.

### Step C2 — Consolidate for Human review

Run Critique Synthesis. It may consolidate genuine duplicates or closely related findings, but it must preserve every source `CR-` ID, design evidence, context/evidence trace, counterevidence, limitations, and validation need. It may assign `High`, `Medium`, `Low`, or `Tentative` severity only when justified by the potential effect on the documented user/task/outcome.

Severity is not iteration priority, implementation effort, business value, or a Human decision. The report must not introduce a new critique concern, redesign recommendation, or Phase 02 guidance.

### Step C3 — Critique-report validation

Before opening Gate 01, confirm:

- [ ] `outputs/phase-01/critique-report.md` exists and is current for the accepted `CR-` findings.
- [ ] Every source `CR-` ID is represented and remains traceable after consolidation or duplicate treatment.
- [ ] Each critique item preserves relevant design evidence, context/requirement/evidence IDs, principle/guidance trace, plausible impact, counterevidence, uncertainty, and validation need.
- [ ] Severity is grounded in potential documented user/task/outcome effect or marked `Tentative` when evidence is insufficient.
- [ ] No new critique finding, outside principle, solution, iteration priority, approval decision, or redesign direction has been introduced.

If any check fails, correct `outputs/phase-01/critique-report.md` through the declared skill before opening Gate 01.

## Gate 01 — Human Critique Review

Follow [Gate G1 — Human Critique Review](../gates/gate-01-critique-review.md) at `gates/gate-01-critique-review.md`. It is the mandatory Human gate between this phase and Phase 02 — Iteration Strategy.

The Human reviewer reviews the validated artifacts in order:

1. `outputs/phase-01/context-findings.md`
2. `outputs/phase-01/design-findings.md`
3. `outputs/phase-01/critique-report.md`

The Human reviewer gives one overall decision for the complete Phase 01 package: `APPROVE`, `REVISE`, or `REJECT`. Do not require per-finding approval decisions.

The Design Critic Agent may present, explain, validate, and revise the package but cannot approve G1. Silence, artifact existence, automated validation, agent validation, or a generic request to continue is not approval. Only an explicit Human `APPROVE` recorded in `outputs/reviews/gate-01-critique-review.md` clears G1. Do not create or pre-fill that future decision record during Phase 01 definition or execution unless explicitly authorized to record a Human decision.

For `REVISE`, collect actionable feedback and route to the earliest affected step according to the dependency logic below. For `REJECT`, stop Phase 01 until the underlying evidence or scope issue is resolved and the package is regenerated for a new Human review.

## Exceptions

| Failure condition | Recovery action |
|---|---|
| Required design evidence is missing, inaccessible, corrupt, or unusable | Stop Phase 01, list exact affected paths, request usable screenshot(s) or equivalent supplied visual evidence, and do not begin Part A substantive work. |
| Required brief, requirements, or project-context material is missing, inaccessible, corrupt, or unusable | Stop Phase 01, list exact affected paths, request usable project context, and do not infer requirements or user needs. |
| Optional recording, feedback, research, usability finding, or constraint is absent | Record the absence and resulting limitation. Continue only if required inputs independently support the scoped work. |
| Supplied material is unreadable, ambiguous, conflicting, or a duplicate | Record the material and limitation. Analyze one verified copy of a true duplicate; retain differing versions or material conflicts. Continue only when remaining evidence supports the scoped artifact; otherwise request usable clarification or source material. |
| `outputs/phase-01/context-findings.md` is stale, incomplete, invalid, or contains critique work | Return to Part A. Rebuild or correct the context artifact through Context & Requirement Evaluation, then rerun Parts B and C. |
| `outputs/phase-01/design-findings.md` is stale, incomplete, invalid, or contains broken/unsupported `CR-` traceability | Return to Part B after validating the current context artifact. Correct the findings through UX/UI Evaluation, then rerun Part C. |
| `outputs/phase-01/critique-report.md` is stale, loses source `CR-` IDs/evidence, adds a concern, or has unsupported severity | Return to Part C. Regenerate the report only from the valid context and design findings. |
| An unsupported requirement, context claim, design finding, principle, severity, or solution appears in a later artifact | Return to the earliest artifact that introduced it, remove or narrow it through the appropriate declared skill, and rerun every dependent artifact. Do not patch around it in a later step. |
| Evidence is insufficient for a confident severity assessment | Preserve the finding and validation need; assign `Tentative` severity rather than inflating, omitting, or converting uncertainty into priority. |
| Gate 01 has no explicit Human `APPROVE` | Present the validated package and stop. Do not infer approval or begin Phase 02. |

## Phase Handoff

Only after the Human reviewer explicitly returns `APPROVE` at Gate 01 may Phase 01 hand off to Phase 02 — Iteration Strategy through the future `workflow/run-phase-02.md` runbook.

The downstream phase receives and must preserve:

- `outputs/phase-01/context-findings.md`;
- `outputs/phase-01/design-findings.md`;
- `outputs/phase-01/critique-report.md`; and
- `outputs/reviews/gate-01-critique-review.md` when the Human decision has been recorded.

Phase 02 must retain relevant source evidence, context, requirements, constraints, stable `CR-` IDs, supporting and contradictory evidence, uncertainty, limitations, validation needs, and severity rationale. It must not treat an approved critique package as permission to invent a new critique issue or disregard its evidence boundaries.

This runbook does not begin or define Phase 02 work.
