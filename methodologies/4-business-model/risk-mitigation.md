# Risk Mitigation

<!-- model: sonnet -->

## When to use

Always runs in step 4 (wave 4). Produces a concrete mitigation plan for every high and critical risk identified across all wave 1-3 outputs. Turns identified risks into actionable contingency plans.

## Inputs needed

- brief.md
- step-3/decisions.md
- revenue-model.md
- gtm-strategy.md
- counter-evidence.md
- assumption-stress-test.md
- competitive-response.md
- business-model-revision.md

## Process

1. **Collect all risks from all inputs.** Build a master risk registry by extracting risks from:
   - revenue-model.md → Revenue Risks section
   - gtm-strategy.md → GTM Risks section
   - counter-evidence.md → assumptions with confidence 1-3
   - assumption-stress-test.md → kill assumptions + low-confidence assumptions
   - competitive-response.md → threats with risk score ≥15/25
   - business-model-revision.md → remaining risks (both pre-launch testable and post-launch)

2. **Deduplicate and prioritize.** Many risks will overlap across files. Merge duplicates, keeping the most detailed version. Assign a unified severity:
   - **Critical:** Could kill the business. Must have a mitigation plan before launch.
   - **High:** Could significantly damage growth or unit economics. Should have a plan within 3 months of launch.
   - **Medium:** Manageable but needs monitoring. Plan should exist but doesn't need immediate action.
   - **Low:** Minor impact. Accept and monitor.

3. **For every Critical and High risk, design a mitigation plan:**
   - **Prevention:** What can be done NOW to reduce the probability of this risk materializing?
   - **Detection:** How will you know early if this risk is materializing? What metrics or signals to watch?
   - **Response:** If the risk materializes, what's the specific playbook? Who does what?
   - **Contingency:** If the risk can't be mitigated, what's the pivot or exit strategy?
   - **Cost of mitigation:** What does it cost (time, money, complexity) to implement this plan?
   - **Owner:** Which function/role owns this mitigation? (product, engineering, legal, ops, growth)

4. **For Medium risks, design a monitoring plan:**
   - What signal to watch
   - At what threshold to escalate to High
   - Basic contingency if escalated

5. **Create a risk timeline.** Map risks to when they're most likely to materialize:
   - Pre-launch risks (regulatory setup, platform risk, technology risk)
   - Launch risks (month 1-3: CAC validation, conversion validation, retention)
   - Growth risks (month 4-12: competitive response, scaling challenges, regulatory changes)
   - Scale risks (year 2+: market maturation, regulation, macro environment)

6. **Identify risk interdependencies.** Which risks are correlated? If one materializes, which others become more likely? Flag risk clusters.

## Output format

```markdown
# Risk Mitigation — [Solution Name]

*Date: [today]*

## Risk Registry

### Critical Risks

| # | Risk | Source(s) | Probability | Impact | Category |
|---|---|---|---|---|---|
| R-01 | [risk] | [which input files] | [high/med/low] | [high/med/low] | [competitive/regulatory/platform/market/operational] |

### High Risks

| # | Risk | Source(s) | Probability | Impact | Category |
|---|---|---|---|---|---|
| R-XX | [risk] | [sources] | [prob] | [impact] | [category] |

### Medium Risks

| # | Risk | Source(s) | Probability | Impact | Category |
|---|---|---|---|---|---|
| R-XX | [risk] | [sources] | [prob] | [impact] | [category] |

### Low Risks (accept & monitor)

| # | Risk | Source(s) | Notes |
|---|---|---|---|
| R-XX | [risk] | [sources] | [why acceptable] |

## Mitigation Plans

### R-01: [Risk Name] — CRITICAL

**Risk:** [detailed description]
**Sources:** [which wave outputs flagged this]

**Prevention:**
- [action to reduce probability — specific, actionable]
- [action]

**Detection:**
- [metric or signal to watch]
- [threshold that triggers response]
- [monitoring frequency]

**Response playbook:**
1. [step 1 — who does what]
2. [step 2]
3. [step 3]

**Contingency (if unmitigable):**
- [pivot option or exit strategy]

**Cost of mitigation:** [time + money + complexity]
**Owner:** [function/role]
**Timeline:** [when to implement]

### R-XX: [Risk Name] — HIGH
[same structure]

[repeat for ALL critical and high risks]

## Monitoring Plans (Medium Risks)

### R-XX: [Risk Name]
- **Signal to watch:** [metric]
- **Escalation threshold:** [at what value]
- **Basic contingency:** [what to do if escalated]

[repeat for ALL medium risks]

## Risk Timeline

### Pre-Launch
| Risk | Mitigation Due | Status |
|---|---|---|
| R-XX | [date/milestone] | [to-do] |

### Launch (Month 1-3)
| Risk | Monitoring Start | Key Metric |
|---|---|---|
| R-XX | [when] | [what to watch] |

### Growth (Month 4-12)
| Risk | Likely Trigger | Response Ready? |
|---|---|---|
| R-XX | [what triggers it] | [yes/no] |

### Scale (Year 2+)
| Risk | Watch For | Strategic Response |
|---|---|---|
| R-XX | [signal] | [high-level plan] |

## Risk Interdependencies

| If this happens... | ...these risks increase: |
|---|---|
| [risk event] | [R-XX, R-YY — because...] |

## Summary

- **Total risks identified:** [X]
- **Critical:** [X] — all have mitigation plans
- **High:** [X] — all have mitigation plans
- **Medium:** [X] — all have monitoring plans
- **Low:** [X] — accepted
- **Top 3 risks to address before launch:**
  1. [R-XX: brief description]
  2. [R-XX: brief description]
  3. [R-XX: brief description]
```
