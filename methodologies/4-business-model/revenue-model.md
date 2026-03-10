# Revenue Model

<!-- model: opus -->

## When to use

Always runs in step 4 (wave 1). Builds complete unit economics, pricing tiers, revenue projections, and CAC/LTV analysis for each solution.

## Inputs needed

- brief.md
- step-3/decisions.md
- step-3/{item-slug}/competitor-mapping.md
- step-3/{item-slug}/scout-enrichment.md
- step-3/{item-slug}/opportunity-ranking.md
- step-3/synthesis.md

## Process

1. **Read all inputs.** Understand the solution's value proposition, target market, competitive landscape, and opportunity score. Pay special attention to competitor pricing and monetization models from competitor-mapping.md and scout-enrichment.md.

2. **Define revenue streams.** For this solution, identify all plausible revenue streams:
   - Primary revenue (subscriptions, transactions, commissions, licensing, etc.)
   - Secondary revenue (data monetization, premium features, API access, advertising)
   - Platform revenue (if applicable — marketplace fees, payment processing margin)
   - For each stream: describe the mechanism, who pays, and when

3. **Build pricing tiers.** Design 2-4 pricing tiers:
   - Free/freemium tier (if applicable) — what's included, conversion assumptions
   - Core paid tier — price point, target customer, value justification
   - Premium/enterprise tier — price point, additional features, target segment
   - For each tier: justify the price relative to competitors found in scout-enrichment.md and competitor-mapping.md

4. **Calculate unit economics:**
   - **CAC (Customer Acquisition Cost):** Estimate per-channel CAC based on market norms for this geography and vertical. Break down: paid acquisition, organic, viral/referral, partnership channels. Use CIS-specific benchmarks where available.
   - **LTV (Lifetime Value):** Estimate based on ARPU × gross margin × average lifetime. Model churn assumptions explicitly.
   - **LTV:CAC ratio:** Calculate and assess health (target >3:1)
   - **Payback period:** Months to recover CAC
   - **Gross margin:** Revenue minus direct costs (hosting, payment processing, content, support)

5. **Build 3-year revenue projections.** Model Year 1, Year 2, Year 3:
   - User/customer growth assumptions (monthly, with sources)
   - Conversion rates (free→paid, trial→paid)
   - ARPU trajectory (expansion revenue, tier migration)
   - Revenue by stream and tier
   - Include bear case, base case, bull case scenarios

6. **Identify revenue risks.** List the 3-5 biggest risks to the revenue model:
   - Price sensitivity in target market
   - Competitor pricing pressure
   - Regulatory impact on monetization
   - Platform dependency risks
   - Payment infrastructure limitations in CIS

## Output format

```markdown
# Revenue Model — [Solution Name]

*Date: [today]*

## Revenue Streams

### Primary: [stream name]
- **Mechanism:** [how money flows]
- **Who pays:** [customer segment]
- **When:** [trigger — transaction, subscription renewal, usage threshold]
- **Expected contribution:** [% of total revenue]

### Secondary: [stream name]
[same structure]

## Pricing Tiers

| Tier | Price | Target Customer | Key Features | Competitor Benchmark |
|---|---|---|---|---|
| [Free] | $0 | [segment] | [features] | [competitor comparison] |
| [Core] | $[X]/mo | [segment] | [features] | [competitor comparison] |
| [Premium] | $[X]/mo | [segment] | [features] | [competitor comparison] |

**Pricing rationale:** [2-3 sentences on why these price points work in the CIS market context]

## Unit Economics

| Metric | Value | Assumption | Confidence |
|---|---|---|---|
| CAC (blended) | $[X] | [source] | [high/medium/low] |
| CAC (paid) | $[X] | [source] | [confidence] |
| CAC (organic) | $[X] | [source] | [confidence] |
| LTV | $[X] | [calculation] | [confidence] |
| LTV:CAC | [X]:1 | — | — |
| Payback period | [X] months | — | — |
| Gross margin | [X]% | [breakdown] | [confidence] |
| Monthly churn | [X]% | [source] | [confidence] |

## 3-Year Revenue Projections

### Base Case

| Metric | Year 1 | Year 2 | Year 3 |
|---|---|---|---|
| Total users | [X] | [X] | [X] |
| Paying users | [X] | [X] | [X] |
| Conversion rate | [X]% | [X]% | [X]% |
| ARPU (monthly) | $[X] | $[X] | $[X] |
| MRR (end of year) | $[X] | $[X] | $[X] |
| ARR (end of year) | $[X] | $[X] | $[X] |
| Gross revenue | $[X] | $[X] | $[X] |

### Bear Case
[same table with conservative assumptions — note what changed]

### Bull Case
[same table with optimistic assumptions — note what changed]

**Key assumptions:**
1. [assumption + source/rationale]
2. [assumption + source/rationale]
3. [assumption + source/rationale]

## Revenue Risks

| # | Risk | Severity | Likelihood | Impact on Model |
|---|---|---|---|---|
| 1 | [risk] | [high/medium/low] | [high/medium/low] | [what breaks if this happens] |
| 2 | [risk] | [severity] | [likelihood] | [impact] |

## Sources Used

- [URL — must match a citation above]
```
