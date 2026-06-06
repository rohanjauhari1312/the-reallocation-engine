# Recipe: pdf -- Generate ATS-Friendly CV PDFs

## Executive Summary

Generate ATS-friendly PDFs from approved Markdown CVs using the maintained
resume script. Agents use this to run the formatting pipeline; humans use the
summary to confirm no resume content is invented or silently altered.

Use this recipe to turn the anonymized Markdown CV examples into PDF files for
classroom testing.

This recipe is for formatting and reproducibility. It should not invent resume
content or tailor a student CV beyond evidence already present in the source
Markdown.

## Required Reads

Read first:

- `recipes/_shared.md`
- `scripts/resumes/README.md`
- `resumes/*.md`
- `logs/RUN_LOG.md`

## Phase Gates

1. **Source gate:** The Markdown CV is anonymized or student-approved.
2. **Local evidence gate:** Use the existing Markdown file; do not invent resume
   content.
3. **Stored script gate:** Use `npm run resumes:pdf` or
   `scripts/resumes/generate-pdf.mjs`; do not write a one-off renderer first.
4. **Verification gate:** Confirm the output PDF exists and, if possible, page
   count and file size are plausible.
5. **Logging gate:** Log generated PDFs and failures.

## Primary Tool

```bash
npm run resumes:pdf -- resumes/aarav-patel-cv.md
```

The underlying script is:

```bash
node scripts/resumes/generate-pdf.mjs <input-cv.md> [output.pdf]
```

## Workflow

1. Choose the Markdown CV.
   - Use only anonymized examples or student-approved Markdown.
   - Do not use deleted original PDFs.

2. Inspect the Markdown.
   - Confirm the name, email, phone number, and links are fake or approved.
   - Confirm the content is plain text and ATS-friendly.

3. Generate the PDF.
   - If no output path is given, the script writes into `output/resumes/`.
   - If Playwright or Chromium is missing, record the failure and the needed
     dependency.

4. Verify the result.
   - Confirm the PDF file exists.
   - If possible, check page count and file size.

5. Log the run in `logs/RUN_LOG.md`.

## Log Template

```markdown
## YYYY-MM-DD -- CV PDF generation

- **Recipe:** pdf
- **Input:** resumes/first-last-cv.md
- **Command:** `npm run resumes:pdf -- resumes/first-last-cv.md`
- **Output:** output/resumes/first-last-cv.pdf
- **Worked:** ...
- **Did not work:** ...
- **Next:** ...
```

## Tailoring Rule

For class exercises, students may create a tailored Markdown variant first.
Every added recipe, project, credential, or achievement must be traceable to the
student's real evidence. Keyword matching is allowed; fabrication is not.
