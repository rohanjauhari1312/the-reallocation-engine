# Recipe: batch -- Batch Triage Draft

## Executive Summary

Triage many URLs only after a small gated run proves the checks work. Agents use
this to process repeated inputs; humans use the summary to confirm the agent is
not scaling an untested workflow.

Current status: draft workflow.

## Required Reads

- `recipes/_shared.md`
- `recipes/pipeline.md`
- `recipes/scan.md`
- `data/ats/pipeline.md`, if it exists
- `logs/RUN_LOG.md`

## Phase Gates

1. **Input gate:** URLs are stored in `data/ats/pipeline.md` or a named input
   file.
2. **Stored script gate:** Use `npm run ats:verify`, `ats:liveness`,
   `ats:dedup`, and `ats:normalize` before ad hoc scripts.
3. **Small-run gate:** Run liveness on a small sample before a large batch.
4. **Verification gate:** Record counts, failures, and output paths.
5. **Logging gate:** Log the batch in `logs/RUN_LOG.md`.

## Verified Sequence

1. Put URLs in `data/ats/pipeline.md`.
2. Run `npm run ats:verify`.
3. Run liveness checks on a small sample.
4. Deduplicate with `npm run ats:dedup` when appropriate.
5. Evaluate selected live roles with `recipes/oferta.md`.
6. Log the batch in `logs/RUN_LOG.md`.

## Batch Log

```markdown
## YYYY-MM-DD -- Batch triage

- **Recipe:** batch
- **Inputs:** data/ats/pipeline.md
- **Commands:** `npm run ats:verify`, `npm run ats:liveness ...`
- **Worked:** ...
- **Did not work:** ...
- **Next:** ...
```

Large batches should record counts, not long pasted job descriptions.
