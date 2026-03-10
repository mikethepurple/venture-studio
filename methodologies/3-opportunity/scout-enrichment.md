<!-- scope: per-solution -->

# Scout Enrichment

## When to use

Runs in step 3 when Scout data is available. Checks if `~/Claude/scout/` exists and uses it to enrich opportunity analysis with structured startup data, funding details, and investor intelligence.

## Inputs needed

- brief.md
- step-2/decisions.md

## Process

1. **Check Scout availability:** Look for `~/Claude/scout/` directory. If it doesn't exist, write a brief note that Scout data was unavailable and exit.

2. **Search Scout research:** Check `~/Claude/scout/research/` for any existing research relevant to this solution's domain.

3. **Enrich competitor data:** Use Scout to find startups in the category — funding amounts, investors, team backgrounds, launch dates. This adds quantitative depth to the competitor mapping.

4. **Investor pattern analysis:** Which VCs are actively investing in this space? What's their thesis? Are deals accelerating or slowing?

5. **Market timing signals:** When did the first startups in this space launch? Are we early, on-time, or late to the trend?

## Output format

```markdown
# Scout Enrichment — [Solution Name]

*Date: [today]*

## Scout Data Available
[yes/no — if no, stop here]

## Startup Landscape

| Company | Founded | Funding | Stage | Investors | Description |
|---|---|---|---|---|---|

## Investor Activity
- Active VCs in this space: [list]
- Total invested (last 24 months): $[X]M
- Deal trend: [accelerating/stable/slowing]

## Market Timing
- First startups appeared: [year]
- Category maturity: [early/growth/mature]
- Assessment: [are we early, on-time, or late?]
```
