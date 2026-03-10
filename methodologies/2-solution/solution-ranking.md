# Solution Ranking

<!-- model: sonnet -->

## When to use

Always runs in step 2 (wave 4). Combines all scoring dimensions into a composite ranking. Identifies top 5 solutions and maps the complexity/impact quadrant. User decides at graduation.

## Inputs needed

- brief.md
- feasibility-check.md
- impact-estimate.md
- differentiation-check.md
- idea-mutation.md

## Process

1. **Collect scores** for every concept from all three scoring agents: feasibility (/5), impact (/5), differentiation (/5).

2. **Collect concept labels** from idea-mutation.md:
   - `[R-SEED]` = refined seed idea (the main thread)
   - `[R]` = refined version of a generated idea
   - `[V-SEED]` = variant/permutation of the seed idea
   - `[V]` = variant of a generated idea
   - No label = original from dedup (unrefined)

3. **Calculate composite score** for each concept: Feasibility + Impact + Differentiation = /15.

4. **Build the ranking table.** Sort by composite score descending. Include the label column.

5. **Map the complexity/impact quadrant.** Classify each concept into one of four quadrants:
   - **Quick Win** — high feasibility (4-5) + high impact (4-5). Build these first.
   - **Big Bet** — low feasibility (1-3) + high impact (4-5). Worth it if you have time.
   - **Easy Win** — high feasibility (4-5) + low impact (1-3). Low-risk filler.
   - **Avoid** — low feasibility (1-3) + low impact (1-3). Skip.

6. **Identify top 5.** Prioritize Quick Wins, then Big Bets with strong differentiation. Flag any concept that's top-5 on composite but sits in the Avoid quadrant — it's differentiated but impractical.

7. **Seed main thread handling.** If an `[R-SEED]` concept exists:
   - It is always included in the top 5, regardless of score
   - If it wouldn't make top 5 by score, add it as a 6th entry clearly marked
   - **Seed-first presentation:** In the Top 5 Solutions section, `[R-SEED]` is always listed as **#1** — regardless of its rank position in the Full Ranking table. The Full Ranking table stays sorted by score; the Top 5 section reorders to put the seed first.
   - `[V-SEED]` variants are ranked normally

8. **Cluster related concepts.** If two top concepts could be combined into one product, note the potential merge. Pay special attention to seed variants that might strengthen the main thread.

## Output format

```markdown
# Solution Ranking — [Segment Name]

*Date: [today]*

## Full Ranking

| Rank | ID | Concept | Label | Feasibility | Impact | Differentiation | Composite /15 | Quadrant |
|---|---|---|---|---|---|---|---|---|
| 1 | [ID] | [name] | [R-SEED] | [X]/5 | [X]/5 | [X]/5 | [X]/15 | Quick Win |
| 2 | [ID] | [name] | [R] | [X]/5 | [X]/5 | [X]/5 | [X]/15 | Big Bet |
| 3 | [ID] | [name] | [V-SEED] | [X]/5 | [X]/5 | [X]/5 | [X]/15 | Quick Win |

[Continue for all concepts]

## Top 5 Solutions

### 1. [Name] (ID) — [X]/15 — [Quadrant] [SEED MAIN THREAD]
[2-3 sentences: what it is, why it ranks high, key risk]

### 2. [Name] (ID) — [X]/15 — [Quadrant]
[summary]

[Continue for top 5]

## Complexity/Impact Quadrant

### Quick Wins (build first)
- [concept] — [one-line rationale]

### Big Bets (worth the investment)
- [concept] — [one-line rationale]

### Easy Wins (low-risk filler)
- [concept] — [one-line rationale]

### Avoid
- [concept] — [one-line rationale]

## Potential Merges

- [Concept A] + [Concept B] → [what the combined product might be]

## Seed Variants Summary

[Only if seed concepts exist. List all [V-SEED] variants and how they compare to the main thread [R-SEED]. Note which variants introduce ideas worth folding back into the main concept.]
```
