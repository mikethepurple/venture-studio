# WTP Signals

## When to use

Always runs in step 1 (wave 4). Scores each problem on willingness to pay — whether people already spend money trying to solve this problem. Uses web research signals, not judgment.

## Inputs needed

- brief.md
- problem-dedup.md

## Process

1. **Read problem-dedup.md** and list all problems (P-01, P-02, etc.).

2. **For each problem, research these WTP signals:**
   - **Existing paid tools:** Search for SaaS, apps, or services that charge to solve this problem. Record names and pricing.
   - **Freelancer/agency market:** Search Upwork, Fiverr, and Google for freelancers hired to solve this problem manually. People hiring humans = high WTP.
   - **Premium workarounds:** Search for paid templates, courses, plugins, or guides. Check Gumroad, Udemy, AppSumo.
   - **Price complaints:** Search for complaints about the cost of existing solutions ("too expensive," "not worth the price"). People complaining about price = they're paying but reluctantly.

3. **Score each problem /5 on WTP.** Evidence quality gates apply:
   - 5 = already paying for workarounds — requires specific $ amounts from 2+ independent sources
   - 4 = strong spending signals from multiple source types (tools + freelancers + templates)
   - 3 = **cap for single-source spending evidence**, even if the amount is large
   - 2 = free workarounds exist, limited paid signals
   - 1 = no spending signal

4. **Record specific dollar amounts** wherever found. "$49/mo for [tool]" is better evidence than "people pay for solutions."

5. **Don't score prevalence, severity, or frequency.** Those are separate agents. Only score WTP.

## Output format

```markdown
# WTP Signals — [Audience]

*Date: [today]*

## WTP Scores

### P-01: [Problem name]
**WTP:** [X]/5
**Paid tools:** [tool names + pricing]
**Freelancer market:** [data or "none found"]
**Premium workarounds:** [data or "none found"]
**Price complaints:** [data or "none found"]
**Source quality:** [list any `[dated source]` or `[weak source]` tags]

### P-02: [Problem name]
**WTP:** [X]/5
[same structure]

[Continue for all problems]

## Summary

| Problem | WTP /5 | Highest Price Found | Source Count | Source Quality |
|---|---|---|---|---|
| P-01 | [X] | $[X]/mo | [X sources] | [clean / dated / weak] |
| P-02 | [X] | $[X] | [X sources] | [quality] |
```
