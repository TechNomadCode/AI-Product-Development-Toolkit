# Agent Configurations

This directory contains behavioral instructions and configuration files for AI coding agents and assistants.

## Purpose

Keep reusable instructions and tool permissions in one place, then adapt them to each project. For Claude Code, use `CLAUDE.md` for working conventions and `settings.json` for permission rules; see the official [directory guide](https://code.claude.com/docs/en/claude-directory).

## Configuration Index

| Configuration | Purpose |
| --- | --- |
| [Claude Opus 5 instructions](./claude-code-desktop/claude-opus-5/) | Model-specific `CLAUDE.md` with working conventions and Context7 MCP guidance. |
| [Claude Code permission guard](./claude-code-desktop/permission-guardrails/README.md) | Strict, model-independent [settings.json](./claude-code-desktop/permission-guardrails/settings.json) policy covering credentials, files, Git, OS administration, cloud infrastructure, containers, databases, publishing, network tools, and MCP services. Remove restrictions to fit your workflow. |

## Configuration Scopes

For Claude Code settings, choose the destination by scope:

| Scope | Settings destination | Use |
| --- | --- | --- |
| User | `~/.claude/settings.json` | Personal settings across projects. On Windows, `~/.claude` normally resolves to `%USERPROFILE%\.claude`. |
| Project | `<project>/.claude/settings.json` | Shared project settings committed to Git. |
| Local | `<project>/.claude/settings.local.json` | Personal project settings. Add this file to `.gitignore` if you create it manually. |

These repository folders store reusable samples. Merge the settings into the intended destination; this nested sample is not the toolkit repository's root configuration. Preserve existing keys and review path rules for the chosen scope before copying. See [settings scopes](https://code.claude.com/docs/en/settings#settings-files).

Managed settings have the highest priority, followed by command-line settings, local, project, and user settings. Permission arrays merge across scopes, so a local file does not erase a global deny list. See [settings precedence](https://code.claude.com/docs/en/settings#settings-precedence).

## Official References

Anthropic's [settings.json directory entry](https://code.claude.com/docs/en/claude-directory#ce-settings-json) describes its purpose as:

> Permissions, hooks, env vars, model defaults

Start with [Explore the .claude directory](https://code.claude.com/docs/en/claude-directory) for file placement, then use [Configure permissions](https://code.claude.com/docs/en/permissions) for rule behavior. The [guard README](./claude-code-desktop/permission-guardrails/README.md) documents the enabled restrictions, how to subtract them, and platform limits.

The guard blocks common high-impact command families, content searches, and shell file readers, and requires approval for remaining shell, MCP, and web tool calls. It also enables the Bash sandbox where supported; native Windows retains permission checks but has no Claude Bash sandbox. Expect routine shell commands to prompt and some read-only operations to be blocked by whole-tool rules. See [sandbox support](https://code.claude.com/docs/en/sandboxing#get-started).

## Related Post

[CLAUDE.md for Opus 5 based on Anthropic's official docs](https://www.reddit.com/r/ClaudeAI/comments/1vd57c0/claudemd_for_opus_5_based_on_anthropics_official/)
