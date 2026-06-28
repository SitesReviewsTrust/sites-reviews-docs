# Sites.Reviews ecosystem — full surface map

Sites.Reviews is more than a website — it's a set of surfaces that all answer the same question: **"Can I trust this site before I pay or share data with it?"** This page maps every surface, what it's for, and where to get it.

---

## 🌐 Website — [sites.reviews](https://sites.reviews)

The home of the catalog. From the website you can:

- **Search any company or domain** to see its trust score, reviews, and security signals.
- **Browse business pages** at `https://sites.reviews/businesses/{domain}` — each page shows the aggregate rating, individual reviews, and automated checks.
- **Run a scam-check** by entering a domain — the platform evaluates technical risk signals (SSL, blacklists, domain age) alongside community reviews.
- **Use free SEO / webmaster tools** at [sites.reviews/tools](https://sites.reviews/tools).
- **Read the blog** for guides on spotting scams and building online reputation.
- **Leave a review** or **claim/add your company** to build reputation.

---

## 🤖 Telegram bot — [@SitesReviews_bot](https://t.me/SitesReviews_bot)

Bring trust checks into any Telegram chat. The bot lets you:

- **Search** a company or domain and get its trust score and review snapshot.
- See **top** and **trending** companies.

Useful when someone shares a link in a chat and you want a quick reputation read without leaving Telegram.

---

## 🧩 Browser extension — [sites.reviews/extension](https://sites.reviews/extension)

> Repo: [SitesReviewsTrust/sites-reviews-extension](https://github.com/SitesReviewsTrust/sites-reviews-extension)

A Chrome/Firefox extension that surfaces a site's **trust score on the page you're actually visiting** — so you see the reputation signal at the moment of decision (before you check out, sign up, or pay). Open-source; contributions and issues welcome in its repo.

---

## 🔌 Public REST API — [sites-reviews-api](https://github.com/SitesReviewsTrust/sites-reviews-api)

**Live.** A no-auth, read-only JSON API for trust scores, business profiles, and reviews.

- **Base URL:** `https://sites.reviews/api/public/v1`
- **No API key**, CORS `*` (call it from browser JS), **60 req/min/IP**, responses cached ~5 min.
- **Endpoints:** `GET /check?domain=` · `GET /business/{domain}` · `GET /reviews/{domain}` · `GET /search?q=`

```bash
curl "https://sites.reviews/api/public/v1/check?domain=1ps.ru"
```

This is the recommended path for programmatic lookups. Full reference lives in the **[sites-reviews-api](https://github.com/SitesReviewsTrust/sites-reviews-api)** repo; an overview with examples is in **[api-and-tools.md](./api-and-tools.md)**.

---

## 🧠 MCP server — [sites-reviews-mcp](https://github.com/SitesReviewsTrust/sites-reviews-mcp)

A [Model Context Protocol](https://modelcontextprotocol.io) server that gives **AI assistants** (Claude and other MCP-compatible clients) the **same data** as the REST API, on demand. Connect it and you can ask *"Is this shop trustworthy?"* and get Sites.Reviews data in the answer. Zero install:

```bash
claude mcp add sites-reviews -- npx -y sites-reviews-mcp
```

Use the **REST API** when your code needs the data; use the **MCP server** when a language model does. See [api-and-tools.md](./api-and-tools.md#-mcp-server-for-ai-assistants).

---

## 🧱 Embeddable reviews widget — [sites-reviews-api](https://github.com/SitesReviewsTrust/sites-reviews-api)

Embed your company's reviews on your own site with a copy-paste snippet. **Beta** — see the [api repo](https://github.com/SitesReviewsTrust/sites-reviews-api) for current embed instructions.

---

## 📊 Public data — schema.org JSON-LD

Each business page embeds structured data following [schema.org](https://schema.org) conventions, typically including:

- `aggregateRating` — the overall score and review count
- `review` — individual reviews with ratings and text

This makes business pages readable by search engines, AI crawlers, and your own scripts. To consume it, fetch `https://sites.reviews/businesses/{domain}` and parse the `<script type="application/ld+json">` block.

> For structured programmatic access, prefer the **[public REST API](#-public-rest-api--sites-reviews-api)** — use JSON-LD when you're already parsing the page (SEO tooling, rich snippets). Exact field availability can vary by business and over time; treat the live data as the source of truth.

---

## 🗂️ Repositories

| Repo | Purpose |
|---|---|
| [sites-reviews-docs](https://github.com/SitesReviewsTrust/sites-reviews-docs) | Documentation hub (cross-linking center) |
| [sites-reviews-extension](https://github.com/SitesReviewsTrust/sites-reviews-extension) | Browser extension |
| [sites-reviews-api](https://github.com/SitesReviewsTrust/sites-reviews-api) | Public REST API reference & embeddable widgets |
| [sites-reviews-mcp](https://github.com/SitesReviewsTrust/sites-reviews-mcp) | MCP server for AI assistants |
| [All repositories](https://github.com/orgs/SitesReviewsTrust/repositories) | The full SitesReviewsTrust org |

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
