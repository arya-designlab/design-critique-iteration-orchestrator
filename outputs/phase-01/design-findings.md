# Design Findings

## Evaluation Basis

- Primary context input: `outputs/phase-01/context-findings.md`
- Evaluation framework: `references/design-evaluation-framework.md`
- Submitted design evidence evaluated: `projects/design_critique_iteration_orchestrator/input/screencapture-ichngoforum-org-2026-10-02-12_05_39.pdf`, pages 1–4; one static desktop homepage capture shown across a vertical scroll.
- Relevant context, task, and requirements: CTX-05, CTX-06, USR-01 through USR-03 as contextual assumptions only, TASK-01, TASK-02, GOAL-01, GOAL-02, REQ-01 through REQ-04, ASM-01, and AMB-01.
- Evidence limitations carried forward: no walkthrough, interaction specification, stakeholder/user feedback, research, usability findings, analytics, formal product requirements, technical constraints, or accessibility audit was supplied. The capture does not establish responsive behaviour, control behaviour, keyboard operation, semantics, assistive-technology output, complete journeys, user comprehension, or actual impact.
- Re-evaluation note: this artifact was regenerated from the supplied evidence using the updated full-scope coverage pass. Existing IDs were retained only for findings that survived the current evidence test; previously considered candidates absent from this artifact were not preserved as findings.

## Supplied Design Coverage

| Visible region / component | Evidence locator | Inspection outcome | Evaluation areas considered |
|----------------------------|------------------|--------------------|----------------------------|
| Header, logo, top-level navigation, social icons, and search | `[screencapture-ichngoforum-org-2026-10-02-12_05_39.pdf, page 1, header]` | Reviewed — no material concern established from supplied evidence. Menu contents, destinations, and search behaviour cannot be determined. | Discoverability/comprehension; information hierarchy; interaction clarity; consistency; typography/readability. Visible labels, chevrons, and search provide route cues; absent menu content is not treated as a problem. |
| Primary image-led news grid | `[capture PDF, page 1, upper and middle news grid]` | Candidate promoted to CR-01. | Information/visual hierarchy; cognitive load; grouping; discoverability; typography/scanability. |
| Secondary text-led news cards and “All the news” action | `[capture PDF, pages 1–2, lower news area]` | Candidate promoted to CR-01 as supporting scope. | Information/visual hierarchy; cognitive load; grouping; discoverability; action clarity. The “All the news” action is counterevidence that a broader route exists. |
| “Safeguarding living cultural traditions” feature | `[capture PDF, page 2, full-width feature]` | Reviewed — no material concern established from supplied evidence. | Hierarchy; grouping; typography/readability; action clarity; visible accessibility. The title, supporting copy, and “Discover all” action form a locally coherent module. |
| Horizontally clipped NGO card sequence and visible indicators | `[capture PDF, page 2, NGO cards; page 3, upper-edge indicators]` | Cannot determine. | Discoverability; grouping; interaction clarity; user control. Partial cards and indicators may signal continuation, but their relationship and operation require interaction evidence; no CR finding was promoted. |
| “Your NGO on this website” callout and form action | `[capture PDF, page 3, upper callout]` | Reviewed — no material concern established from supplied evidence. | Discoverability/comprehension; hierarchy; typography; action clarity; consistency. Heading, explanatory copy, and “Fill out the form” provide a visible local relationship. |
| “Messages to the 2003 Convention” feature | `[capture PDF, page 3, full-width illustrated feature]` | Reviewed — no material concern established from supplied evidence. | Hierarchy; grouping; readability; action clarity; visible accessibility. Title, purpose copy, and “Read messages” action are visibly grouped. |
| Symposium and web-dossier paired feature panels | `[capture PDF, page 3, paired panels]` | Reviewed — no material concern established locally; included in CR-05’s cross-section assessment. | Hierarchy; grouping; typography; action clarity; consistency. Each panel has a title, supporting copy, and action; their broader role in the page sequence remains qualified in CR-05. |
| “#HeritageAlive Sharing Experience” online-journal feature | `[capture PDF, page 4, upper feature]` | Reviewed — no material concern established locally; included in CR-05’s cross-section assessment. | Hierarchy; grouping; typography/readability; action clarity; visible accessibility. The module visibly labels its content type and action. |
| Newsletter signup | `[capture PDF, page 4, newsletter section]` | Candidate promoted to CR-03 for low-emphasis consent text. Form submission, validation, labels/semantics, error prevention, and feedback cannot be determined. | Typography/readability; observable accessibility; interaction clarity; error prevention/recovery; system status. |
| Footer organisation summary, external links, policy links, social icons, and back-to-top control | `[capture PDF, page 4, footer]` | Candidate promoted to CR-03 for low apparent text/background distinction in part of the footer. Other interaction and semantic properties cannot be determined. | Typography/readability; observable accessibility; grouping; discoverability; interaction clarity. |
| Cross-section homepage sequence | `[capture PDF, pages 1–4, complete visible page]` | Candidate promoted to CR-05. | Overall information/visual hierarchy; grouping; cognitive load; discoverability; section relationships. Individual modules provide local counterevidence through titles and actions. |

