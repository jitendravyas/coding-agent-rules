# Coding agent rules

These Markdown rules provide a baseline for everyday coding-agent work on new and existing software projects without assuming a particular agent, model, operating system, or tech stack. They aim to reduce repeated prompting and rework without mandating unnecessary checks. They are not general-purpose assistant instructions or a substitute for project-specific coding standards or specialist procedures.

- [General software-project instructions](global-coding-agent-rules.md) cover task scope, approvals, research, implementation, security, verification, and communication across software projects.
- [Browser-specific instructions](web-development-rules.md) cover browser behaviour, compatibility, web security, and rendered verification for browser-delivered work and its supporting web endpoints.
- [Agent workflow authoring](optional/agent-workflow-authoring-rules.md) is optional guidance for creating or changing agent rules, skills, subagents, or tool workflows. Add or load it only for those tasks, not in rules loaded for every task.

## How to use

Cloning this repository does not activate the rules.

1. **Choose the content.** For web development projects, using both baseline files (general and browser-specific) is recommended. Either baseline file can also be used independently, or you can copy selected relevant sections. These two files are separate here for maintenance. When both are loaded at the same instruction priority, their instructions are intended to apply together in either order, separately or combined.
2. **Choose where they apply.** Copy or adapt the baseline rules into your agent's supported project instruction file for one project, or its user-level instructions for use across projects. For teams, keep the shared baseline in version-controlled project instructions rather than relying on each developer's user-level setup.
3. **Merge and check.** Merge duplicate instructions and resolve conflicts with rules already in place. Keep each section's heading, scope conditions, and nested lists with its content when copying or reordering. Preserve attached safety and approval conditions. Use available loading diagnostics to confirm the complete content is loaded, not just that the file is recognised. Use project checks to enforce mechanical requirements.

For placement details, see the official instructions for [Cursor](https://cursor.com/docs/rules), [Codex](https://developers.openai.com/codex/guides/agents-md), [Claude Code](https://code.claude.com/docs/en/memory), or your chosen agent.

### Keep context relevant

When adapting these rules, distinguish guidance needed across tasks from guidance needed only for a project or activity:

- **Across tasks:** keep approval, privacy, work-preservation, verification, and communication boundaries in the instructions that are always loaded within your chosen scope.
- **For a project:** keep its tools, commands, conventions, and compatibility requirements in project instructions. To avoid loading web guidance during unrelated work, scope it to web projects or browser-related areas of mixed projects using your agent's supported loading controls.
- **For an occasional task:** keep specialist procedures, such as full accessibility audits, performance profiling, or authoring agent workflows, in a task-specific reference or skill. Load them when relevant; keep basic safeguards and checks for affected behaviour in the baseline.

A conditional heading does not save context when the entire file is loaded. Do not move essential safety or approval boundaries solely into optional references.

## Contributing

Issues and pull requests are welcome. Explain the problem your suggestion solves and whether it belongs in the general baseline, web baseline, optional task-specific rules, or project instructions.

## Influences

These rules mainly reflect practical experience with coding agents. The sources below contributed specific guidance that remains in the files; other material reviewed during drafting is not listed.

- Lauren Tan's [pstack article](https://x.com/poteto/article/2094457600259842065) and [verification-skill pattern](https://github.com/cursor/plugins/blob/main/pstack/skills/create-verification-skill/SKILL.md) shaped the emphasis on direct evidence and reusable verification for important recurring work.
- Samuel Hu's [run-receipt suggestion](https://x.com/realSamHu/status/2103409341240119777) and Harsh Munjal's [execution-record feedback](https://x.com/Mr_Munjal/status/2103394763109966193) informed inspecting available execution evidence before retries and naming verification checks, results, and relevant errors in reports. Adapted with error redaction, without requiring automatic logging, spend tracking, or a receipt before each retry.
- Ansh Nanda's [testing discussion](https://x.com/anshnanda/status/2101627891721371971) informed the requirement for meaningful tests with expected results independent of the implementation, without adopting an E2E-only policy.
- Matt Pocock's [tracer-bullet approach](https://www.aihero.dev/tracer-bullets) informed the small end-to-end path for unfamiliar multi-component features.
- Addy Osmani's [Brownfield Agentic Engineering](https://addyosmani.com/blog/brownfield-agentic-engineering/) informed the rules to establish existing behaviour before refactoring and preserve safeguards and consumer compatibility during replacement.
- [AWS's secure agentic development guidance](https://docs.aws.amazon.com/prescriptive-guidance/latest/agentic-ai-security/best-practices-dev-practices.html) and OWASP's [input-validation](https://cheatsheetseries.owasp.org/cheatsheets/Input_Validation_Cheat_Sheet.html), [injection-prevention](https://cheatsheetseries.owasp.org/cheatsheets/Injection_Prevention_Cheat_Sheet.html), and [CSRF-prevention](https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.html) guidance informed the trust-boundary and web-security rules.
- Jad Joubran's [Baseline article](https://www.smashingmagazine.com/2026/08/how-baseline-can-help-ship-less-javascript/) informed the browser-support decision rule without replacing project-specific compatibility requirements.
- [Agent Skills authoring guidance](https://agentskills.io/skill-creation/best-practices) and [activation checks](https://agentskills.io/skill-creation/optimizing-descriptions) informed the optional agent-workflow-authoring rules on descriptions, conditional references, and representative checks.
- [Anthropic's customisation guidance](https://claude.com/blog/steering-claude-code-skills-hooks-rules-subagents-and-more) informed the distinction between instructions and enforceable controls.

## Licence

Licensed under [MIT](LICENSE). When copying these rules or substantial portions of them, retain the copyright and permission notice from the licence.
