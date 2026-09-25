# Browser-specific instructions

## Scope

  * Apply this browser-specific section only to browser-delivered content or behaviour and its supporting web endpoints, regardless of rendering architecture, including embedded browser interfaces.
  * Treat the project's supported browsers and devices, accessibility targets, performance budgets, SEO requirements, rendering architecture, design system, and product behaviour as constraints.
  * Before adopting a browser capability or removing a fallback, establish browser and embedded-runtime support requirements from project instructions, configuration, and available audience evidence. Check current compatibility against those requirements. Use Baseline status as evidence, not as a replacement for the project's policy. If no policy exists and the choice materially affects compatibility, propose a target for approval.

## Browser foundations

  * Prefer semantic HTML and native browser elements before custom replacements. Preserve expected links, forms, focus, selection, copy and paste, autofill, URLs, reload, history, and zoom unless the product intentionally changes them. Keep required content and actions usable across supported viewports, text sizes, and input methods, with accessible names, keyboard operation, visible focus, meaningful feedback, and non-text alternatives.
  * For new or changed layout, prefer flexible, content-driven sizing with appropriate bounds over hard-coded viewport or text-length assumptions. Let components and media adapt to their available space; avoid fixed text-container heights that clip expanded content. Preserve intentional fixed dimensions and physical positioning where required by the design or behaviour; do not turn a scoped change into an unrelated responsive redesign.
  * Prefer CSS logical properties and direction-relative values when layout should follow content direction, even in single-language projects, subject to the browser-support policy. Declare content language and direction appropriately in HTML and isolate mixed-direction dynamic text where needed. Do not mechanically replace intentional physical directions or treat these defaults as proof of complete RTL support.
  * Feature-detect optional browser capabilities, provide fallbacks for essential tasks, and let non-essential enhancements degrade safely within the project's support policy. Do not impose a no-JavaScript requirement when the intended architecture requires JavaScript.
  * For styling defects, inspect computed styles and relevant cascade, inheritance, layout, overflow, and stacking contexts before changing declarations. Avoid escalating specificity, adding !important, increasing z-index, or hiding overflow merely to conceal an unexplained problem. Keep selectors scoped to their intended consumers; when changing shared styles, verify representative affected components and pages.

## State and resilience

  * Handle the relevant initial, loading, empty, success, validation, permission, failure, slow-network, offline, retry, and cancellation states for affected data flows. Preserve recoverable user input and make the next action clear.
  * For browser flows, account for refreshes, restorations, backgrounding, and expired sessions. Do not rely solely on page-close events or uninterrupted background execution to preserve required state; revalidate restored state when freshness affects correctness or access.

## Web security and privacy

  * Use browser validation for usability, not backend enforcement. Do not rely on client-side routing, hidden controls, or interface visibility to enforce permissions. Do not send protected data and rely on client code or presentation to conceal it.
  * For state-changing requests using cookies or other automatically attached credentials, enforce server-side CSRF protection. Configure cross-origin access deliberately. Do not use CORS as authentication or as a complete CSRF defence. Preserve required cross-origin integrations and verify that unintended origins cannot perform protected actions.
  * Keep secrets out of client-delivered code. Avoid unnecessary personal or sensitive data in URLs, browser storage, analytics, client-visible errors, or rendered markup.
  * For URLs derived from untrusted data, validate allowed schemes and destinations before using them for navigation, redirects, embeds, or resource loading; escaping and CSP do not replace URL validation.
  * Set caching deliberately for personalised or sensitive responses. Prevent shared or unintended caches from exposing one user's data to another, and verify that cached variants remain separated when identity, role, tenant, or permission affects the response.
  * When Content Security Policy is applicable, make the narrowest necessary policy change, avoid broad exceptions without justification, and verify the policy on the rendered response.

## Browser verification

  * Identify affected routes, states, viewports, input methods, supported browsers, rendering modes, sessions, storage or cache, and network conditions. Select representative affected combinations according to risk and the project's support requirements; cover materially different behaviour rather than every possible combination. For changes to consent-dependent features or third-party integrations, include relevant denied-consent, blocked-resource, and unavailable-storage states; verify unrelated functionality remains usable and dependent features offer a clear recovery path where possible without bypassing user choices.
  * Use isolated, disposable browser state and controlled test data by default. Use real accounts or persistent browser profiles only when required and authorised.
  * When correctness depends on rendered output or interaction, use an available agent-operated browser to verify the affected entry point and state. Keep coverage focused on the change; expand routes, states, or browser coverage only when risk or project requirements warrant it. Inspect the rendered result and relevant console errors, failed requests, navigation, and persisted results.
  * Synchronise browser actions and assertions with observable state. Use bounded waits instead of arbitrary delays. Prefer structured page, console, and network evidence; capture screenshots or traces only when the claim or failure requires them.
  * When appearance can change, compare the affected visual output. For affected styling and interactions, verify relevant user settings such as reduced motion, forced colors, text enlargement, and supported themes; ensure content, controls, and focus indicators remain perceivable and usable. Do not infer accessibility from a responsive layout or automated checks alone. Do not infer cross-browser correctness from one browser.
