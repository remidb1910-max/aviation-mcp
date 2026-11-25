# Aviation MCP servers

Deterministic aviation rule calculators for AI agents, built by an airline pilot (First Officer). Each answer is computed in code, not by a language model, and cites the rule it applies.

| Server | What it answers | Try it |
|---|---|---|
| **EASA FTL Calculator** | Max FDP, in-flight rest, extensions, commander's discretion, minimum rest, acclimatisation, cumulative limits (Reg. (EU) 965/2012, CS FTL.1) | [Apify Store](https://apify.com/conradvukovic/easa-ftl) |
| **FAA Part 117 Duty & Rest Calculator** | Tables A, B and C, augmented crews, extensions, rest, cumulative limits, consecutive nights, split duty (14 CFR Part 117) | [Apify Store](https://apify.com/conradvukovic/faa-117) |
| **EU261 & UK261 Flight Compensation Calculator** | Is compensation owed and how much, cancellations, denied boarding, right to care, downgrade refunds (Reg. (EC) 261/2004, UK261) | [Apify Store](https://apify.com/conradvukovic/eu261) |

## Connect

All three are remote MCP servers (Streamable HTTP) hosted on Apify:

```
https://conradvukovic--easa-ftl.apify.actor/mcp
https://conradvukovic--faa-117.apify.actor/mcp
https://conradvukovic--eu261.apify.actor/mcp
```

Send your Apify API token as `Authorization: Bearer <token>`. Example for Claude Code:

```bash
claude mcp add --transport http easa-ftl https://conradvukovic--easa-ftl.apify.actor/mcp --header "Authorization: Bearer <APIFY_TOKEN>"
```

Or connect your assistant to `https://mcp.apify.com` (OAuth) and ask it to use these Actors.

## Pricing

Pay per call through Apify: $0.02 per calculation or lookup, $0.10 per full FDP plan, cumulative check or compensation check. Invalid inputs are not charged. No subscription.

## Registry metadata

`servers/*/server.json` describe each server for the [official MCP Registry](https://registry.modelcontextprotocol.io/); they are published by the workflow in `.github/workflows/publish-mcp.yml`.

## Disclaimer

Planning and information aids, not official sources or legal advice. The operator's approved procedures, collective agreements and the courts prevail.
