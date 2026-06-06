# Agent Instructions: The Reallocation Engine

This file is for any coding or writing agent operating in this repository.

## Audience

The repository has two customers:

1. Agents that read instructions, recipes, recipes, data contracts, scripts, and gates in order to execute work.
2. Humans who must understand what those agents do, why the workflow is safe, and when judgment or intervention is required.

Write agent-facing instructions precisely, but include concise human-readable summaries for recipes, recipes, and gates.

## Grounding Order

1. Use verified local data first: `data/`, audits, metadata, source exports, and tracked records.
2. Use tested stored scripts first: `scripts/` and documented package commands.
3. Use external lookup only when verified local sources are missing, stale, or insufficient.
4. Create ad hoc scripts only when no suitable stored script exists. Promote reusable ad hoc scripts into `scripts/` after review.

## Directory Rules

- `scripts/` is canonical. Never create `SCRIPTS/`.
- `docs/` is for human-readable system documentation.
- `recipes/` is for agent-facing operating recipes.
- `chapters/` is for book manuscript content.
- `data/` is for source data, generated data, and evidence artifacts.
- `pantry/` is for research and raw/reference material.

## Phase Gates

Do not run a fully automated pipeline until:

1. the problem is formulated;
2. local data has been checked;
3. vetted scripts have been checked;
4. a small manual run passes;
5. automated tests or validation checks pass;
6. a review or audit has been recorded;
7. rollback or recovery is documented for write operations.
