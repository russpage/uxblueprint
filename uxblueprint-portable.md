---
name: uxblueprint
description: Design, build, improve, and audit application interfaces through a staged UI/UX and frontend engineering workflow. Use for new apps, dashboard redesigns, responsive layouts, design tokens and AGENTS.md, component states, accessibility, motion, performance, keyboard interaction, persistence, localization, and telemetry. Follow existing project and hosting workflows. Exclude backend-only work and standalone marketing copy.
---

> Portable use: When this file is uploaded or pasted alone, resolve relative reference and template paths using the appended `Bundled file: <path>` sections. No platform tools, plugins, browsing, filesystem access, or deployment capability are guaranteed. Use only available capabilities, preserve the operating boundaries below, and mark checks unverified when tooling or access is missing.

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


---

# Bundled file: assets/blueprint.template.md

# UX blueprint: [project]

Use this as a compact working record; omit fields that do not affect the work.

## Task and scope

- Mode and current stage:
- Primary user and context:
- Priority task, trigger, and observable outcome:
- Scope and release authorization:
- Supplied references and existing constraints:
- Observed facts:
- Assumptions and unanswered consequential questions:

## Task flow and responsibility

| Step | Actor/controller | Required input and owner | Prerequisite | Customer benefit | Effort/wait/failure | Evidence |
| --- | --- | --- | --- | --- | --- | --- |
| [verb + object] | | | | | | |

For consequential workflows, include external handoffs and the work after the UI's apparent success. Label inferred steps. Add recovery and completion evidence in the feature contract below.

## Foundations

- Stack/version rationale and existing components to reuse:
- Feature/shared-service folder boundaries:
- Navigation and first-screen hierarchy:
- Token source and selected palette/type/spacing/density:
- Responsive and accessibility strategy:
- Data, identity, and backend contracts:
- Applicable project instructions:

## Feature contract

| Feature/task | State or transition | UI response | Recovery/next action | Completion signal | Evidence |
| --- | --- | --- | --- | --- | --- |
| | | | | | |

- Optional modules included/deferred and why:
- Persistence: eligible fields, storage, identity, expiry, clear condition:
- Localization: locales, time zone, currency/units, date semantics:
- Telemetry: event triggers, allowlist, adapter, permission, receipt layer:
- Performance: budget, baseline, comparable environment:

## Acceptance record

| Check | Status: pass/fail/not applicable/unverified | Evidence | Gap or owner |
| --- | --- | --- | --- |
| Priority task | | | |
| Consequential failure/recovery | | | |
| Required build/type/lint/tests | | | |
| Responsive/long-content/zoom | | | |
| Keyboard/focus | | | |
| Contrast/accessible names/status | | | |
| Other applicable modules | | | |

## Continuation

- Decisions made and reasons:
- Files changed:
- Known limitations and remaining risks:
- Next stage or task:
- Preview/release status:


---

# Bundled file: references/stages.md

# UX blueprint stage playbook

## Contents

- Operating modes and evidence gates
- 0. Inspect and frame
- 1. Blueprint and design foundations
- 2. Responsive application shell
- 3. Components and a useful vertical slice
- 4. UX friction and accessibility audit
- 5. Loading, empty, error, and transition states
- 6. Purposeful motion
- 7. Measured performance
- 8. Keyboard shortcuts and advanced interaction
- 9. Safe persistence
- 10. Internationalization and formatting
- 11. Resilience, telemetry, and error reporting
- 12. Review and delivery

## Operating modes and evidence gates

In **guided mode**, complete the requested stage, verify it, and return its result plus the next useful stage. The user can invoke the following stage when ready. In **build mode**, progress through the authorized, applicable stages sequentially. A stage boundary is a verification checkpoint; it does not require another permission request. A blueprint-only request ends at stage 1 without writing application code.

For an existing application, inspect first and enter at the earliest stage needed by the requested change. Preserve established conventions unless evidence justifies changing them. Skip optional capabilities that do not support the primary task. Do not generate an elaborate platform when one working flow meets the brief.

Each gate records: expected behavior, implementation or decision, evidence obtained, unresolved limits, and next action. Separate observed behavior from an inference or proposal. If a gate fails, fix it before dependent work. A missing environment or service may leave a gate unverified; make the limitation explicit and continue independent work. Honor the user's existing publish, push, and deployment boundaries.

## 0. Inspect and frame

**Purpose:** Identify the smallest useful outcome and constraints before prescribing an interface.

- Read repository instructions, existing routes, package manifests, design tokens, components, and available tests. Inspect the running interface if possible.
- Determine whether the task is a new application, redesign, component, audit, or blueprint only.
- Define the primary user, their task, entry point, desired result, and failure or recovery path. Use supplied evidence; label assumptions.
- Record source-of-truth data, authentication and permission constraints, available integrations, and prototype versus working-product scope.
- Reuse supplied brand references and explicit preferences. Ask only for a missing choice that blocks the next useful action; resolve routine implementation choices yourself.
- Define observable acceptance checks before building. For example: a user can find a record, open it, save a valid edit, and recover from a failed save.

**Gate:** A short task brief states what success looks like, how it will be checked, and which dependencies are unavailable. Do not equate an account connection or a polished mockup with a completed user task.

## 1. Blueprint and design foundations

**Purpose:** Establish a coherent implementation contract without prematurely coding the application.

- Choose a stack appropriate to the deployment environment, existing repository, rendering needs, interaction complexity, and maintenance burden. State the decisive reasons and relevant tradeoff.
- Propose a modular folder structure based on the actual stack; distinguish UI, domain logic, data access, shared tokens, and tests where useful.
- Define navigation, page hierarchy, primary task flow, responsive behavior, and component reuse before detailing decoration.
- Create or carefully merge the design section of `AGENTS.md`; preserve unrelated instructions. Use the supplied template as a starting point.
- Establish named color, typography, spacing, radius, elevation, focus, and motion tokens. Start with an 8px rhythm and a 4px half-step; allow documented exceptions such as borders, text metrics, and target dimensions.
- Derive a palette from the brand or selected references and test required contrast. Do not prohibit a color combination merely because it is conventional.
- Set readable line heights, intentional long-text behavior, hierarchy, and density appropriate to the task. Dense comparison work may need compact tables; every dashboard need not be a card grid.
- Plan mobile layouts with defensive gutters. A comparison table may remain horizontally scrollable within a labeled region rather than lose meaning by becoming cards.
- Define primary, secondary, and tertiary action treatments; semantic forms; clear focus; and non-color error identification. An icon can help but never replaces an error explanation.

