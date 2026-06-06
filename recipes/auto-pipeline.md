# Recipe: auto-pipeline -- Not Yet Automated

## Executive Summary

This recipe documents why the full pipeline is not yet automated. Agents should
use it as a stop sign: run the verified sequence manually or semi-automatically
until phase gates prove the workflow is safe. Humans use this summary to see
which checks must pass before automation expands.

Current status: not implemented as a single command. The Reallocation Engine
currently works as a sequence of verified steps, not a fully automatic apply
pipeline.

## Required Reads

- `recipes/_shared.md`
- `docs/repo-structure.md`
- `scripts/README.md`
- `logs/RUN_LOG.md`

## Full Automation Gates

Do not describe this as automated until all gates pass:

1. **Problem gate:** The target pipeline outcome is defined.
2. **Local evidence gate:** Relevant data and audits exist.
3. **Stored script gate:** Existing scripts have been inventoried.
4. **Small-run gate:** One manually supervised run succeeds.
5. **Test gate:** Verification scripts or tests pass.
6. **Review gate:** A human or independent reviewer checks outputs.
7. **Rollback gate:** Write operations have a recovery path.
8. **Logging gate:** Runs produce `logs/RUN_LOG.md` and audit artifacts.

## Use This Sequence Instead

1. `recipes/scan.md` -- detect ATS/provider/job URLs.
2. `recipes/pipeline.md` -- verify URL liveness and move URLs through triage.
3. `recipes/oferta.md` -- evaluate one role using company, sponsorship, ATS,
   liveness, BLS/SOC, and CV evidence.
4. `recipes/pdf.md` -- generate an ATS-friendly PDF from an approved Markdown CV.
5. `recipes/tracker.md` -- record status changes and outcomes.

## Future Script Contract

A real auto-pipeline should live under `scripts/ats/` or `scripts/pipeline/`
and should emit:

- structured JSON status;
- updated `data/ats/pipeline.md`;
- optional report under `data/ats/reports/`;
- a log entry in `logs/RUN_LOG.md`.

Until that script exists, do not describe this recipe as automatic.
