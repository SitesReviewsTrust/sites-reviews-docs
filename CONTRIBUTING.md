# Contributing to sites-reviews-docs

Thanks for helping improve the Sites.Reviews documentation hub. This repo is the cross-linking center for the whole ecosystem, so keeping it clear and accurate matters. By participating you agree to our **[Code of Conduct](./CODE_OF_CONDUCT.md)**.

## What belongs here

- Fixes to typos, wording, broken links, and formatting.
- Clarifications and small additions to existing docs (`README.md`, `docs/*`).
- Keeping the **ecosystem table**, **cross-link block**, and **API summary** in sync with reality.

## What belongs elsewhere

| Topic | Repo |
|---|---|
| **Public REST API** & widgets — bugs, endpoints, reference | [sites-reviews-api](https://github.com/SitesReviewsTrust/sites-reviews-api) |
| **MCP server** — setup, tools, client configs | [sites-reviews-mcp](https://github.com/SitesReviewsTrust/sites-reviews-mcp) |
| **Browser extension** | [sites-reviews-extension](https://github.com/SitesReviewsTrust/sites-reviews-extension) |
| Wrong **rating/review** or data on a business page | Report it on the [sites.reviews](https://sites.reviews) page itself |

## Ground rules

1. **Stay factual.** Don't add metrics, endpoints, or features that don't exist. If something is in beta or not yet available, say so plainly. When you document an API behaviour, verify it against the live endpoint first.
2. **Mark inferences.** If you describe how something *generally* works (rather than a published behaviour), label it as such — see [docs/trust-score.md](./docs/trust-score.md) for the style.
3. **Keep the cross-link block verbatim.** The shared `🔗 Sites.Reviews ecosystem` block is intentionally identical across files. If it changes, update it everywhere.
4. **The full API reference lives in [sites-reviews-api](https://github.com/SitesReviewsTrust/sites-reviews-api).** Here we *summarize and link* — don't duplicate the whole reference.
5. **Every internal link must resolve.** If you move or rename a page, update every link to it.
6. **English first** (this is a public, global, AI-discoverable repo); a short Russian section is welcome.

## Docs quality checklist (before opening a PR)

- [ ] Links resolve (internal `./docs/*` and external).
- [ ] Any API/endpoint claim matches the live service.
- [ ] New pages are linked from [`docs/README.md`](./docs/README.md) and, if user-facing, the root `README.md`.
- [ ] The cross-link block (if present) is verbatim.
- [ ] No secrets, tokens, or personal data.

## How to contribute

1. Fork the repo and create a branch.
2. Make your change.
3. Open a pull request with a short description of what and why.

Not sure where something goes? Open a **[question issue](https://github.com/SitesReviewsTrust/sites-reviews-docs/issues/new/choose)** and we'll point you.

## License

By contributing, you agree your contributions are licensed under **[CC BY 4.0](./LICENSE)**, attributed to Sites.Reviews.
