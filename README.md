# Coding agent rules

These Markdown rules help coding agents work on new and existing software projects without assuming a particular agent, model, operating system, or tech stack. They aim to reduce repeated prompting and rework without mandating unnecessary checks. They are not general-purpose assistant instructions or a substitute for project-specific coding standards.

- [General software-project instructions](global-coding-agent-rules.md) cover task scope, approvals, research, implementation, security, verification, and communication across software projects.
- [Browser-specific instructions](web-development-rules.md) add browser behaviour, compatibility, web security, and rendered verification for browser-delivered work and its supporting web endpoints.

## How to use

Cloning this repository does not activate the rules.

1. **Choose the content.** Use the complete files or copy only the sections relevant to your needs: general rules for software work, plus web rules for browser-delivered work. The files are separate here for maintenance and can be combined in one instruction file.
2. **Choose where they apply.** Copy or adapt the rules into project instructions for one project, or your agent's user-level instructions for use across projects. For teams, keep the shared baseline in version-controlled project instructions rather than relying on each developer's user-level setup.
3. **Merge and check.** Merge duplicate instructions and resolve conflicts with rules already in place. Preserve any safety or approval conditions attached to the guidance you copy. Confirm each agent loads the instructions; use project checks to enforce mechanical requirements.

For placement details, see the official instructions for [Cursor](https://cursor.com/docs/rules), [Codex](https://developers.openai.com/codex/guides/agents-md), [Claude Code](https://code.claude.com/docs/en/memory), or your chosen agent.

### Keep context relevant

When adapting these rules, distinguish guidance needed across tasks from guidance needed only for a project or activity:

- **Across tasks:** keep approval, privacy, work-preservation, verification, and communication boundaries in the instructions that are always loaded within your chosen scope.
- **For a project:** keep its tools, commands, conventions, and compatibility requirements in project instructions. To avoid loading web guidance during unrelated work, scope it to web projects or browser-related areas of mixed projects using your agent's supported loading controls.
- **For an occasional task:** guidance such as the general file's “Agent instructions and workflows” section can be moved in your setup to a reference loaded when authoring those workflows. A skill is optional; a reference with an explicit reading condition can suffice if your agent supports it. Check that it is actually loaded when needed.

A conditional heading does not save context when the entire file is loaded. Do not move essential safety or approval boundaries solely into optional references.

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
- [Agent Skills authoring guidance](https://agentskills.io/skill-creation/best-practices) and [activation checks](https://agentskills.io/skill-creation/optimizing-descriptions) informed focused workflow descriptions, conditional references, and representative checks. [Anthropic's customisation guidance](https://claude.com/blog/steering-claude-code-skills-hooks-rules-subagents-and-more) informed the distinction between instructions and enforceable controls.

## Licence

Licensed under [MIT](LICENSE). When copying these rules or substantial portions of them, retain the copyright and permission notice from the licence.
