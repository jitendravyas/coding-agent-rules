# Coding agent rules

A global rules file for AI coding agents: safe by default, no wasted tokens, and a human who only steps in for decisions. Works with any agent, model, operating system, or kind of software.

## Install

Put the content of `global-coding-agent-rules.txt` into your agent's user-level rules file, renamed to whatever your tool expects.

One line in the file refers to `triggered-rules.txt`, an optional companion (a review procedure and a quota handoff) not included here. Delete that line if you do not have one.

## Influences

- Anthropic's Claude Code guidance on memory files and best practices
- The AGENTS.md open format
- The pstack engineering principles by poteto
- The Conventional Commits specification
- An ETH Zurich study on context files for coding agents

## Licence

MIT. See `LICENSE`.
