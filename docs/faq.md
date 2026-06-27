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

There is **no public JSON REST API yet.** You can: (1) read **schema.org JSON-LD** from each business page (`https://sites.reviews/businesses/{domain}`), or (2) use the **[MCP server](https://github.com/SitesReviewsTrust/sites-reviews-mcp)** for AI-assistant lookups. An **embeddable reviews widget** is available in **beta** via the [api repo](https://github.com/SitesReviewsTrust/sites-reviews-api). See [getting-started.md](./getting-started.md#-for-developers--using-sitesreviews-data).

### How can my AI assistant use Sites.Reviews?

Connect the **[MCP server](https://github.com/SitesReviewsTrust/sites-reviews-mcp)** to Claude or another MCP-compatible client. Your assistant can then look up trust scores and reviews when you ask about a site.

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
