# Stage 5 of 5: Launch

Goal: the app live in production, checked part by part. Hosted changes are made by the owner or by CI: you prepare them and tell the owner exactly what to do.

Start by asking the *Deferred* items due now, in plain words: the domain, search engines, alerts, cookies and tracking, legal pages, tax and receipts, and anything else marked for stage 5. Then read `docs/decisions.md` and the *Launch* section of each module the app uses. Add each part below as a slice in `docs/plan.md`, skipping the parts the decisions say don't apply. Do one part per session. At the end of each part, report what's done and what the owner must do, then stop.

Each part says what must be true and how to check it. Find the current way to get there in the official docs of the services involved (see *Look it up* in `AGENTS.md`), and write the owner's steps from those docs, not from memory.

## Part 1 · Production environment
Must be true:
- Production has its own database, never a copy of staging. Its schema comes only from migrations, applied by the production workflow that the owner starts.
- The owner has added the production secrets and variables (you list them by name).
- `README.md` says which backups the database plan includes and how a restore works.
- Real data (a catalogue, content, accounts to import) goes in through a reviewed, repeatable script that CI or the owner runs, never from this machine.

**Check:** the production workflow has run, the production schema matches the repository, and production runs on the host's default address with `noindex`.

## Part 2 · Monitoring
Must be true:
- A health endpoint that isn't cached and sits behind no redirect. It returns 200 when the essential dependencies answer within a short timeout, and 503 when they don't. It shows no secrets or customer data.
- An uptime monitor watches it and alerts the person the decisions name, on failure and on recovery.
- With background jobs: alerts for overdue jobs and for a stopped scheduler. An empty queue doesn't prove the scheduler runs.

**Check:** a failure alert and a recovery alert have both arrived, triggered by a safe, fake failure.

## Part 3 · Security
Must be true:
- Security headers are set: HTTPS enforcement, frame protection, no MIME sniffing, a referrer policy and a permissions policy.
- A Content Security Policy chosen for this app. Look up the framework's current options and their cost; a stricter policy can force every page to render on each request. Choose knowingly, and record why.
- Public actions that send email or create records are rate-limited.
- The dependency audit and secret scan are clean, and the database provider's security advisors have been reviewed on production. Any exception the owner accepts goes into `KNOWN-ISSUES.md` with its reason.

**Check:** the headers and the policy are verified on the production address and covered by the browser tests.

## Part 4 · Search and discoverability
Skip this part if the app is private behind a sign-in. Use the current guidance of Google Search Central and Bing Webmaster Tools.

Must be true:
- Only the production domain can be indexed. Pages that must stay out of search, such as order confirmations, send `noindex` and stay crawlable; a page blocked from crawling can never show its `noindex`.
- Each page has one address: one main host (www or bare) that the other redirects to, and an absolute canonical URL on every page.
- Every page has its own title, description and sharing image in the rendered HTML, not ones inherited from a parent layout by accident.
- Structured data matches what the page shows, uses the types that fit (for example a business, products with prices, articles), and passes the search engines' own validators.
- The sitemap comes from the same data as the pages and lists only pages. A page's last-modified date changes only when its content really changes.
- If the site publishes posts, it has a feed linked from the page head, and post images meet the search engines' current size guidance.
- The search and AI crawlers the owner wants are allowed, both by `robots.txt` and by the host's firewall or bot settings.
- Optional: an `llms.txt` map of the site for AI tools, generated from the same data and sent with `noindex`. It's cheap to add, but don't expect much from it.
- The largest element on first load never waits for an animation. Check speed with several PageSpeed runs, because single runs vary.
- All content is real, never invented, and each page answers its visitor's question in the words people search for.

**At launch**, the owner does these, and you write the exact steps from current docs: verify the site in Google Search Console and Bing Webmaster Tools and submit the sitemap; set up instant indexing if Bing still supports IndexNow; request indexing for the most important pages.

**Check:** the validators pass, only the production domain is indexable, and both search engines have the sitemap.

## Part 5 · Privacy and legal
Must be true:
- An inventory lists the personal data the app collects: where it's stored, which services process it and how long it's kept.
- Non-essential cookies and tracking load only after consent, or not at all.
- Privacy, cookie and terms pages match what the app actually does. You draft them; they point to official sources, say what needs a lawyer's review, and never claim compliance.

**Check:** the pages exist and match the app's behavior, and any consent flow is covered by the browser tests.

## Part 6 · Readiness
Must be true:
- All checks pass on the release commit, in CI.
- Every module's *Launch* items are done.
- A written cutover plan lists each step in order, with how to check it and how to undo it.
- Production data starts clean: no test orders, users or content.

**Check:** the owner approves the cutover plan.

## Part 7 · Cutover
The owner does the hosted steps. After each one, you verify it:
- The domain and the redirect to the main host work, and DNS resolves correctly.
- The production domain is indexable, and every other address still sends `noindex`.
- If the app takes money: one real low-value purchase and a refund, with every email received.
- Monitoring is green, and the search engines have the sitemap.

**Check:** every item passes. Record the launch date in `docs/decisions.md`, and set the Now block's stage to **Live**. From then on, new work is added as slices and follows the session rules in `4-build.md`.

## For the owner, after launch
Tell the owner this once, at the end:
- Check Search Console once a month. Impressions rise before clicks. Specific searches can take weeks to show results, broad ones months.
- Links from relevant websites move rankings most: launch sites and directories, curated lists, and communities where the users are. When you republish an article elsewhere, publish it on your own site first, wait until it's indexed, and point the copy's canonical link to the original.
- Describe the product in the same words everywhere.
