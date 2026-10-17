# Setup (instructions for the agent)

The owner asked you to set up a new project with the AI App Starter, and you cloned this repository into a temporary folder. Work in the folder where your session started: that's the project folder, not the clone.

1. **Check the project folder.** It must be empty, or contain only `.git`. If anything else is there, list it and ask the owner before you continue. Never overwrite their files.
2. **Copy the starter.** Copy everything inside `starters/nextjs-supabase-vercel/project/` from the clone into the project folder. Include hidden files and folders: `.claude`, `.codex`, `.kit`, `.gitattributes` and `.worktreeinclude`.
3. **Copy the planning prompts.** Copy these files from the clone's `planning-prompts/` into the project's `.kit/planning/`:
   - `2-prd/prd.md`
   - `3-ux/ux.md`
   - `4-mvp-scope/mvp-scope.md`
   Check that all three files now exist in `.kit/planning/`. If one is missing, stop and tell the owner.
4. **Record the version.** Write one line to `.kit/VERSION`: today's date, the clone's commit hash, and `AI-Product-Development-Toolkit`.
5. **Clean up.** Delete the temporary clone. Copy nothing else from it.
6. **Start Git.** If the project folder isn't a Git repository yet, run `git init`. Commit everything with the message `Start from the AI App Starter`. Don't add a remote and don't push.
7. **Load the rules.** Files copied during a session don't load by themselves until the next session. Read the project's `AGENTS.md` now and follow it from here on. If you're Claude Code, read `CLAUDE.md` too.
8. **Start.** Tell the owner the setup is done in two sentences. Add one sentence on your limits: you work only on this computer with a local database and fake providers, so you never use hosted credentials or API keys, not even test keys, and the owner does those steps while you prepare them. Then explain in plain words how you'll work together: first you talk through the idea, then settle a few practical choices, then build the app one piece at a time, then launch it. At every step you'll say what you need from them. If personal instructions you've loaded conflict with `AGENTS.md` in a way that changes how you work here, name each in one plain line, say the project's rule applies here, and let the owner overrule it. If there's no conflict, say nothing about it. Then begin the stage named in `docs/plan.md`.
