---
name: uxblueprint
description: Design, build, improve, and audit application interfaces through a staged UI/UX and frontend engineering workflow. Use for new apps, dashboard redesigns, responsive layouts, design tokens and AGENTS.md, component states, accessibility, motion, performance, keyboard interaction, persistence, localization, and telemetry. Follow existing project and hosting workflows. Exclude backend-only work and standalone marketing copy.
---

# uxblueprint

Turn a product task into a coherent interface and working frontend, with evidence at each stage. Treat polish as clarity, consistency, responsiveness, and reliable recovery. Avoid promising production readiness from appearance alone.

## Operating contract

1. Inspect the repository, applicable AGENTS.md files, installed versions, existing components, brand references, data contracts, and authorized scope before changing code. Preserve working behavior and unrelated changes. Reuse the existing stack unless a migration solves a concrete problem.
2. Establish the primary user, task, desired outcome, and main constraint. Ask only for missing information that changes the next useful action; otherwise state provisional assumptions and proceed. Prefer one to three high-impact questions over a technical intake checklist.
3. Select a mode from the request:
   - **Blueprint:** Produce the task flow, architecture, tokens, project rules, and acceptance plan. Write no application code.
   - **Guided stages:** Complete the requested stage and its checks, then return its result and next stage. Use when the user asks to proceed one prompt or stage at a time.
   - **Build:** Execute authorized stages sequentially, proceeding after each acceptance gate. Gates require evidence, not repeated permission. Obtain concrete user judgment only for consequential unresolved choices.
   - **Audit or redesign:** Inspect the current interface and actual task flow; prioritize observed problems, then implement the authorized scope. Avoid starting a new stack or aesthetic merely because this skill is invoked.
4. Maintain a compact project blueprint using `assets/blueprint.template.md` when work spans several stages. Record assumptions, decisions, next stage, and evidence so a later turn can resume without rebuilding context.
5. Coordinate with Sites or another required platform skill for site projects; let that skill own hosting and source mechanics. Use JTBD for unresolved customer jobs, PLF for positioning and substantive copy, and service-design analysis only where the task needs it. Do not turn this skill into an unsolicited strategy engagement.
6. Distinguish a mockup, a working prototype, and a connected application. Label synthetic data. Never show a fake successful submission as proof of a real transaction, or invent integrations and backend results.
7. Follow existing release boundaries. A local UI task does not by itself authorize a production deployment, live data mutation, repository push, or new collection of user telemetry. Prepare reviewable work; act on releases and integrations when the session authorizes them.

## Resource map

Read only the relevant files, resolving paths relative to this skill:

- `references/stages.md`: Stage-specific implementation instructions and acceptance criteria; read before running a stage.
- `references/verification.md`: Accessibility, responsive, state, performance, and release evidence; read before auditing or claiming completion.
- `references/service-design.md`: Process boundaries, customer inputs, responsibility, effort, and outcome analysis from the supplied Sampson text; use for onboarding, multistep workflows, dashboards tied to operations, and redesigns.
- `references/prompt-sequence.md`: Reusable invocation prompts for the original staged approach, including the separated telemetry stage.
- `references/sources.md`: Primary technical references and provenance; check current official docs when standards, APIs, or installed versions matter.
- `assets/AGENTS.template.md`: Project-specific UI constraints; adapt rather than overwrite existing project rules.
- `assets/blueprint.template.md`: Task, architecture, state, and evidence record; omit irrelevant fields.

## Sequential workflow

Complete and verify each applicable stage before beginning dependent work. For a small component fix, enter at the relevant stage and run only affected checks. Mark skipped optional stages with a reason.

