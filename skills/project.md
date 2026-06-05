# Skill: project -- Portfolio Project Planning

## Executive Summary

Evaluate whether a portfolio project would create better evidence for future
applications. Agents use this to plan a bounded project; humans use the summary
to check that the project serves an evidence gap rather than generic busyness.

Current status: planning helper. This is not part of the sponsorship or company
master-data pipeline.

## Required Reads

- `skills/_shared.md`
- relevant role evaluations under `data/ats/reports/`, if available
- relevant CV material under `resumes/`
- `data/bls/compact/soc_occupation_compact.csv` when a target SOC is known
- `skills/RUN_LOG.md`

## Phase Gates

1. **Evidence-gap gate:** Name the job-search evidence gap the project addresses.
2. **Local evidence gate:** Check existing CV/project evidence before proposing
   a new build.
3. **Stored script gate:** If the project needs data processing or validation,
   check `scripts/` before suggesting ad hoc code.
4. **Verification gate:** The project plan must include a testable artifact.
5. **Logging gate:** Log project milestones if they become reusable evidence.

## Evidence-Based Project Criteria

Evaluate whether the project would create:

- a concrete artifact;
- measurable behavior or results;
- a role-relevant SOC/skill signal;
- a short explanation suitable for interviews;
- a reproducible repo or demo.

## Output

Return:

- build / skip / narrow;
- the evidence gap it addresses;
- one-week MVP plan;
- how the student will record what worked and what failed.
