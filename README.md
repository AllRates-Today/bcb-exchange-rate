# Banco Central do Brasil Exchange Rate API client

Official **Banco Central do Brasil** (Brazil) daily exchange rates in Node.js / TypeScript — 156 currencies against the BRL, with history back to 2016. Zero dependencies, works in Node 18+, Bun, Deno, and edge runtimes (uses global `fetch`).

These are the *published central bank rates* required for tax filings, customs valuations, audits, and compliant invoicing — not moving market rates. Every response carries the publisher's own publication date.

Powered by [AllRatesToday](https://allratestoday.com/central-bank-rates-api/bcb/). Get a free API key at [allratestoday.com/register](https://allratestoday.com/register) — no credit card required.

## Install

```bash
npm install bcb-exchange-rate
```

## Quick start

```js
import { getRate, getLatestRates } from 'bcb-exchange-rate';

// One pair at the official Banco Central do Brasil rate
const pair = await getRate('USD', 'BRL', { apiKey: 'art_live_...' });
console.log(pair.rate, pair.rate_date); // e.g. USD -> BRL on the bank's own date

// The bank's full published table
const table = await getLatestRates({ apiKey: 'art_live_...' });
console.log(table.rate_date, table.rates.length);
```

## Historical data (paid plans)

```js
import { getRatesForDate, getHistory } from 'bcb-exchange-rate';

// The official table for an invoice date — weekends/holidays return the
// most recent published date, flagged via published_on_requested_date.
const day = await getRatesForDate('2026-06-30', { apiKey: 'art_live_...' });

// Daily series for one pair
const series = await getHistory(
  { source: 'USD', target: 'BRL', from: '2026-01-01' },
  { apiKey: 'art_live_...' }
);
```

## Currencies covered

Banco Central do Brasil currently publishes rates covering **157 currencies** (as of the latest table):

`AED` · `AFN` · `ALL` · `AMD` · `AOA` · `ARS` · `AUD` · `AWG` · `AZN` · `BBD` · `BDT` · `BHD` · `BIF` · `BMD` · `BND` · `BOB` · `BRL` · `BSD` · `BTN` · `BWP` · `BYN` · `BZD` · `CAD` · `CDF` · `CHF` · `CLF` · `CLP` · `CNH` · `CNY` · `COP` · `COU` · `CRC` · `CUP` · `CVE` · `CZK` · `DJF` · `DKK` · `DOP` · `DZD` · `EGP` · `ERN` · `ETB` · `EUR` · `FJD` · `FKP` · `GBP` · `GEL` · `GHS` · `GIP` · `GMD` · `GNF` · `GTQ` · `GYD` · `HKD` · `HNL` · `HTG` · `HUF` · `IDR` · `ILS` · `INR` · `IQD` · `IRR` · `ISK` · `JMD` · `JOD` · `JPY` · `KES` · `KGS` · `KHR` · `KMF` · `KRW` · `KWD` · `KYD` · `KZT` · `LAK` · `LBP` · `LKR` · `LRD` · `LSL` · `LYD` · `MAD` · `MDL` · `MGA` · `MKD` · `MMK` · `MNT` · `MOP` · `MRO` · `MRU` · `MUR` · `MVR` · `MWK` · `MXN` · `MYR` · `MZN` · `NAD` · `NGN` · `NIO` · `NOK` · `NPR` · `NZD` · `OMR` · `PAB` · `PEN` · `PGK` · `PHP` · `PKR` · `PLN` · `PYG` · `QAR` · `RON` · `RSD` · `RUB` · `RWF` · `SAR` · `SBD` · `SCR` · `SDG` · `SDR` · `SEK` · `SGD` · `SHP` · `SLL` · `SOS` · `SRD` · `SSP` · `STN` · `SVC` · `SYP` · `SZL` · `THB` · `TJS` · `TMT` · `TND` · `TOP` · `TRY` · `TTD` · `TWD` · `TZS` · `UAH` · `UGX` · `USD` · `UYU` · `UZS` · `VES` · `VND` · `VUV` · `WST` · `XAF` · `XAU` · `XCD` · `XCG` · `XOF` · `XPF` · `YER` · `ZAR` · `ZMW`

Pairs the central bank does not print directly are resolved from this table (see below).

## Published vs derived rates

If Banco Central do Brasil does not print a pair directly, the API resolves it from the bank's table (inverse, or a cross rate via BRL) and flags it `derived: true` with the `method` — so official and computed values are never confused.

## Notes

- Every request counts toward your AllRatesToday monthly quota. Rates change once per business day — cache a day's table locally and a small quota goes a long way.
- Latest rates are on every plan (including free); historical dates and time series need a [paid plan](https://allratestoday.com/pricing/).
- Full API reference: [allratestoday.com/docs#central-bank](https://allratestoday.com/docs/#central-bank) · All covered sources: [central bank rates API](https://allratestoday.com/central-bank-rates-api/)

## License

MIT
