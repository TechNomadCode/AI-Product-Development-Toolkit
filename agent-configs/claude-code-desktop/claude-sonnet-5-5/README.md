# Claude Sonnet 5.5 working instructions

This folder contains [CLAUDE.md](./CLAUDE.md), a reusable set of working preferences for Claude Sonnet 5.5 in Claude Code. It is the [Opus 5.5 file](../claude-opus-5-5/README.md) plus three short additions that address behavior Anthropic's Sonnet 5.5 guide describes.

## Description

This is a personal configuration informed by Anthropic's documentation, not an official Anthropic preset or a tested performance improvement. Documentation checked on September 28, 2026.

Anthropic's [Sonnet 5.5 guide](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-sonnet-5-5) says existing Sonnet 5 prompts should perform well without changes, so most of the Opus 5.5 file carries over as it is: the scope rule, the limit on review subagents, and the Context7 lookup rule, which is close to the guide's advice to search for details that may have changed.

Claude Code reads `CLAUDE.md` as context. It is neither a system prompt nor an enforced tool policy. Keep controls that must be enforced in [permissions](https://code.claude.com/docs/en/permissions) or appropriate [hooks](https://code.claude.com/docs/en/hooks-guide).

## Changes from the Opus 5.5 file

| Area | Addition and reason |
| --- | --- |
| Scope | Do not add unrequested tests, documentation, or files; mention them at the end. The guide says Sonnet 5.5 tends to add these at every effort level, and more at higher effort. |
| Scope | When asked for ideas, options, or a plan, give that and stop. The guide notes that open-ended requests can turn into a build. |
| Checks | Run a real check before reporting done, or say which one could not run. The guide says that at low effort the model sometimes reports a change as done without one. |

Nothing was removed. The guide also describes a tendency to stop and check in at low and medium effort on long tasks. The existing "make routine choices yourself" rule covers that, and raising the effort is Anthropic's first suggestion. These lines are my reading of the guide, not something I tested.

## Effort and application settings

Anthropic's launch post says the default effort in Claude Code and the Claude apps is `medium`, and the API defaults to `high`. The guide says effort levels were recalibrated, so a level does not give the same amount of thinking as it did on Sonnet 5. Its starting points: `medium` for well-specified agentic coding, `high` for harder or longer work, and `xhigh` or `max` only where you have measured a better result. In Claude Code, `/effort` sets the level. See [effort controls](https://code.claude.com/docs/en/model-config#adjust-effort-level).

Asking the model in a prompt to think less does not reliably reduce its thinking; lower the effort instead. At `xhigh` and `max` it can start its own review rounds, sometimes with subagents. Anthropic's benchmark notes say this cost Sonnet 5.5 points at `max` on one coding test. The "review subagents only when the user requests them" rule in this file addresses the same habit.

## How to Use

1. Read the [rules file](./CLAUDE.md). Merge the preferences you want into the intended project; preserve its commands, architecture constraints, and safety requirements.
2. Select Sonnet 5.5 with `/model` and confirm the selected model, since availability depends on the provider. See [model configuration](https://code.claude.com/docs/en/model-config).
3. Configure [Context7](https://context7.com/docs/clients/claude-code). This file requires a lookup before dependency-related edits, including implementation patterns and configuration. Only when Context7 has no relevant coverage, use `curl` to retrieve official documentation links and read their contents directly. Web fetch and web search are excluded for dependency-related lookups. Adapt or remove the rule if your setup cannot provide these tools.
4. Start a fresh session. Use `/memory` to inspect instruction locations and `/context` to check which files loaded. See [Claude Code memory](https://code.claude.com/docs/en/memory).
5. Try representative tasks and compare completion, scope changes, response length, tool calls, and check results. Keep the rules that address problems you observe.

## Model Compatibility

**Intended target:** Claude Sonnet 5.5 in Claude Code. Reassess these preferences when switching models.

**Documentation references:**

- [Prompting Claude Sonnet 5.5](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-sonnet-5-5)
- [What's new in Claude Sonnet 5.5](https://platform.claude.com/docs/en/models/sonnet-5-5/whats-new-sonnet-5-5)
- [Introducing Claude Sonnet 5.5](https://www.anthropic.com/claude-sonnet-5-5)
- [Claude Code Best Practices (`CLAUDE.md`)](https://code.claude.com/docs/en/best-practices#write-an-effective-claude-md)
- [Claude Opus 5.5 instructions](../claude-opus-5-5/README.md)
