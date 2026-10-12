# Serper.live — live Google SERP API

Real-time organic Google results as JSON for the country, language and device you choose.
Built for rank tracking, SEO tooling and research: every request is a fresh search,
nothing is served from a cache.

- **Up to 100 results per request.** `limit` 1–100, 10 by default; positions go as deep as you ask.
- **No subscription.** Top up from $5 in USDT or USDC; credit never expires.
- **Try it first.** The [playground](https://serper.live/playground) runs a live search without an account.
- **Markets.** Supported countries and languages are listed by `GET /v1/countries` and in the
  [docs](https://serper.live/docs); new markets are added over time.

## Quick start

Create an account, add credit and generate a token at [serper.live](https://serper.live), then:

```bash
curl -X POST https://api.serper.live/v1/search \
  -H "Authorization: Bearer sl_live_YOUR_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"query":"best coffee shops","country":"UA","limit":30}'
```

Use any country code returned by `https://api.serper.live/v1/countries`. The response contains
`organic[]` with `position`, `title`, `url`, `domain` and `snippet` in ranking order, plus `pages`
(the blocks of 10 that were charged). With `limit` 30 the search reads up to three result pages in
one call; leave `limit` out to get the top 10 for a single price.

## Links

- [Documentation](https://serper.live/docs) — endpoints, parameters, response fields, errors and safe retries
- [Pricing](https://serper.live/pricing) — per-market prices and a monthly cost calculator
- [Rank tracking with Serper.live](https://serper.live/rank-tracking-api) — checking a domain's position by country and device
- [Google rankings by country, without maintaining a scraper](https://medium.com/@serper-live/google-rankings-by-country-without-maintaining-a-scraper-233295584a6a) — a walkthrough with a working Python example
- [Contact](https://serper.live/contact) — questions about the API, billing or a market you need
