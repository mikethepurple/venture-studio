# Validation Plan

<!-- model: sonnet -->

## When to use

Always runs in step 2 (wave 5). Designs a validation experiment for each of the top 5 solutions — identifies the riskiest assumption and proposes a fast, cheap test.

## Inputs needed

- brief.md
- step-1/decisions.md
- solution-ranking.md

## Process

1. **Read solution-ranking.md** and identify the top 5 solutions.

2. **For each top solution, identify the riskiest assumption.** The one thing that, if wrong, makes the entire solution worthless. Common risky assumptions:
   - "Users will pay for this" (WTP)
   - "Users will switch from [current tool]" (switching cost)
   - "This can be built with current AI" (technical feasibility)
   - "The audience is large enough" (market size)
   - "Users will trust an AI to do this" (trust barrier)

3. **Design a validation experiment** for that assumption:
   - **What to test:** The specific assumption, stated as a falsifiable hypothesis
   - **Experiment:** The fastest, cheapest way to test it (landing page, fake door, survey, prototype, concierge, Wizard of Oz)
   - **Success threshold:** The specific number that would validate the assumption (e.g., "5% conversion on landing page," "8/10 survey respondents say yes")
   - **Failure threshold:** The number that would invalidate it
   - **Time:** How long the experiment should run
   - **Cost:** Estimated cost (ads, tools, time)

4. **One experiment per solution.** Don't design multi-step validation sequences — just the single most important test.

## Output format

```markdown
# Validation Plan — [Problem Name]

*Date: [today]*

## Solution 1: [Name] (ID)

**Riskiest assumption:** [falsifiable hypothesis]

**Experiment:** [description of what to build/run]

**Success threshold:** [specific number]
**Failure threshold:** [specific number]

**Time:** [days/weeks]
**Cost:** $[estimate]

**Why this test:** [1-2 sentences — why this assumption matters most and why this experiment is the fastest way to test it]

---

## Solution 2: [Name] (ID)

[same structure]

[Continue for top 5]

## Experiment Priority

| Priority | Solution | Experiment Type | Time | Cost |
|---|---|---|---|---|
| 1 | [name] | [type] | [time] | $[cost] |
| 2 | [name] | [type] | [time] | $[cost] |
```
