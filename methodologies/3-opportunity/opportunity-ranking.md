<!-- model: sonnet -->
<!-- scope: per-solution -->

# Opportunity Ranking

## When to use

Always runs in step 3. Ranks the solution as a business opportunity by combining all signals from other step-3 methodologies. Produces the final ranking that the user reviews at graduation.

## Inputs needed

- brief.md
- step-2/decisions.md
- trend-scanning.md (from this solution's market — read from `_markets/{market-slug}/`)
- market-signals.md (from this solution's market — read from `_markets/{market-slug}/`)
- market-report-sizing.md (from this solution's market — read from `_markets/{market-slug}/`)
- conference-mapping.md (from this solution's market — read from `_markets/{market-slug}/`)
- competitor-mapping.md (from this solution's own folder)
- scout-enrichment.md (from this solution's own folder)
- ad-reach-sizing.md (from this solution's own folder)

## Process

1. **Collect signals** from both the per-market research (trends, market signals, TAM, conferences) and per-solution research (competitors, scout data, ad reach).

2. **Score on 5 dimensions** (each /5):
   - **Market size:** Is there a path to $10M+ ARR? (5 = large addressable market, 1 = tiny niche)
   - **Trend tailwind:** Are structural trends making this more urgent? (5 = strong multi-trend tailwind, 1 = headwinds)
   - **Competitive opening:** Is there a clear positioning gap for this specific solution? (5 = wide open, 1 = incumbents dominate)
   - **Monetization clarity:** Is the revenue model obvious? (5 = clear willingness to pay at known price, 1 = unclear how to charge)
   - **Speed to validate:** Can you get a signal in weeks, not months? (5 = can validate in 2 weeks, 1 = requires months of build)

3. **Write the opportunity brief:** A 3-5 paragraph narrative summarizing why this solution is (or isn't) a strong business opportunity. Include specific data points from both market-level and solution-level research.

## Output format

```markdown
# Opportunity Ranking — [Solution Name]

*Date: [today]*

## Score

| Dimension | Score | Rationale |
|---|---|---|
| Market size | /5 | [one line] |
| Trend tailwind | /5 | [one line] |
| Competitive opening | /5 | [one line] |
| Monetization clarity | /5 | [one line] |
| Speed to validate | /5 | [one line] |
| **Total** | **/25** | |

## Opportunity Brief

[3-5 paragraphs: what the opportunity is, why it's attractive, what the risks are, and how this solution is positioned to capture it]

## Key Risk

[The single biggest reason this opportunity might not work]

## Recommended Positioning Angle

[One sentence: how should this solution be positioned to maximize its market opportunity?]
```
