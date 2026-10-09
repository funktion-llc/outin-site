# OUTIN — Public Site
Function LLC d/b/a OUTIN. Hosts the OUTIN public pages and the client hub.
- Production domain (planned): https://outin.golf (wildcard subdomains for event apps, e.g. kiawah26.outin.golf)
- Hosting: Vercel (team john-tibbs-projects), static — no build step.
- Money/legal entity: Funktion LLC (Kentucky). Job IDs (OUTIN-001...) thread Drive folders, docs, and invoices.

## Structure
- `client/` — Client hub page (static example; server-backed version replaces it)
- `.github/workflows/ci.yml` — HTML validation + content checks on every PR

## Environments
- **Production**: branch `main`, deployed automatically by Vercel.
- **Preview**: every pull request gets a Vercel preview URL; merge only after preview review.
- **Development**: local static preview, no build: `npx serve .`

## Rules
- Never commit secrets. Environment variables live in Vercel project settings; keep only names in `.env.example`.
- `main` is protected: PR + CI green + 1 owner approval before merge.
- Client data (rosters, handicaps) never in this repo — the hub reads from the server, not from static files.
