# Jiyani Trading Signals — v0.2

Gujarati mobile-first PWA prototype for intraday paper analysis of NIFTY 50, NIFTY BANK and NSE stocks.

## What's new in v0.2
- EMA 9/21, RSI 14 (Wilder), session VWAP and ATR 14.
- Stricter BUY/SELL conditions with candle-direction and volume confirmation; otherwise NO TRADE.
- ATR-based illustrative stop-loss (1.5 × ATR), 2R and 3R targets.
- Risk-budget/indicative quantity calculator (equity-share style only; does not calculate F&O lot sizes).
- CSV validation and a local paper journal stored in the browser.

## Android installation
1. Extract the ZIP and host this folder on an HTTPS static host.
2. Open the hosted site in Chrome on Android.
3. Chrome menu → Install app / Add to Home screen.

## CSV format
`time,open,high,low,close,volume`
At least 35 valid rows. Example:
```
time,open,high,low,close,volume
2026-11-23T09:15:00+05:30,26000,26020,25990,26010,12000
```
Use real completed candles. The last row is treated as a completed candle. For reliable session VWAP, timestamps should be ISO date/time strings.

## Kotak Neo integration status
This release is still CSV/demo only. No live Kotak login, streaming feed, or order placement is connected. Official Kotak Neo documentation describes TOTP login followed by MPIN validation, historical OHLCV APIs and a new SFeed market WebSocket. The backend must be implemented server-side; never place API tokens, MPIN, TOTP seed or session tokens in this browser app or share them in chat.

Useful official references:
- API getting started/authentication: https://github.com/Kotak-Neo/Kotak-Neo/blob/main/docs/getting-started.md
- Market-data API overview: https://github.com/Kotak-Neo/Kotak-Neo/tree/main/docs/market-data-apis
- Historical candles: https://github.com/Kotak-Neo/Kotak-Neo/blob/main/docs/market-data-apis/historical-data.md
- New market WebSocket: https://github.com/Kotak-Neo/Kotak-Neo/blob/main/docs/market-data-apis/websocket.md
- Kotak bulletin on market-feed migration (15 Sep 2026): https://www.kotakneo.com/bulletins/trade-api-market-feed-migration-15-september-2026/

## Safety
Educational/paper-trading tool only. Signals are unvalidated and do not guarantee returns. Do not use real funds without independent backtesting, forward paper testing, exchange/broker compliance checks and human review. Index signals are directional analysis only; NIFTY/BANKNIFTY indices themselves are not directly tradable. Derivatives require contract-specific lot size, expiry, premium, liquidity and risk calculations. No automatic order feature exists.