**Gate:** The brief, stack, structure, flow, tokens, and project constraints form one consistent blueprint. A blueprint-only request stops here. In a build request, use the blueprint to begin the shell without asking the user to repeat authorization.

## 2. Responsive application shell

**Purpose:** Make orientation and navigation work across screen sizes and input methods.

- Implement only the required shell: header, sidebar or navigation, content region, and mobile navigation behavior.
- Use semantic landmarks, a skip link where useful, descriptive page titles, and correct current-location indication.
- Provide active, hover, and visible keyboard-focus states. Sticky UI must not hide focused controls or reading content.
- Ensure collapsing navigation does not leave invisible elements keyboard-focusable. Use button semantics and expanded-state attributes for toggles.
- Test widths of 320px, 375px, and a representative desktop size; inspect intermediate widths where layout changes.
- Choose content-driven breakpoints; prevent page-level horizontal scrolling while retaining deliberate overflow for meaningful tables or diagrams.
- Maintain access to essential actions on mobile. Avoid hiding a primary task behind unexplained icon-only navigation.

**Gate:** Navigation, content access, focus order, and mobile open/close behavior work in the actual rendered shell. Record observed widths and any unavailable browser checks.

## 3. Components and a useful vertical slice

**Purpose:** Complete one real task before expanding the component inventory.

- Build the highest-priority component inside the shell, then connect enough related UI and data behavior to complete its task.
- Reuse tokens and established primitives. Introduce a shared abstraction only when actual repetition or a stable contract warrants it.
- Include loading, empty, validation, error, disabled, and success states that apply to the component. Keep labels and recovery actions concrete.
- Use native controls where possible; follow the semantics and keyboard contract of a custom widget when one is necessary.
- Aim for 44×44 CSS-pixel touch targets for frequent mobile controls; document deliberate compact exceptions and applicable target-size requirements.
- Handle long strings, missing fields, large values, duplicate labels, and realistic data volume. Keep essential content readable; provide access to full text when truncating it.
- Prevent duplicate mutations, retain recoverable user input, and guard against stale requests overwriting newer results.
- Treat a successful operation as confirmed by the authoritative service, with any optimism reconciled afterward. Label mock data and do not simulate a connected integration's success.

**Gate:** Demonstrate the user's task end to end using available data. Test the relevant failure path as well as the happy path. Repeat this stage for the next necessary feature, not for speculative features.

## 4. UX friction and accessibility audit

**Purpose:** Find barriers through real interaction, not a checklist assertion of compliance.

- Inspect hierarchy, labels, discoverability, feedback, unnecessary steps, and whether actions match the user's intent.
- Check text and non-text contrast, visible focus, zoom, reflow, target size, and information conveyed without color alone.
- Navigate with the keyboard. Use each widget's expected keys: ordinary links and buttons remain in normal Tab order; custom composite widgets may require arrow keys.
- Audit forms for accessible labels, instructions, field-associated errors, validation timing, and a sensible focus destination after failure or success.
- For modal dialogs: provide an accessible name, move focus appropriately, contain focus while open, make background interaction unavailable, and return focus to the invoking element when feasible.
- Support Escape when dismissal is safe. Do not silently discard an unsaved task to satisfy a generic shortcut rule.
- Test long unbroken strings, translated or enlarged text, overflow, empty data, permission restrictions, slow responses, and touch interaction.
- Use automated accessibility checks where available, then manually inspect keyboard and screen-reader behavior. Automated checks alone cannot establish WCAG conformance.

**Gate:** Fix material barriers in the implementation. Report remaining failures or untested criteria accurately; do not label the whole application compliant after a contrast-only audit.

## 5. Loading, empty, error, and transition states

**Purpose:** Explain what is happening and give the user a useful next action.

- Reserve geometry during loading. Use skeletons only when they clarify the expected structure; a brief progress indicator may better fit an action.
- Give prolonged waits an honest status and appropriate recovery; avoid endless skeletons or treating a timeout as proof that server work was canceled.
- Avoid announcing every skeleton element to assistive technology. Expose meaningful busy state and completion feedback without repeated noise.
- Distinguish first-use emptiness, no results after filtering, unavailable data, denied access, and a genuine failure. Each needs its own explanation and action.
- Preserve useful existing content during background refresh when appropriate; communicate stale or refreshing status.
- Show validation errors close to the relevant input and keep important operation errors available until resolved or dismissed.
- Use toasts for supplemental status. Auto-dismiss duration depends on message length and importance; persistent errors and messages needing action must remain accessible.
- Ensure toasts can be dismissed, do not cover essential controls, and use suitable live-region urgency. Do not move focus merely to announce a toast.
- Allow retry where safe; make repeated submissions and competing request responses deterministic. Show success only after the real operation succeeds.

**Gate:** Exercise applicable transitions in the rendered interface, including a slow request, no result, failure, retry, and confirmed success. Verify that user input survives a recoverable error.

## 6. Purposeful motion

**Optional:** Add motion only when it explains a state change, gives feedback, or improves orientation.

- Prefer small, fast transitions on opacity or transforms. Keep timing and easing in shared tokens.
- Use restrained button press feedback without shifting neighboring layout or delaying interaction.
- Animate menus and dialogs without delaying focus management or making content unavailable during transitions.
- Stagger entry only when it aids comprehension; long lists and repeated refreshes should not require waiting through theatrical sequences.
- Respect `prefers-reduced-motion`; remove or simplify nonessential movement, shimmer, and scale effects.
- Preserve functionality when animation is disabled, interrupted, or unsupported. Do not use motion as the only status signal.

**Gate:** Verify ordinary and reduced-motion behavior. Existing flows remain responsive and usable without animation. Skip this stage when motion adds little value.

## 7. Measured performance

**Purpose:** Improve observed bottlenecks while preserving the interface's useful behavior.

