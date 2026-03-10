# Business Model Revision

<!-- model: opus -->

## When to use

Always runs in step 4 (wave 3). Revises the revenue model by incorporating all stress-test findings from wave 2. Produces the final defensible business model with adjusted projections and validated assumptions.

## Inputs needed

- brief.md
- step-3/decisions.md
- revenue-model.md
- gtm-strategy.md
- pricing-research.md
- counter-evidence.md
- assumption-stress-test.md
- competitive-response.md

## Process

1. **Read all inputs.** Pay particular attention to:
   - Kill assumptions from assumption-stress-test.md (confidence 1-2)
   - Strong counter-evidence from counter-evidence.md
   - Critical and high threats from competitive-response.md
   - Pricing benchmarks from pricing-research.md that contradict revenue-model.md assumptions

2. **Triage findings by impact.** Create a list of all issues raised in wave 2, categorized as:
   - **Must fix:** Assumptions scored 1-2, strong counter-evidence, critical competitive threats. The model is wrong or indefensible without addressing these.
   - **Should adjust:** Assumptions scored 3, moderate counter-evidence, high threats. The model is optimistic but not broken.
   - **Acceptable risk:** Assumptions scored 4-5, weak/no counter-evidence, medium/low threats. The model holds.

3. **Revise the revenue model.** For each "must fix" and "should adjust" item:
   - State the original assumption and its score/evidence
   - State the revised assumption and why
   - Recalculate the affected metrics (CAC, LTV, conversion, churn, ARPU, projections)
   - If a revenue stream is no longer viable, remove it and note why
   - If pricing needs adjustment based on pricing-research.md WTP data, adjust

4. **Rebuild 3-year projections.** Using the revised assumptions:
   - New base case (adjusted for all "must fix" items)
   - New bear case (adjusted for "must fix" + "should adjust" items)
   - New bull case (only "must fix" items adjusted, "should adjust" left optimistic)
   - Compare old vs new projections — show the delta

5. **Validate unit economics.** With revised numbers:
   - Does LTV:CAC still exceed 3:1? If not, what needs to change?
   - Is payback period still reasonable (<12 months)? If not, what needs to change?
   - Is gross margin still healthy? What's the floor?

6. **Produce the final defensible model.** This is the "real" business model — stripped of optimistic assumptions, battle-tested against counter-evidence, and adjusted for competitive reality. This is what you'd present to a skeptical investor.

7. **List remaining risks.** After all revisions, what assumptions are still unvalidated? What can't be known until launch? Rank these as pre-launch testable vs only-knowable-post-launch.

## Output format

```markdown
# Business Model Revision — [Solution Name]

*Date: [today]*

## Revision Summary

**Issues addressed:** [X] must-fix, [X] should-adjust, [X] acceptable-risk
**Model health after revision:** [healthy / viable-with-caveats / needs-pivot]

## Issues Triage

### Must Fix
| # | Issue | Source | Original Value | Impact |
|---|---|---|---|---|
| 1 | [issue] | [which wave-2 file] | [original assumption] | [what breaks] |

### Should Adjust
| # | Issue | Source | Original Value | Impact |
|---|---|---|---|---|
| 1 | [issue] | [source] | [value] | [impact] |

### Acceptable Risk
| # | Issue | Source | Rationale for Accepting |
|---|---|---|---|
| 1 | [issue] | [source] | [why it's OK] |

## Revised Assumptions

| # | Assumption | Original | Revised | Rationale | New Confidence /5 |
|---|---|---|---|---|---|
| 1 | [assumption] | [old value] | [new value] | [why changed, citing wave-2 evidence] | [X]/5 |
| 2 | [assumption] | [old value] | [new value] | [rationale] | [X]/5 |

## Revised Revenue Streams

### [Stream 1: name]
- **Status:** [kept / modified / removed]
- **Changes:** [what changed and why]
- **Revised contribution:** [% of total]

### [Stream 2: name]
[same structure]

## Revised Pricing

| Tier | Original Price | Revised Price | Rationale |
|---|---|---|---|
| [tier] | $[X] | $[X] | [citing pricing-research.md + WTP data] |

## Revised Unit Economics

| Metric | Original | Revised | Delta | Health Check |
|---|---|---|---|---|
| CAC (blended) | $[X] | $[X] | [+/-X%] | [pass/fail] |
| LTV | $[X] | $[X] | [delta] | [pass/fail] |
| LTV:CAC | [X]:1 | [X]:1 | [delta] | [>3:1?] |
| Payback period | [X] mo | [X] mo | [delta] | [<12mo?] |
| Gross margin | [X]% | [X]% | [delta] | [>60%?] |
| Monthly churn | [X]% | [X]% | [delta] | [<5%?] |

## Revised 3-Year Projections

### New Base Case (all must-fix + should-adjust revisions)

| Metric | Year 1 | Year 2 | Year 3 |
|---|---|---|---|
| Total users | [X] | [X] | [X] |
| Paying users | [X] | [X] | [X] |
| Conversion rate | [X]% | [X]% | [X]% |
| ARPU (monthly) | $[X] | $[X] | $[X] |
| ARR (end of year) | $[X] | $[X] | $[X] |

### Old vs New Comparison

| Metric | Old Base Y3 | New Base Y3 | Delta |
|---|---|---|---|
| ARR | $[X] | $[X] | [+/-X%] |
| Paying users | [X] | [X] | [+/-X%] |
| LTV:CAC | [X]:1 | [X]:1 | [delta] |

### New Bear Case
[same table with conservative revisions]

### New Bull Case
[same table with only must-fix revisions]

## Remaining Risks

### Pre-Launch Testable
| # | Risk | How to Test | Cost to Test | Timeline |
|---|---|---|---|---|
| 1 | [risk] | [experiment] | $[X] | [X weeks] |

### Only Knowable Post-Launch
| # | Risk | What to Monitor | Decision Trigger |
|---|---|---|---|
| 1 | [risk] | [metric to watch] | [at what value do you pivot] |

## Final Model Assessment

**Viability:** [viable / conditionally viable / not viable]
**Key strength:** [what makes this model work]
**Key vulnerability:** [biggest remaining risk]
**Investor pitch readiness:** [ready / needs work on X / not ready]
```
