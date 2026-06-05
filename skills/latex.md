# Skill: latex -- Not Active

## Executive Summary

LaTeX export is not implemented. Agents should not invent a LaTeX pipeline or
write a one-off converter before checking whether a maintained script exists.
Humans should use this as a clear inactive marker.

The Reallocation Engine currently supports Markdown CV to PDF generation through
`scripts/resumes/generate-pdf.mjs`.

LaTeX export is not implemented in this repo.

Use `skills/pdf.md` unless a maintained LaTeX script is added under
`scripts/resumes/`.

## Phase Gates

1. **Stored script gate:** Stop unless a maintained LaTeX script exists under
   `scripts/`.
2. **Implementation gate:** If a user asks for LaTeX export, create a tested
   script under `scripts/resumes/`, document it, and add a verification command.
3. **Logging gate:** Log any new maintained export path in `skills/RUN_LOG.md`.
