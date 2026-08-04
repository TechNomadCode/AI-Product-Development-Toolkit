# Global Claude Code Agent Rules

This folder contains a `CLAUDE.md` system configuration that defines behavioral guidelines, safety guardrails, MCP tool usage, and execution defaults for Claude Code specifically for Claude Opus 5.

## Description

This `CLAUDE.md` file acts as the universal system prompt for Claude Code. It enforces strict action defaults (parallel tool execution, minimal chatter), mandates modern dependency lookups via Context 7 MCP, establishes destructive command guardrails, and manages subagent delegation boundaries.

> **Official Anthropic Documentation:** Built according to Anthropic's [Claude Prompting Best Practices](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/claude-prompting-best-practices) and optimized specifically using the [Claude Opus 5 Prompting Guidelines](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-opus-5).

## How to Use

Based on the official [Claude Code Documentation](https://code.claude.com/docs/en/best-practices#write-an-effective-claude-md), where you place the `CLAUDE.md` file determines its scope and effect across your sessions:

*   **Global Setup (`~/.claude/CLAUDE.md`) WARNING, DO NOT PLACE MY CONFIG HERE IF YOU ARE USING OTHER MODELS AS THIS IS SPECIFICALLY MADE FOR OPUS 5**
    *   **Effect:** Applies automatically to **all** Claude Code sessions on your computer across every project.
    *   **Use Case:** Personal behavioral rules, safety guardrails, and default tool settings.

*   **Project Root (`./CLAUDE.md`)**
    *   **Effect:** Applies to anyone working in the repository when committed to Git (overrides global rules).
    *   **Use Case:** Shaping Claude Opus 5's behavior when you are working on this project, Build/test commands, repository coding standards and architectural conventions.

*   **Personal Local Notes (`./CLAUDE.local.md`)**
    *   **Effect:** Applies only to your local machine for a specific project (ignored by Git via `.gitignore`).
    *   **Use Case:** Personal environment variables, local paths, or developer-specific workflow notes.

*   **Subdirectories (`./subfolder/CLAUDE.md`)**
    *   **Effect:** Applies specifically when Claude reads or modifies files within that subfolder.
    *   **Use Case:** Shaping Claude Opus 5's behavior when you use it for specific specs, Monorepos or directory-specific rules (e.g., frontend vs. backend conventions).

## Key Features

*   **Context 7 MCP Enforcement:** Mandates fetching up-to-date docs and API versions before writing code to prevent outdated assumptions. Learn more about setting up and using Context 7 via the [Context 7 Documentation](https://context7.com/docs/clients/claude-code).
*   **Safety Guardrails:** Requires user approval for destructive commands (`rm -rf`, `git push --force`, DB drops).
*   **Execution Defaults:** Directs parallel tool calling, concise narration, and autonomous execution without over-verification.
*   **Context Compaction & State Persistence:** Ensures state is saved to `progress.txt`/`tests.json` before context refreshes.
*   **Local Precedence:** Local project `./CLAUDE.md` files automatically override or extend global rules.

## Model Compatibility

*   **Primary Target:** **Claude Opus 5** (utilizes Opus 5 instruction-following and tool-use patterns).
*   **Documentation References:**
    *   [Claude Code Best Practices (`CLAUDE.md`)](https://code.claude.com/docs/en/best-practices#write-an-effective-claude-md)
    *   [Claude Prompting Best Practices](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/claude-prompting-best-practices)
    *   [Prompting Claude Opus 5](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-opus-5)
    *   [Context 7 MCP Documentation](https://context7.com/docs/clients/claude-code)
