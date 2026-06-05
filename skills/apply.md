# Skill: apply -- Draft Application Support

## Executive Summary

Draft application answers from verified role, CV, and evaluation evidence. This
skill is agent-facing, but the summary is for humans deciding whether it is safe
to let the agent draft. It does not decide whether a role is worth pursuing.

Current status: draft workflow. Use this only after `skills/oferta.md` has
produced an evidence-based role evaluation.

## Required Reads

- `skills/_shared.md`
- the saved evaluation under `data/ats/reports/`, if one exists
- the relevant Markdown CV under `resumes/`, if the student is using one
- `skills/RUN_LOG.md`

## Phase Gates

1. **Evaluation gate:** Do not draft until `skills/oferta.md` or a saved
   evaluation has identified verified, inferred, and missing evidence.
2. **Local evidence gate:** Use posting text, evaluation report, CV, and tracker
   notes before external lookup.
3. **Stored script gate:** No maintained application-answer script exists in
   `scripts/`; do not create one unless the user asks for repeatable automation.
4. **Verification gate:** Each answer must name the evidence it uses.
5. **Logging gate:** Log meaningful submissions or reusable answer sets.

## Rules

- Use only facts from the posting, evaluation report, and CV.
- Do not invent projects, credentials, personal stories, work authorization, or
  contact details.
- If the application asks for a claim that is not supported by the CV, draft an
  honest adjacent answer or mark it as a gap.
- Log meaningful application milestones in `skills/RUN_LOG.md` or the tracker.

## Output

Provide copy-paste answers with a short evidence note for each answer:

```markdown
### Question
...

### Draft Answer
...

### Evidence Used
- Posting: ...
- CV/report: ...
```
