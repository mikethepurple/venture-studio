---
name: start
description: Initialize a new venture studio project. Creates the project folder, brief.md, and status.md. Sets the project to Step 1.
argument-hint: "[audience description, e.g. 'English teachers in France' or 'solo founders building SaaS']"
user-invocable: true
allowed-tools: Read, Write, Glob, AskUserQuestion
---

# Start — Initialize a New Project

**Base directory: `/Users/mikethepurple/Claude/venture-studio`**
**IMPORTANT:** All relative paths in this skill (e.g. `projects/`, `templates/`) are relative to the base directory above. Always resolve them to absolute paths before reading/writing. For example, `projects/[slug]/brief.md` means `/Users/mikethepurple/Claude/venture-studio/projects/[slug]/brief.md`.

You are creating a new venture studio project for audience: **$ARGUMENTS**

## Steps

1. Generate a project slug from the audience description (lowercase, hyphens, 2-4 words — e.g., "english-teachers-france")

2. Create the project directory: `projects/[slug]/`

3. **Detect and confirm the seed idea.**

   Read `$ARGUMENTS` carefully. Determine whether the user's description contains:
   - A **solution idea** (they describe a product, tool, or service concept), or
   - A **problem** (they describe a pain point or struggle), or
   - **Neither** (they describe only an audience with no specific idea or problem)

   **If a solution or problem is detected**, present a scope confirmation (do NOT ask the user to re-describe what they already wrote). Use AskUserQuestion with a single question showing your interpretation:

   Format the question text like this:
   ```
   Here's how I read your idea:

   **Type:** Solution idea | Problem to solve
   **Your idea:** [rephrased 1-2 sentence version of their concept]
   **In scope:** [what this project covers — be specific about the product/problem boundaries]
   **Not in scope:** [adjacent things that could be confused with this but should be excluded]
   **Implied problem:** [if solution: what pain does this solve? if problem: restate the problem]

   Does this scope look right?
   ```

   Options: "Looks good" (description: "Proceed with this scope") / "Needs adjustment" (description: "I'll refine the scope")

   If the user picks **"Needs adjustment"**: they will provide corrections via freeform text. Update your interpretation accordingly and proceed.

   If the user picks **"Looks good"**: lock in the seed idea and continue.

   Record the confirmed seed type (solution | problem), description, in-scope, not-in-scope, and implied problem.

   **If no idea or problem is detected** (pure audience description), ask:

   **Q0 — "Are you starting from a specific idea, or exploring openly?"**
   - Options: "Open exploration" (description: "No specific idea, discover what's out there") / "I have a solution idea" (description: "I have a product/service concept to validate") / "I have a problem to solve" (description: "I know the pain point, need to find the best approach")

   If "solution" or "problem": ask a follow-up text question: *"Describe your idea in 1-2 sentences."* Then run the scope confirmation above.

   If "Open exploration": no seed idea. Skip to Q1.

4. Ask the user these questions using AskUserQuestion (one call, all four questions):

   **Q1 — "What do you already know about this audience or space?"**
   - Options: "Nothing — starting fresh" / "Some informal observations" / "I have specific research or contacts"
   - If they pick option 2 or 3, their freeform text goes into Existing Knowledge.

   **Q2 — "Geographic scope?"**
   - Options: "Single city/region" / "Single country" / "Multi-country" / "Global"
   - User adds specifics (e.g., "Hong Kong only") via freeform.

   **Q3 — "Validation budget for this project?"**
   - Options: "< $500 (scrappy)" / "$500–$2K" / "$2K–$10K" / "$10K+"

   **Q4 — "Business models to rule out or prefer?"**
   - Options: "No preference" / "SaaS preferred" / "Marketplace preferred" / "No physical inventory"
   - User can type additional constraints.

   **Q5 — "Does this project have distinct audience segments to track separately?"**
   - Options: "Single audience" / "Two segments" / "Three or more segments"

   If "Two segments" or "Three or more segments": ask a follow-up question:
   "Name your segments (one per line). Example: 'operators / shoppers'."
   (Use AskUserQuestion with dummy options — user types freeform via "Other".)

   Store the segment names. If segments are defined, you will write an `## Audience Segments` section to brief.md (see step 5).

5. Write `projects/[slug]/brief.md` using the answers:

```markdown
# Project Brief

**Audience:** $ARGUMENTS
**Created:** [today's date]
**Geo:** [geographic scope from Q2]
**Validation budget:** [budget from Q3]

## Audience
[Expand the audience description into 2-3 sentences. Who are these people? What context are they in? What makes them a coherent group?]

## Existing Knowledge
[What the user already knows from Q1 — or "Starting fresh — no prior research."]

## Constraints
- Business model filters: [from Q4 — exclusions/preferences]
- Geographic: [restate geo constraint if relevant]
- [Any other constraints mentioned in freeform answers]
```

**If the user defined audience segments (Q5 was "Two segments" or "Three or more segments")**, append this section to brief.md:
```markdown
## Audience Segments
- **[segment-slug]:** [derived description — who are these people, their role in the context of this project]
- **[segment-slug]:** [derived description]
```
Slugs must be lowercase, hyphenated (e.g., "operators", "shoppers", "shop-owners"). Descriptions should be 1-2 sentences expanding on the user's segment name in the context of the audience.

If Q5 was "Single audience", do NOT add an `## Audience Segments` section.

**If the user provided a seed idea (solution or problem detected and confirmed)**, write a separate file `projects/[slug]/seed.md`:

```markdown
# Seed Idea
**Type:** solution | problem
**Description:** [confirmed rephrased description]
**In scope:** [what this project covers]
**Not in scope:** [what's excluded]
**Implied problem:** [if type=solution: what pain does this solution address; if type=problem: same as Description]
```

Do NOT put seed idea information in brief.md. Methodology agents read brief.md — keeping the seed separate prevents contamination of unbiased discovery. Only the synthesis agent reads seed.md.

If no seed idea was detected or the user chose "Open exploration", do NOT create seed.md.

6. Write `projects/[slug]/status.md`:

```markdown
# Status — [slug]

**Current step:** 1
**Step name:** Audience & Problem Discovery
**State:** pending
**Last run:** never
**Summary:** Project initialized. Ready for first /run.
**Next action:** /run [slug]
```

7. Create empty step directories: `projects/[slug]/step-1/` through `projects/[slug]/step-6/`

## Output

Tell the user:
1. Project created: `projects/[slug]/`
2. Audience captured in `brief.md`
3. Next command: `/run [slug]`
