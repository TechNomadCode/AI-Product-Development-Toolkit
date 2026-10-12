# MVP scope prompt

Step 4 of the [planning prompts](../README.md). The AI helps you pick the smallest first version worth building: the one assumption to test first, who it's for, and what's in and out. It picks from your PRD instead of inventing new requirements.

**Prompt:** [mvp-scope.md](./mvp-scope.md)

## What you get

A short MVP scope:

- The core hypothesis: the one assumption this first version tests
- The early adopters it's for, a narrow group from your PRD
- The problem it solves for them
- The minimum features, as an **In** and an **Out** list, each tied to your PRD or UX specs
- Constraints such as budget, timeline or tech
- Optionally, a first idea of how to measure success

## What to bring

- **Your PRD (required):** the full text, from the [PRD prompt](../2-prd/) or your own.
- **Your UX specs (optional):** from the [UX prompt](../3-ux/). They help when choosing features. If you have none, write "not providing".
- **Your first thoughts (required):** what you think the first version could be, however vague.

## How to use it

1. Open [mvp-scope.md](./mvp-scope.md) and copy it with the copy button at the top right of the file (**Copy raw content**).
2. In a text editor, paste your material between the `START` and `END` markers of the three inputs.
3. Paste it into a new AI chat and answer its questions. It starts with the hypothesis, then the audience and problem, then the features.
4. When it offers to write the MVP scope, say yes. Review it and save it as a Markdown file.

**In Claude Code or Codex?** The `/mvp-scope` [skill](../../README.md#skills) runs this same prompt and fills it in from your files.

## Good to know

- The AI helps you narrow down, but the scope is your call. Expect it to push you to leave things out.
- If it asks for something your PRD already answers, point it to the section.

## Next step

[MVP build plan](../5-mvp-plan/): plan the build, as a full development plan or a lean build spec for a fast first version.

← Previous: [UX and user flow](../3-ux/) · [All planning prompts](../README.md)
