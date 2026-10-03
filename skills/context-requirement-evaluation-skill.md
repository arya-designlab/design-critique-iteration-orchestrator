---
name: context-requirement-evaluation-skill
description: Inventory supplied design materials, including screenshots and walkthrough recordings, and establish a traceable context and requirement basis for later UX/UI evaluation. Use before critiquing a design; it does not identify design problems or recommend changes.
---

# Name & Description

**Context & Requirement Evaluation Skill**

Create a factual, traceable evaluation basis for an existing UI/UX design. Read the supplied screenshots, walkthrough recordings when available, and project materials; identify what the sources establish about the product, users, tasks, goals, constraints, and explicit requirements; and record uncertainty without filling gaps. The resulting artifact prepares the next skill to evaluate the design in context; it is not itself a UX/UI critique.

# Role

Act as a design-context analyst. Establish what is known, who or what established it, and what remains unknown before anyone evaluates the submitted interface. Preserve the distinction between requirements, stakeholder assertions, user evidence, design observations, assumptions, and missing information.

Do not decide whether a design is usable, accessible, consistent, compliant, attractive, or correct. Do not propose interface changes.

# Context

This skill is the first transformation in Phase 01 — Design Critique. Its output is the factual basis for `design-findings.md`, which may assess the submitted design only against the supplied context, requirements, evidence, and appropriately qualified evaluation frameworks.

The source set can contain:

- Required design screenshot(s), which establish only what is visible in the submitted state or states.
- Optional product walkthrough video(s) or screen recording(s), which may establish interactions, responsive behavior, transitions, system states, and flow sequence when they are directly demonstrated.
- A required design brief, requirements document, or project-context document.
- Optional stakeholder or user feedback.
- Optional usability-test findings or reports.
- Optional research findings.
- Optional product, business, or technical constraints.

Sources have different evidentiary weight. A screenshot can establish a visible label, control, screen state, or apparent flow boundary, but cannot prove user behavior, intent, accessibility conformance, or implementation behavior. A walkthrough video or screen recording can additionally establish only the interactions, responsive behavior, transitions, system states, semantic structure, or implementation details that it directly shows or explicitly explains. It does not establish unrecorded states, behavior outside the demonstrated path, or conformance beyond the shown evidence. A requirement can establish an expected product outcome or constraint, but does not by itself prove a user need. Feedback establishes what the named source reported, not necessarily representative user behavior. Research and usability findings retain the scope, date, sample, and limitations stated in their source.

When optional materials are absent, record that absence. Their absence does not prevent this skill from producing a context artifact when the required design and project-context inputs are usable; it limits what later evaluation can claim.

# Instructions

1. Inventory the supplied input set before interpreting it.
   - Inspect all accessible required and optional materials, including supported files in nested input folders.
   - Record each source path, source type, readability, relevant date/version when supplied, and intended use.
   - Identify duplicate, conflicting, inaccessible, unreadable, or ambiguous sources. Analyze one verified copy of a true duplicate; retain differing versions as distinct sources.
   - State which optional evidence types were supplied and which were not supplied.

2. Read screenshots and walkthrough recordings as submitted design evidence.
   - Record the available screens, states, annotations, device or viewport information, and any visible flow relationships only when shown or explicitly stated.
   - For each video or screen recording, record the demonstrated flow or flows, relevant time range, visible device or viewport context, and whether audio, captions, annotations, developer tools, or assistive-technology output provide additional direct evidence.
   - Use an unambiguous screen, frame, page, filename, or video time-range locator for every later reference to design evidence.
   - A recording may establish interactions, transitions, responsive changes, system states, semantic structure, or implementation details only when directly demonstrated. Record what is shown, not what is presumed to occur elsewhere in the product.
   - Do not infer hidden interactions, responsive behavior, system states, semantic structure, or implementation details from a static image. Do not generalize a recorded path to unshown states or flows.

3. Extract the project and product context.
   - Capture only source-supported statements about the product or service, intended audience, user roles, tasks, goals, journey stage, success criteria, domain, and known operating context.
   - Preserve the source's scope. For example, distinguish a proposed target user in a brief from a participant observed in a usability study.
   - If a source gives only a broad objective, record that objective without expanding it into unstated user needs or flows.

4. Extract explicit requirements and constraints.
   - Record requirements that are stated in the supplied materials, including functional, content, business, technical, legal, brand, platform, or project constraints when provided.
   - Give each substantive requirement a stable ID such as `REQ-01` and attach a precise source locator.
   - Distinguish explicit requirements from examples, aspirational language, proposed features, stakeholder preferences, and open questions.
   - Do not convert a common UX convention, an external standard, or an unstated expectation into a project requirement.

5. Classify supplied feedback and research evidence without synthesizing beyond it.
   - Record attributable stakeholder feedback, user feedback, usability-test observations, research findings, and constraints separately.
   - Preserve the original scope, participant or source context when available, date, method, and limitations.
   - If sources disagree, record the disagreement and what information would resolve it. Do not choose one account silently.