- Capture a reproducible baseline: route, build mode, device or CPU/network profile, dataset size, cache state, tool, and measurements. Compare equivalent conditions after changes.
- Evaluate current Core Web Vitals: LCP, INP, and CLS. FID is obsolete as a Core Web Vital.
- Distinguish lab measurements from field data. A Lighthouse result cannot prove real-user INP or a passing field assessment; label proxies and missing field evidence.
- Reserve image, media, and async-content dimensions. Size assets for their display, choose suitable formats, and avoid unnecessary requests.
- Prioritize the likely LCP resource; do not lazy-load the main above-the-fold image merely to apply a general optimization rule.
- Split heavy charts, maps, editors, and seldom-used flows where measurement supports it. Avoid loading waterfalls or blank interactions created by excessive splitting.
- Investigate expensive event handlers, large renders, long tasks, and data processing that affect responsiveness.
- Remove genuinely unused CSS and unnecessary DOM structure without damaging semantics. Use virtualization only when actual scale justifies its accessibility and navigation tradeoffs.
- Check the production build for errors and obvious bundle regressions. Performance budgets should fit the product and its users.

**Gate:** Record before/after measurements and relevant tradeoffs. Claim only the improvement demonstrated; a production build or lower bundle size alone is not evidence of faster user interaction.

## 8. Keyboard shortcuts and advanced interaction

**Optional:** Add shortcuts for frequent tasks where their benefit exceeds discoverability and conflict costs.

- Document the shortcut map and expose cues where useful. Adapt modifier displays to platform conventions.
- Do not intercept typing in inputs, textareas, editable content, native selection controls, or an active IME composition.
- For global single-character shortcuts such as `/`, provide a way to disable or remap them, or make them active only when the relevant control has focus.
- Resolve conflicts with browser, operating-system, assistive-technology, and existing application shortcuts.
- Let Escape dismiss the appropriate topmost dismissible overlay; preserve unsaved work and return focus appropriately.
- Apply arrow-key or J/K navigation only to suitable widgets with a defined focus/selection model. Do not turn every ordinary list into a custom keyboard widget.
- Keep pointer, touch, and standard keyboard paths complete without shortcut use.

**Gate:** Verify shortcuts, editable fields, IME guards, overlay priority, disabled/remapped behavior, and focus restoration. Skip this stage when ordinary navigation is sufficient.

## 9. Safe persistence

**Optional:** Persist explicit preferences or drafts when continuity materially helps the task.

- Classify which state belongs in a URL, server account, memory, session storage, or local storage; do not put everything into local storage.
- Never persist passwords, tokens, sensitive personal data, or raw analytics payloads in browser storage. Treat persisted drafts according to their actual sensitivity.
- Guard browser APIs during SSR and handle unavailable storage, quota failures, malformed JSON, schema changes, and hydration consistency.
- Namespace keys by application, schema version, and identity where appropriate. Prevent one user's state appearing for another user on a shared device.
- Define expiry or TTL for drafts and a safe migration or invalidation policy. Expose reset or discard behavior where useful.
- Debounce draft writes appropriately and define conflicts with server edits or other tabs. Do not restore an old draft over a newer authoritative value without explanation.
- Clear only the submitted draft after authoritative success; failed submissions retain recoverable input. Clear identity-scoped state on logout or account change as required.
- Cancel or flush outstanding draft writes so a late debounce cannot recreate a cleared draft. Test this race as part of success cleanup.
- For themes, respect an explicit preference and handle the system default without a distracting hydration flash.

**Gate:** Verify refresh restoration, storage failure, version/expiry behavior, account changes, failed submission, and success cleanup. Document any excluded sensitive drafts.

## 10. Internationalization and formatting

**Purpose:** Separate meaning from the language and presentation used to display it.

- Extract all in-scope user-facing strings, including unique labels, validation, toasts, and accessible names, into the existing localization approach. Avoid introducing a large framework solely for a small interface.
- Use message-aware pluralization and interpolation rather than assembling sentences from separately translated fragments.
- Use `Intl` for locale-aware dates, numbers, units, and currencies. Locale selects formatting conventions; it does not determine the transaction's currency or a user's intended time zone.
- Keep currency codes explicit. Preserve the difference between an instant, a date-only value, and a scheduled local time; do not silently shift a calendar date across time zones.
- Define the source of locale and time-zone preference, fallbacks, and server/client consistency. Honor an explicit user preference.
- Allow text expansion and right-to-left layout when required; use logical CSS properties and avoid hard-coded assumptions about text direction.
- Do not imply translated content exists merely because strings were extracted. Label scaffolding and available translations accurately.

**Gate:** Exercise representative formatting, pluralization, expanded text, and applicable direction changes. Verify that currency and date meaning survive localization.

## 11. Resilience, telemetry, and error reporting

**Purpose:** Recover locally from faults and collect useful evidence within authorized data boundaries.

- Place error boundaries at meaningful feature boundaries in React or use the stack's equivalent. Provide a localized fallback, a safe recovery action, and a way to retain useful surrounding UI.
- React error boundaries do not generally catch event-handler errors, ordinary async failures, SSR errors, or failures inside the boundary itself. Handle those explicitly at their appropriate layer.
- Create separate centralized interfaces for product events and error reporting. Keep providers replaceable and default to a safe no-op until a provider and collection are authorized.
- Expose a typed `trackUserEvent(eventName, properties)` or equivalent adapter. Define the exact trigger, allowed payload, emission owner, permission condition, and evidence of receipt for each event.
- Define an allowlisted event schema: stable names, permitted properties, identity rules, schema version, and event deduplication where needed.
- Record actual user actions and authoritative conversions at the right time. Do not send raw form inputs, secrets, full URLs containing sensitive values, or unredacted exception context.
- Distinguish browser event emission, transport delivery, collector acceptance, and downstream platform receipt. Seeing a console call proves only that layer.
- Treat abandonment as an inference with a stated window and conditions; a closed tab or missed unload request alone does not prove intent or reliably deliver an event.
- Use semantic development diagnostics and redacted production collection. Reporting failures must never block the user's task or create recursive error loops.
- Respect the application's consent and privacy requirements. Adding a wrapper does not authorize installing a vendor, enabling tracking, or transmitting data.

**Gate:** Verify an isolated render fault, an async failure, recovery, no-provider behavior, redaction, and emission timing. State which receipt layers were actually observed.

## 12. Review and delivery

**Purpose:** Make the final result inspectable and accurately describe its practical limits.

