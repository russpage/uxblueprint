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
