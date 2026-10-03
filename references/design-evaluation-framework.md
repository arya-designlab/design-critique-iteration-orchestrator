# Design Evaluation Framework — V1

## Purpose and use

Use this compact reference when evaluating a submitted UI/UX design alongside:

- the submitted screenshots and any walkthrough recordings;
- `outputs/phase-01/context-findings.md`; and
- any supplied feedback, research, usability findings, or constraints.

This is an evaluation framework, not a checklist that automatically produces defects. A later evaluator may raise a critique finding only when it can connect:

```text
observable design evidence + product/user/task context + relevant principle + plausible user impact
```

A deviation from a principle, platform convention, or common pattern is not itself a design problem. The evaluator must record uncertainty where the available evidence does not establish the interaction, user expectation, or impact.

## Evaluation boundaries

- Treat Nielsen's heuristics as broad rules of thumb, not pass/fail requirements.
- Treat Gestalt principles as perceptual organization concepts, not required visual styles.
- Treat the visual-hierarchy and typography material marked **General design guidance** as guidance rather than a formal standard.
- Use WCAG only for the scope for which it applies. Do not claim WCAG conformance or failure without evidence sufficient for the relevant success criterion.
- Do not introduce a finding because a design differs from a current trend, a competitor, or an unspecified platform convention.

## Usability and interaction evaluation

### Visibility of system status

**Principle** — Keep users informed about what is happening through appropriate feedback. This is Nielsen heuristic 1.

**What to inspect** — Visible state labels, selected states, progress, loading, confirmations, system results, or feedback directly demonstrated in a recording.

**Why it may matter** — When people cannot tell what happened or what state they are in, they may repeat an action, wait unnecessarily, or be unsure of the next step.

**Context considerations** — The necessary feedback depends on the task's consequence, duration, reversibility, user expertise, and whether the submitted state is before, during, or after an action.

**Evidence limitation** — A static screenshot rarely establishes feedback timing or behavior after an action. A recording establishes only the demonstrated state and time range.