- Check the priority flow against the original acceptance criteria and retest failures affected by the final changes.
- Run relevant existing checks and inspect rendered output where available. Focus new tests on meaningful user behavior and regression risk.
- Review responsive layout, keyboard use, important state transitions, and any optional capability actually introduced.
- Remove misleading placeholders, accidental debugging output, and unsupported capability claims. Clearly identify prototype data and unavailable integrations.
- Deliver complete integrated files or repository changes, a concise change summary, validation evidence, remaining limits, and the next useful action if work remains.
- Preserve source and configuration according to the project workflow. Prepare a concrete reviewable result before any approval genuinely required for publishing or deployment.

**Gate:** Every claimed outcome has evidence or a stated verification limit. A completed blueprint, a working prototype, and a verified production task are reported as different outcomes.


---

# Bundled file: references/verification.md

# Verification

## Contents

- Scope and result labels
- Pass/fail matrix
- Evidence record
- Release decision

## Scope and result labels

Set the success check before changing a component. Use the agreed primary task, existing project requirements, and applicable criteria; do not run every possible check on every small edit.

Record `pass`, `fail`, `not applicable`, or `unverified` for each applicable row. A source-code review, screenshot, automated scanner, and real interaction provide different evidence. Do not substitute one for another.

- `pass`: Observed behavior meets the stated check in the recorded environment and state.
- `fail`: Observed behavior misses the check; record the reproduction and correction.
- `not applicable`: The feature or condition is outside this change; record why.
- `unverified`: Applicable, but access, tooling, data, or time prevented a meaningful observation; record the gap.

These checks support an implementation review. Passing the matrix does not establish full WCAG conformance, security certification, production performance, or better conversion/adoption.

## Pass/fail matrix

Copy the applicable rows into the implementation report and replace each initial `unverified` value. Use synthetic records for edge cases and controlled test accounts for interactions.

| Check | Pass condition | Evidence to retain | Status |
| --- | --- | --- | --- |
| Primary task | User can complete the agreed task; labels, priority, navigation, and completion feedback match the task. | Task steps, observed outcome, environment. | unverified |
| Responsive shell | Agreed mobile, tablet, and desktop widths preserve access to navigation/actions; no accidental page overflow or obscured content. | Screenshots and interaction at representative widths, including 375px and 320 CSS px where applicable. | unverified |
| Reflow and zoom | Ordinary content works at 320 CSS px equivalent width and with text enlarged to 200%; necessary two-dimensional tables/maps scroll within their own region where practical. | Viewport/zoom settings; inspect content and actions, not only a screenshot. | unverified |
| Text spacing | No loss of content or functionality with line height 1.5, paragraph spacing 2em, letter spacing .12em, word spacing .16em applied together. | Override used and observed representative screens. | unverified |
| Long and awkward data | Long titles, names, URLs, translations, zero/large values, and many rows do not overlap or destroy hierarchy; necessary truncated content remains accessible. | Synthetic fixtures plus screenshot/interaction. | unverified |
| Semantic structure | Headings and landmarks communicate hierarchy; native links/buttons/form controls have correct names, labels, and roles. | DOM/accessibility-tree inspection on changed surfaces. | unverified |
| Keyboard operation | Primary task works without pointer input; Tab/Shift+Tab follow a logical sequence; buttons support Enter/Space; no unintended keyboard traps. | Walkthrough and recorded failures/fixes. | unverified |
| Modal/drawer focus | Modal opening places focus inside, background is inert, Tab stays inside, Escape dismisses the applicable top overlay, and closing restores logical focus; visible dismiss control exists. | Open/close/nested-overlay walkthrough. Mark nonmodal disclosures separately. | unverified |
| Keyboard shortcuts | Implemented shortcuts have visible equivalents; global single-character shortcuts can be disabled/remapped or are focus-scoped; editable targets/composition/native shortcuts remain usable. | Shortcut settings and focused/unfocused input cases. | unverified |
| Focus visibility | Focus indication remains visible and is not entirely hidden by author-created sticky elements/overlays; custom focus colors meet applicable non-text contrast. | Keyboard walkthrough and measured indicator colors. | unverified |
| Contrast and color | Normal text meets 4.5:1, large text 3:1; necessary component/state indicators and meaningful graphics meet applicable 3:1; color alone does not communicate meaning. | Measured foreground/background pairs, states, and documented exceptions. | unverified |
| Touch targets | Project's default 44×44 CSS px activation areas work on touch; any narrower targets meet applicable WCAG 2.2 AA 24×24/spacing exceptions and have a reason. | Activation-area measurements; nearby targets and inline-link exceptions. | unverified |
| Loading and refresh | Loading has honest feedback, stable geometry, and no false completion; refresh preserves useful prior data where appropriate; repeated submit is controlled. | Slow/failed request simulation and observed layout. | unverified |
| Empty and filtered states | First use, genuinely empty data, and no matching filter results have distinct helpful explanations and appropriate next actions. | Controlled records/filter states and CTA behavior. | unverified |
| Error and recovery | Validation identifies affected fields in text; request/auth/permission/offline errors expose appropriate recovery without losing valid input or claiming success. | Injected failures and recovery walkthrough; mark irrelevant failure classes not applicable. | unverified |
| Status messages and toasts | Assistive technologies receive appropriate status feedback; routine messages do not steal focus; required information/actions remain available after dismissal or timing is adjustable. | Live-region inspection, dismissal behavior, retained information/action. | unverified |
| Reduced motion | User's reduced-motion preference removes/reduces nonessential shimmer, entrances, scaling, and spring effects while preserving state feedback. | Browser preference simulation and interaction. | unverified |
| Persistence | Storage denied/full/corrupt/missing does not break the task; approved drafts/preferences restore correctly; specific draft clears only after confirmed success. | Failure simulations, reload, submission, and deletion cases. | unverified |
| Persistence privacy/lifecycle | Stored fields are intentional; no secrets/sensitive fields cached by default; account namespaces, expiry/schema handling, logout clearing, and cross-tab behavior fit the data. | Storage inspection and account-switch/logout/expiry cases. | unverified |
| Locale semantics | User-facing strings are extractable; approved locale formats values; business currency/units/time-zone/date-only meanings stay correct; longer text and RTL work if in scope. | At least two representative locale cases and boundary dates/amounts; explicit defaults. | unverified |
| Rendering/async isolation | Meaningful region failures show recovery; event/network/async failures have explicit handling; collector failures do not crash the UI. | Injected render and async errors; React boundary limitations recorded. | unverified |
| Performance in lab | Relevant assets reserve space; critical content is not needlessly delayed; measured bottlenecks are addressed; agreed lab budgets hold in a recorded device/network simulation. | Build/bundle result, trace or lab report with settings. | unverified |
| Performance in field | If real-user evidence exists, LCP ≤2.5s, INP ≤200ms, CLS ≤0.1 at p75, evaluated separately for mobile/desktop; otherwise remain unverified. | Dated field window, population/sample, segment, collector/source. A page-load Lighthouse score is insufficient. | unverified |
| Telemetry emission | Only authorized instrumentation activates; central events reflect actual outcomes, avoid duplicate firing and sensitive payloads, and tolerate consent/collector failure. | Browser event/network observation and inspected test payload. | unverified |
| Telemetry receipt | Where access exists, the destination received the intended event once with correct properties; browser emission alone does not prove receipt or downstream attribution. | Destination test-event/query result and matching safe identifier/time. | unverified |
| Required project checks | Existing mandatory build/type/lint/tests relevant to the change pass; required commands come from project configuration/instructions rather than invention. | Exact commands, exit results, relevant existing test coverage, unavailable checks. | unverified |

