# Contributing (owner workflow)
1. Branch from `main`: `feat/<thing>` or `fix/<thing>`.
2. Open a PR. CI must pass (HTML validation).
3. Review the Vercel preview URL on a phone.
4. Squash-merge. Production deploys from `main`.
Keep pages static until the server-backed hub phase; when server work starts, data access goes through Supabase keys in Vercel env vars, never the repo.
