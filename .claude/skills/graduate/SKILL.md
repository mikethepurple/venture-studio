---
name: graduate
description: Review step outputs with the user, record decisions, and advance the project to the next step. Handles item selection for multi-item steps and all graduation gates.
argument-hint: "[project-slug]"
user-invocable: true
allowed-tools: Read, Write, Glob, Grep
---

# Graduate — Review & Advance

**Base directory: `/Users/mikethepurple/Claude/venture-studio`**
**IMPORTANT:** All relative paths in this skill (e.g. `projects/`, `process.md`) are relative to the base directory above. Always resolve them to absolute paths before reading/writing. For example, `projects/$ARGUMENTS/status.md` means `/Users/mikethepurple/Claude/venture-studio/projects/$ARGUMENTS/status.md`.

You are running graduation for project: **$ARGUMENTS**

## 1. Read State

- Read `projects/$ARGUMENTS/status.md` — confirm state is "complete" for the current step
- Read `process.md` — get the graduation criteria for this step
- Note the current step number N

If state is not "complete", tell the user: "Step N hasn't finished running. Run `/run $ARGUMENTS` first."

## 2. Present Outputs

Read all output files from `projects/$ARGUMENTS/step-N/`:
- If a `synthesis.md` exists, present that first (it's the summary)
- Then list all other output files with a brief description of each

For multi-item steps, organize by item:
```
## Problem: [item-name]
- trend-scanning.md — [key finding]
- market-signals.md — [key finding]
...
```

**Step 1 with audience segments** — when step-1 outputs are in segment subfolders, organize by segment:
```
## Segment: Operators
- problem-matrix.md — top 5 problems ranked
...

## Segment: Shoppers
- problem-matrix.md — top 5 problems ranked
...

## Cross-segment synthesis
- synthesis.md — key findings
```

Present a clear, scannable summary. Don't dump full file contents — extract the key findings and rankings from each file.

## 3. Graduation Gate

Apply the graduation criteria from process.md for the current step:

### Step 1 → Step 2
Ask the user to review the discovered problems. Present them as a numbered list.
"Which problems should we take forward to solution design? (List numbers, or say 'all')"

### Step 1 → Step 2 (with audience segments)
When step-1 outputs are in segment subfolders, present problems per segment. Ask:
"Which problems should we take forward? You can select from either or both segments. (List by segment and number, or 'all')"

Record each selected problem in decisions.md with a segment tag:
```markdown
## Item: authentication-at-scale
**Name:** Authentication at scale
**Segment:** operators
**Rationale:** Selected by user
```

### Seed Idea Gate (all graduations)

Check if `projects/$ARGUMENTS/seed.md` exists. If it does, add this question after the main graduation question:

"Your project started with a seed idea: [description from seed.md]. Should the next step focus on: (a) Your seed idea only, (b) Everything the agents found, (c) Both — seed idea + agent discoveries?"

Record the answer in decisions.md as `**Seed focus:** [a/b/c]`.

### Step 2 → Step 3
Present solutions per segment (from step-2/{segment-slug}/ outputs). Show solution-ranking scores and solution-pitch summaries. Ask:
"Pick your top 3 solutions to validate in the market. (List numbers)"

### Step 2 → Step 3 (with segment outputs)
When step-2 outputs are in segment subfolders, organize by segment:
```
## Segment: Self-Diagnosers
- solution-ranking.md — top 5 solutions ranked
- solution-pitch.md — pitches for top solutions
...

## Segment: Practitioners
- solution-ranking.md — top 5 solutions ranked
...

## Cross-segment synthesis
- synthesis.md — key findings
```

### Step 2 → Step 3: Market Assignment

After the user picks their top 3 solutions, assign each to a market for step 3's per-market research. Ask:

"Now let's group these by market. Solutions in the same market will share trend scanning, market signals, market sizing, and conference mapping research. Suggest market labels based on the solutions' domains, then ask the user to confirm or adjust."

For example, if the user picks IrisScan Home, IrisPro Clinical Suite, and IrisAnalytics API:
- Suggest: "consumer-iris-wellness" for IrisScan Home, "practitioner-clinical-saas" for IrisPro + IrisAnalytics API
- Let user adjust (they might say "those two are different markets" or "all three are one market")

Record the market tag on each item in decisions.md:
```markdown
## Item: irisscan-home
**Name:** IrisScan Home
**Market:** consumer-iris-wellness
**Rationale:** Selected by user
```

The `**Market:**` tag is used by the run skill to group per-market research in step 3. Solutions sharing the same `**Market:**` value will share one set of trend-scanning, market-signals, market-report-sizing, and conference-mapping outputs (written to `step-3/_markets/{market-slug}/`). Per-solution research (competitor-mapping, scout-enrichment, ad-reach-sizing, opportunity-ranking) still runs once per solution in `step-3/{solution-slug}/`.

### Step 3 → Step 4
Present opportunity validation per solution with market data and rankings. Ask:
"Pick 1 solution with a validated market to build a business model around. (Number)"

### Step 4 → Step 5
Present the business model and GTM plan. Ask:
"Approve this business model and GTM plan? (yes / yes with changes / no, redo)"

### Step 5 → Step 6
Present metrics and hypothesis database. Ask:
"Approve these metrics and hypotheses? (yes / yes with changes / no, redo)"

### Step 6 (graduation = user decision)
Present iteration results. Ask:
"What next? (scale / iterate / pivot to step [N] / stop)"

## 4. Record Decisions

Based on user response, write `projects/$ARGUMENTS/step-N/decisions.md`:

**For multi-item/segment selection steps (1, 2, 3):**

```markdown
# Decisions — Step N

Graduated: [date]

## Item: [slug-from-name]
**Name:** [human-readable name from the outputs]
**Rationale:** [user's reason if provided, or "Selected by user"]

## Item: [another-slug]
**Name:** [name]
**Rationale:** [rationale]
```

Slugs must be lowercase, hyphenated, derived from the item name. These slugs become subfolder names in the next step.

**For approval steps (4, 5):**

```markdown
# Decisions — Step N

Graduated: [date]
**Status:** Approved
**Notes:** [any modifications the user requested]
```

**For Step 6:**

```markdown
# Decisions — Step N

Graduated: [date]
**Decision:** [scale / iterate / pivot / stop]
**Notes:** [user's reasoning]
**Pivot target:** [step number, if pivot]
```

## 5. Update Status

**If advancing to next step (or iterating on step 6):**

```markdown
# Status — $ARGUMENTS

**Current step:** [N+1, or N if iterating]
**Step name:** [from process.md]
**State:** pending
**Last run:** [date of graduation]
**Summary:** Graduated from step N. [one-line summary of decisions made]
**Next action:** /run $ARGUMENTS
```

**If pivot:**
Set current step to the pivot target step. State: pending.

**If stop:**
```markdown
**Current step:** 6
**State:** stopped
**Summary:** Project stopped after iteration [N]. [reason]
**Next action:** none (archived)
```

**If scale:**
```markdown
**Current step:** 6
**State:** scaling
**Summary:** Project graduated to scaling. [key metric]
**Next action:** none (operating independently)
```

## 6. Report to User

Tell the user:
1. Decisions recorded in `step-N/decisions.md`
2. Project advanced to step [N+1] (or current state)
3. Next command: `/run $ARGUMENTS` (or nothing if stopped/scaling)
