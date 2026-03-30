# Methodology Notes: Stablecoin Remittance Cost Comparison for Pakistan

## Data Snapshot Details
- **Analysis Date**: March 30, 2026
- **Transfer Amount**: USD 500
- **Reference Rate (Interbank)**: USD/PKR 279.60 ([HamariWeb](https://hamariweb.com/finance/forex/inter_bank_rates.aspx), [Forex.pk](https://www.forex.pk/inter_bank_rates.asp))
- **Policy Rate (SBP)**: 10.5% per annum ([SBP Monetary Policy](https://www.sbp.org.pk/m_policy/index.asp))
- **Daily Time Cost**: USD 500 × (10.5% / 365) = USD 0.14/day

## Data Sources

### Banking & Traditional Wire Transfers
- **HBL (Habib Bank Limited)**: https://www.hbl.com/ - International remittance fees and FX margins (March 2026)
- **Standard Chartered Pakistan**: https://www.sc.com/pk/ - Wire transfer pricing
- **Barclays International**: https://www.barclays.com/international-banking/ - SWIFT transfer documentation
- **HSBC Cross-Border Payments**: https://www.hsbc.com/ - International payments
- **Riyad Bank Saudi Arabia**: https://www.riyadbank.com/ - Regional remittance rates
- **Samba Financial Group**: https://www.samba.com.sa/ - Saudi remittance offerings
- **Bank of America International**: https://www.bankofamerica.com/ - US international wire
- **Chase International**: https://www.chase.com/ - US international banking
- **Doha Bank Qatar**: https://www.dohabank.com.qa/ - Qatar remittance rates
- **Qatar National Bank**: https://www.qnb.com/ - Qatar banking services

### Money Transfer Operators (MTOs)
- **Western Union**: https://www.westernunion.com/us/en/send-money-to-pakistan.html - $0 fee on bank transfers >$200, 2-4% FX margin ([WU fee analysis](https://wise.com/us/compare/western-union-exchange-rate))
- **Wise (formerly TransferWise)**: https://wise.com/us/send-money/send-money-to-pakistan - $1.17 + 0.8% fee, mid-market rate ([Wise pricing](https://wise.com/us/pricing/send-money))
- **Remitly**: https://www.remitly.com/us/en/pakistan - $1.99 fee + 1-3.7% FX margin ([Remitly rate analysis](https://wise.com/us/compare/remitly-exchange-rate))
- **WorldRemit**: https://www.worldremit.com/en/pakistan - Pakistan mobile money integration

### Mobile Wallet Partners
- **JazzCash via Remitly**: https://www.remitly.com/us/en/providers-pakistan/send-money-to-jazzcash
- **Easypaisa via WorldRemit**: https://www.worldremit.com/en/pakistan/mobile-money
- **Remitly Pakistan**: Direct integration with JazzCash and Easypaisa

### Stablecoin P2P Platforms
- **Binance P2P**: https://p2p.binance.com/en/express/BUY/USDT/PKR - USDT/PKR trading (snapshot collected March 30, 2026, 14:15-14:31 PKT). Buy median: 280.65, Sell median: 278.12. Spread ~0.9%.
- **OKX P2P**: https://www.okx.com/en-us/convert/usdt-to-pkr - USDT/PKR spot rates. 1 USDT = ~279.21 PKR ([OKX converter](https://www.okx.com/en-us/convert/usdt-to-pkr))

### Exchange Rate References
- **USD/PKR Interbank**: https://hamariweb.com/finance/forex/inter_bank_rates.aspx - Buying: 279.25, Selling: 279.75 (March 30, 2026)
- **USD/PKR Forex.pk**: https://www.forex.pk/inter_bank_rates.asp - Interbank midpoint: 279.60
- **USDT/PKR Live**: ~278.97 PKR per USDT ([Binance price](https://www.binance.com/en/price/tether/PKR))

### Global Benchmarks
- **World Bank RPW**: https://remittanceprices.worldbank.org/ - Global avg 6.49%, South Asia avg 4.80% (Q1 2025)
- **World Bank Corridor Data**: https://remittanceprices.worldbank.org/corridor/United-States/Pakistan

### Policy & Regulatory References
- **State Bank of Pakistan FE Manual**: https://www.sbp.org.pk/fe_manual/index.htm
- **SBP Monetary Policy**: https://www.sbp.org.pk/m_policy/index.asp - Policy rate 10.5%
- **Pakistan Virtual Assets Act 2026**: Parliamentary records (passed March 2026)
- **Pakistan Virtual Assets Regulatory Authority (PVARA)**: Established under 2026 Act
- **SECP Regulatory Sandbox**: https://www.secp.gov.pk/

## Core Assumptions

### Time Value of Money
- SBP policy discount rate: 10.5% per annum
- Daily time cost: Settlement delays are valued using daily accrual
- Applies only to settlement period; no additional capital lockup assumed
- Formula: `time_cost = settlement_days × (10.5% / 365) × $500`

### FX Rates & Spreads
- Interbank midpoint: USD/PKR 279.60 (Source: [HamariWeb](https://hamariweb.com/finance/forex/inter_bank_rates.aspx), [Forex.pk](https://www.forex.pk/inter_bank_rates.asp))
- Bank spreads (3.8-4.5%): Represent average dealer margins on SWIFT transfers
- MTO spreads (1.5-2.5%): Based on live platform comparisons (Wise uses mid-market rate with 0% FX markup)
- Stablecoin P2P spreads (~0.9%): Median bid-ask across Binance and OKX on March 30 collection
- No assumption of rate arbitrage or holding gains

### Settlement Periods
- **Banks (SWIFT)**: 3-4 business days depending on corridor
- **MTOs**: 1 hour average (instant to next-day depending on receiving method)
- **Mobile Wallets**: 1-2 hours (digital credit to beneficiary account)
- **Stablecoin**: 2 hours (assumes fiat on-ramp delay ~30 min + on-chain settlement ~30 min + P2P matching ~60 min)

### Fee Components Included
- **Sending fees**: Originating country bank/platform charge
- **FX spreads**: Calculated as margin % applied to base $500
- **Receiving fees**: Final destination bank or wallet credit charges (zero for all channels analyzed)
- **Network fees**: SWIFT network charges for banks; on-chain gas for stablecoin (TRC20 ~$1)
- **Platform costs**: Exchanges fees, P2P trading margins, deposit/withdrawal spreads

### Stablecoin-Specific Assumptions
1. **On-chain cost**: USDT TRC20 network fee ~$1 USD (Tron network - cheapest option)
2. **P2P spread**: Median 1.5% buy-sell gap, not full round-trip
3. **Fiat on-ramp**: 0.1% (US) to 1.0% (UK, Qatar) depending on local payment rail efficiency
4. **Trading fee**: 0.1% on exchange (Binance/OKX maker rate)
5. **Counterparty risk**: NOT included in cost - P2P requires trust in trader (material caveat)
6. **Receive side**: Assumes stablecoin conversion to PKR via local P2P (no premium charged)

## Calculation Methodology

### Step 1: FX Spread Cost
```
FX Spread Cost ($) = FX Margin (%) × $500
Example: 4.2% × $500 = $21.00
```

### Step 2: Time Cost
```
Time Cost ($) = Settlement Days × ($0.14/day)
Example: 3 days × $0.14 = $0.42
```

### Step 3: Total All-In Cost (USD)
```
All-In Cost ($) = Sending Fee + FX Spread + Receiving Fee + Network Fee + Time Cost
Example Bank Transfer:
  = $25 + $21 + $0 + $15 + $0.42 = $61.42
```

### Step 4: All-In Cost as Percentage
```
All-In Cost (%) = (All-In Cost / $500) × 100
Example: ($61.42 / $500) × 100 = 12.28%
```

## Key Findings

### Cheapest Option by Corridor
- **UAE**: Stablecoin P2P (1.30% / $6.51)
- **Saudi Arabia**: Stablecoin P2P (1.30% / $6.51)
- **UK**: Stablecoin P2P (1.30% / $6.51)
- **US**: Stablecoin P2P (1.30% / $6.51)
- **Qatar**: Stablecoin P2P (1.30% / $6.51)

Note: Stablecoin is cheapest on pure cost but carries unpriced counterparty risk (P2P trader) and regulatory uncertainty (SBP authorization pending). For regulated options, Mobile Wallets are the second-cheapest across all corridors.

### Channel Comparison (Average Across All Corridors)
| Channel | Avg Cost (%) | Avg Cost ($) |
|---------|--------------|--------------|
| Banks | 13.31% | $66.52 |
| MTOs | 2.80% | $14.01 |
| Mobile Wallets | 2.10% | $10.51 |
| Stablecoin | 1.30% | $6.51 |

Note: Stablecoin sending_fee = on-ramp fee ($0.50) + platform trade fee ($0.50). P2P spread (0.9% × $500 = $4.50) and TRC20 network fee ($1.00) listed separately. Stablecoin cost is uniform across corridors because P2P spread is exchange-side, not corridor-dependent.

## Data Quality & Limitations

### Known Limitations
1. **Stablecoin rates are volatile**: P2P data represents a 20-minute window on March 30, 2026 (14:15–14:31 PKT). Rates fluctuate hourly and daily.
2. **No counterparty risk included**: Stablecoin P2P trades involve direct dealer/trader counterparty risk not priced in.
3. **No regulatory compliance costs**: Stablecoin corridors may face future compliance requirements not yet established.
4. **Bank rates may vary by tier**: Large customers get better rates; analysis assumes retail pricing.
5. **Settlement speed varies by day/time**: Weekends and off-hours may extend SWIFT settlement.
6. **Mobile wallet availability**: JazzCash/Easypaisa integration varies by remittance partner.
7. **Pakistan receive-side conversion**: Assumes instant USDT→PKR P2P conversion; actual rates may differ.

### Data Collection Caveats
- **Banking data**: Sourced from public rate cards (March 2026); actual execution rates may differ
- **MTO data**: Live rates from platform interfaces; subject to geographic and product limitations
- **Stablecoin data**: Snapshot from two major P2P platforms; does not include all possible traders
- **No transaction volume assumption**: Analysis assumes single $500 remittance; bulk rates would be lower
- **Exchange rate assumption**: Uses fixed 279.5 midpoint; actual rates fluctuate ±2-3% daily

## Regulatory Context

### Current Status (March 2026)
- **Pakistan Virtual Assets Act 2026**: Passed parliament; creates PVARA as regulatory body
- **SBP Position**: Has NOT yet issued specific guidance on stablecoin remittance corridors
- **FX Manual Constraints**: Current Foreign Exchange Manual (https://www.sbp.org.pk/fe_manual/index.htm) predates crypto framework
- **SECP Sandbox**: 2nd cohort approved real estate tokenization; digital payment tokens still under review

### Compliance Gaps
- No explicit authorization for USD stablecoin as remittance vehicle
- FX Manual capital account restrictions may technically apply
- AML/KYC requirements for P2P trades undefined
- Tax treatment of stablecoin gains/losses uncertain

## Recommendations for Users

1. **Best Current Option**: Mobile wallets (JazzCash/Easypaisa) offer 1.7-2.4% costs with low regulatory risk
2. **Stablecoin Timing**: Wait for SBP guidance if compliance is critical; cost advantage currently modest (~0.7%)
3. **Large Transfers**: Banks become more competitive >$5,000 due to fixed fee structures
4. **Urgent Transfers**: MTOs and mobile wallets optimal due to 1-2 hour settlement
5. **Batch Transfers**: Consider stablecoin once regulatory framework clarifies

## Analyst Notes
- Analysis conducted by Fawad Liaqat
- All costs expressed in USD nominal terms
- No currency futures or hedging strategies included
- Tax implications not analyzed (beneficiary jurisdiction matters)
- Pakistan's FDI policy may affect future stablecoin regulatory status
