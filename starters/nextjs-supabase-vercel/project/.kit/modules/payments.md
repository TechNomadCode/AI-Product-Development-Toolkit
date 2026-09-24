# Module: payments

Use this module when the app takes money through a payment provider: a checkout, subscriptions or deposits.

## Ask now (stage 2)
- The provider, and whether payments are one-off, subscriptions or both.

## Later (put under *Deferred* with these due points)
- **Before the first payment piece of work:** the refund and cancellation policy; who pays the provider's fees; receipts or invoices, who issues them and their numbering rules. These are legal and tax questions: show options with official sources, don't decide.
- **Before the payment test on staging:** the provider's test account, which the owner creates.
- **Stage 5:** the live account. Live keys go only into production.

## Rules (stage 3 copies these into the payments folder's AGENTS.md)
1. The server computes every amount: prices, discounts, shipping, tax and totals. Never trust an amount sent by the browser.
2. Orders and payments follow a written state machine with its allowed transitions, for example pending → paid → fulfilled and pending → expired. State changes happen only through those transitions, atomically in the database.
3. Create the order and its payment attempt in one database transaction, not in steps that later have to be undone.
4. Every provider call that creates or captures a payment sends an idempotency key derived from your own attempt ID, with a different key per operation.
5. Treat a webhook as a notification. Verify it the way the provider documents, by signature or by fetching the payment from the provider, before you change any state. Receiving the same event twice must change nothing the second time.
6. Page loads and redirects never move money or change payment state. If the buyer comes back before the webhook arrives, show a "confirming" state that updates by itself, not a failure with a retry button.
7. Before creating a replacement payment, confirm with the provider that the old one can no longer be paid. If the answer is unknown, hold; don't retry.
8. Fulfilment (emails, invoices, stock) starts only from a confirmed paid state, through the job queue.
9. Invoice numbers come from the database, following the numbering rules in the decision record, never from random IDs.
10. Keep a way to see stuck payments and resolve them, at least as a read-only list.
11. The fake adapter covers every path the real provider can take: success, failure, cancellation, expiry, a duplicate webhook and a late webhook.

## Tests
- **Unit:** the state transitions and the amount calculations.
- **Integration** (local database, fake provider): a duplicate webhook causes one state change; a retry after a lost response creates one provider session; concurrent confirmations cause one fulfilment.
- **SQL:** the payment tables deny the public API roles.
- **End to end:** checkout, fake provider, "confirming", paid. Include cancellation and failure.
- **Contract** (you run it with the provider's test keys, never in CI): each provider's real test mode, once before launch and after any change to the provider code.

## Launch (stage 5)
- Live keys and webhook addresses exist only in production, and test mode is off there.
- Webhooks reach production, not a login page from deployment protection, and their signing secret matches.
- After the cutover, make one real low-value purchase and refund it.
