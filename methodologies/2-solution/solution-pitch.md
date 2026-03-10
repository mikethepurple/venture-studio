# Solution Pitch

<!-- model: opus -->

## When to use

Always runs in step 2 (wave 5). Writes a Shape Up-style pitch for each of the top 5 solutions — a concise document that frames the problem, scopes the appetite, describes the solution, and calls out risks.

## Inputs needed

- brief.md
- step-1/decisions.md
- solution-ranking.md
- prior-art.md

## Process

1. **Read solution-ranking.md** and identify the top 5 solutions.

2. **Seed-first ordering.** If an `[R-SEED]` concept exists in the top 5 (or was forced as 6th), write it as **Pitch 1** — always first. Then continue with the remaining top solutions in rank order. The user should immediately see their original idea when opening this document.

3. **For each top solution, write a pitch with these sections:**

   - **Problem:** What specific user pain does this solve? Use language from step-1 research. Include one concrete example scenario.
   - **Appetite:** How much time and effort is this worth? (2 weeks / 4 weeks / 8 weeks). What's the maximum scope before it's not worth pursuing?
   - **Solution:** How does it work? Describe the core mechanic in 3-5 sentences. What does the user actually do? What does the product do in response?
   - **Rabbit Holes:** What parts of this are tempting to over-engineer? What scope creep risks exist? Name 2-3 things to explicitly avoid.
   - **No-Goes:** What is this product NOT? What adjacent features should be explicitly excluded from v1? Name 2-3 boundaries.

3. **Keep each pitch to one page.** Brevity is the point. If a section needs more than 3-4 sentences, it's too complex for a pitch.

## Output format

```markdown
# Solution Pitches — [Problem Name]

*Date: [today]*

## Pitch 1: [Solution Name] (ID)

### Problem
[2-3 sentences + concrete scenario]

### Appetite
[2 weeks / 4 weeks / 8 weeks] — [one-line rationale for the timebox]

### Solution
[3-5 sentences: core mechanic, user flow, key interaction]

### Rabbit Holes
- [thing to avoid over-engineering]
- [scope creep risk]
- [complexity trap]

### No-Goes
- [not this]
- [not this either]
- [explicit boundary]

---

## Pitch 2: [Solution Name] (ID)

[same structure]

[Continue for top 5]
```
