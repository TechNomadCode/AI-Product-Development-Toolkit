# Stage 4 of 5: Build

Goal: the slices in `docs/plan.md`, one per session.

## Each session
1. Take the slice the Now block names, or the first open slice. Check *Deferred* in `docs/decisions.md` for items due before it, and ask those first.
2. If it won't fit in this session, split it in `docs/plan.md` first.
3. Build it. Run the narrow check while you work, then `verify`. Run `verify:db` after database changes and `test:e2e` after UI changes.
4. When you need a decision you can't make, ask the owner and record the answer in `docs/decisions.md`.
5. Problems outside the slice go into `KNOWN-ISSUES.md`, not into the slice.
6. Commit locally. Shorten the finished slice to its title line with "done" and the commit, and update the Now block. A risky slice gets "done" and the commit in its title line now, but keeps its full text until its independent review is settled, so the reviewer can check it against its acceptance criteria. Note the pending review in the Now block.
7. Tell the owner what to review and push. If the slice is marked risky, tell them to run an independent review first (see below).
8. If the slice uses an outside service (payments, email, sign-in, storage), propose the real check once it's on staging. Explain in plain words where the owner adds the provider's test keys for staging, what to click through on the staging site, and what a good result looks like. Look up the current steps; don't write them from memory. Say plainly that your own tests used a fake.

When a CI job fails, read the run with the GitHub CLI if it's signed in, and fix the cause. Otherwise, ask the owner for the log.

## Independent review of risky slices
Explain to the owner in plain words why a second look helps. Ask whether they have a second coding assistant, such as Codex when Claude Code built the slice, or the other way round. A different agent catches more; without one, a fresh session of the same agent works too. Then give them one line to paste into that session. For example: `Review the checkout work (slice 5 in docs/plan.md).` In that session you're the reviewer:
- Read only. Don't change any files.
- Scope: the slice's commits (find them in `docs/plan.md` or `git log`), or the uncommitted changes.
- Check them against the slice's acceptance criteria, `AGENTS.md`, and the `AGENTS.md` of each folder they touch.
- Look for wrong behavior on failure paths, gaps in security or data access, tests that would still pass if the code were wrong, and changes outside the slice.
- For each finding, give the severity, the file and line, a concrete failure scenario and how to confirm it. Label guesses as guesses.
- End with one verdict: **BLOCKER** or **NO BLOCKER**.

When the owner brings findings back to the building session, fix them, then suggest one confirmation review. After that, stop: anything still disputed is the owner's call, not another review round.

Once the review is settled, with or without findings, shorten the slice to its title line and clear the pending review from the Now block.

## Adding a module later
Ask the questions in the module's *Ask now* section, record the answers in `docs/decisions.md`, and put its *Later* items under *Deferred*. Give the module's folder an `AGENTS.md` with its *Rules* and a `CLAUDE.md` containing `@AGENTS.md`, then add the slices it needs.

## Done when
Every slice before *Launch* is done. Set the Now block to **5 of 5 · Launch**.
