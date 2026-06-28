# Security Policy

We take the security of Sites.Reviews and its open-source ecosystem seriously. Thank you for helping keep users safe.

## Reporting a vulnerability

**Please do not open public issues for security vulnerabilities.** Public disclosure before a fix puts users at risk.

Report privately through **GitHub's private vulnerability reporting**:

1. Go to the **Security** tab of the relevant repository.
2. Click **"Report a vulnerability"** (GitHub Private Vulnerability Reporting).
3. Or use this repo's form directly: **[Report a vulnerability](https://github.com/SitesReviewsTrust/sites-reviews-docs/security/advisories/new)**.

This creates a private advisory visible only to you and the maintainers.

### Report in the right repo

Send the report to the repository that contains the affected code or surface:

| Affected surface | Report in |
|---|---|
| Public REST API, widgets | [sites-reviews-api](https://github.com/SitesReviewsTrust/sites-reviews-api/security/advisories/new) |
| MCP server | [sites-reviews-mcp](https://github.com/SitesReviewsTrust/sites-reviews-mcp/security/advisories/new) |
| Browser extension | [sites-reviews-extension](https://github.com/SitesReviewsTrust/sites-reviews-extension/security/advisories/new) |
| This documentation | [sites-reviews-docs](https://github.com/SitesReviewsTrust/sites-reviews-docs/security/advisories/new) |

If you're unsure which repo applies, report it here in `sites-reviews-docs` and we'll route it.

## What to include

- A clear description of the issue and its potential impact.
- Steps to reproduce (proof-of-concept, requests, or screenshots).
- The affected surface, URL, or version.
- Any suggested remediation, if you have one.

## What to expect

- We aim to acknowledge a valid report within a few business days.
- We'll keep you updated as we investigate and work on a fix.
- Please give us reasonable time to remediate before any public disclosure.
- We're grateful for responsible disclosure and happy to credit reporters (with your permission).

## Scope

This is a documentation repository — it contains no application code, secrets, or runtime services. Security issues in the *content* (e.g. a link pointing somewhere malicious) are welcome here; issues in the *services* belong in the repos listed above. For abuse, fraudulent listings, or incorrect ratings on the platform itself, use the report option on the relevant page at [sites.reviews](https://sites.reviews).
