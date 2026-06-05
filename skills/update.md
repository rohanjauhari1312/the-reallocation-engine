# Skill: update -- Repo-Local Maintenance

## Executive Summary

Maintain the skills when repo structure, scripts, data contracts, or audits
change. Agents use this as the maintenance recipe; humans use the summary to
check that agent-facing recipes and human-readable docs stay aligned.

Use this skill to update the student-facing operating recipes when scripts,
data contracts, or audits change.

This is not an upstream package update flow. Do not fetch from an old source
repo unless the user explicitly asks.

## Required Context

Read first:

- `README.md`
- `CLAUDE.md`
- `AGENTS.md`
- `docs/repo-structure.md`
- `DATA_CONTRACT.md`
- `scripts/README.md` if it exists
- `skills/README.md`
- `skills/_shared.md`
- `skills/RUN_LOG.md`

## Phase Gates

1. **Structure gate:** Confirm the repo still uses lowercase `scripts/`,
   `data/`, `docs/`, `skills/`, and `chapters/`.
2. **Local evidence gate:** Read changed data contracts, audits, and docs before
   editing skills.
3. **Stored script gate:** Confirm new commands live under `scripts/` and are
   documented.
4. **Human-doc gate:** Update `docs/` or `README.md` when a skill changes the
   system a human must understand.
5. **Verification gate:** Search for stale paths and unsupported commands.
6. **Logging gate:** Log skill maintenance in `skills/RUN_LOG.md`.

## Workflow

1. Check what changed.
   - New script under `scripts/`.
   - New audit under `data/**`.
   - New compact extract.
   - New report or project draft.

2. Update the relevant skill.
   - Add exact commands.
   - Add exact input and output paths.
   - Add what the script can and cannot verify.
   - Add logging instructions when the workflow changes data or produces a
     reusable result.

3. Check for stale references.

```bash
rg -n "cv.md|config/profile.yml|analyze-patterns|cv-sync" skills
```

Some references may be historical notes, but active workflows should point to
The Reallocation Engine paths and scripts.

4. Validate file readability.

```bash
rg -n "scripts/|data/|RUN_LOG" skills
```

5. Log the update in `skills/RUN_LOG.md`.

## Log Template

```markdown
## YYYY-MM-DD -- Skill maintenance

- **Skill:** update
- **Changed:** skills/...
- **Reason:** ...
- **Worked:** ...
- **Did not work:** ...
- **Next:** ...
```

## Rules

- Keep maintained automation under `scripts/`.
- Keep generated data reports next to the data with `-audit.md`.
- Keep student-specific private data out of source/reference data folders.
- Prefer "not implemented yet" over pretending a script exists.
