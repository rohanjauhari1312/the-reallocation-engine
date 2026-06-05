# Skills

## Executive Summary

The `skills/` folder contains student-facing operating recipes for The
Reallocation Engine.

Each skill is written for two customers:

- **Agents** need precise executable instructions: required reads, stored
  scripts, allowed outputs, tests, handoff conditions, and stop rules.
- **Humans** need a readable summary of what the skill does, what evidence it
  uses, where risk remains, and when judgment is required.

These are not the engine itself. The engine is the combination of:

- collected source data in `data/`;
- maintained scripts in `scripts/`;
- generated audits and compact extracts;
- skill recipes that tell students how to run, inspect, and interpret those
  scripts.

## Design Rule

Skills must use verified data and vetted stored scripts before prompting or
writing new code.

Good skill behavior:

- read the skill's executive summary;
- check `skills/_shared.md`;
- check verified local data and audits;
- check existing commands and scripts under lowercase `scripts/`;
- run a script;
- read an audit;
- inspect generated output;
- record what happened;
- then explain or decide.

Bad skill behavior:

- ask an LLM to guess sponsorship likelihood;
- ask an LLM to invent labor-market statistics;
- create an ad hoc script before checking `scripts/`;
- reference uppercase `SCRIPTS/`;
- skip available audits;
- produce a confident recommendation without checking source data.

## Required Skill Shape

Every active skill should include:

1. `Executive Summary` for humans.
2. `Required Reads` or `Required Context`.
3. `Phase Gates` showing what must pass before action.
4. `Primary Tools` or a clear statement that no stored script exists.
5. `Workflow`.
6. `Output` or `Output Contract`.
7. `Logging` requirements.

## Active Skills

| Skill | Current role |
|---|---|
| `_shared.md` | Shared verified-data contract and logging rules. |
| `scan.md` | ATS detection and portal scanning using `scripts/ats/`. |
| `pipeline.md` | Process `data/ats/pipeline.md` through verified liveness/scoring steps. |
| `oferta.md` | Evaluate a job/role using sponsorship, ATS, BLS/SOC, and CV evidence. |
| `pdf.md` | Generate PDFs from anonymized Markdown CVs using `scripts/resumes/`. |
| `tracker.md` | Inspect and maintain `data/ats/applications.md`. |
| `patterns.md` | Future outcome-pattern analysis; requires tracker history first. |
| `update.md` | Repo-local update and skill-maintenance checklist. |

## Draft Or Helper Skills

| Skill | Current role |
|---|---|
| `apply.md` | Draft application answers from verified role/CV evidence. |
| `auto-pipeline.md` | Placeholder; documents the manual verified sequence until a script exists. |
| `batch.md` | Small-batch triage pattern for many URLs. |
| `contacto.md` | Outreach drafting with verified context only. |
| `deep.md` | External research prompt builder after local checks. |
| `followup.md` | Follow-up tracking draft; no cadence script yet. |
| `interview-prep.md` | Interview prep draft from saved evidence. |
| `latex.md` | Explicitly inactive until a LaTeX script exists. |
| `ofertas.md` | Multi-role comparison after individual evaluations. |
| `project.md` | Portfolio project planning helper. |
| `training.md` | Learning-plan evaluation helper. |

Before using any draft skill, check whether it calls real scripts and whether it
logs its outputs.

## Run Log

Use `skills/RUN_LOG.md` for human-readable history:

- what was run;
- what worked;
- what failed;
- what file changed;
- what should be tested next.

Generated data audits still belong next to the data they inspect, using
`-audit.md`.
