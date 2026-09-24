# Coding agent rules

Agent-neutral, gender-neutral plain-text rules with Markdown headings for AI coding agents. The general coding instructions apply across software types; the browser-specific instructions apply only to browser-delivered work and its supporting web endpoints.

## Install

These `.txt` files are source files, not filenames that every agent loads automatically. To apply the rules across all projects, copy and paste `global-coding-agent-rules.txt` into the agent's user-level `AGENTS.md` (where supported) or its equivalent global rules file. Add `web-development-rules.txt` for browser-delivered work, using scoped loading when supported or manual inclusion for relevant sessions.

To apply these rules only to one project, copy and paste the applicable content into that project's supported instruction file, such as its `AGENTS.md` or `CLAUDE.md`. Do not put project-only rules in a user-level file: user-level rules apply across projects. Keep the two source files separate for maintenance.

If an agent accepts only one always-loaded instruction file, combine both only when browser guidance must be available automatically; retain the headings and browser-applicability condition. Recognition, loading, and scope depend on the agent and file location; use its documented mechanism and confirm the instructions are loaded.

Preserve existing project instructions and resolve conflicts when merging. Avoid loading duplicate copies through global settings, project files, or imports. When both files are loaded, both occupy context even when the browser-specific section is inapplicable.

## Maintaining these rules

When revising instructions, merge duplicates and remove obsolete guidance rather than accumulating overlapping rules. Keep general policy in the global file and browser-specific behaviour in the web file; refer to shared policy instead of restating it. Check meaningful revisions on representative tasks with the agents and models the team actually uses, observing whether behaviour improves. Preserve explicit safety and approval boundaries even when one model usually follows them without a reminder. These checks guide rule maintenance, not every development task.

Keep file descriptions, installation details, and maintenance guidance here rather than in the loaded rules. Rules should give actionable instructions, not describe who does all the work or require a human-free workflow. Retain short applicability conditions where needed. Express general guidance in terms of capabilities and outcomes rather than a particular agent, model, operating system, shell, language, or framework. Keep project-specific commands, paths, conventions, and detailed procedures in project or nested instructions or relevant skills.

Write rules as direct instructions. Put conditions next to the actions they govern, state exceptions explicitly, and use consistent terms. Prefer clear natural language over conversational phrasing, compressed shorthand, or model-specific prompting syntax. Preserve policy meaning when changing wording; clearer prose alone does not establish improved adherence across models.

## Influences

These rules mainly reflect practical experience with coding agents. The sources below contributed specific guidance that remains in the files; other material reviewed during drafting is not listed.

- Lauren Tan's [pstack article](https://x.com/poteto/article/2094457600259842065) and [verification-skill pattern](https://github.com/cursor/plugins/blob/main/pstack/skills/create-verification-skill/SKILL.md) shaped the emphasis on direct evidence and reusable verification for important recurring work.
- Ansh Nanda's [testing discussion](https://x.com/anshnanda/status/2101627891721371971) informed the requirement for meaningful tests with expected results independent of the implementation, without adopting an E2E-only policy.
- Matt Pocock's [tracer-bullet approach](https://www.aihero.dev/tracer-bullets) informed the small end-to-end path for unfamiliar multi-component features.
- Addy Osmani's [Brownfield Agentic Engineering](https://addyosmani.com/blog/brownfield-agentic-engineering/) informed the rules to establish existing behaviour before refactoring and preserve safeguards and consumer compatibility during replacement.
- [AWS's secure agentic development guidance](https://docs.aws.amazon.com/prescriptive-guidance/latest/agentic-ai-security/best-practices-dev-practices.html) and OWASP's [input-validation](https://cheatsheetseries.owasp.org/cheatsheets/Input_Validation_Cheat_Sheet.html), [injection-prevention](https://cheatsheetseries.owasp.org/cheatsheets/Injection_Prevention_Cheat_Sheet.html), and [CSRF-prevention](https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.html) guidance informed the trust-boundary and web-security rules.
- Jad Joubran's [Baseline article](https://www.smashingmagazine.com/2026/08/how-baseline-can-help-ship-less-javascript/) informed the browser-support decision rule without replacing project-specific compatibility requirements.

## Licence

MIT. See `LICENSE`.
