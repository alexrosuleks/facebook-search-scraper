# Facebook Search Scraper: Facebook Scraper API for Python & Node.js (2026)

Search public Facebook posts, pages, places, profiles, and reels by keyword. Collect authors, reactions, comments, links, and page contact details in one dataset.

**[▶ Try the Facebook Search Scraper free on Scrapely](https://scrape.ly/store/echofield/facebook-search-scraper)** · [Compare Scrapely vs other scraping tools](https://scrape.ly/compare)

This repository shows how to scrape Facebook data with the [Facebook Search Scraper](https://scrape.ly/store/echofield/facebook-search-scraper) using the official
**Scrapely SDKs for JavaScript and Python**. You pass the input, Scrapely runs the facebook scraper in the cloud
(proxies, retries, browser and scaling included) and returns clean, structured data as JSON, CSV or Excel.
No scraper code to maintain and no blocked requests to debug.

## Why use this Facebook scraper

- **No-code or API:** run it from the [Scrapely Store](https://scrape.ly/store/echofield/facebook-search-scraper) or from your code with the SDK.
- **Structured facebook data:** ready-to-use fields instead of raw HTML.
- **Pay per result:** $5.10 per 1,000 result results, no monthly subscription required.
- **Maintained and monitored:** scrapers are tested around the clock and fixed fast when Facebook changes.
- **Integrations:** n8n, Make, Zapier, LangChain, LlamaIndex, MCP (Claude, Cursor) and webhooks.

## What Facebook data can you extract?

Search public Facebook posts, pages, places, profiles, and reels by keyword. Collect authors, reactions, comments, links, and page contact details in one dataset.

| Output field |
|---|
| `type` |
| `url` |
| `name` |
| `message` |
| `timestamp` |
| `reactions_count` |
| `comments_count` |
| `reshare_count` |

## Quick start

1. [Sign up for Scrapely](https://scrape.ly) (free plan available) and copy your API token from
   **Settings → API & Integrations**.
2. Clone this repo and set your token:

```bash
export SCRAPELY_TOKEN=your_token
```

### Node.js (JavaScript SDK)

```bash
npm install
node example.js
```

```js
const { ScrapelyClient } = require('scrapely-client');
const client = new ScrapelyClient({ token: process.env.SCRAPELY_TOKEN });

const run = await client.actor('echofield/facebook-search-scraper').call({"query": "Mausritter", "search_type": "posts", "max_posts": 10, "recent_posts": false, "proxyConfiguration": {"useScrapelyProxy": true, "scrapelyProxyGroups": ["DATACENTER"]}});
const { items } = await client.dataset(run.defaultDatasetId).listItems();
```

### Python (Python SDK)

```bash
pip install -r requirements.txt
python example.py
```

```python
from scrapely_client import ScrapelyClient
client = ScrapelyClient(os.environ['SCRAPELY_TOKEN'])

run = client.actor('echofield/facebook-search-scraper').call(run_input={ "query": "Mausritter", "search_type": "posts", "max_posts": 10, "recent_posts": False, "proxyConfiguration": { "useScrapelyProxy": True, "scrapelyProxyGroups": [ "DATACENTER" ] } })
items = list(client.dataset(run.default_dataset_id).iterate_items())
```

### REST API / cURL

```bash
curl -X POST "https://api.scrape.ly/v2/acts/echofield~facebook-search-scraper/run-sync-get-dataset-items?token=$SCRAPELY_TOKEN" \
  -H "Content-Type: application/json" \
  -d @input.json
```

## Example input

```json
{
  "query": "Mausritter",
  "search_type": "posts",
  "max_posts": 10,
  "recent_posts": false,
  "proxyConfiguration": {
    "useScrapelyProxy": true,
    "scrapelyProxyGroups": [
      "DATACENTER"
    ]
  }
}
```

See every input option on the [Facebook Search Scraper page](https://scrape.ly/store/echofield/facebook-search-scraper).

## Pricing

**$5.10 per 1,000 result results.** Free plan available, no credit card needed to start. Check current pricing on the
[Store page](https://scrape.ly/store/echofield/facebook-search-scraper) and see how Scrapely compares with other tools on [scrape.ly/compare](https://scrape.ly/compare).

## FAQ

**How do I scrape Facebook with Python?** Install `scrapely-client-python`, set `SCRAPELY_TOKEN` and run
`example.py`. The scraper runs on Scrapely and you read the results from the dataset.

**How do I scrape Facebook with Node.js?** Install `scrapely-client`, set `SCRAPELY_TOKEN` and run `example.js`.

**Is there a facebook scraper API?** Yes. Call `POST https://api.scrape.ly/v2/acts/echofield~facebook-search-scraper/runs`
or use `run-sync-get-dataset-items` to get results in one request.

**Do I need proxies?** No. Proxies, retries and browsers are handled by Scrapely.

**Is scraping Facebook legal?** This scraper collects publicly available data. Check Facebook's terms and the
laws that apply to you, especially for personal data (GDPR, CCPA).

**Can I schedule it or get results by webhook?** Yes. Use Scrapely schedules and webhooks, or n8n, Make and Zapier.

## Related Facebook scrapers

- [Facebook Posts Scraper](https://github.com/alexrosuleks/facebook-posts-scraper): Scrape posts from public Facebook pages and profiles: text, timestamps, reactions, comments and shares counts, media,…
- [Facebook Ad Library Scraper](https://github.com/alexrosuleks/facebook-ads-scraper): Scrape Facebook and Instagram ads from the Meta Ad Library: ad text, creatives, page, platforms, dates and spend…
- [Facebook Pages Scraper](https://github.com/alexrosuleks/facebook-pages-scraper): Extract public Facebook page data: name, category, followers, likes, phone, email, website and address. No login…
- [Facebook Groups Scraper](https://github.com/alexrosuleks/facebook-groups-scraper): Scrape posts from public Facebook groups: text, author, date, reactions, comments count and media links. No login…
- [Facebook Comments Scraper](https://github.com/alexrosuleks/facebook-comments-scraper): Scrape comments and replies from public Facebook posts, reels and videos: text, author, date and reactions. No login or…
- [Facebook Reels Scraper](https://github.com/alexrosuleks/facebook-reels-scraper): Scrape public Facebook reels from pages and profiles: caption, video URL, thumbnail, views, likes, comments and date.…

## Looking for an alternative?

Scrapely is an alternative to Apify, Bright Data, ScraperAPI, Firecrawl, Octoparse, PhantomBuster, SerpApi,
Zyte and others. See the side-by-side pricing on [scrape.ly/compare](https://scrape.ly/compare).

---

**Keywords:** facebook search scraper, facebook scraper, facebook scraper api, facebook scraper python, facebook scraper node.js,
scrape facebook, facebook data extraction, facebook crawler, facebook api, export facebook data to csv, facebook-search-scraper

License: MIT. Example code only; the scraper runs on [Scrapely](https://scrape.ly/store/echofield/facebook-search-scraper).
