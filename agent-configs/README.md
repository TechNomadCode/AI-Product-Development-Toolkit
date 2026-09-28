# Agent Configurations

Reusable working instructions for AI coding agents. Merge them into your own setup instead of replacing it.

## Configuration Index

| Configuration | Purpose |
| --- | --- |
| [Claude Sonnet 5.5 instructions](./claude-code-desktop/claude-sonnet-5-5/) | Latest model-specific `CLAUDE.md`: the Opus 5.5 file plus three short additions for behavior Anthropic's Sonnet 5.5 guide describes, and effort notes. |
| [Claude Opus 5.5 instructions](./claude-code-desktop/claude-opus-5-5/) | Model-specific `CLAUDE.md`: the Opus 5 conventions and Context7 guidance with fewer repeated or rigid rules, plus effort-level notes. |
| [Claude Opus 5 instructions](./claude-code-desktop/claude-opus-5/) | Model-specific `CLAUDE.md` with working conventions and Context7 guidance. |

## Where the file goes

`CLAUDE.md` is context, not an enforced policy. Place it where Claude Code loads it, for yourself across projects or for one project, and check which files loaded with `/memory`. See [Claude Code memory](https://code.claude.com/docs/en/memory). Anything that must be enforced belongs in [permissions](https://code.claude.com/docs/en/permissions) or [hooks](https://code.claude.com/docs/en/hooks-guide).

## Related Post

[CLAUDE.md for Opus 5 based on Anthropic's official docs](https://www.reddit.com/r/ClaudeAI/comments/1vd57c0/claudemd_for_opus_5_based_on_anthropics_official/)
