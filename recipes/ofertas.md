# Recipe: ofertas -- Multi-Role Comparison

## Executive Summary

Compare multiple roles only after each has an evidence-based evaluation. Agents
use this to assemble a decision table; humans use the summary to confirm that
missing data is not being converted into a fake ranking.

Current status: draft workflow.

## Required Reads

- `recipes/_shared.md`
- one `recipes/oferta.md` evaluation or saved report for each role
- `data/ats/applications.md`, if statuses matter
- `logs/RUN_LOG.md`

## Phase Gates

1. **Evaluation gate:** Every compared role must have an individual evaluation
   or be marked incomplete.
2. **Local evidence gate:** Use saved reports, tracker rows, and local data
   before external lookup.
3. **Stored script gate:** Use existing ATS, liveness, and pattern scripts when
   fields need verification.
4. **Verification gate:** Do not compute precise ranks from missing data.
5. **Logging gate:** Log comparisons that change application strategy.

## Comparison Fields

| Field | Source |
|---|---|
| Company | posting or ATS/provider output |
| Role | posting |
| Liveness | `scripts/ats/` liveness tools |
| Sponsorship | SEC/H-1B mapped data |
| SOC/BLS | BLS compact table when SOC is known |
| CV fit | student CV evidence |
| Missing data | evaluation report |

## Rule

Do not compute a precise ranking from missing data. Use `unknown` and explain
which check would improve the comparison.
