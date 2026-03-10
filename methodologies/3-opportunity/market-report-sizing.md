<!-- scope: per-market -->

# Market Report Sizing

## When to use

Always runs in step 3. Finds published market reports and public company data to calculate TAM. Produces one number — a total addressable market estimate from industry data.

## Inputs needed

- brief.md
- step-2/decisions.md

## Process

1. **Search for published market reports** on this market:
   - Search for "[industry] market size," "[industry] market report 2024/2025," "[category] TAM"
   - Check Grand View Research, Statista, IBISWorld, Fortune Business Insights for free summaries
   - Look for press releases citing market size numbers (companies often publish these when raising funding)

2. **Search for public company data** in adjacent categories:
   - Find publicly traded companies in or near this space
   - Look for revenue figures, ARR, or GMV from earnings reports, SEC filings, or financial news
   - Calculate implied market size from market share estimates

3. **Search for VC and startup data:**
   - Recent funding rounds in this space (from Crunchbase, TechCrunch, PitchBook summaries)
   - VC thesis posts or investment memos that mention market size
   - Startup pitch decks that have been shared publicly (SlideShare, press coverage)

4. **Calculate TAM:**
   - Method 1: Top-down from market reports (total market x relevant segment %)
   - Method 2: Bottom-up from public company data (revenue / estimated market share)
   - Method 3: Comparable from VC data (what investors are betting on)
   - Produce one estimate with confidence range, noting which method is most reliable

5. **Output one number** with supporting methodology.

## Output format

```markdown
# Market Report Sizing — [Market Name]

*Date: [today]*

## Published Market Data

| Source | Market Size | Year | Geography | Confidence |
|---|---|---|---|---|
| [report name] | $[X]B | [year] | [global/US/etc.] | [high/medium/low] |

## Public Company Data

| Company | Revenue/ARR | Est. Market Share | Implied Market |
|---|---|---|---|
| [name] | $[X]M | [X]% | $[X]M |

## VC / Startup Data

| Company | Funding | Valuation | Date | Source |
|---|---|---|---|---|
| [name] | $[X]M | $[X]M | [date] | [URL] |

## TAM Estimate

- **Top-down:** $[X]M — [methodology]
- **Bottom-up:** $[X]M — [methodology]
- **VC-comparable:** $[X]M — [methodology]
- **Best estimate:** $[X]M — [which method is most reliable and why]

## Sources Used

- [URL — must match a citation above]
```
