---
name: run
description: Run all methodologies for the current step of a project. Discovers methodology files, spawns isolated Task agents for each, collects outputs, and runs synthesis if configured.
argument-hint: "[project-slug]"
user-invocable: true
allowed-tools: Read, Write, Glob, Grep, Bash, Agent
---

# Run — Execute Current Step

**Base directory: `/Users/mikethepurple/Claude/venture-studio`**
**IMPORTANT:** All relative paths in this skill (e.g. `projects/`, `methodologies/`, `process.md`) are relative to the base directory above. Always resolve them to absolute paths before reading/writing. For example, `projects/$ARGUMENTS/status.md` means `/Users/mikethepurple/Claude/venture-studio/projects/$ARGUMENTS/status.md`.

You are running the current step's methodologies for project: **$ARGUMENTS**

## 1. Read Project State

Read these files (stop and tell the user if any are missing):
- `projects/$ARGUMENTS/status.md` — get the current step number N
- `projects/$ARGUMENTS/brief.md` — the audience definition
- `process.md` — find the definition for step N (inputs, multi-item, synthesis, model defaults)

If status.md shows state "complete" (not yet graduated), tell the user: "Step N is complete. Run `/graduate $ARGUMENTS` to review outputs and advance."

## 2. Resolve Input Paths

From the step definition in process.md, build a list of input file paths available for this step. Do NOT read their contents — just note the paths.

For example, step 2 inputs are: `brief.md`, `step-1/decisions.md`, `step-1/*.md`. Resolve the glob to actual paths. Store these as `AVAILABLE_INPUTS` (a list of absolute paths).

## 2b. Detect Audience Segments (Steps 1 and 2)

**Step 1:** After reading brief.md, check whether it contains an `## Audience Segments` section.

**If step is 1 AND `## Audience Segments` exists:**
- Parse each bullet under that heading as a segment: `- **{slug}:** {description}`
- Store as SEGMENTS list (e.g., ["operators", "shoppers"])
- All subsequent methodology runs will execute once per segment (same as multi-item)
- Output paths: `step-1/{segment-slug}/{methodology-filename}.md`
- Wave dependencies still apply within each segment track
- Both segment tracks run in parallel within each wave

**Step 2:** Check if process.md says `Audience segments: yes` for this step.

**If step is 2 AND audience segments is yes:**
- Read step-1/decisions.md
- Parse each `## Item:` heading and its `**Segment:**` tag
- Build SEGMENT_GROUPS: `{ segment-slug: [list of item objects with name + rationale] }`
- Items without a `**Segment:**` tag go into `_default` segment
- All methodology runs execute once per segment (NOT per item)
- Each agent receives ALL items in its segment as context
- Output paths: `step-2/{segment-slug}/{methodology-filename}.md`
- Wave dependencies still apply within each segment track
- Both segment tracks run in parallel within each wave

**If step is not 1 or 2, OR no segments configured:**
- Continue as normal (skip this logic entirely)

## 3. Handle Multi-Item Steps

Check if the step definition says `multi-item: yes`.

> Note: For step 1 with audience segments, segment handling (section 2b) replaces multi-item logic. The behavior is identical — methodology × item matrix — but the "items" are audience segments parsed from brief.md instead of decisions.md.

**If multi-item:**
- Read the decisions.md from the previous step (specified in "Item source" in process.md)
- Parse each `## Item: {slug}` heading — each is a separate item
- Agents will run once per item (methodology x item matrix)

**Step 3 dual-scope override:** Step 3 is multi-item but uses dual-scope execution instead of the simple methodology × item matrix. When step is 3:
- Read step-2/decisions.md
- Parse each `## Item: {slug}` heading as a SOLUTION, including its `**Market:**` tag
- Build SOLUTION_LIST: `[{ slug, name, market, rationale }]`
- Build MARKET_GROUPS: `{ market-slug: [list of solution objects in this market] }`
- Methodologies with `<!-- scope: per-market -->` run once per unique market (not per solution)
- Methodologies with `<!-- scope: per-solution -->` run once per solution (normal multi-item)
- Output paths differ by scope (see section 7)
- Skip the normal methodology × item matrix for step 3 — use dual-scope logic instead