## Evidence record

For each material finding record: check; intended behavior; observed result; status; route/component; viewport or device; data/state; reproduction; evidence path; applied correction; retest result. Avoid retaining secrets or real personal data in screenshots/logs.

Report observed facts, inferred causes, proposed work, applied work, and verified results separately. An inaccessible dependency is a verification gap, not a pass. Do not mark a task successful because the account connection, scaffold, or configuration exists.

## Release decision

Fix failures that block the agreed task or required project checks; retest the original behavior and the affected recovery path. Broaden testing only for new changes, failures, or unresolved concerns. Summarize remaining unverified checks and their practical limits.

Implementation verification does not authorize deployment, a production mutation, a push, or analytics activation. Follow the user's existing operating boundaries and platform workflow; do not invent an extra approval checkpoint when the session already authorizes the action.


---

# Bundled file: references/service-design.md

# Service design for useful interface work

## Provenance and limits

This is an original application of Scott E. Sampson's *Essentials of Service Design
and Innovation*, fourth edition, supplied by the user as
`ESDI-4E_Chapters_1-6 (1).pdf`. The supplied PDF has 70 pages and ends at printed
page 56. For Arabic printed pages, PDF page = printed page + 14.
References below identify printed pages first, then PDF pages. The source
presents Process Chain Network (PCN) analysis. This file adapts its
concepts to interface work; frontend prescriptions are our extensions.

## Begin with one useful customer task

Identify the user's priority task, the event that starts it, and evidence that it
has succeeded. Include preparation before the UI and necessary work afterward.
Analyze a bounded process segment; subdivide complex journeys. A process with
roughly 10–20 steps is a manageable audit scope, not a required UI step count.
Source: pp. 30–31, 54 / PDF pp. 44–45, 68.

Use the user's judgment for intended success, business ambiguity, and operating
boundaries. Discover mechanical details yourself. Draft the task and assumptions
for correction, then deliver an early useful result appropriate to the request.
Do not turn every small component edit into a research or configuration exercise.

## Map resources, control, and dependencies

Service processes depend on participant resources: effort, information,
belongings, and sometimes the participants themselves. Customers supply inputs
as well as receive outputs. Source: pp. 12–15 / PDF pp. 26–29.
Record who controls each step and who supplies each required resource. Include
operators, partners, and downstream beneficiaries when they affect success.
In B2B work, the immediate customer's customer may matter.
Source: pp. 24–31 / PDF pp. 38–45.

| Step: action + object | Actor/controller | Required input and owner | Prerequisite state | Benefit | Effort/wait | Failure point | Evidence |
|---|---|---|---|---|---|---|---|
| Confirm appointment | Customer; provider validates availability | Selected slot; provider | Slot available; required details accepted | Reserved time | Form completion; response wait | Slot unavailable | Observation or labeled hypothesis |

Adapt this responsibility table to the task. For implementation, add the UI/system
response, handoff recipient, recovery path, and evidence of completion.
An interface transition or submitted request is not proof the next actor completed
their work. Expose pending approvals, external delays, and handoff status.

## Preserve the meaning of PCN

PCN steps use action verbs. Position assigns the actor and region; arrows express
state dependencies, not necessarily transfers of material or information.
A process domain contains steps an entity initiates, leads, or controls.
Source: pp. 18, 21–22, 24 / PDF pp. 32, 35–36, 38.

- Direct interaction: people interact with people across entities.
- Surrogate interaction: an entity acts on another entity's information,
  belongings, or technology without interacting with that person.
- Independent processing: an entity acts on its own controlled resources.

Source: pp. 24–29 / PDF pp. 38–43. Using a provider's website is surrogate
interaction in this framework. A UI/server swimlane diagram or the table above
is an adapted UX map; call it a PCN diagram only if it preserves PCN grammar.

## Separate preparation from realized benefit

Co-production creates value potential through participants' contributions.
Realized benefit occurs when the resulting resource satisfies a need, often
later in the customer's own activities. The source cautions that co-creation
can conflate these moments. Source: pp. 36–37 / PDF pp. 50–51.
In UX work, connected accounts, completed setup, or generated output can be
preparation; do not assume the intended benefit follows. An output can itself
satisfy a need. Define the actionable result or verified improvement that matters.

## Reduce effort while preserving useful control

Assess value for the chosen customer segment. Necessary steps can lack direct
customer value; waiting, uncertainty, confusion, and effort are real costs.
Source: pp. 40–44, 55–56 / PDF pp. 54–58, 69–70.
Remove unnecessary work; explain essential work; simplify, assist, or automate
demanding work. Compare self-service with assistance using required skill,
resources, effort, customization, control, and provider cost. Moving work to
customers can improve provider efficiency while increasing customer burden.
Source: pp. 47–52 / PDF pp. 61–66. Fewer steps alone do not establish better UX.

## Audit with evidence and define recovery

