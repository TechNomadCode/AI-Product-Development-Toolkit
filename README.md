# AI Product Development Toolkit

Free, copy-paste prompts and coding-assistant rules for building software with AI.

Everything here is a plain Markdown file. You don't need to install anything or clone this repository.

## How to use a prompt

1. Pick a prompt from the table below and open its file.
2. Copy the contents and fill in the bracketed placeholders with your project details.
3. Paste it into your AI chat, answer its questions, and review the draft it produces.

**New here?** Start with the [PRD prompt](./prompt-templates/prd-generation/prd-generation.md) ([guide](./prompt-templates/prd-generation/README.md)). It turns a rough app idea into a clear requirements document.

## Prompts

Listed in the order you would normally use them. You can start at any step; each folder's guide explains what to bring.

| Step | Prompt | What you get |
| --- | --- | --- |
| 1. Research users | [User research questionnaire](./prompt-templates/user-research-questionnaire/) | A questionnaire, then a research summary for your PRD |
| 2. Define the product | [PRD generation](./prompt-templates/prd-generation/) | Goals, users, requirements, and constraints |
| 3. Map the experience | [UX and user flow](./prompt-templates/ux-user-flow/) | User journeys and interface requirements |
| 4. Scope the first release | [MVP concept](./prompt-templates/mvp-concept-definition/) | Core problem, hypothesis, and a short feature list |
| 5. Plan the build | [MVP development plan](./prompt-templates/mvp-development-planning/) or [ultra-lean version](./prompt-templates/ultra-lean-mvp-development-planning/) | A detailed plan, or a smaller build spec |
| 6. Plan testing | [Test plan](./prompt-templates/test-plan-generation/) | Test scope, cases, and acceptance criteria |
| 7. Design the UI | [v0 design prompts](./prompt-templates/v0-design-prompts/) | A ready-to-use prompt for v0.dev |
| Anytime | [Session continuation](./prompt-templates/session-continuation/) | A handoff so you can continue in a fresh chat |

More detail: [prompt template guide](./prompt-templates/README.md). \
Why this approach works: [How I Turn Ideas Into Products With AI Prompts](https://promptquick.ai/blog/turn-ideas-into-products-with-ai).

## Coding assistant configs

Rules and settings for Claude Code. Merge them into your own setup instead of replacing it.

| Config | What it does |
| --- | --- |
| [Claude Opus 5.5 rules](./agent-configs/claude-code-desktop/claude-opus-5-5/README.md) (latest) | A `CLAUDE.md` for clear scope, concise replies, and up-to-date docs lookups |
| [Claude Opus 5 rules](./agent-configs/claude-code-desktop/claude-opus-5/README.md) | The same idea, written for Opus 5 |
| [Permission guardrails](./agent-configs/claude-code-desktop/permission-guardrails/README.md) | An optional, strict `settings.json` that blocks risky commands. Read it before using it |

More detail: [agent configuration guide](./agent-configs/README.md). \
What changed in Opus 5.5: [What Anthropic Says Has Improved in Opus 5.5](https://promptquick.ai/blog/opus-5-5-improvements-and-prompting).

## Good to know

- AI output is a draft. Review requirements, plans, and code before relying on them.
- Don't paste private information your AI tool doesn't need.

## Feedback and license

Found an unclear step? [Open an issue](https://github.com/TechNomadCode/AI-Product-Development-Toolkit/issues) with the template name and a small, non-sensitive example. If this helps you, star the repo to find it again.

I build these using official documentation, AI tools, and my own development work. For broader prompting techniques, see my [Prompt Rulebook](https://promptquick.ai).

Free to use, adapt, and share under the [MIT license](./LICENSE).
