# Architecture Notes — Methodology System

## Current state

**Plug and play within a step:** yes — drop a .md file with `## Inputs needed` into the right step folder, it gets auto-discovered, wave-ordered, and run.

**Not plug and play:**
- `maxTurns` — step-level default in `process.md` only, no per-methodology override
- New steps require touching `process.md` + `run/SKILL.md` + `graduate/SKILL.md`

**Potential future improvements (not planned):**
- `<!-- max-turns: N -->` comment support in methodology files
- Step self-description to reduce hardcoding in SKILL.md files
