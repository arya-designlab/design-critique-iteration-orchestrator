# Iteration Plan

## Plan Basis

- Approved Phase 01 package: `outputs/phase-01/context-findings.md`, `outputs/phase-01/design-findings.md`, and `outputs/phase-01/critique-report.md`, approved in `outputs/reviews/gate-01-critique-review.md` for the recorded SHA-256 artifact versions.
- Prioritization artifact: `outputs/phase-02/prioritized-issues.md`
- Gate 02 revision basis: `outputs/reviews/gate-02-iteration-review.md`, decision `REVISE`; Issue Prioritization is accepted unchanged and only Improvement & Validation is rerun.
- Plan scope: CR-01, CR-03, and CR-05; all remain classified `Needs validation before prioritization`.
- Known constraints to preserve: The evaluation covers one static desktop homepage capture. Hidden interactions, responsive behaviour, implementation details, semantics, assistive-technology output, actual user behaviour, intended editorial hierarchy, and business or technical priorities are not established in approved evidence.
- Important limitations and unresolved evidence gaps: The approved evidence does not establish a relative issue order, implementation effort or feasibility, user prevalence, measured task impact, rendered accessibility properties, stakeholder priority, deadline, or business value.
- Hypothesis boundary: The directions below are provisional design hypotheses derived from the approved findings. They are not proven solutions, implementation-ready recommendations, exact specifications, or evidence that a change will improve the experience.

## P1 — Address First

None in the approved prioritization artifact.

## P2 — Address Next

None in the approved prioritization artifact.

## P3 — Address Later

None in the approved prioritization artifact.

## Needs Validation Before Prioritization

### CR-01 — Similar visual weight across the opening news area may make the most relevant starting point harder to identify

**Priority and confidence**

- Priority: `Needs validation before prioritization` — unchanged.
- Phase 01 severity: Tentative.
- Confidence boundary: The approved evidence shows similar visible treatment across many news items, but it does not establish intended editorial priority, visitor arrival goals, actual scanning difficulty, task effect, or prevalence.

**Original problem**

The opening news area gives many different items closely related prominence. This may make a relevant starting point harder to identify, but the approved evidence does not show whether visitors experience meaningful difficulty.

**What should improve if the concern is validated**

Visitors should be able to distinguish the content most relevant to their immediate discovery goal without losing access to the broader range of news and participation items.

**Provisional design hypothesis — not ready for implementation**

Explore whether clearer differentiation between intended primary and supporting content would make the opening news area easier to scan. Possible design levers include relative emphasis, grouping, ordering, or clearer content labeling. The appropriate lever depends on first establishing which content should be primary for which visitor goal.

**Why this hypothesis relates to the approved problem**

The approved concern is about many items receiving similar visual weight. Testing a clearer distinction directly addresses that possible source of scanning difficulty without assuming that any specific item, layout, or treatment should change.

**Evidence required before treating the hypothesis as justified**

- Clarify the intended visitor goals and editorial priorities for the opening news area without treating the contextual user assumptions as validated personas.
- Observe representative visitors locating a current item for a stated, relevant discovery goal in the current design.
- Determine whether hesitation or missed content is meaningfully connected to similar visual weight rather than content relevance, terminology, or another unestablished cause.
- Compare the validated task consequence with CR-03 and CR-05 before assigning relative iteration order.

**How to validate a future design change**

- What to test/check: Compare the current and revised opening news area using the same relevant discovery tasks. Check whether visitors can identify an appropriate starting point and still understand that broader news is available.
- Evidence that would support improvement: Visitors identify relevant content with less observable hesitation or confusion while continuing to notice useful category, date, image, and broader-news cues.
- Remaining uncertainty: The result would support only the tested goals, content, design state, and participants; it would not prove a universal hierarchy or the best visual treatment.

**Useful cues and constraints to preserve**

- Preserve useful discovery cues unless evidence supports changing them: images, category labels, dates, distinct titles, and “All the news.”
- Preserve access to varied news, events, resources, publications, NGO information, and participation opportunities.
- Do not prescribe an exact layout, order, component, size, or style before editorial priority and task evidence are established.

**Trace**

- Priority: Needs validation before prioritization — `[outputs/phase-02/prioritized-issues.md, CR-01]`
- Phase 01 finding and severity: `[outputs/phase-01/critique-report.md, CR-01]`
- Evidence/context: CR-01; CTX-05; CTX-06; TASK-01; GOAL-01; REQ-01 through REQ-04.
- Related CR IDs or dependencies: Related to CR-05 at a different scope; no relative order or blocking dependency is established.