## Evaluation-Area Coverage

| Area | Status | Scope or reason |
|------|--------|-----------------|
| Visibility of system status | Cannot determine from supplied evidence | No action, loading, submission, carousel change, search result, or post-action state is shown. A walkthrough or interaction-state evidence is required. |
| Discoverability, comprehension, and recognition rather than recall | Applicable and evaluated | Header/navigation, news routes, module titles, CTA labels, NGO-card sequence, newsletter, and footer were inspected. CR-01 and CR-05 apply. Navigation and carousel candidates were not promoted because unshown interaction/menu evidence is required and visible cues provide counterevidence. |
| User control and freedom | Cannot determine from supplied evidence | The capture does not show unwanted states, cancel/back/undo behaviour, modal states, form progress, carousel control, or recovery paths. Interaction evidence is required. |
| Consistency and conventions | Applicable and evaluated | Visible navigation, cards, feature modules, CTA labels/treatments, and typography were compared within the captured homepage. Reviewed — no material concern established from supplied evidence; variation generally corresponds to visibly different module types, and product-wide consistency cannot be established. |
| Error prevention and recovery | Cannot determine from supplied evidence | The newsletter form is visible, but no validation, error, destructive action, constraint, or recovery state is shown. Form interaction and error-state evidence is required. |
| Cognitive load and focused information | Applicable and evaluated | News density and the full page’s many content modules were inspected. CR-01 and CR-05 apply; no user-performance evidence establishes actual cognitive load. |
| Interaction clarity and signifiers | Applicable and evaluated | Visible chevrons, search, buttons, card actions, newsletter field, carousel cues, social icons, and back-to-top control were inspected. Reviewed — no material concern established from supplied evidence beyond evidence-limited carousel/form behaviour; visible controls generally include familiar shapes or text labels. |
| Information hierarchy and visual hierarchy | Applicable and evaluated | News hierarchy, individual modules, paired features, footer, and complete page sequence were inspected. CR-01 and CR-05 apply. |
| Grouping and Gestalt principles | Applicable and evaluated | Card grids, horizontal card sequence, callout, banners, paired panels, newsletter, and footer groupings were inspected. CR-05 applies at cross-section level; most individual modules are visibly grouped by proximity, enclosure, image treatment, and alignment. |
| Typography and readability | Applicable and evaluated | Headings, card titles/summaries, navigation, feature copy, CTA labels, newsletter copy, and footer text were inspected. CR-03 applies; other reviewed regions produced no material supported concern. |
| Observable accessibility concerns | Applicable and evaluated | Visible text distinction and information presentation were inspected across the page. CR-03 is an observable validation concern only; no conformance conclusion is made. |
| Requirements needing implementation or interaction evidence | Cannot determine from supplied evidence | Semantic structure, names/roles, text alternatives, keyboard operation, focus order, reflow, dynamic announcements, and assistive-technology behaviour require implementation or interaction evidence not supplied. |