6. Identify assumptions, ambiguities, and missing information.
   - List only assumptions explicitly stated in the sources or necessary to interpret an ambiguous source; label them as assumptions and name their basis.
   - Record missing information that would materially limit a later critique, such as unknown primary task, unavailable screen state, unclear requirement, absent user evidence, or unknown technical constraint.
   - Do not create assumptions merely to make the context appear complete.

7. Produce a requirement and evidence map for the next skill.
   - For each requirement or context claim that a later UX/UI evaluation may use, provide its ID, statement, classification, source locator, and applicability to the submitted design.
   - Mark applicability as `Visible in submitted design`, `Not visible in submitted design`, `Cannot determine from supplied materials`, or `Not applicable to this design scope`.
   - Applicability records evidence coverage; it is not a pass/fail evaluation and must not identify a design problem.

8. Review the artifact before completion.
   - Confirm that every substantive claim can be traced to a supplied source.
   - Confirm that facts, explicit requirements, feedback, research evidence, assumptions, ambiguity, and missing information remain separate.
   - Confirm that no UX/UI critique, severity rating, heuristic judgment, accessibility conclusion, or design recommendation has been added.
   - Write only the final context artifact to the declared output path.

# Input / Output Contract

## Input

Read the supplied materials from `projects/design_critique_iteration_orchestrator/input/` and its nested folders:

```text
Required
- Design screenshot(s) or other supplied visual design artifacts
- Design brief, requirements, or project-context material

Optional
- Product walkthrough video(s) or screen recording(s)
- Stakeholder or user feedback
- Usability-test findings or reports
- Research findings
- Product, business, technical, legal, brand, or platform constraints
```

Supported readable sources may include image files, common video or screen-recording formats (such as `.mp4`, `.mov`, and `.webm`), plain text (`.txt`), Markdown (`.md`), PDF (`.pdf`), Word (`.docx` and readable `.doc`), and other provided formats that can be reliably inspected. Do not use outside knowledge to fill gaps.

If either required input category is missing, inaccessible, or unusable, do not establish an evaluation basis. Record the exact missing or affected paths and request the needed material.

## Output

Write one Markdown file to:

```text
outputs/phase-01/context-findings.md
```

Use this structure:

```markdown
# Context Findings

## Source Inventory

| Source | Type | Readability | Date/version | Classification | Use in evaluation basis |
|--------|------|-------------|--------------|----------------|-------------------------|
| [path] | [type] | Readable / limited / unavailable | [if supplied] | Screenshot / walkthrough video / screen recording / brief / requirement / feedback / research / constraint | [what it can establish] |

## Submitted Design Scope

- Screens or states available: [screen/frame/file locators]
- Directly visible scope: [what the screenshots visibly show]
- Demonstrated recording scope: [video/time-range locators and the interactions, responsive behavior, transitions, system states, semantic structure, or implementation details directly shown]
- Scope not established by supplied design evidence: [unshown states, interactions, responsive behavior, semantic structure, implementation behavior, or other unknowns]

## Product and Design Context

- **CTX-01 · [Fact / stakeholder assertion / research finding]:** [Scoped statement] — `[source path, heading/page/frame]`

## Users, Tasks, and Goals

### Users or roles
- **USR-01 · [classification]:** [Scoped statement] — `[source locator]`

### Tasks and journey context
- **TASK-01 · [classification]:** [Scoped statement] — `[source locator]`

### Goals or success criteria
- **GOAL-01 · [classification]:** [Scoped statement] — `[source locator]`

Write `Not established in supplied sources` for any section without support. Do not add an ID to an unsupported statement.

## Explicit Requirements and Constraints

| ID | Statement | Type | Source and locator | Applicability to submitted design |
|----|-----------|------|--------------------|-----------------------------------|
| REQ-01 | [explicit requirement] | Functional / content / business / technical / legal / brand / platform | `[source locator]` | Visible in submitted design / Not visible in submitted design / Cannot determine from supplied materials / Not applicable to this design scope |

## Supplied Feedback and Research Evidence

| ID | Evidence type | Scoped finding or report | Source and locator | Scope and limitation |
|----|---------------|--------------------------|--------------------|----------------------|
| EVD-01 | User feedback / usability finding / research finding / stakeholder feedback | [what the source actually reports] | `[source locator]` | [participant, method, date, ambiguity, or limitation if supplied] |

State `No [evidence type] supplied` for each optional category that is absent.

## Assumptions, Ambiguities, and Missing Information

### Assumptions stated or required for interpretation
- **ASM-01:** [Assumption and its source basis]. Validation or clarification needed: [specific need].

### Ambiguities or contradictions
- **AMB-01:** [Unclear or conflicting information, affected source(s), and what would resolve it].

### Missing information that limits later evaluation
- [Missing item and the critique claim it would limit].

## Evaluation Basis Handoff

- Requirements and context claims that may be used by the UX/UI Evaluation skill: [IDs].
- Evidence limitations the next skill must preserve: [limitations].
- Evaluation boundaries: The next skill may assess only the submitted design scope and must not treat absent evidence, invisible behavior, assumptions, or common conventions as confirmed project facts.
```

