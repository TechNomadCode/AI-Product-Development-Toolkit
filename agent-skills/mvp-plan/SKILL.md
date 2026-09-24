---
name: mvp-plan
description: Plan the MVP build from a PRD and an MVP concept, as a full development plan or an ultra-lean build spec, with the AI Product Development Toolkit's planning prompts.
disable-model-invocation: true
---

<!-- From the AI Product Development Toolkit (https://github.com/TechNomadCode/AI-Product-Development-Toolkit). Paste its skills install line again to update. -->

This skill has two prompts in its folder. Unless the owner's message makes it clear, ask which one they need:

- `Guided-MVP.md`: a full development plan, with scope, tech stack, phases, testing and success metrics.
- `Guided-Ultra-Lean-MVP.md`: a short build spec for a fast first version, with purpose, user, features and tech choices.

If a file is missing, tell the owner to install the skills again. Then run the prompt:

- Read it in full and follow it exactly, as if the owner had pasted it.
- Fill its placeholders from the owner: use what's in their message or the files they point to, and ask for the rest. Don't guess.
- When the owner approves the draft, offer to save it as a Markdown file.