### CR-03 — Some newsletter and footer text has low apparent distinction from its background at the captured scale

**Priority and confidence**

- Priority: `Needs validation before prioritization` — unchanged.
- Phase 01 severity: Tentative.
- Confidence boundary: The capture supports an observable concern, but it does not establish rendered contrast values, relevant viewing conditions, zoom/reflow behaviour, semantics, assistive-technology output, accessibility conformance, task criticality, or prevalence.

**Original problem**

Some newsletter consent and footer text appears less distinct from its background than nearby content. It may be harder to notice or read, but the static capture cannot establish the actual rendered or functional effect.

**What should improve if the concern is validated**

The affected consent, external-link, and policy information should be sufficiently distinguishable and readable in the contexts where visitors need it.

**Provisional design hypothesis — not ready for implementation**

Explore whether increasing the affected text’s distinction from its background and surrounding content would improve readability. Depending on confirmed implementation evidence and the existing design system, possible levers could include contrast, typographic emphasis, or separation from nearby content. No particular color, value, type treatment, or spacing change is established yet.

**Why this hypothesis relates to the approved problem**

The approved concern is specifically about low apparent distinction. Exploring greater distinction addresses that observation directly while preserving the boundary that a screenshot alone cannot establish an accessibility failure or the correct treatment.

**Evidence required before treating the hypothesis as justified**

- Inspect the implemented newsletter and footer states and measure the rendered text/background relationships through an appropriate accessibility review.
- Check the affected information under relevant zoom/reflow conditions and inspect its semantic and assistive-technology presentation.
- Establish the purpose and task relevance of the consent, external-link, and policy information.
- Use the findings to confirm, narrow, or refute CR-03 before determining its relative priority.

**How to validate a future design change**

- What to test/check: Recheck the revised rendered states through the same accessibility and readability inspection, and confirm that visitors can perceive and read the affected information in the relevant task context.
- Evidence that would support improvement: The confirmed source of low distinction is reduced without making the information’s role less clear or weakening the already prominent newsletter heading, field, and signup action.
- Remaining uncertainty: A successful check would apply to the inspected implementation and conditions; it would not by itself establish broader product priority or prove that every visitor experience improved.

**Useful cues and constraints to preserve**

- Preserve the current prominence and clarity of the newsletter heading, supporting line, email field, and signup action.
- Preserve the distinction between an observable concern and a formal accessibility-conformance conclusion.
- Do not invent exact colors, contrast values, typography sizes, weights, spacing, or component changes without implementation evidence and applicable requirements.

**Trace**

- Priority: Needs validation before prioritization — `[outputs/phase-02/prioritized-issues.md, CR-03]`
- Phase 01 finding and severity: `[outputs/phase-01/critique-report.md, CR-03]`
- Evidence/context: CR-03; CTX-05; GOAL-01; GOAL-02; REQ-01 through REQ-04.
- Related CR IDs or dependencies: None established in approved evidence; validation can proceed independently.

### CR-05 — The relationship between several major homepage modules may not be immediately clear from the captured page sequence

**Priority and confidence**

- Priority: `Needs validation before prioritization` — unchanged.
- Phase 01 severity: Tentative.
- Confidence boundary: The approved evidence shows a long sequence of varied modules, but it does not establish the intended homepage hierarchy, primary route, module importance, visitor comprehension, scroll behaviour, actual task effect, or prevalence.

**Original problem**

The homepage presents many locally understandable modules without an explicit visible explanation of their overall relationship or relative importance. Visitors may need to infer how the sections fit together, but the approved evidence does not show whether this causes meaningful orientation or discovery difficulty.

**What should improve if the concern is validated**

Visitors should be able to understand the intended roles and relative importance of the major homepage areas and identify a relevant route while scanning the page.

**Provisional design hypothesis — not ready for implementation**

Explore whether making the intended relationships among major modules more explicit would improve page-level orientation. Possible design levers include clearer section-level hierarchy, grouping, sequencing, or descriptive labels. The appropriate approach depends on first establishing the intended editorial structure and module roles.

**Why this hypothesis relates to the approved problem**

The approved concern is about the page not making the relationship or priority among major modules explicit. Exploring stronger relationship cues addresses that possible gap while retaining the existing local clarity within individual modules.

