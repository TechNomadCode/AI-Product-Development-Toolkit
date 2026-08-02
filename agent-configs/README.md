# Agent Configurations

This directory contains system prompts, behavioral guidelines, safety rules, and configuration files for AI coding agents and assistants.

## Purpose

AI coding agents perform best when provided with explicit boundaries, tool execution defaults, and project conventions. Storing these configurations centrally allows for consistent behavior across projects and easy distribution to local environments.

## Configuration Index

*   [claude-code-desktop/claude-opus-5](./claude-code-desktop/claude-opus-5/): Global `CLAUDE.md` optimized for Claude Opus 5 with context 7 MCP specifically.

## Configuration Scopes

Agent configurations can be applied at different directory levels depending on your tool:

*   **Global Level:** Configurations placed in your user home directory (such as `~/.claude/CLAUDE.md`) apply to all coding sessions on your machine.
*   **Project Level:** Configurations placed in a repository root (such as `./CLAUDE.md` or `.cursorrules`) apply specifically to that codebase and can be shared with team members via Git.
*   **Local Overrides:** Uncommitted local configuration notes (such as `./CLAUDE.local.md`) apply only to your local machine for a specific codebase.