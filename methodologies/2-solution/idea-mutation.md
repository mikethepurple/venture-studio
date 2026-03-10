# Idea Mutation

## When to use

Always runs in step 2 (wave 2). Two jobs: (1) refine every concept into its best version, and (2) generate divergent mutations. Both jobs run on all concepts — seed ideas, generated ideas, everything.

## Inputs needed

- brief.md
- idea-volume.md
- idea-tech.md

## Process

### Part 1: Refinement Pass

1. **Collect all concepts** from idea-volume.md and idea-tech.md.

2. **For each concept, produce a refined version** — the best expression of that core idea:
   - Add specificity: business model, pricing, delivery mechanism, target user
   - Fix obvious gaps (missing revenue model, unclear user, no delivery mechanism)
   - Sharpen the description (make it concrete and specific)
   - **NEVER change what the concept fundamentally IS.** Refinement adds detail — it does not reframe, reposition, or change the core value proposition. If the concept says "diagnose health conditions," the refined version still diagnoses health conditions. It does not become "wellness mapping." If the concept says "diagnostic aid for practitioners," it stays a diagnostic aid. Adding a business model or UX details is refinement. Changing the product's purpose is not.

3. **Label each refined concept `[R]`.** The refined version becomes the canonical version of that idea going forward.

4. **`[SEED]` concepts get refined too** — but the refinement MUST preserve the seed's exact value proposition. Add business model, pricing, delivery, UX — but the core idea from seed.md stays intact. Label the refined seed `[R-SEED]`. This is the "main thread."

### Part 2: Divergent Mutations

5. **Pick 8 strongest concepts** from wave-1 outputs — the ones that feel most promising based on gut reaction (novelty, clarity, obvious demand). Don't overthink the selection.

6. **Pick 5 weakest concepts** — the ones that feel least promising, weirdest, or most impractical.

7. **For each of the 8 strong concepts, generate 1 variant** using one of these mutations:
   - **Invert:** What if we did the exact opposite? (B2B → B2C, SaaS → one-time, automated → manual)
   - **Combine:** Merge two strong concepts into one hybrid
   - **Narrow:** What if this only served one hyper-specific niche?
   - **Broaden:** What if this served a much wider audience than intended?

8. **For each of the 5 weak concepts, generate 1 variant** using:
   - **Rescue:** What's the kernel of a good idea buried in here? Extract it and rebuild
   - **Invert:** The opposite of a bad idea might be a good one
   - **Reframe:** Same mechanism, different customer or problem

9. **Label all divergent mutations `[V]`.** These are variants, not canonical versions.

10. **In seed-only mode** (only seed concepts exist): apply divergent mutations to the seed and its tech-axis explorations. All mutations are labeled `[V-SEED]` — clearly identifiable as permutations of the original idea, not independent concepts.

## Output format

```markdown
# Idea Mutation — [Segment Name]

*Date: [today]*

## Refined Concepts

| # | Original | Refined Version | Label |
|---|---|---|---|
| R-01 | idea-volume #1 "[name]" | **[Refined Name]** — [2-3 sentence sharpened description] | [R-SEED] |
| R-02 | idea-volume #2 "[name]" | **[Refined Name]** — [description] | [R] |
| R-03 | idea-tech AI "[name]" | **[Refined Name]** — [description] | [R] |

[One refined version per wave-1 concept]

## Divergent Mutations — Strong Concepts

| # | Original | Mutation Type | New Concept | Label |
|---|---|---|---|---|
| V-01 | idea-volume #2 "[name]" | Invert | **[New Name]** — [2-3 sentence description] | [V] |
| V-02 | idea-tech AI + idea-volume #5 | Combine | **[New Name]** — [description] | [V-SEED] |

[8 mutations from strong concepts]

## Divergent Mutations — Weak Concepts

| # | Original | Mutation Type | New Concept | Label |
|---|---|---|---|---|
| V-09 | idea-volume #14 "[name]" | Rescue | **[New Name]** — [description] | [V] |

[5 mutations from weak concepts]

## Summary

- Refined concepts: [X] (of which [X] are seed-derived)
- Strong mutations: 8
- Weak mutations: 5
- Total output concepts: [X]
```
