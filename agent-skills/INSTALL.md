# Install the skills (instructions for the agent)

The owner asked you to install this toolkit's skills, and you cloned this repository into a temporary folder. Install them into the owner's personal skills folder, so they work in every project.

1. **Find the skills folder.** Use the personal skills folder of the tool you're running in:

   | Tool | Personal skills folder |
   | --- | --- |
   | Claude Code | `~/.claude/skills/` |
   | Codex | `~/.agents/skills/` |

   On Windows, `~` is the user's home folder. Create the folder if it doesn't exist. If the owner asks for both tools, install into both folders.

2. **Copy each skill.** If the owner named specific skills, install only those. For each row below, copy the folder `agent-skills/<skill>/` from the clone to `<skills folder>/<skill>/`, including its `agents/` folder. Then copy the listed prompt files from the clone's `planning-prompts/` into that same installed folder, next to its `SKILL.md`.

   | Skill | Prompt files to copy in |
   | --- | --- |
   | `user-research` | `1-user-research/questionnaire.md`, `1-user-research/research-to-prd.md` |
   | `prd` | `2-prd/prd.md` |
   | `ux` | `3-ux/ux.md` |
   | `mvp-scope` | `4-mvp-scope/mvp-scope.md` |
   | `mvp-plan` | `5-mvp-plan/mvp-plan.md`, `5-mvp-plan/mvp-plan-lean.md` |
   | `test-plan` | `6-test-plan/test-plan.md` |
   | `nextjs-supabase-vercel` | none |
   | `remotion-video` | none |

3. **Don't overwrite the owner's own skills.** If `<skills folder>/<skill>/` already exists, look at its `SKILL.md`. If it contains the line `From the AI Product Development Toolkit`, it's an earlier install: replace the whole folder. Otherwise it's the owner's own skill with the same name: leave it untouched, skip that skill, and tell the owner.

   The `mvp` skill is now called `mvp-scope`. When you install `mvp-scope`, check `<skills folder>/mvp/` the same way: if it's an earlier install, delete it; otherwise leave it.

4. **Check.** Every installed folder has its `SKILL.md`, its `agents/openai.yaml` and all of its prompt files. If anything is missing, stop and tell the owner.

5. **Clean up.** Delete the temporary clone. Change nothing else on the owner's computer.

6. **Tell the owner,** in a few plain lines: which skills are installed and where, and how to run one: `/prd` in Claude Code, `$prd` in Codex. Skills run only when the owner calls them. If a skill doesn't show up yet, a new session loads it. To update the skills later, they paste the same install line again. If you removed an earlier `mvp` skill, say that `/mvp` is now `/mvp-scope`.
