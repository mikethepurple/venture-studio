# Impact Estimate

<!-- model: haiku -->

## When to use

Always runs in step 2 (wave 3). Scores each solution concept on potential impact — how many people it helps and how much pain it relieves. Does not assess feasibility or differentiation.

## Inputs needed

- brief.md
- step-1/decisions.md
- idea-dedup.md
- idea-mutation.md

## Process

1. **Collect all concepts** from idea-dedup.md and idea-mutation.md.

2. **For each concept, assess potential impact:**
   - **People helped:** How large is the addressable audience for this specific solution? (Use market size data from step-1/decisions.md)
   - **Pain relieved:** Does this eliminate the problem or just reduce it? (eliminate = high, reduce = moderate, workaround = low)
   - **New vs incremental:** Does this create a new capability or improve an existing one? (new = higher impact)
   - **Frequency of use:** Would users need this daily, weekly, or once? (daily = compounding impact)

3. **Score each concept /5 on impact:**
   - 5 = eliminates a daily pain for a large audience, creates a new capability
   - 4 = significantly reduces a frequent pain for a large audience
   - 3 = moderately reduces pain or serves a smaller audience well
   - 2 = incremental improvement or niche audience
   - 1 = marginal improvement for few people

4. **Don't assess feasibility.** A concept that would take 5 years to build can still score 5/5 on impact.

## Output format

```markdown
# Impact Estimate — [Problem Name]

*Date: [today]*

## Impact Scores

| ID | Concept | Impact /5 | People Helped | Pain Relieved | New vs Incremental | Frequency |
|---|---|---|---|---|---|---|
| S-01 | [name] | [X]/5 | [large/medium/small] | [eliminate/reduce/workaround] | [new/incremental] | [daily/weekly/once] |
| S-02 | [name] | [X]/5 | [size] | [level] | [type] | [frequency] |

[Continue for all concepts]

## Highest Impact

[Top 5 concepts by impact score — the biggest potential upside regardless of build difficulty]
```
