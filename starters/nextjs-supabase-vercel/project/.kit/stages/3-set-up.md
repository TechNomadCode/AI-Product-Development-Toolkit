# Stage 3 of 5: Set up

Goal: a walking skeleton. The smallest real feature of the app works through every layer, with the checks, safety rules and project documents in place. Then you stop.

## Before you build
- Check *Deferred* in `docs/decisions.md` for items due now.
- Read `docs/decisions.md`, `docs/product/`, and the file in `.kit/modules/` for each module the decisions name.
- If a decision is missing, ask the owner. Don't guess anything `docs/decisions.md` should contain.
- Tell the owner which feature you'll use as the walking skeleton (the smallest real feature that stores data and shows it), and wait for their confirmation.

## Rules for this stage
- Look up every tool, library and platform setting in its current docs before you use it (see *Look it up* in `AGENTS.md`). Commit the lockfile.
- The stack below counts as approved by the owner. Install it without asking; ask before adding anything else.
- Never link the Supabase CLI to a hosted project, run Vercel CLI commands or ask for hosted credentials. You prepare the hosted setup; the owner carries it out.
- Write helper scripts in Node, not shell, so they work on Windows, macOS and Linux.
- Keep information in the places listed in `AGENTS.md`. Don't create other documents.

## 1. Project documents
- **Slices:** turn `docs/product/` into slices in `docs/plan.md`, in build order. Slice 1 is this set-up. Each slice must fit in one session. Mark a slice risky if it touches sign-in and permissions, payments, data migrations or live data. Use this format:
  ```markdown
  ### 2 · <title> · risk: normal · status: todo
  - **Goal:** <what a user can do once it's done>
  - **Acceptance:**
    - <an observable result>
    - <a failure case that must be handled>
  ```
- **Folder rules:** give `supabase/`, the tests folder and each module's folder an `AGENTS.md` with the rules for working there. For the database: how schema changes work, the grant rules and any gotchas. For tests: the layers, the fixtures and how to run a single test. For a module: its *Rules* section, adapted to the decisions. Next to each, add a `CLAUDE.md` containing only `@AGENTS.md`, so Claude Code loads it when it works in that folder.
- **README:** replace `README.md` with the app's own. Include a one-sentence description, a quick start (`npm ci`, `npm run db:start`, `npm run env:local`, `npm run dev`), the daily commands, how to change the database, an environments table (local, staging, production: database, providers, who changes it), the secrets to add, and where the main code lives.
- **AGENTS.md:** fill in the commands table.
- **.gitignore:** Next.js defaults, plus every `.env*` file except `.env.example`, plus `docs/records/`.

## 2. App
- **Stack:** Next.js App Router with strict TypeScript; Tailwind CSS with shared design tokens and shadcn/ui-style accessible components; React Hook Form with Zod, validating on the server as well; Supabase; Vitest, Testing Library and Playwright; GitHub Actions; Vercel.
- Routes and API handlers in `src/app/`, business operations in server-side modules, database access in one data layer, and shared UI kept apart from feature UI.
- Site-wide facts (name, URL, description, social links) in one module. Every page sets its own metadata.
- Privileged keys only in server code.

## 3. Local environment
- Pin Node in `.nvmrc`, and the Supabase CLI as a dev dependency.
- `env:local` writes `.env.local` from the running local stack only: local URLs, local keys, fake adapters. It won't overwrite a file it didn't write.
- One environment guard runs before every dev, build, test and database command. It stops when a database or API address isn't local, or when an adapter isn't a fake. Test both refusals.

## 4. Database
- The schema has one source of truth, following Supabase's current recommended workflow. Migrations and TypeScript types are generated from it, and the checks fail when they drift.
- Deny by default: revoke table and function access from the public API roles, then grant exactly what each role needs. Turn on row-level security for every table. Test the grants and policies in SQL, for each role.
- A seed that looks like production: realistic shape and scale, generated from the real data source if the decisions name one.

## 5. External services
- For each service in the decisions: an interface, a fake and the real implementation. Local runs and CI use the fake. Hosted environment variables select the real one. An unknown adapter name is an error.
- Real provider calls happen only on staging (in test mode) and in production. If a module needs a test against the provider's sandbox, make it a separate command that only the owner runs.

## 6. Commands
Create these npm scripts, leaving out any for modules the app doesn't have:

