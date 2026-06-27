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

## 🧠 MCP server — [sites-reviews-mcp](https://github.com/SitesReviewsTrust/sites-reviews-mcp)

A [Model Context Protocol](https://modelcontextprotocol.io) server that lets **AI assistants** (Claude and other MCP-compatible clients) look up trust scores and reviews on demand. Connect it to your assistant and you can ask things like *"Is this shop trustworthy?"* and get Sites.Reviews data in the answer.

This is the recommended path today for programmatic / AI-driven lookups (see the API note below).

---

## 🔌 API & widgets — [sites-reviews-api](https://github.com/SitesReviewsTrust/sites-reviews-api)

Programmatic and embeddable access to Sites.Reviews data. Current state, stated honestly:

- **Public structured data** — every business page ships **schema.org JSON-LD** (`aggregateRating` + `review`) you can read from `https://sites.reviews/businesses/{domain}`. This is machine-readable today, no key required.
- **Embeddable reviews widget** — embed your company's reviews on your own site. **Beta.**
- **There is no public JSON REST API yet.** If you need programmatic lookups, use the **[MCP server](https://github.com/SitesReviewsTrust/sites-reviews-mcp)** or read the JSON-LD. Watch the [api repo](https://github.com/SitesReviewsTrust/sites-reviews-api) for updates.

---

## 📊 Public data — schema.org JSON-LD

Each business page embeds structured data following [schema.org](https://schema.org) conventions, typically including:

- `aggregateRating` — the overall score and review count
- `review` — individual reviews with ratings and text

This makes business pages readable by search engines, AI assistants, and your own scripts. To consume it, fetch `https://sites.reviews/businesses/{domain}` and parse the `<script type="application/ld+json">` block.

> Exact field availability can vary by business and over time; treat the JSON-LD on each page as the source of truth.

---

## 🗂️ Repositories

| Repo | Purpose |
|---|---|
| [sites-reviews-docs](https://github.com/SitesReviewsTrust/sites-reviews-docs) | Documentation hub (cross-linking center) |
| [sites-reviews-extension](https://github.com/SitesReviewsTrust/sites-reviews-extension) | Browser extension |
| [sites-reviews-mcp](https://github.com/SitesReviewsTrust/sites-reviews-mcp) | MCP server for AI assistants |
| [sites-reviews-api](https://github.com/SitesReviewsTrust/sites-reviews-api) | API & embeddable widgets (beta) |
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
