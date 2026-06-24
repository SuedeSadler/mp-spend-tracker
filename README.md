# Where Did It Go? — NZ Ministerial Spend Tracker

A single-page, client-side dashboard that visualises NZ executive expenses across four quarters (Apr 2025 – Mar 2026), adjusted for each minister's portfolio and travel obligations.

Built in a day as part of a weekly portfolio series demonstrating forward deployed engineering — parachute in, find real public data, make it readable.

---

## What it does

- Visualises **$7.1M** in ministerial expenses across 30 members of the executive
- Breaks down spend by **internal costs vs international travel** for each minister
- Assigns each minister their **portfolio** and rates international spend against what the role actually demands
- Three-tier verdict system: **Expected / Elevated / Scrutiny**
- Click any minister for a full breakdown, portfolio context, and a "what this could buy" converter
- Sort by total spend, international travel, domestic costs, or flagged ministers first

---

## Data source

All figures sourced directly from the **Department of Internal Affairs** quarterly executive expense disclosures:

- [Apr–Jun 2025](https://www.dia.govt.nz/ministerial-expenses)
- [Jul–Sep 2025](https://www.dia.govt.nz/ministerial-expenses)
- [Oct–Dec 2025](https://www.dia.govt.nz/ministerial-expenses)
- [Jan–Mar 2026](https://www.dia.govt.nz/ministerial-expenses)

Figures exclude GST, Fringe Benefit Tax, and depreciation. International travel figures include ministers, spouses, and staff where applicable. Negative values (refunds) are treated as zero.

Portfolio assignments reflect roles held **during the expense period**. The April 2026 cabinet reshuffle occurred after the final quarter closes and is noted in affected minister profiles.

---

## Verdict methodology

Each minister is assigned a travel expectation level based on their portfolio:

| Level | Portfolios | International threshold |
|-------|-----------|------------------------|
| High | PM, Foreign Affairs, Trade, Defence, Finance | Up to $200k expected |
| Medium | Education, Climate, Customs, Environment, Tourism | Up to $80k expected |
| Low | Housing, Police, Social Development, Corrections, Domestic portfolios | Up to $30k expected |

Spend above the threshold for a given level is flagged as **Elevated** or **Scrutiny**. This is a starting point for analysis, not a definitive verdict — context matters and some spend may be fully justified despite the flag.

---

## Tech

- Vanilla HTML, CSS, JavaScript — no frameworks, no dependencies, no build step
- Fully client-side — no backend, no data sent anywhere
- Single file — deploy anywhere static

---

## Deploy

```bash
# Clone or download spend-tracker.html
# Drop into a Vercel project or any static host

vercel deploy
```

Or just open `spend-tracker.html` directly in a browser — it works offline.

---

## Key findings

- **Winston Peters** spent $718k on international travel — 92% of his total spend, the highest ratio in the dataset
- **Todd McClay** spent $525k internationally as Trade Minister — elevated in raw terms but consistent with the role given the India FTA signing and multiple bilateral trade missions
- **Louise Upston** (Social Development) and **Chris Bishop** (Housing) both show significant international spend against portfolios that are primarily domestic
- **James Meager** is the only minister with zero international spend across all four quarters
- International travel accounts for **45% of total executive spend** ($3.2M of $7.1M)

---

## Limitations

- Figures may include expenses from previous quarters due to invoicing timing (per DIA notes)
- International travel includes accompanying staff and spouses — not solely the minister
- Portfolio travel expectations are assigned by judgement — reasonable people may disagree on thresholds
- This tool makes no claim about whether any specific expense was appropriate or inappropriate

---

Built by [Suede Sadler](https://www.linkedin.com/in/suede-sadler) · Part of a weekly FDE portfolio series