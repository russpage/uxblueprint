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