**Evidence required before treating the hypothesis as justified**

- Clarify the intended role and relative importance of the major homepage modules with appropriate project stakeholders or content owners.
- Observe representative visitors scanning the current homepage, describing its main content areas, and locating a relevant route for a stated goal.
- Determine whether uncertainty is connected to cross-section relationships rather than an individual module, terminology, missing destination context, or another unestablished cause.
- Establish whether CR-05 and CR-01 have a real sequencing dependency or can be addressed independently.

**How to validate a future design change**

- What to test/check: Compare current and revised page structures using the same comprehension and route-finding prompts. Check whether visitors can describe the main content areas, their relationships, and an appropriate route.
- Evidence that would support improvement: Visitors form a clearer account of the page structure or locate a relevant route with less observable uncertainty while still understanding individual module subjects and actions.
- Remaining uncertainty: The result would apply to the tested goals, page state, and participants; it would not prove a universal homepage structure or the best grouping treatment.

**Useful cues and constraints to preserve**

- Preserve helpful local cues unless evidence supports changing them: module titles, distinct imagery, spatial separation, content descriptions, and visible action labels.
- Preserve the separate identity of CR-05 and CR-01 unless new approved evidence establishes a different relationship.
- Do not prescribe an exact page order, layout, navigation structure, label, component, or grouping treatment before intended hierarchy and task evidence are established.

**Trace**

- Priority: Needs validation before prioritization — `[outputs/phase-02/prioritized-issues.md, CR-05]`
- Phase 01 finding and severity: `[outputs/phase-01/critique-report.md, CR-05]`
- Evidence/context: CR-05; CTX-05; CTX-06; TASK-01; GOAL-01; REQ-01 through REQ-04.
- Related CR IDs or dependencies: Related to CR-01 at a broader page scope; no relative order or blocking dependency is established.

## Cross-Issue Iteration Notes

- CR-01 and CR-05 both concern discovery and hierarchy at different scopes. Clarifying intended editorial and homepage priorities may support both, but the approved evidence does not justify merging them, assigning either a P1/P2/P3 priority, or placing one first.
- CR-03 can be checked through implementation and accessibility evidence independently of the discovery validation for CR-01 and CR-05. Independence does not automatically make it earlier or later work.
- The provisional hypotheses identify directions worth exploring only if the corresponding concern is validated. They are not recommendations ready for implementation.
- Preserve useful existing cues during exploration: news images, category labels, dates, “All the news,” local module titles, distinct imagery, spatial separation, action labels, and prominent newsletter controls.
- Future validation results are new evidence. Route them through the appropriate Phase 01 artifacts and Gate 01 before rerunning Phase 02; do not insert them directly into the current approved lineage.

## Validation Overview

| Related CR-IDs | Before treating the hypothesis as justified | Future design-change validation | Remaining boundary |
|----------------|---------------------------------------------|---------------------------------|--------------------|
| CR-01 | Clarify visitor goals/editorial priority and observe current-design discovery tasks | Compare current and revised news-area scanning using the same relevant tasks | Does not establish the best hierarchy treatment or broader prevalence |
| CR-03 | Inspect rendered accessibility/readability properties and establish task relevance | Recheck the revised implementation and confirm the affected information can be perceived and read in context | Does not by itself establish broader product priority or a universal visual treatment |
| CR-05 | Clarify intended module roles and observe current-design comprehension/route-finding | Compare current and revised page structures using the same comprehension and route-finding prompts | Does not establish the best page structure or broader prevalence |
| CR-01, CR-05 | Review whether the current-design evidence establishes a dependency | Review both change results together if both proceed | Does not justify merging the findings or assigning order without evidence |

## Unresolved Questions

- Which users, homepage tasks, content types, and modules are primary for this product?
- What editorial relationship is intended between the opening news area and the later homepage modules?
- Do CR-01 and CR-05 produce observable difficulty in relevant discovery tasks, and is either a dependency for the other?
- Does implementation evidence confirm, narrow, or refute the apparent CR-03 readability/accessibility concern, and what task consequence follows?
- What business, stakeholder, technical, implementation, timing, or accessibility constraints should influence relative order? These remain `Not established in approved evidence`.
- After new evidence passes through Phase 01 and Gate 01, which issues remain supported, what are their relative priorities, and which provisional hypotheses should proceed to design exploration?
