# Idea Tech

## When to use

Always runs in step 2 (wave 1). Generates solution concepts by forcing exploration along different technology axes. Complements idea-volume by ensuring tech-diverse ideas aren't missed.

## Inputs needed

- brief.md
- step-1/decisions.md
- seed.md

## Process

1. **Check for seed mode.** Read step-1/decisions.md and look for `**Seed focus:**`.

   - **Seed focus: a** (seed only) — Read seed.md. Explore the seed idea through each tech axis: "What would this seed idea look like built on [axis]?" Generate one variant per axis, all rooted in the seed concept. Label each with `[SEED-TECH]`. These are tech explorations of the same idea, not new ideas.
   - **Seed focus: c** (seed + generate) — Read seed.md. Note which tech axis the seed naturally fits. Generate that axis first (labeled `[SEED]`), then generate fresh concepts for all other axes as normal.
   - **Seed focus: b** (generate only) — Ignore seed.md. Generate one concept per axis as normal.
   - **No `Seed focus` field found** — If seed.md exists, treat as mode "c". If no seed.md exists, treat as mode "b".

2. **Review the problem and opportunity context.** Understand the problem deeply before generating.

3. **Generate one solution concept per technology axis.** For each axis, ask: "What would a solution look like if it was built primarily on this technology?"

   Required axes (generate at least one concept for each):
   - **AI/ML-native** — the core value comes from a model (generation, classification, prediction, recommendation)
   - **Marketplace/platform** — connect supply and demand, take a cut
   - **API/infrastructure** — sell capability to developers or other products
   - **Browser extension / plugin** — augment existing tools the audience already uses
   - **Mobile-first** — the value depends on being in someone's pocket (location, camera, notifications)
   - **Hardware / IoT** — a physical device or sensor solves the problem
   - **No-code / template** — a pre-built system the user customizes (Notion, Airtable, Webflow)
   - **Community / content** — the product IS the community or knowledge base

4. **Add 2-3 hybrid concepts** that combine two axes. In mode "a", these should be hybrid explorations of the seed idea.

5. **Write each concept.** 2-3 sentences: what it is, the core tech, how the user interacts with it.

## Output format

```markdown
# Idea Tech — [Segment Name]

*Date: [today]*
*Seed mode: [a/b/c]*

## Technology-Axis Concepts

### AI/ML-Native
**[Name]** [SEED-TECH] — [2-3 sentence description]

### Marketplace/Platform
**[Name]** — [description]

### API/Infrastructure
**[Name]** — [description]

### Browser Extension/Plugin
**[Name]** — [description]

### Mobile-First
**[Name]** — [description]

### Hardware/IoT
**[Name]** — [description]

### No-Code/Template
**[Name]** — [description]

### Community/Content
**[Name]** — [description]

## Hybrid Concepts

1. **[Name]** ([Axis A] + [Axis B]) — [description]
2. **[Name]** ([Axis A] + [Axis B]) — [description]
3. **[Name]** ([Axis A] + [Axis B]) — [description]
```
