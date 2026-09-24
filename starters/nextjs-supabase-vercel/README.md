# AI App Starter: Next.js + Supabase + Vercel

Build and launch a web app with an AI coding agent that leads the way. It can't touch production, keeps the project organized, and always tells you what's next.

## Start

**1. Open your agent in a new, empty folder.**

| You use | How |
| --- | --- |
| Claude Code, desktop app | In the Code tab, start a new session and choose the folder. |
| Claude Code, terminal | Run `claude` in the folder. |
| Codex | Run `codex` in the folder. When it asks to use the network for the download, approve it. |

**2. Paste this:**

```text
Set up this folder with the AI App Starter: clone https://github.com/TechNomadCode/AI-Product-Development-Toolkit with git clone --depth 1 into a temporary folder, then follow starters/nextjs-supabase-vercel/SETUP.md from it.
```

**3. Answer its questions.** After that, just talk to it: ask **what's next?**, then say **continue** or **do X instead**. Ask for a new feature or report a bug in your own words, and it fits the request into the plan.

## What happens

| Stage | The agent | You |
| --- | --- | --- |
| 1. Plan | Asks for any PRD, scope or notes you already have and uses them. It interviews you only to fill the gaps, using this toolkit's planning prompts. | Answer questions |
| 2. Decide | Settles only what the first build needs: who uses the app, what it stores, languages, and which services. Your documents usually answer most of it. | Answer a few questions |
| 3. Set up | Builds the first real feature end to end, with tests, automatic checks on GitHub, and a staging and production pipeline. Then it asks about your accounts and writes your setup steps. | Create accounts, follow its steps, push |
| 4. Build | Builds one piece of the app per session, with tests. Payment and permission work gets an independent review first. | Review and push |
| 5. Launch | Prepares production, monitoring, security, search engines, privacy pages and the cutover, one part at a time. | Do the hosted steps |

**What it's like to work with:**
- **Few questions, at the right time.** It asks what the next piece of work needs. Everything else, such as your domain, tax, legal pages or refund policy, is noted with a due moment and comes up then. When you say **yes**, you accept all its recommendations.
- **It explains its limits up front.** It never uses hosted credentials or API keys, not even test keys. For anything that needs them, like trying payments with a PayPal sandbox key, it gives you the steps and you do them on the staging site. Its own tests use stand-ins, and it tells you so.
- **It speaks plain language.** No jargon, so owners without a technical background can follow every step.
- **It does the legwork.** It does every local step itself and hands you one command or a few clicks for the rest.
- **It checks, not remembers.** Before using a tool or service, it reads the current official docs and notes its source. It won't decide law, tax or pricing questions; it shows you options with official sources.
- **It saves as it goes.** Progress is saved after every step. At natural stopping points it suggests a fresh session: type what it says (`/clear` or `/new`), then **continue**.
- **It respects your setup.** If your personal agent instructions conflict with the project's rules, it tells you once at the start, and you choose.

## You need
- Node.js, Git and Docker on your computer.
- Optional: [Context7](https://context7.com/), a free docs tool for your agent. It makes the agent's checks of current docs faster and more reliable. Without it, the agent reads the official websites.
- GitHub, Vercel and Supabase accounts once the app goes online, at the end of stage 3. The agent tells you when.
- A budget check for commercial apps. Free hosting and database plans may not allow a shop, or enough separate projects. The agent checks the current plans when it's time.

**Tip:** setup (stage 3) is the heaviest step. If your agent lets you choose how hard the model thinks (an effort or reasoning setting), a higher level helps here, though low worked in testing.

## Tested so far
- **Tested:** Claude Code desktop, from setup through planning, decisions, the first feature, and the first pieces of a shop (catalogue, photos, cart). The automatic checks passed on GitHub on the first push.
- **Not tested yet:** Codex, the hosted staging and production pipeline, and the launch stage.

Found a problem? [Open an issue](https://github.com/TechNomadCode/AI-Product-Development-Toolkit/issues).

<details>
<summary>What's different per tool</summary>

| | Claude Code (desktop and terminal) | Codex |
| --- | --- | --- |
| Reads the project rules from | `CLAUDE.md`, which imports `AGENTS.md` | `AGENTS.md` |
| Blocked commands | `.claude/settings.json` | `.codex/rules/default.rules` |
| Starting a fresh session | `/clear`, or a new session in the same folder (desktop app) | `/new` |
| Extras | Desktop app: previews the app in its Browser pane (`.claude/launch.json`). Worktree sessions get `.env.local` copied in (`.worktreeinclude`). | Network and Docker usually need your approval in its sandbox. |

Either way the agent can't reach production: the project never holds hosted credentials. The blocked commands are only a backstop.

</details>

<details>
<summary>Set up by hand instead</summary>

1. Download this repository as a ZIP (**Code → Download ZIP**) and unzip it.
2. Copy everything inside `starters/nextjs-supabase-vercel/project/` into your empty folder, including hidden files and folders.
3. Copy `prd-generation.md`, `Guided-UX-User-Flow.md` and `Guided-MVP-Concept-Definition.md` from `prompt-templates/` into your folder's `.kit/planning/`.
4. Open your agent in the folder and ask **what's next?**

</details>

<details>
<summary>How it works</summary>

- **The agent can't reach production.** You develop against a local database with stand-in payment and email services. Staging and production change only through CI or through you, and their credentials never sit on your computer.
- **Database changes before code.** Staging follows your main branch by itself, and production changes only when you start it. In both, the database is updated before the new code runs.
- **Each question when it matters.** Choices that shape the code are settled before any code. Everything else sits under *Deferred* in `docs/decisions.md` with a due moment.
- **Rules, not recipes.** The kit says what must be true and how to check it. The agent looks up how today's tools do it and writes the chosen setup, with its sources, into the folder it concerns.
- **Everything has one place.** `docs/plan.md` holds the stage, where you are and the pieces of work. `docs/decisions.md` holds the choices, and `KNOWN-ISSUES.md` the open problems. Git holds the history.
- **Only what's needed is loaded.** `AGENTS.md` loads every session. The agent reads only the current stage's file in `.kit/`, and each folder's own rules load when it works there.
- **One piece per session.** Every piece has acceptance criteria and tests, which are never weakened to pass. Risky pieces get an independent review, then one confirmation round at most.
- **The planning prompts are the same ones.** Stage 1 runs this toolkit's [PRD](../../prompt-templates/prd-generation/), [UX](../../prompt-templates/ux-user-flow/) and [MVP](../../prompt-templates/mvp-concept-definition/) prompts inside your agent. You can also run them in any AI chat on their own.

</details>
