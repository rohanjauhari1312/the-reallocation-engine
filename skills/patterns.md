# Skill: patterns -- Outcome Pattern Analysis

## Executive Summary

Analyze outcome patterns only when enough tracker history exists. Agents use
this to run the maintained pattern script and summarize readiness; humans use
the summary to prevent premature conclusions from tiny samples.

This is a cautious analysis skill. It should not be used as a confident advisor
until the tracker contains enough real outcomes.

## Current Status

Partially implemented as a Python audit scaffold:

```bash
python3 scripts/ats/analyze_patterns.py
```

It writes:

```text
data/ats/application-patterns-audit.md
```

The script currently measures readiness and descriptive counts across the
tracker, scan history, pipeline, reports, and run log. Deeper conversion
analysis still requires real application outcomes.

## Minimum Data Requirement

Before analysis, require at least 5 tracked opportunities with an outcome beyond
`Evaluated`, such as:

- `Applied`
- `Responded`
- `Interview`
- `Offer`
- `Rejected`
- `Withdrawn`
- `Skip`

If fewer than 5 exist, stop and log:

```markdown
## YYYY-MM-DD -- Pattern analysis blocked

- **Skill:** patterns
- **Worked:** Tracker inspected.
- **Did not work:** Not enough outcomes for pattern analysis.
- **Evidence:** N/5 outcome-bearing rows.
- **Next:** Continue collecting outcomes, then extend `scripts/ats/analyze_patterns.py`.
```

## Phase Gates

1. **Data-volume gate:** Require at least five outcome-bearing tracker rows
   before interpretation.
2. **Stored script gate:** Prefer `python3 scripts/ats/analyze_patterns.py`.
3. **Verification gate:** Read the generated audit before summarizing.
4. **Inference gate:** Label recommendations as descriptive until enough data
   supports stronger claims.
5. **Logging gate:** Log blocked or completed analysis runs.

## Future Analysis Contract

The script should eventually produce:

- total entries;
- date range;
- counts by status;
- live vs stale posting outcomes;
- sponsorship evidence vs outcomes;
- SOC group vs outcomes;
- company size or funding recency vs outcomes when available;
- recommendations with evidence.

## Allowed Current Use

Until enough tracker history exists, this skill may only:

- summarize tracker counts;
- identify missing fields;
- recommend data cleanup;
- create a task to build the script.

It must not infer "what works" from a tiny or unverified sample.
