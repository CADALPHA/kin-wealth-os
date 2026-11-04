# Development and configuration

## Local configuration

1. Copy `.env.example` to `.env`.
2. Never commit `.env` or real credentials.
3. `VITE_SUPABASE_*` values and the Supabase publishable key are browser configuration. They are not service-role secrets.
4. `LOVABLE_API_KEY`, service-role keys, and private tokens must remain server-side and out of version control.

If a real credential was ever committed, rotate it in the provider dashboard. Removing a file from the current branch does not remove it from Git history.

## Before a pull request

Run:

```bash
npm ci
npm run lint
npm run build
npm test
```

The GitHub quality workflow runs these checks for each pull request to `main`, and rejects any tracked `.env` file. The finance tests cover allocations, liquidity, ROI, risk alerts, income balances, loans, and net worth.
