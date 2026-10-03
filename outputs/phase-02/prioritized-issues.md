# Prioritized Issues

## Prioritization Basis

- Gate 01 status: `APPROVE` — `[outputs/reviews/gate-01-critique-review.md, Decision; Reviewed package; Approved source CR-IDs; Reviewed artifact versions]`
- Approved artifacts used: `outputs/phase-01/context-findings.md`; `outputs/phase-01/critique-report.md`; `outputs/phase-01/design-findings.md` for existing evidence and limitation detail.
- Approved source CR-IDs: CR-01, CR-03, CR-05.
- Known prioritization constraints: The approved evidence establishes no primary homepage task, intended editorial hierarchy, relative module importance, business priority, user prevalence, implementation constraint, or cross-issue dependency that would support a relative iteration order. — `[outputs/phase-01/context-findings.md, Missing information that limits later evaluation; outputs/phase-01/critique-report.md, Critique Summary]`
- Important limitations and missing factors: Implementation effort, feasibility, engineering complexity, development time, business value, revenue or conversion impact, deadlines, stakeholder priority, user prevalence, device/browser distribution, and measured task impact are `Not established in approved evidence`.
- Priority boundary: Priority reflects supported iteration order only. It does not prove a solution, effort estimate, business case, or implementation commitment.

## Priority Summary

| Priority | CR-IDs | Why this group is here |
|----------|--------|------------------------|
| P1 — Address first | None | The approved evidence does not establish a defensible reason to place any issue first. |
| P2 — Address next | None | No relative order is established after a P1 issue. |
| P3 — Address later | None | The approved evidence does not establish that any issue can responsibly wait behind another. |
| Needs validation before prioritization | CR-01, CR-03, CR-05 | All three findings are Tentative, and the evidence needed to compare their actual task relevance, impact, dependencies, and constraints is missing. Each requires issue-specific validation before relative order can be established. |

## Prioritized Issues

### CR-01: Similar visual weight across the opening news area may make the most relevant starting point harder to identify

**Phase 01 severity:** Tentative

**Priority:** Needs validation before prioritization

**Why this priority:**
- The approved evidence establishes a possible discovery concern in the opening news area, but it does not establish the intended editorial priority, visitors’ arrival goals, scan behaviour, task effect, or prevalence. Without that information, its relative iteration order cannot be compared responsibly with CR-03 or CR-05. — `[outputs/phase-01/critique-report.md, CR-01, Severity rationale; Uncertainty and validation need]`

**User / task / requirement impact:**
- Visitors may need to discover varied news, events, resources, publications, NGO information, and participation opportunities, and the website needs to support information discovery. The approved finding states that some visitors may need more scanning to identify a relevant starting point. — `[outputs/phase-01/context-findings.md, TASK-01; GOAL-01; outputs/phase-01/critique-report.md, CR-01, Why this may matter]`

**Dependencies / sequencing:**
- Clarification of intended discovery and editorial priorities is required before relative iteration order can be established. No dependency on CR-03 or CR-05 is established in approved evidence.

**Relevant constraints:**
- Evaluation is limited to one static desktop homepage capture. Hidden interactions, responsive behaviour, user comprehension, and actual task performance are not established. — `[outputs/phase-01/context-findings.md, REQ-01 through REQ-04; Missing information that limits later evaluation]`

**Evidence / context trace:**
- CR-01; CTX-05; CTX-06; TASK-01; GOAL-01; REQ-01 through REQ-04. — `[outputs/phase-01/critique-report.md, CR-01; outputs/phase-01/design-findings.md, CR-01]`

**Counterevidence / uncertainty:**
- Images, category labels, dates, title differences, and “All the news” provide discovery cues and a broader route. The evidence does not show that visitors actually struggle or which items should receive editorial priority. — `[outputs/phase-01/critique-report.md, CR-01, Supporting or contradictory evidence]`

**Validation need:**
- Clarify intended discovery priorities, then check whether representative visitors can locate a current item relevant to a stated goal and whether the opening area creates meaningful difficulty compared with the other approved concerns.

### CR-03: Some newsletter and footer text has low apparent distinction from its background at the captured scale

**Phase 01 severity:** Tentative

**Priority:** Needs validation before prioritization

**Why this priority:**
- The approved evidence supports a visible validation concern, but it does not establish rendered contrast values, viewing conditions, affected-user prevalence, task criticality, or accessibility conformance. Its actual effect and relative urgency therefore cannot be compared responsibly with CR-01 or CR-05. — `[outputs/phase-01/critique-report.md, CR-03, Severity rationale; Uncertainty and validation need]`

**User / task / requirement impact:**
- If the rendered treatments are difficult to distinguish in use, some visitors may overlook or have difficulty reading consent, external-link, or policy information. Readability and observable accessibility are included in the approved evaluation goal. — `[outputs/phase-01/context-findings.md, GOAL-02; outputs/phase-01/critique-report.md, CR-03, Why this may matter]`

**Dependencies / sequencing:**
- Rendered contrast and text-behaviour checks are required before relative iteration order can be established. No dependency on CR-01 or CR-05 is established in approved evidence.

