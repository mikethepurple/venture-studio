# Analytics Reader

## When to use

Runs in step 6 execution (analytics phase). Reads validation data from the current iteration and produces a recommendation: scale, iterate, pivot, or stop.

## Inputs needed

- brief.md
- step-5/*.md (metrics, success criteria, hypothesis database)
- Current iteration's build and marketing outputs
- Any analytics data provided by the user or available via GA4

## Process

1. **Gather data** from the current iteration:
   - Total traffic (sessions/clicks)
   - Conversion rate (and absolute conversions)
   - Traffic source breakdown
   - Time on page / bounce rate
   - Any qualitative signals (comments, replies, DMs)
   - If analytics data isn't available, ask the user to paste key metrics

2. **Diagnose the funnel:**
   | Stage | Metric | Problem if low |
   |---|---|---|
   | Traffic volume | Total clicks | Traffic source failing (budget, targeting, creative) |
   | Engagement | Bounce rate, time on page | Wrong audience or confusing message |
   | Conversion | Form submits, purchases | CTA friction, price, or trust gap |
   | Quality | Reply rate, interview rate | Wrong audience attracted |

3. **Compare to success criteria** from step-5 metrics (not industry averages — the specific thresholds set before the campaign ran).

4. **Make a recommendation:**
   | Signal | Recommendation |
   |---|---|
   | Above threshold | **Scale:** increase budget, expand traffic, build next thing |
   | At threshold | **Iterate:** test new messaging or audience, run longer |
   | Below with traffic | **Diagnose:** is it traffic, page, or offer? |
   | Below no traffic | **Fix traffic** first before concluding |
   | Small sample (<500 clicks) | **Get more data** before deciding |

5. **Specific next actions** — not vague ("improve copy") but specific ("rewrite headline to lead with [pain point], test against current in ad set 3").

## Output format

```markdown
# Analytics — Iteration [N]

*Date: [today]*

## Raw Metrics
| Metric | Value | Target | Status |
|---|---|---|---|
| Traffic | [X] sessions | [target] | [above/below] |
| Conversion rate | [X]% | [target]% | [above/below] |
| Conversions | [X] | [target] | [above/below] |

## Funnel Diagnosis
[which stage is the bottleneck and why]

## Signal Assessment
**Verdict:** [Strong / Minimum / Below / Inconclusive]
[2-3 sentences comparing results to pre-set criteria]

## Recommendation
**[Scale / Iterate / Pivot / Stop / Get more data]**

## Next Actions
1. [Specific action]
2. [Specific action]
3. [Specific action]
```