## Findings

### CR-01: The opening news area presents many content items with similar visual weight, which may make the most relevant starting point harder to identify

**Evaluation area:** Information and visual hierarchy; cognitive load and focused information; discoverability and comprehension

**Observable design evidence:**
- The first captured homepage view presents six image-led news cards across two rows, followed by six text-led cards across the page break. The initial cards repeatedly use an image, small category labels, bold multi-line titles, summary copy, and dates. — `[screencapture-ichngoforum-org-2026-10-02-12_05_39.pdf, pages 1–2, news area]`
- The visible items cover different content types, including tourism dialogues, a UNESCO meeting, webinars, a symposium call, #HeritageAlive articles, calls for films/papers, and an electoral-board call. — `[capture PDF, pages 1–2, news area]`

**Relevant context and evidence:**
- The website is an information, communication, and resource platform containing news, events, resources, publications, NGO information, and participation opportunities. — `[outputs/phase-01/context-findings.md, CTX-05; CTX-06]`
- Visitors may need to discover several different content types, and the site needs to support information discovery. — `[outputs/phase-01/context-findings.md, TASK-01; GOAL-01]`

**Applicable principle or guidance:**
- Information hierarchy and visual hierarchy: visible organisation and emphasis should help distinguish task-relevant primary, supporting, and secondary information. — `[references/design-evaluation-framework.md, Information hierarchy and visual hierarchy]`
- Cognitive load and focused information: competing visible information may make task-relevant information less noticeable. — `[references/design-evaluation-framework.md, Cognitive load and focused information]`

**Finding rationale:**
- The opening area gives many different news and participation items closely related prominence. For a visitor arriving with a specific discovery goal, the visible treatment may provide limited help in deciding which item is the most relevant starting point.

**Plausible user impact:**
- Some visitors may need more time to scan the opening area or may overlook a relevant current item among similarly weighted alternatives.

**Supporting or contradictory evidence:**
- Images, category labels, dates, title differences, and the “All the news” action provide discovery cues and a route to broader content. No supplied evidence establishes the intended editorial priority or that visitors actually struggle with the area.

**Evidence limitation and validation need:**
- The capture does not establish intended content priority, visitor goals on arrival, click behaviour, scan behaviour, or task success. Clarify the intended discovery priorities and test whether representative visitors can locate a current item relevant to a stated goal.

### CR-03: Some newsletter and footer text has low apparent distinction from its background at the captured scale

**Evaluation area:** Typography and readability; observable accessibility concerns

**Observable design evidence:**
- The newsletter consent sentence appears in small, light, italic text on a pale yellow background. — `[screencapture-ichngoforum-org-2026-10-02-12_05_39.pdf, page 4, newsletter section]`
- The “Useful external links” heading appears in dark teal against the teal footer background, while adjacent footer content uses white text. Copyright and policy text near the lower edge also appears low-emphasis against the footer background. — `[capture PDF, page 4, footer]`

**Relevant context and evidence:**
- The site supports information and access to the Forum’s resources and network activities. — `[outputs/phase-01/context-findings.md, CTX-05; GOAL-01]`
- The supplied evaluation goal explicitly includes readability, scanability, and accessibility where reasonably observable. — `[outputs/phase-01/context-findings.md, GOAL-02]`
- No accessibility audit, rendered contrast values, device/browser distribution, zoom evidence, or implementation evidence was supplied. — `[outputs/phase-01/context-findings.md, Missing information that limits later evaluation]`

