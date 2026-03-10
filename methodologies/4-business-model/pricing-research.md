# Pricing Research

<!-- model: haiku -->

## When to use

Always runs in step 4 (wave 1). Web research on competitor pricing, willingness-to-pay data, and CIS payment norms. Provides pricing evidence for the revenue model.

## Inputs needed

- brief.md
- step-3/decisions.md
- step-3/{item-slug}/competitor-mapping.md
- step-3/{item-slug}/scout-enrichment.md

## Process

1. **Read inputs.** Identify the solution, its category, and competitors from competitor-mapping.md and scout-enrichment.md.

2. **Research competitor pricing.** For each major competitor identified:
   - Search for "[competitor] pricing," "[competitor] plans," "[competitor] fees"
   - Document: free tier features, paid tier prices, enterprise pricing, transaction fees
   - Note any CIS-specific pricing (localized pricing, regional discounts)
   - Cover both direct competitors and adjacent platforms (betting platforms, fintech apps, crypto exchanges)

3. **Research willingness-to-pay in CIS markets.**
   - Search for average spending on: mobile apps, gambling/betting, crypto trading, financial services in Russia, Kazakhstan, Georgia, Armenia
   - Search for: "average bet size Russia," "crypto trading volume CIS," "Telegram premium adoption CIS"
   - Look for income data and purchasing power parity adjustments for CIS countries
   - Find any surveys or reports on willingness-to-pay for prediction/betting/fintech services

4. **Research CIS payment norms.**
   - Search for: payment methods in Russia/CIS (cards, e-wallets, USDT, TON, bank transfers)
   - Crypto adoption rates by country (Russia, KZ, GE, AM, UZ)
   - USDT usage patterns (P2P volumes, exchange volumes, Telegram trading bots)
   - TON wallet adoption and transaction volumes
   - Payment friction points (sanctions, card processing limitations, fiat on/off ramps)

5. **Research prediction market / betting market economics.**
   - Search for: "prediction market take rate," "betting margin," "Kalshi fees," "Polymarket fees"
   - Sports betting margin benchmarks (typically 5-15%)
   - Prediction market commission structures
   - Market maker economics and spread models

6. **Compile pricing benchmarks.** Create a structured summary of all pricing data found, organized by category.

## Output format

```markdown
# Pricing Research — [Solution Name]

*Date: [today]*

## Competitor Pricing

| Competitor | Free Tier | Paid Tier | Premium/Enterprise | Transaction Fees | Geography |
|---|---|---|---|---|---|
| [name] | [features] | $[X]/mo | $[X]/mo | [X]% | [countries] |
| [name] | [features] | $[X]/mo | $[X]/mo | [X]% | [countries] |

### Detailed Competitor Pricing

#### [Competitor Name]
- **Pricing model:** [subscription / transaction / freemium / etc.]
- **Price points:** [detail]
- **CIS-specific:** [localized pricing if any]
- **Source:** [URL]

[repeat for each competitor]

## Willingness-to-Pay Data

### CIS Market Spending Benchmarks

| Category | Russia | Kazakhstan | Georgia | Armenia | Source |
|---|---|---|---|---|---|
| Avg monthly mobile app spend | $[X] | $[X] | $[X] | $[X] | [source] |
| Avg monthly betting spend | $[X] | $[X] | $[X] | $[X] | [source] |
| Avg crypto transaction size | $[X] | $[X] | $[X] | $[X] | [source] |
| Avg monthly income | $[X] | $[X] | $[X] | $[X] | [source] |

### Key WTP Findings
1. [finding with source]
2. [finding with source]
3. [finding with source]

## CIS Payment Landscape

### Payment Method Adoption

| Method | Russia | Kazakhstan | Georgia | Armenia | Trend |
|---|---|---|---|---|---|
| Bank cards | [adoption %] | [%] | [%] | [%] | [growing/stable/declining] |
| USDT (P2P) | [adoption] | [adoption] | [adoption] | [adoption] | [trend] |
| TON Wallet | [adoption] | [adoption] | [adoption] | [adoption] | [trend] |
| E-wallets (QIWI, YooMoney) | [adoption] | [adoption] | [adoption] | [adoption] | [trend] |

### Payment Friction Points
1. [friction point — specific to CIS/sanctions context]
2. [friction point]
3. [friction point]

### Crypto On/Off Ramp Options
- [option + availability + fees]

## Prediction Market / Betting Economics

| Platform Type | Take Rate | Spread | Fee Structure | Source |
|---|---|---|---|---|
| Prediction markets (Kalshi) | [X]% | [X]% | [details] | [URL] |
| Prediction markets (Polymarket) | [X]% | [X]% | [details] | [URL] |
| Sports betting (typical) | [X]% | [X]% | [details] | [URL] |
| Crypto betting | [X]% | [X]% | [details] | [URL] |

## Pricing Recommendations

Based on the research above:
1. **Suggested price range:** [range with rationale tied to competitor data + WTP data]
2. **Suggested fee structure:** [transaction vs subscription vs hybrid, with benchmarks]
3. **CIS adjustment factor:** [how much to adjust vs Western pricing, based on PPP and income data]

## Sources Used

- [URL — must match a citation above]
```
