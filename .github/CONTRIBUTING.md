# Contributing

Thanks for helping improve the toolkit. The most useful contribution is a report of a step that was unclear or didn't work.

## Report a problem or suggest an idea

[Open an issue](https://github.com/TechNomadCode/AI-Product-Development-Toolkit/issues/new/choose) and pick a form. For questions, use [Discussions](https://github.com/TechNomadCode/AI-Product-Development-Toolkit/discussions). Share only small, non-sensitive examples: no private data, keys or client details.

## Pull requests

For anything bigger than a typo, open an issue first, so the change is agreed before you spend time on it.

Keep to how the toolkit works:

- **Prompts interview first.** They ask a few questions at a time, state their assumptions, and draft only after the person agrees.
- **Plain language.** Short sentences and no jargon, written for someone new to the topic.
- **Same guide layout.** Each prompt folder has a README with what you get, what to bring, how to use it, good to know, and the next step.
- **Prompt paths are used by the installers.** The [skills installer](../agent-skills/INSTALL.md), the [starter setup](../starters/nextjs-supabase-vercel/SETUP.md) and the starter's [planning stage](../starters/nextjs-supabase-vercel/project/.kit/stages/1-plan.md) copy prompt files by name. If you rename or move a prompt, update those files and the README links in the same pull request.
- **Edit prompts in `planning-prompts/`.** The skills and the starter run those files unchanged, so one edit reaches all of them.

Contributions are released under the repository's [MIT license](../LICENSE).
