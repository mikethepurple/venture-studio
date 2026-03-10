# /studio — View All Projects

List all venture studio projects and their current status.

## Instructions

1. Use `Glob` to find all `status.md` files under `projects/`:
   ```
   Glob pattern: "projects/*/status.md"
   path: "/Users/mikethepurple/Claude/venture-studio"
   ```

2. Read each `status.md` file to extract:
   - Project name (folder name)
   - Current step number and name
   - Status (pending / complete)
   - Last action date

3. Also read each project's `brief.md` (first 5 lines) to get the seed idea / audience description.

4. Display a summary table:

   | Project | Step | Status | Seed Idea |
   |---------|------|--------|-----------|
   | ... | ... | ... | ... |

5. If no projects exist, say: "No projects yet. Run `/start \"your idea\"` to create one."
