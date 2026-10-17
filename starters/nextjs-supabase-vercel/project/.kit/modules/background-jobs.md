# Module: background jobs

Use this module when work must happen after a request finishes and must not get lost: emails, follow-ups to payments, document generation, syncs with other systems.

## Ask now (stage 2)
- How soon background work must happen, if the product documents don't say. Choose the scheduler and its interval yourself from current docs, and record them.

## Later (put under *Deferred* with these due points)
- **Stage 5:** who gets alerted when jobs get stuck, and how.

## Rules (stage 3 copies these into the jobs folder's AGENTS.md)
1. Jobs live in a database table. Add a job in the same transaction as the change that causes it.
2. Workers claim jobs with a lease. Only the current lease holder may finish or fail a job, and a job whose lease expired can be claimed again.
3. Retries are limited, with growing delays. After the limit, a job is either dead (safe to run again) or unresolved (the outcome is unknown and someone must decide).
4. Every job is idempotent: running it twice has the same effect as running it once.
5. The worker endpoint requires a secret, and the public API roles can't touch the job tables or the claim functions.
6. A replay command runs dead jobs again and records the reason. Unresolved jobs are never replayed blindly.
7. Alert when jobs are overdue or the scheduler has stopped. An empty queue doesn't prove the scheduler runs.
8. Don't rely on framework features that run work after the response is sent for anything that must not get lost.
9. The scheduler's own history stays small. If it records every run, delete old records on a schedule; otherwise a run every minute can add hundreds of megabytes a year, close to a free database plan's limit.

## Tests
- **Integration:** concurrent workers claim different jobs; an expired lease is claimed again; the retry limit leads to dead; a replay runs exactly once.
- **SQL:** the privileges on the job tables and functions.

## Launch (stage 5)
- The scheduler runs in production, with its secret in the platform's secret store.
- The overdue-job alert has been tested with a fake failure that has no effect on customers.
