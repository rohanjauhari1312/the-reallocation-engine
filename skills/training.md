# Skill: training -- Learning Plan Evaluation

## Executive Summary

Evaluate whether a course, certificate, or practice plan creates useful
evidence for target roles. Agents use this to compare options; humans use the
summary to keep the recommendation tied to opportunity cost and verifiable
outputs.

Current status: planning helper.

## Required Reads

- `skills/_shared.md`
- role evaluations or target-role notes, if available
- `data/bls/compact/soc_occupation_compact.csv` when SOC evidence is known
- student-approved CV/profile evidence
- `skills/RUN_LOG.md`

## Phase Gates

1. **Target gate:** Identify the target role or evidence gap before evaluating
   training.
2. **Local evidence gate:** Check existing student evidence and local role data
   before external lookup.
3. **Stored script gate:** If labor-market or role-quality evidence is needed,
   use existing data/scripts before prompting.
4. **Verification gate:** Recommend only plans with observable proof of work.
5. **Logging gate:** Log chosen training only when it affects the application
   strategy or produces reusable evidence.

## Evaluation Criteria

| Criterion | Question |
|---|---|
| Role evidence | Does it improve evidence for a target role? |
| Labor-market direction | Does it match BLS/SOC or project research signals? |
| Portfolio output | Does it produce something inspectable? |
| Time cost | What is the opportunity cost? |
| Verification | How will the student prove completion or skill? |

## Rule

Prefer projects and artifacts that can be logged, tested, and reused in role
evaluations. Do not treat a certificate as useful without explaining the signal
it creates.