**Relevant constraints:**
- No accessibility audit, rendered contrast values, zoom/reflow evidence, semantic evidence, assistive-technology evidence, or device/browser distribution is supplied. — `[outputs/phase-01/context-findings.md, Missing information that limits later evaluation; outputs/phase-01/critique-report.md, CR-03]`

**Evidence / context trace:**
- CR-03; CTX-05; GOAL-01; GOAL-02; REQ-01 through REQ-04. — `[outputs/phase-01/critique-report.md, CR-03; outputs/phase-01/design-findings.md, CR-03]`

**Counterevidence / uncertainty:**
- The newsletter heading, supporting line, email field, and signup button are prominent, and the external-link items appear lighter than their heading. The static capture cannot establish actual contrast values or accessibility conformance. — `[outputs/phase-01/critique-report.md, CR-03, Supporting or contradictory evidence]`

**Validation need:**
- Measure rendered text/background contrast in relevant states and inspect text rendering, zoom/reflow, semantics, and assistive-technology behaviour. Use those results and the information’s task relevance to determine relative iteration order; do not infer WCAG compliance or failure from the capture.

### CR-05: The relationship between several major homepage modules may not be immediately clear from the captured page sequence

**Phase 01 severity:** Tentative

**Priority:** Needs validation before prioritization

**Why this priority:**
- The approved evidence establishes a possible page-level orientation concern, but it does not establish the intended homepage hierarchy, primary route, module importance, visitor comprehension, scroll behaviour, task effect, or prevalence. Its broad visible scope alone does not justify placing it ahead of the other findings. — `[outputs/phase-01/critique-report.md, CR-05, Severity rationale; Uncertainty and validation need]`

**User / task / requirement impact:**
- The website needs to support discovery and access to varied Forum content. Some visitors may need additional effort to decide which major section to attend to or may overlook a relevant route while scanning the long page. — `[outputs/phase-01/context-findings.md, CTX-05; CTX-06; GOAL-01; outputs/phase-01/critique-report.md, CR-05, Why this may matter]`

**Dependencies / sequencing:**
- Clarification of the intended homepage hierarchy and relative role of major modules is required before relative iteration order can be established. CR-05 is related to CR-01, but the approved package explicitly retains them as distinct findings and establishes no order between them. — `[outputs/phase-01/critique-report.md, Duplicate and Relationship Notes]`

**Relevant constraints:**
- Evaluation is limited to a static desktop capture. Scroll behaviour, destination content, analytics, user comprehension, and task performance are not established. — `[outputs/phase-01/context-findings.md, REQ-01 through REQ-04; outputs/phase-01/critique-report.md, CR-05]`

**Evidence / context trace:**
- CR-05; CTX-05; CTX-06; TASK-01; GOAL-01; REQ-01 through REQ-04. — `[outputs/phase-01/critique-report.md, CR-05; outputs/phase-01/design-findings.md, CR-05]`

**Counterevidence / uncertainty:**
- Individual modules have clear titles, distinct imagery, spatial separation, and usually visible action labels, which support local comprehension. The evidence does not establish that visitors experience the overall sequence as unclear. — `[outputs/phase-01/critique-report.md, CR-05, Supporting or contradictory evidence]`

**Validation need:**
- Clarify the intended homepage hierarchy, then check whether representative visitors can describe the main content areas and locate a relevant route after scanning the page. Use the result to determine whether and where CR-05 belongs in the iteration order.

## Dependency & Sequencing Notes

| Related CR-IDs | Relationship | Evidence / constraint trace | Effect on iteration order |
|----------------|--------------|-----------------------------|---------------------------|
| CR-01, CR-05 | Related but distinct hierarchy/discovery concerns at different scopes | `[outputs/phase-01/critique-report.md, Duplicate and Relationship Notes]` | No relative order is established. Clarifying intended editorial and homepage hierarchy may inform both issues, but the approved evidence does not establish that either must be addressed first. |
| CR-03 | Separate readability and observable-accessibility validation concern | `[outputs/phase-01/critique-report.md, CR-03]` | Can be validated independently, but independent validation does not by itself establish earlier or later iteration priority. |

## Unresolved Prioritization Questions

- Which homepage audiences and discovery tasks are primary?
- What is the intended editorial priority within the opening news area and across the major homepage modules?
- Do representative visitors experience the possible scanning or orientation effects described in CR-01 and CR-05, and with what task consequence?
- What are the rendered contrast values and actual text behaviours relevant to CR-03, and how important are those text elements to documented tasks?
- Are there business, stakeholder, accessibility, technical, implementation, timing, or sequencing constraints that materially affect relative order? These are `Not established in approved evidence`.

## Handoff to Improvement & Validation

- Issues available for improvement-direction and validation planning: CR-01, CR-03, and CR-05, each classified `Needs validation before prioritization`.
- None is ready for a design improvement recommendation under the current evidence. The next skill should state why a direction would be premature and define the evidence needed before each issue can be prioritized and acted on.
- Preserve all Tentative severity rationales; the static-capture boundary; local hierarchy and discovery counterevidence; absent user/task-performance evidence; absent accessibility measurements; unknown editorial priorities; and the separate identities of CR-01, CR-03, and CR-05.
- Priority does not establish that a particular solution will work. The next skill must not introduce a new critique issue or treat an ordering decision as evidence of solution effectiveness.