If no usable optional evidence exists, retain the relevant sections and state the limitation rather than removing them. If no explicit requirements are supplied, state `No explicit requirements established in supplied sources`; do not generate requirements from the screenshot or common design practice.

# Rules & Guardrails

- Use only supplied materials. Do not use outside knowledge, common conventions, design trends, heuristic libraries, accessibility standards, competitor practices, or assumed product patterns as evidence.
- Do not perform UX/UI critique. Do not identify usability problems, visual-hierarchy problems, navigation failures, accessibility failures, inconsistencies, severity, or recommended changes.
- Do not invent users, tasks, needs, motivations, goals, requirements, constraints, feedback, research findings, implementation details, or business priorities.
- Keep a screenshot observation, recording observation, and inference about behavior or impact separate. A static screenshot cannot establish interaction behavior, keyboard behavior, screen-reader behavior, responsive behavior, error handling, or user comprehension unless supplied evidence establishes it. A recording can establish only the behavior directly demonstrated at its cited time range.
- Preserve source provenance with the most precise available locator: file and heading for text/Markdown, page for PDF, heading or page for Word, filename/frame/screen description for screenshots, and filename plus time range for video or screen recordings.
- Treat stakeholder claims, product briefs, requirements, feedback, research, and test findings according to what they actually establish. Do not upgrade a claim into validated user evidence because it appears in a formal document.
- Preserve material conflicts. Do not average, resolve, or conceal them.
- Mark uncertain claims as assumptions or ambiguities. Mark absent information as missing; absence is not evidence that a requirement, user need, or constraint does not exist.
- Do not silently exclude supplied optional sources. Inventory and classify them, even when they do not materially affect the current design scope.
- Do not modify source inputs, create downstream artifacts, or write any file other than `outputs/phase-01/context-findings.md` when this skill is executed.

# References & Examples

## References

Use the supplied project materials as the only references for this skill. Future reference or knowledge layers—such as accessibility guidance, usability heuristics, visual-principle references, interaction-pattern libraries, analytics, competitor evidence, or richer testing evidence—may be added to a project later. Unless they are supplied and explicitly in scope, they must not be used or implied by this skill.

## Example

Illustrative supplied materials:

- `projects/starter/input/checkout-screen.png` shows a checkout screen with an order summary and a primary button.
- `projects/starter/input/checkout-walkthrough.mov`, from `00:12–00:18`, shows the order total update after a delivery method is selected.
- `projects/starter/input/brief.md`, under **Primary task**, says that returning customers should complete checkout quickly on mobile.
- `projects/starter/input/usability-note.md`, under **Session 2**, reports that one participant looked for delivery cost before confirming an order.
- No technical constraints or accessibility testing are supplied.

An acceptable excerpt from `outputs/phase-01/context-findings.md` is:

```markdown
## Submitted Design Scope

- Screens or states available: `projects/starter/input/checkout-screen.png`, single submitted checkout screen.
- Directly visible scope: An order summary and a primary checkout action are visible.
- Demonstrated recording scope: `projects/starter/input/checkout-walkthrough.mov, 00:12–00:18` shows the order total update after a delivery method is selected.
- Scope not established by supplied design evidence: Error handling, payment selection, keyboard behavior, screen-reader behavior, other responsive breakpoints, and post-confirmation state.

## Users, Tasks, and Goals

### Tasks and journey context
- **TASK-01 · Fact:** Returning customers are expected to complete checkout on mobile — `[projects/starter/input/brief.md, Primary task]`.

### Goals or success criteria
- **GOAL-01 · Stakeholder assertion:** Checkout should be completed quickly — `[projects/starter/input/brief.md, Primary task]`.

## Supplied Feedback and Research Evidence

| ID | Evidence type | Scoped finding or report | Source and locator | Scope and limitation |
|----|---------------|--------------------------|--------------------|----------------------|
| EVD-01 | Usability finding | One participant looked for delivery cost before confirming an order. | `[projects/starter/input/usability-note.md, Session 2]` | One reported session; the note does not establish prevalence or whether the submitted screen caused difficulty. |

## Assumptions, Ambiguities, and Missing Information

### Missing information that limits later evaluation
- No supplied accessibility test, semantic specification, or interaction specification. A later skill cannot conclude accessibility conformance or failure from this screenshot alone.
```

This example establishes an evaluation basis. It does not claim that the submitted checkout design hides delivery cost, creates confusion, behaves the same way in unrecorded states, or should be redesigned.
