# Browser-specific instructions

## Web scope and browser compatibility

  * Apply all browser-specific instructions only to authorised work on browser-delivered content or behaviour and its supporting web endpoints, regardless of rendering architecture, including embedded browser interfaces.
  * Treat the project's supported browsers and devices, accessibility targets, performance budgets, SEO requirements, rendering architecture, design system, and product behaviour as constraints.
  * Before adopting a browser capability with uncertain or limited support across project targets or removing a fallback, identify supported browsers and embedded runtimes from project instructions, configuration, or documented usage data. Check current compatibility; Baseline is evidence, not a replacement for project policy. If policy is missing and compatibility is materially affected, propose a target for approval.

## Browser behaviour, layout, and accessibility

  * Prefer semantic HTML and native browser elements before custom replacements. Preserve expected links, forms, focus, selection, copy and paste, autofill, URLs, reload, history, and zoom unless the product intentionally changes them. Keep required content and actions usable across supported viewports, text sizes, and input methods, with accessible names, keyboard operation, visible focus, meaningful feedback, and text alternatives for non-text content.
  * For new or changed layouts, prefer flexible, content-driven sizing with bounds over fixed viewport or text-length assumptions. Let components and media adapt to available space; avoid fixed text-container heights that clip expanded content. Preserve intentional fixed dimensions and physical positioning required by design or behaviour.
  * For layouts that follow text direction, prefer CSS logical properties and direction-relative values in new or changed styles, even in single-language projects. Follow existing project conventions and browser-support policy. Set the language and direction in HTML; isolate mixed-direction dynamic text when needed. These defaults do not prove complete RTL support. Do not mechanically replace intentional physical directions.
  * Use feature detection when capability availability can vary within supported environments and built-in browser fallback behaviour is insufficient. Provide fallbacks for essential tasks and let non-essential enhancements degrade safely within the project's support policy. Do not impose a no-JavaScript requirement when the intended architecture requires JavaScript.
  * Before fixing a styling defect, inspect relevant source evidence and, when browser access is available, computed styles or layout evidence needed to identify the cause. If browser access is unavailable, report what remains visually unverified. Do not conceal unexplained problems with specificity, !important, z-index, or hidden overflow. Scope selectors to intended consumers; verify representative affected components and pages after shared-style changes.

## Browser lifecycle and state recovery

  * For changes affecting client-side state, sessions, or lifecycle-dependent behaviour, account for refreshes, restorations, backgrounding, and expired sessions. Do not rely solely on page-close events or uninterrupted background execution to preserve required state; revalidate restored state when freshness affects correctness or access.

## Web security and privacy

  * Use browser validation for usability. When a server processes the data, enforce validation server-side regardless of browser checks. Do not rely on client-side routing, hidden controls, or interface visibility to enforce permissions. Do not send protected data and rely on client code or presentation to conceal it.
  * For state-changing requests using cookies or other automatically attached credentials, enforce server-side CSRF protection. Configure cross-origin access deliberately. Do not use CORS as authentication or as a complete CSRF defence. Preserve required cross-origin integrations and verify that unintended origins cannot perform protected actions.
  * Keep secrets out of client-delivered code. Avoid unnecessary personal or sensitive data in URLs, browser storage, analytics, client-visible errors, or rendered markup.
  * For URLs derived from untrusted data, validate allowed schemes and destinations before using them for navigation, redirects, embeds, or resource loading; escaping and CSP do not replace URL validation.
  * Set caching deliberately for personalised or sensitive responses. Prevent shared or unintended caches from exposing one user's data to another, and verify that cached variants remain separated when identity, role, tenant, or permission affects the response.
  * When Content Security Policy is applicable, make the narrowest necessary policy change, avoid broad exceptions without justification, and verify the policy on the rendered response.

## Browser verification

  * Identify only the dimensions a change can affect, such as routes, states, viewports, input methods, supported browsers, rendering modes, sessions, storage, caches, and network conditions. Test representative combinations by risk and project support requirements, covering materially different behaviour rather than every combination. For changes to consent-dependent features or third-party integrations, include relevant denied-consent, blocked-resource, and unavailable-storage states. In those failure states, verify other functionality within affected flows remains usable and dependent features offer a clear recovery path where possible without bypassing user choices.
  * Use isolated, disposable browser state and controlled test data by default. When changed UI depends on variable content, verify representative data extremes, such as empty values, long labels, or large lists within expected usage. Check that essential information remains distinguishable and controls remain usable. Use real accounts or persistent browser profiles only when required and authorised.
  * With parallel worktrees or local previews, confirm which checkout the preview serves before browser testing; do not assume a familiar host, port, or open tab points to the intended worktree.
  * When correctness depends on rendered output or interaction, use an available agent-operated browser to verify the affected entry point and state. Inspect the rendered result and relevant console errors, failed requests, navigation, and persisted results.
  * Synchronise browser actions and assertions with observable state. Use bounded waits instead of arbitrary delays. Prefer structured page, console, and network evidence; capture screenshots or traces only when the claim or failure requires them.
  * Compare affected visual output when appearance can change. For affected styling and interactions, verify settings the change can affect, such as reduced motion, forced colors, text enlargement, and supported themes. Keep content, controls, and focus indicators perceivable and usable. Responsive layouts or automated checks alone do not prove accessibility; one browser does not prove cross-browser correctness.