| Stage | Produce | Gate before advancing |
| --- | --- | --- |
| 0. Inspect and frame | Current-state evidence, priority task, outcome, assumptions, scope | Task and constraints are concrete enough to act on |
| 1. Blueprint and foundations | Stack rationale, modular structure, task flow, design tokens, adapted AGENTS.md, acceptance plan | Define a coherent hierarchy and how task success will be observed |
| 2. Shell | Responsive navigation, content container, route states, mobile behavior | Navigate with pointer and keyboard at desktop and narrow widths |
| 3. Component or feature | One complete task slice, real content contract, relevant states | Complete the task and recover from expected failures |
| 4. Friction and accessibility | Observed defects, fixes, evidence | No blocking keyboard, contrast, overflow, or task-friction defect in scope |
| 5. Defensive UX | Loading, empty, filtered, denied, failed, pending, and success states as applicable | Transitions preserve context and provide honest next actions |
| 6. Motion | Purposeful feedback, transitions, reduced-motion alternatives | Motion neither delays actions nor hides state; reduced motion works |
| 7. Performance | Measured bottlenecks, scoped changes, asset and bundle improvements | Compare before/after under comparable conditions; disclose missing field data |
| 8. Power-user interaction | Appropriate shortcuts and established keyboard patterns | No collision with typing, assistive technology, or existing controls |
| 9. Persistence | Safe preferences and eligible drafts, lifecycle and schema | Reload, corruption, denial, expiry, identity change, and submission cleanup work |
| 10. Localization | Extracted strings where appropriate, Intl formatting, locale/time-zone contract | Long strings and locale-sensitive data retain meaning and layout |
| 11. Telemetry and isolation | Error containment, event contract, configured adapter or inert stub | Errors recover; events omit sensitive data and match verified outcomes |
| 12. Final verification | Working preview or changed files, evidence matrix, remaining risks | Required checks pass; unverified claims remain explicit |

Repeat stage 3 for each feature. Build one useful vertical slice early, then expand; avoid completing every optional subsystem before the user can perform a meaningful task.

## Design constraints

- Follow supplied identity and successful reference patterns. Explain a visual direction through the task: hierarchy, density, navigation, and emphasis. Avoid automatic gradient heroes, glass cards, oversized metric tiles, arbitrary decorative imagery, or a generic sidebar on every app.
- Use semantic tokens for color, spacing, typography, radii, elevation, motion, and layering. Default to the user's 8px rhythm with a documented 4px half-step. Allow borders, icon strokes, font metrics, and fluid sizing to use appropriate units; do not distort usability to make every measurement a multiple of eight.
- Give dense working interfaces purposeful density and progressive disclosure. Use spacing to show relationships. Do not require every dashboard to become sparse or every mobile table to become cards.
- Preserve reading and task order across breakpoints. Give controls useful labels and information a deliberate hierarchy. Handle long titles, URLs, identifiers, localization expansion, and actual worst-case data.
- Target WCAG 2.2 AA. Treat 44x44 CSS px touch areas as the project default, not the exact AA requirement. Combine automated checks with manual keyboard, zoom/reflow, and relevant screen-reader checks; never infer compliance from a token palette or tool score alone.
- Use native elements and tested component patterns first. Distinguish links from actions, ordinary lists from composite widgets, modals from nonmodal popovers, and current route from selection.
- Show error explanations in text, associated with fields or affected controls; use icons when useful and never rely on color alone. Preserve input, focus, and retry paths.
- Support reduced motion. Give status messages accessible announcements without moving focus. Keep actionable or essential errors available; do not force every toast to disappear after four seconds.
- Preserve data meaning: label units, periods, filters, sources, freshness, denominators, and uncertainty where relevant. Include a text/table alternative for important charts.

## Acceptance and reporting

Define task checks before coding. Use the project's required build, type, lint, and test commands; add focused behavior tests for consequential state transitions, not tests that merely mirror CSS. Inspect a rendered interface at relevant desktop and mobile widths when the environment permits. Record exactly what ran and what was observed.

For every gate, record **pass**, **fail**, **not applicable**, or **unverified**, with its evidence and reason. Fix failures within the authorized scope. For missing access or tools, complete available work and name the unresolved check; do not describe a gate as passed.

Report the result first, then the meaningful changes, validation, and remaining constraints. In guided mode, name the next stage without claiming it is completed. For a full build, provide the runnable preview or repository changes using the platform's normal delivery route. Distinguish source implementation, browser emission, backend receipt, field measurement, and realized customer outcomes.
