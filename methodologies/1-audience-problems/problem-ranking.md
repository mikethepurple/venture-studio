# Problem Ranking

<!-- model: sonnet -->

## When to use

Always runs in step 1 (wave 6). Combines all scores weighted by confidence to produce a final ranked problem list. User decides at graduation.

## Inputs needed

- brief.md
- problem-dedup.md
- prevalence-check.md
- wtp-signals.md
- problem-scoring.md
- counter-evidence.md

## Process

1. **Collect all scores** for each problem:
   - Prevalence (/5) from prevalence-check.md
   - WTP (/5) from wtp-signals.md
   - Severity (/5) from problem-scoring.md
   - Frequency (/5) from problem-scoring.md
   - Underserved (/5) from problem-scoring.md
   - Confidence (/5) from counter-evidence.md

2. **Calculate composite score.** For each problem:
   - Raw score = Prevalence + WTP + Severity + Frequency + Underserved (out of /25)
   - Confidence-weighted score = Raw score x (Confidence / 5)
   - This means a 20/25 problem with 2/5 confidence scores 8, while a 15/25 problem with 5/5 confidence scores 15. Low-confidence problems aren't removed — they're ranked lower.

3. **Rank by confidence-weighted score** descending.

4. **Identify top 5-8 problems** worth investigating as opportunities in step 2.

5. **Cluster related problems.** If two problems could be solved by one product, note the cluster. Clusters are hints, not decisions — the user chooses at graduation.

6. **For each top problem, write a 2-3 sentence summary:** what the problem is, who has it, what makes it a strong opportunity, and what the key risk is (from counter-evidence).

## Output format

```markdown
# Problem Ranking — [Audience]

*Date: [today]*

## Full Ranking

| Rank | Problem | Prevalence | WTP | Severity | Frequency | Underserved | Raw /25 | Confidence | Weighted |
|---|---|---|---|---|---|---|---|---|---|
| 1 | P-[X]: [name] | [X] | [X] | [X] | [X] | [X] | [X] | [X]/5 | [X.X] |
| 2 | P-[X]: [name] | [X] | [X] | [X] | [X] | [X] | [X] | [X]/5 | [X.X] |

[Continue for all problems]

## Top Problems (Recommended for Step 2)

### 1. P-[X]: [Problem name] — Weighted: [X.X]
[2-3 sentences: what the problem is, who has it, why it's a strong opportunity, key risk from counter-evidence]

### 2. P-[X]: [Problem name] — Weighted: [X.X]
[summary]

[Continue for top 5-8]

## Problem Clusters

- **[Cluster name]:** P-[X] + P-[Y] — [why these are related and could be one solution]

## Low-Confidence Problems

[List any problems with confidence ≤2 and what would be needed to validate them]
```
