# Planning prompts

Guided prompts that interview you, then write your plan. They work in any AI chat.

**New here?** Start with step 2, the [PRD prompt](./2-prd/). Do step 1 first if you have potential users you can ask.

| Step | Prompt | You bring | You get |
| --- | --- | --- | --- |
| 1. Research users | [User research](./1-user-research/) | A research brief, and later the responses | A questionnaire, then evidence for your PRD |
| 2. Define the product | [PRD](./2-prd/) | Your notes, however rough | A product requirements document |
| 3. Map the experience | [UX and user flow](./3-ux/) | Your PRD | Screens, user flows and interface specs |
| 4. Scope the first release | [MVP scope](./4-mvp-scope/) | Your PRD, and UX specs if you have them | The first assumption to test, and what's in and out |
| 5. Plan the build | [MVP build plan](./5-mvp-plan/), full or lean | Your PRD and MVP scope | A development plan, or a short build spec |
| 6. Plan testing | [Test plan](./6-test-plan/) | What you want to test | A test plan outline |

## How they work

Most prompts tell the AI to write a document straight away, so it fills every gap with guesses. These make it interview you first:

- **It asks before it writes.** A few targeted questions at a time.
- **It checks what it understood.** It states its assumptions and confirms them with you before moving on.
- **It drafts only once you agree.** The document is built from your answers.
- **Each step feeds the next.** Later prompts take your earlier documents as input, so the plan stays consistent.

## How to use a prompt

1. Open the prompt file and copy it with the copy button at the top right of the file (**Copy raw content**).
2. In a text editor, replace the placeholders, such as `[ <<< PASTE YOUR PRD HERE >>> ]`, with your material. Fill in or delete the bracketed lines under `TONE & CONSTRAINTS`.
3. Paste it into a new AI chat and answer its questions.
4. When it offers to write the document, say yes. Review it and save it as a Markdown file: later steps ask for it.

Each folder's guide says exactly what to bring and what you get.

## Tips

- Start a new chat for each prompt, and paste in the documents from earlier steps.
- Use a model that keeps a long conversation in view. Later steps paste in whole documents.
- Don't paste private information the AI doesn't need.
- The output is a draft. Review it before you rely on it.

## Use them in Claude Code or Codex

Each prompt also installs as a skill, such as `/prd`. The skill runs the same prompt and fills it in from your message or files. See [Skills](../README.md#skills).

## When you're ready to build

These prompts work on their own, with any AI chat and any stack. To build the product with an AI coding agent, the [AI App Starter](../starters/nextjs-supabase-vercel/) sets up a Next.js, Supabase and Vercel project. It runs the PRD, UX and MVP scope prompts inside your agent, or uses the documents you already made with them.
