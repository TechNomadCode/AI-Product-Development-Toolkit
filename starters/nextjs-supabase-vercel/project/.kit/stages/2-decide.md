# Stage 2 of 5: Decide

Goal: `docs/decisions.md` holds what stage 3 and the first pieces of work need, so you can build without guessing. Ask only what changes that code. Everything else goes under *Deferred* with a due point, and you don't mention it now. You don't design features: `docs/product/` covers those.

## How to run it
1. Read `docs/product/`. Don't ask what it already answers; confirm it in one short summary instead.
2. Ask the questions below that the documents leave open, 1–3 at a time, each with a recommendation and a one-sentence reason.
3. When the owner answers, write the decisions into `docs/decisions.md` right away, one line each, and ask the next questions in the same message. Read back first only when you filled in something the owner didn't say.
4. Before recommending a provider or tool, check its current docs (see *Look it up* in `AGENTS.md`).
5. Don't invent requirements. If the documents contradict each other, point it out and ask.

## Fixed rules
Explain these if the owner asks, but don't reopen them:
- Development uses a disposable local database and fake providers.
- Staging and production are separate hosted environments with their own databases. Production starts empty and is never a copy of staging.
- Hosted credentials live only in the hosting and CI settings, never on the development machine.
- Database changes reach staging and production only through CI. Production changes start only when the owner starts them.

## Ask now
**1. Who and what.** Who uses the app (visitors, guests, signed-in users, roles, admins) and what each can see and change. How people sign in, if they do. The main things the app stores, roughly how many, and any files or images. Real data to seed from, if there is any.

**2. Languages and markets.** The languages of the app and its emails, the countries it serves and the currencies.

**3. Outside services.** The provider for each service the first release needs: payments, email, background jobs, file storage. For each of payments, email and background jobs that applies, read its file in `.kit/modules/` and ask its *Ask now* questions. Record the modules that apply. Then explain in plain words how services get tested: you build and test against a fake; the owner puts the provider's test keys on staging and tries the real flow there; you never hold any keys.

## Put under Deferred, without asking
Record each with its due point. Bring it up only when it's due.

| Item | Due |
| --- | --- |
| The GitHub repository and whether it's public or private; the hosting and database accounts, their region and plan limits | End of stage 3, when the app goes online |
| Items in the modules' *Later* sections | Where each says |
| Deleting personal data on request, and how long data is kept | Before the first piece of work that stores personal data |
| The domain, search engines, alerts, cookies and tracking, legal pages, tax and receipts | Stage 5 |

Don't ask about coding assistants or test tools. The project works with Claude Code and Codex, and the test tools are part of the stack.

## Done when
The questions above are answered and written to `docs/decisions.md`, and the *Deferred* items are recorded. Set the Now block to **3 of 5 · Set up**.
