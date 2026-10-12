# Stage 1 of 5: Plan

Goal: product documents in `docs/product/` that the next stages build from, in the owner's own words. Don't invent requirements.

## First: ask for existing documents
Before anything else, ask the owner whether they already have a PRD, an MVP scope, a UX specification or notes. If they do, save them in `docs/product/`. Read them, tell the owner what's clear and what's missing, and run only the interviews below that fill a real gap.

## Then: interview the owner where documents are missing
Each interview uses a prompt template in `.kit/planning/`. Never run an interview from memory:
- At the start of each interview, read the template file in full. Then explain it to the owner in plain words: what this conversation is for, what they'll have at the end, roughly how long it takes, and that they can stop and continue later. For example: "I'll ask you about your idea: who it's for, what it should do, how people pay. From your answers I'll write a product description (developers call it a PRD) that everything we build follows. It usually takes 20–40 minutes, and we can pause any time."
- If the template file is missing, stop and tell the owner. Don't improvise a replacement.
- Follow its role, process and output structure exactly, and build the saved document on the template's structure.
- Fill its input sections from the owner's answers and from the documents already in `docs/product/`.
- Ask 1–3 questions at a time, as the template says.
- Don't paste the template to the owner.

| Order | Template | Save to | When |
| --- | --- | --- | --- |
| 1 | `prd.md` | `docs/product/prd.md` | Always |
| 2 | `ux.md` | `docs/product/ux.md` | If the app has more than a few screens. Ask the owner. |
| 3 | `mvp-scope.md` | `docs/product/mvp.md` | Always |

In the PRD template, the product type is a web application built with Next.js, Supabase and Vercel. Ask the owner for any other constraints.

Save each document once the owner approves its draft. An interview can take a whole session; update the Now block between sessions so the next one picks up where you left off.

If the owner wants to test the idea with real people first, point them to the user research prompts in the AI Product Development Toolkit. That work happens outside this project.

## Done when
`docs/product/prd.md` and `docs/product/mvp.md` exist and the owner has approved them. Set the Now block to **2 of 5 · Decide** and tell the owner what that stage involves.
