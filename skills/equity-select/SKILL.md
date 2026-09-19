---
name: equity-select
description: |
  Scans Indian market news and data sites (Moneycontrol, TradingView, NSE/BSE,
  Economic Times, etc.) to shortlist ~10 NSE/BSE stocks with bullish near-term
  signals, with sourced reasons for each. Use when asked for tomorrow's buy
  ideas or which stocks look strong for the next session.
---

## Instructions

Invoking this skill on its own (no question attached) only loads the rules
below into context — do not start researching or producing a watchlist yet.
Wait for the user to ask a specific question (e.g. "what looks strong for
tomorrow?", "check on VEDL", "any order-win stocks today?") before doing any
research. Answer only what was asked — don't default to a full 10-stock
watchlist unless the user asks for one.

## Sources

Use in this priority order:

1. **NSE India** (nseindia.com), **BSE India** (bseindia.com) — official filings, corporate announcements, board meeting outcomes. Most reliable.
2. **Company investor-relations pages** — press releases, results, transcripts.
3. **Moneycontrol**, **Economic Times Markets**, **LiveMint Markets**, **Business Standard Markets**, **CNBC-TV18**, **BQ Prime**, **Reuters India** — business news and market commentary.
4. **TradingView**, **Screener.in**, **Tickertape**, **Trendlyne** — charts, fundamentals, analyst ratings, block/insider deals.
5. **Zerodha Varsity** — background/education only, not signals.
6. **SEBI** (sebi.gov.in) — regulatory orders/circulars, check for relevance.

Always separate confirmed exchange filings from media speculation.

## What To Capture

- Earnings beat vs. estimates, positive management commentary/guidance
- Broker upgrade, target price hike, new "buy" initiation
- Technical breakout: new 52-week high, volume spike, breakout above resistance
- FII/DII net buying, large block/bulk deals, promoter buying
- Order wins, large contracts, capex announcements
- Sector-wide tailwinds: policy change, commodity price move, PLI/budget benefit
- Corporate actions: bonus, buyback, stock split (short-term price reaction)

## Classification

| Label | Meaning |
|-------|---------|
| Confirmed | Exchange filing or official company statement |
| Reported | Named business-news outlet, not yet exchange-confirmed |
| Technical | Chart-pattern based, no fundamental news trigger |
| Speculative | Rumor, social media, or unverified — flag clearly, use sparingly |

## Output

```markdown
## Tomorrow's Watchlist — [Date]
| # | Ticker | Trigger | Source | Classification |
|---|--------|---------|--------|-----------------|

Summary: [2-3 sentences on overall market tone/theme influencing picks]
```

List exactly 10 stocks unless fewer than 10 meet the bar — never pad with weak/speculative picks to hit the count.

## Save Results

Only if the user asks to save/record the list: write the table + summary to
`picks/YYYY-MM-DD.md` (create the `picks/` folder if missing), for later
comparison against actual performance. Do not save automatically.

## Disclaimer

Always end output with: *"Educational research only, not financial advice. No source predicts next-day price moves reliably — verify independently before trading."*
