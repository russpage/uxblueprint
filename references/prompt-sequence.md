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
