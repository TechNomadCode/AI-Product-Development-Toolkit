# MVP build plan prompts

Step 5 of the [planning prompts](../README.md). The AI turns your PRD and MVP scope into a plan for building it. Pick one of two versions:

| Prompt | Use it when | You get |
| --- | --- | --- |
| [mvp-plan.md](./mvp-plan.md) | You want timeline, testing, metrics and risks planned | A full development plan |
| [mvp-plan-lean.md](./mvp-plan-lean.md) | You want to start building now | A short build spec: purpose, user, features and tech |

## What you get

**From the full plan:**

- The MVP goal and hypothesis, and its target users
- The core features, prioritized as **In** and **Out**
- The tech stack, with reasons
- Development phases with rough time estimates
- Testing strategy and deployment approach
- Success metrics with targets
- Risks and how to handle them
- Optionally, team roles and a budget outline
- What to decide after the MVP: iterate, pivot, expand or stop

**From the lean build spec:**

- The core purpose of this build, tied to your PRD
- Who uses this first version
- The features to build now
- The key technology choices, picked for speed and simplicity
- Optionally, the first one to three build tasks

The lean version leaves out metrics, testing, timelines and risks on purpose.

## What to bring

- **Your PRD (required):** the full text, from the [PRD prompt](../2-prd/) or your own.
- **Your MVP scope (required):** from the [MVP scope prompt](../4-mvp-scope/), or your own description of the hypothesis, first users, minimum features and constraints. Keep it short for the lean version.
- **Product type and constraints (optional):** fill in the two bracketed lines under `TONE & CONSTRAINTS`, or delete them.

## How to use it

1. Open [mvp-plan.md](./mvp-plan.md) or [mvp-plan-lean.md](./mvp-plan-lean.md) and copy it with the copy button at the top right of the file (**Copy raw content**).
2. In a text editor, paste your PRD and MVP scope between their `START` and `END` markers.
3. Paste it into a new AI chat and answer its questions. The full version settles the goal and features first, then the tech stack, then phases, testing and metrics. The lean version asks one or two direct questions at a time and makes reasonable assumptions to keep moving, stating each one.
4. When it offers to write the plan, or once the features and tech are settled in the lean version, ask for the document. Review it and save it as a Markdown file.

**In Claude Code or Codex?** The `/mvp-plan` [skill](../../README.md#skills) asks which version you need, then runs it and fills it in from your files.

## Good to know

- Don't need team roles or a budget in the full plan? Tell it to skip them.
- The lean version moves fast by assuming common practice. Correct any assumption that doesn't fit.
- Time estimates are rough. Expect the plan to change once you start building and learning.

## Next step

[Test plan](../6-test-plan/): plan how to test what you build.

← Previous: [MVP scope](../4-mvp-scope/) · [All planning prompts](../README.md)
