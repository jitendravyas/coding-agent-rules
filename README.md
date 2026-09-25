# Coding agent rules

Agent-neutral, gender-neutral Markdown rules for AI coding agents working on software development projects and related development tasks. They are not general-purpose assistant instructions. The general coding instructions apply across software types; the browser-specific instructions apply only to browser-delivered work and its supporting web endpoints.

## How to use

The two `.md` files are kept separate in this repository only for maintenance. They are source content: cloning the repository does **not** make an agent load them. Copy their contents into the instruction files or settings your coding agent actually uses. A web project's instructions can contain both in one file.

Choose the scope that suits you:

- **User-level rules:** copy [global-coding-agent-rules.md](global-coding-agent-rules.md) and, if you want web guidance available across projects, [web-development-rules.md](web-development-rules.md) into your agent's user-level instructions.
- **Project-specific rules:** copy the global rules into each chosen project's instructions, adding the web rules for web projects.
- **A mix:** keep the global rules at user level and add the web rules only to selected projects. Avoid loading the same rules twice.

User-level rules load more broadly, including when the agent handles non-development work. The scope statements inside the files still limit when their instructions apply.

### In Cursor

1. For user-level use, open **Customize → Rules → User Rules** and paste the contents of the file(s) you want available across projects. Cursor Agent (Chat) will use them across your projects.
2. For project-specific use, open the project and use **Customize → Rules → Add Rule** to create a **Project Rule**. Set it to **Always Apply** and paste in the rules that project needs but does not already get at user level: the global rules and, for a web project, the web rules. Cursor saves project rules as `.mdc` files under `.cursor/rules/`.
3. If the project already uses `AGENTS.md`, you can put its rules there instead. Use one route for each set of rules, not both.

Cursor User Rules apply to Agent (Chat), not Inline Edit or Cursor Tab. See [Cursor's rules documentation](https://cursor.com/docs/rules).

### In Codex

1. For user-level use, paste the contents of the file(s) you want available across projects into your Codex home `AGENTS.md` (`~/.codex/AGENTS.md` by default). Codex loads it for every project.
2. For project-specific use, add the rules the project needs but does not already get at user level to its root `AGENTS.md`: the global rules and, for a web project, the web rules. Merge them with any instructions already present.
3. Start a new Codex session after changing instruction files. See [Codex's AGENTS.md guide](https://learn.chatgpt.com/docs/agent-configuration/agents-md).

The two rule files together exceed Codex's default 32 KiB combined instruction-file limit. To load both completely, set `project_doc_max_bytes = 65536` in your Codex home `config.toml` (`~/.codex/config.toml` by default), or reduce the instructions you load. Check the limit again if the project has other instruction files.

### In Claude Code

1. For user-level use, paste the contents of the file(s) you want available across projects into `~/.claude/CLAUDE.md`.
2. For project-specific use, add the rules the project needs but does not already get at user level to its `CLAUDE.md` or `.claude/rules/`: the global rules and, for a web project, the web rules. Merge them with existing instructions.
3. Run `/context` in a new Claude Code session to check which instruction files loaded. See [Claude Code's memory guide](https://code.claude.com/docs/en/memory).

Claude Code can also read a project's `AGENTS.md` when no project `CLAUDE.md` or `CLAUDE.local.md` takes its place. Support varies by version; confirm with `/context` before relying on one project file across agents.

For any other agent, use its documented instruction mechanism. Choose user-level or project-specific placement for each file, and check that the intended rules load.

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