**Applicable principle or guidance:**
- Typography and readability: visible text should support reading and distinction in the supplied task and viewing context. — `[references/design-evaluation-framework.md, Typography and readability]`
- Observable accessibility concerns: text that appears difficult to distinguish may be flagged for validation without claiming conformance failure. — `[references/design-evaluation-framework.md, Concerns that may be raised from visible design evidence]`

**Finding rationale:**
- These text treatments have lower apparent distinction than nearby content and backgrounds. If the rendered treatments are difficult to distinguish in use, newsletter consent information and footer navigation/policy information may be less available to visitors who need them.

**Plausible user impact:**
- Some visitors may overlook or have difficulty reading the consent, external-link heading, or policy information in the captured viewing conditions.

**Supporting or contradictory evidence:**
- The newsletter heading, supporting line, email field, and signup button are visibly prominent, and the external-link items below the footer heading appear lighter than the heading itself. The capture cannot establish actual contrast values or users’ viewing conditions.

**Evidence limitation and validation need:**
- This is an observable validation concern only. Measure rendered text/background contrast in relevant states and inspect text rendering, zoom/reflow, semantics, and assistive-technology behaviour before making any accessibility-conformance conclusion.

### CR-05: The relationship between several major homepage modules may not be immediately clear from the captured page sequence

**Evaluation area:** Information and visual hierarchy; grouping and Gestalt principles; cognitive load and focused information

**Observable design evidence:**
- After the extended news area, the homepage moves through a “Safeguarding living cultural traditions” banner, an NGO-card sequence, a “Your NGO on this website” callout, a “Messages to the 2003 Convention” banner, symposium and web-dossier panels, an online-journal banner, newsletter signup, and footer. — `[screencapture-ichngoforum-org-2026-10-02-12_05_39.pdf, pages 2–4, complete lower-page sequence]`
- These modules use several visual structures—full-width image banners, horizontally arranged cards, a text-and-button callout, paired feature panels, and a form area—and the capture does not show an overarching visible label or explanation connecting the sequence. — `[capture PDF, pages 2–4, complete lower-page sequence]`

**Relevant context and evidence:**
- The website functions as an information, communication, and resource platform with varied content types. — `[outputs/phase-01/context-findings.md, CTX-05; CTX-06]`
- The site needs to support information discovery and access to the Forum’s network, activities, and resources. — `[outputs/phase-01/context-findings.md, GOAL-01]`
- No supplied requirement establishes the intended editorial hierarchy, primary homepage route, or relative importance of the modules. — `[outputs/phase-01/context-findings.md, Missing information that limits later evaluation]`

**Applicable principle or guidance:**
- Information hierarchy and visual hierarchy: the organisation and emphasis of content should fit the relevant task. — `[references/design-evaluation-framework.md, Information hierarchy and visual hierarchy]`
- Grouping and Gestalt principles: grouping cues influence how sections appear related or separate. — `[references/design-evaluation-framework.md, Grouping and Gestalt principles]`
- Cognitive load and focused information: competing modules may increase the effort needed to identify task-relevant information. — `[references/design-evaluation-framework.md, Cognitive load and focused information]`

**Finding rationale:**
- Each module communicates its local subject, but the captured page does not make the intended relationship or priority among the modules explicit. A visitor trying to understand the homepage as a whole may need to infer whether a module is a primary route, current campaign, resource collection, or secondary promotion.

**Plausible user impact:**
- Some visitors may spend additional effort deciding which section to attend to or may overlook a relevant route while scanning the long page.

**Supporting or contradictory evidence:**
- Individual modules have clear titles, distinct imagery, spatial separation, and usually a visible action label; these cues support local comprehension. No supplied evidence establishes the intended editorial sequence or whether visitors experience the overall relationship as unclear.

**Evidence limitation and validation need:**
- The static capture cannot establish scroll behaviour, destination content, analytics, comprehension, or task performance. Clarify the intended page hierarchy and test whether representative visitors can describe the main content areas and locate a relevant route after scanning the homepage.

