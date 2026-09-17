# Options OI hedge tables

Static GitHub Pages dashboard for **multi-ticker** open-interest hedge tables (not SPCX-only).

- Live site: https://galigutta.github.io/spcx-oi-site/
- Pipeline: https://github.com/galigutta/open_interest

## Watchlist (single-stock)

`NVDA TSLA AAPL MSFT AMZN META AMD MU INTC NFLX SPCX` — no ETFs.

## Layout

- `index.html` — symbol directory + links
- `symbols/{TICKER}/index.html` — per-symbol history + latest expiry×shock pivot
- `watchlist.txt` / `tickers.json` — source list

## Rebuild

From the `open_interest` repo after running `python oi.py --watchlist` (or individual tickers):

```bash
python build_site.py --out ../spcx-oi-site
```

**Spot** comes from yfinance; **IV** from AlphaQuery 30-day IV mean scrape (flat ~52% if scrape fails). Do not invent historical OI rows — only publish days that were actually pulled from OCC.