**If not multi-item:**
- Run each methodology once

**Step 6 special case:**
- Check if `projects/$ARGUMENTS/step-6/` already has iteration folders
- Count existing `iteration-N/` folders and create the next one: `iteration-{N+1}/`
- If no iterations exist, create `iteration-1/`
- Output dir for this run = `step-6/iteration-N/`

## 4. Discover Methodologies

Use Glob to find all `.md` files in the step's methodology folder:
- Steps 1-5: `methodologies/N-*/*.md` (e.g., `methodologies/1-audience-problems/*.md`)
- Step 6: `methodologies/6-execution/builders/*.md`, then `methodologies/6-execution/marketing/*.md`, then `methodologies/6-execution/analytics/*.md`

Skip files starting with `_` (like `_template.md`, `_synthesis.md`).

If no methodology files are found, tell the user: "No methodology files found for step N. Add .md files to `methodologies/N-folder/` and run again."

**For step 3 (dual-scope):** After discovering methodology files, check the first 3 lines of each for a `<!-- scope: per-market -->` or `<!-- scope: per-solution -->` comment. Categorize each methodology:
- `per-market`: trend-scanning, market-signals, market-report-sizing, conference-mapping
- `per-solution`: competitor-mapping, scout-enrichment, ad-reach-sizing, opportunity-ranking
- If no scope annotation is found, default to `per-solution`

## 5. Resolve Execution Order (Wave Dependencies)

Methodologies within a step may depend on each other's outputs. Resolve this before spawning agents.

**For each methodology file:**
1. Read its `## Inputs needed` section
2. Check if any listed input matches another methodology's output filename in the same step
   - A methodology's output filename = its own filename (e.g., `problem-discovery.md` outputs to `step-1/problem-discovery.md`)
   - If methodology B lists `problem-discovery.md` as an input, and methodology A is named `problem-discovery.md`, then B depends on A

**Group into waves:**
- **Wave 1:** Methodologies whose inputs are all external to this step (e.g., `brief.md`, prior step outputs)
- **Wave 2:** Methodologies that depend on at least one wave-1 methodology's output
- **Wave 3:** Methodologies that depend on at least one wave-2 methodology's output
- Continue until all methodologies are assigned

**Example — Step 1:**
- `problem-discovery.md` inputs: `brief.md` → **wave 1**
- `problem-validation.md` inputs: `brief.md`, `problem-discovery.md` → **wave 2**
- `problem-matrix.md` inputs: `brief.md`, `problem-discovery.md`, `problem-validation.md` → **wave 3**

**Example — Step 2 (per segment):**
- `idea-volume.md`, `idea-tech.md`, `prior-art.md` → all inputs are `brief.md` + `step-1/decisions.md` + `seed.md` → **wave 1**
- `idea-dedup.md`, `idea-mutation.md` → inputs include `idea-volume.md`, `idea-tech.md` → **wave 2**
- `solution-ranking.md` inputs include `feasibility-check.md`, `impact-estimate.md`, `differentiation-check.md`, `idea-mutation.md` → **wave 4**

**Example — Step 3 (dual-scope):**
Wave 1 runs both per-market and per-solution agents in parallel (all have only external inputs):
- Per-market (once per unique market): `trend-scanning.md`, `market-signals.md`, `market-report-sizing.md`, `conference-mapping.md`
- Per-solution (once per solution): `competitor-mapping.md`, `scout-enrichment.md`, `ad-reach-sizing.md`

Wave 2 (depends on wave 1 outputs):
- Per-solution: `opportunity-ranking.md` — reads per-market outputs from `_markets/{market-slug}/` AND per-solution outputs from `{solution-slug}/`

