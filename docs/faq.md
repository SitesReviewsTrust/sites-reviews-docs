# FAQ

> Answers reflect how the platform works. Where exact internal policy isn't published, the answer is phrased generally — when in doubt, the behaviour on [sites.reviews](https://sites.reviews) is the source of truth.

---

### Is it free?

Yes — checking a company's trust score, reading reviews, and running a domain scam-check on [sites.reviews](https://sites.reviews) are free for users. The Telegram bot and browser extension are free too.

### How are reviews verified?

Reviews come from real users sharing their experiences. The platform applies moderation to keep reviews genuine and combines them with **automated technical checks** (SSL, blacklists, domain age) and **AI summaries** so a single fake or one-off review doesn't dominate the overall picture. The trust score is meant to reflect the *pattern* across many signals, not any single review.

### Can businesses respond to reviews?

Reputation platforms like this are designed for two-way engagement — a business builds reputation by being present and responsive. If you represent a company, claim/add your business on [sites.reviews](https://sites.reviews) to manage your presence; check the on-site options for the current ways to engage with reviewers.

### How do I add my company?

Go to [sites.reviews](https://sites.reviews), search for your company, and follow the prompts to add or claim it. If it isn't listed yet, you can add it so customers can find and review it. This is how you start building your online reputation on the platform.

### What does the trust score actually measure?

It blends **community signals** (user reviews + AI summaries) with **automated security/scam checks** (SSL/HTTPS, blacklists, domain age) into one at-a-glance rating. Full details in [trust-score.md](./trust-score.md).

### A site has no reviews — is it safe?

Not necessarily. No reviews plus a young domain just means there isn't enough signal yet. Absence of bad reviews is **not** proof of trust — be cautious and cross-check before paying or sharing personal data.

### Does Sites.Reviews cover non-Russian companies?

Yes. The catalog spans Russian and global markets, with thousands of companies.

### Is there a public API I can call?

**Yes.** There's a live, **no-auth, read-only** REST API at `https://sites.reviews/api/public/v1`:

```bash
curl "https://sites.reviews/api/public/v1/check?domain=1ps.ru"
```

Endpoints: `GET /check?domain=` · `GET /business/{domain}` · `GET /reviews/{domain}` · `GET /search?q=`. CORS is open (`*`), so you can call it from browser JavaScript. The full reference lives in the **[sites-reviews-api](https://github.com/SitesReviewsTrust/sites-reviews-api)** repo; see also **[api-and-tools.md](./api-and-tools.md)**. (Every business page also embeds **schema.org JSON-LD**, and an **embeddable reviews widget** is in **beta**.)

### What are the API rate limits?

**60 requests per minute per IP.** Responses include `X-RateLimit-Limit` / `X-RateLimit-Remaining` headers, and they're cached for about 5 minutes — so cache on your side and you'll rarely hit the limit. Exceeding it returns HTTP `429`. No key is required.

### How can my AI assistant use Sites.Reviews?

Connect the **[MCP server](https://github.com/SitesReviewsTrust/sites-reviews-mcp)** to Claude or another MCP-compatible client — it serves the same data as the REST API as callable tools. Zero install:

```bash
claude mcp add sites-reviews -- npx -y sites-reviews-mcp
```

Then ask your assistant about a site's reputation and it answers with Sites.Reviews data.

### Can I reuse the data — what's the licence?

The **documentation** in this repo is **[CC BY 4.0](../LICENSE)**. When you display data from the API or business pages, attribute "Sites.Reviews" and link back. Don't republish wholesale copies of the catalog or scrape around the rate limit — use the API as intended. For commercial or high-volume use, reach out via the website.

### I think a rating or review is wrong — how do I report it?

Open the business page on [sites.reviews](https://sites.reviews) and use the on-site report/flag option for the specific review or business. Inaccurate technical signals (e.g. a wrong SSL or blacklist flag) are best reported the same way, from the page where they appear. For bugs or inaccuracies in **this documentation**, open an issue in [sites-reviews-docs](https://github.com/SitesReviewsTrust/sites-reviews-docs/issues). Please don't post personal data in public issues.

### Is this open source?

The client-facing surfaces — docs, extension, MCP server, and API/widgets — are open source under the [SitesReviewsTrust org](https://github.com/orgs/SitesReviewsTrust/repositories). Contributions are welcome.

---

## 🔗 Sites.Reviews ecosystem
- 🌐 **Website** — https://sites.reviews
- 🔍 **Trust score / scam-check** — search any domain on [sites.reviews](https://sites.reviews)
- 🤖 **Telegram bot** — [@SitesReviews_bot](https://t.me/SitesReviews_bot)
- 🧩 **Browser extension** — [sites.reviews/extension](https://sites.reviews/extension) · [repo](https://github.com/SitesReviewsTrust/sites-reviews-extension)
- 📚 **Docs** — [sites-reviews-docs](https://github.com/SitesReviewsTrust/sites-reviews-docs)
- 🔌 **API & widgets** — [sites-reviews-api](https://github.com/SitesReviewsTrust/sites-reviews-api)
- 🧠 **MCP server** — [sites-reviews-mcp](https://github.com/SitesReviewsTrust/sites-reviews-mcp)
- 🏛 **All repositories** — https://github.com/orgs/SitesReviewsTrust/repositories
