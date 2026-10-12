# PRD prompt

Step 2 of the [planning prompts](../README.md). The AI interviews you about your idea, then drafts a product requirements document (PRD).

**Prompt:** [prd.md](./prd.md)

## What you get

A draft PRD with an overview, goals, target users, user stories, functional and non-functional requirements, design considerations, success metrics, and open questions.

## What to bring

- **Your notes (required):** ideas, goals, features, problems, anything you have, however rough. They go between `--- BRAINDUMP START ---` and `--- BRAINDUMP END ---`. Did [user research](../1-user-research/)? Paste its `PRD Research Input` section here.
- **Product type and constraints (optional):** fill in the two bracketed lines under `TONE & CONSTRAINTS`, such as "a web app" or "3-month timeline", or delete them.

## How to use it

1. Open [prd.md](./prd.md) and copy it with the copy button at the top right of the file (**Copy raw content**).
2. In a text editor, replace the placeholders with your material.
3. Paste it into a new AI chat and answer its questions. It asks a few at a time, states its assumptions, and checks with you before it moves on.
4. When it offers to write the PRD, say yes. Review the draft and save it as a Markdown file: the next steps ask for it.

**In Claude Code or Codex?** The `/prd` [skill](../../README.md#skills) runs this same prompt and fills it in from your message or files.

## Good to know

- Rough notes are fine. The interview fills the gaps, and the more you share up front, the fewer questions it asks.
- Use a model that keeps a long conversation in view: the PRD is built from everything you said.
- The PRD is a draft. Check every requirement, especially any you don't remember agreeing to.

## Next step

[UX and user flow](../3-ux/): turn this PRD into screens and user flows. Or skip to the [MVP scope](../4-mvp-scope/) if the app has only a few screens.

← Previous: [User research](../1-user-research/) · [All planning prompts](../README.md)
