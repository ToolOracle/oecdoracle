# OECDOracle MCP Server

OECD economic data via MCP (Model Context Protocol). Cache-first architecture with rate limiting.

## Features

- **GDP Growth** — Quarterly real GDP growth (YoY) for 38 OECD countries
- **Unemployment** — Monthly rates, seasonally adjusted
- **CLI** — Composite Leading Indicators (economic cycle signal)
- **CPI** — Consumer Price Index / Inflation
- **Interest Rates** — Short-term (3M), long-term (10Y), share prices
- **Country Profiles** — Full economic snapshot per country
- **G7 / EU Dashboards** — Multi-country comparison
- **13 MCP Tools** total

## Data Source

OECD SDMX REST API (`sdmx.oecd.org`). No API key required.

- Rate limit: 10 requests/minute (conservative)
- Cache: SQLite, 24h TTL for monthly data, 7d for annual
- Nightly prefetch via cron (04:00 UTC)

## Endpoint

```
https://tooloracle.io/oecd/mcp/
```

## Tools

| Tool | Description |
|------|-------------|
| `oecd_gdp` | GDP growth rate (quarterly real YoY) |
| `oecd_unemployment` | Monthly unemployment rate |
| `oecd_cli` | Composite Leading Indicators |
| `oecd_cpi` | Consumer Price Index |
| `oecd_interest_rates` | Interest rates + share prices |
| `oecd_country_compare` | Compare indicator across countries |
| `oecd_country_profile` | Full economic profile |
| `oecd_g7_dashboard` | G7 economic dashboard |
| `oecd_eu_dashboard` | EU Big-4 dashboard |
| `oecd_search` | Search indicators |
| `oecd_indicator_info` | Indicator metadata |
| `health_check` | Server status |
| `ping` | Connectivity test |

## 38 OECD Countries

AUS, AUT, BEL, CAN, CHL, COL, CRI, CZE, DNK, EST, FIN, FRA, DEU, GRC, HUN, ISL, IRL, ISR, ITA, JPN, KOR, LVA, LTU, LUX, MEX, NLD, NZL, NOR, POL, PRT, SVK, SVN, ESP, SWE, CHE, TUR, GBR, USA

## Part of ToolOracle

65 MCP servers, 589 tools. [tooloracle.io](https://tooloracle.io)

## License

MIT
