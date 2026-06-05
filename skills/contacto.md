# Skill: contacto -- Outreach Drafting

## Executive Summary

Draft short outreach messages from verified company, role, and CV evidence.
This skill is primarily for agents to execute, while humans use this summary to
confirm the agent is not inventing contacts or relationships.

Current status: draft workflow. Use only after a role has been evaluated or the
student supplies a verified outreach context.

## Required Reads

- `skills/_shared.md`
- Company and role from a live posting or evaluation report.
- Student-approved CV facts.
- Optional public source supplied by the student.
- `skills/RUN_LOG.md` if outreach is tracked.

## Phase Gates

1. **Evidence gate:** Do not draft if the company, role, and reason for outreach
   are not locally verified or supplied by the student.
2. **Privacy gate:** Do not search for private contact details.
3. **Stored script gate:** No maintained outreach script exists in `scripts/`;
   keep this as bounded drafting unless automation is explicitly requested.
4. **Verification gate:** Every message must include an evidence note.
5. **Logging gate:** Log only meaningful outreach milestones.

## Rules

- Keep messages short and factual.
- Do not include private phone numbers.
- Do not imply a referral, interview, or relationship that does not exist.
- If no verified reason for outreach exists, ask for more context or stop.
- Log outreach milestones only if the student is tracking applications.

## Output

```markdown
## Outreach Draft

**Audience:** recruiter | hiring manager | peer | unknown
**Evidence used:** ...

Message:
...
```
