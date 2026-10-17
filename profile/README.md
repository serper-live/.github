# Serper.live — live Google SERP API

Real-time organic Google results as JSON for the country, language and device you choose,
typically in 2–3 seconds. Built for rank tracking, SEO tooling and research: every request
is a fresh Google search, never a cached copy.

- **Live and fast.** A page of 10 results usually comes back in 2–3 seconds, and every
  response reports its own time in `latencyMs`.
- **Up to 100 results per request.** `limit` 1–100, 10 by default; positions are counted
  across Google's result pages.
- **Desktop and mobile in every market**, at the same price.
- **No subscription.** Top up from $5 in USDT or USDC and pay per page of up to 10 results;
  credit never expires.
- **Try it first.** The [playground](https://serper.live/playground) runs a live search without an account.
- **Markets.** Open countries and the default Google language of each are listed by
  `GET /v1/countries` and in the [docs](https://serper.live/docs); new markets are added over time.

## Quick start

Create an account, add credit and generate a token at [serper.live](https://serper.live), then:

```bash
curl -X POST https://api.serper.live/v1/search \
  -H "Authorization: Bearer sl_live_YOUR_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"query":"best coffee shops","country":"US","device":"mobile","limit":30}'
```

Use any country code returned by `https://api.serper.live/v1/countries`. The response contains
`organic[]` with `position`, `title`, `url`, `domain` and `snippet` in ranking order, plus
`latencyMs` and `pages` (the pages of 10 that were charged). With `limit` 30 the search reads up
to three result pages in one call; leave `limit` out to get the top 10 for a single price.

## Links

- [Blog](https://serper.live/blog) — guides on rank tracking, Google markets and moving off Google's own search APIs
- [Rank tracking with Serper.live](https://serper.live/blog/rank-tracking-api) — checking a domain's position by country and device
- [Google Custom Search JSON API alternative](https://serper.live/blog/google-custom-search-api-alternative) — parameter mapping (`q`, `gl`, `hl`, `num`) and migration steps
- [Documentation](https://serper.live/docs) — endpoints, parameters, response fields, errors and safe retries
- [Pricing](https://serper.live/pricing) — per-market prices and a monthly cost calculator
- [Contact](https://serper.live/contact) — questions about the API, billing or a market you need
