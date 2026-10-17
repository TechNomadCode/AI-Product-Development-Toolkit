# Module: transactional email

Use this module when the app sends email: confirmations, receipts, sign-in links, owner notifications.

## Ask now (stage 2)
- The provider.
- Which messages exist, who receives each one (customer or owner), and any attachments such as invoices or tickets.

## Later (put under *Deferred* with these due points)
- **Before the email test on staging:** the provider account, which the owner creates.
- **Stage 5:** the sending domain and the from and reply-to addresses.

## Rules (stage 3 copies these into the email folder's AGENTS.md)
1. Send through the job queue, not during a request. A request only adds a job.
2. Every send uses an idempotency key derived from its job and unique to its environment: staging and production may share one provider account, and their job IDs overlap. Every retry sends the identical message: the same recipient, subject, body and attachments. Generate attachments so the same input always produces the same bytes.
3. Know the provider's idempotency window. After it closes, an earlier attempt with an unknown result counts as unresolved and needs a decision; it's never retried blindly.
4. Escape every piece of customer text in HTML. Test with markup in names and addresses.
5. The fake adapter stores messages locally, and tests read them from there.
6. Alert the owner when a message fails for good.
7. Log no message bodies, and no more personal data than debugging needs.

## Tests
- **Unit:** rendering with hostile input, and the choice of recipient and subject.
- **Integration:** a state change adds the job; a retry sends the identical payload; a permanent failure raises the alert.
- **End to end:** each flow that sends email leaves the expected message in the fake outbox.

## Launch (stage 5)
- The sending domain is verified, with SPF, DKIM and DMARC set up as the provider describes.
- Production sends a real message to an inbox you control. Check that it doesn't land in spam.
- The failure alert has been tested.
