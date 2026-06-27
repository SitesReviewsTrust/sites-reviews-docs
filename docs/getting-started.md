# Getting started

Two paths below — pick the one that fits you.

---

## 👤 For users — "Is this site safe to trust or pay?"

### 1. Check a domain on the website

Go to **[sites.reviews](https://sites.reviews)** and search the company name or domain (e.g. `example.com`). You'll see:

- the **trust score**,
- **user reviews** and an **AI summary** of them,
- **automated security checks** (SSL, blacklists, domain age).

Open the full business page at `https://sites.reviews/businesses/{domain}` for all the detail.

### 2. Check from a chat

Open the Telegram bot **[@SitesReviews_bot](https://t.me/SitesReviews_bot)** and search a company, or browse **top** and **trending** companies — handy when a link gets dropped in a group chat.

### 3. Check while you browse

Install the **[browser extension](https://sites.reviews/extension)** (Chrome/Firefox) to see a site's trust score **on the page you're visiting**, right when you're deciding whether to buy or sign up.

### 4. Leave a review or add your company

- **Leave a review** of a company you've dealt with directly on [sites.reviews](https://sites.reviews).
- **Add or claim your business** to start building reputation. See the [FAQ](./faq.md) for how reviews are handled and whether businesses can respond.

---

## 🛠️ For developers — using Sites.Reviews data

### Read structured data today (no key needed)

Every business page embeds **schema.org JSON-LD** with `aggregateRating` and `review`. Fetch the page and parse the JSON-LD:

```
GET https://sites.reviews/businesses/{domain}
```

Look for `<script type="application/ld+json">` in the HTML and read the `aggregateRating` / `review` fields. This is the simplest machine-readable access available right now.

### Let an AI assistant look things up — MCP server

Connect the **[sites-reviews-mcp](https://github.com/SitesReviewsTrust/sites-reviews-mcp)** server to Claude (or any MCP-compatible client) so your assistant can fetch trust scores and reviews on demand. See that repo's README for setup.

### Embed reviews on your own site — widget (beta)

The **[sites-reviews-api](https://github.com/SitesReviewsTrust/sites-reviews-api)** repo provides an embeddable reviews widget (currently in **beta**). Check the repo for current embed instructions.

### What's *not* available (yet)

There is **no public JSON REST API** at this time. For programmatic access, use the **MCP server** or the **JSON-LD** approach above, and watch the [api repo](https://github.com/SitesReviewsTrust/sites-reviews-api) for updates.

---

## Next steps

- Understand the project's surfaces → [ecosystem.md](./ecosystem.md)
- Understand the rating → [trust-score.md](./trust-score.md)
- Common questions → [faq.md](./faq.md)

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
