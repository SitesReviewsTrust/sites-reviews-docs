<div align="center">

# Sites.Reviews — Documentation Hub

**Check a site before you trust or pay it.**

Independent catalog of company & website reviews, trust ratings, and scam-checks — for Russia and worldwide.

[![Website](https://img.shields.io/badge/Website-sites.reviews-2563eb?style=for-the-badge)](https://sites.reviews)
[![Telegram](https://img.shields.io/badge/Telegram-@SitesReviews__bot-229ED9?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/SitesReviews_bot)
[![License: CC BY 4.0](https://img.shields.io/badge/Docs%20License-CC%20BY%204.0-lightgrey?style=for-the-badge)](./LICENSE)

</div>

---

## What is this?

**Sites.Reviews** is an independent platform that helps people decide who to trust online. Search any company or website to see its **trust score**, **real user reviews**, **AI-generated review summaries**, and **automated security/scam checks** (SSL, blacklists, domain age). For businesses, it's a place to build and manage online reputation. The catalog covers thousands of companies across Russian and global markets.

This repository — **`sites-reviews-docs`** — is the documentation hub and cross-linking center for the whole open-source ecosystem. If you (or your AI assistant) want to understand the project and find every surface, start here.

---

## 🧭 Ecosystem at a glance

| Surface | What it does | Link |
|---|---|---|
| 🌐 **Website** | Catalog, business pages, scam-check by domain, free SEO/webmaster tools, blog | [sites.reviews](https://sites.reviews) |
| 🔍 **Trust score / scam-check** | Enter any domain → trust score + security signals + reviews | [search on sites.reviews](https://sites.reviews) |
| 🤖 **Telegram bot** | Search, top, and trending companies right inside a chat | [@SitesReviews_bot](https://t.me/SitesReviews_bot) |
| 🧩 **Browser extension** | See a site's trust score on any page you visit (Chrome/Firefox) | [sites.reviews/extension](https://sites.reviews/extension) · [repo](https://github.com/SitesReviewsTrust/sites-reviews-extension) |
| 🧠 **MCP server** | Lets AI assistants (Claude, etc.) look up trust scores & reviews | [sites-reviews-mcp](https://github.com/SitesReviewsTrust/sites-reviews-mcp) |
| 🔌 **API & widgets** | Programmatic / embeddable access (public structured data + embeddable reviews widget, beta) | [sites-reviews-api](https://github.com/SitesReviewsTrust/sites-reviews-api) |
| 📚 **Docs (this repo)** | Understand the whole project; find every surface | [sites-reviews-docs](https://github.com/SitesReviewsTrust/sites-reviews-docs) |

---

## ⚡ Quick links — "I want to…"

- **…check a domain before I trust or pay it** → search it on **[sites.reviews](https://sites.reviews)**
- **…check a company from a chat** → use the Telegram bot **[@SitesReviews_bot](https://t.me/SitesReviews_bot)**
- **…see trust scores while I browse** → install the **[browser extension](https://sites.reviews/extension)**
- **…ask my AI assistant about a site's reputation** → connect the **[MCP server](https://github.com/SitesReviewsTrust/sites-reviews-mcp)**
- **…embed reviews on my own site / read data programmatically** → see **[API & widgets](https://github.com/SitesReviewsTrust/sites-reviews-api)**
- **…leave a review or add my company** → do it on **[sites.reviews](https://sites.reviews)** (see the [FAQ](./docs/faq.md))

---

## 🛡️ How the Trust Score works (in short)

A business's trust rating combines two kinds of signals:

1. **Community signals** — real user reviews and ratings on the platform, summarized (including AI-generated summaries to capture the overall sentiment quickly).
2. **Automated security/scam checks** — technical signals about the website itself, such as:
   - **SSL/HTTPS** — is the connection secured with a valid certificate?
   - **Blacklists** — does the domain appear on known scam/abuse lists?
   - **Domain age** — brand-new domains are riskier than long-established ones.

Together these produce an at-a-glance score that helps you judge whether a site is safe to trust or pay.

> Full breakdown in **[docs/trust-score.md](./docs/trust-score.md)**. Where exact internal weighting isn't published, the docs say so and describe how such checks generally work.

---

## 📖 Documentation

| Page | What's inside |
|---|---|
| [docs/getting-started.md](./docs/getting-started.md) | Start here — for everyday users and for developers |
| [docs/ecosystem.md](./docs/ecosystem.md) | Full surface map: website, bot, extension, MCP, API, public data |
| [docs/trust-score.md](./docs/trust-score.md) | How ratings and scam-checks work (SSL, blacklists, domain age, AI summaries) |
| [docs/faq.md](./docs/faq.md) | Is it free? How are reviews verified? Can businesses respond? How do I add my company? |

---

## 🗂️ Repositories index

| Repo | Purpose |
|---|---|
| [sites-reviews-docs](https://github.com/SitesReviewsTrust/sites-reviews-docs) | This documentation hub (the page you're reading) |
| [sites-reviews-extension](https://github.com/SitesReviewsTrust/sites-reviews-extension) | Browser extension — trust score on any site |
| [sites-reviews-mcp](https://github.com/SitesReviewsTrust/sites-reviews-mcp) | MCP server for AI assistants |
| [sites-reviews-api](https://github.com/SitesReviewsTrust/sites-reviews-api) | API & embeddable widgets (beta) |
| [All repositories](https://github.com/orgs/SitesReviewsTrust/repositories) | Everything in the SitesReviewsTrust org |

---

## 🤝 Contributing

Improvements to these docs are welcome — fix a typo, clarify a section, or add an example. See **[CONTRIBUTING.md](./CONTRIBUTING.md)**. For the code surfaces (extension, MCP, API), open issues and PRs in their own repositories.

## 📄 License

Documentation in this repository is licensed under **[CC BY 4.0](./LICENSE)** — you may share and adapt it with attribution to **Sites.Reviews**.

---

## 🇷🇺 Кратко по-русски

**Sites.Reviews** — независимый каталог отзывов о компаниях и сайтах с рейтингом доверия. Помогает понять, кому можно доверять в интернете: **рейтинг доверия**, **реальные отзывы пользователей**, **AI-сводки отзывов** и **автоматические проверки на мошенничество** (SSL, чёрные списки, возраст домена). Главный принцип — **«проверь сайт, прежде чем доверять или платить»**.

- 🌐 Сайт — [sites.reviews](https://sites.reviews)
- 🤖 Telegram-бот — [@SitesReviews_bot](https://t.me/SitesReviews_bot)
- 🧩 Расширение для браузера — [sites.reviews/extension](https://sites.reviews/extension)
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
