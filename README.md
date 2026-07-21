# Galli Bazaar

A free paper-trading simulator for Nepal's stock market (NEPSE). Practice trading real, NEPSE-listed companies using simulated capital — no real money, no brokerage account, no risk.

**[Live site →](https://bikram-fin7.github.io/galli-bazaar/)**

## What it does

- Every new user starts with **Rs. 1,00,000** in virtual capital
- Trade real NEPSE-listed companies across all major sectors — banking, hydropower, insurance, microfinance, and more
- Live NEPSE Composite Index with 1D / 1W / 1M charts, automatically falling back to a synchronized simulation when the live data feed is unavailable
- A shared leaderboard, ranked by net worth or by financial literacy score
- A community feed for discussing trades and market moves
- A financial literacy quiz and a "bull or bear" market-scenario game

## How it works

This is a single self-contained HTML file — no build step, no server required. It runs entirely in the browser.

- **Market data:** attempts a live feed from the open-source [NepseAPI-Unofficial](https://github.com/surajrimal07/NepseAPI-Unofficial) project, and falls back to a deterministic, synchronized simulation when that feed is unavailable.
- **Personal data** (portfolio, holdings, quiz progress): stored in the browser's `localStorage`.
- **Shared data** (leaderboard, community posts): stored via [Supabase](https://supabase.com) (free tier) once configured — see below.

## Setting up the shared backend (optional)

By default, the leaderboard and community feed only show activity from your own browser. To make them genuinely shared across every visitor:

1. Create a free project at [supabase.com](https://supabase.com)
2. Run the SQL setup (see comments in `index.html` near the `SUPABASE_URL` constant)
3. Paste your project URL and anon key into the two constants near the top of the `<script>` section

## Disclaimer

Galli Bazaar is an independent, non-commercial educational project. It is **not affiliated with NEPSE, SEBON, MeroShare, or any licensed brokerage**, and nothing in this project constitutes financial or investment advice. All currency shown is fictional and cannot be deposited, withdrawn, or converted to real money. Market data is sourced on a best-effort basis from unofficial, community-maintained tools and may be delayed, incorrect, or simulated — never use it to inform a real trade.

## License

MIT — see [LICENSE](LICENSE).
