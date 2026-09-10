# Coding agent rules

A global rules file for AI coding agents that work on real codebases: safe by default, no wasted tokens, and a human who only steps in for decisions.

Written for any agent, any model including small or older ones, any operating system, and any kind of software: web, mobile, desktop, backend, or scripts. Nothing in it names a tool, a language, or a framework.

## Install

Copy `global-coding-agent-rules.txt` into your agent's user-level rules location, renamed to whatever file name your tool expects. Common places: `~/.claude/CLAUDE.md` for Claude Code, the global rules setting in Cursor, `~/.codex/AGENTS.md` for Codex. The content is plain text and works as markdown.

Then mirror the "Ask before" list in your tool's permission settings. The rules ask; the settings enforce. This matters most with small models.

Project-specific facts, such as commands, versions, safe environments, and conventions, belong in each repository's own agent instructions file. The global file tells the agent to find and follow those.

One line in the file refers to `triggered-rules.txt`, an optional companion holding a code review procedure and a handoff procedure for when quota or time runs out. It is not included here. If you do not have one, delete that line.

## How it works

The file is ordered by the stages of a task: Always, Before you start, Ask before, While coding, Documents, Security, Before you say done, Commit, Final report, Replies. Each rule is one line, one instruction, with a number wherever a judgement word used to be, so that weak models can follow it too.

The agent works through a task on its own and asks only for decisions a human must make: unclear intent, a change in scope, or an item on the ask-before list. Everything else it decides, notes in the final report, and continues.

## Defaults you may want to change

These are opinions. Override them in your project's instructions file, which takes precedence.

- Comments are off by default; code should explain itself.
- The agent may commit locally on a working branch, but asks before pushing, deploying, or committing on the main branch.
- New dependencies, schema changes, migrations, and anything that leaves the machine need approval.
- Replies are capped at 15 lines outside plans and reports.

## Contributing

Before adding a rule, apply the test used to build this file: would a capable model do this anyway? If yes, it does not belong here. Rules that only matter for one stack or one project belong in that project's instructions, not here.

## Influences

- Anthropic's Claude Code guidance on memory files and best practices
- The AGENTS.md open format
- The pstack engineering principles by poteto
- The Conventional Commits specification
- An ETH Zurich study on context files for coding agents

## Licence

MIT. See `LICENSE`.
