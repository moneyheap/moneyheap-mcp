# moneyheap MCP server

Stock market research from [moneyheap](https://moneyheap.ai) in Claude, ChatGPT, Codex and any other MCP client: the day's market overview, the Daily Standout, the biggest movers, trending stocks, market-moving news and the analysis of the stocks you follow.

```
https://moneyheap.ai/mcp
```

A hosted remote server (Streamable HTTP) with OAuth 2.1 sign-in. Nothing to install and no API key: add the URL to your AI app, sign in with a free moneyheap account and click Allow. This repository holds the server's documentation and its [MCP Registry](https://registry.modelcontextprotocol.io) listing ([`server.json`](server.json), `ai.moneyheap/moneyheap`); the server itself runs on moneyheap.ai.

## Tools

All five tools are read-only. None can add or remove stocks, change settings, touch billing or place trades.

| Tool | What it returns |
|---|---|
| `get_daily_edition` | The day's market overview, Daily Standout, other stocks that stood out, biggest movers and trending stocks, as a short summary or one part in full |
| `get_market_news` | The latest Market Stories (news grouped by event, with every outlet's article and the tickers it touches), or only the ones about one stock |
| `list_portfolio` | The stocks and ETFs in your moneyheap portfolio with their latest sentiment |
| `get_asset_analysis` | One stock's latest analysis: what changed, the news behind it, and sentiment and confidence for three time horizons |
| `get_sentiment_history` | How the read on one stock has moved over time |

Every answer carries the time its data is from.

## Connect

**Claude** (web or desktop): Settings → Connectors → Add custom connector → paste `https://moneyheap.ai/mcp` → sign in to moneyheap and click Allow.

**Claude Code:**

```bash
claude mcp add --transport http moneyheap https://moneyheap.ai/mcp
```

Then type `/mcp` in Claude Code, pick moneyheap and sign in.

**Codex:**

```bash
codex mcp add moneyheap --url https://moneyheap.ai/mcp
codex mcp login moneyheap
```

**ChatGPT:** Settings → Apps → Advanced settings → turn on Developer mode → create an app with `https://moneyheap.ai/mcp` → sign in to moneyheap and click Allow.

Any client that supports remote MCP servers over HTTP with OAuth should work. The full guide, with example questions and troubleshooting: [How to connect Claude to stock market research via MCP](https://moneyheap.ai/blog/connect-claude-to-market-research-mcp/).

## Plans

The server works on every plan, including Free. A free account gets the Daily Standout and each day's top 3 Market Stories in full and follows up to 4 stocks; [Pro](https://moneyheap.ai/pricing) adds the full research on every stock of the day and every story, and follows up to 100 stocks. The app sees what your plan shows in moneyheap.

## Access and privacy

The app reads only your portfolio and moneyheap's research, and only after you click Allow. Access tokens last one hour; refresh tokens last 60 days and are replaced on every use. Codes and tokens are stored only as hashes. Each connected app is listed under Settings → [Connected apps](https://moneyheap.ai/connected-apps), where Disconnect removes it with all of its tokens. See the [privacy policy](https://moneyheap.ai/legal/privacy).

## Support

[support@moneyheap.ai](mailto:support@moneyheap.ai)

---

moneyheap is a market research tool. Its output is for information and education only. It is not financial advice or a recommendation to buy, sell or hold any security. Sentiment and confidence scores are a model's read of the evidence at one moment, not forecasts. See the [methodology](https://moneyheap.ai/legal/methodology) and [risk disclosures](https://moneyheap.ai/legal/risk).
