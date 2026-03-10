# Venture Studio Process

The 6-step pipeline from audience to execution. Each step produces outputs, requires user approval to advance (graduation), and feeds into the next step.

## Step Defaults

| Step | Model | Max Turns | Tools | Rationale |
|---|---|---|---|---|
| 1-audience-problems | haiku | 20 | WebSearch, WebFetch, Read, Write | Data gathering — search + structure |
| 2-solution | opus | 25 | WebSearch, WebFetch, Read, Write | Ideation — quality of ideas matters most |
| 2-solution (ranking) | sonnet | 25 | WebSearch, WebFetch, Read, Write | Scoring requires judgment |
| 3-opportunity | haiku | 20 | WebSearch, WebFetch, Read, Write | Research + extraction |
| 3-opportunity (ranking) | sonnet | 20 | WebSearch, WebFetch, Read, Write | Scoring requires judgment |
| 4-business-model | opus | 25 | WebSearch, Read, Write | Strategic thinking — business model + GTM |
| 5-metrics | sonnet | 15 | Read, Write | Structured but requires reasoning |
| 6-execution/builders | sonnet | 80 | Read, Write, Bash, WebFetch | Code generation |
| 6-execution/marketing | haiku | 20 | WebSearch, Read, Write | Copy production from existing strategy |
| 6-execution/analytics | sonnet | 15 | Read, Write | Interpreting data + making real calls |
| synthesis (all steps) | sonnet | 10 | Read, Write | Cross-source reasoning |

## Model Assignment Rules

Step defaults (table above) set the model for the dominant task type in each step. Individual methodology files override the default with `<!-- model: X -->` in the first 3 lines. The rules:

| Task type | Model | Examples |
|---|---|---|
| Web research (search, fetch, catalogue) | haiku | prior-art, competitor-mapping, market-signals, forum-mining |
| Creative/ideation (brainstorm, write, design) | opus | idea-volume, idea-tech, idea-mutation, solution-pitch |
| Judgment/scoring (evaluate, rank, synthesize) | sonnet | solution-ranking, feasibility-check, impact-estimate, problem-scoring |

When a methodology's task type differs from its step default, the file MUST have an explicit `<!-- model: X -->` override. The run skill reads this override and uses it instead of the step default.

## Execution Limits

- **Max concurrent agents:** 20 (agents beyond this limit queue within the same wave)

## Seed Idea Gate

At every graduation, if `seed.md` exists in the project folder, ask the user:

> Your project started with a seed idea: [description from seed.md].
> Should the next step focus on:
> (a) Your seed idea only
> (b) Everything the agents found
> (c) Both — seed idea + agent discoveries

Record the answer in decisions.md as `**Seed focus:** [a/b/c]`. The run skill uses this to filter items in the next step.

## Step Definitions

### Step 1: Audience & Problem Discovery

- **Input:** brief.md
- **Multi-item:** no
- **Synthesis:** yes
- **Output dir:** step-1/
- **Graduation:** User confirms problem list. `/graduate` writes decisions.md with approved problems.
- **Audience segments:** Optional. If `brief.md` contains an `## Audience Segments` section, step 1 runs each methodology once per segment. Outputs go to `step-1/{segment-slug}/`. Synthesis runs cross-segment. Graduation produces a unified problem list with `**Segment:**` tags on each item.

### Step 2: Solution Design & Validation Planning

- **Input:** brief.md, seed.md, step-1/decisions.md, step-1/synthesis.md, step-1/*.md
- **Multi-item:** no
- **Audience segments:** yes — runs per segment using `**Segment:**` tags from step-1/decisions.md. Groups items by segment. Each methodology agent receives ALL problems in its segment. This is the same mechanism as step 1 audience segments.
- **Synthesis:** yes (cross-segment solution comparison)
- **Output dir:** step-2/{segment-slug}/
- **Graduation:** User picks top 3 solutions. `/graduate` writes decisions.md.

### Step 3: Opportunity Validation

- **Input:** brief.md, step-2/decisions.md, step-2/synthesis.md, step-1/synthesis.md
- **Multi-item:** yes (each solution from step-2/decisions.md)
- **Item source:** step-2/decisions.md — each `## Item:` heading is one item, with a `**Market:**` tag
- **Dual-scope:** yes — methodologies have `<!-- scope: per-market -->` or `<!-- scope: per-solution -->` annotations
  - Per-market (trend-scanning, market-signals, market-report-sizing, conference-mapping): run once per unique `**Market:**` tag. Output to `step-3/_markets/{market-slug}/`.
  - Per-solution (competitor-mapping, scout-enrichment, ad-reach-sizing, opportunity-ranking): run once per solution. Output to `step-3/{solution-slug}/`.
  - Opportunity-ranking reads both per-market outputs (from `_markets/{market-slug}/`) and per-solution outputs (from its own folder).
- **Synthesis:** yes (cross-solution market comparison)
- **Output dir:** `step-3/{solution-slug}/` (per-solution) and `step-3/_markets/{market-slug}/` (per-market)
- **Graduation:** User picks 1 solution with validated market. `/graduate` writes decisions.md.

### Step 4: Business Model & GTM

- **Input:** brief.md, step-3/decisions.md, step-3/{item-slug}/*, step-3/_markets/*, step-3/synthesis.md
- **Multi-item:** yes (each solution from step-3/decisions.md)
- **Item source:** step-3/decisions.md — each `## Item:` heading is one item
- **Synthesis:** yes (cross-solution portfolio comparison)
- **Output dir:** step-4/{item-slug}/
- **Graduation:** User approves business model and GTM plan.

### Step 5: Metrics & Hypothesis Database

- **Input:** step-4/decisions.md, step-4/*
- **Multi-item:** no
- **Synthesis:** no
- **Output dir:** step-5/
- **Graduation:** User approves north star metric, KPIs, and hypothesis database.

### Step 6: Execution

- **Input:** all prior decisions + step-5/*
- **Multi-item:** no (but subfolder-based: builders, marketing, analytics run in sequence)
- **Looping:** yes — each `/run` creates a new iteration-N/ folder
- **Output dir:** step-6/iteration-N/{build,marketing,analytics}/
- **Graduation:** User decides: scale / iterate / pivot / stop.
  - **scale:** Exit the pipeline. Project is live.
  - **iterate:** Stay on step 6. Next `/run` creates iteration-N+1/.
  - **pivot:** Jump back to a specified step (user chooses which).
  - **stop:** Archive the project.

## decisions.md Format

Written by `/graduate`. Each selected item is a heading with a slug and a brief rationale:

```markdown
# Decisions — Step N

## Item: item-slug-here
**Name:** Human-readable name
**Rationale:** Why this was selected (1-2 sentences)

## Item: another-item-slug
**Name:** Another item
**Rationale:** Why this was selected
```

For non-multi-item steps, decisions.md contains the approval and any user notes:

```markdown
# Decisions — Step N

**Status:** Approved
**Notes:** [Any user feedback or modifications]
```

## status.md Format

```markdown
# Status — [project-slug]

**Current step:** N
**Step name:** [name from step definitions]
**State:** [running | complete | graduated]
**Last run:** [date]
**Summary:** [one-line summary of latest outputs]
**Next action:** [/run slug | /graduate slug]
```