| Script | What it does |
| --- | --- |
| `dev`, `build`, `start` | Next.js, behind the environment guard |
| `doctor` | Checks the Node version, Git, Docker, the pinned Supabase CLI, the secret scanner, and whether the GitHub CLI is signed in |
| `env:local` | Writes `.env.local` from the running local stack |
| `db:start`, `db:stop` | Start and stop the local stack |
| `db:reset` | Rebuild the local database from migrations and seed (deletes local data) |
| `db:migration`, `db:types` | Generate a migration from the schema files; regenerate the types |
| `test:unit`, `test:integration`, `test:sql`, `test:e2e` | The four test layers |
| `verify` | Format check, lint, typecheck, unit tests and a production build |
| `verify:db` | Reset, schema lint, type drift, SQL tests and integration tests |
| `verify:secrets` | A secret scan of the full Git history |

## 7. Tests
Four layers, each with at least one real test of the walking-skeleton feature:
- **Unit** (Vitest and Testing Library): logic, validation, components.
- **Integration** (Vitest against the local database, with fakes): real operations, from the action to the database.
- **SQL** (pgTAP through the Supabase CLI): grants, row-level security and constraints, as each role.
- **End to end** (Playwright): against a production build, never the dev server, with an automated accessibility check on every page. Use stable selectors, and wait for visible conditions rather than fixed times.

Fixtures are deterministic. Fakes sit only at external boundaries.

## 8. CI
GitHub Actions on pull requests and on pushes to `main`, as separate jobs: `verify`; `verify:db`; `test:e2e`; a dependency audit that fails on production dependencies; `verify:secrets`.
- Minimal permissions, no stored checkout credentials, job timeouts, and superseded runs cancelled.
- Install from the lockfile. Use the local stack and fakes only, and refuse real credentials.
- Clean up containers and servers, even after a failure.

## 9. Staging and production pipeline
Prepare it; don't run it. These must be true:
1. Staging follows `main` by itself: after a merge, staging's database gets the new migrations first, then staging runs the new code.
2. Production changes only when the owner starts it, from a commit that passed CI: migrations first, then code.
3. No environment ever runs code before its database has that code's migrations. If the migration step fails, the code isn't deployed.
4. Staging uses the providers' test keys. Until launch, production has no live provider keys.
5. Each workflow gets only its own environment's credentials, for that one database, not an account-wide token, where the platform allows it.
6. No tool can copy hosted credentials to the development machine, such as an environment-variable sync.
7. Only the production domain can be indexed. Every other address, including staging and the host's default addresses, sends `noindex`.

Find the current way to achieve each of these in the Vercel, GitHub and Supabase docs. Write the chosen setup and its sources into `.github/workflows/AGENTS.md`, next to a `CLAUDE.md` containing `@AGENTS.md`. Write the owner's setup steps (accounts, connections, settings, secrets by name) into `README.md`, click by click and in an order that works: anything a step picks, such as a branch, exists before that step. For every setting and secret, name the site and the exact place, such as which GitHub or Vercel environment. Say when a change takes effect only after a redeploy. The workflows' structure must show rule 3: the deploy step can't run unless the migration step succeeded.

## 10. Agent tool files
These are already in the project. Check they still fit:
- `.claude/launch.json` runs `npm run dev` on the app's port (Claude Code desktop preview).
- `.claude/settings.json` (Claude Code) and `.codex/rules/default.rules` (Codex) block pushing, the hosted Supabase and Vercel commands, starting workflows and changing secrets. If the app adds another hosted CLI, block it in both.
- `.worktreeinclude` lists `.env.local`.

## Done when
- [ ] On a fresh clone, `npm ci`, `npm run db:start`, `npm run env:local` and `npm run dev` start the app locally, with fakes.
- [ ] `doctor`, `verify`, `verify:db` and `test:e2e` pass.
- [ ] The walking-skeleton feature works through schema, migration, types, grants, server code and UI, and has a test in each layer.
- [ ] Tests show the guard refusing a hosted database address and a real adapter.
- [ ] The CI workflow and the staging and production workflows exist and meet the rules in section 9, and `README.md` lists the owner's setup steps.
- [ ] `AGENTS.md` stays under about 100 lines, not counting blocks that tools add by themselves, and every folder with rules has its `AGENTS.md` and `CLAUDE.md`.
- [ ] Everything is committed locally. Nothing is pushed.

Then ask the *Deferred* items due now (the repository and the accounts), check the current plan limits in the providers' official pages, and set the Now block to **4 of 5 · Build**, with the owner's next steps under *Waiting on the owner*:
1. Create the repository and accounts, if they don't exist yet.
2. Follow the setup steps in `README.md`: connections, settings and secrets.
3. Push, open a pull request and wait for CI.
4. Merge, then confirm that staging got the migrations and then the code.

Report what exists and the check results, then stop.
