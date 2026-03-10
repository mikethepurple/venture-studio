<!-- scope: per-market -->

# Market Signals

## When to use

Always runs in step 3. Assesses whether the market has real, growing demand by looking at search trends, funding activity, community discussion, and job postings.

## Inputs needed

- brief.md
- step-2/decisions.md

## Process

1. **Search volume trends:** Search for Google Trends data on terms related to this market. Is interest growing, flat, or declining? What specific phrases are people searching?

2. **Funding activity:** Search for VC funding in this market. How much has been invested in the last 24 months? Are deals getting larger? Which VCs are active?

3. **Community discussion:** Search Reddit, forums, and Slack communities for organic discussion in this market. Look for repeated questions with no satisfying answers, active threads with 50+ comments, and DIY workarounds.

4. **Job postings:** Search for roles that exist in this market. Are companies hiring for roles that didn't exist 2 years ago?

5. **Market sizing (bottom-up):**
   - Who is the target customer in this market?
   - How many exist?
   - What would they pay? (check pricing of adjacent tools)
   - Realistic 3-year penetration rate?
   - TAM = customers x price x penetration

## Output format

```markdown
# Market Signals — [Market Name]

*Date: [today]*

## Demand Signals

| Signal Type | Strength | Evidence |
|---|---|---|
| Search trends | Strong/Moderate/Weak | [data] |
| Funding activity | Strong/Moderate/Weak | [data] |
| Community discussion | Strong/Moderate/Weak | [data] |
| Job postings | Strong/Moderate/Weak | [data] |

## Market Size Estimate
- Target customer: [who]
- Number of potential customers: [X]
- Annual price point: $[X] (based on [comparable tools])
- Realistic penetration: [X]%
- TAM estimate: $[X]M

## Strongest Signals
1. [signal + evidence + source]
2. [signal + evidence + source]

## Weak or Missing Signals
- [what you expected to find but didn't]

## Confidence Level
[High/Medium/Low] — [one sentence rationale]
```