For redesigns, ask customers and operators to describe the process, identify
valued steps, and explain inconvenient, confusing, difficult, or failure-prone
steps. Record branches and waiting; let participants correct the sequence.
Compare perspectives, preserve unresolved differences, label hypotheses, and
repeat the audit after changes. Source: pp. 53–56 / PDF pp. 67–70.
The supplied chapters introduce fail points and error prevention; detailed service
recovery belongs to later chapters not provided. Draft preservation, safe retries,
duplicate prevention, cancellation, rollback, escalation, and recovery copy are
uxblueprint engineering extensions. Specify them when the workflow needs them;
verify recovery behavior rather than claiming the source mandates these mechanisms.


---

# Bundled file: references/prompt-sequence.md

# Guided prompt sequence

## Contents

- 1. Blueprint and tech stack
- 2. Responsive shell
- 3. Component and useful flow
- 4. UX friction and accessibility audit
- 5. Defensive states
- 6. Purposeful motion
- 7. Performance
- 8. Keyboard shortcuts
- 9. Safe persistence
- 10. Internationalization
- 11. Resilience and telemetry
- 12. Review and delivery

Use these prompts one at a time for guided work. Replace bracketed values with the application or component. Invoke `$uxblueprint` by name when available; otherwise ask the agent to read this skill's `SKILL.md` first. A build request may authorize the applicable stages together.

For an existing project, begin with inspection and enter at the relevant stage. Optional stages are justified by the task, not automatically added to every app. Carry decisions and evidence forward; do not make the user repeat the brief.

## Prompt 1. Blueprint and tech stack

```text
Use uxblueprint in guided mode for [application idea or existing project].
Act as the frontend architect and UX designer. Inspect project instructions,
available code, references, and integrations. Define the primary user task and
observable success. Do not write application code yet. Recommend a suitable
stack and modular folder structure; create or merge AGENTS.md with named design
tokens, an 8px rhythm with a 4px half-step, accessible typography and focus,
purposeful density, and mobile behavior. State assumptions and dependencies.
```

## Prompt 2. Responsive shell

```text
Use uxblueprint to implement the agreed application shell. Build semantic
navigation, a content region with defensive gutters, and accessible mobile
open/close behavior. Include current, hover, and visible focus states. Inspect
320px, 375px, and desktop layouts. Deliver integrated files and verified behavior.
```

## Prompt 3. Component and useful flow

```text
Use uxblueprint to build [component/feature] inside the shell. Follow established
tokens and primitives. Complete [user task] using the available data/service;
label any mock data. Include applicable loading, empty, validation, failure, and
success states, readable long content, usable touch targets, and request-race
and duplicate-submission handling. Verify the real success and recovery paths.
```

## Prompt 4. UX friction and accessibility audit

```text
Use uxblueprint to audit the implemented flow and fix demonstrated barriers.
Inspect hierarchy, labels, long text, reflow, contrast, keyboard use, form errors,
and custom-widget semantics. For dialogs verify focus entry, containment,
background isolation, safe dismissal, and return. Combine available automated
checks with manual interaction; report evidence and untested criteria.
```

## Prompt 5. Defensive states

```text
Use uxblueprint to finish missing transition states. Reserve loading geometry;
choose skeletons only where helpful. Distinguish first use, filtered-out results,
missing data, denied access, and failure. Preserve recoverable input and support
safe retry. Add accessible supplemental toasts if useful; keep consequential
errors and action messages available. Verify slow, empty, failed, and successful
operations without substituting simulated success for real integration.
```

## Prompt 6. Purposeful motion — optional

```text
Use uxblueprint to add restrained motion where it clarifies feedback or change.
Apply shared timing tokens to relevant controls, menus, and dialogs. Add entry
stagger only when useful. Honor reduced-motion preferences and keep focus,
interaction, and functionality correct with animation disabled or interrupted.
```

## Prompt 7. Performance

```text
Use uxblueprint to measure and improve frontend performance. Capture a
reproducible baseline and compare equivalent production-build conditions.
Evaluate LCP, INP, and CLS; distinguish lab proxies from field evidence. Fix
measured asset, layout, interaction, rendering, or bundle bottlenecks. Preserve
the likely LCP resource's priority. Report before/after results and tradeoffs.
```

## Prompt 8. Keyboard shortcuts — optional

```text
Use uxblueprint to add shortcuts for [frequent tasks]. Show discoverable cues,
avoid typing and IME conflicts, and offer disable/remap or focus-only activation
for single-character shortcuts. Define overlay dismissal and focus restoration.
Use arrows/J/K only for appropriate widgets. Verify ordinary input still works.
```

## Prompt 9. Safe persistence — optional

```text
Use uxblueprint to persist [explicit preferences/non-sensitive drafts]. Select
the right storage layer. Handle SSR, failures, schema versions, identity changes,
expiry, conflicts, and reset. Exclude secrets and sensitive inputs. Restore useful
state after refresh and clear a submitted draft only after authoritative success.
```

## Prompt 10. Internationalization

```text
Use uxblueprint to prepare the interface for [required locales]. Extract strings
using the project's localization approach and handle plurals and text expansion.
Use Intl with explicit currency and correct date/time meaning. Define locale,
time-zone, and fallback behavior. Test applicable direction and formatting;
distinguish translation scaffolding from actual available translations.
```

## Prompt 11. Resilience and telemetry

```text
Use uxblueprint to isolate runtime faults and handle async/action failures.
Provide localized recovery UI. Create separate no-op-by-default product-event
and error-reporting adapters with allowlisted schemas and redaction. Connect an
external provider only within existing authorization and consent requirements.
Verify event timing and distinguish emission, transport, and platform receipt.
Treat abandonment as an explicitly defined inference. Collector failure must
never block the user's task.
```

## Prompt 12. Review and delivery

```text
Use uxblueprint to verify the original acceptance criteria and deliver the work.
Check relevant responsive layouts, keyboard behavior, failures, and introduced
capabilities. Run appropriate project checks. Give complete integrated changes,
validation evidence, known limits, and any concrete next step. Honor the project's
push, publish, and deployment boundaries.
```


---

# Bundled file: references/sources.md

# Sources and corrected defaults

## Contents

- Provenance
- Technical sources
- Corrections to the supplied blueprint
- Evidence boundaries

## Provenance

Checked: 2026-10-14. Official technical sources below were opened and inspected on that date. Recheck version-sensitive documentation when implementation depends on a newer framework or changed browser behavior.

