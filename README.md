<div align="center">

# AI Product Development Toolkit

**Plan, build and launch products with AI, without the mess.**

[![MIT license](https://img.shields.io/badge/license-MIT-blue)](./LICENSE)
![Works with Claude Code](https://img.shields.io/badge/works%20with-Claude%20Code-D97757)
[![Works with Codex (beta)](https://img.shields.io/badge/works%20with-Codex%20(beta)-412991)](#tested-so-far)

</div>

| | What it is | Use it when |
| --- | --- | --- |
| **[Planning prompts](#planning-prompts)** | Guided prompts that interview you, then write your plan. Any AI chat. | You have an idea and want a solid plan |
| **[AI App Starter](#ai-app-starter)** | A project your coding agent builds with you, step by step, up to launch. | You want to build and launch a web app |
| **[Agent configurations](#agent-configurations)** | Working instructions for Claude Code. | You code with Claude Code every day |

The planning prompts and the AI App Starter also install as [skills](#skills) for Claude Code and Codex, with one line.

## Planning prompts

Most prompts tell the AI to write a document straight away, so it fills every gap with guesses. These prompts make it **interview you first**:

- **It asks before it writes.** A few targeted questions at a time, about your idea, users and goals.
- **It checks what it understood.** It states its assumptions and confirms them with you before moving on.
- **It drafts only once you agree.** The document is built from your answers, not from guesses.
- **Each step feeds the next.** Later prompts use your earlier documents, so the whole plan stays consistent.

| Step | Prompt | What you get |
| --- | --- | --- |
| 1. Research users | [User research questionnaire](./prompt-templates/user-research-questionnaire/) | A questionnaire, then an evidence-based research summary for your PRD |
| 2. Define the product | [PRD generation](./prompt-templates/prd-generation/) | A product requirements document: goals, users, requirements and constraints |
| 3. Map the experience | [UX and user flow](./prompt-templates/ux-user-flow/) | User journeys, screens and interface requirements |
| 4. Scope the first release | [MVP concept](./prompt-templates/mvp-concept-definition/) | The core hypothesis, the problem to solve first and a short in/out feature list |
| 5. Plan the build | [MVP development plan](./prompt-templates/mvp-development-planning/) or [ultra-lean version](./prompt-templates/ultra-lean-mvp-development-planning/) | A full development plan, or a lean build spec for a fast first version |
| 6. Plan testing | [Test plan](./prompt-templates/test-plan-generation/) | Test scope, cases and acceptance criteria |

**How to use them:** open a prompt, fill in the bracketed placeholders, paste it into any AI chat and answer its questions. Start at any step; each folder's guide says what to bring. Most people start at step 2, the [PRD prompt](./prompt-templates/prd-generation/prd-generation.md). Do step 1 first if you have potential users you can ask.

More: the [prompt template guide](./prompt-templates/README.md), and why this approach works: [How I Turn Ideas Into Products With AI Prompts](https://promptquick.ai/blog/turn-ideas-into-products-with-ai).

## AI App Starter

The [AI App Starter](./starters/nextjs-supabase-vercel/) turns your AI coding agent into a guide that builds a Next.js, Supabase and Vercel app with you, from idea to launch. You don't need to know the process: it leads, and you answer in plain words.

**1.** Open your agent in a new, empty folder.

| You use | How |
| --- | --- |
| Claude Code, desktop app | In the Code tab, start a new session and choose the folder. |
| Claude Code, terminal | Run `claude` in the folder. |
| Codex | Run `codex` in the folder. When it asks to use the network for the download, approve it. |

**2.** Paste this:

```text
Set up this folder with the AI App Starter: clone https://github.com/TechNomadCode/AI-Product-Development-Toolkit with git clone --depth 1 into a temporary folder, then follow starters/nextjs-supabase-vercel/SETUP.md from it.
```

**3.** Just talk to it. Ask **what's next?**, then say **continue** or **do X instead**. Already made a PRD or MVP scope with the planning prompts? It asks for them and skips those interviews.

### Why use it

- **It can't break production.** It works only on your computer, with a local database and stand-in payment and email services. It never holds keys, not even test keys, and pushing and deploying are blocked.
- **It leads, in plain language.** It asks only what the next piece of work needs, does every local step itself, and hands you one command or a few clicks for the rest.
- **It stays organized.** One plan, one decisions file, one list of known issues. Separate local, staging and production environments exist from day one, and new ideas go into the plan instead of derailing the work.
- **It's honest about what's real.** It checks current official docs before using a tool, says when a test used a stand-in, and never decides law, tax or pricing for you.
- **Risky work gets a second look.** Payment and permission work gets an independent review, ideally by a second agent.

More: the [starter guide](./starters/nextjs-supabase-vercel/), which walks through the five stages and what the agent does at each one, and why I made it: [AI App Starter: A Custom Step-by-Step Process for Apps With Claude Code](https://promptquick.ai/blog/ai-app-starter-nextjs-supabase-vercel).

### What you need

- **To start:** Node.js, Git and Docker on your computer, and your coding agent. Setup is the heaviest step. If your agent lets you choose how hard the model thinks (an effort or reasoning setting), a higher level helps here, though low worked in testing.
- **Optional:** [Context7](https://context7.com/), a free docs tool for your agent. The agent checks current docs before using any tool or service; Context7 makes that faster and more reliable. Without it, the agent reads the official websites.
- **Later, when the app goes online:** GitHub, Vercel and Supabase accounts. The agent tells you when. Free plans may not allow a commercial app, such as a shop; it checks the current plans for you.

### Tested so far

Tested with Claude Code desktop, through the first working pieces of a web shop. The automatic checks passed on GitHub on the first push. Not tested yet: Codex, the hosted staging and production setup, and launch.

<details>
<summary>How it works under the hood</summary>

Setup copies this structure into your project:

```text
your-project/
├── AGENTS.md              rules loaded every session (CLAUDE.md imports it for Claude Code)
├── docs/plan.md           the current stage, the next action, and the pieces of work
├── docs/decisions.md      the choices made, plus a Deferred list with due moments
├── docs/product/          your PRD, MVP scope and UX flow
├── KNOWN-ISSUES.md        open problems
├── .kit/stages/           one instruction file per stage, read only while it's current
├── .kit/modules/          payments, email and background jobs: questions, rules and tests
├── .kit/planning/         the PRD, UX and MVP interview prompts from this toolkit
├── .claude/settings.json  blocks pushing, deploying and hosted commands (Claude Code)
└── .codex/rules/          the same blocks for Codex
```

- **Session loop:** the agent reads where things stand in `docs/plan.md`, loads only the current stage, does one step, saves, and updates the plan. At natural stopping points it suggests a fresh session, which picks up from the plan.
- **Safety by design, not by promise:** no hosted credentials exist on your machine. An environment guard refuses to run against anything but the local database and stand-in services. Blocked commands are only a backstop.
- **Rules, not recipes:** the kit states what must be true and how to check it. The agent looks up how today's tools do it and writes the chosen setup, with its sources, into the `AGENTS.md` of the folder it concerns. That folder's rules load only when the agent works there.
- **Pipeline:** staging follows the main branch by itself. Production changes only when you start it. In both, the database is updated before the new code runs, and only the production domain can be indexed.
- **Questions on time:** anything not needed yet goes on the Deferred list with a due moment. The agent checks that list before each stage and each piece of work.

</details>

## Skills

Use Claude Code or Codex? You can install the planning prompts and the AI App Starter as skills, then you can run each one by name.

**Install:** paste this into Claude Code or Codex.

```text
Install the AI Product Development Toolkit skills: clone https://github.com/TechNomadCode/AI-Product-Development-Toolkit with git clone --depth 1 into a temporary folder, then follow agent-skills/INSTALL.md from it.
```

The agent copies seven skills into your personal skills folder, so they work in every project. To update them, paste the same line again.

| Skill | Run it with | What it does |
| --- | --- | --- |
| User research | `/user-research` | Plans a questionnaire, then turns the responses into input for your PRD |
| PRD | `/prd` | Interviews you, then drafts your product requirements |
| UX and user flows | `/ux` | Maps the screens and user flows from your PRD |
| MVP concept | `/mvp` | Picks the smallest first version worth building |
| MVP build plan | `/mvp-plan` | Plans the build: a full plan or an ultra-lean spec |
| Test plan | `/test-plan` | Drafts a test plan with scope and acceptance criteria |
| AI App Starter | `/nextjs-supabase-vercel` | Sets up an empty folder with the AI App Starter |

In Codex, type `$` instead of `/`, for example `$prd`. Skills run only when you call them. Each planning skill runs its [planning prompt](#planning-prompts) unchanged and fills it from what you give it.

## Agent configurations

Working instructions for Claude Code, based on Anthropic's documentation. Merge them into your own setup instead of replacing it.

| Config | What it does |
| --- | --- |
| [Claude Opus 5.5 rules](./agent-configs/claude-code-desktop/claude-opus-5-5/README.md) (latest) | A `CLAUDE.md` for clear scope, concise replies and up-to-date docs lookups. The lookups use Context7, a free docs tool; the guide shows how to add it. |
| [Claude Opus 5 rules](./agent-configs/claude-code-desktop/claude-opus-5/README.md) | The same idea, written for Opus 5. |

More: the [agent configuration guide](./agent-configs/README.md), and [What Anthropic Says Has Improved in Opus 5.5](https://promptquick.ai/blog/opus-5-5-improvements-and-prompting).

## Good to know

- AI output is a draft. Review requirements, plans, and code before relying on them.
- Don't paste private information your AI tool doesn't need.

## Feedback and license

Found an unclear step? [Open an issue](https://github.com/TechNomadCode/AI-Product-Development-Toolkit/issues) with the template name and a small, non-sensitive example. If this helps you, star the repo to find it again.

I build these using official documentation, AI tools, and my own development work. For broader prompting techniques, see my [Prompt Rulebook](https://promptquick.ai).

Free to use, adapt, and share under the [MIT license](./LICENSE).
