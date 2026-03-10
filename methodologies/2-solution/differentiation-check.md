# Differentiation Check

<!-- model: haiku -->

## When to use

Always runs in step 2 (wave 3). Scores each solution concept on differentiation versus prior art. Does not assess feasibility or impact — only how different it is from what already exists.

## Inputs needed

- brief.md
- prior-art.md
- idea-dedup.md
- idea-mutation.md

## Process

1. **Collect all concepts** from idea-dedup.md and idea-mutation.md.

2. **Assess market context from prior-art.md** (do this ONCE before scoring individual concepts):
   - **Market saturation:** Is there more demand than quality supply, or is the market oversaturated? A fragmented market with many weak players is underserved, not crowded.
   - **Competitor quality and funding:** Are competitors well-funded with strong products, or small/underfunded with low-quality offerings? Low-quality competition means the execution bar is low — "similar" to a weak competitor is an opportunity, not a threat.
   - **Market structure:** Is this winner-take-all (where similarity = death) or expanding-pie (where more entrants normalize the category and grow total demand)?
   - **Geographic coverage:** Do competitors serve global markets or only specific regions? If the user's target geography is underserved, existing competitors in other regions are less relevant.

   Write a 2-3 sentence **Market Context** summary that informs all subsequent scoring.

3. **For each concept, compare against prior-art.md:**
   - **Closest existing product:** Which existing product/workaround is most similar?
   - **Type of differentiation:**
     - Structural — fundamentally different approach (new tech, new business model, new delivery)
     - Incremental — same approach done better/cheaper/faster
     - None — essentially the same as something that exists
   - **Defensibility:** Could the closest competitor realistically copy this AND compete effectively? Consider their funding, team size, product quality, and geographic reach — not just whether they theoretically could build it.

4. **Score each concept /5 on differentiation:**
   - 5 = structural differentiation, nothing like this exists, hard to copy
   - 4 = structural differentiation on at least one axis (tech, model, or delivery)
   - 3 = meaningful incremental improvement over existing solutions, OR similar approach in a market where competition is weak/fragmented and more entrants grow demand
   - 2 = minor incremental improvement in a saturated, well-funded competitive market
   - 1 = clone of a well-executed, well-funded existing product in a zero-sum market

   **Critical:** "A competitor exists" is not the same as "a competitor threatens you." Score 2 means a strong competitor can easily replicate AND the market is zero-sum. If the market is fragmented, competitors are underfunded, or more entrants would grow the pie, adjust upward. A concept that looks like an existing product but executes better in an underserved market is a 3, not a 2.

5. **Don't assess feasibility or impact.** A concept that's impossible to build can still score 5/5 on differentiation.

## Output format

```markdown
# Differentiation Check — [Problem Name]

*Date: [today]*

## Differentiation Scores

## Market Context

[2-3 sentences: market saturation, competitor quality/funding, market structure (zero-sum vs expanding-pie), geographic coverage gaps]

## Differentiation Scores

| ID | Concept | Diff /5 | Closest Existing | Differentiation Type | Defensible? |
|---|---|---|---|---|---|
| S-01 | [name] | [X]/5 | [product name] | [structural/incremental/none] | [yes/no — why] |
| S-02 | [name] | [X]/5 | [product] | [type] | [assessment] |

[Continue for all concepts]

## Most Differentiated

[Top 5 concepts by differentiation score — the most novel ideas in the pool]

## Clone Risk

[List any concepts scoring 1-2 that are essentially copies of existing products]
```
