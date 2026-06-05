# Skill: deep -- Research Prompt Builder

## Executive Summary

Build an external-research prompt only after verified local evidence and stored
scripts have been checked. This skill helps agents ask better research
questions; humans use the summary to confirm that external lookup is justified.

Current status: prompt-building helper. It is not a replacement for SEC/H-1B,
ATS, liveness, or BLS/SOC scripts.

## Required Local Checks First

- Read `skills/_shared.md`.
- Run or read the relevant company evidence from the SEC/H-1B mapped data.
- Check ATS/liveness if there is a job URL.
- Check BLS/SOC data if a SOC code is known.
- Check whether a stored script in `scripts/` already answers the question.
- Review `skills/RUN_LOG.md` for previous attempts.

## Phase Gates

1. **Local evidence gate:** Name which local files, audits, or tracker records
   were checked.
2. **Stored script gate:** Name which `scripts/` tool was used, or why none fit.
3. **External research gate:** Only ask for external research after the local
   gaps are explicit.
4. **Citation gate:** Requested external claims must require citations.
5. **Logging gate:** Log research blockers or reusable prompt improvements.

## Output

Create a research prompt that clearly separates:

- verified local evidence;
- open questions;
- external research requested;
- claims that need citations.

No uncited factual claims should be presented as verified.