Example with 3 solutions across 2 markets: wave 1 = (4 × 2 markets) + (3 × 3 solutions) = **17 agents**. Wave 2 = 3 agents. Total = **20 agents**.

## 6. Resolve Model Per Methodology

For each methodology file:
1. Check the first 3 lines for a `<!-- model: X -->` comment
2. If found, use that model (haiku, sonnet, or opus)
3. If not found, use the default from process.md's Step Defaults table

## 7. Spawn Agents (Wave by Wave)

Execute each wave in sequence. Within a wave, launch all agents in parallel.

**For each wave (starting at wave 1):**

For each methodology in this wave (and for each item if multi-item), spawn a Task agent:

**Agent prompt structure:**
```
You are a research/analysis agent for a venture studio. Complete the methodology below and write your output to the specified file.

## Your methodology
[paste full content of the methodology .md file]

## Input files
Read ONLY the files listed in the methodology's "Inputs needed" section. Here are the available paths:
[list ONLY the paths from AVAILABLE_INPUTS that match what the methodology's "Inputs needed" section asks for]

For inputs that reference another methodology's output from THIS step, use the path where that methodology wrote its output (the agent from the earlier wave already created it).

For example, if the methodology says "Inputs needed: brief.md, problem-discovery.md" — list the brief.md path AND the step output path for problem-discovery.md (e.g., projects/$ARGUMENTS/step-1/problem-discovery.md).

## Item (if multi-item)
You are analyzing: [item name from decisions.md]
[item details from decisions.md — name and rationale only, not full file]

## Audience segment (if step 1 with audience segments)
You are researching ONLY this audience segment: [segment-slug]
Description: [segment description from brief.md]
Do NOT research other audience segments. Treat the segment description above as your complete audience definition.

## Segment context (if step 2 with audience segments)
You are designing solutions for the "[segment-slug]" segment.
These are the validated problems in this segment:
1. **[item-name]** — [rationale from decisions.md]
2. **[item-name]** — [rationale from decisions.md]
[list ALL items in this segment from step-1/decisions.md]

Your output should address ALL of these problems. Solutions may address multiple problems simultaneously. Focus on the shared landscape for this audience segment.

## Market context (if step 3, per-market methodology)
You are researching the market: "[market-slug]"
These solutions target this market:
1. **[solution-name]** — [rationale from decisions.md]
[list ALL solutions assigned to this market from step-2/decisions.md]

Your research should cover the market broadly — trends, signals, sizing, and ecosystem that apply to ALL solutions in this market, not just one.

## Solution context (if step 3, per-solution methodology)
You are analyzing this solution: **[solution-name]**
[solution rationale from decisions.md]
Market: [market-slug]

For opportunity-ranking specifically, also read the per-market research files:
- projects/$ARGUMENTS/step-3/_markets/[market-slug]/trend-scanning.md
- projects/$ARGUMENTS/step-3/_markets/[market-slug]/market-signals.md
- projects/$ARGUMENTS/step-3/_markets/[market-slug]/market-report-sizing.md
- projects/$ARGUMENTS/step-3/_markets/[market-slug]/conference-mapping.md

## Output
Write your output to: projects/$ARGUMENTS/step-N/[methodology-filename].md
For multi-item: projects/$ARGUMENTS/step-N/[item-slug]/[methodology-filename].md
For step 1 with audience segments: projects/$ARGUMENTS/step-1/[segment-slug]/[methodology-filename].md
For step 2 with audience segments: projects/$ARGUMENTS/step-2/[segment-slug]/[methodology-filename].md
For step 3 per-market: projects/$ARGUMENTS/step-3/_markets/[market-slug]/[methodology-filename].md
For step 3 per-solution: projects/$ARGUMENTS/step-3/[solution-slug]/[methodology-filename].md
For step 6: projects/$ARGUMENTS/step-6/iteration-N/[subfolder]/[methodology-filename].md

When done, return ONLY a single confirmation line:
Done — [one sentence summary of the key finding or output]
```

