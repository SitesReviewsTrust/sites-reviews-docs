# API & developer tools

Everything you can build on Sites.Reviews data — and **when to use which**. This page is the overview; the full, authoritative REST reference (every field, every error) lives in **[sites-reviews-api](https://github.com/SitesReviewsTrust/sites-reviews-api)**.

All developer access is **read-only** and **needs no API key**.

---

## Which tool should I use?

| You want to… | Use | Why |
|---|---|---|
| Read trust scores / reviews from a script, backend, or another site's frontend | **[Public REST API](#-public-rest-api-live)** | Plain JSON, no key, CORS `*` — call it from anywhere |
| Let an AI assistant (Claude, Cursor, …) answer "is this site safe?" | **[MCP server](#-mcp-server-for-ai-assistants)** | Drops the same data into the model as callable tools |
| Show *your* company's reviews on *your own* website | **[Embeddable widget](#-embeddable-reviews-widget-beta)** | Copy-paste embed, no coding |
| Show a trust score for whatever page a person is visiting | **[Browser extension](#-browser-extension)** | End-user product, in-page badge |
| Get rich SEO-readable data with zero API call | **[schema.org JSON-LD](#-schemaorg-json-ld-on-every-business-page)** | Already embedded in every business page |

---

## 🔌 Public REST API (Live)

- **Base URL:** `https://sites.reviews/api/public/v1`
- **Auth:** none — public, read-only
- **CORS:** `Access-Control-Allow-Origin: *` (callable from browser JS)
- **Methods:** `GET`, `OPTIONS`
- **Rate limit:** **60 requests / minute / IP** (`X-RateLimit-Limit` / `X-RateLimit-Remaining` headers; exceeding it returns HTTP `429`)
- **Caching:** responses are cached ~5 minutes (`Cache-Control: max-age=300, public`)
- **Format:** JSON (UTF-8; Cyrillic returned as `\uXXXX` escapes, decoded by any JSON parser)

> This is a **summary**. For the complete field-by-field schema, query parameters, and error catalogue, see the reference in **[sites-reviews-api](https://github.com/SitesReviewsTrust/sites-reviews-api)**.

### Endpoints

| Method & path | Purpose |
|---|---|
| `GET /check?domain={domain}` | Fast trust-score lookup for one domain |
| `GET /business/{domain}` | Full business profile (description, AI summary, social links, tags…) |
| `GET /reviews/{domain}` | Paginated reviews for a business |
| `GET /search?q={query}` | Search businesses by name or domain |

### `GET /check?domain=`

The quickest "should I trust this?" call.

```bash
curl "https://sites.reviews/api/public/v1/check?domain=1ps.ru"
```

```jsonc
{
  "id": 1841,
  "name": "Продвижение сайтов от 1PS.RU",
  "slug": "1ps.ru",
  "website": "https://1ps.ru",
  "trust_score": 9.6,        // 0–10
  "avg_ratings": 4.8,        // 0–5 stars
  "total_reviews": 34,
  "is_verified": false,
  "url": "https://sites.reviews/businesses/1ps.ru",
  "logo": null
}
```

If the domain isn't in the catalog yet, you get a `found: false` payload (HTTP `200`) with a `submit_url` for adding it:

```jsonc
{ "found": false, "domain": "example-unknown.com",
  "submit_url": "https://sites.reviews/businesses/add?website=example-unknown.com" }
```

Missing the `domain` parameter returns HTTP `422` `{"error":"domain_required"}`.

### `GET /business/{domain}`

The full profile — everything in `/check` plus `short_description`, `description`, `ai_about`, `ai_summary`, `social_links`, `address`, `category_id`, `sub_category_id`, `tags`, `created_at`.

```bash
curl "https://sites.reviews/api/public/v1/business/1ps.ru"
```

Unknown domain → HTTP `404` `{"error":"not_found"}`.

### `GET /reviews/{domain}`

Paginated reviews. Each review includes `stars` (1–5), the original `title`/`body`, an English translation `body_en`, plus structured `pros` / `cons` arrays, `author`, and `created_at`.

```bash
curl "https://sites.reviews/api/public/v1/reviews/1ps.ru?page=1&per_page=20"
```

```jsonc
{
  "business": { "id": 1841, "name": "…", "trust_score": 9.6, "…": "…" },
  "page": 1,
  "per_page": 20,
  "total": 34,
  "reviews": [
    {
      "id": 23000,
      "title": "…",
      "body": "1PS.ru — удобный сервис …",
      "body_en": "1PS.ru is a convenient service …",
      "stars": 5,
      "pros": ["удобный сервис", "комплексные инструменты"],
      "cons": [],
      "author": null,
      "created_at": "2026-05-31T23:41:07+03:00"
    }
  ]
}
```

### `GET /search?q=`

```bash
curl "https://sites.reviews/api/public/v1/search?q=seo"
```

Returns `{ "count": N, "results": [ … ] }`, where each result has the same shape as `/check`. Queries that are too short return HTTP `422` `{"error":"query_too_short"}`.

### Quick start in JavaScript

Because CORS is open, you can call the API straight from the browser:

```js
const r = await fetch("https://sites.reviews/api/public/v1/check?domain=1ps.ru");
const data = await r.json();
console.log(data.trust_score, data.avg_ratings, data.total_reviews);
```

### Good citizenship

- Stay under **60 req/min/IP**; cache results on your side (responses are already cached ~5 min upstream).
- Treat the live values as the source of truth — scores change as new reviews and signals arrive.
- The data is licensed **CC BY 4.0** — attribute "Sites.Reviews" and link back when you display it. See [FAQ → data licensing](./faq.md#can-i-reuse-the-data--whats-the-licence).

---

## 🧠 MCP server (for AI assistants)

The **[sites-reviews-mcp](https://github.com/SitesReviewsTrust/sites-reviews-mcp)** server exposes the same data to AI assistants through the **[Model Context Protocol](https://modelcontextprotocol.io)**. Your assistant can then call Sites.Reviews as a tool — *"Is `shop.example` trustworthy?"* — and answer with real trust scores and reviews.

No clone, no global install, no key — it runs on demand via `npx`:

**Claude Code / Claude Desktop (one-liner):**

```bash
claude mcp add sites-reviews -- npx -y @sitesreviews/mcp
```

**Any MCP client (config block):**

```jsonc
{
  "mcpServers": {
    "sites-reviews": {
      "command": "npx",
      "args": ["-y", "@sitesreviews/mcp"]
    }
  }
}
```

The same `command`/`args` work for Cursor, Continue, and most MCP-compatible clients. Full setup, available tools, and troubleshooting are in the **[sites-reviews-mcp README](https://github.com/SitesReviewsTrust/sites-reviews-mcp)**.

**API vs. MCP — how to choose:** use the **REST API** when *your code* needs the data (backend, dashboard, your own site). Use the **MCP server** when *a language model* needs the data inside a conversation or agent loop. They serve the same numbers from the same source.

---

## 🧱 Embeddable reviews widget (beta)

Want your company's reviews on your own website without writing code? The **embeddable reviews widget** (currently **beta**) in **[sites-reviews-api](https://github.com/SitesReviewsTrust/sites-reviews-api)** gives you a copy-paste snippet. See that repo for the current embed code and options.

---

## 🧩 Browser extension

The **[browser extension](https://sites.reviews/extension)** ([repo](https://github.com/SitesReviewsTrust/sites-reviews-extension)) is an end-user product, not an API — it shows a site's trust score **on the page a person is visiting**, right at the moment of decision. Build on it or report issues in its repo.

---

## 🔎 schema.org JSON-LD (on every business page)

Independent of the REST API, every business page at `https://sites.reviews/businesses/{domain}` embeds **[schema.org](https://schema.org) JSON-LD** (`aggregateRating` + `review`) inside a `<script type="application/ld+json">` block. This makes pages readable by search engines and AI crawlers with no API call at all. For structured programmatic access, prefer the **REST API** above; use JSON-LD when you're already parsing the page (SEO tooling, scrapers, rich snippets).

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
