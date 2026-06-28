# How the Trust Score & scam-check work

The Sites.Reviews **trust score** is a single, at-a-glance signal that answers: *"How safe is it to trust or pay this website?"* It blends what **people** say with what the **site itself** technically looks like.

> **A note on precision.** Where Sites.Reviews publishes exact behaviour, this page states it directly. Where the precise internal weighting or algorithm isn't public, this page describes **how such checks generally work** and marks it as such. Treat the live score on a business page as the source of truth.

---

## The two input families

### 1. Community signals (what people report)

- **User reviews and ratings.** Real users leave star ratings and written reviews about their experience with a company or site.
- **AI review summaries.** Because reading dozens of reviews is slow, the platform generates AI summaries that distil the overall sentiment and recurring themes, so you can grasp the consensus quickly.
- **Volume and consistency.** *(How this generally works:)* a score backed by many consistent reviews is more reliable than one based on a handful, so review count and agreement typically matter.

### 2. Automated security / scam checks (what the site technically looks like)

These are technical signals about the website itself, evaluated automatically:

- **SSL / HTTPS** — Does the site serve traffic over HTTPS with a valid TLS certificate? A missing or invalid certificate is a basic red flag, especially for anything involving payment or login.
- **Blacklists** — Does the domain appear on known scam, phishing, or abuse blacklists? A listing is a strong negative signal.
- **Domain age** — How long has the domain existed? Freshly registered domains are statistically riskier (scam sites are often brand-new and short-lived), while long-established domains carry more inherent trust.

*(How this generally works:)* additional hygiene signals — such as whether the site is reachable, and basic reputation lookups — can also feed a technical risk assessment. The exact set and weighting may evolve.

---

## How they combine

The trust score brings the community signals and the automated checks together into one rating shown on the business page. In practice:

- **Strong community + clean technicals → high trust.** Lots of positive, consistent reviews on an established, secure, un-blacklisted domain.
- **Red flags pull the score down.** A blacklist hit, no SSL, or a brand-new domain are warning signs even before any reviews exist.
- **New or thin data → treat with caution.** A site with no reviews and a young domain simply doesn't have enough signal to be considered trustworthy yet — absence of bad reviews is not the same as proof of trust.

> The precise formula and weights are not publicly published; the above describes the principle. Always read the specific signals shown on a business page, not just the headline number.

---

## How to use it

- **Before you pay or sign up**, search the domain on [sites.reviews](https://sites.reviews) (or use the [browser extension](https://sites.reviews/extension) to see it in-page).
- **Read the actual reviews**, not just the score — context matters (e.g. one angry review vs. a pattern).
- **Take the technical flags seriously** — no SSL or a blacklist hit on a checkout page is a reason to stop.
- **Cross-check** a young, review-less site against other sources before trusting it with money or personal data.

---

## Where the data lives

You can read a business's score and reviews programmatically through the **[public REST API](./api-and-tools.md#-public-rest-api-live)**:

```bash
curl "https://sites.reviews/api/public/v1/check?domain=1ps.ru"
# → {"trust_score":9.6,"avg_ratings":4.8,"total_reviews":34, …}
```

Here `trust_score` is the 0–10 headline score and `avg_ratings` is the 0–5 star average. The same signals are also reflected in each business page's structured data (schema.org JSON-LD with `aggregateRating` and `review`) at `https://sites.reviews/businesses/{domain}` — see [ecosystem.md](./ecosystem.md#-public-data--schemaorg-json-ld).

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
