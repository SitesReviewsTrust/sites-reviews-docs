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

All developer access is **read-only** and **needs no API key**. Full details in **[api-and-tools.md](./api-and-tools.md)**.

### Call the public REST API (no key)

Base URL `https://sites.reviews/api/public/v1` — no auth, CORS `*`, 60 req/min/IP.

```bash
# Trust score + rating for any domain
curl "https://sites.reviews/api/public/v1/check?domain=1ps.ru"
# → {"trust_score":9.6,"avg_ratings":4.8,"total_reviews":34, …}
```

From the browser (CORS is open):

```js
const r = await fetch("https://sites.reviews/api/public/v1/check?domain=1ps.ru");
const { trust_score, avg_ratings, total_reviews } = await r.json();
```

Endpoints: `GET /check?domain=` · `GET /business/{domain}` · `GET /reviews/{domain}` · `GET /search?q=`. Full reference: **[sites-reviews-api](https://github.com/SitesReviewsTrust/sites-reviews-api)**.

### Let an AI assistant look things up — MCP server

Connect the **[sites-reviews-mcp](https://github.com/SitesReviewsTrust/sites-reviews-mcp)** server so Claude (or any MCP-compatible client) can fetch the same data on demand — zero install:

```bash
claude mcp add sites-reviews -- npx -y @sitesreviews/mcp
```

### Embed reviews on your own site — widget (beta)

The **[sites-reviews-api](https://github.com/SitesReviewsTrust/sites-reviews-api)** repo provides an embeddable reviews widget (currently in **beta**). Check the repo for current embed instructions.

### Also available — schema.org JSON-LD

Every business page at `https://sites.reviews/businesses/{domain}` embeds **schema.org JSON-LD** (`aggregateRating` + `review`) — handy if you're already parsing the page (SEO tooling, rich snippets). For structured data, prefer the REST API above.

---

## Next steps

- Understand the project's surfaces → [ecosystem.md](./ecosystem.md)
- Build on the data (API + MCP + widget) → [api-and-tools.md](./api-and-tools.md)
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
