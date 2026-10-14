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