**Wait for the current wave to complete before starting the next wave.** Wave-2+ agents depend on files written by earlier waves.

**Key rule: agents read their own inputs.** The orchestrator passes file paths, not file contents. Each agent uses the Read tool to load only what its methodology declares. This keeps the orchestrator's context small and prevents agents from receiving irrelevant context.

**Execution rules:**
- Within each wave: launch methodology agents in parallel (use multiple Task tool calls in one message)
- **Concurrency limit:** If a wave has more than 20 agents, split into sub-batches of 20. Launch sub-batch 1, wait for completion, launch sub-batch 2, etc. Sub-batches within the same wave have no dependency — the split is purely for rate limiting.
- Between waves: wait for all agents in wave N to finish before starting wave N+1
- Step 6 special case: run subfolder groups in sequence (builders → marketing → analytics), applying wave logic within each group
- Set each agent's model and maxTurns per the resolved values
- Each agent gets subagent_type: "general-purpose"

## 8. Collect Results

After all waves complete, note the one-line summaries returned by all agents.

## 9. Run Synthesis (if configured)

Check process.md — does this step have `synthesis: yes`?

If yes:

**9a. Pre-concatenate inputs.** Before spawning the synthesis agent, build a single concatenated input file to avoid dozens of individual Read calls (which bloat the agent's context with tool-call overhead):

1. Collect all output file paths written by methodology agents in this run
2. Also include: `projects/$ARGUMENTS/brief.md` and `projects/$ARGUMENTS/seed.md` (if it exists)
3. Use Bash to concatenate them into a temp file:
   ```bash
   echo "" > /tmp/synthesis-input-$ARGUMENTS.md
   for f in [list of all file paths]; do
     echo "---" >> /tmp/synthesis-input-$ARGUMENTS.md
     echo "# SOURCE: $(basename $f)" >> /tmp/synthesis-input-$ARGUMENTS.md
     echo "---" >> /tmp/synthesis-input-$ARGUMENTS.md
     cat "$f" >> /tmp/synthesis-input-$ARGUMENTS.md
     echo "" >> /tmp/synthesis-input-$ARGUMENTS.md
   done
   ```
4. Also extract ONLY the current step's catalog rules from `_synthesis.md` — strip catalog rules for other steps to reduce prompt size.

**9b. Spawn synthesis agent:**

**Synthesis agent prompt:**
```
[paste content of methodologies/_synthesis.md, but only include the Step-Specific Catalog Rules section for the CURRENT step — omit rules for other steps]

## Input
All methodology outputs, the project brief, and seed idea (if applicable) have been concatenated into a single file for efficiency. Read this ONE file:
/tmp/synthesis-input-$ARGUMENTS.md

Each section is delimited by `# SOURCE: [filename]` headers.

## Output
Write synthesis to: projects/$ARGUMENTS/step-N/synthesis.md
For step 1 with audience segments: projects/$ARGUMENTS/step-1/synthesis.md (cross-segment)
For multi-item with per-item synthesis: also write to step-N/synthesis.md (cross-item)
For step 6: projects/$ARGUMENTS/step-6/iteration-N/synthesis.md
```

Use model: sonnet, maxTurns: 10 for the synthesis agent.

## 10. Update Status

Write `projects/$ARGUMENTS/status.md`:

```markdown
# Status — $ARGUMENTS

**Current step:** N
**Step name:** [from process.md]
**State:** complete
**Last run:** [today's date]
**Summary:** [one-line synthesis result, or combined agent summaries if no synthesis]
**Next action:** /graduate $ARGUMENTS
```

## 11. Report to User

Tell the user:
1. Step N complete — [step name]
2. Methodologies that ran (list filenames)
3. Key finding (synthesis one-liner or top agent result)
4. Files written (list paths)
5. Next command: `/graduate $ARGUMENTS`