## Requirement Alignment and Counterevidence

| Context ID | Observation | Status | Evidence limitation |
|------------|-------------|--------|---------------------|
| REQ-01 | The full four-page homepage capture was inspected, including the header, all major modules, form area, and footer. | Appears supported | The capture does not establish unshown states or pages. |
| REQ-02 | Interaction, responsive, hidden-state, semantic, and implementation properties are recorded as `Cannot determine` rather than inferred. | Appears supported | Direct interaction and implementation evidence is still needed. |
| REQ-03 | Coverage and findings separate direct visible observations, context, inference, counterevidence, and validation needs. | Appears supported | This separation does not establish actual user impact. |
| REQ-04 | Candidate observations were not promoted solely because they differed from a principle or convention; navigation and carousel candidates were withheld where grounding was insufficient. | Appears supported | Further evidence could support, narrow, or refute those candidates. |

## Unresolved Evaluation Limits

- Dropdown contents, search behaviour, destinations, hover/focus states, carousel controls, newsletter submission/validation, and back-to-top behaviour cannot be evaluated from the static capture.
- Responsive layouts, keyboard operation, focus order, semantic structure, text alternatives, programmatic names/roles, reflow, dynamic announcements, and assistive-technology behaviour cannot be determined.
- Intended primary audience, primary homepage task, editorial priority, business importance, user comprehension, prevalence, and actual task impact are not established by the supplied evidence.
- Product-wide consistency cannot be concluded from one homepage capture.

## Coverage Completion Check

- Meaningful supplied design regions/components inspected: header/navigation; image-led and text-led news content; “All the news”; safeguarding feature; NGO-card sequence/indicators; NGO participation callout; Convention messages feature; symposium and web-dossier panels; online-journal feature; newsletter; footer; and the complete cross-section sequence.
- Framework areas applicable and evaluated: discoverability/comprehension, consistency/conventions, cognitive load/focused information, interaction clarity/signifiers, information/visual hierarchy, grouping/Gestalt, typography/readability, and observable accessibility concerns across their relevant visible regions.
- Reviewed with no material concern established: visible header/navigation treatment; local safeguarding-feature structure; NGO participation callout; Convention messages feature; local structure of paired feature panels; local structure of the online-journal feature; visible CTA/action-label system; and homepage-level visible consistency beyond the findings recorded.
- Cannot determine from supplied evidence: system-status feedback, user control/freedom, error prevention/recovery, carousel operation, form behaviour, responsive behaviour, semantics, keyboard/focus behaviour, and other implementation-dependent accessibility requirements.
- Candidate concerns not promoted: navigation predictability was not promoted because menus/search/destinations are unshown and visible labels/chevrons provide counterevidence; carousel traversal was not promoted because the partial cards and indicators may intentionally signal continuation while their operation is unshown; CTA variation was not promoted because the labels generally identify locally relevant actions and no supported impact was established.
- Coverage boundary: Broad inspection does not require a finding count. CR-01, CR-03, and CR-05 are the only candidates that met the evidence standard in this pass.

## Handoff to Critique Synthesis

- Findings available for consolidation: CR-01, CR-03, CR-05.
- Potential duplicates or related findings: CR-01 and CR-05 both involve hierarchy and scanning but concern distinct scopes—the opening news area and the cross-section homepage sequence—and should remain separately traceable.
- Evidence limitations and counterevidence that must be preserved: visible labels/chevrons/search; category labels, dates, images, and “All the news”; locally clear module titles/actions; partial-card and indicator cues; prominent newsletter controls; absence of interaction/user evidence; absence of stated editorial priorities; and absence of accessibility-conformance evidence.
- Previously considered candidates concerning navigation predictability and carousel traversal did not meet the current evidence standard and are retained only as coverage/evidence-limit notes, not `CR-` findings.
- This artifact identifies findings only; it does not assign severity, make approval decisions, prioritize iteration work, or recommend design changes.
