<!-- scope: per-solution -->

# Ad Reach Sizing

## When to use

Always runs in step 3. Estimates audience size for this specific solution using Meta and Google ad reach calculators. Produces one number — a total addressable audience estimate from ad platform data.

## Inputs needed

- brief.md
- step-2/decisions.md

## Process

1. **Build a targeting spec** for the audience this solution serves, using brief.md and step-2/decisions.md for context:
   - Demographics: age range, gender, geography
   - Interests: tools, publications, competitors, hobbies the audience follows
   - Behaviors: job titles, purchase behaviors, device usage

2. **Estimate Meta (Facebook/Instagram) reach:**
   - Search for what Meta's ad manager would report for these targeting parameters
   - Look for published case studies, ad benchmarking reports, or social media marketing blogs that share reach estimates for similar audiences
   - Record the estimated monthly active users for this targeting spec

3. **Estimate Google Ads reach:**
   - Search for Google Keyword Planner data on terms related to this audience and their problems
   - Look for published search volume data, SEMrush/Ahrefs reports, or marketing case studies
   - Record monthly search volume for the top 10-15 relevant keywords

4. **Extrapolate to total population:**
   - Ad platform reach ≈ addressable online audience
   - Note: not everyone is on Meta or searches Google — adjust for platform penetration in this audience's demographics
   - Produce one total audience size estimate with confidence range (low/mid/high)

5. **Output one number** with supporting methodology. This is a sizing input for opportunity-ranking, not a standalone analysis.

## Output format

```markdown
# Ad Reach Sizing — [Solution Name]

*Date: [today]*

## Targeting Spec

| Parameter | Value |
|---|---|
| Age | [range] |
| Geography | [regions] |
| Interests | [list] |
| Behaviors | [list] |

## Meta Reach Estimate

- Estimated monthly reach: [X]
- Source: [how this was estimated]
- Confidence: [high/medium/low]

## Google Search Volume

| Keyword | Monthly Volume | Trend |
|---|---|---|
| [keyword] | [X] | [rising/flat/declining] |

- Total monthly search volume: [X]
- Source: [how this was estimated]

## Total Audience Size Estimate

- **Low:** [X]
- **Mid:** [X]
- **High:** [X]
- **Methodology:** [1-2 sentences on how you derived the estimate]

## Sources Used

- [URL — must match a citation above]
```
