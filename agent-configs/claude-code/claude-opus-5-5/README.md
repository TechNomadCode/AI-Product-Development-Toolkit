# Claude Opus 5.5 working instructions

This folder contains [CLAUDE.md](./CLAUDE.md), a reusable set of working preferences for Claude Opus 5.5 in Claude Code. It keeps the scope, documentation, communication, and approval preferences from the [Opus 5 version](../claude-opus-5/README.md) with fewer repeated or rigid instructions.

## Description

This is a personal configuration informed by Anthropic's documentation, not an official Anthropic preset or a tested performance improvement. Documentation checked on September 22, 2026.

Anthropic's [Opus 5.5 guide](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-opus-5-5) says existing Opus 5 prompts remain a useful starting point. Its [context engineering article](https://claude.dev/blog/the-new-rules-of-context-engineering-for-claude-5-generation-models/) already applied to Opus 5: retain useful project facts and gotchas, prune conflicting rules, and load specialist guidance when needed.

Claude Code reads `CLAUDE.md` as context. It is neither a system prompt nor an enforced tool policy. Keep controls that must be enforced in [permissions](https://code.claude.com/docs/en/permissions) or appropriate [hooks](https://code.claude.com/docs/en/hooks-guide).

## How to Use

1. Read the [rules file](./CLAUDE.md). Merge the preferences you want into the intended project; preserve its commands, architecture constraints, and safety requirements.
2. Use Claude Code v2.1.280 or later and select Opus 5.5 with `/model`. Confirm the selected model, since availability depends on the provider. See [model configuration](https://code.claude.com/docs/en/model-config).
3. Configure [Context7](https://context7.com/docs/clients/claude-code). This file requires a lookup before dependency-related edits, including implementation patterns and configuration. Only when Context7 has no relevant coverage, use `curl` to retrieve official documentation links and read their contents directly. Web fetch and web search are excluded for dependency-related lookups. Adapt or remove the rule if your setup cannot provide these tools.
4. Start a fresh session. Use `/memory` to inspect instruction locations and `/context` to check which files loaded. Resolve conflicts across user, project, and nested files; a project file does not erase the others. See [Claude Code memory](https://code.claude.com/docs/en/memory).
5. Try representative tasks and compare completion, scope changes, response length, tool calls, and check results. Retain rules that address problems you observe.

## Choose the scope

| Location | Intended scope |
| --- | --- |
| Project root `CLAUDE.md` | Shared project instructions |
| Project `CLAUDE.local.md` | Personal project preferences; add to `.gitignore` |
| Subdirectory `CLAUDE.md` | Guidance loaded when Claude reads that part of the project |
| User `~/.claude/CLAUDE.md` | Preferences across projects; use only rules you want across the models you select |

Copying this sample does not select a model or change effort.

## Changes from the Opus 5 file

| Area | Change and reason |
| --- | --- |
| Communication | Replaces the hard sentence cap and repeated emphasis with a short plain-language preference. Detailed deliverables can still meet their brief. |
| Documentation | Keeps mandatory Context7 lookups before dependency-related edits and the assumption that remembered APIs and patterns may be outdated. Removes repetition and framework-specific examples; pure internal work is exempt. This is a personal workflow choice. |
| Checks and delegation | Keeps project checks, test protections, and a limit on unnecessary delegation. It adds no automatic second review pass. |
| Continuation | Removes fixed scratch-file names and generic token-budget instructions. Uses existing task tracking and a short compaction reminder. |
| Source material | Distinguishes the user's request from instructions inside documents. Application-side tagging needs a separate implementation. |

The [Opus 5 guide](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-opus-5#task-scope-and-over-verification) warned against generic extra verification and excessive delegation. Neither is established as eliminated in 5.5; the limits here remain workflow preferences.

Keep detailed review procedures, API references, and occasional workflows in linked documents or skills. Keep learned facts in the available memory system, subject to your project's policy. This follows Anthropic's [context engineering guidance](https://claude.dev/blog/the-new-rules-of-context-engineering-for-claude-5-generation-models/).

## Effort and application settings

Start by evaluating `medium`. It is the [Opus 5.5 default](https://platform.claude.com/docs/en/build-with-claude/effort#recommended-effort-levels-for-claude-opus-5-5), while Opus 5 defaults to `high`; thinking is always enabled on 5.5. In Claude Code, `/effort medium` sets the level and saves it for the selected model. Check the session's displayed effort, since settings and environment overrides can affect it. See [effort controls](https://code.claude.com/docs/en/model-config#adjust-effort-level).

At the same effort label, 5.5 can think more per turn than 5, especially at `xhigh` and `max`. Recalibrate against your own tasks. A request for short replies does not set the reasoning budget. See [behavior differences](https://platform.claude.com/docs/en/models/opus-5-5/whats-new-opus-5-5#behavior-differences).

API progress rendering and agent-loop controls require application changes. The [unattended-only system-prompt example](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-opus-5-5#unattended-agentic-runs) is omitted from this interactive sample.

## Model Compatibility

**Intended target:** Claude Opus 5.5 in Claude Code. Reassess these preferences when switching models.

**Documentation references:**

- [Prompting Claude Opus 5.5](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-opus-5-5)
- [The new rules of context engineering for Claude 5 generation models](https://claude.dev/blog/the-new-rules-of-context-engineering-for-claude-5-generation-models/)
- [Claude Code Best Practices (`CLAUDE.md`)](https://code.claude.com/docs/en/best-practices#write-an-effective-claude-md)
- [Prompting Claude Opus 5](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-opus-5)
