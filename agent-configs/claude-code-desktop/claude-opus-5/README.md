# Claude Opus 5 working instructions

This folder contains [CLAUDE.md](./CLAUDE.md), a reusable set of working instructions intended for Claude Opus 5 in Claude Code. It asks for concise responses, clear task scope, current documentation, and controlled tool use.

## Description

Claude Code loads `CLAUDE.md` as context, not as its system prompt or an enforced permission policy. Conflicting instructions can reduce adherence; review the rules alongside your existing configuration. See [how Claude Code loads memory](https://code.claude.com/docs/en/memory).

The configuration was written with Anthropic's [prompting guidance](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/claude-prompting-best-practices) and [Opus 5 guide](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-opus-5) as references.

## How to Use

1. Read the [rules file](./CLAUDE.md) and compare it with your existing project instructions.
2. For a project using the intended model, merge the relevant rules into the project's root `CLAUDE.md`; preserve its build commands and other project requirements.
3. This file requests Context7 lookups: configure [Context7 for Claude Code](https://context7.com/docs/clients/claude-code) if you keep that workflow, or adapt the instructions to your available documentation tools.
4. Start a fresh session and use `/memory` and `/context` to inspect the loaded files. Try a small task before adopting the rules more widely.

## Choose the scope

| Location | Intended scope |
| --- | --- |
| Project root `CLAUDE.md` | Shared project instructions when committed to Git |
| Project `CLAUDE.local.md` | Personal project notes; confirm your Git ignore rules before using it |
| Subdirectory `CLAUDE.md` | Instructions loaded when Claude works with that directory |
| User `~/.claude/CLAUDE.md` | Instructions across projects; avoid placing this model-specific sample here if you switch models |

Multiple instruction files can contribute context. Do not assume a project file erases conflicting user instructions; resolve conflicts and check what loaded. See [memory troubleshooting](https://code.claude.com/docs/en/memory).

## Key Features

* **Documentation:** Requests current dependency references before implementation.
* **Task scope:** Requests concise narration, parallel independent work, and checks appropriate to the change.
* **Destructive actions:** Asks the assistant to request approval; use Claude Code permissions for tool restrictions, not prose alone.
* **Continuation:** Requests saved progress before context refreshes.

For an optional strict tool policy, read the separate [permission guardrails guide](../permission-guardrails/README.md) before applying it.

## Model Compatibility

*   **Intended target:** **Claude Opus 5**; inspect the selected model and test the rules for your workflow rather than assuming they suit every model.
*   **Documentation References:**
    *   [Claude Code Best Practices (`CLAUDE.md`)](https://code.claude.com/docs/en/best-practices#write-an-effective-claude-md)
    *   [Claude Prompting Best Practices](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/claude-prompting-best-practices)
    *   [Prompting Claude Opus 5](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-opus-5)
    *   [Context 7 MCP Documentation](https://context7.com/docs/clients/claude-code)
