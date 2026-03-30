## Stablecoin Remittance Cost Comparison for Pakistan

## Overview
Complete data-driven analysis comparing total cost of sending $500 to Pakistan through 4 channels (Banks, MTOs, Mobile Wallets, Stablecoin) across 5 major corridors (UAE, Saudi Arabia, UK, US, Qatar).

**Analysis Date:** March 30, 2026  
**Transfer Amount:** USD 500  
**Reference Rate:** USD/PKR 279.5 (interbank)  
**SBP Policy Rate:** 10.5% per annum

## Project Contents

### 1. Data Files (`/data/`)

#### `rpw_raw.csv`
Raw provider data from 45 remittance providers across 4 channel types and 5 corridors.
- **Columns:** corridor, provider_type, provider_name, fee_pct, fx_margin_pct, total_cost_pct, transfer_speed, source, date_collected
- **Rows:** 45 providers (Banks, MTOs, Mobile Wallets, Stablecoin platforms)
- **Sources:** HBL, Standard Chartered, Barclays, HSBC, Wise, Remitly, Western Union, Binance P2P, OKX P2P, etc.

#### `cost_matrix.csv`
Complete 5×4 cost breakdown with all calculated fields.
- **Columns:** corridor, channel, sending_fee_usd, fx_spread_pct, fx_spread_usd, receiving_fee_usd, network_fee_usd, settlement_days, time_cost_usd, all_in_cost_usd, all_in_cost_pct
- **Rows:** 20 data points (5 corridors × 4 channels)
- **Key Insight:** Mobile wallets cheapest (avg 2.10%), banks most expensive (avg 13.31%)

#### `stablecoin_snapshot.csv`
Point-in-time P2P rate data from Binance P2P and OKX P2P.
- **Columns:** platform, pair, direction, rate_pkr, trader_count, min_trade, payment_method, timestamp_pkt, date
- **Rows:** 20 trades (10 buy, 10 sell across 2 platforms)
- **Median Buy:** 280.5 PKR/USDT
- **Median Sell:** 278.0 PKR/USDT
- **Spread:** 1.5% (from 277.0-281.0 range)

#### `methodology_notes.md`
Comprehensive technical documentation including:
- Data collection sources with URLs
- Assumptions (time value, FX spreads, settlement periods)
- Fee components breakdown
- Calculation methodology with examples
- Key findings by corridor
- Limitations and caveats
- Regulatory context and compliance gaps
- Recommendations by user type



### 3. Key Findings

| Metric | Value | Notes |
|--------|-------|-------|
| Cheapest overall | 1.70% (Saudi Arabia, Mobile Wallets) | USD 8.51 |
| Most expensive | 16.11% (US via Banks) | USD 80.56 |
| Bank average | 13.31% | Range: 10.89% - 16.12% |
| MTO average | 2.80% | Wise, Remitly, Western Union |
| Mobile wallet average | 2.10% | JazzCash/Easypaisa via partners |
| Stablecoin average | 2.48% | Binance/OKX P2P, with counterparty risk |
| Savings vs banks | 81% | Using mobile wallets |

### 4. Corridors Analyzed

1. **UAE → Pakistan** ($7.83B/year remittance volume)
   - Cheapest: Mobile Wallets (1.90%)
   - Reference: Binance P2P median 280.5 PKR

2. **Saudi Arabia → Pakistan** ($9.34B/year)
   - Cheapest: Mobile Wallets (1.70%)
   - Largest corridor by volume

3. **UK → Pakistan** ($5.99B/year)
   - Cheapest: Mobile Wallets (2.40%)
   - Highest bank cost (14.61%)

4. **US → Pakistan** ($3.72B/year)
   - Cheapest: Stablecoin (2.00%)
   - Only corridor where stablecoin outcompetes MTOs

5. **Qatar → Pakistan** (~$1.5B/year estimated)
   - Cheapest: Mobile Wallets (2.60%)
   - Widest spreads due to smaller ecosystem


## How to Use

1. **Open `index.html` in a modern web browser** for the interactive analysis
2. **Use corridor filter buttons** to view individual corridors
3. **Hover over table rows** to see highlighted costs
4. **Read methodology_notes.md** for technical details and assumptions
5. **Share linkedin_article.md** for professional/social media publication
6. **Reference data CSVs** for further analysis or updates

## Data Quality & Caveats

### High Confidence
- Banking data from official rate cards (March 2026)
- MTO data from live platform screenshots
- Mobile wallet data from integration documentation
- Settlement times from platform specifications

### Point-in-Time Snapshot
- Stablecoin P2P rates are volatile (±2-3% daily)
- Snapshot collected March 28, 2026, 14:32-14:50 PKT
- Actual trading conditions vary hourly
- Not suitable for timing market entry/exit

### Known Limitations
- Retail pricing only (corporate/bulk rates better)
- No counterparty risk priced into stablecoin analysis
- Settlement timing may vary by day/time
- Bank rates assume standard international transfers
- No regulatory compliance costs included
- Mobile wallet availability varies by partner

## Regulatory Context (March 2026)

- Pakistan Virtual Assets Act 2026 passed parliament
- PVARA (Pakistan Virtual Assets Regulatory Authority) established
- **SBP has NOT yet authorized stablecoin remittance corridors**
- Foreign Exchange Manual predates crypto framework
- Current: Stablecoin P2P operates in regulatory gray area
- Future: SBP guidance could enable compliant stablecoin rails

See `index.html` policy section and `methodology_notes.md` for full regulatory analysis.

## Analyst Information

- **Created by:** Fawad Liaqat
- **Date:** March 30, 2026
- **Purpose:** Portfolio analysis / fintech research / diaspora education
- **Sources:** Public rate cards, live platform data, regulatory documentation

## Next Steps / Updates

This is a living analysis. To keep it current:
1. Re-collect stablecoin P2P data weekly (high volatility)
2. Re-check MTO rates monthly (moderate drift)
3. Re-check bank rates quarterly (stable)
4. Monitor SBP announcements on stablecoin policy
5. Track PVARA licensing framework developments
6. Update FY26 remittance volume data as released

## Contact & Feedback

Questions about methodology, data sources, or findings? This analysis is designed to be reproducible and challengeable. All sources are linked and documented.

---

**Document Version:** 1.0  
**Last Updated:** March 28, 2026  
**Status:** Production-ready
