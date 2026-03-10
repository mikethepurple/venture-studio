# GTM Revision

<!-- model: sonnet -->

## When to use

Always runs in step 4 (wave 4). Revises the GTM strategy based on counter-evidence and competitive response findings from wave 2. Produces a battle-tested go-to-market plan.

## Inputs needed

- brief.md
- step-3/decisions.md
- gtm-strategy.md
- pricing-research.md
- counter-evidence.md
- competitive-response.md
- business-model-revision.md

## Process

1. **Read all inputs.** Focus on:
   - Counter-evidence that challenges GTM assumptions (channel effectiveness, CAC estimates, viral coefficients)
   - Competitive response scenarios that affect channel strategy (competitor blocking, platform risk)
   - Business model revision changes that affect GTM (revised pricing, new target segments, dropped features)
   - Pricing research data that informs channel budget allocation and messaging

2. **Audit every GTM assumption against wave 2 findings.** For each element of the original GTM:
   - **Channel strategy:** Are the proposed channels still viable given competitive response? Any channels blocked by platform risk?
   - **Launch sequence:** Does the phasing still make sense given counter-evidence about time-to-market and competitive urgency?
   - **Growth loops:** Are the viral assumptions supported or contradicted? What's the realistic viral coefficient?
   - **Budget allocation:** Does the budget make sense given revised CAC from business-model-revision.md?
   - **Partnership strategy:** Are proposed partnerships still feasible given competitive and regulatory landscape?

3. **Revise the channel strategy.** For each channel:
   - **Keep as-is:** Channel is well-supported, no significant counter-evidence
   - **Adjust:** Channel is viable but assumptions need recalibrating (revised CAC, different timeline, modified tactics)
   - **Deprioritize:** Counter-evidence or competitive response makes this channel risky or uneconomical
   - **Add:** Wave 2 findings suggest a new channel not considered in the original GTM
   - For each change: cite the specific finding from wave 2 that drives the revision

4. **Revise the launch sequence.** Based on:
   - Competitive urgency (from competitive-response.md — how fast do competitors move?)
   - Regulatory timeline (from competitive-response.md — when do regulations change?)
   - Revised budget (from business-model-revision.md)
   - Counter-evidence about market timing

5. **Revise growth loops.** For each proposed loop:
   - Is the mechanism validated or challenged by counter-evidence?
   - What's the realistic coefficient/impact?
   - Are there new growth loops suggested by the competitive analysis?

6. **Produce a revised GTM with change log.** Show what changed and why, so the reader can track the evolution from the original GTM through the stress test.

## Output format

```markdown
# GTM Revision — [Solution Name]

*Date: [today]*

## Revision Summary

**Changes made:** [X] channels adjusted, [X] deprioritized, [X] added
**Launch sequence:** [unchanged / modified / significantly reworked]
**Budget impact:** [+/-X% from original]
**Overall GTM health:** [strong / viable / needs-more-work]

## Change Log

| # | Element | Original | Revised | Reason | Source |
|---|---|---|---|---|---|
| 1 | [channel/tactic/assumption] | [what it was] | [what it is now] | [why] | [which wave-2 file] |
| 2 | [element] | [original] | [revised] | [reason] | [source] |

## Revised Channel Strategy

| Channel | Status | Revised CAC | Revised Volume | Priority | Change Reason |
|---|---|---|---|---|---|
| [channel] | [keep/adjust/deprioritize/new] | $[X] | [volume] | [P1/P2/P3] | [brief reason] |

### Channel Details (Revised)

#### [Channel Name] — [KEPT / ADJUSTED / DEPRIORITIZED / NEW]
- **Original plan:** [what the original GTM proposed]
- **What changed:** [specific revision, or "unchanged" if kept]
- **Evidence:** [specific finding from wave-2 that drove the change]
- **Revised tactics:** [updated tactics]
- **Revised budget (Year 1):** $[X] (was: $[X])
- **Revised expected users:** [X] (was: [X])

[repeat for each channel]

## Revised Launch Sequence

### Phase 1: Seed (Month 1-3)
- **Goal:** [X] users (was: [X])
- **Budget:** $[X] (was: $[X])
- **Key changes from original:**
  - [change + reason]
- **Revised tactics:**
  1. [tactic]
  2. [tactic]
- **Success metrics:** [what proves this phase worked]

### Phase 2: Growth (Month 4-8)
[same structure]

### Phase 3: Scale (Month 9-12)
[same structure]

## Revised Growth Loops

### Loop 1: [Name] — [KEPT / ADJUSTED / REMOVED]
- **Original mechanism:** [what was proposed]
- **Counter-evidence:** [what wave-2 found]
- **Revised mechanism:** [updated version or "removed — replaced by Loop X"]
- **Revised viral coefficient:** [X] (was: [X])

### Loop 2: [Name]
[same structure]

### [New Loop Name] — NEW
- **Why added:** [evidence from wave-2 suggesting this opportunity]
- **Mechanism:** [how it works]
- **Expected impact:** [realistic estimate]

## Revised Partnership Strategy

| Partner Type | Status | Original Plan | Revised Plan | Reason |
|---|---|---|---|---|
| [type] | [keep/adjust/drop/new] | [original] | [revised] | [reason] |

## Revised Budget Summary (Year 1)

| Category | Original | Revised | Delta | Rationale |
|---|---|---|---|---|
| Paid acquisition | $[X] | $[X] | [+/-X%] | [why] |
| Content/SEO | $[X] | $[X] | [delta] | [why] |
| Partnerships | $[X] | $[X] | [delta] | [why] |
| Referral incentives | $[X] | $[X] | [delta] | [why] |
| **Total** | **$[X]** | **$[X]** | **[delta]** | — |

## Final GTM Assessment

**Defensibility:** [how well does this GTM hold up against competitive response?]
**Key advantage:** [strongest GTM element]
**Key vulnerability:** [biggest remaining GTM risk]
**Confidence level:** [high / medium / low] — [one-sentence rationale]
```
