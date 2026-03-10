# Assumption Stress Test

<!-- model: sonnet -->

## When to use

Always runs in step 4 (wave 2). Red-teams every assumption in the revenue model — scores confidence, identifies breaking points, and flags assumptions that could kill the business.

## Inputs needed

- brief.md
- step-3/decisions.md
- revenue-model.md
- gtm-strategy.md
- pricing-research.md

## Process

1. **Extract every assumption from revenue-model.md.** Go line by line and identify every number, percentage, or assertion that isn't a hard fact. Categorize each as:
   - **Market assumptions:** TAM, growth rate, market timing
   - **Customer assumptions:** conversion rates, churn, ARPU, willingness-to-pay
   - **Cost assumptions:** CAC by channel, hosting costs, payment processing fees, team costs
   - **Growth assumptions:** viral coefficient, month-over-month growth, channel capacity
   - **Competitive assumptions:** market share capture, pricing power, differentiation durability

2. **For each assumption, determine the evidence basis:**
   - **Hard data:** backed by specific source (competitor data, market report, public financials)
   - **Soft data:** inferred from analogies, similar markets, or adjacent categories
   - **Guess:** no supporting evidence, pure assumption
   - Note the source quality: primary research vs secondary vs expert opinion vs nothing

3. **Stress test each assumption.** For every assumption:
   - **What's the breaking point?** At what value does this assumption break the model? (e.g., "If churn exceeds 15%/mo, LTV drops below CAC")
   - **How sensitive is the model?** If this assumption is 2x wrong, does the model still work?
   - **What's the downside scenario?** What happens in the real world if this assumption fails?
   - **Is there a way to validate before launch?** Can this be tested cheaply?

4. **Score each assumption 1-5:**
   - 5 = Well-supported by hard data, tested in comparable markets, low sensitivity
   - 4 = Supported by soft data, reasonable analogy, moderate sensitivity
   - 3 = Mixed evidence, assumption is plausible but unproven, model sensitive to it
   - 2 = Weak evidence, assumption is optimistic, model breaks if wrong
   - 1 = No evidence, assumption is a guess, model critically depends on it

5. **Identify the "kill assumptions."** Which 2-3 assumptions, if wrong, would kill the entire business model? These are the highest-priority items to validate.

6. **Produce a sensitivity matrix.** Show how key output metrics (ARR, LTV:CAC, payback period) change when the top 5 assumptions vary by -50%, -25%, +25%, +50%.

## Output format

```markdown
# Assumption Stress Test — [Solution Name]

*Date: [today]*

## Assumption Inventory

### Market Assumptions
| # | Assumption | Value Used | Evidence Basis | Source Quality | Confidence /5 |
|---|---|---|---|---|---|
| M-1 | [assumption] | [value] | [hard/soft/guess] | [quality] | [X]/5 |
| M-2 | [assumption] | [value] | [basis] | [quality] | [X]/5 |

### Customer Assumptions
| # | Assumption | Value Used | Evidence Basis | Source Quality | Confidence /5 |
|---|---|---|---|---|---|
| C-1 | [assumption] | [value] | [basis] | [quality] | [X]/5 |

### Cost Assumptions
| # | Assumption | Value Used | Evidence Basis | Source Quality | Confidence /5 |
|---|---|---|---|---|---|
| X-1 | [assumption] | [value] | [basis] | [quality] | [X]/5 |

### Growth Assumptions
| # | Assumption | Value Used | Evidence Basis | Source Quality | Confidence /5 |
|---|---|---|---|---|---|
| G-1 | [assumption] | [value] | [basis] | [quality] | [X]/5 |

### Competitive Assumptions
| # | Assumption | Value Used | Evidence Basis | Source Quality | Confidence /5 |
|---|---|---|---|---|---|
| P-1 | [assumption] | [value] | [basis] | [quality] | [X]/5 |

## Stress Test Results

### [Assumption ID]: [Assumption statement]
- **Value used:** [X]
- **Breaking point:** [at what value does the model break?]
- **Sensitivity:** [high/medium/low] — [what happens if 2x wrong]
- **Downside scenario:** [real-world consequence if wrong]
- **Pre-launch validation:** [yes/no — how to test cheaply]

[repeat for EVERY assumption]

## Kill Assumptions

These assumptions, if wrong, would kill the business model:

1. **[Assumption ID]: [statement]**
   - Why it's critical: [explanation]
   - Current confidence: [X]/5
   - Validation approach: [how to test before committing]

2. **[Assumption ID]: [statement]**
   [same structure]

3. **[Assumption ID]: [statement]**
   [same structure]

## Sensitivity Matrix

| Assumption | -50% | -25% | Base | +25% | +50% |
|---|---|---|---|---|---|
| [assumption] → ARR Y3 | $[X] | $[X] | $[X] | $[X] | $[X] |
| [assumption] → LTV:CAC | [X] | [X] | [X] | [X] | [X] |
| [assumption] → Payback (mo) | [X] | [X] | [X] | [X] | [X] |

## Summary

- **Total assumptions identified:** [X]
- **High confidence (4-5):** [X] ([%])
- **Medium confidence (3):** [X] ([%])
- **Low confidence (1-2):** [X] ([%])
- **Kill assumptions:** [X]
- **Overall model robustness:** [robust / fragile / needs work] — [one-sentence rationale]
```