The user supplied **Codex UI/UX Design & Engineering Blueprint**, a staged prompt framework spanning foundations, shell, components, friction audit, defensive states, motion, performance, shortcuts, persistence, internationalization, and telemetry. It is the workflow source, not evidence that its defaults establish production quality or accessibility conformance.

The user also supplied **Scott E. Sampson, Essentials of Service Design and Innovation, fourth edition, January 2015**, Chapters 1–6. Supplied file: `ESDI-4E_Chapters_1-6 (1).pdf`; chapter span: printed pp. 1–56, PDF pages 15–70. Use original synthesis and page-level attribution; do not bundle the book, reproduce its chapters, or imply that it establishes frontend standards. Service-process and co-production concepts inform task/outcome analysis and customer participation; their application to conversational setup is an interpretation, not measured evidence of adoption or delight.

## Technical sources

- WCAG 2.2 normative requirements and conformance framework: https://www.w3.org/TR/WCAG22/
- Text contrast minimum, including large-text exceptions and non-rounded thresholds: https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum.html
- Contrast of necessary component/state indicators and meaningful graphics: https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast.html
- Reflow at 320 CSS px equivalent width and scoped exceptions for necessary two-dimensional content: https://www.w3.org/WAI/WCAG22/Understanding/reflow.html
- Adapting to user text-spacing overrides without content/functionality loss: https://www.w3.org/WAI/WCAG22/Understanding/text-spacing.html
- WCAG 2.2 AA minimum pointer targets, 24×24 CSS px and exceptions: https://www.w3.org/WAI/WCAG22/Understanding/target-size-minimum.html
- WCAG AAA enhanced pointer targets, 44×44 CSS px and exceptions: https://www.w3.org/WAI/WCAG22/Understanding/target-size-enhanced.html
- Visible keyboard-focus indication: https://www.w3.org/WAI/WCAG22/Understanding/focus-visible.html
- AA rule against author-created content entirely hiding the focused component: https://www.w3.org/WAI/WCAG22/Understanding/focus-not-obscured-minimum.html
- AAA focus-indicator area and focused/unfocused contrast: https://www.w3.org/WAI/WCAG22/Understanding/focus-appearance.html
- Off/remap/focus-only options for single-character keyboard shortcuts: https://www.w3.org/WAI/WCAG22/Understanding/character-key-shortcuts.html
- Adequate time, adjustable timing, and temporary-toast alternative example: https://www.w3.org/WAI/WCAG22/Understanding/timing-adjustable.html
- Programmatically available status feedback without changing focus: https://www.w3.org/WAI/WCAG22/Understanding/status-messages.html
- Textual identification of automatically detected input errors: https://www.w3.org/WAI/WCAG22/Understanding/error-identification.html
- Avoiding color as the sole means of communication: https://www.w3.org/WAI/WCAG22/Understanding/use-of-color.html
- AAA criterion for disabling nonessential interaction-triggered animation: https://www.w3.org/WAI/WCAG22/Understanding/animation-from-interactions.html
- Modal dialog semantics, inert background, opening/return focus, Tab containment, and Escape: https://www.w3.org/WAI/ARIA/apg/patterns/dialog-modal/
- Listbox selection semantics, keyboard behavior, and limitations on interactive descendants: https://www.w3.org/WAI/ARIA/apg/patterns/listbox/
- Button naming, action semantics, Space/Enter activation: https://www.w3.org/WAI/ARIA/apg/patterns/button/
- Choosing the correct accessible widget pattern: https://www.w3.org/WAI/ARIA/apg/patterns/
- Core Web Vitals, LCP/INP/CLS thresholds, p75 segmentation, and lab-versus-field limits: https://web.dev/articles/vitals
- Platform preference for removing/reducing/replacing nonessential motion: https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/At-rules/@media/prefers-reduced-motion
- localStorage lifetime, origin scope, private sessions, and SecurityError: https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage
- Synchronous Web Storage operations and session behavior: https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API
- Storage quotas, persistence/eviction behavior, and error handling: https://developer.mozilla.org/en-US/docs/Web/API/Storage_API/Storage_quotas_and_eviction_criteria
- Language-sensitive number formatting with explicit currency/unit options: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat
- Language-sensitive date/time formatting and explicit time-zone options: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat
- React rendering-error boundaries and exclusions for ordinary event handlers, most async callbacks, SSR, and errors in the boundary itself; current transition-function exception: https://react.dev/reference/react/Component#catching-rendering-errors-with-an-error-boundary

WCAG Understanding documents explain the normative success criteria. WAI-ARIA APG supplies implementation patterns; matching one pattern does not establish full WCAG conformance. MDN and framework documentation describe platform behavior, not product-specific quality guarantees.

## Corrections to the supplied blueprint

| Original default | Skill treatment | Basis |
| --- | --- | --- |
| LCP, FID, CLS | Use LCP, INP, CLS; good thresholds 2.5s, 200ms, .1 at field p75 by mobile/desktop. | Current official Core Web Vitals guidance. |
| Test to 375px | Include 375px product review and 320 CSS px reflow equivalent, plus appropriate zoom/text enlargement. | WCAG reflow plus project choice. |
| Every grid becomes one column | Reflow ordinary content; preserve necessary table/map/grid relationships with scoped scrolling. | WCAG exception is content-specific. |
| All targets at least 44×44px | Keep a 44×44 CSS px touch default; accurately distinguish AA's 24×24/spacing rule from enhanced AAA. | Stronger project choice plus standard. |
| Tab and Enter are sufficient | Match widget keyboard semantics, including Space for buttons; test focus and logical navigation. | Native semantics/APG. |
| Focus traps must be eliminated | Eliminate unintended traps; intentionally contain modal focus and provide dismissal/return focus. | Modal APG pattern. |
| Global / and J/K shortcuts | Allow off/remap or focus-only scope; exclude editing/composition contexts and preserve ordinary controls. | WCAG shortcut requirement plus engineering precautions. |
| Every toast expires after four seconds | Expire only when equivalent information/action remains available or timing is adjustable; keep actionable recovery available. | Timing requirement plus recovery design choice. |
| Shimmer, stagger, spring on every component | Motion is optional and subordinate to task clarity, performance, and reduced-motion preference. | Platform guidance plus design judgment. |
| Never use black on white | Treat softer colors as aesthetic preference; validate actual contrast pairs. | No universal accessibility prohibition on black/white. |
| Strict eight-pixel spacing everywhere | Use the selected token scale with justified exceptions for borders, typography, activation areas, and optical alignment. | Consistency convention, not a WCAG rule. |
| Heading 1.2 and body 1.5 guarantee readability | Use as adjustable defaults; support required user-spacing overrides without loss. | Defaults are design choices; override resilience is AA. |
| An icon is mandatory for every error | Require clear associated error text and a non-color cue; icons can supplement it. | Error identification and use-of-color requirements. |
| Persist every draft locally | Cache approved nonsensitive fields; handle denied/full/corrupt storage, account isolation, expiry, and confirmed-success clearing. | API limitations plus privacy/lifecycle engineering choices. |
| System locale determines all formatting | Format for the approved locale; explicitly preserve business currency, units, date-only semantics, and chosen time zone. | Intl capability plus product data semantics. |
| Error boundaries catch every failure | Use meaningful rendering boundaries plus explicit event/async/network recovery. | Current React behavior. |
| A central tracker proves conversion measurement | Distinguish implementation, browser emission, platform receipt, and attributed results; activate only within authorization. | Evidence and operating-boundary discipline. |
| Premium polish means production-ready | Verify the actual task, recovery paths, applicable standards, project checks, and relevant real environments; expose gaps. | Engineering review policy, not an empirical claim. |

