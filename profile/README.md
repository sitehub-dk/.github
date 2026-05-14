# SiteHub

We build software for the construction industry: planning, IoT, reporting, recycling, document workflows. Modular monolith on .NET + Angular + Next, hosted on Hetzner, with edge via Cloudflare.

## For new joiners

1. Set up your laptop with **[sitehub-dk/dev-kit](https://github.com/sitehub-dk/dev-kit)** — Windows-first PowerShell or Mac bash, runs in under 5 minutes.
2. Read **[SECURITY.md](./SECURITY.md)** for how we handle vulnerabilities.
3. Ping `#it-security` on Slack if anything looks wrong.

## Security baseline

Every active repo runs the org-default workflow defined here: pin-check, npm/pnpm audit, Aikido `safe-chain`, Dependency Review, CodeQL, secret-scan summary. Read more in `.github/workflows/security-baseline.yml`.
