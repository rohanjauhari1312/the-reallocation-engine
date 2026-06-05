# Skill: oferta -- Evidence-Based Role Evaluation

## Executive Summary

Evaluate one role using verified local data, maintained scripts, and bounded
human judgment. Agents use this to assemble evidence and produce a pursue /
investigate / skip recommendation; humans use the summary to see what was
verified, inferred, missing, or blocked.

Use this skill when a student pastes a job description or job URL and wants to
know whether it is worth pursuing.

This skill may produce a recommendation, but every recommendation must show
which parts are verified, inferred, or missing.

## Required Reads

Read first:

- `skills/_shared.md`
- `data/80-days-to-stay/data/SEC_DOL_H1b_data_mapped-audit.md`
- `data/bls/bls-audit.md`
- `data/bls/compact/soc_occupation_compact.csv` if SOC evidence is needed
- `resumes/*.md` if the student asks for fit against a CV
- `skills/RUN_LOG.md`

## Phase Gates

1. **Role gate:** The company, role, and posting or job description are named.
2. **Local evidence gate:** Check sponsorship, ATS/liveness, BLS/SOC, CV, and
   existing reports locally before external lookup.
3. **Stored script gate:** Use `scripts/ats/`, npm commands, and local data
   before ad hoc code.
4. **Evidence gate:** Keep verified, inferred, and missing fields separate.
5. **Recommendation gate:** Do not recommend `Pursue` when liveness, fit, or
   sponsorship evidence is missing in a way that changes the decision.
6. **Logging gate:** Save reports and log meaningful evaluations.

## Evidence Blocks

### A. Role Summary

Extract only what the posting says:

- company;
- role title;
- location or remote policy;
- employment type;
- seniority;
- compensation, if present;
- required skills;
- posting URL and date, if visible.

If the posting does not say it, mark it as missing.

### B. Company Sponsorship Evidence

Check the mapped SEC/H-1B data when the company name is available:

- `Total Approvals`
- `Total Denials`
- `Approval_Rate`
- `median_salary_offered`
- `top_job_titles_sponsored`
- SEC funding fields such as `latest_funding_amount` and funding date fields,
  when present.

Report:

- `Proven` only when H-1B evidence is present and clearly tied to the company.
- `Likely` only when related evidence exists but is incomplete.
- `Unknown` when the company is not found or key fields are null.

Do not claim sponsorship from a careers page alone.

### C. ATS And Liveness Evidence

Use the ATS tools when a URL or company name is available:

```bash
cd scripts/ats
python3 detect_ats.py --file ../../data/ats/company-check.txt --output ../../data/ats/<slug>-ats-check.csv
cd ../..
npm run ats:liveness -- https://example.com/job/123
```

Keep these separate:

- ATS provider detected;
- job URL currently live;
- job URL stale or redirected;
- not checked.

### D. Role Quality And Labor-Market Evidence

Use BLS/SOC data only when the SOC code is known or has been explicitly
classified by a script.

Use:

- `data/bls/compact/soc_occupation_compact.csv`
- `data/bls/bls-audit.md`

If SOC is unknown, write:

`SOC evidence: missing; classifier not run.`

### E. CV Fit Evidence

If evaluating against a student CV, use only the Markdown CV files in
`resumes/` or text pasted by the student.

Map requirements to exact CV evidence:

| Requirement | CV evidence | Gap | Mitigation |
|---|---|---|---|

Do not invent projects, schools, companies, certifications, or tools.

### F. Recommendation

Use this tiering:

- `Pursue`: live posting, plausible company evidence, role is aligned with CV,
  and no obvious blockers.
- `Investigate`: useful opportunity but one or more important fields are
  missing.
- `Skip for now`: stale posting, poor fit, or no supporting company/role
  evidence after checking available data.

## Report Location

If a written report is needed, save it near the relevant workflow data:

```text
data/ats/reports/YYYY-MM-DD-company-role-evaluation.md
```

Then add a short entry to `skills/RUN_LOG.md`.

## Output Format

```markdown
# Evaluation: Company -- Role

**Date:** YYYY-MM-DD
**URL:** ...
**Recommendation:** Pursue | Investigate | Skip for now

## Evidence Summary

| Area | Status | Evidence |
|---|---|---|
| Sponsorship | Proven/Likely/Unknown | ... |
| ATS | Detected/Not detected/Not checked | ... |
| Liveness | Live/Stale/Unknown | ... |
| SOC/BLS | Verified/Missing | ... |
| CV fit | Strong/Mixed/Weak/Not checked | ... |

## Missing Data

- ...

## Next Action

- ...
```
