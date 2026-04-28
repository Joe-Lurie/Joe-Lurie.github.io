# SER375Project
# Joseph Lurie — Financial Markets Dashboard

A personal stock-tracking dashboard with live market data, charts, and AI-powered analysis.

🔗 [www.josephlurie.com](https://www.josephlurie.com)

## Pages

- **Home** — landing page
- **Data** — live prices, charts, AI buy/sell/hold analysis, CSV export
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

```bash
python3 -m http.server 8000
```

Then open [http://localhost:8000](http://localhost:8000).