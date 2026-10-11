# Serper.live — live Google SERP API

Real-time organic Google results as JSON for the country, language and device you choose.
Built for rank tracking, SEO tooling and research: every request is a fresh search,
nothing is served from a cache.

- **Pay per successful request.** Failed or empty searches are not billed.
- **No subscription.** Top up from $5 in USDT or USDC; credit never expires.
- **Try it first.** The [playground](https://serper.live/playground) runs a live search without an account.
- **Markets.** Supported countries and languages are listed by `GET /v1/countries` and in the [docs](https://serper.live/docs);
  new markets are added over time.

## Quick start

Create an account, add credit and generate a token at [serper.live](https://serper.live), then:

```bash
curl -X POST https://api.serper.live/v1/search \
  -H "Authorization: Bearer sl_live_YOUR_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"query":"best coffee shops","country":"UA"}'
```

Use any country code returned by `https://api.serper.live/v1/countries`. The response contains
`organic[]` with position, title, link and snippet for the first page of results, plus the
price charged for the request.

## Links

- [Documentation](https://serper.live/docs) — endpoints, parameters, response fields, errors and retries
- [Pricing](https://serper.live/pricing) — per-request prices by market
- [Rank tracking with Serper.live](https://serper.live/rank-tracking-api) — checking a domain's position
- [Contact](https://serper.live/contact) — questions about the API, billing or a market you need

Serper.live is run from Ukraine by its owner. Code samples and SDKs will appear in this organization.
