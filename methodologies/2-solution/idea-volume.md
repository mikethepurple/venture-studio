# Idea Volume

## When to use

Always runs in step 2 (wave 1). Generates solution concepts through rapid divergent brainstorming. Quantity over quality — no filtering allowed.

## Inputs needed

- brief.md
- step-1/decisions.md
- seed.md

## Process

1. **Check for seed mode.** Read step-1/decisions.md and look for `**Seed focus:**`.

   - **Seed focus: a** (seed only) — Read seed.md. Output the seed idea as the single concept, using the description from seed.md. Add specificity (business model, delivery method, target user, price point) but NEVER change the core value proposition. If the seed says "diagnose health conditions," the output says "diagnose health conditions" — not "wellness mapping," not "health insights," not any softened reframe. Label it `[SEED]`. Do NOT generate any other ideas.
   - **Seed focus: c** (seed + generate) — Read seed.md. List the seed idea as concept #1 (labeled `[SEED]`), adding specificity without changing what it does. Then brainstorm 14-19 additional concepts as normal.
   - **Seed focus: b** (generate only) — Ignore seed.md. Brainstorm 15-20 concepts as normal.
   - **No `Seed focus` field found** — If seed.md exists, treat as mode "c". If no seed.md exists, treat as mode "b".

2. **Read the problem and opportunity context.** Understand who has the problem, how big the market is, and what trends are at play. Don't start generating until you fully understand the space.

3. **Generate solution concepts.** (Skip this in mode "a" — you already have the seed.) Each should be 1-2 sentences describing what it is and how it works. Deliberately diverge across:
   - Business models (SaaS, marketplace, agency, productized service, one-time purchase, freemium, API)
   - Delivery (web app, mobile, browser extension, Slack bot, email, physical product, service)
   - Customer segments (power users vs beginners, B2B vs B2C, enterprise vs SMB)
   - Price points (free, $10/mo, $100/mo, $1000+)

4. **Force variety.** If concepts start clustering around one approach, explicitly pivot to a different axis. At least 3 concepts should feel uncomfortable or "bad" — that's how you know you're diverging enough.

5. **Write each concept.** Number them. One-two sentences each. No evaluation, no scoring, no "this is good because." Just ideas.

## Output format

```markdown
# Idea Volume — [Segment Name]

*Date: [today]*
*Seed mode: [a/b/c]*

## Solution Concepts

1. **[Name]** [SEED] — [1-2 sentence description of what it is and how it works]
2. **[Name]** — [description]
3. **[Name]** — [description]

[Continue — 1 concept in mode a, 15-20 in mode b/c]

## Divergence Check

- Business models covered: [list]
- Delivery methods covered: [list]
- Customer segments covered: [list]
- Price points covered: [list]
```
