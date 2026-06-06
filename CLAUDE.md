# Claude Instructions: The Reallocation Engine

This repository is both a book and an agent-running project. Treat it as a verified-data system first and a writing project second.

## Operating Rules

1. Read `README.md` and `docs/repo-structure.md` before making structural changes.
2. Check verified local data before external lookup. Prefer `data/`, stored audits, metadata, and maintained source exports.
3. Check vetted stored scripts before creating ad hoc scripts. Prefer `scripts/` for repeatable work.
4. Use lowercase `scripts/` only. Do not create or reference `SCRIPTS/`.
5. Recipes in `recipes/` are agent-facing recipes with human-readable summaries. Follow their required reads, commands, tests, and logging rules.
6. Record meaningful agent runs in `logs/RUN_LOG.md` when a recipe changes data, outputs, decisions, or repository state.
7. Keep book manuscript content in `chapters/`. Do not mix operational scripts or data into manuscript folders.
8. Preserve human judgment gates. Do not advance an automated pipeline until the previous step has an explicit test and evidence artifact.

## Preferred Structure

- `README.md` — human-facing project overview and architecture entry point.
- `CLAUDE.md` — Claude/Cowork behavior rules.
- `AGENTS.md` — cross-agent behavior rules.
- `docs/` — human-readable system documentation.
- `data/` — vetted local data, source exports, generated datasets, and audits.
- `scripts/` — tested, vetted, reusable automation.
- `recipes/` — agent-readable recipes and operating procedures.
- `chapters/` — book manuscript.
- `slides/` — optional teaching decks if needed later.
- `pantry/` — research notes, source notes, and raw/reference material.

## Verification

Before reporting completion, state:

- files changed;
- scripts or data checked;
- tests, builds, or searches run;
- any unverified assumptions or remaining risks.
