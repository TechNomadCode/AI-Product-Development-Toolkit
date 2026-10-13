<div align="center">

# AI Product Development Toolkit

**Plan, build and launch products with AI, without the mess.**

[![MIT license](https://img.shields.io/badge/license-MIT-blue)](./LICENSE)
![Works with Claude Code](https://img.shields.io/badge/works%20with-Claude%20Code-D97757)
[![Codex: untested](https://img.shields.io/badge/Codex-untested-lightgrey)](./starters/nextjs-supabase-vercel/README.md#tested-so-far)

</div>

| | What it is | Use it when |
| --- | --- | --- |
| **[Planning prompts](#planning-prompts)** | Guided prompts that interview you, then write your plan. Any AI chat. | You have an idea and want a solid plan |
| **[AI App Starter](#ai-app-starter)** | Instructions your coding agent follows to build a web app with you, step by step, up to launch. | You want to build and launch a web app |
| **[Skills](#skills)** | The planning prompts and the AI App Starter as commands, plus one that makes short product videos in code. Installed with one line. | You use Claude Code or Codex |
| **[Agent configurations](#agent-configurations)** | Working instructions for Claude Code. | You code with Claude Code every day |

## Planning prompts

Most prompts tell the AI to write a document straight away, so it fills every gap with guesses. These prompts make it **interview you first**:

- **It asks before it writes.** A few targeted questions at a time, about your idea, users and goals.
- **It checks what it understood.** It states its assumptions and confirms them with you before moving on.
- **It drafts only once you agree.** The document is built from your answers, not from guesses.
- **Each step feeds the next.** Later prompts use your earlier documents, so the whole plan stays consistent.

| Step | Prompt | What you get |
| --- | --- | --- |
| 1. Research users | [User research questionnaire](./planning-prompts/1-user-research/) | A questionnaire, then an evidence-based research summary for your PRD |
| 2. Define the product | [PRD generation](./planning-prompts/2-prd/) | A product requirements document: goals, users, requirements and constraints |
| 3. Map the experience | [UX and user flow](./planning-prompts/3-ux/) | User journeys, screens and interface requirements |
| 4. Scope the first release | [MVP scope](./planning-prompts/4-mvp-scope/) | The core hypothesis, the problem to solve first and a short in/out feature list |
| 5. Plan the build | [MVP build plan](./planning-prompts/5-mvp-plan/), full or ultra-lean | A full development plan, or a lean build spec for a fast first version |
| 6. Plan testing | [Test plan](./planning-prompts/6-test-plan/) | A test plan outline: scope, test types, environments, and when testing starts and ends |

**How to use them:** open a prompt and copy it with the copy button at the top right of the file (**Copy raw content**). Fill in the bracketed placeholders, paste it into any AI chat and answer its questions. Start at any step; each folder's guide says what to bring and links to the next step. Most people start at step 2, the [PRD prompt](./planning-prompts/2-prd/). Do step 1 first if you have potential users you can ask.

More: the [planning prompts guide](./planning-prompts/README.md), and why this approach works: [How I Turn Ideas Into Products With AI Prompts](https://promptquick.ai/blog/turn-ideas-into-products-with-ai).

## AI App Starter

The [AI App Starter](./starters/nextjs-supabase-vercel/) turns your AI coding agent into a guide that builds a Next.js, Supabase and Vercel app with you, from idea to launch. You don't need to know the process: it leads, and you answer in plain words.

The starter contains no code: it's stage-by-stage instructions, permission rules, and the test and CI requirements the agent follows. The agent writes the app, its tests and its checks.

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

- **It can't touch production directly.** It works only on your computer, with a local database and stand-in payment and email services. It never holds hosted keys, not even test keys, and you push and start production deploys yourself. Its list of blocked commands is only a backstop.
- **It leads, in plain language.** It asks only what the next piece of work needs, does every local step itself, and hands you one command or a few clicks for the rest.
- **It stays organized.** One plan, one decisions file, one list of known issues, and new ideas go into the plan instead of derailing the work.

### What you need

Node.js, Git and Docker to start, and GitHub, Vercel and Supabase accounts once the app goes online. The agent tells you when. Tested with Claude Code desktop up to the first pieces of a web shop; Codex, the hosted staging and production setup, and launch aren't tested yet.

More: the [starter guide](./starters/nextjs-supabase-vercel/) covers the five stages, what working with it is like, what's been tested, and how it works under the hood. Why I made it: [AI App Starter: A Custom Step-by-Step Process for Apps With Claude Code](https://promptquick.ai/blog/ai-app-starter-nextjs-supabase-vercel).

## Skills

Use Claude Code or Codex? You can install the planning prompts, the AI App Starter and a video maker as skills, then you can run each one by name.

**Install:** paste this into Claude Code or Codex.

```text
Install the AI Product Development Toolkit skills: clone https://github.com/TechNomadCode/AI-Product-Development-Toolkit with git clone --depth 1 into a temporary folder, then follow agent-skills/INSTALL.md from it.
```

The agent copies the skills into your personal skills folder, so they work in every project. To update them, paste the same line again.

**Install only some skills:** add their names from the table below to the end of the same line, for example:

```text
Install the AI Product Development Toolkit skills: clone https://github.com/TechNomadCode/AI-Product-Development-Toolkit with git clone --depth 1 into a temporary folder, then follow agent-skills/INSTALL.md from it. Install only these skills: prd, remotion-video
```

| Skill | Run it with | What it does |
| --- | --- | --- |
| User research | `/user-research` | Plans a questionnaire, then turns the responses into input for your PRD |
| PRD | `/prd` | Interviews you, then drafts your product requirements |
| UX and user flows | `/ux` | Maps the screens and user flows from your PRD |
| MVP scope | `/mvp-scope` | Picks the smallest first version worth building |
| MVP build plan | `/mvp-plan` | Plans the build: a full plan or an ultra-lean spec |
| Test plan | `/test-plan` | Drafts a test plan outline: scope, test types, and entry and exit criteria |
| AI App Starter | `/nextjs-supabase-vercel` | Sets up an empty folder with the AI App Starter |
| Video | `/remotion-video` | Makes a short video about your product in code (Remotion), after you approve the idea and a storyboard |

In Codex, type `$` instead of `/`, for example `$prd`. Skills run only when you call them. Each planning skill runs its [planning prompt](#planning-prompts) unchanged and fills it from what you give it.

The video skill needs Node.js. It also makes its sound in code, usually with Python, so have Python installed too. It installs Remotion itself, once you approve its plan.

**Demo:** a video for [promptquick.ai](https://promptquick.ai), made with the process behind `/remotion-video`. Sound on.

https://github.com/user-attachments/assets/674cb631-cde3-4cf4-bd6b-047d3bb3f5a0

## Agent configurations

Working instructions for Claude Code, based on Anthropic's documentation. Merge them into your own setup instead of replacing it.

| Config | What it does |
| --- | --- |
| [Claude Sonnet 5.5 rules](./agent-configs/claude-code/claude-sonnet-5-5/README.md) (latest) | The Opus 5.5 file plus three short additions: no unrequested extras, stop after giving a plan, and run a real check before saying done. |
| [Claude Opus 5.5 rules](./agent-configs/claude-code/claude-opus-5-5/README.md) | A `CLAUDE.md` for clear scope, concise replies and up-to-date docs lookups. The lookups use Context7, a free docs tool; the guide shows how to add it. |
| [Claude Opus 5 rules](./agent-configs/claude-code/claude-opus-5/README.md) | The same idea, written for Opus 5. |

More: the [agent configuration guide](./agent-configs/README.md), and [What Anthropic Says Has Improved in Opus 5.5](https://promptquick.ai/blog/opus-5-5-improvements-and-prompting).

## Good to know

- AI output is a draft. Review requirements, plans, and code before relying on them.
- Don't paste private information your AI tool doesn't need.

## Feedback and license

Found an unclear step or have an idea? [Open an issue](https://github.com/TechNomadCode/AI-Product-Development-Toolkit/issues/new/choose); the form asks which prompt, skill or starter you used. Questions go to [Discussions](https://github.com/TechNomadCode/AI-Product-Development-Toolkit/discussions). Want to help? See [contributing](./.github/CONTRIBUTING.md). If this helps you, star the repo to find it again.

I build these using official documentation, AI tools, and my own development work. For broader prompting techniques, see my [Prompt Rulebook](https://promptquick.ai).

Free to use, adapt, and share under the [MIT license](./LICENSE).
