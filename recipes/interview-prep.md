# Recipe: interview-prep -- Evidence-Based Prep Draft

## Executive Summary

Prepare interview notes from verified role, company, CV, and evaluation
evidence. Agents use this to assemble prep material; humans use the summary to
confirm that the agent is not fabricating questions or personal stories.

Current status: draft workflow. Use this only after a role has been evaluated or
an interview has been confirmed.

## Required Reads

- `recipes/_shared.md`
- Role evaluation under `data/ats/reports/`, if available.
- Live posting or saved job description.
- Student-approved CV facts.
- Company evidence from SEC/H-1B and ATS checks, when relevant.
- `logs/RUN_LOG.md`

## Phase Gates

1. **Role gate:** Do not prep without a confirmed role, saved posting, or
   interview context.
2. **Local evidence gate:** Use saved evaluations, CV facts, company evidence,
   and posting text before external lookup.
3. **Stored script gate:** Use existing `scripts/` outputs when company,
   liveness, or role-quality checks are needed.
4. **Verification gate:** Separate sourced questions from inferred questions.
5. **Logging gate:** Log reusable notes or story-bank material.

## Rules

- Separate sourced questions from inferred questions.
- Do not fabricate interview questions.
- Do not invent personal STAR stories.
- Use BLS/SOC and company evidence when discussing market or role context.
- Log the prep session if it creates reusable notes or story-bank material.

## Output

```markdown
# Interview Prep: Company -- Role

## Verified Context

## Likely Interview Areas

## Questions To Prepare

## Student Evidence To Use

## Missing Data
```