**Source/framework** — Jakob Nielsen, [10 Usability Heuristics: Visibility of System Status](https://www.nngroup.com/articles/ten-usability-heuristics/).

### Discoverability, comprehension, and recognition rather than recall

**Principle** — Use language and concepts familiar to intended users, and make needed actions, elements, and options visible or retrievable rather than requiring recall. These are Nielsen heuristics 2 and 6.

**What to inspect** — Labels, terminology, icon-plus-label relationships, visible task cues, instructions, field labels, navigation options, and information a user would need to carry between screens.

**Why it may matter** — Unclear language or hidden task information may make a task harder to understand or increase memory effort.

**Context considerations** — Meaning depends on the supplied user group, domain expertise, task frequency, language, platform, and product vocabulary. Specialist terminology can be appropriate when it is supported by the intended users and task.

**Evidence limitation** — A reviewer can observe wording and visibility but cannot establish actual comprehension, a user mental model, or the prevalence of confusion from a screenshot alone.

**Source/framework** — Jakob Nielsen, [10 Usability Heuristics: Match Between System and the Real World; Recognition Rather than Recall](https://www.nngroup.com/articles/ten-usability-heuristics/).

### User control and freedom

**Principle** — Support clear ways to leave an unwanted action or recover from it. This is Nielsen heuristic 3.

**What to inspect** — Visible cancel, back, close, undo, discard, edit, or exit choices; whether recordings demonstrate their result; and whether the task context identifies a consequential or reversible action.

**Why it may matter** — Where users can make an unwanted or consequential action, a missing or unclear exit may leave them feeling stuck or unable to recover.

**Context considerations** — The appropriate control depends on task consequence, security, legal requirements, workflow stage, and platform behavior. A control may be intentionally unavailable in a given state for a supplied constraint.

**Evidence limitation** — Presence of a control does not establish that it works, is available by keyboard, preserves data, or is appropriate for every state. Its absence in one screenshot may simply reflect an unshown state.

**Source/framework** — Jakob Nielsen, [10 Usability Heuristics: User Control and Freedom](https://www.nngroup.com/articles/ten-usability-heuristics/).

### Consistency and conventions

**Principle** — Users should not have to wonder whether different words, situations, or actions mean the same thing. Nielsen heuristic 4 addresses internal consistency and relevant external standards or conventions.

**What to inspect** — Repeated labels, icons, control treatments, state indicators, ordering, terminology, and behavior demonstrated across supplied screens or recordings.

**Why it may matter** — Inconsistent meaning can require users to relearn an action or interpret similar-looking elements differently.

**Context considerations** — Evaluate internal consistency against the submitted product first. External conventions are relevant only when the platform, audience, task, or supplied evidence makes the convention pertinent. Intentional novelty or a domain-specific pattern is not automatically a problem.

**Evidence limitation** — One screen cannot establish product-wide consistency or user expectations. A reviewer should not assume an external convention without a relevant source or context.

**Source/framework** — Jakob Nielsen, [10 Usability Heuristics: Consistency and Standards](https://www.nngroup.com/articles/ten-usability-heuristics/).

### Error prevention and recovery

**Principle** — Prevent error-prone conditions where feasible, and help users recognize, diagnose, and recover from errors. These are Nielsen heuristics 5 and 9.

**What to inspect** — Visible constraints, confirmation opportunities, validation cues, error messages, recovery paths, destructive actions, and error handling directly shown in a recording.

**Why it may matter** — An error-prone task without clear prevention or recovery may lead to incorrect, costly, or abandoned outcomes.

**Context considerations** — Focus on errors that are plausible for the supplied task and their stated consequence. Additional confirmation can itself add friction, so its value depends on reversibility, risk, and user frequency.

**Evidence limitation** — Screenshots commonly omit validation, edge cases, error messages, server failures, and recovery behavior. Do not conclude that errors are unhandled because an error state was not provided.

**Source/framework** — Jakob Nielsen, [10 Usability Heuristics: Error Prevention; Help Users Recognize, Diagnose, and Recover from Errors](https://www.nngroup.com/articles/ten-usability-heuristics/).

### Cognitive load and focused information

**Principle** — Make task-relevant information and options available when needed, and avoid information that competes with what is relevant to the user's task. This draws on Nielsen heuristics 6 and 8.

**What to inspect** — Competing content, repeated information, visible choices, task-critical details, step complexity, and whether a user would have to remember information that could be shown.

**Why it may matter** — A crowded or memory-dependent task can make relevant information less noticeable and increase effort.

**Context considerations** — Information density is not inherently negative. It may be appropriate for expert workflows, data-heavy tasks, comparison tasks, or a user-requested overview. Assess relevance against the stated task and users, not a preference for minimalism.

**Evidence limitation** — Visual density does not prove cognitive overload, and a screenshot cannot show progressive disclosure, personalization, shortcuts, or what users actually need during the task.

**Source/framework** — Jakob Nielsen, [10 Usability Heuristics: Recognition Rather than Recall; Aesthetic and Minimalist Design](https://www.nngroup.com/articles/ten-usability-heuristics/).

### Interaction clarity and signifiers

**Principle** — In interaction design, signifiers communicate where and how an action can take place; affordances concern the possible actions of an object or environment. Use this distinction to examine whether actionable elements visibly communicate their intended interaction.

**What to inspect** — Controls, labels, icons, input fields, draggable or selectable elements, control-to-result mapping, and interaction feedback shown in the submitted design or recording.

**Why it may matter** — When an intended action is not visibly signaled or its result is unclear, users may overlook it, hesitate, or make an unintended choice.

**Context considerations** — The needed signifier depends on platform, user familiarity, task criticality, device, and the product's visual language. A minimal or unconventional treatment may work when the supplied context and evidence support it.

**Evidence limitation** — An evaluator can observe a cue but cannot prove that users perceive it as intended. Static images cannot establish gestures, hit areas, focus order, or actual mapping behavior.

**Source/framework** — Don Norman, *The Design of Everyday Things*, revised and expanded edition (2013); [Norman, “Affordances and Design”](https://jnd.org/affordances-and-design/).

## Information and visual organization

### Information hierarchy and visual hierarchy

**Principle** — **General design guidance, not a formal standard:** organize content and visual emphasis so people can distinguish primary task information, supporting information, and secondary detail in a way that fits the task.

**What to inspect** — Relative placement, grouping, order, type scale and weight, color emphasis, spacing, contrast of emphasis, repeated section patterns, and what appears most prominent in the submitted state.

**Why it may matter** — If the visual emphasis does not support the stated task or goal, users may overlook relevant information or give attention to a less relevant element.

**Context considerations** — Desired emphasis depends on the task, risk, sequence, business intent, user expertise, content volume, localization, device size, and supplied brand constraints. Visual prominence is not a substitute for user evidence.

**Evidence limitation** — A reviewer can describe apparent emphasis but cannot establish actual scan behavior, reading order, attention, or comprehension without user evidence or appropriate testing.

**Source/framework** — General design guidance. Apply with the task-relevance framing in Jakob Nielsen's [Aesthetic and Minimalist Design heuristic](https://www.nngroup.com/articles/ten-usability-heuristics/); no universal hierarchy rule is asserted here.

### Grouping and Gestalt principles

**Principle** — Gestalt perceptual organization includes grouping cues such as proximity, similarity, good continuation, and closure. Use them to examine what elements may appear related, separate, or structurally connected.

**What to inspect** — Spacing, alignment, enclosure, shared visual treatment, repeated shape or color, continuation of lines or layout, and figure–ground separation.

**Why it may matter** — Grouping cues can influence how people parse sections, associate labels with controls, or distinguish related from unrelated information.

**Context considerations** — Cues can reinforce or compete with one another. Their interpretation depends on the whole composition, reading direction, device, visual language, task, and content. Do not treat any single grouping cue as determinative.

**Evidence limitation** — A screenshot can reveal candidate grouping cues, but it cannot prove users' interpretation, task performance, or whether a perceived grouping causes a problem.

**Source/framework** — Max Wertheimer, [“Laws of Organization in Perceptual Forms” (1923), translation](https://psychclassics.yorku.ca/Wertheimer/Forms/forms). This framework covers foundational proximity, similarity, continuation, and closure concepts; it is not a UI compliance standard.

### Typography and readability

**Principle** — **General design guidance, not a formal standard:** typography should support reading and distinction of content in the supplied task and viewing context. WCAG supplies testable criteria for some accessibility concerns, but it is not a general visual-style prescription.

**What to inspect** — Legibility of visible text at the supplied scale, hierarchy between headings and body content, line breaks, truncation, label distinction, and whether text is differentiated by color alone in the submitted state.

**Why it may matter** — Text that is difficult to distinguish or parse may slow comprehension or make task-relevant information easier to miss.

**Context considerations** — Suitability depends on audience, language/script, content complexity, device and viewport, zoom support, brand constraints, and task. Avoid treating a particular typeface, size, or line length as universally correct without a project requirement.

**Evidence limitation** — A screenshot does not establish rendered font settings, zoom/reflow behavior, text spacing support, localization behavior, or actual contrast calculation. Do not infer these properties from appearance alone.

**Source/framework** — General design guidance; relevant accessibility standard: W3C [WCAG 2 Overview](https://www.w3.org/WAI/standards-guidelines/wcag/) and [Understanding WCAG 2.2](https://www.w3.org/WAI/WCAG22/Understanding/).

## Observable accessibility concerns and boundaries

### Concerns that may be raised from visible design evidence

**Principle** — WCAG 2 organizes accessibility guidance under perceivable, operable, understandable, and robust principles. In a visual review, flag only observable concerns as concerns for validation, not conformance conclusions.

**What to inspect** — Text or controls that appear difficult to distinguish from their background; information apparently conveyed only through color; unclear visible focus indication in a demonstrated keyboard flow; text embedded in images; visually ambiguous labels; and visible states that may be hard to differentiate.

**Why it may matter** — These visible characteristics may create barriers for people with different visual, cognitive, or interaction needs.

**Context considerations** — Consider the supplied medium, device, user evidence, brand constraints, and whether a recording demonstrates an alternative cue or state. A concern should be framed as a validation need when the evidence is incomplete.

**Evidence limitation** — A screenshot or recording alone does not establish actual contrast values across all states, text alternatives, programmatic names and relationships, keyboard operation, focus order, semantics, assistive-technology behavior, or WCAG conformance.

**Source/framework** — W3C [WCAG 2 Overview](https://www.w3.org/WAI/standards-guidelines/wcag/); relevant supporting material includes [Understanding WCAG 2.2](https://www.w3.org/WAI/WCAG22/Understanding/) and [Understanding Contrast (Minimum)](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum.html).

### Requirements that need implementation or interaction evidence

**Principle** — WCAG conformance is determined by meeting applicable testable success criteria, many of which require code, interaction, and assistive-technology evidence.

**What to inspect** — When the supplied material includes a recording, accessibility tree, semantic markup, keyboard demonstration, screen-reader output, or implementation notes, record the exact demonstrated evidence and time/location. Otherwise, identify the evidence that would be needed.

**Why it may matter** — Semantic structure, text alternatives, names and roles, focus management, keyboard access, reflow, and dynamic announcements are not reliably determined from visual appearance.

**Context considerations** — The applicable standard and requirements depend on product medium, jurisdiction, organization policy, and supplied technical context. The evaluator should not assume legal or contractual obligations that are absent from the project materials.

**Evidence limitation** — Do not claim WCAG compliance or failure from screenshots alone. A video may show one behavior but does not establish behavior across all content, devices, inputs, or assistive technologies unless the supplied evidence covers them.

**Source/framework** — W3C [WCAG 2 Overview](https://www.w3.org/WAI/standards-guidelines/wcag/), including its explanation that conformance is determined through WCAG success criteria; W3C tutorials on [page regions](https://www.w3.org/WAI/tutorials/page-structure/regions/) and [text alternatives for images](https://www.w3.org/WAI/tutorials/images/decision-tree/).

## Finding-quality check for the future evaluator

Before raising a critique finding, confirm that it states:

- the observable design evidence, with screenshot/frame or recording time-range locator;
- the relevant product, user, task, and constraint context from `context-findings.md`;
- the applicable principle or clearly labeled general guidance;
- a plausible, qualified user impact rather than an asserted outcome; and
- what remains unproven and would need validation.

Do not raise a finding when the only rationale is personal preference, an unspecified convention, a trend, or a principle cited without a relevant context and potential impact.

## Included source list

- Jakob Nielsen / Nielsen Norman Group, [10 Usability Heuristics for User Interface Design](https://www.nngroup.com/articles/ten-usability-heuristics/).
- World Wide Web Consortium (W3C), [Web Content Accessibility Guidelines (WCAG) 2 Overview](https://www.w3.org/WAI/standards-guidelines/wcag/) and [Understanding WCAG 2.2](https://www.w3.org/WAI/WCAG22/Understanding/).
- Max Wertheimer, [“Laws of Organization in Perceptual Forms” (1923), translation](https://psychclassics.yorku.ca/Wertheimer/Forms/forms).
- Don Norman, *The Design of Everyday Things*, revised and expanded edition (2013); [“Affordances and Design”](https://jnd.org/affordances-and-design/).

## Deliberately excluded from V1

- Competitor analysis and current design-trend guidance.
- Product-type-specific conventions and pattern libraries.
- Analytics interpretation and behavioral-psychology or UX-law libraries.
- Numerical thresholds, benchmarks, or unqualified “best practices.”
- A full WCAG audit checklist, because reliable conformance evaluation requires scope-specific implementation and interaction evidence.
