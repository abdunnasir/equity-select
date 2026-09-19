# equity-select

A Claude Code skill that scans Indian market news and data sites to
shortlist NSE/BSE stocks with bullish near-term signals, with sourced
reasons for each pick — built for ongoing tracking and improvement.

## Install

npx skills add abdunnasir/equity-select -a claude-code -g -y

## Usage

Invoke `/equity-select` in Claude Code to get tomorrow's watchlist.

## What it does

Checks official exchange filings (NSE/BSE), company IR pages, business
news (Moneycontrol, Economic Times, etc.), and chart/screening tools
(TradingView, Screener.in) for bullish triggers — earnings beats, broker
upgrades, technical breakouts, FII/DII buying — and outputs a table of
up to 10 stocks with the trigger, source, and reliability classification
for each.

Picks are saved to `picks/YYYY-MM-DD.md` so future runs can review what
actually happened and refine the skill over time.
