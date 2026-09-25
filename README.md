# Coding agent rules

These Markdown rules help coding agents work on software projects without assuming a particular agent, model, operating system, or tech stack. They aim to reduce repeated prompting and rework without mandating unnecessary checks. They are not general-purpose assistant instructions or a substitute for project-specific coding standards.

- [General software-project instructions](global-coding-agent-rules.md) cover task scope, approvals, research, implementation, security, verification, and communication across software projects.
- [Browser-specific instructions](web-development-rules.md) add browser behaviour, compatibility, web security, and rendered verification for browser-delivered work and its supporting web endpoints.

## How to use

Copy or adapt the relevant rules into your agent's user-level or project instructions; cloning this repository does not load them. Use the general rules for software work, and add the browser-specific rules where applicable. The files are separate here for maintenance and can be combined in one instruction file.

Merge duplicate instructions and resolve conflicts with rules already in place. For teams, keep the shared baseline in version-controlled project instructions rather than relying on each developer's user-level setup. Confirm each agent loads the project instructions; use project checks to enforce mechanical requirements. If you do not want browser guidance loaded during unrelated work, add it only to web projects. For placement details, see the official instructions for [Cursor](https://cursor.com/docs/rules), [Codex](https://developers.openai.com/codex/guides/agents-md), [Claude Code](https://code.claude.com/docs/en/memory), or your chosen agent.

## Contributing

Issues and pull requests are welcome. Explain the problem your suggestion solves and why it belongs in the general or web rules rather than project instructions.

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
