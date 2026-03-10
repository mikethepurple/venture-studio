# AI Venture Studio

6-step pipeline: Audience & Problems > Solution Design > Opportunity Validation > Business Model > Metrics > Execution. Each step runs methodologies as isolated agents. Manual graduation between steps.

## Commands

| You want to... | Use... |
|---|---|
| Start a new project | `/start [audience description]` |
| Run current step's methodologies | `/run [project-slug]` |
| Advance to next step | `/graduate [project-slug]` |
| See all projects | `/studio` |

## How It Works

1. Methodologies live in `methodologies/N-folder/*.md` — each file is a complete agent prompt
2. `/run` discovers methodology files for the current step, spawns one Task agent per methodology
3. Agents run in parallel, write outputs to the project's step folder
4. `/graduate` presents outputs to the user, records decisions, advances to next step

Edit a methodology file = change how agents work. Drop a new file in a folder = add a new methodology. No other files to touch.

## File Structure

```
CLAUDE.md              <- you are here
process.md             <- step definitions, defaults, graduation criteria
methodologies/
  _template.md         <- how to write a methodology
  _synthesis.md        <- internal: cross-methodology synthesis
  1-audience-problems/ <- step 1 methodologies
  2-solution/          <- step 2 methodologies
  3-opportunity/       <- step 3 methodologies
  4-business-model/    <- step 4 methodologies
  5-metrics/           <- step 5 methodologies
  6-execution/         <- step 6 (builders/, marketing/, analytics/)
.claude/skills/        <- start, run, graduate, studio
projects/[slug]/       <- all project state (brief, status, step outputs, decisions)
templates/             <- reusable output formats
_archive/              <- old methodology files preserved as reference
```

## Session Discipline

Start a fresh session for each `/run` or `/graduate`. State lives in files. Read `projects/[slug]/status.md` to resume.

## Adding a Methodology

1. Copy `methodologies/_template.md`
2. Fill it in
3. Drop it in the right step folder (e.g., `methodologies/2-opportunity/`)
4. Next `/run` picks it up automatically
