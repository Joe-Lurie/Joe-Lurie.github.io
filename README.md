# Joseph Lurie — Financial Markets Dashboard

A personal stock-tracking dashboard with live market data, charts, and AI-powered analysis. Built as a class project for **SER375**.

🔗 [www.josephlurie.com](https://www.josephlurie.com)

## What this project is

A static web dashboard that fetches live stock data, visualizes price history with interactive charts, and uses Claude (Anthropic's AI) to generate buy / sell / hold recommendations. Users can star stocks to build a personal watchlist saved in their browser.

## Who it's for

Anyone curious about combining AI with finance — whether you're exploring how LLMs can analyze market data, looking at how to wire up real APIs in a static site, or just want to track a few defense and tech stocks.

## Pages

- **Home** — landing page
- **Data** — live prices, interactive charts, AI buy/sell/hold analysis, CSV export
- **Stocks** — your starred watchlist with grid and table views

## Features

- 70+ tickers across Defense, Tech, Finance, Healthcare, Consumer, Energy, Industrial, and ETFs
- Search and filter by sector
- Star (★) any stock to save it to your watchlist
- Watchlist with live prices, search, sector filters, grid/table views
- Interactive price chart with 20D / 60D / ALL ranges
- AI analysis powered by Claude
- Export historical data to CSV

## Tech

Plain HTML, CSS, and JavaScript. No build step.

- **Alpha Vantage** for stock data
- **Claude API** (via Cloudflare Worker) for analysis
- **localStorage** for watchlist, **sessionStorage** for price cache
- **GitHub Pages** for hosting

## Files

```
index.html    Home
data.html     Live data, charts, AI analysis
stocks.html   Watchlist
CNAME         Custom domain
```

## Run locally

You'll need:

- A browser
- **Python 3** (or any local HTTP server)

From the project folder:

```bash
python3 -m http.server 8000
```

Then open [http://localhost:8000](http://localhost:8000).

> Note: Opening the HTML files directly with `file://` will load the UI but the AI analysis button won't work due to CORS. Use a local server.

## Setup for your own copy

If you fork this repo and want it running with your own keys:

1. **Alpha Vantage key** — get a free one at [alphavantage.co](https://www.alphavantage.co/support/#api-key) and replace the `apikey=` value in the fetch URLs inside `data.html` and `stocks.html`.
2. **Anthropic API key** — get one at [console.anthropic.com](https://console.anthropic.com), then deploy your own Cloudflare Worker that proxies requests to the Anthropic API. Update `WORKER_URL` at the top of the script in `data.html` to point to your worker.
3. **GitHub Pages** — push to a repo, enable Pages in the repo settings, and (optionally) add a `CNAME` file for a custom domain.

## Limitations

- Alpha Vantage's free tier is limited to 5 requests/minute and 500/day
- Watchlist is per-browser via localStorage — it doesn't sync across devices
- AI analysis is for educational purposes and is **not financial advice**