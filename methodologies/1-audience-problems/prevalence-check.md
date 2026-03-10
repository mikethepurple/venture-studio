# Prevalence Check

## When to use

Always runs in step 1 (wave 4). Scores each problem on prevalence — how many people in the audience actually have this problem. Uses web research signals, not judgment.

## Inputs needed

- brief.md
- problem-dedup.md

## Process

1. **Read problem-dedup.md** and list all problems (P-01, P-02, etc.).

2. **For each problem, research these prevalence signals:**
   - **Google Trends:** Search related terms. Is interest rising, flat, or declining? Compare to baseline terms for context.
   - **Community size:** Find subreddits, groups, or forums specifically about this problem. How many members? How active?
   - **Competitor count:** How many products/services already address this? More competitors = more validated demand.
   - **Job postings:** Are companies hiring for roles that exist to solve this problem manually?

3. **Score each problem /5 on prevalence.** Evidence quality gates apply:
   - 5 = nearly everyone in the audience — requires 2+ independent, recent (<3yr), geo-relevant sources
   - 4 = most of the audience — requires 2+ independent sources (minor recency/geo gaps OK)
   - 3 = **cap for single-source or dated (>3yr) evidence**, even if the claim says "nearly everyone"
   - 2 = limited evidence suggests a smaller segment
   - 1 = rare edge case or no credible evidence

4. **Tag source quality** for each key claim:
   - `[dated source: YYYY]` — older than 3 years
   - `[weak source]` — wrong geography, different audience, or unreliable outlet

5. **Don't score WTP, severity, or frequency.** Those are separate agents. Only score prevalence.

## Output format

```markdown
# Prevalence Check — [Audience]

*Date: [today]*

## Prevalence Scores

### P-01: [Problem name]
**Prevalence:** [X]/5
**Google Trends:** [rising/flat/declining] — [search terms used]
**Community size:** [data]
**Competitor count:** [X products found]
**Job postings:** [data or "none found"]
**Source quality:** [list any `[dated source]` or `[weak source]` tags]

### P-02: [Problem name]
**Prevalence:** [X]/5
[same structure]

[Continue for all problems]

## Summary

| Problem | Prevalence /5 | Strongest Signal | Source Quality |
|---|---|---|---|
| P-01 | [X] | [one-line] | [clean / dated / weak] |
| P-02 | [X] | [one-line] | [quality] |
```
