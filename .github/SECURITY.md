# Security Policy

## Reporting a vulnerability

If you discover a security vulnerability in any sitehub-dk repository:

1. **Do not open a public issue.**
2. Email **security@sitehub.dk** with:
   - Affected repository and version/commit
   - Steps to reproduce
   - Impact assessment
   - Your contact info (so we can follow up)
3. We acknowledge within 48 hours and aim to fix within 14 days for critical, 30 days for high, 60 days for medium.

For employees of SiteHub: post in `#it-security` on Slack instead of email.

## Supported versions

We patch the `main` / `master` / `develop` branch and the most recent release branch. Older release branches receive critical fixes only.

## Our baseline

Every sitehub-dk repo runs the org-default security baseline:

- **Dependabot alerts** + automated security fixes
- **Secret scanning + push protection** (GHAS) with custom patterns for our token formats (HETZNER, PROXMOX, ECONOMIC, etc.)
- **CodeQL** code scanning where the language is supported
- **Dependency Review** on every PR — blocks vulnerable deps at PR time
- **Branch protection** on default: PR required, 1 approving review, no force push, no deletion
- **Read-only `GITHUB_TOKEN`** by default in workflows
- **Reusable security workflow** (`.github/workflows/security-baseline.yml`) running: pin-check, npm/pnpm audit, Aikido `safe-chain` scan, Dependency Review, CodeQL, secret-scan summary on every push + weekly cron

Developer machines run the `sitehub-dk/dev-kit` bootstrap: pinned npm/bun installs with a 7-day release-age guard, Aikido `safe-chain` package firewall, hardened Claude Code / Codex CLI defaults, and 1Password CLI for secret access.

## Disclosure policy

We disclose patched vulnerabilities via GitHub Security Advisories. We will coordinate timing with reporters when needed.
