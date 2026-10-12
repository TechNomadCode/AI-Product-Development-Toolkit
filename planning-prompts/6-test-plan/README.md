# Test plan prompt

Step 6 of the [planning prompts](../README.md). The AI helps you plan how to test a feature, a release or your MVP.

**Prompt:** [test-plan.md](./test-plan.md)

## What you get

A test plan outline:

- The objective, and what's in and out of scope
- The features to test
- The kinds of testing and the approach, such as functional, usability, performance or security, manual or automated
- Test environments and test data
- Who runs the tests, and how bugs are reported
- What the testing produces, such as test cases and reports
- Entry and exit criteria: when testing can start, and when it's done
- Risks to the testing and how to handle them
- Optionally, tools and a schedule

It's an outline, not a list of test cases. Write those from it afterwards, or ask the AI to in the same chat.

## What to bring

- **What to test (required):** the features, requirements, user stories or MVP spec for this round of testing. Add context from your PRD if it helps.
- **Constraints (optional):** fill in the bracketed line under `TONE & CONSTRAINTS`, such as limited time, no dedicated testers or a required bug tracker, or delete it.

## How to use it

1. Open [test-plan.md](./test-plan.md) and copy it with the copy button at the top right of the file (**Copy raw content**).
2. In a text editor, replace the example between `--- SCOPE START ---` and `--- SCOPE END ---` with what you want to test.
3. Paste it into a new AI chat and answer its questions. It starts with the objective and scope, then moves through the rest of the plan.
4. When it offers to write the outline, say yes. Review it and save it as a Markdown file.

**In Claude Code or Codex?** The `/test-plan` [skill](../../README.md#skills) runs this same prompt and fills it in from your files.

## Good to know

- Be specific about scope. The clearer the list of what's in, the more useful the plan.
- Update the plan as requirements change or bugs turn up.

## Next step

This is the last planning step. Ready to build? The [AI App Starter](../../starters/nextjs-supabase-vercel/) builds a web app with you, step by step, using the documents you made.

← Previous: [MVP build plan](../5-mvp-plan/) · [All planning prompts](../README.md)
