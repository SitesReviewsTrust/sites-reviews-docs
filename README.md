<div align="center">

# Sites.Reviews — Documentation Hub

**Check a site before you trust or pay it.**

Independent catalog of company & website reviews, trust scores, and scam-checks — for Russia and worldwide.

[![Website](https://img.shields.io/badge/Website-sites.reviews-2563eb?style=for-the-badge)](https://sites.reviews)
[![Telegram](https://img.shields.io/badge/Telegram-@SitesReviews__bot-229ED9?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/SitesReviews_bot)
[![Public API](https://img.shields.io/badge/Public%20API-Live-16a34a?style=for-the-badge)](https://github.com/SitesReviewsTrust/sites-reviews-api)
[![Docs License: CC BY 4.0](https://img.shields.io/badge/Docs%20License-CC%20BY%204.0-lightgrey?style=for-the-badge)](./LICENSE)

**[Get started](./docs/getting-started.md) · [Ecosystem](./docs/ecosystem.md) · [Trust score](./docs/trust-score.md) · [API & tools](./docs/api-and-tools.md) · [FAQ](./docs/faq.md)**

</div>

---

## What is this?

**Sites.Reviews** is an independent platform that helps people decide who to trust online. Search any company or website to see its **trust score**, **real user reviews**, **AI-generated review summaries**, and **automated security/scam checks** (SSL, blacklists, domain age). For businesses, it's a place to build and manage online reputation. The catalog spans thousands of companies across Russian and global markets.

This repository — **`sites-reviews-docs`** — is the documentation hub and cross-linking center for the whole open-source ecosystem. If you (or your AI assistant) want to understand the project and find every surface, **start here**.

---

## 🧭 Ecosystem at a glance

| Surface | What it does | Link |
|---|---|---|
| 🌐 **Website** | Catalog, business pages, scam-check by domain, free SEO/webmaster tools, blog | [sites.reviews](https://sites.reviews) |
| 🔍 **Trust score / scam-check** | Enter any domain → trust score + security signals + reviews | [search on sites.reviews](https://sites.reviews) |
| 🤖 **Telegram bot** | Search, top, and trending companies right inside a chat | [@SitesReviews_bot](https://t.me/SitesReviews_bot) |
| 🧩 **Browser extension** | See a site's trust score on any page you visit (Chrome/Firefox) | [sites.reviews/extension](https://sites.reviews/extension) · [repo](https://github.com/SitesReviewsTrust/sites-reviews-extension) |
| 🔌 **Public REST API** | **Live, no-auth, read-only** JSON for trust scores, businesses & reviews | [sites-reviews-api](https://github.com/SitesReviewsTrust/sites-reviews-api) |
| 🧠 **MCP server** | Gives AI assistants (Claude, etc.) the same data over [MCP](https://modelcontextprotocol.io) | [sites-reviews-mcp](https://github.com/SitesReviewsTrust/sites-reviews-mcp) |
| 🧱 **Embeddable widget** | Drop your company's reviews onto your own site (beta) | [sites-reviews-api](https://github.com/SitesReviewsTrust/sites-reviews-api) |
| 📚 **Docs (this repo)** | Understand the whole project; find every surface | [sites-reviews-docs](https://github.com/SitesReviewsTrust/sites-reviews-docs) |

---

## ⚡ Quick links — "I want to…"

| I want to… | Use this |
|---|---|
| **Check a domain before I trust or pay it** | Search it on **[sites.reviews](https://sites.reviews)** |
| **Check a company from a chat** | The Telegram bot **[@SitesReviews_bot](https://t.me/SitesReviews_bot)** |
| **See trust scores while I browse** | The **[browser extension](https://sites.reviews/extension)** |
| **Read trust data programmatically** | The **[public REST API](./docs/api-and-tools.md#-public-rest-api-live)** (no key) |
| **Let my AI assistant check sites** | The **[MCP server](https://github.com/SitesReviewsTrust/sites-reviews-mcp)** (`npx -y sites-reviews-mcp`) |
| **Embed reviews on my own site** | The **[reviews widget](https://github.com/SitesReviewsTrust/sites-reviews-api)** (beta) |
| **Leave a review or add my company** | Do it on **[sites.reviews](https://sites.reviews)** (see the [FAQ](./docs/faq.md)) |

---

## 🛡️ How the Trust Score works (in short)

A business's trust score combines two kinds of signals:

1. **Community signals** — real user reviews and ratings on the platform, summarized (including AI-generated summaries to capture the overall sentiment quickly).
2. **Automated security/scam checks** — technical signals about the website itself:
   - **SSL/HTTPS** — is the connection secured with a valid certificate?
   - **Blacklists** — does the domain appear on known scam/abuse lists?
   - **Domain age** — brand-new domains are riskier than long-established ones.

Together these produce an at-a-glance score (0–10) that helps you judge whether a site is safe to trust or pay.

> Full breakdown in **[docs/trust-score.md](./docs/trust-score.md)**. Where the exact internal weighting isn't published, the docs say so and describe how such checks generally work.

---

## 🧑‍💻 Developers

Two read-only, no-key ways to build on Sites.Reviews data. The full REST reference lives in **[sites-reviews-api](https://github.com/SitesReviewsTrust/sites-reviews-api)**; the overview is in **[docs/api-and-tools.md](./docs/api-and-tools.md)**.

**1. Public REST API** — base `https://sites.reviews/api/public/v1` · no auth · CORS `*` · 60 req/min/IP.

```bash
# Trust score + rating for any domain
curl "https://sites.reviews/api/public/v1/check?domain=1ps.ru"
# → {"id":1841,"name":"…","trust_score":9.6,"avg_ratings":4.8,"total_reviews":34,…}
```

Endpoints: `GET /check?domain=` · `GET /business/{domain}` · `GET /reviews/{domain}` · `GET /search?q=`.

**2. MCP server** — same data for AI assistants (Claude, Cursor, etc.), zero install:

```bash
claude mcp add sites-reviews -- npx -y sites-reviews-mcp
```

Then ask your assistant *"Is 1ps.ru trustworthy?"* and it answers with Sites.Reviews data. → **[docs/api-and-tools.md](./docs/api-and-tools.md)**

---

## 📖 Documentation

| Page | What's inside |
|---|---|
| [docs/getting-started.md](./docs/getting-started.md) | Start here — separate tracks for users and developers |
| [docs/ecosystem.md](./docs/ecosystem.md) | Full surface map: website, bot, extension, API, MCP, widget |
| [docs/trust-score.md](./docs/trust-score.md) | How ratings and scam-checks work (SSL, blacklists, domain age, AI summaries) |
| [docs/api-and-tools.md](./docs/api-and-tools.md) | Developer overview: API + MCP + widget + extension, and when to use which |
| [docs/faq.md](./docs/faq.md) | Is it free? How are reviews verified? Is there an API? Rate limits? Data licensing? |

The full docs index is in **[docs/README.md](./docs/README.md)**.

---

## 🗂️ Repositories index

| Repo | Purpose |
|---|---|
| [sites-reviews-docs](https://github.com/SitesReviewsTrust/sites-reviews-docs) | This documentation hub (the page you're reading) |
| [sites-reviews-api](https://github.com/SitesReviewsTrust/sites-reviews-api) | Public REST API reference & embeddable widgets |
| [sites-reviews-mcp](https://github.com/SitesReviewsTrust/sites-reviews-mcp) | MCP server for AI assistants |
| [sites-reviews-extension](https://github.com/SitesReviewsTrust/sites-reviews-extension) | Browser extension — trust score on any site |
| [All repositories](https://github.com/orgs/SitesReviewsTrust/repositories) | Everything in the SitesReviewsTrust org |

---

## 🤝 Contributing

Improvements to these docs are welcome — fix a typo, clarify a section, or add an example. See **[CONTRIBUTING.md](./CONTRIBUTING.md)** and our **[Code of Conduct](./CODE_OF_CONDUCT.md)**. For the code surfaces (API, MCP, extension), open issues and PRs in their own repositories. Found a security issue? See **[SECURITY.md](./SECURITY.md)**.

## 📄 License

Documentation in this repository is licensed under **[CC BY 4.0](./LICENSE)** — share and adapt with attribution to **Sites.Reviews**.

---

## 🇷🇺 Кратко по-русски

**Sites.Reviews** — независимый каталог отзывов о компаниях и сайтах с рейтингом доверия. Помогает понять, кому можно доверять в интернете: **рейтинг доверия**, **реальные отзывы пользователей**, **AI-сводки отзывов** и **автоматические проверки на мошенничество** (SSL, чёрные списки, возраст домена). Главный принцип — **«проверь сайт, прежде чем доверять или платить»**.

Для разработчиков доступен **публичный REST API** (без ключа, только чтение): `https://sites.reviews/api/public/v1` — а для AI-ассистентов те же данные отдаёт **MCP-сервер** (`npx -y sites-reviews-mcp`). Подробности — в [docs/api-and-tools.md](./docs/api-and-tools.md).

- 🌐 Сайт — [sites.reviews](https://sites.reviews)
- 🤖 Telegram-бот — [@SitesReviews_bot](https://t.me/SitesReviews_bot)
- 🧩 Расширение для браузера — [sites.reviews/extension](https://sites.reviews/extension)
- 🔌 Публичный API и виджеты — [sites-reviews-api](https://github.com/SitesReviewsTrust/sites-reviews-api)
- 🧠 MCP-сервер для AI-ассистентов — [sites-reviews-mcp](https://github.com/SitesReviewsTrust/sites-reviews-mcp)

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
