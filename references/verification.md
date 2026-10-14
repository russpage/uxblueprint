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
