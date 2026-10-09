# Banco Central do Brasil Exchange Rates API — bcb-exchange-rate

[![npm version](https://img.shields.io/npm/v/bcb-exchange-rate.svg)](https://www.npmjs.com/package/bcb-exchange-rate)
[![license](https://img.shields.io/npm/l/bcb-exchange-rate.svg)](https://github.com/AllRates-Today/bcb-exchange-rate/blob/main/LICENSE)
[![zero dependencies](https://img.shields.io/badge/dependencies-0-brightgreen.svg)](https://www.npmjs.com/package/bcb-exchange-rate)
[![TypeScript](https://img.shields.io/badge/TypeScript-types%20included-3178C6.svg)](https://www.typescriptlang.org/)
[![USD/BRL today](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fallratestoday.com%2Fapi%2Fopen%2Fcentral-bank%2Fbcb%3Fsource%3DUSD%26target%3DBRL&query=%24.rate&label=USD%2FBRL%20published%20by%20Banco%20Central%20do%20Brasil&color=0A7E8C&cacheSeconds=3600)](https://allratestoday.com/central-bank-rates-api/bcb/)
[![rate date](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fallratestoday.com%2Fapi%2Fopen%2Fcentral-bank%2Fbcb%3Fsource%3DUSD%26target%3DBRL&query=%24.rate_date&label=rate%20date&color=555&cacheSeconds=3600)](https://allratestoday.com/central-bank-rates-api/bcb/)

**Official Banco Central do Brasil (Brazil) daily exchange rates for Node.js and TypeScript. The published central bank rates behind tax filings, customs valuations, audits, and compliant invoicing — not market estimates, but the numbers Banco Central do Brasil itself prints, every business day.**

## 🚀 Why this client?

- 🏛️ **Official published rates** — Banco Central do Brasil's own table, with the publisher's own `rate_date` on every response
- 📅 **History back to 2016** — point-in-time tables and daily series for any past date
- 🔀 **Published vs derived, always flagged** — computed inverse/cross pairs carry `derived: true`, never mixed with official prints
- ⚡ **Zero dependencies** — pure ESM + CJS over global `fetch`; Node 18+, Bun, Deno, and edge runtimes
- 🔷 **Type-safe** — full TypeScript definitions shipped with the package
- 🧾 **Compliance-grade metadata** — `rate_type`, publication date, and source disclaimer on every response

> **Official rate, not mid-market:** every value here is a number Banco Central do Brasil itself published, fixed once printed and carrying the central bank's own `rate_date` — what filings and audits require. Need the live mid-market rate for pricing or display instead? Use the [mid-market API](https://allratestoday.com/docs/) or [`@allratestoday/sdk`](https://www.npmjs.com/package/@allratestoday/sdk). The two can diverge by several percent.

## ⚡ Try it without a key

The latest Banco Central do Brasil table is also served keyless, CORS-open and edge-cached, for evaluation, embeds and AI agents:

```bash
curl "https://allratestoday.com/api/open/central-bank/bcb?source=USD&target=BRL"
```

```js
const r = await fetch('https://allratestoday.com/api/open/central-bank/bcb').then((x) => x.json());
console.log(r.rate_date, r.rates.length); // the central bank's latest published table, no key
```

The open endpoint serves the *latest* table only and asks for a visible attribution link. The client below uses the keyed API, which adds point-in-time tables, history, and CSV/XML/Excel output.

## 📈 Latest published table

Today's full Banco Central do Brasil table, straight from the central bank's latest publication. On GitHub it is refreshed by [a daily Action](.github/workflows/daily-table.yml) that reads the keyless endpoint above and commits only when the central bank publishes a new table; the copy on npm is as of the package's publish date.

<!-- daily-table:start -->
Published **2026-10-09** by Banco Central do Brasil — 312 rates, first 60 shown. Updated 2026-10-09.

| Base | Quote | Type | Rate |
| --- | --- | --- | ---: |
| AED | BRL | buy | 1.3582 |
| AED | BRL | sell | 1.3585 |
| AFN | BRL | buy | 0.0768 |
| AFN | BRL | sell | 0.07704 |
| ALL | BRL | buy | 0.06069 |
| ALL | BRL | sell | 0.06116 |
| AMD | BRL | buy | 0.01375 |
| AMD | BRL | sell | 0.01382 |
| AOA | BRL | buy | 0.005385 |
| AOA | BRL | sell | 0.005465 |
| ARS | BRL | buy | 0.003291 |
| ARS | BRL | sell | 0.003292 |
| AUD | BRL | buy | 3.4805 |
| AUD | BRL | sell | 3.483 |
| AWG | BRL | buy | 2.7714 |
| AWG | BRL | sell | 2.8029 |
| AZN | BRL | buy | 2.9259 |
| AZN | BRL | sell | 2.9435 |
| BBD | BRL | buy | 2.4573 |
| BBD | BRL | sell | 2.497 |
| BDT | BRL | buy | 0.04039 |
| BDT | BRL | sell | 0.04053 |
| BHD | BRL | buy | 13.2043 |
| BHD | BRL | sell | 13.2164 |
| BIF | BRL | buy | 0.001657 |
| BIF | BRL | sell | 0.001671 |
| BMD | BRL | buy | 4.9886 |
| BMD | BRL | sell | 4.9892 |
| BND | BRL | buy | 3.8949 |
| BND | BRL | sell | 3.8957 |
| BOB | BRL | buy | 0.4185 |
| BOB | BRL | sell | 0.4239 |
| BSD | BRL | buy | 4.9886 |
| BSD | BRL | sell | 4.9892 |
| BTN | BRL | buy | 0.05157 |
| BTN | BRL | sell | 0.05158 |
| BWP | BRL | buy | 0.3442 |
| BWP | BRL | sell | 0.3837 |
| BYN | BRL | buy | 1.6282 |
| BYN | BRL | sell | 1.6423 |
| BZD | BRL | buy | 2.4669 |
| BZD | BRL | sell | 2.4944 |
| CAD | BRL | buy | 3.4951 |
| CAD | BRL | sell | 3.4965 |
| CDF | BRL | buy | 0.00215 |
| CDF | BRL | sell | 0.002161 |
| CHF | BRL | buy | 6.0031 |
| CHF | BRL | sell | 6.0067 |
| CLF | BRL | buy | 209.5112 |
| CLF | BRL | sell | 209.5364 |
| CLP | BRL | buy | 0.005094 |
| CLP | BRL | sell | 0.0051 |
| CNH | BRL | buy | 0.7453 |
| CNH | BRL | sell | 0.7454 |
| CNY | BRL | buy | 0.7454 |
| CNY | BRL | sell | 0.7455 |
| COP | BRL | buy | 0.001564 |
| COP | BRL | sell | 0.001565 |
| COU | BRL | buy | 0.65 |
| COU | BRL | sell | 0.6501 |

[Full table on the Banco Central do Brasil rates page](https://allratestoday.com/central-bank-rates-api/bcb/) · Source: [Official rates published by BCB, served by AllRatesToday](https://allratestoday.com/central-bank-rates-api/bcb/). Rates are as printed by the central bank; AllRatesToday is not affiliated with it.
<!-- daily-table:end -->

## 🔑 Get your API key

Get a free API key at [allratestoday.com/register](https://allratestoday.com/register) — no credit card required. Latest rates are on every plan, including free.

## 📦 Installation

```bash
npm install bcb-exchange-rate
```

```bash
yarn add bcb-exchange-rate
```

```bash
pnpm add bcb-exchange-rate
```

Requires Node 18+ (global `fetch`); also runs on Bun, Deno and edge runtimes. Also published under the org scope as [`@allratestoday/bcb-exchange-rate`](https://www.npmjs.com/package/@allratestoday/bcb-exchange-rate) — same code, same versions.

## 🏁 Quick start

```js
import { getRate } from 'bcb-exchange-rate';

const pair = await getRate('USD', 'BRL', { apiKey: 'art_live_...' });
console.log(pair.rate, pair.rate_date); // the official Banco Central do Brasil rate, on the central bank's own date
```

## 📚 API reference

- [Latest pair rate](#latest-pair-rate) — one pair from the latest published table
- [Full published table](#full-published-table) — everything the central bank printed, in one call
- [Table for a date](#table-for-a-date) — the official table for an invoice or filing date
- [Daily time series](#daily-time-series) — one pair across a date range

---

### Latest pair rate

Free plan and up. Pairs the central bank does not print directly are resolved from its table and flagged (see *Published vs derived rates* below).

```js
const pair = await getRate('USD', 'BRL', { apiKey: 'art_live_...' });
```

**Response:**

```javascript
{
  bank: 'bcb',
  name: 'Banco Central do Brasil',
  rate_date: '2026-10-08',   // Banco Central do Brasil's own publication date
  source: 'USD',
  target: 'BRL',
  rate: 5.0119,
  rate_type: 'sell',
  derived: false,
  method: 'published',
  disclaimer: 'Official rates as published by the named central bank. On weekends/holidays the most recent published rate_date is returned.'
}
```

### Full published table

Free plan and up. The complete table for the latest publication date.

```js
import { getLatestRates } from 'bcb-exchange-rate';

const table = await getLatestRates({ apiKey: 'art_live_...' });
console.log(table.rate_date, table.rates.length);
```

**Response:**

```javascript
{
  bank: 'bcb',
  name: 'Banco Central do Brasil',
  rate_date: '2026-10-08',
  rates: [
    { "base": "USD", "quote": "BRL", "type": "sell", "value": 5.0119 },
    { "base": "USD", "quote": "BRL", "type": "buy", "value": 5.0113 },
    // … the rest of the published table (156 currencies vs BRL)
  ],
  disclaimer: '…'
}
```

### Table for a date

Paid plans. The official table for any date since 2016 — weekends and holidays return the most recent published date, flagged via `published_on_requested_date`, which is exactly the in-force rate a filing needs.

```js
import { getRatesForDate } from 'bcb-exchange-rate';

const day = await getRatesForDate('2026-06-30', { apiKey: 'art_live_...' });
// Optionally narrow to one pair:
const one = await getRatesForDate('2026-06-30', { apiKey: 'art_live_...', source: 'USD', target: 'BRL' });
```

**Response:**

```javascript
{
  bank: 'bcb',
  requested_date: '2026-06-30',
  rate_date: '2026-06-30',                // the date actually published
  published_on_requested_date: true,      // false when a weekend/holiday fell back
  rates: [ /* the full table for that date */ ],
  disclaimer: '…'
}
```

### Daily time series

Paid plans. One resolved rate per publication date — ready for charting, revaluation runs, or audit workpapers.

```js
import { getHistory } from 'bcb-exchange-rate';

const series = await getHistory(
  { source: 'USD', target: 'BRL', from: '2026-01-01', to: '2026-10-08' },
  { apiKey: 'art_live_...' }
);
```

**Response:**

```javascript
{
  bank: 'bcb',
  source: 'USD',
  target: 'BRL',
  from: '2026-01-01',
  to: '2026-10-08',
  count: 152,
  rates: [
    // one entry per publication date
    { date: '2026-10-08', rate: 5.0119, rate_type: 'sell', derived: false, method: 'published' },
    // …
  ],
  disclaimer: '…'
}
```

Pass `{ symbol: 'USD' }` instead of `source`/`target` to get the raw published rows for one currency (all rate types, no pair resolution).

---

## 🗺️ Currencies covered

Banco Central do Brasil currently publishes rates covering **156 currencies** against the BRL (as of the latest table):

🇦🇪 `AED` · 🇦🇫 `AFN` · 🇦🇱 `ALL` · 🇦🇲 `AMD` · 🇦🇴 `AOA` · 🇦🇷 `ARS` · 🇦🇺 `AUD` · 🇦🇼 `AWG` · 🇦🇿 `AZN` · 🇧🇧 `BBD` · 🇧🇩 `BDT` · 🇧🇭 `BHD` · 🇧🇮 `BIF` · 🇧🇲 `BMD` · 🇧🇳 `BND` · 🇧🇴 `BOB` · 🇧🇸 `BSD` · 🇧🇹 `BTN` · 🇧🇼 `BWP` · 🇧🇾 `BYN` · 🇧🇿 `BZD` · 🇨🇦 `CAD` · 🇨🇩 `CDF` · 🇨🇭 `CHF` · 🇨🇱 `CLF` · 🇨🇱 `CLP` · 🇨🇳 `CNH` · 🇨🇳 `CNY` · 🇨🇴 `COP` · 🇨🇴 `COU` · 🇨🇷 `CRC` · 🇨🇺 `CUP` · 🇨🇻 `CVE` · 🇨🇿 `CZK` · 🇩🇯 `DJF` · 🇩🇰 `DKK` · 🇩🇴 `DOP` · 🇩🇿 `DZD` · 🇪🇬 `EGP` · 🇪🇷 `ERN` · 🇪🇹 `ETB` · 🇪🇺 `EUR` · 🇫🇯 `FJD` · 🇫🇰 `FKP` · 🇬🇧 `GBP` · 🇬🇪 `GEL` · 🇬🇭 `GHS` · 🇬🇮 `GIP` · 🇬🇲 `GMD` · 🇬🇳 `GNF` · 🇬🇹 `GTQ` · 🇬🇾 `GYD` · 🇭🇰 `HKD` · 🇭🇳 `HNL` · 🇭🇹 `HTG` · 🇭🇺 `HUF` · 🇮🇩 `IDR` · 🇮🇱 `ILS` · 🇮🇳 `INR` · 🇮🇶 `IQD` · 🇮🇷 `IRR` · 🇮🇸 `ISK` · 🇯🇲 `JMD` · 🇯🇴 `JOD` · 🇯🇵 `JPY` · 🇰🇪 `KES` · 🇰🇬 `KGS` · 🇰🇭 `KHR` · 🇰🇲 `KMF` · 🇰🇷 `KRW` · 🇰🇼 `KWD` · 🇰🇾 `KYD` · 🇰🇿 `KZT` · 🇱🇦 `LAK` · 🇱🇧 `LBP` · 🇱🇰 `LKR` · 🇱🇷 `LRD` · 🇱🇸 `LSL` · 🇱🇾 `LYD` · 🇲🇦 `MAD` · 🇲🇩 `MDL` · 🇲🇬 `MGA` · 🇲🇰 `MKD` · 🇲🇲 `MMK` · 🇲🇳 `MNT` · 🇲🇴 `MOP` · 🇲🇷 `MRO` · 🇲🇷 `MRU` · 🇲🇺 `MUR` · 🇲🇻 `MVR` · 🇲🇼 `MWK` · 🇲🇽 `MXN` · 🇲🇾 `MYR` · 🇲🇿 `MZN` · 🇳🇦 `NAD` · 🇳🇬 `NGN` · 🇳🇮 `NIO` · 🇳🇴 `NOK` · 🇳🇵 `NPR` · 🇳🇿 `NZD` · 🇴🇲 `OMR` · 🇵🇦 `PAB` · 🇵🇪 `PEN` · 🇵🇬 `PGK` · 🇵🇭 `PHP` · 🇵🇰 `PKR` · 🇵🇱 `PLN` · 🇵🇾 `PYG` · 🇶🇦 `QAR` · 🇷🇴 `RON` · 🇷🇸 `RSD` · 🇷🇺 `RUB` · 🇷🇼 `RWF` · 🇸🇦 `SAR` · 🇸🇧 `SBD` · 🇸🇨 `SCR` · 🇸🇩 `SDG` · `SDR` · 🇸🇪 `SEK` · 🇸🇬 `SGD` · 🇸🇭 `SHP` · 🇸🇱 `SLL` · 🇸🇴 `SOS` · 🇸🇷 `SRD` · 🇸🇸 `SSP` · 🇸🇹 `STN` · 🇸🇻 `SVC` · 🇸🇾 `SYP` · 🇸🇿 `SZL` · 🇹🇭 `THB` · 🇹🇯 `TJS` · 🇹🇲 `TMT` · 🇹🇳 `TND` · 🇹🇴 `TOP` · 🇹🇷 `TRY` · 🇹🇹 `TTD` · 🇹🇼 `TWD` · 🇹🇿 `TZS` · 🇺🇦 `UAH` · 🇺🇬 `UGX` · 🇺🇸 `USD` · 🇺🇾 `UYU` · 🇺🇿 `UZS` · 🇻🇪 `VES` · 🇻🇳 `VND` · 🇻🇺 `VUV` · 🇼🇸 `WST` · `XAF` · `XAU` · `XCD` · `XCG` · `XOF` · `XPF` · 🇾🇪 `YER` · 🇿🇦 `ZAR` · 🇿🇲 `ZMW`

## 🏛️ Source

Banco Central do Brasil is Brazil's central bank. Its PTAX rate — the official reference rate for the real — is calculated from dealer surveys during each business day, with the closing bulletin published in the early afternoon Brasília time. The bulletin covers around 155 currencies, and its closing sell rate is also the rate Brazilian customs uses to value imports under Portaria MF nº 6/1999 — so Brazil has no separate tax-authority rate.

- Publisher's own page: [PTAX exchange rates](https://www.bcb.gov.br/en/financialstability/exchangerate) · [www.bcb.gov.br](https://www.bcb.gov.br)
- Publication: every business day; the exact schedule, freshness status and any current delay are on the [Banco Central do Brasil rates page](https://allratestoday.com/central-bank-rates-api/bcb/)
- Values are stored unmodified, with the publisher's own `rate_date` on every row — see the [methodology](https://allratestoday.com/official-rates-methodology/)

## 🧭 Reading the numbers

- `value` is always **quote currency per 1 unit of base currency** (`base: "EUR", quote: "USD", value: 1.15` means 1 EUR = 1.15 USD).
- Banco Central do Brasil quotes **BRL per 1 unit of foreign currency** (e.g. `base: "USD", quote: "BRL"` means BRL per one US dollar).
- Need the other way round? Ask `getRate(target, source)` and the API inverts or crosses for you, flagged `derived: true` — never divide a published rate yourself in a compliance workflow.
- Precious-metal codes (`XAU`, `XAG`, `XPT`, `XPD`) are quoted **per troy ounce**.
- `rate_type` tells you which of the central bank's series a row belongs to (`sell` here); some publishers print buy/sell or several fixings for the same pair.

## 🧩 ERP & accounting systems

Loading the official Banco Central do Brasil rate into an accounting system is a supported workflow, not a hack. Step-by-step guides with the direction each system expects:

- [Dynamics 365 Business Central](https://allratestoday.com/docs/integrations/business-central/) — built-in Currency Exchange Rate Service, no code
- [Xero](https://allratestoday.com/docs/integrations/xero/) · [QuickBooks Online](https://allratestoday.com/docs/integrations/quickbooks/) · [SAP S/4HANA and ECC](https://allratestoday.com/docs/integrations/sap/) · [Odoo](https://allratestoday.com/docs/integrations/odoo/)

The same keyed endpoints return `?format=csv`, `?format=xml` and `?format=xlsx`, and accept the key as `?api_key=` on the URL for importers that cannot send headers:

```bash
curl "https://allratestoday.com/api/v1/central-bank/bcb/latest?format=xml&api_key=art_live_..."
```

## 🤖 AI agents

- MCP server: `npx -y @allratestoday/central-bank-mcp` (stdio) or the hosted endpoint `https://allratestoday.com/api/mcp` — tools for official rates, history, cross-bank comparison and publication calendars
- Already using the general SDK or MCP server? Since 2026-10-01 [`@allratestoday/sdk`](https://www.npmjs.com/package/@allratestoday/sdk) 1.4+ has `officialRates('bcb')` and [`@allratestoday/mcp-server`](https://www.npmjs.com/package/@allratestoday/mcp-server) 0.6+ has a `get_official_rates` tool — both return this source's latest table with no key, so you can add it without a second dependency
- Claude Code plugin (no key): `/plugin marketplace add AllRates-Today/claude-code-plugin` then `/plugin install allratestoday@allratestoday` — bundles both MCP servers plus an `/official-rate bcb ...` command
- Machine-readable site guide: [llms.txt](https://allratestoday.com/llms.txt) · [for-ai-agents](https://allratestoday.com/for-ai-agents/)

## ⚖️ Published vs derived rates

If Banco Central do Brasil does not print a pair directly, the API resolves it from the central bank's own table and says so — official and computed values are never confused:

| `method` | `derived` | Meaning |
| --- | --- | --- |
| `published` | `false` | The central bank printed this pair directly |
| `inverse` | `true` | Computed as 1 ÷ the published opposite direction |
| `cross` | `true` | Computed via BRL from two published rates |

## 🛡️ Error handling

Errors are thrown as `Error` with `status` (HTTP code) and `body` (the API's JSON error) attached:

```js
try {
  const pair = await getRate('USD', 'XXX', { apiKey: 'art_live_...' });
} catch (err) {
  console.log(err.message); // human-readable reason
  console.log(err.status);  // e.g. 404
}
```

| Status | Meaning |
| ------ | ------- |
| — | Missing `apiKey` (thrown before any request) |
| `400` | Malformed date or parameters |
| `401` | Invalid API key |
| `403` | Endpoint needs a [paid plan](https://allratestoday.com/pricing/) (historical dates & series) |
| `404` | Pair or date range not covered by Banco Central do Brasil |
| `429` | Monthly quota exceeded |

## 🔷 TypeScript

Full definitions ship with the package — no `@types` install:

```ts
import type { LatestRates, PairRate, DatedRates, RateEntry, HistoryQuery, RequestOptions } from 'bcb-exchange-rate';
```

## 📦 CommonJS

```javascript
const { getRate } = require('bcb-exchange-rate');

getRate('USD', 'BRL', { apiKey: 'art_live_...' }).then((pair) => console.log(pair.rate));
```

## 💡 Quota tips

- Rates change once per business day — cache the published table locally and a small monthly quota goes a long way.
- Every request counts toward your AllRatesToday quota, shared across all AllRatesToday endpoints on your key.

## 📖 Methods reference

| Method | Plan | Description |
| ------ | ---- | ----------- |
| `getRate(source, target, { apiKey })` | Free | Latest rate for one pair, resolved from the published table |
| `getLatestRates({ apiKey })` | Free | The central bank's full latest published table |
| `getRatesForDate(date, { apiKey, source?, target? })` | Paid | The official table (or one pair) for a YYYY-MM-DD date |
| `getHistory({ symbol \| source+target, from?, to? }, { apiKey })` | Paid | Daily series since 2016 |

## 📥 Bulk data (no key)

Need the whole archive rather than an API call? The same published tables are mirrored daily as open data:

- Hugging Face: [AllRates/central-bank-exchange-rates](https://huggingface.co/datasets/AllRates/central-bank-exchange-rates) — one CSV per institution (`rates/bcb.csv`)
- Kaggle: [allratestoday/central-bank-exchange-rates](https://www.kaggle.com/datasets/allratestoday/central-bank-exchange-rates)
- CDN JSON: `https://cdn.jsdelivr.net/gh/AllRates-Today/central-bank-exchange-rates@main/data/bcb/latest.json`

## 🔗 Links

- [Banco Central do Brasil rates page](https://allratestoday.com/central-bank-rates-api/bcb/) — live table, publication cadence, FAQ
- [All central bank sources](https://allratestoday.com/central-bank-rates-api/)
- [Package docs on the site](https://allratestoday.com/docs/sdk/bcb-exchange-rate/) · [ERP integration guides](https://allratestoday.com/docs/integrations/)
- [API documentation](https://allratestoday.com/docs/#central-bank) · [Interactive reference](https://allratestoday.com/api-reference/) · [Methodology](https://allratestoday.com/official-rates-methodology/)
- [Register (free)](https://allratestoday.com/register) · [Pricing](https://allratestoday.com/pricing/)
- [GitHub](https://github.com/AllRates-Today/bcb-exchange-rate)

## 📜 License

MIT
