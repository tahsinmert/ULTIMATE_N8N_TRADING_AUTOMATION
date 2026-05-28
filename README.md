# ULTIMATE_N8N_TRADING_AUTOMATION

An n8n workflow export for automated trading signals and execution. The workflow listens for incoming market data, evaluates trend and momentum conditions, validates the trade, executes an order through Binance Futures, and sends a Telegram alert when a trade is placed.

## What’s Inside

- `TradingView Webhook` receives webhook payloads
- `Logic Engine` calculates the trade decision
- `Trade Validation` filters out `NONE` actions
- `Execute Trade` sends an order request to Binance Futures
- `Telegram Alert` notifies you after execution

## Workflow Logic

The workflow evaluates:

- EMA 50 vs EMA 200 for trend direction
- RSI thresholds for momentum confirmation
- MACD vs signal line for confirmation
- Volume vs average volume for strength
- ATR for minimum volatility

If conditions are aligned, the workflow returns `LONG` or `SHORT`; otherwise it returns `NONE`.

## Requirements

- n8n instance with webhook access
- Binance Futures API credentials
- Telegram bot token and chat ID
- TradingView or another system capable of sending webhook payloads

## Setup

1. Import the JSON workflow file into n8n.
2. Configure the webhook endpoint in TradingView or your signal source.
3. Replace placeholder values in the workflow, including:
   - `YOUR_CHAT_ID`
   - Binance authentication settings if your deployment requires them
4. Test the workflow with a sample payload before using live funds.

## Example Payload

```json
{
  "symbol": "BTCUSDT",
  "close": 65000,
  "ema50": 64800,
  "ema200": 64200,
  "rsi": 61,
  "macd": 120,
  "signal": 100,
  "volume": 15320,
  "avgVolume": 11000,
  "atr": 1.2
}
```

## Important

This project is for educational and automation purposes only. Trading cryptocurrencies and derivatives carries significant risk. You are responsible for verifying logic, credentials, order size, and exchange settings before enabling live execution.

## Repository Files

- `n8n-trading-otomation.json` - the workflow export
- `README.md` - project documentation
- `LICENSE` - open-source license for the repository
