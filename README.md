# EU TED Tenders Scraper — MCP Server

Every EU public tender, award and change notice from TED — the EU's official procurement journal — as clean structured records from your AI agent or MCP client. This Actor reads TED through the Publications Office's official Search API v3 (keyless — no API key, no login, no scraping) and turns it into flat, analysis-ready records: buyer, title, CPV codes, place of performance, the submission deadline, estimated value, and — on award notices — who won and for how much. With monitoring mode on, scheduled runs deliver only the notices you haven't seen.

This repo is the MCP listing for the [EU TED Tenders Scraper](https://apify.com/magnova/eu-ted-tenders-scraper) Actor by Magnova on Apify. The server is hosted by Apify at the pinned endpoint below — there is nothing to install or run from this repository; you just point your MCP client at the URL.

## Tools

The pinned connection loads a focused tool set:

- **magnova--eu-ted-tenders-scraper** — Search EU TED tenders, awards and change notices via the official Search API v3, with an optional only-new monitoring mode. Returns structured records: publication number, buyer, title, CPV codes, deadline, estimated value, and award winners.
- **fetch-actor-details** — Fetch the Actor's full input schema, pricing, and documentation, so an agent can check parameters and cost before running it.
- **get-actor-run / get-dataset-items** — Run and storage helpers, loaded automatically, used to fetch the results a run produced.

## Connect

Pinned endpoint (Streamable HTTP):

```
https://mcp.apify.com?tools=fetch-actor-details,magnova/eu-ted-tenders-scraper
```

On first connect, your client will ask you to sign in with your Apify account (OAuth). If your client cannot do OAuth, pass your Apify API token as an `Authorization: Bearer <YOUR_APIFY_TOKEN>` header instead.

### Cursor / VS Code / other Streamable HTTP clients

```json
{
  "mcpServers": {
    "eu-ted-tenders-scraper": {
      "url": "https://mcp.apify.com?tools=fetch-actor-details,magnova/eu-ted-tenders-scraper"
    }
  }
}
```

### Claude Desktop

Claude Desktop's config file only runs local commands, so use the `mcp-remote` bridge:

```json
{
  "mcpServers": {
    "eu-ted-tenders-scraper": {
      "command": "npx",
      "args": [
        "-y",
        "mcp-remote",
        "https://mcp.apify.com?tools=fetch-actor-details,magnova/eu-ted-tenders-scraper"
      ]
    }
  }
}
```

The same pinned URL also lives in this repo's `.mcp.json`, and `server.json` is the listing for the Official MCP Registry, published as `io.github.memeanalyst/eu-ted-tenders-scraper-mcp`.

## Pricing

Pay per event, billed to your own Apify account: **$0.005 per notice returned — $5 per 1,000 notices**. No start fee, no subscription, and you are only charged for records actually delivered.

## Links

- Actor on Apify Store: https://apify.com/magnova/eu-ted-tenders-scraper
- MCP endpoint: https://mcp.apify.com?tools=fetch-actor-details,magnova/eu-ted-tenders-scraper

*Tender records come from TED's official Search API v3 — no scraping, no API key.*