## Evidence boundaries

No source above supports universal conversion lift, customer delight, a mandatory palette/layout/style, or automatic production readiness. Project choices such as token discipline, restrained shadows, account-keyed drafts, scoped telemetry, and topmost-overlay dismissal are reasoned implementation defaults, not standards mandates.

Build telemetry wrappers so failures cannot crash the task, redact payloads, and keep live collection within the user's authorization. Browser evidence can prove an event was attempted/emitted; destination access is needed to verify receipt. Neither alone proves attribution or commercial impact.

Do not call an app WCAG-conformant or production-verified based solely on these references or an automated scan. State what was observed, the environment and states covered, and what remains unverified.


---

# Bundled file: assets/AGENTS.template.md

# UI/UX and frontend engineering constraints

Adapt this template to the project. Resolve bracketed fields before adopting it. Merge with applicable existing instructions; preserve unrelated requirements.

## Product and scope

- Primary user: [role and relevant constraints].
- Primary task and outcome: [action and observable result].
- Intended density and hierarchy: [what matters first; where detail belongs].
- References and brand source: [verified assets or supplied examples].
- Runtime and component system: [existing or selected versions and conventions].
- Release boundary: [authorized local, preview, repository, and production actions].

## Tokens and visual direction

- Direction: [task-specific layout and identity; avoid generic decoration].
- Semantic colors: [background, surface, text, muted text, primary, accent, border, focus, success, warning, error; include verified dark variants only if supported].
- Spacing: 4, 8, 16, 24, 32, 48, and 64px; extend with a named token only for a clear need. Use the 4px half-step within an 8px rhythm.
- Radii: [control, card, pill]. Default examples: 8, 12, 9999px.
- Elevation and layering: [surface shadows and z-index tokens]. Prefer restrained borders/elevation appropriate to hierarchy.
- Typography: [family, sizes, weights]. Start with heading line height 1.2 and body 1.5; adjust for font, size, language, and readability.
- Motion: [short duration/easing tokens]; provide reduced-motion behavior.
- Allow appropriate border/stroke/font metrics and fluid dimensions; spacing rules do not apply mechanically to every measurement.

## Responsive behavior

- Use mobile-first layout and content-driven breakpoints. Check 375px mobile, 320 CSS px reflow, representative tablet, and desktop widths.
- Keep edge padding, sticky offsets, and safe areas explicit.
- Preserve reading and task order. Use purposeful stacking, horizontal scrolling for genuinely two-dimensional content, or a task-specific mobile representation.
- Prevent accidental document overflow. Handle long titles, URLs, translations, and numeric values.
- Use deliberate text wrapping; use balanced headings where supported. Apply language-aware hyphenation only where appropriate. Do not truncate essential information without a usable full-value path.

## Components and accessibility

- Target WCAG 2.2 AA and record actual checks; a checklist alone does not prove conformance.
- Use native semantics or established tested primitives. Give controls accessible names and visible focus.
- Default touch hit areas to at least 44x44 CSS px; document any compact target and verify applicable AA target-size/spacing rules.
- Use primary filled, secondary outlined, and tertiary text actions when this hierarchy fits the product. Style hover, active, focus-visible, disabled, and busy states.
- Associate labels, instructions, and text errors with inputs. Use color plus text/shape, adding icons where useful.
- Implement modal focus containment/return and inert background; do not trap focus in ordinary disclosures or nonmodal popovers.
- Use statuses and announcements without moving focus unnecessarily. Keep essential errors and actionable notifications available.
- Represent loading, refreshing, empty, filtered-empty, partial, denied, failed, pending, and successful states as applicable.
- Preserve input and offer real recovery. Confirm success only after its completion condition is met.
- Support keyboard, touch, reduced motion, zoom/reflow, and relevant screen-reader tasks.

## Data and engineering

- Label synthetic data, sources, units, periods, filters, and freshness where relevant. Do not render missing data as zero.
- Treat backend records as authoritative. Document client state, URL state, eligible drafts, and preferences separately.
- Do not store secrets or sensitive drafts in localStorage by default. Guard storage failures, schema versions, identity separation, expiry, and cleanup.
- Guard shortcuts against typing/IME and follow the selected widget pattern. Make single-character shortcuts switchable, remappable, or focused in scope.
- Support localization contracts for locale, time zone, currency, units, and date-only versus instant values.
- Use isolated render fallbacks and explicit async error handling.
- Keep analytics behind a configured, authorized adapter with allowlisted payloads. Never collect raw sensitive inputs or claim browser emission proves ingestion.
- Measure performance before/after. Use LCP, INP, and CLS with current official thresholds; distinguish lab diagnostics from field results.

## Acceptance commands and evidence

- Required commands: [actual build, type, lint, and relevant test commands].
- Task checks: [priority successful path and consequential failure/recovery paths].
- Render checks: [viewport, interaction, contrast, zoom, motion, localization as applicable].
- Record every required check as pass, fail, not applicable, or unverified with evidence. State missing access or tools explicitly.
