---
title: "The Reallocation Engine"
author: "Nik Bear Brown and Humanitarians AI"
date: 2026
lang: en-US
rights: "Copyright © 2026 Nik Bear Brown and Humanitarians AI. All rights reserved. Published by Humanitarians AI."
publisher: "Humanitarians AI"
subtitle: "Verified Data, Phase Gates, and CLI Pipelines for the F-1 OPT Search"
subject_domain: ""
tone: ""
audience: ""
chapter_titles: []
keywords: []
avoid: []
palette_preference: ""
series_name: ""
thumbnail_priority: "title and central icon"
...
<!--
  FRONT MATTER — title page, copyright, dedication, preface.
  Pre-body sections (roman-numeral in a print edition); do not number them as chapters.
  Keep the Medhavy note in the copyright area. Preface is Nik's voice (first person).
-->

# The Reallocation Engine

*Verified Data, Phase Gates, and CLI Pipelines for the F-1 OPT Search*

**Nik Bear Brown · Humanitarians AI**

---

## Copyright

Copyright © 2026 Nik Bear Brown and Humanitarians AI. All rights reserved.

Published by Humanitarians AI, a 501(c)(3) nonprofit organization.

No part of this publication may be reproduced, distributed, or transmitted in any form or by any means without the prior written permission of the publisher, except in the case of brief quotations in critical reviews and certain other noncommercial uses permitted by copyright law.

ISBN: [INSERT ISBN]

First edition: 2026

> These are Kindle / online editions, designed for integration with **Medhavy** (also **Medhavi**) — मेधावी, Sanskrit for "intelligent" or "intellectually brilliant" — an AI-powered intelligent-textbook system. In Medhavy the chapters become adaptive practice: hints, worked examples, quizzes, and feedback loops. Learn more at https://www.medhavy.com/.

---

## Dedication

*For the international student with the clock running — spend the judgment where it counts.*

---

## Preface

I wrote this book because the job search has quietly become a place where fluency and truth come apart. A cover letter can read beautifully and be aimed at a posting that closed three weeks ago. A résumé can sail through every keyword filter and land on a role that was never going to sponsor a visa. An AI can produce, in seconds, a hundred polished applications that the underlying evidence says will go nowhere. The output looks like progress. Often it is the opposite of progress — it is scarce effort, spent confidently, in the wrong place.

For most job-seekers that is an annoyance. For an international student on an F-1 visa with a counting clock — ninety aggregate days of unemployment on post-completion OPT, and the record terminates with no grace period — it is something closer to an emergency. The deadline does not care how busy you felt. It is the cleanest case I know of a more general truth: now that AI has made *execution* cheap, the scarce, decisive resource is *judgment* — knowing which role is worth a day of your life, which evidence to trust, and when to walk away. This book is about reallocating effort toward that judgment, and building a small machine that does the grunt work honestly so you can.

I write from the intersection of teaching, engineering, and AI systems. At Northeastern I teach AI, data science, and AI fluency, and my through-line is *learn AI by doing AI* — not pressing a button and accepting the output, but specifying, delegating, auditing, and taking responsibility for what leaves the screen. Through Humanitarians AI, the nonprofit I founded, I work with international graduates on OPT who are building production-scale AI with public evidence of real work — people living this exact deadline. The Reallocation Engine grew out of that work: a real repository of scripts and recipes that turns a record, not a feeling, into an Apply / Consider / Skip decision about a real role.

A word on what this book is not. It is not immigration counsel — nothing here is legal advice, and the visa rules it leans on must be checked against current USCIS guidance and a qualified attorney before you act on them. It is not a guide to gaming applicant-tracking systems, and it argues hard against misrepresentation of any kind. And it is not a general AI manual; it is one worked example — a job search under a deadline — of a discipline that applies far beyond it. The chapters that follow turn that discipline into something you can run.
# Introduction

It is week six. A student — call her Mira, an F-1 graduate three months out from her degree — has sent two hundred applications. The cover letters are clean. The résumés are tailored. The dashboard says she is working hard, and she is. What the dashboard does not say is that a third of the postings were ghost listings that were never going to hire anyone, that more than half of the companies have never filed a single visa petition, and that her ninety-day OPT unemployment clock has thirty-one days left on it. Every application *looked* like progress. Almost none of it was. She did not have a motivation problem. She had an allocation problem — and no instrument that could tell the difference between effort and progress before the deadline did it for her.

This book is about that instrument: a method, and a working machine, for running a high-stakes search without surrendering the judgment the search depends on.

## The argument, in one breath

The first sign of trouble is usually not failure. It is fluency.

A draft looks clean. An answer sounds reasonable. A chart has labels, the code runs, the plan has phases. Nothing on the surface announces that a human still has work to do. AI has made that surface cheap to produce — and in making *execution* cheap, it has left *judgment* scarce and more valuable, not less. That is the testable claim of this book, and you can watch it fail or hold in your own search: when execution costs nothing, the polished artifact stops being evidence of anything. A randomized trial of engineers learning a new library found that those who delegated to AI scored about seventeen points lower on a comprehension test than those who hand-coded — two letter grades — while *feeling* they had learned more.[^anthropic] The fluency of the output was indistinguishable from the feeling of mastery. The mastery was not there.

The Reallocation Engine points that general claim at one concrete problem. A student with sixty to ninety days to find a sponsoring employer cannot afford to spend judgment evenly. The engine's whole purpose is to **reallocate scarce effort** — away from polished-looking cold applications that the evidence says will go nowhere, and toward the few roles where a record, not a feeling, says effort can matter. The machine does the parts that can be grounded in records and audits. You do the part that cannot be delegated: deciding whether a role is worth a day of your life.

## Who this is for

This is for the international student on the clock, for the career advisors and Humanitarians AI fellows who work alongside them, and for anyone who wants to see what disciplined human–AI collaboration looks like when a real deadline removes the option of self-deception.

## What this book is

It is a **book** and a **working machine** at once. The chapters in `chapters/` teach a method for using AI in a high-stakes search. The same repository contains the scripts, data, and operating recipes that *run* that method — you can clone it, open a terminal, type a command, and get a sourced Apply / Consider / Skip decision about a real role. The book is not a description of a system that lives somewhere else. The book *is* the system, explained.

Along the way it teaches a vocabulary you will use for the rest of your working life, well past this one search. The **fluency trap**: a confident output is not a correct one. The **phase gate**: the explicit point where AI execution stops and human judgment begins — not where you trust the machine less, but where the cognitive work is irreducibly yours. The **verified-data contract**: every number traces to a source, and a figure with no record behind it is decoration, labeled as such. **Gates versus votes**: some facts veto a role outright (a dead posting, an impossible visa timeline) rather than merely lowering its score. And the deeper division underneath all of it — the one this whole series turns on — between what machines now do superbly (pattern-finding, retrieval, drafting, formatting: call it Tier 1) and what remains stubbornly human: auditing an output for plausibility, formulating the right question, reasoning about cause, and being accountable for a decision once it leaves the screen. AI has decisively won the first. The premium, and the danger, both live in the second.

A short list of principles runs through everything here. If you understand these, the rest is detail.

1. **Run the script and read the audit before you prompt.** Verified local data comes before an AI's guess, every time. The engine reads records; it does not improvise them.
2. **Never invent a count, a rate, a match quality, or a confidence.** Every number traces to a source.
3. **Liveness and timeline are gates, not votes.** A dead posting or an impossible visa timeline zeroes a role no matter how good it looks.
4. **Skip is a successful outcome.** A healthy run skips at least half the roles it evaluates. The engine's value is in the applications it talks you *out of*.
5. **Machines verify conformance; humans verify adequacy.** A script can prove a file parses. Only you can decide whether the decision it produced is one you should act on.

These five are a domain-specific reading of a more general framework. Open `SNICKERDOODLE.md` and you will find the constitution this repository is built on — an agent-operating-system that treats a project as a contract between human judgment and AI execution. It names principles, defines hard gates cleared by a named human and logged, sets a lifecycle for every recipe from `DRAFT` to `VERIFIED`, and insists that provenance, never deletion, and honest logging are not optional. The Reallocation Engine is one *domain* governed by it; `DOMAIN.md` is where everything specific to this repository lives. Snickerdoodle is treated lightly here — named, leaned on, not fully unpacked — because this is a book about a job search, not about the framework. The strict, general version is written separately; this repository is the worked example.

## What this book is not

It is not immigration counsel. Nothing here is legal advice; every visa rule must be checked against current USCIS guidance and a qualified attorney before you act. It is not a manual for gaming applicant-tracking systems, and it argues against misrepresentation of any kind — the hard rule against misrepresenting yourself overrides every framing suggestion in these pages. It assumes you can open a terminal and run a command; it does not assume you can program. And it is not a general AI textbook. It is one search, run honestly, as a way of teaching a discipline that travels.

## The fluency trap, running underneath

There is one idea the whole engine exists to defend, and it is worth naming before you meet it twenty times. Genuine understanding is built by *friction* — by the struggle of working something out yourself. Remove the friction and you remove the thing that was supposed to be built. The job-search version is exact: an AI can remove the friction of *writing* a hundred applications, and in doing so remove the friction of *deciding* which one deserves the writing. The clean output stands in for the judgment that never happened. The engine's design is a refusal of that substitution. It automates the execution — drafting, formatting, retrieval, scoring — and then, at a deliberate gate, it stops and hands you back the decision, with its sources labeled, so the part that is irreducibly yours stays yours. The skip rate is the visible proof that the gate is working: a healthy run argues you *out of* most of what you were about to do.

## How this book is organized

The book moves in four movements, then a synthesis.

- **Chapters 1–3 — the core method.** *The Fluency Trap* (Ch. 1): fluency is not correctness. *The Reallocation Principle* (Ch. 2): effort must be reallocated by expected return. *The Verified-Data Contract* (Ch. 3): every factual claim traces to a source or is labeled as decoration.
- **Chapters 4–5 — the discipline.** *Two Customers* (Ch. 4): a recipe is written for two readers at once, the AI agent and the human. *Verifying the Data* (Ch. 5): verified records still need epistemic interrogation.
- **Chapters 6–13 — the evidence components.** *Where the Money Went: SEC Form D* (Ch. 6), *Who Sponsors: The 80 Days Sponsorship Scorer* (Ch. 7), *Is the Job Real: ATS Detection and Liveness* (Ch. 8), *Is the Role Any Good: BLS / O\*NET Role Quality* (Ch. 9), *The Visa Timeline Manager* (Ch. 10), *The Bayesian Role Scorer* (Ch. 11) that composes them, *The OPT Framing Generator* (Ch. 12), and *Resumes That Survive the Filter* (Ch. 13).
- **Chapters 14–16 — operating the engine.** *Recipes: Operating the Engine* (Ch. 14), *The Pipeline Tracker and the Skip Rate* (Ch. 15), and *The Build and the Honest Run* (Ch. 16) — the first honest, gated, end-to-end run.
- **Chapter 97 — synthesis.** The load-bearing themes, gathered. An appendix of best practices closes the book.

To orient yourself in the repository, start with `_MANIFEST.md` — the read-first map of what is canonical, what is task-relevant, and what to ignore (its machine-readable twin is `.ai/manifest.yaml`). From there, `DOMAIN.md` tells you what the project *is* and what is runnable today; `SNICKERDOODLE.md` tells you what governs it; `logs/RUN_LOG.md` tells you what has actually been run; `status.md` tells you where things stand now. A couple of minutes there and you can navigate without reading the whole tree.

## How to read this book

You do not have to read it front to back before touching the machine. The chapters are written to be self-contained — you can drop into Chapter 7 to understand sponsorship and it will hold. Each chapter closes with the same features: a *What would change my mind* prompt, a *Still puzzling* note, and exercises that push you to run, trace, and break the thing rather than just read about it. But the fastest way to understand the argument is to watch the engine make one decision and trace it. With the repository open in a terminal:

1. **Read the orientation files.** Open `_MANIFEST.md`, then `SNICKERDOODLE.md` and `DOMAIN.md`. Five minutes. You now know what to read, what governs the engine, and what actually works.
2. **Check the environment.** Run `npm run doctor`. It reports what tools are installed and which commands have real scripts behind them — an honest map of the runnable surface.
3. **Run the decision core and trace it.** Run `npm run score data/examples/ch11-roles.json`, then open the audit at `data/examples/role-scores.md`. Pick one row and read it term by term: sponsorship, fit, liveness, timeline — each labeled *record*, *model-judgment*, or *your-input*. If you cannot explain a recommendation from its sources, distrust the recommendation before you distrust your confusion.
4. **Read Chapter 1.** Open `chapters/01-the-fluency-trap.md`. The idea you just watched the scorer enforce — that a confident output is not a correct one — is the idea the whole engine exists to defend.

## A note about AI

This book asks you to use AI more aggressively than most career advice would, and to trust it less. Both at once. That is not a contradiction; it is the whole method.

Use it aggressively for what it is genuinely superb at — the Tier 1 work. Let it draft the cover letter, reformat the résumé into ATS-safe plain structure, summarize a ten-K, extract the sponsorship history from a filing, generate five framings of the same experience for the OPT conversation. This work is real, it is tedious, and the engine automates it without apology. The labor market is, in fact, paying for exactly this combination: the wage premium attached to validated AI skill is large and growing, and it lands not on people who abandoned their field to become generic technologists but on domain experts who kept their judgment and added AI fluency on top.[^premium] The arrow that pays is *your domain plus AI*, not *your domain, traded in for AI*.

Trust it less for the work on the other side of the gate. An applicant-tracking system will screen your résumé with AI and may auto-reject it with no human in the loop[^screening]; a match-score vendor will rank you with a model whose bias you cannot see.[^eightfold] These are AI systems making consequential judgments about you, fluently and without accountability. The engine's response is not to fight fluency with more fluency. It is to insist on records the machine cannot fake: who has actually filed visa petitions, whether a posting is actually live, whether a role actually clears the BLS / O\*NET bar, whether the visa timeline is actually possible. Some of those facts are *gates* — they veto a role outright rather than nudging a score — because a dead posting and an impossible deadline are not weak signals to be averaged away.[^opt]

There is a specific trap the deadline makes vivid. The same weights that produce an AI's confident output are the weights that would have to audit it, which is why a model cannot reliably flag its own errors — the plausibility check has to come from outside the model, from a human with real stakes. You are that human. The machine cannot know that this particular role, with this particular team, in this particular city, is one you would actually take; it cannot be accountable for the day of your life the application costs; it cannot tell you when to stop. Those are not temporary gaps that the next model closes. They are the permanent shape of the division of labor. The engine is built to make that shape visible: AI executes up to the gate, and at the gate it hands you a decision with every source labeled — *record*, *model-judgment*, or *your-input* — so you can do the one thing it cannot, which is decide. These chapters also integrate with **Medhavy** (also **Medhavi**), an AI-powered intelligent-textbook system, where they become adaptive practice — hints, worked examples, feedback loops. Even there, the learning target stays human.

## Begin

Mira's problem was never effort. It was that nothing told her, before the clock did, where the effort was worth spending. So open the repository. Do not ask first whether the engine looks impressive. Ask what would have to be true for one of its decisions to be trusted, what the machine could not know, and what you are now responsible for. Then run the script, read the audit, and begin.

**Tags:** F-1 OPT job search · AI judgment vs execution · the fluency trap · verified-data contract · sponsorship and visa timeline · Snickerdoodle · Humanitarians AI · reallocating scarce effort

[^anthropic]: Judy Hanwen Shen & Alex Tamkin, "How AI Impacts Skill Formation," Anthropic, Feb 3 2026 (arXiv:2601.20245). A randomized controlled trial of engineers learning the Trio asynchronous Python library: the AI-assisted group averaged 50% on the comprehension quiz versus 67% for the hand-coding group (~17 points, ≈ two letter grades), with the largest gap on the debugging questions. High-engagement AI use (asking conceptual questions) scored far higher than delegation use (generate, accept, move on); the mechanism is cognitive engagement, not manual typing.
[^premium]: Validated-AI-skill wage premium (~56%, 2025) from "The Collapse of the Traditional Résumé" (N. Bear Brown), echoing the PwC 2025 Global AI Jobs Barometer; the premium attaches to AI-fluent domain experts, not domain-abandoning career-switchers. **[verify]** the figure against the primary source before publication.
[^screening]: ~82% of companies screen résumés with AI and ~21% auto-reject without human review — "The Collapse of the Traditional Résumé" (N. Bear Brown). **[verify]** against the primary survey.
[^eightfold]: Eightfold AI's match-score learning-manager bias, and *Kistler v. Eightfold* (FCRA: disclose the score, allow disputes), from "The Eightfold AI Match Score" (N. Bear Brown). **[verify]** the litigation specifics before publication.
[^opt]: F-1 post-completion OPT: max 90 aggregate days of unemployment (150 with the STEM OPT extension); exceeding it terminates the record with no grace period. USCIS Policy Manual, Vol. 2, Part F, Ch. 5: https://www.uscis.gov/policy-manual/volume-2-part-f-chapter-5
# Chapter 1 — The Fluency Trap
*What the screen never asks you — and why fluency and correctness stopped being the same thing.*

It is a Tuesday in March, and you are twelve minutes into a take-home assignment for a job you need more than the people interviewing you will ever know. The prompt asks you to clean a dataset and justify your choices. You paste it into the model. Three seconds pass. The answer arrives — complete, formatted, confident. There is a function. There are comments. There is even a short paragraph explaining the reasoning, written in the calm cadence of someone who has done this a hundred times.

You read it. It looks right. It looks, in fact, exactly like what a competent analyst would produce. You run it. It runs. The chart has labels. The nulls are handled. Nothing on the screen is asking you for anything.

So you submit it.

Here is what you cannot see in that moment: whether the model dropped a category of rows that mattered, whether the imputation it chose quietly biased the result toward the answer the hiring manager wants, whether the "reasonable" choice it made is the one a domain expert would have flagged in a sentence. You cannot see it because seeing it is a separate skill from producing it — and producing it is the part you just handed away.

This is the trap. Not failure. Fluency. The first sign of trouble is almost never a crash or an error message or a blank screen. It is a clean output that looks like the work of an expert, produced by a system that has no idea whether it is right, handed to a person who has not yet built the judgment to check.

I want to take that apart, because almost everything that matters about working in the AI era — and almost everything that matters for you specifically, if you are an international student with a visa clock running — lives inside it.

## Two Words Doing Different Jobs

We need to separate two things that the word "work" has been quietly gluing together.

The first is **execution**: producing the artifact. Writing the function, drafting the email, building the slide, generating the SQL, cleaning the rows. Execution is the visible output — the thing that appears on the screen and can be graded, shipped, or submitted.

The second is **judgment**: the decision about whether that artifact should exist, whether it is right, whether it fits the situation in front of you, what it leaves out, and what follows from using it. Judgment is the part that does not appear on the screen. It is the analyst noticing that the "cleaned" dataset threw away every applicant who left one field blank — and that those applicants were disproportionately the ones the model was supposed to find.

For most of the history of work, these two arrived welded together. You could not produce the artifact without exercising at least some judgment along the way, because producing it was slow and manual and full of small decisions. The grind *was* the training. Every junior analyst who hand-cleaned a thousand datasets was, without being told, building the pattern-recognition that would later let them glance at a result and feel that something was off.

AI breaks the weld. It makes execution nearly free and nearly instant, and it leaves judgment exactly as expensive as it ever was. That is the whole event. Not "AI is smart" or "AI is dumb." AI is *fluent* — it produces the surface of competence at a speed and polish no human can match — and fluency and correctness are not the same thing.

Watch how this shows up in how work is actually graded. In courses that permit AI use — because in the real world everyone has the same tools — roughly three-quarters of a typical grade measures procedural competence: did you follow the constraints, meet the technical requirements, use the tools correctly, produce complete and coherent work on time? Everyone with a model can now do that. The remaining fifth or so measures judgment: did you understand the *actual* problem rather than the stated one, what did you decide under ambiguity, would this survive contact with a real stakeholder?[^grading] The first portion has collapsed in value because it has collapsed in scarcity. The second has not, because it cannot be generated.

So the question "can you do the work?" has split into two questions that now have wildly different answers. Can you produce the artifact? Yes — so can everyone, instantly. Can you tell whether the artifact is any good? That is the only question left with a scarce answer. And it is the one the screen never asks you.

![Two aligned stacked bars. The first splits total value into a large procedural-competence base and a smaller judgment cap. The second recuts the same split by supplier — the procedural base is machine-suppliable, the small judgment cap is human-exclusive.](images/01-the-fluency-trap-fig-01.png)
*Figure 1.1 — The value split: who can supply the work*

<!-- → [CHART: two-bar column chart showing the value split — "Procedural competence" (~75-80%) vs "Judgment" (~20-25%) as share of grade/market value; a second panel shows the same split for "Who can supply it" — AI can supply the first bar almost entirely, humans exclusively supply the second; caption should read: "The question 'can you do the work?' has split. One half is now free. The other has not moved."] -->

## Why the Doing Was the Training

Now the mechanism — the part I had to think through several times before it sat still.

If judgment is so valuable, why not just skip the grind and learn judgment directly? Read the textbook, study the patterns, let the machine handle the grunt work, and arrive at the senior-level skill without the thousand tedious repetitions?

Because that is not how the skill forms. And we now have a clean experiment showing it.

In January 2026, Anthropic published a randomized controlled trial — the kind of study where you split people into two groups, change exactly one thing, and watch what happens.[^anthropic] They took fifty-two junior software engineers and had them learn a Python library called Trio that none of them knew. One group could use an AI assistant. The other had to write the code by hand. Same problem, same time, one difference: who did the executing.

Then — and this is the move that makes it an experiment about judgment rather than productivity — they gave everyone the same quiz afterward. Fourteen questions on reading, debugging, and understanding the library. A test not of *can you produce code* but of *do you understand what the code does*.

The hand-coding group averaged 67 percent. The AI-assisted group averaged 50 percent. Seventeen points — close to two letter grades — opened up between two sets of people who had just spent the same amount of time on the same problem.[^anthropic] The only thing that differed was whether a machine did the executing.

Read that result carefully, because the obvious lesson is the wrong one. The hand-coders did not win because typing code by hand is some lost virtue. Typing is not the skill, and the machine is a superb typist — faster and more accurate at producing syntax than any human will ever be. The hand-coders won because writing the code themselves forced them to understand it: to hold the problem in their heads, to test what they wrote, to debug it when it broke. The hand was incidental. The understanding was the point. Take a group that gets that same understanding some other way — and the gap closes.

And here is the detail that turns a finding into a warning. Inside the AI group, behavior split the outcome cleanly. The engineers who used the model to *interrogate* — asking it conceptual questions, challenging its answers, forcing themselves to understand what it produced — scored in the 65-to-86 percent range. The engineers who used it to *delegate* — describe the problem, accept the output, move on — scored in the 24-to-39 percent range.[^anthropic] Same tool. Same task. Opposite result. The variable was not the AI, and it was not who typed. It was whether the human kept checking — reading, questioning, testing — while the machine produced.

That second mode has a name now, and it is worth saying plainly: *vibe-coding*. Prompt, glance, accept, move on. It feels like productivity because the artifact appears and it runs. It is the precise behavior that scored below 40. The discipline this book teaches is its opposite — not "do it by hand," but *check the work*: read what came back, test it, try to break it, validate it against something real, and refuse to ship what you cannot defend. Let the machine type. Keep the checking for yourself.

![Three vertical bars showing comprehension-quiz scores. Hand-coding and AI-plus-interrogation sit at nearly the same height, joined by a faint reference line; AI-plus-delegation drops off sharply. The two high bars share not a typing method but a behavior: the human kept checking.](images/01-the-fluency-trap-fig-02.png)
*Figure 1.2 — The Anthropic RCT: the variable is checking, not typing. Interrogating the model matches writing it yourself; delegating to it — vibe-coding — collapses.*

<!-- → [INFOGRAPHIC: three-column comparison — "Hand-coding" (67% comprehension quiz average), "AI + interrogation" (≥65%), "AI + delegation" (<40%); visual treatment should emphasize that the middle and left columns converge while the right column falls off sharply; caption: "The tool is identical in the middle and right columns. The variable is what the human does while it runs."] -->

That is the mechanism, and it has a name worth carrying: **comprehension debt**. When you let the machine execute and you skip the understanding, you do not avoid the cost of learning. You defer it. You take out a loan against a moment in the future when the system breaks in a way that requires you to understand it — and comprehension debt, like every debt, comes due at the worst possible time, with interest.

The senior engineer and the junior engineer can run the exact same prompt and get opposite trajectories from it. Give a model to someone who already has judgment, and it multiplies them — they read the output, hear the wrong note before the tests catch it, steer and correct. Researchers call that the **AI boost**. Give the same model to someone who has not yet built that judgment, and it produces plausible output they cannot evaluate, the work gets done, and the learning does not happen. That is **AI drag**.[^drag] The tool is identical. The difference is entirely in what the human brings to it — and what they keep doing while it runs.

Sit with the cruelty of that for a second, because it is the center of this book. The boost goes to people who already have judgment. The drag falls on the people still trying to build it. AI does not lift everyone equally. It widens the gap between those who can already tell good from plausible and those who cannot yet — and it does so precisely at the rung where that telling was supposed to be learned.

## The Rung That Got Removed

Step back from the one student at the desk and look at the whole structure.

The traditional path to judgment ran through unglamorous work. You joined as a junior, you did the boilerplate, the cleanup, the first drafts nobody senior wanted to write — and in doing it, over a couple of years, you built the eye. The grunt work was the apprenticeship. It was never efficient. It was how the judgment got made.

That rung is the exact rung AI executes best. Boilerplate code, first-draft memos, routine cleanup, standard analysis — the fluent, common, likely output is precisely what the machine produces at no cost. So the rational short-term move for a company is to stop hiring for it. Why pay a junior to do slowly and imperfectly what the model does instantly?

You can watch the contradiction this creates play out in public. In February 2026, IBM's chief human resources officer, Nickle LaMoreaux, stood up at a summit in New York and announced that IBM would *triple* its entry-level hiring in the United States — including software developers, the very roles "we're being told AI can do."[^ibm] Her argument was not sentimental. It was structural: a company that skips entry-level hiring to save money now will, in three to five years, have no one with the judgment to run the powerful tools it bought, and will have to poach mid-level people from competitors at a premium. The pipeline that produces senior judgment runs through junior work. Cut the bottom rung and you do not get cheaper seniors. You get no seniors.

IBM rewrote the junior role rather than deleting it — less routine coding, more AI oversight, error correction, customer contact, what they called "systems judgment."[^ibm] Read that closely. They did not eliminate the entry-level job. They redefined it as *the judgment part of the job, with the execution stripped out*. The boilerplate went to the machine. What is left for the human, even on day one, is the part the machine cannot do.

This is the inversion that has happened to skilled work across the board. A software engineer used to spend perhaps ninety percent of the day as the musician — fingers on keys, translating intent into syntax, debugging semicolons — and maybe ten percent on judgment, squeezed into the margins. That ratio has flipped. The execution is cheap; the work that is left, and the work that is paid for, is the judgment: what should this system do, does it introduce a risk, is it solving a problem worth solving.[^inversion]

And the market is pricing it exactly that way. As of 2025, AI had moved from a curiosity to a board-level liability: the share of S&P 500 companies naming AI as a *material risk* in their annual filings jumped from 12 percent in 2023 to 72 percent in 2025.[^spx] A material risk is not hype — it is a legal disclosure that this could hurt the company badly enough that shareholders must be warned. Seven hundred of America's largest firms, in the dry language of securities law, are telling their investors that getting the judgment wrong about these fluent machines is a danger to the enterprise. The thing they are afraid of is not that the AI cannot execute. It is that someone will trust a fluent output that was wrong.

![A single rising line across three time points — about 12 percent in 2023, 72 percent in 2025, and 83 percent in the late-2025 update — with the steep first segment emphasized as the moment hype becomes liability.](images/01-the-fluency-trap-fig-03.png)
*Figure 1.3 — AI as material risk: S&P 500 disclosures, 2023–2025*

<!-- → [CHART: line chart, 2023–2025, showing share of S&P 500 companies disclosing AI as material risk in 10-K filings — from 12% to 72% to 83% (Conference Board Dec 2025 update); annotate the 2023→2025 jump with a label reading "hype becomes liability"; caption: "Seven hundred of America's largest companies are telling investors in legal language: trusting the wrong fluent output is an enterprise risk."] -->

## Why This Lands Hardest on You

Now bring the two pictures together — the student at the desk and the structure around them — because at their intersection sits a specific person this book is written for.

If you are an international student in the United States on F-1 status, working under Optional Practical Training, you are standing exactly where the boost and the drag pull hardest in opposite directions, and you are doing it against a clock written into federal law.

Here is the clock. On post-completion OPT, you may accrue no more than ninety cumulative days of unemployment across your entire authorization period. Not business days — calendar days. Weekends count. Holidays count. The counter starts the day your work authorization begins and does not stop. Exceed it, and the Department of Homeland Security terminates your immigration record. There is no grace period. You must leave the country.[^opt] This is why the system at the heart of this book budgets to *eighty* days, not ninety — you want a margin between you and a cliff that does not forgive.

![A single horizontal authorization bar with a filled cumulative-unemployment segment, a dashed marker at 80 days labeled the book's working limit, and a solid hard stop at 90 days where the immigration record is terminated with no grace period.](images/01-the-fluency-trap-fig-04.png)
*Figure 1.4 — The 90-day OPT unemployment clock*

<!-- → [INFOGRAPHIC: timeline diagram showing the 90-day unemployment clock — a horizontal bar representing the OPT authorization period, with a red segment marking cumulative unemployment days, a dashed line at 80 days labeled "this book's working limit," and a hard stop at 90 labeled "DHS terminates record / no grace period"; annotate that weekends and holidays count; caption: "The clock does not distinguish between a Tuesday and a Sunday. It runs."] -->

Now lay the structure on top of that clock. The entry-level rung — the one that used to absorb new graduates and teach them judgment over a patient couple of years — is the rung being automated and, in most companies that are not IBM, quietly removed. The market is paying for judgment you have not yet been given the chance to build. And the most natural response to a ninety-day clock and a wall of rejections is to apply faster — to let the machine generate the cover letters, autofill the applications, produce the take-home in three fluent seconds and submit it. To delegate. To run up comprehension debt at the precise moment you can least afford to have it come due in an interview.

The fluency trap, for you, is not abstract. It is the difference between using these tools as a boost — interrogating, checking, building the judgment that makes you the rare candidate who can tell good from plausible — and using them as a drag, producing fluent applications that look like everyone else's fluent applications, learning nothing, and watching the days tick down.

This is the trade-off named plainly. AI optimizes for the fluent, the common, the likely. That is what it is *for*, and it is genuinely miraculous at it. What it cannot do is supply the salient, the situated, the correct-in-this-particular-case — the judgment about whether the likely answer is the right answer here, for this dataset, this employer, this person whose visa depends on it. Lean on the fluency and skip the judgment, and the tool works beautifully right up until the moment it matters, which is the one moment it cannot help you.

## What the Screen Never Asks

Return to the Tuesday afternoon, the take-home, the answer that arrived in three clean seconds.

Nothing on that screen was wrong, exactly. The code ran. The chart had labels. The reasoning read like competence. The trap was never that the output would look like failure. The trap is that it looks like success — and that the success is the machine's, produced in a register of fluency that asks nothing of you and quietly skips the one contribution only you can make.

So the discipline this entire book is built on starts with a single reflex, and you can begin practicing it this afternoon. When the fluent artifact appears, do not first ask whether it is impressive. Ask what would have to be true for it to be trusted. Ask what the machine could not know — about this dataset, this employer, this situation it has never seen. Ask what you are now responsible for when this leaves the screen and reaches a human who will act on it.

That reflex is judgment. It is the part that does not get cheaper. On a ninety-day clock, with the bottom rung disappearing and the boost flowing to whoever already has the eye, it is also the only thing that reliably separates you from the flood of fluent, identical, unexamined output arriving in every inbox you are trying to reach.

The machine will do the typing — and it is better at it than you are. The checking is yours, and it always was: the judgment about whether the fluent thing on the screen is actually right. The rest of this book is about how to build that judgment on purpose — fast enough to beat the clock.

---

**What Would Change My Mind.** If a replication of the Anthropic trial — or several — found that AI-assisted learners caught up to or surpassed hand-coders on delayed comprehension once they had used the tools for longer, the "comprehension debt" mechanism would need serious revision: it would mean the debt is repaid by familiarity rather than compounding. The current evidence is one well-designed but small (n = 52) study; one study is a finding, not a law.

**Still Puzzling.** I do not fully understand where the line sits between *interrogating* a model and *delegating* to it in real practice. The trial shows the two produce opposite outcomes, but a working analyst does both within the same hour, often within the same prompt. I do not yet know how to teach someone to feel which skill they are in while they are in it — and that, not the statistics, may be the hardest thing this book has to do.

---

## Chapter 1 Exercises: The Fluency Trap

**Project:** Your Own Reallocation Engine

**This chapter adds:** the foundation of your engine — the judgment frame it runs on. Before you collect a single record, you set up the project, write the interrogation reflex into it as a standing rule, and open the "what the machine could not know" log that every later chapter will feed.

---

### Exercise 1 — When to Use AI

**The judgment:** In this chapter's work, AI assistance is appropriate for the following tasks:

- **Drafting the scaffolding of your project's founding documents.** — *Why AI works here:* a README, a folder layout, a checklist template are reformatting and boilerplate generation; you can read every line and judge whether it says what you mean.
- **Generating a first-pass list of interrogation questions to ask of any fluent output.** — *Why AI works here:* this is option generation — the model proposes candidate questions, and you, holding the chapter's execution/judgment distinction, keep the ones that actually probe correctness.
- **Explaining a concept you half-understand back to you in three different framings.** — *Why AI works here:* this is the *interrogation* mode the Anthropic trial rewarded; you are using the model to build judgment, not to skip it, and you verify by trying to re-explain it yourself.

**The tell:** You know you are using AI appropriately when you can evaluate the output — when you have independent criteria to judge whether it is correct, complete, and fit for purpose. In this chapter the criterion is: can you re-explain it without the model in front of you?

---

### Exercise 2 — When NOT to Use AI

**The judgment:** In this chapter's work, the following tasks require human judgment. Delegating them to AI is not appropriate — not because AI cannot produce output, but because AI output in these cases cannot be trusted without verification that requires the same expertise as doing the task yourself.

- **Deciding what your engine is actually for and what "a good outcome" means for you.** — *Why AI fails here:* this is a values-and-stakes judgment tied to your visa clock, your field, and your risk tolerance — facts the model does not have and would fabricate plausibly if asked.
- **Submitting any take-home or assessment the model produced that you cannot defend line by line.** — *Why AI fails here:* this is the chapter's central trap — fluent output you cannot evaluate is comprehension debt, and the interview is where it comes due, with interest.
- **Judging whether you are interrogating or delegating in a given session.** — *Why AI fails here:* the model cannot see your learning; only you can notice whether you understood the output or merely accepted it.

**The tell:** You know you have crossed the line when you are using AI output as your reason for a conclusion rather than as a tool for reaching one. If you could not explain the conclusion without the AI, the AI did the work that should have been yours.

**Series connection:** This exercise trains **Tier 4 (Metacognitive supervision)** — the capacity to monitor your own understanding and to distinguish a fluent surface from a grasped mechanism. The whole book's spine is this tier; Chapter 1 installs it before any tool is picked up.

---

### Exercise 3 — LLM Exercise

**What you're building this chapter:** the founding charter of your engine — a one-page "What the machine cannot know about my search" document plus a reusable interrogation checklist — the first entry in the account that becomes your final deliverable.

**Tool:** Claude (claude.ai chat). A Claude Project is worth starting now if you'll run the whole book here — put the charter in the project knowledge so every later chat inherits your stakes.

**The Prompt:**

```
I am building a personal job-search "reallocation engine" over the course of a
book, and this is the founding step. Help me draft two short documents. Ask me
nothing you can infer; where you need a fact about my situation that you do not
have, insert a clearly marked [FILL IN] placeholder rather than inventing it.

Document 1 — "What the machine cannot know about my search" (about half a page):
a plain-language list of the things an AI scorer or chatbot structurally cannot
know about my job search — for example, private information about specific
employers, my own deadline pressure, which mission I can speak about with
conviction, what a particular rejection actually meant. Frame each as a
one-line reminder I will re-read whenever I'm tempted to trust a fluent answer.

Document 2 — "Interrogation checklist" (6–10 questions): a reusable list of
questions I should ask of ANY fluent AI output before I act on it, grounded in
the distinction between producing an artifact and judging whether it is correct.
Include at least one question about what the output left out, one about what it
would take to verify it, and one about what I become responsible for once I pass
it to a human.

Output both as clean markdown I can save. Do not pad with motivation.
```

**What this produces:** two markdown documents — `what-the-machine-cannot-know.md` and `interrogation-checklist.md` — that seed your project and that you will literally reuse in every later validation exercise.

**How to adapt this prompt:**
- *For your own project:* fill the `[FILL IN]` placeholders with your real field, visa timeline, and target sector before saving. The charter is worthless generic and sharp when specific.
- *For ChatGPT / Gemini:* works as-is; both tend to add a pep-talk intro — append "no preamble, start with the first document's heading."
- *For a Claude Project:* paste the finished charter into the project's custom instructions so it constrains every future answer.

**Connection to previous chapters:** this is the first exercise — it establishes the judgment frame the rest build on.

**Preview of next chapter:** Chapter 2 turns this frame into a time budget — you'll build the 3-3-2 plan and the target list your engine actually runs against.

---

### Exercise 4 — CLI Exercise

**What you're building this chapter:** the skeleton of your project repository — the folders, a `JUDGMENT_LOG.md`, and a `CLAUDE.md` seeded with the interrogation rule so the rule binds every future agentic session.

**Tool:** Claude Code. Scaffolding a directory, creating several files, and seeding a persistent instruction file is a multi-file setup task that suits an agentic CLI over chat.

**Skill level:** Beginner — this is your first terminal exercise; it creates files and does not touch data.

**Setup:**

Before running this exercise, confirm:
- [ ] You have a folder where your engine will live, and Claude Code can open it.
- [ ] You saved the two documents from Exercise 3 (you'll move them into the repo).
- [ ] You have decided nothing destructive runs without your say-so (you'll state this in the task).

**The Task:**

```
Create the starting structure for a personal job-search project in this folder.
Do not delete or overwrite anything that already exists — if a file is present,
stop and show me before changing it.

1. Create these folders: data/, recipes/, reports/, notes/.
2. Create JUDGMENT_LOG.md with a short header and one empty dated template entry
   with fields: Date, What I asked AI to do, Interrogation/Delegation (which was
   it?), What the machine could not know, What I verified myself.
3. Create CLAUDE.md containing a single standing rule, stated plainly:
   "Before trusting any count, claim, or recommendation in this project, run the
   check that produces it and read the output. Never accept an invented number.
   Label anything that is AI judgment rather than a counted fact."
4. Move my two files (what-the-machine-cannot-know.md and
   interrogation-checklist.md) into notes/ if they are in this folder.
5. Print the resulting file tree and the contents of CLAUDE.md so I can confirm.

Stop after step 5.
```

**Expected output:** a project tree with four folders, a `JUDGMENT_LOG.md` template, a `CLAUDE.md` carrying the interrogation rule, and your two charter files filed under `notes/`.

**What to inspect in the output:** read `CLAUDE.md` back — is the rule stated as an instruction the agent will actually follow, or as vague aspiration? Confirm nothing pre-existing was overwritten.

**If it goes wrong:** the most common failure is the agent creating files at the wrong path (e.g. a nested duplicate folder). Recover by asking it to print the absolute path of each file it created and move any misplaced ones; do not let it "clean up" by deleting without showing you first.

**CLAUDE.md / AGENTS.md note:** this exercise *is* the CLAUDE.md note — you are establishing the project's first standing rule. Every later chapter adds to this file; Chapter 3 will tighten this rule into the full verified-data contract.

---

### Exercise 5 — AI Validation Exercise

**What you're validating:** a fluent, confident take-home solution of exactly the kind the chapter opens with — code that runs clean and is quietly wrong.

**Validation type:** Code (with a reasoning-chain component).

**Risk level:** High — it runs without errors, which is precisely what makes the flaw invisible to anyone who only checks whether it executes.

**Setup (pre-generated artifact — option b):** This chapter's lesson is that fluent output looks like success, so validate this pre-generated artifact rather than something you wrote. An AI was asked to "clean this applicant dataset and justify your choices":

> ```python
> # Clean the applicant dataset: drop incomplete records, then summarize.
> import pandas as pd
> df = pd.read_csv("applicants.csv")
> df_clean = df.dropna()          # remove rows with any missing values
> rate = (df_clean["passed_screen"].mean())
> print(f"Cleaned {len(df_clean)} of {len(df)} rows.")
> print(f"Screen pass rate: {rate:.1%}")
> ```
> *Justification (model-written):* "I removed incomplete records to ensure data
> quality, then computed the screen pass rate on the clean data. The code runs
> without errors and handles nulls appropriately."

**The Validation Task:**

Evaluate the AI output above using the following checklist. For each item, record: Pass / Fail / Cannot determine — and explain your reasoning.

```
Validation Checklist — The Fluency Trap

□ Correctness: Does "runs without errors" mean the result is correct?
  What does dropna() across ALL columns do to applicants who left one optional
  field blank?
□ Completeness: What did the justification leave out?
  Does it report HOW MANY rows were dropped, or which kind of applicant they
  were?
□ Scope: Did the AI answer the actual question or a convenient version of it?
  The task said "justify your choices" — is dropping all incomplete rows a
  justified choice, or an unexamined default?
□ Silent bias (chapter-specific): If applicants who skipped an optional field
  are disproportionately the ones the screen was meant to surface, what does
  dropping them do to the pass rate?
□ Defensibility (chapter-specific): Could you explain and defend this cleaning
  choice in an interview, line by line, without the model?
□ Failure mode check: Does this output exhibit any of the following?
  - Fluent but wrong (a clean, confident result that is quietly biased)
  - Comprehension debt (output you would submit but could not reconstruct)
  - Missing ground truth (no check on whether the dropped rows mattered)
```

**What to do with your findings:**
- If the output passes all checks: use it. (It will not — `dropna()` across all columns is the trap.)
- If the output fails one check: rewrite the prompt to ask which rows are dropped and why, re-run, and re-validate.
- If the output fails multiple checks or you cannot determine pass/fail: this is a "When NOT to Use AI" moment — do the cleaning decision yourself and let the model only format the result.

**AI Use Disclosure prompt:**
After completing this validation, write a two-sentence AI Use Disclosure:
> *Sentence 1:* What AI produced in this exercise and how you used it.
> *Sentence 2:* One specific thing the AI could not determine that required your judgment.

**Series connection:** This exercise trains **Tier 4 metacognitive supervision** — catching fluent-but-wrong output by asking what the clean result concealed. It is the reflex the entire book is built to install: the difference between code that runs and code that is right.

---

**Tags:** #fluency-trap #execution-vs-judgment #comprehension-debt #OPT-90-day-clock #AI-and-entry-level-work

[^grading]: Grading split (≈75–80% procedural / 20–25% judgment) drawn from "The Job Apocalypse (Not Yet): Thinking Has Become the Job" (uploaded essay, N. Bear Brown). **[verify]** — locate the primary syllabus/rubric data this figure summarizes before publication; currently sourced to the author's own essay, not an external study.

[^anthropic]: Judy Hanwen Shen & Alex Tamkin, "How AI Impacts Skill Formation," Anthropic, Feb 3 2026 (arXiv:2601.20245, https://arxiv.org/abs/2601.20245); plain-language summary at https://www.anthropic.com/research/AI-assistance-coding-skills. A randomized controlled trial of 52 (mostly junior) engineers learning the Trio asynchronous Python library: the AI-assisted group averaged 50% on the comprehension quiz versus 67% for the hand-coding group (~17 points, ≈ two letter grades), with the largest gap on the debugging questions. The study reports substantial heterogeneity *within* the AI group: high-engagement usage (asking conceptual questions, requesting explanations alongside generated code) scored 65–86%, while delegation usage (generate code, accept, move on) scored 24–39%. The mechanism is cognitive engagement, not manual typing — Anthropic's own recommendation is to use AI in ways that keep the engineer "cognitively engaged," preserving debugging and validation skill. Hand-coding and interrogation both force understanding; delegation does not.

[^drag]: "AI boost" / "AI drag" framing attributed to Mark Russinovich and Scott Hanselman, via "The Ladder That Isn't There" (uploaded essay, N. Bear Brown). **[verify]** — trace to the original Russinovich/Hanselman source before publication.

[^ibm]: IBM to triple US entry-level hiring in 2026, announced by CHRO Nickle LaMoreaux at Charter's Leading with AI Summit, Feb 12 2026; roles recast toward AI oversight, error correction, customer contact, and "systems judgment." Fortune, Feb 13 2026: https://fortune.com/2026/02/13/tech-giant-ibm-tripling-gen-z-entry-level-hiring-according-to-chro-rewriting-jobs-ai-era/

[^inversion]: The "90% musician → 90% judgment" inversion is developed in "The Inversion: Why Software Engineers Are Becoming Judgment Workers" (uploaded essay, N. Bear Brown).

[^spx]: Share of S&P 500 companies disclosing AI as a material risk rose from 12% (2023) to 72% (10-K filings through Aug 15 2025), per The Conference Board / ESGAUGE. Fortune, Oct 8 2025: https://fortune.com/2025/10/08/sp-500-companies-disclosed-ai-risk-10-k-forms-reputation-risk/. A December 2025 update put the figure at 83%: https://www.conference-board.org/press/governing-AI-2026

---

## Prompts

### Figure 1.1 — The value split: who can supply the work
**Files:** ../images/01-the-fluency-trap-fig-01.svg · ../d3/01-the-fluency-trap-fig-01.html
**Prompt:** Two aligned stacked bars on white, the same value split recut by a second question. Render procedural competence as a tall neutral-gray base and judgment as a small cap in the one red accent; align the segment boundary across both bars with a dashed ink rule, zero baseline anchored.

### Figure 1.2 — The Anthropic RCT: the variable is checking, not typing
**Files:** ../images/01-the-fluency-trap-fig-02.svg · ../d3/01-the-fluency-trap-fig-02.html
**Prompt:** Three vertical bars on white at zero baseline — hand-coding and AI-plus-interrogation near-level, AI-plus-delegation dropping off a cliff. Title the chart so the lesson is unmistakable: what the two high bars share is checking, not a typing method. Keep the high bars in neutral ink-gray, let the convergence read through a faint dashed reference line, and reserve red for the one engaged-AI bar; subtitle names delegation as vibe-coding.

### Figure 1.3 — AI as material risk: S&P 500 disclosures, 2023–2025
**Files:** ../images/01-the-fluency-trap-fig-03.svg · ../d3/01-the-fluency-trap-fig-03.html
**Prompt:** A single ascending line across three time points on a zero-anchored percent axis, nodes marked in ink. Draw the line in the one red accent and emphasize the steep first segment where hype becomes liability with a soft ochre slope band, gridlines as faint border hairlines only.

### Figure 1.4 — The 90-day OPT unemployment clock
**Files:** ../images/01-the-fluency-trap-fig-04.svg · ../d3/01-the-fluency-trap-fig-04.html
**Prompt:** One horizontal authorization bar on white with uniform day ticks, a dashed ink marker at the 80-day working limit and a solid red hard stop at 90 days. The 80-to-90 gap reads as a deliberate safety margin; no calendar or clock imagery, the bar and its two markers carry all the meaning.
# Chapter 2 — The Reallocation Principle
*Why the most disciplined job search strategy in the room is usually the most broken one.*

Here is a number I want you to hold: **54%**.

In 2025, roughly 54% of hires came through personal connections rather than through a cold application.[^connections] More than half. Sit with that for a moment, because the implication is structural, not motivational. The market is not rewarding effort distributed evenly across all channels. It is rewarding effort concentrated in specific ones. And the channel that produces more than half of all hires is not the channel that feels most like work.

I want to show you why that is, and why it is almost impossible to act on without first understanding the machinery behind it.

---

The applicant I have in mind is not a slacker. They are awake at eight, coffee cooling beside a browser with seventeen open tabs, and they apply. By noon the counter reads thirty. By end of day, forty-one. They do this five days a week. The spreadsheet is color-coded and meticulous. Five hundred applications in a month, almost all to companies you would recognize from a billboard.

This person has optimized hard — for the wrong variable.

Here is what the spreadsheet cannot show. By 2025, around 82% of companies were screening résumés with software, and roughly one in five rejected candidates automatically, with no human in the loop.[^screening] A large fraction of the postings were not even real openings — somewhere between a quarter and 42% of listings at any given moment are "ghost jobs," postings the company has no active intent to fill.[^ghost] Every hour spent clicking Submit was an hour not spent on the two activities that actually move the needle.

The question worth asking is: why does the volume strategy persist? Why does anyone — smart, hardworking, data-literate — continue doing something the numbers have quietly stopped rewarding?

The answer has to do with what feedback looks like in a broken system. Volume produces a counter. The counter goes up. The counter going up feels like progress. Networking and portfolio work produce nothing for days, then suddenly produce a conversation, which may eventually produce an offer. The feedback loop is delayed and nonlinear, which means our instincts misread it. We reach for the activity that generates immediate, legible signal — the number — and we call it discipline.

What we are actually doing is optimizing for throughput in a channel that has been quietly devalued by the very automation we learned to use.

![Three vertical bars on a zero baseline — cold application near 0.2 percent reads as a thin sliver beside employee referral at 2 to 4 percent and direct network introduction at 5 to 10 percent, preserving the order-of-magnitude gap.](images/02-the-reallocation-principle-fig-01.png)
*Figure 2.1 — Conversion rate by channel*

<!-- → [CHART: bar chart comparing conversion rates across three channels — cold application (~0.2%), employee referral (~2–4%), direct network introduction (~5–10%) — student should see the order-of-magnitude gap between channels, not just the absolute numbers] -->

---

The asymmetry in conversion rates is the crux of this. A referred candidate is several times more likely to convert than an inbound one — cold applications convert at something like 0.2%, while a warm referral can convert at rates an order of magnitude higher.[^referral] When you combine that with the 54% figure, the arithmetic of the typical job search becomes almost painful to look at.

If you have eight hours, and you spend all eight applying cold, you are concentrating all of your effort in the channel that produces less than half of hires at the lowest conversion rate in the system. You are not unlucky. You are mathematically misallocated.

This is not a motivational observation. It is a resource-allocation problem. And resource-allocation problems have a structural solution: stop distributing effort by habit and start distributing it by expected return.

The expected return on an hour is not constant across activities. An hour of targeted networking reaches into the 54% channel. An hour building a portfolio piece creates verifiable evidence of capability — and in 2025, workers with validated AI skills were commanding something like a 56% wage premium over peers who only claimed equivalent skills.[^premium] An hour of cold applying, by contrast, feeds a machine that discounts most of what you send it before a human reads a word.

Once you see the return structure, the reallocation is obvious. Two hours applying — targeted, filtered, not sprayed. Three hours networking. Three hours on portfolio. I call this the 3-3-2 day, and the rest of this book is built to make it actually achievable rather than just strategically correct.

![Three proportional columns on a common baseline — a short two-hour applying column beside two taller three-hour columns for networking and portfolio, with the networking column tied to the 54 percent hire-via-connections figure and the portfolio column to the 56 percent validated-skill premium.](images/02-the-reallocation-principle-fig-02.png)
*Figure 2.2 — The 3-3-2 day*

<!-- → [INFOGRAPHIC: three-column layout showing the 3-3-2 split — "2 hrs: Targeted Applying," "3 hrs: Networking," "3 hrs: Portfolio" — with the 54% and 56% figures anchored to the networking and portfolio columns respectively] -->

---

Let me be precise about what 3-3-2 is doing, because there is a version of this argument that sounds like "apply less," and that is not it.

The two hours of applying are not a ceiling on ambition. They are a forcing function for quality. If you can only apply to roles for two hours, you apply to fewer roles. That means you must filter more aggressively before you apply. And that filtering — knowing which roles are real, which companies have any history of sponsoring the visa type you need, which postings match what you can actually demonstrate — is where most of the signal lives anyway.

The machine I am building across the next several chapters is designed to compress that filter into something fast. The goal is not fewer applications as an end in itself. The goal is: make two hours of targeted applying produce more movement than eight hours of spray-and-pray did — and then use the reclaimed six hours on the channels the data says to use.

This is the reallocation principle in one sentence: **spend effort where the return is, not where the feedback is.**

---

There is a worked example worth walking through, because the principle is easy to endorse and hard to execute.

A master's graduate on OPT, three months into a search, switches strategies mid-stream. Week one of the old approach: forty hours, roughly two hundred applications to brand-name firms. Four auto-acknowledgements, one recruiter screen, zero onsites. Several of those companies, it turns out, had near-zero history of sponsoring the visa type needed — so even the "successful" applications were dead on arrival.

Week one of 3-3-2: ten hours applying — about twenty-five targeted applications, each to a company pre-checked for sponsorship history and a live posting. Fifteen hours networking — twelve outreach messages, four informational conversations, two of which produced referrals into the 54% channel. Ten hours portfolio — one deployed project with real metrics, written up.

Fewer applications. More movement.

The mechanism is not magic. The referrals work because they bypass the parser. The portfolio piece works because it converts a claim into evidence. The targeted applications work because they are aimed at companies that can actually act on them.

| Measure | Spray-and-pray week | 3-3-2 week |
|---|---|---|
| Hours spent | 40 | 35 |
| Applications sent | ~200 | ~25 |
| Recruiter screens | 1 | (rolling from referrals) |
| Referrals generated | 0 | 2 |
| Informational conversations | 0 | 4 |
| Portfolio pieces completed | 0 | 1 |
| Estimated pipeline value | Low — most applications dead on arrival | High — two warm referrals into the 54% channel |

*Table 2.1 — The same week, two strategies: fewer applications, more movement. The left column wins only on raw volume; the right column wins on every outcome that matters.*

![Two job-search weeks compared row by row with paired horizontal bars — the spray-and-pray week wins only on raw application count, while the 3-3-2 week wins on recruiter screens, referrals, and portfolio pieces.](images/02-the-reallocation-principle-fig-03.png)
*Figure 2.3 — Spray-and-pray vs. 3-3-2: the input-output flip*

---

Now I want to tell you something the 3-3-2 day cannot know.

A scorer — any algorithm — can tell you a role appears low-value and should be skipped. It cannot know that the hiring manager is your former professor's co-founder. It cannot know that the company whose posting scores mediocre is the one organization whose mission you can speak about with genuine conviction in a room, which is worth something the number ignores. It cannot know that you are three weeks from a visa deadline, which changes the entire calculus of which channel can close fast enough to matter.

The reallocation principle is a default for where returns *usually* lie. The person operating it is the one who holds private information the model cannot access. Override the default when you have a reason. Follow it when you don't.

This matters because there is a failure mode on both ends. The applicant who ignores the principle and keeps spraying is the one we started with — disciplined, misallocated, watching the counter go up. But the applicant who treats 3-3-2 as a ritual and never deviates is making a different mistake: substituting a heuristic for judgment. The whole argument of this book is that judgment is what you bring, and the tools are what handle the parts that do not require it.

![A top-to-bottom decision tree for a freed hour — first gate routes to networking if fewer than about ten live conversations are going, second gate routes to portfolio if no deployed metric-bearing project exists from the last ninety days, and only when both are healthy does the hour go to additional targeted applications.](images/02-the-reallocation-principle-fig-04.png)
*Figure 2.4 — Where does a freed hour go?*

<!-- → [DIAGRAM: decision tree for "where does a freed hour go?" — branch: fewer than ~10 live conversations → send to networking; portfolio has no deployed metric-bearing project from last 90 days → send to portfolio; both healthy → additional targeted applications; student should see this as a rule, not a preference] -->

---

There is one more piece of the reallocation puzzle that does not show up in time budgets: the skip.

A skip is a deliberate decision not to apply to a role you would otherwise have applied to. I am going to argue throughout this book that the skip is a first-class action — not a failure, not laziness, but a resource-allocation decision with the same weight as apply.

The freed time from a skip does not go back into applying to a different marginal role. The whole point of the filter is to catch marginal roles before they consume your two applying hours. When the filter fires and you do not apply, the freed time goes to networking if you have fewer than about ten live conversations going, and to portfolio if you have not deployed a metric-bearing project in the last ninety days. Only after both of those are healthy does a freed hour go back into more targeted applications.

The rule exists to stop the volume instinct from quietly reclaiming the time the filter just saved. Because it will try. The counter is seductive. "I have a free half-hour, I could just send one more application" is the volume instinct speaking in its most reasonable voice.

The answer is: no, you couldn't. That half-hour is already spent. You just haven't decided where yet.

---

By the end of this chapter, you should be able to explain — not just agree with — why volume is the wrong optimization target in the current market. You should be able to map the return structure across the three channels and defend a personal time allocation against expected return. And you should be able to write a 3-3-2 plan that names the times, names the networking actions, and names the portfolio piece in progress.

What you do not yet have is a filter trustworthy enough to actually skip on. That is the next problem. A reallocation strategy built on a filter you can't trust is just a different way of guessing. The question the next chapter forces is: what would make a claim about a role's value reliable enough to act on?

[^screening]: AI résumé-screening and auto-rejection rates (~82% screen with AI; ~21% auto-reject) from "The Collapse of the Traditional Résumé" (uploaded essay, N. Bear Brown). **[verify]** — trace to primary survey before publication.

[^ghost]: Ghost-job rate (≈28–42% depending on source/month) from "What Is a Ghost Job?" and "Can AI Help Detect Ghost Jobs?" (uploaded essays, N. Bear Brown), citing standstill rates held ~28–38% over five years. **[verify]** — trace to the underlying labor-market reports.

[^connections]: ~54% of 2025 hires via personal connections — "The 3-3-2 Split" (uploaded essay, N. Bear Brown). **[verify]**

[^referral]: Referral vs. cold-application conversion (referrals several-fold higher; cold ≈0.2%) — "The 3-3-2 Split." **[verify]** — the "4–10× more likely" figure appears in the plain-summary and must be source-cited.

[^premium]: ~56% wage premium for validated AI skills (2025) — "The Collapse of the Traditional Résumé." **[verify]**

---

## Chapter 2 Exercises: The Reallocation Principle

**Project:** Your Own Reallocation Engine

**This chapter adds:** the operating policy your engine enforces — a 3-3-2 time budget, an initial target list filtered by expected return, and the skip logged as a first-class action. This is the decision layer the later data pipelines will feed.

---

### Exercise 1 — When to Use AI

**The judgment:** In this chapter's work, AI assistance is appropriate for the following tasks:

- **Drafting outreach and informational-interview messages for the networking block.** — *Why AI works here:* this is drafting against a template you can read and personalize; you judge fit, the model handles the first pass.
- **Reformatting your week's logged hours into an apply/network/portfolio tally.** — *Why AI works here:* this is summarizing structured data you supply — pure reformatting, instantly checkable against your own log.
- **Generating candidate target companies in a sector, as a starting list to verify.** — *Why AI works here:* the model proposes; you treat the list as leads, not facts, and every name gets checked in later chapters before it earns an application.

**The tell:** You know you are using AI appropriately when you can evaluate the output — when you have independent criteria to judge whether it is correct, complete, and fit for purpose. Here: does the message sound like you, and is every suggested company something you will verify before applying?

---

### Exercise 2 — When NOT to Use AI

**The judgment:** In this chapter's work, the following tasks require human judgment. Delegating them to AI is not appropriate — not because AI cannot produce output, but because AI output in these cases cannot be trusted without verification that requires the same expertise as doing the task yourself.

- **Deciding your actual time allocation given your deadline and network.** — *Why AI fails here:* this is a stakes-weighted resource decision; the model cannot know your unemployment-day count, your live conversations, or your risk tolerance, so any split it recommends is a guess dressed as advice.
- **Deciding whether to override the 3-3-2 default in a specific case.** — *Why AI fails here:* overrides exist precisely because *you* hold private information the model cannot access — the hiring manager who is your professor's co-founder, the mission you can speak to with conviction.
- **Accepting an AI list of "best companies to apply to" as a reason to apply.** — *Why AI fails here:* it has no sponsorship history, no ghost-job check, no live-posting signal; trusting it reintroduces the volume instinct the chapter warns against.

**The tell:** You know you have crossed the line when you are using AI output as your reason for a conclusion rather than as a tool for reaching one. If you could not explain the conclusion without the AI, the AI did the work that should have been yours.

**Series connection:** This exercise trains **Tier 7 (Wisdom — values and accountability)**, with a Tier 4 edge. Where to spend a scarce hour against a federal deadline is a judgment about your own stakes; no scorer can own that decision, because no scorer bears its consequences.

---

### Exercise 3 — LLM Exercise

**What you're building this chapter:** your concrete 3-3-2 plan and a first target list — the policy document and candidate set your engine will run against from here forward.

**Tool:** Claude (claude.ai chat). Use a Claude Project if you want the plan to persist as context for later chapters.

**The Prompt:**

```
Help me build a job-search time-allocation plan based on the "3-3-2" principle:
spend effort where the expected return is, not where the feedback is. The
return structure I'm working from: roughly 54% of hires come through personal
connections; cold applications convert near 0.2% while referrals convert far
higher; most application time is wasted on ghost jobs and auto-rejection. So the
default day is ~2 hours targeted applying, ~3 hours networking, ~3 hours
portfolio.

Do three things. Where you need a fact about me you don't have, use a clearly
marked [FILL IN] placeholder — do not invent my schedule, network size, or
target sector.

1. Draft a one-day 3-3-2 plan with NAMED time blocks (actual clock hours),
   three specific networking actions, and one portfolio piece in progress.
2. Write the "freed-hour rule": when I skip a low-value role, where does the
   reclaimed time go? Encode this as an explicit if/then I can follow without
   re-deciding each time (hint: networking if I have fewer than ~10 live
   conversations; portfolio if no deployed metric-bearing project in 90 days;
   only then more targeted applications).
3. Give me a target-list TEMPLATE (as a markdown table) with columns for
   company, why-it's-a-lead, and a blank column for each verification I'll add
   in later chapters: sponsorship history, funding recency, posting liveness,
   role quality. Pre-fill 5 example rows in my [FILL IN] sector as leads only,
   clearly marked "unverified."

Output as clean markdown. No motivational filler.
```

**What this produces:** a `332-plan.md` with a dated plan and an explicit freed-hour rule, and a `targets.md` table seeded with unverified leads and empty verification columns — the spine your later pipelines populate.

**How to adapt this prompt:**
- *For your own project:* replace every `[FILL IN]` with your real sector, hours, and network state. Keep the "leads only, unverified" labeling — it stops you treating the model's list as a result.
- *For ChatGPT / Gemini:* works as-is; on both, add "use a real markdown table, not a bulleted list" to keep the target template machine-usable.
- *For a Claude Project:* store the freed-hour rule in the project instructions so future chats enforce it automatically.

**Connection to previous chapters:** the target table's "why-it's-a-lead" column is where you apply Chapter 1's interrogation reflex — every lead is a fluent suggestion until verified.

**Preview of next chapter:** Chapter 3 makes "verified" mean something specific — you'll fork the engine and run the contract that decides which of these leads survive.

---

### Exercise 4 — CLI Exercise

**What you're building this chapter:** a machine-readable target list and a simple skip log in your project repo, so decisions are recorded rather than remembered.

**Tool:** Cowork (or Claude Code). The task reads your plan and writes structured files across the project directory — a file-organization job that suits Cowork's workspace handling.

**Skill level:** Beginner — file creation and a small reformat; no data pipelines yet.

**Setup:**

Before running this exercise, confirm:
- [ ] The project repo from Chapter 1 exists (with `data/`, `notes/`, `recipes/`).
- [ ] You have the `targets.md` table and `332-plan.md` from Exercise 3.
- [ ] You have decided your skip-rate target (the book argues for ≥50%).

**The Task:**

```
In my project repo, turn my planning notes into tracked files. Do not invent any
company data — only restructure what I provide.

1. Read notes/targets.md (my unverified leads table).
2. Create data/targets.csv with these columns: company, source_of_lead,
   sponsorship_status, funding_recency, posting_live, role_quality, decision.
   Fill company and source_of_lead from my notes; leave every verification
   column and decision blank (later chapters fill them).
3. Create reports/SKIP_LOG.md with a dated-entry template: company, date,
   reason for skip, where the freed hour went. Add one header line stating my
   skip-rate target.
4. Print targets.csv and the SKIP_LOG template so I can confirm the columns.

Do not apply to anything, do not contact anyone, do not fill verification
columns with guesses. Stop after step 4.
```

**Expected output:** `data/targets.csv` with named leads and empty verification columns, plus `reports/SKIP_LOG.md` ready to record decisions.

**What to inspect in the output:** open `targets.csv` — are the verification columns genuinely blank (not auto-filled with the model's guesses)? A pre-filled "sponsorship_status: likely" is exactly the contract violation Chapter 3 forbids.

**If it goes wrong:** the most likely failure is the agent helpfully "completing" the verification columns from its training data. Recover by instructing it to blank every column except company and source, and re-print; treat any auto-filled value as untrusted.

**CLAUDE.md / AGENTS.md note:** add a standing rule — *"`targets.csv` verification columns may only be filled by a script that reads a public record and writes an audit; never by model inference."* This pre-commits your repo to the verified-data contract before you even build the pipelines.

---

### Exercise 5 — AI Validation Exercise

**What you're validating:** an AI-generated job-search strategy recommendation — the kind that sounds disciplined and quietly optimizes the wrong variable.

**Validation type:** Reasoning chain.

**Risk level:** Medium — wrong strategy here doesn't crash anything; it just burns days you can't get back on a federal clock.

**Setup (pre-generated artifact — option b):** This chapter's lesson is that the volume instinct hides inside reasonable-sounding advice, so validate this pre-generated recommendation:

> **Your job-search plan.** To maximize your chances, apply to as many roles as
> possible — aim for 25–30 applications per day across all major job boards.
> Consistency is what gets results: candidates who apply daily get the most
> responses. Use AI to auto-fill applications and generate tailored cover
> letters at scale so volume doesn't cost you quality. Networking is helpful but
> slow, so treat it as a secondary activity once your application numbers are up.
> With 500+ applications a month, the law of large numbers is on your side.

**The Validation Task:**

Evaluate the AI output above using the following checklist. For each item, record: Pass / Fail / Cannot determine — and explain your reasoning.

```
Validation Checklist — The Reallocation Principle

□ Correctness: Does the advice optimize for return or for feedback?
  Does "apply to as many as possible" target the channel that produces >half of
  hires, or the lowest-converting one?
□ Completeness: What does it ignore?
  Where are ghost jobs, AI auto-rejection, and sponsorship history in this plan?
□ Scope: Did it answer "how do I get hired" or "how do I feel busy"?
  Is "the counter going up" being mistaken for progress?
□ Channel allocation (chapter-specific): Does relegating networking to
  "secondary" match the 54% / 0.2% numbers, or contradict them?
□ Stakes handling (chapter-specific): For someone on a 90-day unemployment
  clock, is 500 cold applications/month a defensible use of scarce time?
□ Failure mode check: Does this output exhibit any of the following?
  - Fluent but wrong (disciplined-sounding advice that targets the wrong metric)
  - Volume instinct (mistaking legible activity for expected return)
  - Missing ground truth (no base rate for how often cold applications convert)
```

**What to do with your findings:**
- If the output passes all checks: follow it. (It will not — it inverts the chapter's central argument.)
- If the output fails one check: rewrite it yourself as a 3-3-2 plan and note exactly which claim you rejected and why.
- If the output fails multiple checks or you cannot determine pass/fail: this is a "When NOT to Use AI" moment — allocation is your call, made from your stakes.

**AI Use Disclosure prompt:**
After completing this validation, write a two-sentence AI Use Disclosure:
> *Sentence 1:* What AI produced in this exercise and how you used it.
> *Sentence 2:* One specific thing the AI could not determine that required your judgment.

**Series connection:** This exercise trains **Tier 7 wisdom** — the judgment to reject confident advice that ignores your stakes and the real return structure. It is the difference between an engine that allocates effort and a counter that just goes up.

---

## Prompts

### Figure 2.1 — Conversion rate by channel
**Files:** ../images/02-the-reallocation-principle-fig-01.svg · ../d3/02-the-reallocation-principle-fig-01.html
**Prompt:** Three vertical bars on white at a zero baseline, scaled so the order-of-magnitude gap reads honestly — cold application a near-flat sliver beside referral and direct introduction. Render the devalued cold-application bar in the one red accent and keep referral and direct introduction in neutral ink-gray so the eye lands on what the chapter devalues.

### Figure 2.2 — The 3-3-2 day
**Files:** ../images/02-the-reallocation-principle-fig-02.svg · ../d3/02-the-reallocation-principle-fig-02.html
**Prompt:** Three proportional columns on a common baseline sized strictly two-three-three for applying, networking, and portfolio. Keep the columns in neutral grays with a single red accent marking the networking column as the high-return channel; the shortest applying column should read as deliberate, not deficient.

### Figure 2.3 — Spray-and-pray vs. 3-3-2: the input-output flip
**Files:** ../images/02-the-reallocation-principle-fig-03.svg · ../d3/02-the-reallocation-principle-fig-03.html
**Prompt:** Two columns of paired horizontal bars on white across six shared outcome rows, one color per week held consistent down the page. Let the spray-and-pray week win only on raw application count in neutral gray and the 3-3-2 week win every outcome row that matters in the one red accent.

### Figure 2.4 — Where does a freed hour go?
**Files:** ../images/02-the-reallocation-principle-fig-04.svg · ../d3/02-the-reallocation-principle-fig-04.html
**Prompt:** A top-to-bottom decision tree on white with two diamond gates and three terminal action nodes, single-direction ink arrows throughout. Route networking and portfolio off the early gates in neutral tones and make the additional-applications terminal visually subordinate, reached last after both gates, with a single red accent on the active path.
# Chapter 3 — The Verified-Data Contract
*The one rule that separates a filter you can trust from a guess wearing the costume of one.*

There is a particular kind of wrong answer that is worse than no answer at all, and it is this: an answer that sounds right. Not obviously wrong. Not hedged or uncertain. Fluent, confident, plausible — and untrue.

I want to be precise about what I mean, because the distinction matters more here than almost anywhere else I can think of. A language model asked whether a particular Cambridge biotech sponsors work visas will not say "I don't know." It will say something like: "as a mid-size biotech competing for specialized talent, this company likely sponsors visas for research-focused roles." Every word of that sentence is defensible. The reasoning is plausible. The conclusion is probably true for a lot of companies in that description. And it is not a finding. It is the most coherent-sounding sentence the model could assemble from patterns in its training data — which is a completely different operation from looking at a record.

The Department of Labor publishes every Labor Condition Application a U.S. employer files before hiring a foreign worker. The USCIS publishes H-1B approval and denial counts by employer. If you run a script against those records and ask the same question, you get a different kind of answer: this company filed fifteen LCAs in three years and had an 85% H-1B approval rate. Or you get zero filings, ever. The number is not the most plausible thing you could say — it is what actually happened, as far as the public record goes.

The whole architecture of this book is built on that distinction. One answer is fluent. The other is *true*. The discipline required to build on the second, and only the second, is what I mean by the verified-data contract.

![Two columns: on the left, a model's fluent prose answer floating with no source anchor; on the right, a verified answer — filing count, approval rate, year — tied by solid connectors down to two labeled record sources, the Department of Labor and USCIS.](images/03-the-verified-data-contract-fig-01.png)
*Figure 3.1 — Same question, two kinds of answer*

<!-- → [INFOGRAPHIC: Two-column side-by-side: left column labeled "Model's answer" shows the fluent prose sentence with no source; right column labeled "Verified answer" shows the LCA count, approval rate, and year, traced to DOL and USCIS records. Caption: "Same question. One answer is plausible. One is checkable."] -->

## Why the contract is a single rule, not a set of guidelines

I've seen job-search systems — and empirical systems of all kinds — that try to manage the fluency problem with caveats: add a disclaimer, note that the model might be wrong, invite the user to verify. This doesn't work, and it doesn't work for a specific reason. A caveat lives outside the output. It is a warning label on a product, not a change to what the product contains. If the number inside the output was produced by a language model filling in a plausible-sounding value, the caveat is decoration on a fabrication.

The contract is different because it is a *prior constraint on what gets to enter the system at all*, not an advisory attached to what came out. The rule is stated once, in the shared configuration that every recipe in this system reads before doing anything else: **Run the script and read the audit before you prompt. Never invent a count, a rate, or a coverage number.**

That is it. One rule. The simplicity is intentional. Complex rules are negotiated; a one-rule contract is harder to quietly break. The model's role in this system is to help you *read* data — to frame a finding, identify what's interesting about a number, suggest what to look at next. It is not permitted to be the source of a number. Sources of truth in this system are specific things: script outputs, audit reports, logged runs. Not the model's best guess at what the number probably is.

## What the system actually measures, and where it lives

The verified-data contract is not a philosophy statement. It is enforced by the architecture. There are three subsystems that produce the numbers this book is built on, and each of them writes to auditable records you can read and question.

![A systems diagram: three source pipelines — funding, postings and liveness, role quality — each producing its own audit output, with all three audits converging into a single run log; small self-loops on each source mark a local-verified-data-first cache check.](images/03-the-verified-data-contract-fig-02.png)
*Figure 3.2 — Three pipelines, three audits, one log*

<!-- → [DIAGRAM: Three boxes labeled scripts/sec/ (funding), scripts/ats/ (postings and liveness), scripts/bls/ (role quality), each with an arrow pointing to a corresponding *-audit.md output, all feeding into RUN_LOG.md. Caption: "The three pipelines and where their output lives — every number traces back through this graph."] -->

`scripts/sec/` pulls from SEC filings to measure company funding. When a company raises a round or files material financials, that event is in the public record. The script finds it; the audit reports what was found and what was dropped. `scripts/ats/` queries job-board data to measure whether a company is actively posting and whether particular openings are live. `scripts/bls/` draws on Bureau of Labor Statistics data to assess role quality — compensation, demand trajectory, geographic concentration. Each subsystem writes an audit: a record of what the pipeline did on a given run, how many rows it processed, what coverage it achieved, what it couldn't match.

`DATA_CONTRACT.md` defines what data exists and where it lives — including which files are private (your own application records, credentials, anything that identifies you personally) and how those are handled. `RUN_LOG.md` is the system's memory: every run leaves a trace, so a decision you make today on the strength of a number can be reconstructed and questioned tomorrow. This is the same practice good empirical work has always demanded — state your method, show your coverage, let a claim be checked.

## The tool prefers what it already trusts

There is a mechanism underneath the contract I haven't named yet, and it is the part people miss when they picture a verification tool. They imagine it reaching out to the network every time — hitting the Department of Labor server, re-downloading the disclosure file, re-counting from scratch. That is not what happens, and the difference is the whole reason the contract is cheap to keep.

Each of these tools checks for **local verified data first**. Once the DOL disclosure data has been downloaded and checked, it lives in a local store. When a script runs, it asks a prior question before it asks the network anything: *do I already have verified data for this, and is it still fresh?* If the answer is yes, the script reads the local copy and never touches the network. The audit says so plainly — *served from cache* — so you can see that this run rested on data already verified, not on a fresh pull nobody checked.

Only when the local answer is no — the data is missing, or older than the freshness window the contract defines — does the tool go and fetch. And fetching is not the same as trusting. The moment new data arrives it is **verified on arrival**: the schema is what was expected, the row counts are sane, the source is the one it claims to be. Only then is it written to the local store, and only then does a line go into the run log recording that a fetch happened and what it pulled. The network is the fallback, not the default.

This is not mainly an optimization for speed, though it is faster. It is what makes a run **reproducible**. A number you cited last Tuesday can be regenerated today from the same local verified data, because the tool did not silently re-pull a changed file underneath you. When the data genuinely changes — a new quarter of filings drops — the fetch is logged, visible, and dated, so the change is a recorded event instead of a mystery. Verified-once-then-cached is how "never invent a number" stays affordable: you are not re-earning trust on every run, you are reusing trust you already audited.

## The smallest honest thing you can do right now

Before you understand every component, before the sponsorship pipeline and the ATS scraper and the funding detector are fully built, there is one thing you can do that establishes the contract in practice rather than just in principle. Run a verification:

```bash
npm run ats:verify
```

This calls `scripts/ats/verify-pipeline.mjs`, which checks the tracker and scan data for internal consistency and prints what it found. The output is the audit. I want you to run this not because you need the result yet, but because there is a specific feeling I want you to have: the difference between being told the data is fine and *seeing the check pass*. One of those is someone's word. The other is evidence. The contract is the decision to require the second.

| Pipeline | What it verifies | What the audit reports |
|---|---|---|
| `ats:verify` | Tracker and scan-data consistency | Row counts, coverage, drop reasons |
| `sec:verify` | Filing-record completeness | Companies matched, date range, gaps |
| `bls:verify` | Role-quality data freshness | Series IDs, last update, missing occupations |

*Table 3.1 — The three verification commands and what each audit tells you.*

## The seam where fluency sneaks back in

Here is the error I want to warn you about specifically, because it is not obvious and it catches almost everyone, including me when I'm moving fast. You run the script. The script returns a real number — fifteen filings, 85% approval rate, sourced to DOL records. Now you hand that number to a language model and ask it to interpret the finding. The model says: "fifteen filings over three years is strong for a company of this size in this sector."

Did the model count anything? No. It estimated. It applied a pattern from its training data about what "strong" looks like for biotechs of similar size — a pattern it cannot actually show you, because it does not know what the pattern is, only that the output sounds reasonable. The moment an unsourced judgment re-enters through interpretation, the contract has been quietly broken. You ran the script, which was right. You then let the model paper over a gap in the reading, which was wrong.

The discipline required is to watch the seam between the data and the reading of the data. Data claim: fifteen filings, 85% approval rate, sourced to DOL/USCIS. Model judgment: this is strong for a company of this type. Both are present in that paragraph. Only the first can be defended against scrutiny. The second is permitted — it is genuinely useful — but it has to be *labeled as judgment*, not dressed as a fact derived from counting.

For any sentence in a system output, one question settles it: could this sentence have been produced by counting records? If yes, it must trace to a script output or an audit report. If it cannot be traced, it is not allowed to stand. If no — if it is a reading, a framing, a suggestion — it is model judgment, and it is allowed, but it must be visible as such.

![A decision tree: one question — could this sentence have been produced by counting records? — splits into a data-claim branch that must trace to a script output or audit and a model-judgment branch that is allowed but must be labeled, with both branches reconverging on a final check that the label is visible in the output.](images/03-the-verified-data-contract-fig-03.png)
*Figure 3.3 — The one-question test for every sentence*

<!-- → [INFOGRAPHIC: Decision tree — "Could this sentence have been produced by counting records?" Yes branch leads to "Data claim: must trace to script output or audit." No branch leads to "Model judgment: allowed, but must be labeled." Both branches end at "Is the label visible in the output?" Caption: "The one-question test for every sentence in a mixed output."] -->

## What the data can't tell you

The contract guarantees that counts and rates are real. It does not guarantee that the right things were measured. This is a distinction the contract cannot collapse for you, and I want to be honest about where it leaves you.

The data knows a company filed fifteen LCAs. It does not know that all fifteen were for one senior scientist role that was filled and will not open again. It knows an approval rate; it does not know that the company was acquired last month and the sponsorship policy changed last week. A name-matching failure — "Google LLC," "Google Inc," "Alphabet" — can make a prolific sponsor look like a non-filer. A company can sponsor and stay below the detection threshold if they filed in a window your data doesn't cover.

The contract stops you from building on fiction. It does not give you omniscience. What it gives you is a floor: you know the numbers you have are real, and you know where the gaps are, because the audit reported them instead of hiding them. A 94%-accurate system can still harm someone systematically if no one asks what it failed to measure. The contract makes you the person who asks that question — not the model, not the system, you. The gaps it reports are your honest starting debt: claims you currently cannot source, labeled as such, waiting for better data.

| What the contract guarantees | What the contract cannot guarantee |
|---|---|
| Counts and rates are real | That the right things were measured |
| Gaps are labeled, not hidden | That coverage is complete |
| Decisions trace to auditable records | That the records captured the full picture |
| Model judgments are labeled | That those judgments are correct |

*Table 3.2 — The floor the contract provides and the ceiling it doesn't claim to reach.*

![A two-column matrix pairing each guarantee with its matching limit — counts are real versus the right thing was measured, gaps are labeled versus coverage is complete, decisions trace to records versus the records captured the full picture, judgments are labeled versus those judgments are correct — a wall of solid assurances facing a wall of honest caveats.](images/03-the-verified-data-contract-fig-04.png)
*Figure 3.4 — The floor and the ceiling: guarantees vs. limits*

## The shape of everything that follows

Before any of those tools, two chapters finish the method this one began. Chapter 4 shows that every tool here is a *recipe* with two customers — the AI that runs it and the human who maintains it — and that you therefore write each one twice. Chapter 5 takes the floor this chapter laid down (the numbers are real) and asks the harder question the contract cannot answer on its own: are they the *right* numbers, measured the right way?

Then the building starts. Every chapter from there forward builds one of the three sources of truth or shows you how to read what they produce. Chapter 6 builds the funding detector — SEC filings, round size, recency, the money that forces companies to hire. Chapter 7 builds the sponsorship pipeline. Chapter 8 builds the posting liveness check. Each of them opens by reading the shared contract, each of them writes to an audit, each of them contributes a line to the run log.

The prime directive is already set: run the script and read the audit before you prompt. Never invent a count, a rate, or a coverage number. From here, the work is building the scripts worth running.

The one question I haven't fully answered yet: of all the companies in the world, which ones just got the money that forces them to hire? That's where we go next — and the answer, it turns out, is sitting in a federal filing database, waiting to be counted.

---

## Chapter 3 Exercises: The Verified-Data Contract

**Project:** Your Own Reallocation Engine

**This chapter adds:** the floor your engine stands on — you fork the repo, run your first verification, write your first `RUN_LOG.md` entry, and harden the `CLAUDE.md` rule from Chapter 1 into the full one-rule contract: run the script and read the audit before you prompt; never invent a count.

---

### Exercise 1 — When to Use AI

**The judgment:** In this chapter's work, AI assistance is appropriate for the following tasks:

- **Summarizing what a verification audit reported, in plain language.** — *Why AI works here:* the audit is the ground truth; the model is reformatting numbers you can read for yourself — a checkable summary, not a source.
- **Drafting a `RUN_LOG.md` entry from the command you ran and the output you paste in.** — *Why AI works here:* this is structured reformatting of facts you supply; the log's accuracy is verifiable against the terminal output.
- **Explaining what a given script does by reading its README with you.** — *Why AI works here:* comprehension support you verify by running the script — the interrogation mode, not delegation.

**The tell:** You know you are using AI appropriately when you can evaluate the output — when you have independent criteria to judge whether it is correct, complete, and fit for purpose. Here the criterion is the audit file itself: every claim the model makes must be checkable against it.

---

### Exercise 2 — When NOT to Use AI

**The judgment:** In this chapter's work, the following tasks require human judgment. Delegating them to AI is not appropriate — not because AI cannot produce output, but because AI output in these cases cannot be trusted without verification that requires the same expertise as doing the task yourself.

- **Producing any count, rate, or coverage number.** — *Why AI fails here:* this is the prime directive — a model asked "how many LCAs did this firm file?" returns a plausible number, not a counted one; that is fabrication, the exact failure the contract exists to stop.
- **Deciding whether a sentence in an output is a data claim or a model judgment.** — *Why AI fails here:* the model that wrote the fluent interpretation is the worst-placed to flag it; the seam where an estimate re-enters as fact is yours to police.
- **Judging whether a labeled coverage gap is acceptable for a given decision.** — *Why AI fails here:* whether a missing visa category matters depends on your situation — a stakes judgment the model cannot make.

**The tell:** You know you have crossed the line when you are using AI output as your reason for a conclusion rather than as a tool for reaching one. If you could not explain the conclusion without the AI, the AI did the work that should have been yours.

**Series connection:** This exercise trains **Tier 4 (Metacognitive supervision)** — the discipline of watching the seam between counted fact and fluent estimate, and refusing to let the second wear the costume of the first.

---

### Exercise 3 — LLM Exercise

**What you're building this chapter:** a clean separation, for one real audit output, of what is a data claim (must trace to a record) and what is model judgment (allowed, but labeled) — the reading discipline every later score depends on.

**Tool:** Claude (claude.ai chat). Chat is the right fit; you paste a real audit and interrogate it.

**The Prompt:**

```
I am enforcing a verified-data contract: any sentence that could have been
produced by counting records must trace to a script output or audit; any
sentence that is interpretation must be labeled as model judgment, never dressed
as a counted fact. You must NOT invent any number — if a number isn't in what I
paste, you do not have it.

Below is the output of a verification command from my job-search engine. Do four
things:

1. List every DATA CLAIM in the output (counts, rates, coverage, dates) and, for
   each, name the source it should trace to (which script or audit).
2. List every MODEL JUDGMENT or interpretation, and rewrite each so it is
   explicitly labeled as judgment (e.g. "Interpretation, not counted: ...").
3. Apply the one-question test to one borderline sentence: "Could this have been
   produced by counting records?" Show your reasoning for yes or no.
4. Draft a RUN_LOG.md entry: what I ran, what the audit reported, and one thing
   the output told me I would otherwise have assumed.

If any step needs a number not present below, say "not in the provided output"
instead of estimating.

--- PASTE YOUR AUDIT OUTPUT BELOW ---
[paste the printed output of your verify command here]
```

**What this produces:** a labeled breakdown of your own audit into data claims vs. judgments, plus a ready `RUN_LOG.md` entry — the habit that keeps fluency from sneaking back in at the reading layer.

**How to adapt this prompt:**
- *For your own project:* paste the real terminal output of whatever verify command you ran. The prompt is useless on an invented audit and sharp on a real one.
- *For ChatGPT / Gemini:* works as-is; both occasionally "helpfully" estimate a missing number — the "not in the provided output" instruction is the guardrail, keep it verbatim.
- *For a Claude Project:* put the one-question test and the data-claim/judgment definitions in the project instructions so every reading inherits them.

**Connection to previous chapters:** this operationalizes Chapter 1's interrogation reflex on real data and gives Chapter 2's "unverified" target columns a rule for how they get filled.

**Preview of next chapter:** Chapter 4 shows you how to write the recipes that produce these audits — twice, once for the agent and once for the human who maintains it.

---

### Exercise 4 — CLI Exercise

**What you're building this chapter:** your first real run — you fork the engine, execute a verification command, and record it, turning the contract from principle into a logged event.

**Tool:** Claude Code. Cloning, running an `npm` command, reading an audit, and writing a log entry is a terminal workflow that suits an agentic CLI.

**Skill level:** Intermediate — requires cloning a repo and running commands; recoverable if a command fails.

**Setup:**

Before running this exercise, confirm:
- [ ] You have forked/cloned the engine repo and run its install step (e.g. `npm install`).
- [ ] `recipes/_shared.md`, `DATA_CONTRACT.md`, and `RUN_LOG.md` exist in the repo.
- [ ] Your `CLAUDE.md` from Chapter 1 is present (you'll extend it).

**The Task:**

```
Work inside my forked engine repo. Do not modify any data files or any script;
this is a read-and-run-and-record task only.

1. Read recipes/_shared.md and tell me, in two lines, what the prime directive
   is and which files are named as sources of truth.
2. Run the ATS verification command:  npm run ats:verify
   Paste the full output back to me. If it errors, show the error and stop.
3. From that output, append a dated entry to RUN_LOG.md using the repo's log
   format: what ran, what the audit reported (row counts / coverage / drops),
   what worked, what didn't, and one thing the output revealed.
4. Append one line to CLAUDE.md under a "Verified-data contract" heading:
   "Run the script and read the audit before prompting. Never invent a count, a
   rate, or a coverage number. Label model judgment as judgment."
5. Show me the diff of RUN_LOG.md and CLAUDE.md before saving.

Do not fetch from the network beyond what ats:verify does on its own. Stop after
step 5.
```

**Expected output:** the verify command's audit printed back, a new `RUN_LOG.md` entry, and the contract rule appended to `CLAUDE.md` — shown as a diff for your approval.

**What to inspect in the output:** read the audit — does it report *served from cache* or a fresh fetch? Are the row counts non-zero and sane? Confirm the `RUN_LOG.md` entry contains only numbers that appear in the actual output, not rounded or "approximately" values the model smoothed in.

**If it goes wrong:** the most likely failure is `npm run ats:verify` erroring because data hasn't been downloaded yet or `portals.yml` is missing. Recover by reading the error and the script's README (Chapter 4's scan recipe covers the missing-config case) — do not let the agent fabricate a plausible audit to "complete" the task.

**CLAUDE.md / AGENTS.md note:** this exercise writes the load-bearing rule of your whole repo into `CLAUDE.md`. Every later pipeline (Chapters 6–9) inherits it; if you add a data source, this rule is what it must satisfy before its numbers count.

---

### Exercise 5 — AI Validation Exercise

**What you're validating:** a mixed system output where a real, sourced number and an unsourced estimate sit in the same paragraph — the seam failure the chapter warns about.

**Validation type:** Reasoning chain (data-claim / judgment boundary).

**Risk level:** Medium — the data claim is true, which is what lends the smuggled judgment its credibility.

**Setup (pre-generated artifact — option b):** This chapter's lesson is the seam where fluency re-enters through interpretation, so validate this pre-generated output:

> **Sponsorship finding — Acme Bio.** Acme Bio filed 15 LCAs over the past three
> years with an 85% H-1B approval rate (source: DOL/USCIS records). This is a
> strong sponsorship signal for a company of this size, and Acme Bio is very
> likely to sponsor your visa for a research role. Given their Series B funding,
> they are also probably expanding their team and would be a great culture fit.

**The Validation Task:**

Evaluate the AI output above using the following checklist. For each item, record: Pass / Fail / Cannot determine — and explain your reasoning.

```
Validation Checklist — The Verified-Data Contract

□ Correctness: Which sentences are counted facts and which are estimates?
  Apply the one-question test to each: could it have been produced by counting
  records?
□ Completeness: Do the data claims carry their source, and do the judgments
  carry a "this is interpretation" label?
□ Scope: Did the output stay within what the data supports, or did it add a
  culture-fit and expansion claim nothing measured?
□ Seam check (chapter-specific): Identify the exact sentence where a verified
  number ("15 filings") is used to launch an unsourced judgment ("strong
  signal," "very likely to sponsor"). Is that judgment labeled?
□ Coverage-gap check (chapter-specific): Does the output mention what it could
  NOT see (name-matching gaps, visa categories not covered, filing recency)?
□ Failure mode check: Does this output exhibit any of the following?
  - Fluent but wrong (a true number used to certify an untrue conclusion)
  - Unlabeled model judgment dressed as a counted fact
  - Missing ground truth ("probably expanding" — sourced to nothing)
```

**What to do with your findings:**
- If the output passes all checks: use it. (It will not — at least two judgments are unlabeled.)
- If the output fails one check: rewrite the paragraph so every counted fact carries its source and every judgment is labeled as judgment, then re-validate.
- If the output fails multiple checks or you cannot determine pass/fail: this is a "When NOT to Use AI" moment — write the finding yourself from the audit.

**AI Use Disclosure prompt:**
After completing this validation, write a two-sentence AI Use Disclosure:
> *Sentence 1:* What AI produced in this exercise and how you used it.
> *Sentence 2:* One specific thing the AI could not determine that required your judgment.

**Series connection:** This exercise trains **Tier 4 metacognitive supervision** — catching the moment a fluent interpretation borrows the authority of a verified number. The contract gives you the floor; this skill keeps you standing on it.

---

## Prompts

### Figure 3.1 — Same question, two kinds of answer
**Files:** ../images/03-the-verified-data-contract-fig-01.svg · ../d3/03-the-verified-data-contract-fig-01.html
**Prompt:** Two columns on white — a model's fluent answer as a soft unanchored block on the left, the verified answer on the right as a compact data cluster bolted by solid connector lines down to two labeled record sources. Render the floating block in neutral gray and the grounded cluster and its connectors in the one red accent so groundedness reads as the whole contrast.

### Figure 3.2 — Three pipelines, three audits, one log
**Files:** ../images/03-the-verified-data-contract-fig-02.svg · ../d3/03-the-verified-data-contract-fig-02.html
**Prompt:** A left-to-right systems diagram on white — three stacked source pipelines, each with a solid ink arrow to its own audit node, all three converging into one run-log node. Keep sources and audits in neutral grays, mark the converging run log in the one red accent, and add a small cache self-loop on each source as a thin minor accent.

### Figure 3.3 — The one-question test for every sentence
**Files:** ../images/03-the-verified-data-contract-fig-03.svg · ../d3/03-the-verified-data-contract-fig-03.html
**Prompt:** A top-to-bottom decision tree on white, one entry diamond splitting into a data-claim branch and a model-judgment branch that reconverge at a final visibility diamond. Single-direction ink arrows, neutral-gray outcome nodes, and a single red accent on the data-claim path that must trace to a record.

### Figure 3.4 — The floor and the ceiling: guarantees vs. limits
**Files:** ../images/03-the-verified-data-contract-fig-04.svg · ../d3/03-the-verified-data-contract-fig-04.html
**Prompt:** A two-column matrix on white pairing four guarantees against four matching limits as rounded chips. Give guarantee chips a solid affirming mark in the one red accent and limit chips a hollow cautionary mark in neutral gray, so a wall of assurances faces a wall of honest caveats row by row.
# Chapter 4 — Two Customers: Writing a Recipe for the AI and the Human

*A document that tries to serve everyone serves no one — the problem is older than software, and recipes are not exempt from it.*

There is a small confusion built into the word "recipe" that I want to name before it causes trouble. A recipe lives in a markdown file. Markdown is text you read. So naturally, when someone writes a recipe, they write it for a reader — they explain what it does, they describe its purpose, they use complete sentences and transitions. The file is readable and pleasant and almost entirely useless to the agent that has to execute it tonight.

I want to be precise about what I mean by "tonight." The F-1 clock is running. You have somewhere between sixty and ninety days to line up a job offer with a company willing to sponsor, file the paperwork, and get it processed. Every recipe in this engine either runs on verified data or it doesn't. And whether it runs on verified data is decided not by what you intended when you wrote it, but by what happens when an agent reads it at eleven PM and starts executing. The document that should have said "call `npm run ats:scan` first, before anything else" instead said "the recipe is designed to use the scan results" — and the agent, unable to locate the output it needed, quietly substituted something plausible. The recipe ran. Nothing in the output announced the substitution. The data was invented.

That failure has a cause, and the cause is a design error. The recipe was written for one customer and executed by another.

## The two customers

Every recipe has two customers with completely different needs.

The first customer is the AI executing it. It needs the recipe to be **complete, explicit, and unambiguous**. It needs to know — precisely, with nothing left to inference — what to read first, what commands to run in what order, what output files to inspect, what to log, and under what conditions to stop. What it does *not* need is narrative or rationale: prose explaining *why* is budget spent on something other than the task. But stripping the prose does not mean making the artifact short. Often the opposite — a serious agent contract can run to hundreds or thousands of lines of exact steps and structured JSON, because every case the agent might hit has to be specified rather than left to its judgment. Terse in prose, exhaustive in specification. The AI doesn't care that the scan recipe exists to enforce the verified-data contract — it cares that the first line says "Read `recipes/_shared.md`," that the next line names the file, and that nothing it needs is missing. The executable recipe is optimized for an agent to follow exactly, tonight.

The second customer is the human maintaining it. This is future-you, reading in March, who has forgotten what the recipe does, has no memory of why certain design choices were made, and needs to understand the recipe well enough to fix it when it breaks or extend it when your search changes. The human does *not* want the exhaustive specification the agent needs — handed a thousand lines of exact steps, a person skims and loses the thread. What the maintainer wants is orientation first: a high-level summary of what the recipe is and why it exists, and then the ability to drill into detail only on the question they actually have. So the human artifact is layered: a one- or two-sentence purpose and the big picture on top, then dependencies, how to run it, what it produces, and how it fails underneath — each there to expand when a specific question arises, not to be read end to end. Optimized for fast comprehension and selective depth rather than execution.

The problem is that these two needs are in tension. The agent contract is stripped of explanation so nothing is ambiguous and nothing is left to improvisation. The human card leads with the summary and keeps the detail a layer down, so the maintainer grasps the point before deciding how deep to go. A document that tries to do both splits the difference: too much prose to be clean and exact for the agent, too much exhaustive detail up front to make sense to a reader who has forgotten the context. A recipe written to serve both customers simultaneously serves neither.

So you write it twice.

![Two boxes side by side — an AI-artifact box that is complete and explicit (read-first order, verbatim commands, stop conditions, as long as precision requires) and a human-artifact box that leads with a summary and lets the reader drill into detail on demand — both resting on a single wide foundation bar labeled the verified-data contract, with arrows rising from the foundation into each box.](images/04-two-customers-fig-01.png)
*Figure 4.1 — Two customers, one contract*

<!-- → [DIAGRAM: Two boxes side by side, labeled "AI Artifact (recipe)" and "Human Artifact (card)". AI box lists: complete, explicit, imperative, read-first order, commands verbatim, stop conditions (as long as precision requires). Human box lists: purpose statement, dependencies, how-to-run, what-it-produces, failure modes. Both boxes share a footer labeled "Verified-Data Contract (_shared.md)" with arrows pointing into both. Caption: "Same recipe, two documents. The contract is the one thing both artifacts must honor."] -->

## What each artifact contains

The AI artifact — the recipe an agent follows — has a predictable structure. It opens with what to read first, before anything else. This is not optional and it is not decorative: loading `recipes/_shared.md` first is what makes the runtime honest by construction. The shared contract states the prime directive, identifies the sources of truth, and defines the rules for when a number is verified and when it must be labeled as judgment. An agent that loads the shared contract before running the first command operates inside a defined constraint. An agent that skips it operates from its own priors.

After the read-first order, the recipe lists the commands — actual, verbatim, runnable commands, not descriptions of what commands could be run. Then it names what to inspect in the output and what counts as evidence of a successful run: not "the output looks reasonable" but "row count is nonzero, provider hits are listed by platform, no errors in stderr." Then it states the stop conditions: what halt execution. Then it names the log entry to write. That's the recipe. It should be readable at a glance without decoding.

The human artifact is structured differently. It opens with a purpose statement that tells the maintainer what the recipe is *for* in one or two sentences. Then it lists dependencies: which files the recipe reads, which scripts it calls, which other recipes it assumes have run first. Then it gives the commands — the same commands as the recipe, but here they're annotated: what each one does, what the output is, what to notice in the result. Then it describes what the recipe produces when everything works: which files are written, what an audit looks like, what a log entry should contain. Finally, and most importantly, it lists failure modes: specific, named ways the recipe can break. Not "something might go wrong" but "if `data/ats/portals.yml` doesn't exist, the scan will silently use the example config and produce output against the example companies, not your companies."

That last section is the one that gets skipped when someone writes a recipe fast. And it is the one you need most at eleven PM on a Thursday when the output looks wrong and you don't know why.

| Section | AI artifact | Human artifact |
|---|---|---|
| Opening | Read-first list | Purpose statement |
| Core content | Imperative commands, no commentary | Annotated commands with output descriptions |
| Evidence | Stop conditions and output checks | What success looks like, in full |
| Logging | Log-entry template | What the log should contain, and why |
| Failure | Not present | Named failure modes with specific causes |

*Table 4.1 — The structural difference between the two artifacts: the same commands appear in both, but their context is inverted.*

## Drift is a failure mode, not just inconvenience

There is a failure mode I have not named yet, and it is more damaging than either the missing rationale or the over-explained recipe. It is drift: the recipe changes, and the human doc doesn't.

Drift happens because updates feel minor. You change one command — you add a flag, rename an output file, change the order of two steps because the second one now depends on output from the first. You update the recipe because the recipe is what the agent runs, and the agent fails if the recipe is wrong. The human doc also needs updating, but you're in a hurry, and it's just documentation, and you'll do it later. Later doesn't come, because it never does when you're racing a clock.

Six weeks later, you read the human doc to understand why the scan recipe works the way it does. The human doc describes a workflow that no longer exists. It names a file the recipe no longer produces. It lists a command that now fails without a flag the recipe added. You can no longer trust the documentation, which means you now have to reverse-engineer the recipe to understand your own recipe, which costs more time than writing the human doc would have.

Drift is its own failure mode — not a consequence of forgetting to maintain the docs, but a structural property of having two artifacts with no enforcement binding them. The only enforcement is discipline: when you update one, you update both in the same commit, and the human doc's failure-modes section explicitly lists "human doc not updated when recipe changes" as one of the named failure modes. The system cannot automate this. The discipline is yours.

![Two parallel tracks — recipe and card — across three time positions: initially in sync, then the recipe is updated while the card stays unchanged and the connector between them breaks, then a reader follows the stale card down a wrong path diverging from the recipe's actual behavior.](images/04-two-customers-fig-03.png)
*Figure 4.3 — Drift: when the map leaves the territory*

## Both artifacts honor the verified-data contract

The shared contract from Chapter 3 is the one thing both artifacts must honor, and each honors it differently.

The AI artifact honors it procedurally: `recipes/_shared.md` is the first item in the read-first list. The agent loads it, and the contract's prime directive is active for the entire run. The rules are live in context: use collected data and tested scripts first; never invent counts, rates, or coverage numbers; if a result comes from LLM judgment, label it as such.

The human artifact honors it structurally: the dependencies section lists which scripts the recipe calls and which audits it reads, making the data provenance visible to anyone reading the card. The failure modes section includes specific entries for contract violations — what happens if the script isn't called, what the output looks like when a model fills in a gap versus when a script ran. The maintainer who reads the human artifact should finish it knowing exactly which parts of the verified-data contract this recipe relies on and what breaks if that reliance is violated.

There is an additional fact here worth stating plainly. The F-1/OPT reader running this engine is both customers at different times. You author the recipe, sitting at your laptop with context about what the recipe is supposed to do, what scripts you built, what data you collected, what can go wrong. You are the human customer. Tonight, an agent runs the recipe you wrote. The agent is the AI customer. In March, you — or someone who is nearly a stranger to this codebase — reads the human doc to understand why something is behaving strangely. You are the human customer again, but with much less context than you had when you wrote it.

The reader who has forgotten everything is not a hypothetical. It is you in three months. The human artifact is a letter you are writing to that person. Write it like it is.

## The scan recipe, shown both ways

The best way to understand the two-artifact structure is to see it for one recipe. The `scan` recipe is the right choice: it is the first active recipe in the engine's chain, it calls real scripts, and it exists in the repository you are using, so the commands are not examples I've constructed for illustration.

Here is the recipe an AI would follow:

---

**scan — AI recipe**

Read first:
- `recipes/_shared.md`
- `scripts/ats/README.md`
- `data/ats/portals.example.yml`
- `data/ats/portals.yml` (if it exists)
- `data/ats/scan-history.tsv` (if it exists)
- `recipes/RUN_LOG.md`

Run:
```bash
cd scripts/ats
python3 detect-ats.py "Company Name" --output ../../data/ats/ats_detection_sample.csv
cd ../..
npm run ats:scan
npm run ats:liveness -- --file data/ats/job-urls.txt
npm run ats:verify
```

Inspect output: count rows; count provider hits by platform; record empty results separately from errors; note where output was written.

Deduplicate: prefer exact URL; then company plus normalized role title; record suspected duplicates, do not delete uncertain entries.

Stop conditions: if `data/ats/portals.yml` does not exist, copy `data/ats/portals.example.yml` and edit before proceeding. Do not run the provider scanner against the example config.

Log template:
```markdown
## YYYY-MM-DD -- ATS scan
- **Recipe:** scan
- **Input:** data/...
- **Command:** `...`
- **Output:** data/...
- **Worked:** ...
- **Did not work:** ...
- **Evidence:** row counts, provider counts, sample URLs
- **Next:** ...
```

Prompting rule: use LLM judgment only after script output has been inspected. The LLM may summarize patterns, explain likely failure causes, or propose the next test. It must not invent ATS hits, live job counts, or sponsorship claims.

---

Now here is the human card a maintainer reads:

---

**scan — human card**

**Purpose.** Detect which applicant-tracking system (ATS) a company uses and pull current job postings from configured portals. This is a data-collection step, not an analysis step. Its output feeds the pipeline recipe.

**What it can verify:** whether a company exposes Greenhouse, Lever, or Ashby jobs; whether a portal scan produced new URLs; whether a posting URL appears in scan history; whether a posting is probably live after a liveness check.

**What it cannot verify on its own:** sponsorship likelihood; role quality; whether a company is a good target. Those require SEC/H-1B and BLS/SOC data, handled by later recipes.

**Dependencies:**
- `recipes/_shared.md` — the verified-data contract; must be loaded first
- `scripts/ats/detect-ats.py` — detects ATS by company name or CSV input
- `scripts/ats/scan.mjs` (via `npm run ats:scan`) — runs configured portal scan
- `scripts/ats/` — liveness check and verify commands
- `data/ats/portals.yml` — your working portal config (not the example)
- `data/ats/scan-history.tsv` — deduplication history from prior runs

**How to run:**
```bash
# Detect ATS for specific companies:
cd scripts/ats
python3 detect-ats.py "Company A" "Company B" --output ../../data/ats/ats_detection_sample.csv

# Run full portal scan (requires portals.yml to be configured):
cd ../..
npm run ats:scan

# Check liveness of specific URLs:
npm run ats:liveness -- --file data/ats/job-urls.txt

# Verify pipeline consistency:
npm run ats:verify
```

**What it produces:** detection output CSV; scan output with provider hits by platform; liveness signals per URL; a verification audit. A log entry in `recipes/RUN_LOG.md` documenting what ran, what it found, and what failed.

**How it fails:**
1. `data/ats/portals.yml` missing — the scan will use the example config and return results for example companies, not your companies. The output will look plausible and be wrong. Check that `portals.yml` exists and is not identical to `portals.example.yml` before trusting any scan result.
2. ATS detection hits vs. live postings conflated — "ATS detected" means the provider is present. "Live posting" requires a liveness check. They are different facts. A recipe output that reports ATS hits as if they were open jobs has skipped the liveness step.
3. Recipe updated, human doc not updated — if the commands in the recipe diverge from the commands in this card, one of them is wrong. Check the recipe before troubleshooting.
4. LLM fills in missing data — if the scan produces no results and the recipe output contains confident sponsorship claims or ATS findings, the prompting rule was violated. No script output means no verified data. The output must say what it couldn't find, not invent a replacement.

---

The commands are identical between the two artifacts. What differs is the frame: the recipe assumes the reader will execute immediately; the human card assumes the reader is trying to understand. The same content, arranged for two different questions — "what do I run?" versus "what is this and how does it break?"

![A section-by-section matrix mapping the five recipe sections across the two artifacts — opening, core content, evidence, logging, failure — where the AI column carries exact, imperative chips and the human column fuller annotated chips, and the failure row shows an empty AI cell against the heaviest chip in the human column.](images/04-two-customers-fig-02.png)
*Figure 4.2 — Same content, inverted context: section-by-section*

<!-- → [INFOGRAPHIC: Two annotated documents side by side — left labeled "AI Recipe (scan.md)" with callout arrows pointing to: read-first list, verbatim commands, stop condition, log template; right labeled "Human Card (scan — maintainer view)" with callout arrows pointing to: purpose statement, dependency list, annotated commands, failure modes numbered 1–4. Caption: "The recipe is optimized for execution. The card is optimized for comprehension. Neither does the other's job."] -->

## What writing them twice forces you to think about

There is an unexpected benefit to writing the recipe twice that I didn't anticipate when I designed this architecture. The discipline of writing the human card — especially the failure-modes section — forces you to think adversarially about your own recipe. When you sit down to write "how does this fail," you discover that you have not thought carefully about what happens when `portals.yml` is missing, or when the liveness check returns zero results, or when the output CSV is empty because none of the companies matched. Those are the moments you realize the recipe has a gap: it doesn't say what to do in those cases, which means the agent running it tonight will improvise. Improvisation in a verified-data system looks a lot like invention, which is what the contract prohibits.

Writing the failure modes is how you find the missing stop conditions. The human card is not just documentation — it is a test of the recipe.

## The bridge to Chapter 5

Writing a recipe well — two artifacts, shared contract loaded first, failure modes named, recipe and card maintained together — does not make the data the recipe reads trustworthy. The scan recipe can be structurally correct in every way this chapter describes and still return stale detection results, or miss a company because of a name-matching failure, or report a liveness signal on a posting that closed yesterday. The recipe follows the contract. The contract ensures the numbers aren't invented. Neither of those guarantees the numbers are the right numbers, measured the right way.

That question — are these the right numbers? — is the subject of Chapter 5. The verified-data contract set a floor: what you have is real. Chapter 5 asks whether real is enough.

---

## Chapter 4 Exercises: Two Customers

**Project:** Your Own Reallocation Engine

**This chapter adds:** the authoring discipline your engine is maintained with — for one recipe in your repo you write both artifacts, the complete-and-explicit AI recipe and the summary-first human card, bound by the shared contract, so tonight's agent can run it and March's you can fix it.

---

### Exercise 1 — When to Use AI

**The judgment:** In this chapter's work, AI assistance is appropriate for the following tasks:

- **Drafting the human card's prose sections (purpose, how-to-run) from the recipe.** — *Why AI works here:* turning a command list into readable explanation is drafting against a source you hold; you check it against the actual recipe.
- **Generating a first list of candidate failure modes for a recipe.** — *Why AI works here:* this is adversarial brainstorming — the model proposes ways things break, you keep the ones that are real for your setup.
- **Diffing a recipe against its human card to flag mismatched commands.** — *Why AI works here:* spotting where two texts disagree is pattern-matching you can confirm line by line.

**The tell:** You know you are using AI appropriately when you can evaluate the output — when you have independent criteria to judge whether it is correct, complete, and fit for purpose. Here the criterion is the recipe file: the card must describe what the recipe actually does.

---

### Exercise 2 — When NOT to Use AI

**The judgment:** In this chapter's work, the following tasks require human judgment. Delegating them to AI is not appropriate — not because AI cannot produce output, but because AI output in these cases cannot be trusted without verification that requires the same expertise as doing the task yourself.

- **Deciding the recipe's stop conditions — when an agent must halt rather than improvise.** — *Why AI fails here:* a missing stop condition is exactly where an agent invents data; deciding where the cliffs are requires knowing your data and your stakes, not generic caution.
- **Confirming the commands in the recipe actually run in your environment.** — *Why AI fails here:* the model can write a plausible command that doesn't exist in your repo; only running it proves it.
- **Judging whether a failure mode is complete enough to trust the recipe tonight.** — *Why AI fails here:* "have I thought of how this breaks for my companies?" is the adversarial judgment the chapter says writing the card forces — and it forces *you*, not the model.

**The tell:** You know you have crossed the line when you are using AI output as your reason for a conclusion rather than as a tool for reaching one. If you could not explain the conclusion without the AI, the AI did the work that should have been yours.

**Series connection:** This exercise trains **Tier 4 (Metacognitive supervision)** — writing the failure-modes section is a structured way of asking "what don't I yet understand about my own recipe?", which is metacognition made into a document.

---

### Exercise 3 — LLM Exercise

**What you're building this chapter:** the human card for one recipe in your engine — purpose, dependencies, annotated commands, and named failure modes — the maintainer's letter to future-you.

**Tool:** Claude (claude.ai chat). Chat fits: you paste a recipe and have the model help draft its companion card, which you then verify against the file.

**The Prompt:**

```
I follow a "two customers" rule: every recipe has an AI version (complete,
explicit, and imperative — as long as precision requires, for an agent to
execute) and a human card (summary first, with detail to drill into, for the
maintainer who has forgotten the context). I will paste the AI recipe below.
Write its HUMAN CARD only. Do not invent commands, files, or behavior that are not in the recipe
— if something is unclear, list it under "Open questions for me to resolve"
rather than guessing.

Structure the card as:
1. Purpose — 1–2 sentences: what this recipe is FOR.
2. What it can verify / what it cannot verify on its own.
3. Dependencies — files it reads, scripts it calls, recipes it assumes ran first
   (only those named in the recipe).
4. How to run — the same commands, annotated with what each does and what to
   notice in the output.
5. What it produces — files written, what a good audit looks like, the log entry.
6. How it fails — at least 4 NAMED failure modes with specific causes, including
   one for "recipe updated but this card wasn't" (drift) and one for "script
   produced nothing and the model filled the gap" (contract violation).

--- PASTE YOUR AI RECIPE BELOW ---
[paste one recipe from your recipes/ directory here]
```

**What this produces:** a complete human card for a real recipe, with an explicit drift failure mode and a contract-violation failure mode — saved next to the recipe it documents.

**How to adapt this prompt:**
- *For your own project:* paste a recipe you actually have. If the model lists "open questions," that's the gap in your recipe surfacing — resolve those before trusting the card.
- *For ChatGPT / Gemini:* works as-is; both may pad the purpose section — append "purpose section max two sentences."
- *For a Claude Project:* keep the two-artifact structure in the project instructions so every card you draft has the same shape.

**Connection to previous chapters:** the card's "what it cannot verify" section is where Chapter 3's coverage-gap honesty becomes part of your documentation.

**Preview of next chapter:** Chapter 5 asks whether the data these recipes read is measuring the right thing — the card's "what it cannot verify" line is where that question first appears.

---

### Exercise 4 — CLI Exercise

**What you're building this chapter:** a matched recipe + human card pair committed together, with a check that their commands agree — drift caught at write time, not at 11 PM.

**Tool:** Claude Code. Reading a recipe, writing a card, and diffing the two across files is a multi-file workflow suited to an agentic CLI.

**Skill level:** Intermediate — file editing plus a comparison step.

**Setup:**

Before running this exercise, confirm:
- [ ] Your forked repo has a `recipes/` directory with at least one recipe.
- [ ] You completed Chapter 3's run so `RUN_LOG.md` and the contract rule exist.
- [ ] You've picked which recipe to document (the `scan` recipe is a good first target).

**The Task:**

```
In my engine repo, create a maintainer card for one recipe and verify it matches.
Do not change the recipe's behavior; do not run any data-fetching scripts.

1. Read recipes/scan.md (or the recipe I name).
2. Write recipes/scan.card.md as the human card: purpose, can/cannot verify,
   dependencies, annotated commands, what it produces, and at least 4 named
   failure modes (include drift and contract-violation). Use ONLY commands and
   files that appear in the recipe.
3. Extract the list of shell/npm commands from the recipe and from the card and
   compare them. Print any command that appears in one but not the other — this
   is the drift check.
4. If the command lists differ, do NOT silently fix them; show me the difference
   and ask which is correct.
5. Show me both files and the drift-check result. Stop.
```

**Expected output:** a new `recipes/scan.card.md`, plus a printed drift-check confirming the recipe and card list the same commands (or flagging where they differ).

**What to inspect in the output:** read the failure-modes section — are they specific to your setup ("if `portals.yml` is missing, the scan runs against the example config") or generic ("errors may occur")? Generic failure modes mean the card isn't yet doing its job. Confirm the drift check actually compared commands rather than just asserting they match.

**If it goes wrong:** the likely failure is the card inventing a command the recipe doesn't have (or vice versa), which the drift check should catch. Recover by trusting the recipe as ground truth and correcting the card — never edit the recipe to match a card the model wrote.

**CLAUDE.md / AGENTS.md note:** add a standing rule — *"Every recipe has a paired `.card.md`; when a recipe's commands change, update the card in the same commit and re-run the drift check. 'Card not updated' is itself a logged failure mode."* This is the lightweight enforcement the chapter's final question asks for.

---

### Exercise 5 — AI Validation Exercise

**What you're validating:** an AI-written recipe/card pair that has drifted — the card describes a workflow the recipe no longer runs.

**Validation type:** Agentic output (documentation vs. executable instructions).

**Risk level:** High — a drifted card sends an agent down a path that silently produces wrong data, and nothing in the run announces it.

**Setup (pre-generated artifact — option b):** This chapter's lesson is drift, which your own freshly-written pair won't yet show, so validate this pre-generated mismatched pair:

> **AI recipe (refresh.md):**
> ```
> Read first: recipes/_shared.md
> Run:
>   npm run sec:refresh -- --since 2024-01-01
>   npm run sec:verify
> Stop if: sec:verify reports coverage below 90%.
> ```
> **Human card (refresh.card.md):**
> *Purpose.* Re-download SEC Form D data and verify it.
> *How to run:* `npm run sec:refresh` then `npm run sec:audit`.
> *What it produces:* a refreshed dataset and an audit; no stop conditions
> needed since the script handles errors automatically.

**The Validation Task:**

Evaluate the AI output above using the following checklist. For each item, record: Pass / Fail / Cannot determine — and explain your reasoning.

```
Validation Checklist — Two Customers

□ Correctness: Do the commands in the recipe and the card match?
  (recipe: sec:refresh --since ... + sec:verify;  card: sec:refresh + sec:audit)
□ Completeness: Does the card capture the recipe's stop condition?
  The recipe halts below 90% coverage — does the card mention it?
□ Scope: Does the card claim something the recipe contradicts?
  ("no stop conditions needed" vs. an explicit stop-if line)
□ Drift check (chapter-specific): List every command/condition present in one
  artifact but absent or different in the other.
□ Contract check (chapter-specific): The card says the script "handles errors
  automatically" — does anything in the recipe support that, or is it an
  unverified reassurance?
□ Failure mode check: Does this output exhibit any of the following?
  - Drift (recipe and card describe different workflows)
  - A dropped stop condition (the agent won't halt where it should)
  - Fluent but wrong (a confident card that misdescribes the recipe)
```

**What to do with your findings:**
- If the pair passes all checks: trust it. (It will not — the commands and stop conditions disagree.)
- If it fails one check: correct the card to match the recipe (the executable artifact is ground truth) and re-run the drift check.
- If it fails multiple checks or you cannot determine pass/fail: this is a "When NOT to Use AI" moment — rewrite the card yourself against the recipe, line by line.

**AI Use Disclosure prompt:**
After completing this validation, write a two-sentence AI Use Disclosure:
> *Sentence 1:* What AI produced in this exercise and how you used it.
> *Sentence 2:* One specific thing the AI could not determine that required your judgment.

**Series connection:** This exercise trains **Tier 4 metacognitive supervision** applied to your own tooling — noticing when the map (the card) and the territory (the recipe) have quietly diverged, before an agent acts on the wrong one.

---

## Prompts

### Figure 4.1 — Two customers, one contract
**Files:** ../images/04-two-customers-fig-01.svg · ../d3/04-two-customers-fig-01.html
**Prompt:** Two boxes side by side on white — a complete-and-explicit AI artifact (read-first order, verbatim commands, stop conditions; as long as precision requires) and a summary-first human artifact (purpose on top, detail to drill into) — both resting on one wide foundation bar for the verified-data contract, arrows rising from the foundation into each. Keep the two boxes in neutral grays and mark the shared contract foundation in the one red accent so the shared-base-different-shapes reads at a glance.

### Figure 4.2 — Same content, inverted context: section-by-section
**Files:** ../images/04-two-customers-fig-02.svg · ../d3/04-two-customers-fig-02.html
**Prompt:** A section-by-section matrix on white with a section-label column and two artifact columns across five rows, each cell a weighted chip. Hold the columns in neutral grays and make only the failure row asymmetric — an empty AI cell against the heaviest human chip rendered in the one red accent.

### Figure 4.3 — Drift: when the map leaves the territory
**Files:** ../images/04-two-customers-fig-03.svg · ../d3/04-two-customers-fig-03.html
**Prompt:** Two parallel tracks on white across three time positions — recipe and card in sync, then the recipe edits while the connector breaks, then a reader follows the stale card down a wrong path. Render both tracks in neutral grays and reserve the one red accent for the broken connector and the diverging wrong-path branch.
# Chapter 5 — Verifying the Data

*A number that traces to a real record can still be measuring the wrong thing.*

Chapter 3 established a floor: every count, rate, and coverage number in this system must trace to a script output or an audit report, never to a model's best guess. That floor matters enormously. It is the difference between building on evidence and building on fluent fabrication.

But a floor is not a ceiling. Chapter 3 guarantees the number is real — that it came from counting rows in a public record, not from a language model estimating what the number probably was. This chapter asks a harder question: even if the number is real, is it trustworthy? Does it measure what you think it measures? Does the headline figure hold up when you look at the assumptions underneath it?

The distinction is not subtle. You can have a perfectly audited, perfectly script-sourced count that is quietly measuring the wrong thing. A join failure can make a prolific sponsor look like a non-filer. A base-rate mismatch can make a genuine signal look stronger than it is. A name-matching gap can exclude an entire corporate family from the dataset without leaving any evidence the missingness check can see. These are not data-pipeline bugs — they are epistemic failures. The numbers are real. The interpretation is wrong.

The methods in this chapter come from a companion book, *Computational Skepticism for AI*, where they are developed in full technical depth. I'm drawing on them here because they apply directly to the DOL and USCIS datasets this book runs on. If the reasoning feels compact in places, that's intentional — this is the practitioner application, not the derivation. What matters here is the procedure and what it surfaces.

![A three-tier vertical stack: a wide foundation tier for the Chapter 3 guarantee that numbers trace to real records, a middle working tier asking whether the right things are being measured, and a narrower top tier for trustworthy inference, with a left-side ascent arrow marking the gap between the bottom two tiers as where coverage gaps, name-matching failures, and base-rate mismatch live.](images/05-verifying-the-data-fig-01.png)
*Figure 5.1 — The three-tier trust stack*

<!-- → [INFOGRAPHIC: Three-tier stack. Bottom tier labeled "Chapter 3 guarantee: numbers trace to real records." Middle tier (this chapter) labeled "Chapter 5 asks: are the right things being measured?" Top tier labeled "Trustworthy inference." An arrow on the left side labels the gap between tiers 1 and 2: "Coverage gaps, name-matching failures, base-rate mismatch." Caption: "The floor the contract provides. This chapter builds the next tier."] -->

## The opening question: why are there exactly N rows?

Before I run any analysis on the LCA disclosure data, I ask a question that sounds almost too simple: *why are there exactly N rows in this dataset?*

The question comes from the epistemic-frame interrogation developed in *Computational Skepticism for AI*. The point is this: a dataset is not a census. It is a recording made by a particular instrument under particular conditions. The row count is not a fact about the world — it is a fact about the recording. Something determined where the data collection started, where it stopped, what joined successfully, and what got dropped quietly along the way. Unless you know what that something was, you don't fully know what the dataset represents.

For the DOL LCA disclosure data, the answer is more specific than it first appears. The dataset contains every Labor Condition Application that employers filed before hiring a foreign worker on an H-1B, H-1B1, or E-3 visa. So the row count is bounded by: who filed, in what time window, for what visa category, under what employer name, and whether the filing was accepted into the disclosure system. Each of those conditions is a filter the dataset silently applies before you ever open it.

Here is the practical consequence for this book: an employer who sponsored consistently but always filed under slightly different name variations — "Google LLC" in one quarter, "Google Inc." in another, "Alphabet Inc." in a third — will produce rows scattered across three employer-name buckets. An aggregation that groups by employer name and counts filings will treat these as three different companies, each with a modest filing count, instead of one company with a substantial one. The dataset is not wrong. The join is not broken. The rows are real. But the count you compute from them is not the count you meant to compute.

This is the "why exactly N rows?" move applied to the join problem. The boundary of the dataset is not just the schema — it is the schema plus every reference the schema's contents imply. The LCA dataset references employer names. Employer names reference legal entities. Legal entities undergo mergers, renamings, and restructurings. The full count lives somewhere in that chain. The dataset gives you a sample of it, bounded by however the names happened to be entered in the filing system.

![Three small employer-name buckets — variants of one firm, each with a modest filing count — enclosed by a dotted boundary labeled the same legal filer, with a single arrow pointing right to one larger consolidated node representing the true aggregated count.](images/05-verifying-the-data-fig-02.png)
*Figure 5.2 — Name-matching fragmentation*

<!-- → [DIAGRAM: One company (Alphabet / Google LLC / Google Inc.) shown as three separate employer-name buckets in the LCA filing data, each with a small filing count. A dotted box around all three labeled "Same legal filer." An arrow pointing to the aggregated true count. Caption: "Name-matching failures don't break the dataset. They fragment it. The rows are real; the employer grouping is not."] -->

## The six-step interrogation procedure

The six-step procedure in *Computational Skepticism for AI* is designed for any dataset you intend to base a deployment on. I'll walk through it applied to the sponsorship dataset — the LCA-to-H-1B join that the Sponsorship Scorer in Chapter 7 will run.

![A six-step linear flowchart — read metadata and lock a prediction, run exploratory analysis, test metadata against the data, ask what is not in the data, trace one row end to end, write the epistemic frame and compare to the prediction — with a dashed reference arc closing from the final compare step back to the locked prediction.](images/05-verifying-the-data-fig-03.png)
*Figure 5.3 — The six-step interrogation procedure*

**Step 1 — Read the metadata and lock your prediction.** Before running any analysis, read the DOL disclosure file documentation. It tells you what fields are present, what time window is covered, and what constitutes a valid LCA. Write down what you expect the data to look like: how many rows, which employers should be there, what the approval rate distribution should look like. Lock this prediction before you look.

The prediction-lock matters for a specific reason. Without it, you only ever see the data as it is, which feels obvious, and you don't notice you've learned anything. With it, every gap between prediction and reality is a finding — the data is telling you something you didn't already know.

**Step 2 — Run the exploratory analysis.** Distributions, missingness, counts by employer, counts by year, counts by SIC code. The procedural pass. Note what shows up. Chapter 3's verification commands (`npm run ats:verify`, the sec and bls equivalents) produce the artifacts this step needs.

**Step 3 — Test the metadata against the actual data.** Does the time range match what the documentation says? Are the row counts consistent with the filing volumes the DOL reports in its summary statistics? Are there SIC codes present that shouldn't be, or absent that should be?

Here is where the "exactly N rows" question pays off. If the documentation implies a certain employer-universe coverage and the data shows a different pattern, that gap is a finding. Pursue it before moving on.

**Step 4 — Ask what is not in the data.** Look for dropped rows in the LCA-to-USCIS join. An employer who filed LCAs but whose H-1B counts appear zero or missing in the join may have a name-matching failure rather than a sponsorship failure. Look for time periods with sparse records — USCIS data has known gaps in certain fiscal quarters. Look for the companies that your prediction said should be there but aren't.

This step is not about finding errors in the data. It is about finding the shape of the data's coverage. What it can and cannot see.

**Step 5 — Trace at least one row end to end.** Pick one company from the dataset — say, the Cambridge biotech from Chapter 3's example. Follow its LCA filings through to the USCIS H-1B approval counts. Check whether the employer name in the LCA disclosure file matches the employer name in the USCIS data. Check whether the filing dates fall inside the H-1B fiscal year that would produce the approval counts you see.

I have done this trace. The experience is instructive every time. Almost every real dataset you trace this way turns up at least one surprise: a quarter where the filing count jumps because the company changed its legal name mid-year; a match that works on the first four words of the name but fails on the fifth; an approval count that appears lower than expected because one subsidiary filed separately.

**Step 6 — Write the epistemic frame and compare to your prediction.** What does the sponsorship dataset actually represent? It represents: LCA filings by employers operating under the names they used in a specific DOL submission window, joined to USCIS approval counts under the names USCIS recorded in its data, for the visa categories included in both disclosure regimes.

That is a more specific statement than "sponsorship data." The gap between the two is where the interpretation risk lives.

## Base rates and the confidence illusion

Even after the interrogation, there is a second failure mode that the procedure alone doesn't catch. It lives not in the data itself but in how a signal derived from the data gets interpreted. The mechanism is base rates, and the analysis comes from *Computational Skepticism for AI*'s treatment of calibration.

Here is the problem stated concretely. Suppose the Sponsorship Scorer produces a "0.65 probability of sponsorship" for a company in a given SIC code. That number came from a real signal — fifteen LCA filings, an 85% H-1B approval rate, sourced to DOL/USCIS records, exactly as Chapter 3 requires. But what does 0.65 actually warrant you to say?

It depends on the base rate. In most SIC codes, only a small fraction of employers have ever filed an LCA. In some technology-adjacent codes, this fraction might be 15–20%. In manufacturing, healthcare administration, or retail, it might be 2–3%. If only 3% of employers in a SIC code have ever filed an LCA, and the scorer's signal is calibrated, then even a strong positive signal produces a posterior probability that is lower than the raw 0.65 suggests. The math is Bayes' theorem, and it produces a result that consistently surprises people until they've worked through it enough times for it to become intuitive.

The false-positive problem is not hypothetical. A 99%-accurate test applied to a population where 1 in 10,000 people has the condition produces, for every 10,000 tests, approximately 1 true positive and approximately 100 false positives — so among all positive results, fewer than 1% are genuine. The numbers for sponsorship signals are not as extreme as this example, but the structure is identical: the base rate of the underlying phenomenon (this specific employer actually sponsoring H-1B workers for this type of role, right now, with openings available) is lower than the signal suggests.

Four diagnostic questions, drawn from *Computational Skepticism for AI*, settle whether a sponsorship signal is actually telling you what you think it is:

**What is the base rate?** What fraction of employers in this SIC code, size range, and geography have filed an LCA in the past three years? If the answer is 4%, a "likely sponsor" signal is working against a strong prior that says the company is not a sponsor. The signal has to overcome that prior, not just clear some absolute threshold.

**Is the signal calibrated?** A calibrated scorer means that when it says 0.65, the actual frequency of true positives among all cases scored at 0.65 is genuinely around 65%. Modern models are often well-calibrated in the middle of their probability range and badly overconfident at the extremes. Has anyone checked this scorer's calibration curve?

**What is the cost distribution of errors?** A false positive costs you an application fee, a cover letter, and time. A false negative costs you a lead you didn't pursue. These are not symmetric costs for an F-1 student racing a 90-day clock, but they are also not equally weighted across all circumstances. The right threshold depends on the cost ratio.

**What has changed since the data was collected?** The LCA data is historical. A company that was a prolific filer in 2021–2023 may have implemented a hiring freeze in 2024 or been acquired by a parent with a different sponsorship policy. The filing history is real; the inference to present sponsorship posture is an extrapolation across a time gap the data cannot bridge.

| Diagnostic question | What it surfaces | Where to find the answer | What to do if the answer is unfavorable |
|---|---|---|---|
| Base rate | Prior probability before seeing the signal | SIC-level LCA filing frequency in the audit | Lower the effective threshold; require stronger corroboration |
| Calibration | Whether the scorer's stated probability is reliable | Calibration curve if available; cross-validate on a holdout | Treat stated probabilities as ordinal ranks, not face-value probabilities |
| Cost distribution | Whether false positives or false negatives cost more | Depends on application deadline and role fit | Adjust the threshold accordingly |
| Freshness | Whether historical filings predict current posture | Filing date in the LCA data; recency filter in the audit | Downweight filings older than 18 months; flag acquisitions |

*Table 5.1 — The four base-rate diagnostic questions and how to act on each.*

## The verb taxonomy: what a score warrants you to say

There is a third failure mode, and it is the most insidious because it looks like good practice. You have done the interrogation. You have checked the base rate. The signal is real and reasonably calibrated. You hand the result to a language model to frame for the user. The model says: "This company sponsors H-1B visas for data science roles."

That sentence is not warranted by the evidence.

*Computational Skepticism for AI* has a verb taxonomy for exactly this problem. Different levels of evidence warrant different verbs: *hypothesize, suggest, observe, find, show, demonstrate, conclude, prove.* Each occupies a specific evidential posture. Using a verb stronger than the evidence warrants is an epistemic error — a category of error that happens at the output layer, after the data is already verified, and is therefore invisible to any data-quality check.

Here is what the evidence actually warrants, stated in calibrated language:

The DOL LCA disclosure data **shows** fifteen filings by this employer in the three-year window covered by the dataset. The USCIS approval data **shows** an 85% H-1B approval rate for this employer in the same period. The Sponsorship Scorer **observes** a signal consistent with active filing.

What the evidence does not warrant: *this company sponsors.* "Sponsors" is a present-tense claim about current employer policy, extrapolated from historical filings through a name-matching join that may have coverage gaps. The historical evidence supports a finding about what happened. It does not support an unhedged present-tense conclusion.

The practical rule: every claim the system emits should carry its warranted epistemic verb. "We observe fifteen filings" is a data claim. "We find a strong historical sponsorship signal" is a finding from the data. "This company sponsors" is a conclusion that requires more than the data can directly supply. Chapter 3 established the data-claim / model-judgment distinction. This chapter gives it a finer vocabulary.

## The honest ceiling

I want to be direct about what the verified-data contract cannot guarantee, because the temptation to overstate it is real — especially when the data checks out, the pipeline runs clean, and everything looks right.

The contract guarantees counts are real. It cannot guarantee the right thing was measured.

Coverage gaps are structural. The LCA dataset covers H-1B, H-1B1, and E-3 visas. A company that sponsors TN workers under the US-Mexico-Canada Agreement, or L-1 intracompany transfers, or O-1 extraordinary ability visas, will appear in none of these disclosures. From the dataset's perspective, they are not a sponsor. From the candidate's perspective, they are.

Name-matching failures are not edge cases. The LCA database and the USCIS approval database are maintained by different agencies under different administrative systems. A company that appears as "TechCorp LLC" in DOL filings and "TECHCORP" in USCIS data may join successfully or may not, depending on the exact normalization applied in the join script. The join script's coverage is documented in the audit; the audit reports how many rows matched and how many didn't. But it reports this at the aggregate level. The individual company that fell through the join looks identical to a genuine non-filer from the outside.

Freshness windows are a policy choice with real consequences. The default in this system uses a three-year lookback window. That is long enough to provide stable signal for established sponsors and short enough to exclude obviously stale data. But a company that sponsored aggressively in 2020–2022 and then implemented a blanket hiring freeze in 2023 will still score as a strong sponsor under this window. The filing history is real. The current hiring posture is unknown.

None of these are arguments for abandoning the data. They are arguments for being precise about what the data can and cannot say, and for making sure the output layer respects that precision. The honest ceiling is not a failure — it is the accurate description of what you have.

| What this chapter's method guarantees | What it cannot guarantee |
|---|---|
| The N rows in the dataset represent real filings | That all filings by this employer are in the dataset |
| The employer-name grouping reflects the filing record | That name-matching failures don't fragment prolific sponsors |
| The sponsorship signal is calibrated against base rates | That historical filing rates predict current hiring posture |
| Output verbs are warranted by the evidence | That the right visa category is covered for this candidate |
| Coverage gaps are labeled in the audit | That the gaps don't systematically exclude a type of employer |

*Table 5.2 — What this chapter adds to the floor Chapter 3 built.*

## Worked example: one company end to end

Let me make this concrete with the kind of trace Step 5 requires.

Take a mid-sized Cambridge biotech — the type of company Chapter 3 used to contrast verified and model-generated answers. It's a reasonable sponsorship candidate: talent-competitive field, specialized roles, graduate-intensive hiring.

I run the sponsorship dataset query. The result comes back: twelve LCA filings over three years, 80% H-1B approval rate, predominantly filed under job titles in "Life Sciences Researchers" SOC codes. The Sponsorship Scorer returns 0.68. So far, so good.

Now the trace. I pull the raw LCA rows for this employer. The name appears in two variants: "BioTechCo LLC" (ten rows) and "BioTechCo, LLC" (two rows — note the comma). The USCIS approval data has this employer under "BIOTECHCO LLC" (all caps, no comma). The join script normalized case but did not strip punctuation. The two rows filed under "BioTechCo, LLC" did not join to the USCIS data. They appear in the LCA count but not in the approval count. The approval rate calculation is therefore based on ten LCA filings, not twelve.

This does not change the conclusion dramatically — the employer is still a genuine historical sponsor. But it illustrates the mechanism. The gap is not a data error. Both records are correct. The join is the fragmentation point. And the dataset's missingness check reported zero missing values — because the rows are present, just in separate buckets that don't join.

Now the base rate check. In this SIC code (pharmaceutical and medicine manufacturing), the three-year LCA filing rate among employers in the DOL's universe is approximately 8%. The scorer returned 0.68. Working through the Bayes update: prior 0.08, likelihood ratio based on the observed filing count, posterior approximately 0.38–0.45 depending on assumptions. The 0.68 overstates the posterior probability by somewhere between 50% and 75%.

![A horizontal probability axis from zero to one with three markers — a low base-rate prior near 0.08 at the far left, the raw scorer output at 0.68 toward the right, and the corrected posterior landing between them in the high-thirties to mid-forties — with a correction arrow sweeping from the raw output leftward to the posterior and a faint anchor line from the prior showing the downward pull.](images/05-verifying-the-data-fig-04.png)
*Figure 5.4 — Base rate pulls the posterior down*

What does this mean for an F-1 student considering this company? It means the verified-data finding is: "We observe twelve LCA filings in three years and an 80% historical approval rate." It does not mean "this company sponsors." It means this company has a demonstrated filing history that makes them a reasonable target for further investigation — specifically, a direct inquiry about current H-1B sponsorship posture for the specific role and visa type relevant to you.

That's a more conservative conclusion than the raw score implies. It is also an honest one.

## The bridge to Chapter 6

Chapter 6 builds the first complete tool: the funding detector, which queries SEC Form D filings to find companies that just raised capital and are therefore under pressure to hire.

The method from this chapter travels with it. For every number the funding detector produces — round size, recency, investor profile — the same four questions apply: what is the base rate of companies in this category that are actually hiring? Is the signal calibrated? What does a false positive cost? What has changed since the filing date?

The practical difference from a user perspective is significant. A company that just closed a Series B and has zero verified sponsorship history is a different kind of lead than a company with fifteen LCA filings that raised no capital in three years. Neither signal alone is sufficient. Both together, interrogated against base rates, interpreted with calibrated verbs, and labeled with their coverage gaps, are what a trustworthy inference looks like.

That is the architecture of every chapter from here forward. The verified-data contract provides the floor: numbers trace to records. The epistemic-frame interrogation provides the next tier: those records are measuring what you think they're measuring, within documented limits. The verb taxonomy provides the output discipline: the system says exactly what the evidence warrants, and no more.

---

## Chapter 5 Exercises: Verifying the Data

**Project:** Your Own Reallocation Engine

**This chapter adds:** the data-trust layer of your engine — you interrogate the sponsorship dataset your own target list will run on, pin its base rates to the audit, and force every output into calibrated verbs before any score reaches a decision.

---

### Exercise 1 — When to Use AI

**The judgment:** In this chapter's work, AI assistance is appropriate for the following tasks:

- **Drafting the exploratory-analysis pass (Step 2).** — *Why AI works here:* producing distributions, missingness tables, and counts-by-employer is reformatting and boilerplate code generation against a fixed schema you can immediately run and eyeball; the output verifies itself the moment the script executes.
- **Writing a name-normalization function for employer variants.** — *Why AI works here:* the "BioTechCo LLC" / "BioTechCo, LLC" problem is a pattern-transformation task with a concrete pass/fail test — you have the raw rows to check the merge against, so a wrong function announces itself.
- **Generating candidate calibrated phrasings of a finding.** — *Why AI works here:* turning "twelve filings, 80% approval, prior 0.08" into several verb-taxonomy-correct sentences is option generation; you hold the taxonomy and pick the warranted one.

**The tell:** You know you are using AI appropriately when you can evaluate the output — when you have independent criteria to judge whether it is correct, complete, and fit for purpose. Here the criteria are the script's own run, the raw rows, and the verb taxonomy.

---

### Exercise 2 — When NOT to Use AI

**The judgment:** In this chapter's work, the following tasks require human judgment. Delegating them to AI is not appropriate — not because AI cannot produce output, but because AI output in these cases cannot be trusted without verification that requires the same expertise as doing the task yourself.

- **Supplying the base rate.** — *Why AI fails here:* the SIC-level filing rate is a number that must trace to the audit (the Chapter 3 contract); if a model produces "around 8%," that is fabrication wearing a decimal point — a missing-ground-truth problem, not a recall problem.
- **Deciding whether a missing company is a non-filer or a join failure.** — *Why AI fails here:* from the aggregate the two are identical; resolving it is a causal-identification problem that requires tracing one row end to end (Step 5) against records the model never sees.
- **Ruling on whether a score warrants the verb "sponsors."** — *Why AI fails here:* this is the exact failure the chapter names — a calibration-and-values judgment about present-tense claims across a time gap; the fluent model reaches for the strong verb precisely where the evidence forbids it.

**The tell:** You know you have crossed the line when you are using AI output as your reason for a conclusion rather than as a tool for reaching one. If you could not explain the conclusion without the AI, the AI did the work that should have been yours.

**Series connection:** This exercise trains **Tier 5 (Causal / identification)**, with a Tier 4 metacognitive edge. Distinguishing a structural join failure from a genuine absence, and refusing to extrapolate historical filings into a present-tense "sponsors," are identification problems: the data underdetermines the causal claim, and only a human tracing the mechanism can close the gap.

---

### Exercise 3 — LLM Exercise

**What you're building this chapter:** the written epistemic frame for your own target list's sponsorship dataset — the Step 6 output, stated in calibrated verbs — which becomes the trust note that travels with every score in later chapters.

**Tool:** Claude (claude.ai chat). A Claude Project is worth it if you'll iterate across your whole target list — put the verb taxonomy and your audit numbers in the project knowledge so every message inherits them.

**The Prompt:**

```
You are helping me write the epistemic frame for a sponsorship dataset I am
using to evaluate employers, following the six-step interrogation method:
(1) lock a prediction, (2) exploratory pass, (3) test metadata vs data,
(4) ask what is NOT in the data, (5) trace one row end to end, (6) write the
epistemic frame and compare to prediction.

Here are my verified audit numbers (already traced to script outputs — do not
change them, and do NOT invent any number I have not given you, especially the
base rate):

- Dataset: DOL LCA filings joined to USCIS H-1B approvals, 3-year window.
- Employer under review: a mid-size pharmaceutical/medicine-manufacturing firm.
- LCA filings: 12 over three years. H-1B approval rate: 80%.
- Sponsorship Scorer output: 0.68.
- SIC-level base rate (from my audit): 8% of employers in this SIC filed an LCA
  in the window.
- Known coverage gaps: dataset covers H-1B / H-1B1 / E-3 only (no TN, L-1, O-1);
  join normalizes case but not punctuation.

Do three things:

1. Write the epistemic-frame paragraph (Step 6): state precisely what this
   dataset represents, in one specific sentence — not "sponsorship data."

2. Apply the four base-rate diagnostic questions (base rate, calibration, cost
   distribution, freshness) and give the rough posterior direction relative to
   0.68. Show the reasoning; do not output a false-precision number.

3. Write the finding in TWO sentences using the verb taxonomy
   (hypothesize < suggest < observe < find < show < demonstrate < conclude <
   prove). Sentence 1 is a data claim using "observe" or "find." Sentence 2 is
   an explicit calibration note using "does not warrant" or "is consistent
   with." Do NOT use "sponsors" as an unqualified present-tense claim anywhere.

If any step requires a number I did not provide, say so explicitly instead of
estimating it.
```

**What this produces:** a short trust note — one epistemic-frame paragraph, a base-rate reasoning block, and a two-sentence calibrated finding — that you paste into your engine's notes for this employer.

**How to adapt this prompt:**
- *For your own project:* replace the employer details, the 12 / 80% / 0.68 figures, and the 8% base rate with your own audited numbers. Keep the "do not invent the base rate" instruction verbatim — it is the load-bearing line.
- *For ChatGPT / Gemini:* works as-is; on Gemini, add "think step by step before writing the finding" to stop it jumping to a confident verb.
- *For a Claude Project:* put the verb taxonomy and the four diagnostic questions in the system prompt; send only the audit numbers in the message.

**Connection to previous chapters:** this consumes the verified counts Chapter 3 forced you to source and the data-claim/model-judgment line it drew; here you give that line a finer vocabulary.

**Preview of next chapter:** in Chapter 6 the same four questions get pointed at SEC Form D funding signals — the LLM exercise there asks the model to flag what a fresh raise cannot tell you about hiring.

---

### Exercise 4 — CLI Exercise

**What you're building this chapter:** a punctuation-aware employer-name normalizer added to your fork's join step, plus a before/after join-coverage report showing how many rows the fix rescues.

**Tool:** Claude Code. The task spans reading the existing join script, editing it, re-running, and diffing two coverage numbers — a multi-step file workflow that suits an agentic CLI over chat.

**Skill level:** Intermediate — requires comfort running the repo's verification commands in a terminal.

**Setup:**

Before running this exercise, confirm:
- [ ] You have forked/cloned the engine repo and the join script under `scripts/` runs locally.
- [ ] At least one quarter of DOL LCA data and the USCIS approval data are downloaded (the Chapter 3 verify commands succeed).
- [ ] Your `CLAUDE.md` already carries the Chapter 3 rule: numbers come from script output, never from the model.

**The Task:**

```
Read the employer-name join logic in this repo (the script that matches DOL LCA
employer names to USCIS approval records). Do NOT modify any raw data files and
do NOT change the downloaded datasets.

1. Show me the current normalization: report exactly what transformations it
   applies (e.g. lowercasing) before matching.
2. Run the join as-is and record the current match count and unmatched count.
   Save this baseline to reports/join-coverage-before.txt.
3. Add a normalization step that strips punctuation and collapses whitespace
   (so "BioTechCo, LLC" and "BioTechCo LLC" normalize identically), as a new,
   clearly named function. Keep the original behavior available behind a flag.
4. Re-run the join. Save the new match/unmatched counts to
   reports/join-coverage-after.txt.
5. Print a diff of before vs after: how many previously-unmatched rows now join,
   and list 5 example employer names that were rescued.

Stop after step 5 and show me the diff. Do not "improve" the matching further
(no fuzzy/Levenshtein matching) — that is a separate decision I will make.
```

**Expected output:** an edited join script with a punctuation-stripping function behind a flag, two coverage report files, and a printed list of rescued employer names.

**What to inspect in the output:** check the rescued names by hand — are they genuinely the same legal filer, or did stripping punctuation merge two *different* companies (e.g. "Smith, Co" and "Smith Co" that are unrelated)? This is the chapter's point: the fix trades one coverage gap for a new false-merge risk.

**If it goes wrong:** the most common failure is the match count jumping implausibly — that means the normalization is now over-merging (e.g. it stripped so much that distinct firms collapse). Recover by tightening the function to strip only punctuation and case, not significant tokens like "LLC" vs "Inc", and re-run step 4–5; do not accept a coverage gain you can't explain row-by-row.

**CLAUDE.md / AGENTS.md note:** add a standing rule — *"Employer-name matching changes must report before/after coverage counts and a sample of rescued rows; never enable fuzzy matching without explicit human sign-off."* This keeps every future join edit honest.

---

### Exercise 5 — AI Validation Exercise

**What you're validating:** a pre-generated sponsorship summary an LLM produced from correct, verified numbers — the kind of output your engine will emit if you don't police the output layer.

**Validation type:** Reasoning chain (with a factual-claim component).

**Risk level:** High — every number in it is real, which is exactly what makes the overstatement convincing and hard to catch.

**Setup (pre-generated artifact — option b):** This chapter's lesson is the verb-overstatement failure mode, which a well-instructed prompt (Exercise 3) is designed *not* to produce. So validate this artifact instead — it traces to real figures but fails at the output layer:

> **Sponsorship summary — BioTechCo LLC.** Based on Department of Labor and USCIS
> records, BioTechCo LLC **sponsors H-1B visas** for life-sciences roles, with a
> strong 0.68 sponsorship probability. The company filed 12 LCAs over the past
> three years with an 80% approval rate, making it a **confirmed sponsor** and a
> high-priority target for your application. You can rely on this company to
> sponsor your visa.

**The Validation Task:**

Evaluate the AI output above using the following checklist. For each item, record: Pass / Fail / Cannot determine — and explain your reasoning.

```
Validation Checklist — Verifying the Data

□ Correctness: Does the output accurately reflect the chapter's core concept?
  Are the verbs warranted by the evidence, or does it use "sponsors" /
  "confirmed sponsor" as unqualified present-tense claims?
□ Completeness: Is anything important missing?
  Where is the base rate? Does it tell you that an 8% SIC prior pulls the
  posterior well below 0.68?
□ Scope: Did the AI stay within the task boundaries?
  Did it add an unrequested recommendation ("high-priority target," "you can
  rely on this company")?
□ Base-rate handling (chapter-specific): Does it treat 0.68 as a face-value
  probability, or as a signal that must be updated against the prior?
□ Coverage-gap labeling (chapter-specific): Does it disclose the H-1B/H-1B1/E-3-
  only coverage and the punctuation join gap that dropped 2 of the 12 filings?
□ Failure mode check: Does this output exhibit any of the following?
  - Fluent but wrong (plausible-sounding incorrect claims)
  - Verb overstatement (a stronger epistemic verb than the evidence warrants)
  - Missing ground truth (a present-posture claim the historical data can't
    support across the time gap)
```

**What to do with your findings:**
- If the output passes all checks: proceed to use it. (It will not — that is the point.)
- If the output fails one check: revise the prompt and re-run Exercise 3, then re-validate.
- If the output fails multiple checks or you cannot determine pass/fail: this is a "When NOT to Use AI" moment. Write the finding yourself using the verb taxonomy.

**AI Use Disclosure prompt:**
After completing this validation, write a two-sentence AI Use Disclosure:
> *Sentence 1:* What AI produced in this exercise and how you used it.
> *Sentence 2:* One specific thing the AI could not determine that required your judgment.

**Series connection:** This exercise trains the learner to catch **verb overstatement at the output layer** — fluent, fully-sourced text that claims more than its evidence warrants. It is **Tier 4 metacognitive supervision**: the capacity to know that a true number and a true verb are different trust questions, and that the machine, left alone, will reach for the verb the data has not earned.

---

## Prompts

### Figure 5.1 — The three-tier trust stack
**Files:** ../images/05-verifying-the-data-fig-01.svg · ../d3/05-verifying-the-data-fig-01.html
**Prompt:** A three-tier vertical stack on white, widest and most solid at the base, narrowing toward a provisional top tier. Render the tiers in neutral grays with the middle working tier marked in the one red accent, and put a left-side ascent arrow with an ochre gap callout naming where coverage gaps and base-rate mismatch live.

### Figure 5.2 — Name-matching fragmentation
**Files:** ../images/05-verifying-the-data-fig-02.svg · ../d3/05-verifying-the-data-fig-02.html
**Prompt:** Three small employer-name buckets on white inside a dotted ink boundary marking them one legal filer, with a single arrow to a larger consolidated true-count node on the right. Keep the fragment buckets in neutral gray and render the consolidated true count in the one red accent so the payoff reads as the point.

### Figure 5.3 — The six-step interrogation procedure
**Files:** ../images/05-verifying-the-data-fig-03.svg · ../d3/05-verifying-the-data-fig-03.html
**Prompt:** A strictly linear six-node spine on white connected by single-direction ink arrows, with a dashed reference arc closing from the final compare step back to the locked prediction. Hold the steps in neutral grays and emphasize the prediction-lock node in the one red accent so the closing loop between expectation and finding is unmistakable.

### Figure 5.4 — Base rate pulls the posterior down
**Files:** ../images/05-verifying-the-data-fig-04.svg · ../d3/05-verifying-the-data-fig-04.html
**Prompt:** A single horizontal probability axis from zero to one on white with three markers — a neutral prior near 0.08, the raw scorer output at 0.68, and the corrected posterior between them — plus a correction arrow sweeping the raw value down to the posterior. Mark the corrected posterior in the one red accent and the prior's downward pull as a faint anchor line, no false-precision numerals baked in.

# Chapter 6 — Where the Money Went: SEC Form D

<!-- voice-anchored: root style/VOICE.md. Anatomy: TIKTOC Part 10.
     Sourced from scripts/sec/README.md, data/80-days-to-stay day logs, CHAPTER-RESEARCH-MAP,
     "80 Days to Stay" essay. Draft. Never published. -->

There is a peculiar asymmetry in the way most people search for jobs. They look where the light is good — the big job boards, the recognizable logos, the company names they have heard of. The light is good there because those companies spent money to put it there. But the companies that most need to hire you right now, the ones sitting on fresh capital and a mandate to grow, often have no light on them at all. They are fourteen people in a converted warehouse in Cambridge. They just raised twelve million dollars. They have never crossed your radar. And the reason they haven't is not that they're obscure — it's that you've been using the wrong map.

The Securities and Exchange Commission maintains a public record of every private fundraise above a certain threshold. When a company closes a seed round, a Series A, a bridge round — when it takes in outside capital through what's called a private offering — it is legally required to file a form disclosing that fact. The form is called Form D. It has been sitting in a publicly accessible database for years, structured and searchable, containing the company name, its address, its industry, the amount raised, and when. In one snapshot of that record, there were over **568,000** companies that had reported raising money, and nearly **247,000** of them had raised at least five million dollars.[^formd]

![A large outer rectangle represents roughly 568,000 companies that filed Form D; a smaller nested rectangle represents the roughly 247,000 that raised at least five million dollars.](images/06-where-the-money-went-sec-form-d-fig-01.png)
*Figure 6.1 — The Form D corpus and the funded subset*

Almost no job seeker has ever looked at it.

This is not because the data is hard to find. It is because the idea of looking there has not occurred to most people. The job board has trained a generation of candidates to think that companies find workers, not that workers find companies. Form D inverts this. Instead of waiting for a company to post a job, you identify the companies that just received the resources to hire — before the posting exists, before the recruiter has been briefed, often before the hiring manager has even written the job description. You show up earlier in the process, which is almost always an advantage.

The logic is simple enough to state in a sentence: **a company that just raised money is a company under pressure to spend it on people.** Early-stage companies don't raise capital to sit on it. They raise it to execute — and execution, in a young company, means hiring. Funding recency is therefore a leading indicator. A company that filed Form D for a twenty-million-dollar round eight weeks ago will be hiring in the next two quarters with near-certainty. The question is not whether they'll hire. The question is whether you'll know they exist.

This chapter is about making sure you know.

---

The pipeline for turning raw Form D filings into a usable shortlist lives in `scripts/sec/`, and the data it works with lives in `data/sec/form-d/` across three layers: `raw/` holds exactly what the SEC published, `extracted/` holds the parsed output, and `processed/` holds the cleaned and deduplicated result. The three-layer structure matters not for aesthetic reasons but for epistemic ones. If you look at a processed number and wonder where it came from, you can trace it back through extracted and into raw. That traceability is part of a larger contract running through this book: every company, every amount, every date in a real run comes from a filing, not from a guess. The pipeline is the source of truth. The audit log it writes is the receipt.

Running it is a sequence of seven commands:

```bash
cd scripts/sec

# 1. Download the Form D filing archives for the quarters you want
python download-form-d-quarters.py

# 2. Pull in the most recent quarters (keeps the archive current)
python refresh-recent-sec-quarters.py

# 3. Combine quarters into one dataset
python sec-combine-quarters.py

# 4. Filter to real offerings above your funding threshold
python sec-filter.py

# 5. Collapse to one record per company
python sec-unique.py

# 6. Infer each company's web domain
python sec-domain-inference.py

# 7. Flatten to the final processed table
python sec-flatten.py
```

![A seven-step linear pipeline arranged across three horizontal layer bands — raw, extracted, processed — with each step descending toward the processed layer as it moves left to right, and a small audit-receipt marker beside every step.](images/06-where-the-money-went-sec-form-d-fig-02.png)
*Figure 6.2 — The seven-step Form D pipeline across three layers*

Each step writes its output into the appropriate layer of `data/sec/form-d/` and leaves an audit file alongside it. The final product is a flat table: one row per funded company, with amount, date, industry, location, and — where the inference engine succeeded — a web domain. That last column matters more than it might seem. A company name without a website is a dead end. The domain inference step tries to give you a way in.

The inference works by guessing and verifying URLs from company names. It gets the right answer about sixty-two percent of the time.[^domain] Which means roughly thirty-eight percent of funded companies still need a human to locate the website before anything further can happen. This is not a bug in the pipeline — it is a feature of the problem. Some work cannot be automated, and the pipeline is honest about where it stops and you begin.

---

The hard part of working with Form D is not running the pipeline. It is resisting a mistake that is easy to make once the ranked table is in front of you: sorting by dollar amount and concluding that bigger is better.

It is not.

A two-hundred-million-dollar late-stage round is not a hiring opportunity in the same sense as a six-million-dollar seed. The company that raised two hundred million is probably large enough to have a formal recruiting apparatus — a parser-gated application system, a hundred applicants for every role, a process designed to process. The company that raised six million at fourteen people is a founder who will read your email. The signal in Form D is not the size of the raise. The signal is the combination of recency and company size. A small company that just got funded is a company where you can make a difference and where the people deciding to hire you will know your name.

![A two-by-two quadrant map with funding recency on the horizontal axis and company size on the vertical axis; the small-and-recently-funded bottom-right quadrant is emphasized as the target zone, while large-company quadrants are marked as lower-value leads regardless of raise size.](images/06-where-the-money-went-sec-form-d-fig-03.png)
*Figure 6.3 — Recency × size beats raise amount*

Recency degrades. The hiring surge that follows a funding announcement is real and it is time-limited. In the quarters immediately after a raise, a company is actively trying to build the team the investors paid for. Eighteen months later, the urgency has passed — either they hired or they didn't, and the fresh-capital energy has moved on to execution. When you filter the table, the recency cutoff matters: within twelve months is a signal; beyond eighteen months is history.

The geography filter matters for obvious reasons. A biotech seed round in San Diego is not a useful lead for someone who needs to work in Boston. But there is a subtler geographic point worth making. Early-stage companies cluster. Cambridge, MA has a density of biotech labs that no job board adequately surfaces. Filtering Form D to a metro area and a relevant industry will often reveal a population of companies that simply does not appear in a normal job search — not because the jobs aren't there, but because the companies haven't yet bought the advertising that makes them visible.

---

Consider a concrete case, the kind of thing that actually happens when you run this pipeline. A data-science graduate is targeting Boston, open to biotech and AI. The pipeline runs over the most recent quarters. Filtering to Massachusetts, raised at least five million, filed within twelve months, sorted by recency, produces a list. Near the top: a few names the graduate recognizes. Three rows down: a Cambridge biotech with a twelve-million-dollar raise eight weeks ago that has no job board presence, no careers page in search results, and no recruiter outreach in anyone's inbox. It exists in this search because it filed a form with the SEC. It would not exist in any other search the graduate might run.

That company goes on the target list above several brand names. Not because it's more prestigious. Because it just got the money, and at its size, a single hire — one good data scientist — changes what they can do. The job board optimizes for visibility. The Form D search optimizes for timing. Timing is almost always worth more.

The limit of this approach is equally concrete and equally worth stating plainly. Form D tells you a company raised money. It does not tell you what they will hire for, whether a given role fits your background, whether they have ever sponsored a visa, or whether the posting you eventually find reflects a real and open position. Funded is a necessary signal. It is not a sufficient one. It narrows the population of companies worth investigating — it does not close the investigation. The next several chapters add the facts that Form D cannot supply: whether the company has the machinery to sponsor visas, whether the specific roles they post match your profile, whether the geography works, and whether the humans at the company are actually responsive.

Think of Form D as triangulation. You are not picking your next employer from this table. You are identifying which companies are worth the effort of deeper research. The companies that make the list are the ones where the effort has a real chance of paying off — where the money is recent, the size is right, and the industry is relevant. Everything else is noise.

---

There is one more thing the pipeline cannot do that is worth being explicit about. Sixty-two percent domain inference sounds like a high number until you think about what the thirty-eight percent represents. Each company in that remainder is a funded firm you cannot easily reach without further work. Some of them are the most interesting leads — small, obscure, operating without a marketing department. The fact that the pipeline couldn't find their website is not evidence that they're not worth pursuing. It is evidence that finding them requires a human judgment that no script can substitute for.

![A single horizontal bar split into two segments: a larger left segment for the roughly sixty-two percent of companies whose domain was inferred automatically, and a smaller, emphasized right segment for the roughly thirty-eight percent that still require a human to locate the site.](images/06-where-the-money-went-sec-form-d-fig-04.png)
*Figure 6.4 — Domain inference: where the pipeline stops and you begin*

This is not an accident of implementation. It is a structural property of the search problem. The companies that are hardest to find automatically are often the ones where showing up — actually tracking down the website, finding the right person, writing the email — yields the most asymmetric return. Everyone else gave up at the domain lookup step. You didn't.

The pipeline's job is to get you to the right population and sort it by the strongest signal available, which is recency. Your job is to take that shortlist and close the gap between a row in a table and a real conversation with a real person. Form D is where you find the companies worth having that conversation with.

## Chapter 6 Exercises: Where the Money Went

**Project:** Your Own Reallocation Engine

**This chapter adds:** the funding-recency signal — you run the SEC Form D pipeline against your target metro and industry to produce a shortlist of recently funded companies, the population your sponsorship and liveness checks will work on next.

---

### Exercise 1 — When to Use AI

**The judgment:** In this chapter's work, AI assistance is appropriate for the following tasks:

- **Summarizing the pipeline's audit (quarters processed, row counts, drops).** — *Why AI works here:* it reformats numbers the audit already produced; you check every figure against the audit file.
- **Generating candidate website URLs for a company whose domain inference failed.** — *Why AI works here:* this is pattern-based guessing you immediately verify by visiting the URL — the model proposes, the browser confirms.
- **Drafting a first-contact email to a founder once you've found a high-fit funded firm.** — *Why AI works here:* outreach drafting against facts you supply; you judge tone and accuracy before sending.

**The tell:** You know you are using AI appropriately when you can evaluate the output — when you have independent criteria to judge whether it is correct, complete, and fit for purpose. Here the criteria are the audit file and the live website.

---

### Exercise 2 — When NOT to Use AI

**The judgment:** In this chapter's work, the following tasks require human judgment. Delegating them to AI is not appropriate — not because AI cannot produce output, but because AI output in these cases cannot be trusted without verification that requires the same expertise as doing the task yourself.

- **Producing the funded-company list, amounts, or dates.** — *Why AI fails here:* these must come from Form D filings through the pipeline; a model asked "which Boston biotechs raised money recently?" returns plausible names and numbers, not filed ones — fabrication.
- **Confirming a domain-inference match is the right company.** — *Why AI fails here:* inference is right ~62% of the time; the model is exactly as likely to confidently assert the wrong company's site — a missing-ground-truth problem only a human visit settles.
- **Deciding which funded company is the best target.** — *Why AI fails here:* the chapter's central trap is sorting by dollar amount; a model will happily rank "biggest raise first," which is the wrong signal — recency × right-size is a judgment tied to your goals.

**The tell:** You know you have crossed the line when you are using AI output as your reason for a conclusion rather than as a tool for reaching one. If you could not explain the conclusion without the AI, the AI did the work that should have been yours.

**Series connection:** This exercise trains **Tier 4 (Metacognitive supervision)** with a **Tier 5 (Causal)** edge — distinguishing a counted filing from a plausible guess, and resisting the "bigger raise = better lead" correlation that the size signal does not actually support.

---

### Exercise 3 — LLM Exercise

**What you're building this chapter:** a ranked research shortlist from your pipeline output — ordered by recency and right-size, not dollar amount — plus a first-contact draft for the top lead.

**Tool:** Claude (claude.ai chat). You paste real rows from your processed table and interrogate them; chat is the right fit.

**The Prompt:**

```
Below are rows from a processed SEC Form D table I generated — real funded
companies in my target area. Each row has: company, amount raised, date filed,
industry, location, and (where found) a domain. Do NOT add companies, amounts,
or dates; work only with what I paste.

1. Rank these leads for a job seeker who needs to be HIRED SOON and wants to
   matter at the company. Rank by funding RECENCY and right-size (small, recently
   funded firms where one hire moves the needle), NOT by dollar amount. Explain
   the ranking in one line each, and explicitly flag any case where the biggest
   raise is NOT the best lead.
2. For the top lead with a known domain, draft a 120-word first-contact email to
   a founder/hiring lead: specific, non-generic, referencing that they recently
   raised and why I'm reaching out before a posting exists.
3. For any lead missing a domain, list 3 candidate URLs I should check by hand —
   labeled as guesses to verify, not answers.

--- PASTE YOUR TABLE ROWS BELOW ---
[paste 8–12 rows from data/sec/form-d/processed/]
```

**What this produces:** a recency-and-size ranking with the "bigger isn't better" cases flagged, one outreach draft, and a short list of domains to verify by hand.

**How to adapt this prompt:**
- *For your own project:* paste your real processed rows. The prompt is inert without them — and pasting them is what keeps the model from inventing companies.
- *For ChatGPT / Gemini:* works as-is; both may re-sort by amount out of habit — keep the "NOT by dollar amount" instruction in caps.
- *For a Claude Project:* store your target metro, industry, funding floor, and recency window in the instructions so every ranking inherits your filters.

**Connection to previous chapters:** the ranked leads populate the `targets.csv` you built in Chapter 2; the "verify the domain by hand" step is Chapter 1's interrogation reflex in miniature.

**Preview of next chapter:** Chapter 7 takes this funded shortlist and asks the harder question — which of them have actually sponsored visas — by scoring them against DOL and USCIS records.

---

### Exercise 4 — CLI Exercise

**What you're building this chapter:** your own processed Form D table — a funded-company shortlist filtered to your metro, industry, and recency window, with its row count confirmed against the audit.

**Tool:** Claude Code. Running the seven-step `scripts/sec/` pipeline, reading audits, and applying filters is a multi-command terminal workflow.

**Skill level:** Intermediate — Python pipeline with several steps; recoverable per step.

**Setup:**

Before running this exercise, confirm:
- [ ] Your forked repo has `scripts/sec/` and the `data/sec/form-d/{raw,extracted,processed}/` layout.
- [ ] Python dependencies for the SEC scripts are installed.
- [ ] You've decided your filter thresholds: metro/state, funding floor, recency window.

**The Task:**

```
Run the SEC Form D pipeline in scripts/sec/ to produce a processed funded-company
table for my target area. Do not edit raw data; do not invent any company.

1. Run the pipeline in order, stopping and showing me any error before
   continuing:
     python download-form-d-quarters.py
     python refresh-recent-sec-quarters.py
     python sec-combine-quarters.py
     python sec-filter.py        # apply my funding floor
     python sec-unique.py
     python sec-domain-inference.py
     python sec-flatten.py
2. After sec-flatten, report the processed row count AND the matching number
   from the audit file — confirm they agree. If they differ, stop and show me.
3. Filter the processed table to my target state/metro and a 12-month recency
   window; save it to reports/funded-shortlist.csv.
4. Count and list the companies where domain inference FAILED (no domain) — these
   are my manual-lookup queue.
5. Show me the shortlist row count, the audit row count, and the missing-domain
   count. Stop.
```

**Expected output:** `reports/funded-shortlist.csv` filtered to your area and recency, plus a printed count of domain-inference failures to chase by hand.

**What to inspect in the output:** confirm the processed row count matches the audit (Chapter 3's discipline). Spot-check three rows back through `extracted/` to `raw/` — does the amount trace? Are the missing-domain companies genuinely missing, or did inference attach a wrong domain (worse than none)?

**If it goes wrong:** the most common failure is an empty or tiny processed table — usually the funding floor in `sec-filter.py` was set too high or the wrong quarters downloaded. Recover by checking the filter threshold and the combine step's audit; do not let the agent "fill in" companies to make the table look populated.

**CLAUDE.md / AGENTS.md note:** add a standing rule — *"Form D shortlists are sorted by recency and right-size, never by raise amount; domain-inference results are unverified until a human opens the site."* This bakes the chapter's two judgments into the repo.

---

### Exercise 5 — AI Validation Exercise

**What you're validating:** an AI-generated ranking of funded companies — the kind that confidently optimizes the wrong variable.

**Validation type:** Reasoning chain (over structured data).

**Risk level:** Medium — a wrong ranking sends your scarce application time at big firms with formal gates instead of founders who'll read your email.

**Setup (pre-generated artifact — option b):** This chapter's lesson is "bigger raise ≠ better lead," so validate this pre-generated ranking:

> **Top funded targets for you (ranked):**
> 1. MegaCloud Inc. — raised $220M (Series D, 14 months ago), ~3,000 employees.
>    *Largest raise = most hiring; apply here first.*
> 2. DataCorp — raised $90M (Series C, 11 months ago), ~600 employees.
> 3. Helix Bio — raised $6M (seed, 7 weeks ago), ~14 employees.
>    *Small raise, lowest priority.*
> All three are strong because they're well funded. Start at the top and work down.

**The Validation Task:**

Evaluate the AI output above using the following checklist. For each item, record: Pass / Fail / Cannot determine — and explain your reasoning.

```
Validation Checklist — Where the Money Went

□ Correctness: Is the list ranked by the signal the chapter says matters
  (recency × right-size) or by dollar amount?
□ Completeness: Does it account for how a 3,000-person firm hires (formal gates,
  100 applicants/role) vs. a 14-person firm (the founder reads your email)?
□ Scope: Did it conflate "well funded" with "good hiring lead"?
□ Recency check (chapter-specific): A 14-month-old round vs. a 7-week-old round —
  which is the live hiring signal? Does the ranking reflect that?
□ Size check (chapter-specific): At which company does one hire change what they
  can do? Is that company ranked first or last?
□ Failure mode check: Does this output exhibit any of the following?
  - Fluent but wrong (a confident ranking on the wrong axis)
  - Sorting by dollar amount (the chapter's named error)
  - Missing ground truth (no trace to the filing dates that justify recency)
```

**What to do with your findings:**
- If the output passes all checks: use it. (It will not — it inverts the chapter's argument by ranking Helix Bio last.)
- If it fails one check: re-rank by recency and right-size yourself and note which company moved most.
- If it fails multiple checks or you cannot determine pass/fail: this is a "When NOT to Use AI" moment — you set the ranking criteria; the model only formats.

**AI Use Disclosure prompt:**
After completing this validation, write a two-sentence AI Use Disclosure:
> *Sentence 1:* What AI produced in this exercise and how you used it.
> *Sentence 2:* One specific thing the AI could not determine that required your judgment.

**Series connection:** This exercise trains **Tier 4 metacognitive supervision** — catching a fluent ranking that optimizes the loudest number (raise size) instead of the predictive one (recency × size). The pipeline finds the companies; the judgment about how to order them is yours.

---

## Key terms

- **Form D:** the SEC filing a company makes when it raises money in a private offering; public, structured, and rich with hiring signal.
- **Funding recency:** how recently a company raised; a leading indicator of near-term hiring and a twenty-percent factor in the sponsorship tier.
- **Entity resolution:** collapsing the many spellings of one company into a single record.
- **Domain inference:** automatically guessing and verifying a company's website so a funded firm can actually be reached.

## Run-log prompt

Record the quarters processed, the audited row count, your filter thresholds (geography, funding floor, recency), and the count of high-fit firms whose domains you had to find by hand.

[^formd]: Aggregate Form D counts (≈568,707 filers; ≈246,572 raising ≥$5M) from the "80 Days to Stay" build logs (`data/80-days-to-stay/`) and connecting essay. **[verify]** against a current pipeline run.

[^domain]: ~62% domain-inference success (≈38% requiring manual lookup) from the "80 Days to Stay" build logs and the "80 Days to Stay: Connecting Recent Funding" essay. **[verify]**

## Prompts

### Figure 6.1 — The Form D corpus and the funded subset
**Files:** ../images/06-where-the-money-went-sec-form-d-fig-01.svg · ../d3/06-where-the-money-went-sec-form-d-fig-01.html
**Prompt:** Brutalist nested-proportion figure: one large neutral-fill rectangle for the full Form D population (~568,000 filers) fully enclosing a smaller red-stroked rectangle (~247,000 raising ≥$5M) sized at a little under half the outer area. One red, one canvas, hairline strokes; the proportion between the two regions must be honest.

### Figure 6.2 — The seven-step Form D pipeline across three layers
**Files:** ../images/06-where-the-money-went-sec-form-d-fig-02.svg · ../d3/06-where-the-money-went-sec-form-d-fig-02.html
**Prompt:** Brutalist layer-banded flowchart: three faint horizontal bands (raw / extracted / processed) with seven step nodes marching left to right and descending from raw into processed, single-direction arrows, a small audit-receipt marker beside each step. Ink and red only, mono labels, no decoration.

### Figure 6.3 — Recency × size beats raise amount
**Files:** ../images/06-where-the-money-went-sec-form-d-fig-03.svg · ../d3/06-where-the-money-went-sec-form-d-fig-03.html
**Prompt:** Brutalist 2×2 quadrant map: horizontal axis funding recency (stale → recent), vertical axis company size (large → small); emphasize the bottom-right small-and-recent quadrant in red as the target zone, render large-company quadrants as muted lower-value leads. Hairline axes, one accent color, sentence-case labels.

### Figure 6.4 — Domain inference: where the pipeline stops and you begin
**Files:** ../images/06-where-the-money-went-sec-form-d-fig-04.svg · ../d3/06-where-the-money-went-sec-form-d-fig-04.html
**Prompt:** Brutalist single-bar proportion split anchored at zero: a larger ~62% inferred segment in neutral ink and a smaller ~38% manual-lookup segment emphasized in ochre as the human-handoff line. Two segments only, no pie, no baked percentages as art.
# Chapter 7 — Who Sponsors: The 80 Days Sponsorship Scorer
*Why the record always outranks the reputation.*

Here is something that bothers me every time I see a job seeker's target list: the names on it are chosen for how they feel, not for what they've done. A household brand — a logo you've worn on a t-shirt — sits at the top. Fifteen companies you've never heard of sit nowhere, because you've never heard of them. And that ranking is exactly backwards, in a way that is measurable, sourced, and correctable.

A Cambridge biotech with no consumer presence files fifteen Labor Condition Applications over three years and maintains an 85% H-1B approval rate. The household brand files essentially zero LCAs for roles like yours. For a candidate who needs sponsorship, the unknown biotech is a vastly better target — not by opinion, not by vibe, but by the public record. The whole problem is that prestige is loud and the visa record is quiet. This chapter makes the quiet record louder.

![A grouped horizontal bar chart comparing a famous brand against an unknown biotech across LCA count, approval rate, funding recency, and composite score; the unknown biotech wins on the record even though the famous brand wins on name recognition.](images/07-who-sponsors-the-80-days-sponsorship-scorer-fig-05.png)
*Figure 7.1 — Famous brand versus unknown biotech: the ranking flip*

<!-- → [CHART: horizontal bar chart showing a hypothetical pair of companies — "Famous Brand" vs. "Unknown Biotech" — with bars for LCA count, approval rate, funding recency, and composite score; the visual should make the ranking flip visceral and immediate] -->

What I want you to notice before we go further: this is not about dismissing well-known companies. Some famous companies are prolific sponsors. Some unknown biotechs file nothing. The point is that you do not know which is which from the name alone — you only know from the record. Everything in this chapter is about reading the record correctly.

---

The record lives in three datasets, all public, all free.

The first is **SEC Form D**, which you met in Chapter 6. It tells you when a company raised money and how much. Funding recency matters because a company that raised $12 million eight weeks ago is a different entity than one whose last round was three years ago and whose runway is unclear.

The second is the **DOL LCA disclosure data** — every Labor Condition Application an employer files with the Department of Labor as a precondition for hiring a foreign worker. An LCA is not the visa itself; it is the step before. It says: this employer is willing, organized, and legally set up to go through the process. A company with a filing history has built the machinery. A company with no filings either has not built it or has decided not to use it for roles like yours. Both conclusions matter.

The third is the **USCIS H-1B Employer Data Hub** — actual approvals and denials by employer and year. This is not intent; it is outcome. An employer can file LCAs and still fail at the H-1B stage. The approval rate tells you how the filings resolve.

![A convergent pipeline diagram: three public datasets — SEC Form D, DOL LCA data, and the USCIS H-1B Hub — feed a single sponsorship scorer node, with a fourth, lighter company-size input joining from below.](images/07-who-sponsors-the-80-days-sponsorship-scorer-fig-01.png)
*Figure 7.2 — Three records into one score*

<!-- → [DIAGRAM: three-node pipeline showing SEC Form D → DOL LCA Data → USCIS H-1B Hub flowing into a "Sponsorship Scorer" node, with arrows labeled "funding recency," "filing behavior," and "approval rate"; include a fourth node for "company-size signals" feeding in from below] -->

These three datasets are joined by the **80 Days pipeline** on resolved company names. That last phrase — resolved company names — is doing more work than it appears to. "Google LLC," "Google Inc.," and "Alphabet" must be recognized as one entity or a real sponsor looks like a stranger in the data. The join is the hard part. An "Unknown" tier caused by a failed name match is not the same as a true absence of filings, and I will return to that distinction because it is one of the two most important things in this chapter.

---

The scorer reduces those three datasets into a single number:

> **P(sponsorship) = LCA filing rate (3-yr) × 0.40 + H-1B approval rate × 0.30 + funding recency × 0.20 + company-size signals × 0.10**

Read those weights as a claim, and ask whether you agree with it.

The LCA filing rate carries 40% of the weight because filing is the most direct revealed action available in public data. A company that files LCAs has made a decision — to build the legal infrastructure, engage immigration counsel, pay the fees, and go through the process. That decision is load-bearing in a way that a company's reputation is not. You can be famous without ever filing an LCA. You can be unknown and file thirty.

The H-1B approval rate carries 30% because filings that don't succeed tell a different story than filings that do. An employer with a 40% approval rate and an employer with an 85% approval rate are both sponsors in name. In practice, they are different bets.

| Component (weight) | Employer A — high filing, low approval | Employer B — moderate filing, high approval |
|---|---|---|
| LCA filing rate (×0.40) | High — files often, ~0.90 | Moderate — files steadily, ~0.55 |
| H-1B approval rate (×0.30) | Low — ~0.40 | High — ~0.85 |
| Funding recency (×0.20) | Recent, ~0.80 | Recent, ~0.80 |
| Company-size signals (×0.10) | Neutral, ~0.60 | Neutral, ~0.60 |
| **Composite** | **≈ 0.66 → Likely** | **≈ 0.69 → Likely / Proven edge** |
| What the profile implies | Willing and organized, but filings resolve poorly — possible role mismatch, weak counsel, or aggressive over-filing | Selective filer whose filings actually convert — a cleaner process, even at lower volume |

*Two employers can reach a similar composite for opposite reasons. The filing rate says "they try"; the approval rate says "it works." Read both before you read the tier.*

Funding recency carries 20% because the question is not just whether a company has sponsored in the past but whether it has the resources and growth trajectory to do so now. A company that raised eight weeks ago is in a different hiring skill than one that is managing a quiet contraction.

Company-size signals carry 10% — not because size is unimportant, but because its effect is already partially captured by the other three. A fourteen-person lab and a ten-thousand-person firm behave differently on average, but the record is the record. A small lab with a strong filing history is better evidence than a large firm with none.

The composite probability then maps to a tier. **Proven** means strong, recent filing history and high approval — the evidence is unambiguous. **Likely** means some evidence: a few filings, or strong funding plus partial history. **Unknown** means no evidence either way. **Avoid** means evidence the company does *not* sponsor in your kind of role — a clear zero-history non-sponsor that the engine should actively skip rather than merely lack data on.

I should flag something here. The system design document underlying the 80 Days pipeline describes three tiers — Proven, Likely, Unknown. The plain-language summary of the same system adds Avoid as a fourth. This chapter uses four tiers because "Avoid" does real work: it lets the engine actively deprioritize known non-sponsors rather than merely lacking data on them. The tier set and exact probability thresholds for each boundary need to be reconciled against the SDD before this goes to print. I am being transparent about that because the tier labels and thresholds are the output a reader will act on, and the distinction between a system that has three skills and one that has four is not cosmetic.

![A horizontal spectrum running from Avoid through Unknown and Likely to Proven, with ascending evidence bands on the axis and a small action cue beneath each tier; Unknown is rendered distinct from Avoid.](images/07-who-sponsors-the-80-days-sponsorship-scorer-fig-03.png)
*Figure 7.3 — The four-tier sponsorship spectrum*

<!-- → [INFOGRAPHIC: a horizontal spectrum from "Avoid" through "Unknown" through "Likely" to "Proven," with approximate probability ranges on the axis and brief action cues below each tier — what the engine does and what you do] -->

---

Now let me show you what this looks like on a real case — or rather, a case that is real in structure, with illustrative numbers, so you can see how the reasoning works before you run it on your own list.

Return to the Cambridge biotech. LCA filings: 15 over three years. That is a strong filing rate for a company of this size — they are not dabbling in sponsorship, they have built the process. H-1B approval rate: 85%. Funding: $12 million raised eight weeks ago, which puts the recency score near maximum. Size: roughly 40 employees, which is mid-small.

Running the weights: the LCA rate (×0.40) dominates because it is high and the weight is highest. The approval rate (×0.30) confirms the filings are not just optimistic paperwork. The funding recency (×0.20) says they have the resources to keep going. Size (×0.10) is neutral-to-positive — a 40-person lab is not so large that bureaucracy slows everything down and not so small that one departure breaks the immigration infrastructure. The composite lands well into Proven.

Now run the same logic on the household name. LCA rate: approximately zero for roles like yours. That ×0.40 term contributes nothing. No relevant H-1B approvals in your role category. The funding and size numbers are strong — they have the money, they have the infrastructure — but those terms together carry only 30% of the weight, and they cannot rescue a zero on the 70% that measures actual sponsorship behavior. The company lands in Avoid.

![Two side-by-side stacked bars showing the weighted composite score for each company; the unknown biotech builds to a high total from all four weighted segments while the famous brand's filing-rate and approval-rate segments — together seventy percent — are empty, collapsing its bar into the Avoid range.](images/07-who-sponsors-the-80-days-sponsorship-scorer-fig-02.png)
*Figure 7.4 — Weighted score: the ranking flip*

<!-- → [CHART: two stacked bar charts side-by-side showing the weighted score breakdown for each company — each bar segment labeled with its component and weight, making visible how the "Avoid" company's 70% goes to zero while the Proven company builds from all four components] -->

The decision is not close. The unknown biotech goes to the top of the active application list. The household name gets skipped. That is the backwards ranking, now defended by four sourced numbers.

But I want to be careful here. The record is a rear-view mirror. A company that sponsored heavily for three years may have frozen sponsorship last month. The immigration attorney who drove those 85% approvals may have left in March and taken the process knowledge with them. The LCA data is published on a lag. A company that raises a new round and starts hiring aggressively may look Unknown today and Proven in six months — and the record will not tell you that yet.

This is not a reason to distrust the tier. It is a reason to hold the tier correctly: as a well-evidenced prior, not a guarantee. You are Bayesian here. The tier tells you where the evidence points. The conversation you have with the recruiter is where you update.

---

The most common misread of this system is treating Unknown as Avoid. I want to spend a moment on this because it is not a subtle error — it is the error that throws away exactly the companies Chapter 6 worked to surface.

*Avoid* means the record shows this company does not sponsor your kind of role. The evidence is there; it is just negative. *Unknown* means the record is silent. Silent is different from negative. A company is Unknown for one of two reasons: either there is genuinely no filing history (they have never sponsored, or they are so young that the data does not exist yet), or the name did not match when the pipeline joined the datasets.

Those two causes of Unknown require opposite responses. A true absence of filings on a three-year-old company with strong funding is a prompt to look for direct sponsorship signals — a careers page that says "visa sponsorship available," a LinkedIn post about a recent hire on an H-1B, a direct question to the recruiter. A failed name match is a data problem you fix by resolving the entity and re-running. You cannot tell which you are dealing with by looking at the tier alone. You tell by reading the join-coverage audit.

| | True Unknown | Name-Match Artifact Unknown |
|---|---|---|
| How to identify it | Company matched in the join, but no filings found; often young or never-sponsoring | Company failed to match in the join; flagged in low join-coverage runs |
| What the record shows | Genuine silence — no LCA or H-1B history exists yet | The history may exist under a different legal name ("Inc." vs "LLC" vs parent) |
| What action it requires | Look for direct signals — careers page, recruiter question, recent H-1B hire posts | Resolve the entity (map the name variants) and re-run the join |
| Cost of treating it as Avoid | You discard a young, well-funded company that may sponsor — exactly the lead Chapter 6 surfaced | You discard a proven sponsor because of a spelling mismatch — a pure data error |

*Both look identical from the tier alone. The join-coverage number is what tells them apart: low coverage raises the odds that an Unknown is an artifact, not a verdict.*

The pipeline exposes this. From the project root:

```bash
cd scripts/sec
python validate-h1b-join-sample.py
```

checks the company-name join against USCIS H-1B data, and:

```bash
python scripts/audit-sec-dol-h1b-data.py
```

audits the full SEC + DOL + H-1B join coverage. The output is a number: how many companies on your shortlist matched, how many failed to match, and therefore how much of your list the tier actually covers. You read that coverage number before trusting any Unknown. If 30% of your shortlist failed to match, a significant fraction of your Unknowns are artifacts, not verdicts.

---

Let me say what I actually cannot see from this data, because intellectual honesty requires it.

The pipeline knows a company filed fifteen LCAs. It cannot know those fifteen were all for senior principal scientists and the company has a quiet policy against sponsoring entry-level hires. It knows an 85% approval rate; it cannot know that the attorney who drove those approvals left in March. It cannot know that an Avoid company just hired a new VP of Engineering who is changing the sponsorship policy this quarter. It cannot know that a Proven company just went through a round of layoffs and has frozen all new sponsorship for six months.

The tier is what the public record supports. What the public record cannot support is inference about a specific role, a specific month, a specific team. That is not a flaw in the scorer — it is the honest boundary of what any retrospective dataset can tell you. The boundary matters because crossing it silently is how you make bad decisions with confident numbers.

What the record can tell you, reliably, is: has this company demonstrated that it is willing and able to sponsor? That is the question the tier answers. Whether this company will sponsor you, in this role, right now — that is the question the tier informs but cannot answer.

![A decision tree that resolves why a company landed in the Unknown tier and what to do: from an Unknown entry node, a join-coverage decision splits a likely name-match artifact (resolve the entity and re-run) from a true absence (seek direct sponsorship signals), making visible that Unknown is never read as Avoid.](images/07-who-sponsors-the-80-days-sponsorship-scorer-fig-04.png)
*Figure 7.5 — Why a company is "Unknown": three causes, three responses*

<!-- → [DIAGRAM: a decision tree beginning at "Tier assigned" — branching from Proven/Likely to "Target actively" and then to "Verify role type matches filing history," from Unknown to "Check coverage / resolve name match" and "Look for direct signals," and from Avoid to "Skip — reallocate application time (see Chapter 2)"] -->

The last thing I want to leave you with is the decision rule, because knowing the tier is only useful if you know what to do with it.

Proven and Likely justify the targeted two hours of application effort from Chapter 2. These are companies where the evidence supports the investment. Unknown — if fit and funding are strong — stays on the list, but gets a different kind of attention: resolve the name match, find the direct signal, and only then decide. Avoid gets skipped. This is precisely the class of target the engine exists to let you skip. The hours you save on non-sponsors are the hours that fund the depth you put into Proven targets.

The puzzle the record cannot solve is one level up: a company that will sponsor is worthless to you if the posting they listed is a ghost. So before you spend the targeted application time a Proven tier earns — is the role even real?

---

## Chapter 7 Exercises: Who Sponsors

**Project:** Your Own Reallocation Engine

**This chapter adds:** the sponsorship tier for each company on your funded shortlist — computed from the SEC + DOL + USCIS join — and, just as important, the join-coverage number that tells you which "Unknown" tiers to trust and which to fix.

---

### Exercise 1 — When to Use AI

**The judgment:** In this chapter's work, AI assistance is appropriate for the following tasks:

- **Computing the composite score from inputs you supply.** — *Why AI works here:* the weighted sum (LCA×0.40 + approval×0.30 + recency×0.20 + size×0.10) is arithmetic you can re-check by hand in seconds.
- **Summarizing the join-coverage audit into "how much of my list is actually covered."** — *Why AI works here:* it reformats a number the audit produced; you verify against the file.
- **Drafting the recruiter question for a true-Unknown company.** — *Why AI works here:* outreach drafting against your situation; you judge it before sending.

**The tell:** You know you are using AI appropriately when you can evaluate the output — when you have independent criteria to judge whether it is correct, complete, and fit for purpose. Here the criterion is the coverage audit and the formula itself.

---

### Exercise 2 — When NOT to Use AI

**The judgment:** In this chapter's work, the following tasks require human judgment. Delegating them to AI is not appropriate — not because AI cannot produce output, but because AI output in these cases cannot be trusted without verification that requires the same expertise as doing the task yourself.

- **Producing the LCA counts, approval rates, or funding inputs.** — *Why AI fails here:* these are the scorer's raw materials and must come from DOL/USCIS/SEC records; a model's "this firm files a lot" is a guess, and the whole tier inherits its falseness.
- **Deciding whether an Unknown is a name-match artifact or a true absence of filings.** — *Why AI fails here:* this is a causal-identification problem — the two look identical from the tier alone; only the coverage audit plus an entity trace resolves it.
- **Treating a Proven tier as a guarantee this company will sponsor you, now, for this role.** — *Why AI fails here:* the record is a rear-view mirror; whether the attorney left in March or sponsorship froze last month is intent the data cannot see.

**The tell:** You know you have crossed the line when you are using AI output as your reason for a conclusion rather than as a tool for reaching one. If you could not explain the conclusion without the AI, the AI did the work that should have been yours.

**Series connection:** This exercise trains **Tier 5 (Causal / identification)** with a **Tier 4** edge — the Unknown≠Avoid distinction is precisely an identification problem (silence vs. negative evidence vs. broken join), and resolving it is what separates a real verdict from a data artifact.

---

### Exercise 3 — LLM Exercise

**What you're building this chapter:** a triage of your Unknown-tier companies into "fix the name match and re-run" vs. "true absence — go find a direct signal," each with a next action — the move that keeps Chapter 6's hard-won leads from being thrown away.

**Tool:** Claude (claude.ai chat). You paste real scorer output plus your coverage number; chat fits the interrogation.

**The Prompt:**

```
Below is output from my sponsorship scorer: a list of companies with their tier
(Proven / Likely / Unknown / Avoid) and the inputs behind each (LCA count,
approval rate, funding recency, size). I also paste my join-coverage number:
what % of my shortlist matched in the SEC+DOL+USCIS join. Do NOT invent any
tier, count, or rate — work only with what I paste.

1. For every UNKNOWN company, classify the most likely cause as either
   (a) "name-match artifact — re-resolve and re-run" or (b) "true absence —
   look for direct signals," using my coverage number as evidence (low coverage
   raises the odds of (a)). State which and why for each.
2. For each (a), tell me what to check (entity name variants to try).
   For each (b), draft a one-line recruiter question to confirm current
   sponsorship for my role and visa type.
3. Flag any PROVEN tier I should NOT treat as a present-tense guarantee, and
   write the one-sentence caveat I should attach (rear-view-mirror risk).

Do not tell me a company "sponsors" as an unqualified present-tense fact.

--- PASTE SCORER OUTPUT + COVERAGE NUMBER BELOW ---
[paste tiers, inputs, and your join-coverage %]
```

**What this produces:** an Unknown-triage list with concrete next actions and caveated Proven tiers — the reading discipline the chapter's "most common misread" warning demands.

**How to adapt this prompt:**
- *For your own project:* paste your real scorer rows and coverage number. The coverage number is the load-bearing input — without it, the (a)/(b) split is a guess.
- *For ChatGPT / Gemini:* works as-is; both may default to calling Unknowns "non-sponsors" — keep the explicit (a)/(b) framing.
- *For a Claude Project:* store the four-tier definitions and the Unknown≠Avoid rule in the instructions.

**Connection to previous chapters:** this fills the `sponsorship_status` column of your `targets.csv` and applies Chapter 5's verb taxonomy (no unqualified "sponsors").

**Preview of next chapter:** Chapter 8 asks whether the postings at your Proven companies are even real — a Proven sponsor with a ghost posting is still a dead end.

---

### Exercise 4 — CLI Exercise

**What you're building this chapter:** sponsorship tiers for your shortlist plus a measured join-coverage number — and a worked fix of one name-match failure, so you can see an Unknown flip to a real tier.

**Tool:** Claude Code. Running the join validators, reading coverage, editing an entity map, and re-running is a multi-step terminal workflow.

**Skill level:** Intermediate to Advanced — touches entity resolution.

**Setup:**

Before running this exercise, confirm:
- [ ] You have a funded shortlist from Chapter 6 to score.
- [ ] `scripts/sec/validate-h1b-join-sample.py` and `scripts/audit-sec-dol-h1b-data.py` exist in your repo.
- [ ] The SEC/DOL/USCIS data the scorer needs is downloaded.

**The Task:**

```
Score my shortlist for sponsorship and measure join coverage. Do not invent
counts, rates, or tiers; every number must come from a script.

1. Run:  python scripts/sec/validate-h1b-join-sample.py
   and:   python scripts/audit-sec-dol-h1b-data.py
   Report the join-coverage number: how many shortlist companies matched, how
   many failed.
2. List my Unknown-tier companies and mark which fall in the unmatched set
   (likely name-match artifacts) vs. matched-but-no-filings (likely true
   absence).
3. Pick ONE unmatched company I care about. Show me its name variants across the
   SEC, DOL, and USCIS data. Propose an entity-resolution fix (a name mapping) —
   show it to me, do not apply it silently.
4. With my approval, apply the mapping and re-run the audit. Report whether the
   company's tier changed and the new coverage number.
5. Append a RUN_LOG.md entry: coverage before/after, the company fixed, the tier
   change. Stop.
```

**Expected output:** a coverage number for your shortlist, an Unknown list split by cause, and one entity-resolution fix with a before/after tier and coverage change logged.

**What to inspect in the output:** does the coverage number make the Unknowns interpretable (e.g. "30% unmatched → a third of my Unknowns are artifacts")? After the fix, did the tier change for the right reason (a real filing history surfaced), or did the mapping over-merge two different firms? Verify the rescued filings actually belong to your company.

**If it goes wrong:** the likely failure is an entity mapping that merges distinct companies, inflating a tier. Recover by tightening the mapping to the exact legal entity and re-running; never accept a tier jump you can't trace to specific filings.

**CLAUDE.md / AGENTS.md note:** add a standing rule — *"Never read an Unknown tier without first reading the join-coverage number; entity-resolution mappings require human approval and a before/after coverage log."* This encodes the chapter's core discipline.

---

### Exercise 5 — AI Validation Exercise

**What you're validating:** an AI tier summary that commits the chapter's most common misread — treating Unknown as Avoid and discarding a strong lead.

**Validation type:** Reasoning chain.

**Risk level:** High — this error silently deletes exactly the companies Chapter 6 worked to surface.

**Setup (pre-generated artifact — option b):** This chapter names Unknown-as-Avoid as the most common and most damaging misread, so validate this pre-generated summary:

> **Sponsorship triage.** Acme Bio (Proven) and Cortex Labs (Likely) are your
> targets — apply to both. The rest are Unknown, which means they don't sponsor,
> so skip them. Note: NovaGen is Unknown despite raising a $20M Series B two
> months ago and being three years old — no filing history found, so treat as a
> non-sponsor and remove from the list. (Join coverage for this run: 64%.)

**The Validation Task:**

Evaluate the AI output above using the following checklist. For each item, record: Pass / Fail / Cannot determine — and explain your reasoning.

```
Validation Checklist — Who Sponsors

□ Correctness: Does the summary treat "Unknown" as "Avoid"? Is that the
  distinction the chapter draws?
□ Completeness: With 64% coverage, what does that imply about the ~36% of the
  list that didn't match — could some Unknowns be name-match artifacts?
□ Scope: Did it discard a young, well-funded company (NovaGen) on the basis of
  silence rather than negative evidence?
□ Unknown-cause check (chapter-specific): For NovaGen, are the two possible
  causes (no history yet vs. failed join) distinguished, or collapsed into
  "non-sponsor"?
□ Action check (chapter-specific): True-Unknowns with strong funding should
  trigger a direct-signal search, not removal — does the summary do that?
□ Failure mode check: Does this output exhibit any of the following?
  - Unknown-as-Avoid (the named most-common misread)
  - Ignoring the coverage number when interpreting Unknowns
  - Fluent but wrong (a confident triage that deletes a real lead)
```

**What to do with your findings:**
- If the output passes all checks: use it. (It will not — it removes NovaGen on silence and ignores 36% unmatched.)
- If it fails one check: re-triage the Unknowns by cause using the coverage number, and restore any wrongly-removed lead.
- If it fails multiple checks or you cannot determine pass/fail: this is a "When NOT to Use AI" moment — read the coverage audit and decide each Unknown yourself.

**AI Use Disclosure prompt:**
After completing this validation, write a two-sentence AI Use Disclosure:
> *Sentence 1:* What AI produced in this exercise and how you used it.
> *Sentence 2:* One specific thing the AI could not determine that required your judgment.

**Series connection:** This exercise trains **Tier 5 causal identification** — refusing to read silence as negative evidence, and using the coverage number to tell a broken join from a true absence. It is the single discipline that keeps the scorer from throwing away your best leads.

## Prompts

### Figure 7.1 — Famous brand versus unknown biotech: the ranking flip
**Files:** ../images/07-who-sponsors-the-80-days-sponsorship-scorer-fig-05.svg · ../d3/07-who-sponsors-the-80-days-sponsorship-scorer-fig-05.html
**Prompt:** Brutalist grouped horizontal bar chart, zero baseline: two companies (famous brand, unknown biotech) compared across LCA count, approval rate, funding recency, and composite score. Unknown biotech bars in red as the winner on the record; famous brand bars in neutral ink. Hairline axis, mono tick labels, no decoration.

### Figure 7.2 — Three records into one score
**Files:** ../images/07-who-sponsors-the-80-days-sponsorship-scorer-fig-01.svg · ../d3/07-who-sponsors-the-80-days-sponsorship-scorer-fig-01.html
**Prompt:** Brutalist convergent-pipeline diagram: three equal source nodes (SEC Form D, DOL LCA, USCIS H-1B Hub) with single-direction arrows into one red scorer node, plus a visibly thinner company-size input joining from below. Ink and red only, hairline strokes, sentence-case labels, no database-cylinder shading.

### Figure 7.3 — The four-tier sponsorship spectrum
**Files:** ../images/07-who-sponsors-the-80-days-sponsorship-scorer-fig-03.svg · ../d3/07-who-sponsors-the-80-days-sponsorship-scorer-fig-03.html
**Prompt:** Brutalist horizontal evidence spectrum with four ordered zones (Avoid, Unknown, Likely, Proven) and one action-cue chip beneath each; render Unknown visibly distinct from Avoid. Red marks the Proven end, neutral grays the middle, ochre accent for the Unknown distinction. No gauge or speedometer imagery.

### Figure 7.4 — Weighted score: the ranking flip
**Files:** ../images/07-who-sponsors-the-80-days-sponsorship-scorer-fig-02.svg · ../d3/07-who-sponsors-the-80-days-sponsorship-scorer-fig-02.html
**Prompt:** Brutalist paired stacked bars, zero baseline: four weighted segments each (filing 0.40, approval 0.30, recency 0.20, size 0.10). The unknown-biotech bar fills all four to a high total; the famous-brand bar shows the two behavior segments (70%) hollow, collapsing it into the Avoid range. Red for the dominant filing segment, grays and ochre for the rest.

### Figure 7.5 — Why a company is "Unknown": three causes, three responses
**Files:** ../images/07-who-sponsors-the-80-days-sponsorship-scorer-fig-04.svg · ../d3/07-who-sponsors-the-80-days-sponsorship-scorer-fig-04.html
**Prompt:** Brutalist top-down disambiguation tree from a single Unknown entry node: one join-coverage decision splits a name-match-artifact path (resolve entity, re-run) from a true-absence path (seek direct signals). Single-direction arrows, one accent color for the active action nodes, hairline decision diamond. The visual thesis: Unknown is never Avoid.
# Chapter 8 — Is the Job Real: ATS Detection and Liveness
*A posting is not a job opening — it is a signal, and signals can lie.*

Here is a number that should bother you. Somewhere between 28 and 42 percent of job postings, depending on the study and the year, are ghosts — listings a company has no active intention of filling. One survey found 81 percent of recruiters admitting to posting jobs they weren't actually hiring for. That figure has held roughly steady across five years of measurement, which means it isn't an artifact of a particular labor market cycle. It is a structural feature of how hiring works, or rather, how it appears to work from the outside.

I want to sit with that before we get to the detection problem, because the number is stranger than it looks. A ghost job isn't a posting that went live and then the position was cancelled. It's a posting that was never, at the moment of posting, connected to an intention to hire someone. It can be a pipeline hedge — the company isn't hiring now but wants résumés queued when it does. It can be a signal to investors that the firm is growing. It can be bureaucratic inertia: a listing that went up two quarters ago and no one has gotten around to taking down. Whatever the cause, the effect for a candidate on a finite clock is the same. A day spent writing a cover letter, tailoring a résumé, researching the company, submitting an application — to a door that was never going to open.

![A quantitative chart with a time axis from 2019 to 2024 and a prevalence axis from zero to fifty percent; a shaded band at twenty-eight to forty-two percent holds steady across the years while individual study points scatter in and near it, with a couple of lower outliers.](images/08-is-the-job-real-ats-detection-and-liveness-fig-01.png)
*Figure 8.1 — Ghost-job prevalence holds across years*

<!-- → [CHART: Bar chart showing ghost-job prevalence estimates across multiple studies and years (2019–2024), y-axis 0–50%, with a shaded band at 28–42% and individual city/source data points labeled (e.g., LA 30.5%, Seattle 16.6%). Caption: "Ghost-job prevalence has held in the 28–42% range across five years — not a cycle artifact but a structural feature of the posting market."] -->

The question I want to work through with you is this: can you tell, before spending that day, whether the door is real? The answer is yes — not perfectly, but well enough to matter. To see how, you have to stop reading job postings as prose and start reading them as data.

## What you are actually looking at

When you pull up a careers page in a browser, you are looking at a rendered surface. What feeds that surface is a piece of software called an applicant-tracking system — Greenhouse, Lever, Ashby are the names you'll encounter most. These are not interchangeable wrappers around the same underlying structure. Each one organizes its data differently, exposes different fields through its feed, and structures timestamps and job identifiers in its own way. That matters because the signals that distinguish a real posting from a ghost live in those fields — not in the prose of the job description, which is marketing, but in the metadata, which is evidence.

The first thing I do when I hit a new company is run a single script:

```bash
python scripts/ats/detect-ats.py --company "Example Bio"
```

It returns a label — Greenhouse, Lever, Ashby, or unknown. That label is not interesting on its own. What it unlocks is the ability to read the feed correctly. A scraper built for Greenhouse reads Lever data as noise. Detection is the key; without it, everything downstream is garbled.

![Three applicant-tracking platforms — Greenhouse, Lever, and Ashby — each with its own feed structure, all resolving to one unified postings-record schema with fields for job id, title, posted date, last updated, description, and status.](images/08-is-the-job-real-ats-detection-and-liveness-fig-05.png)
*Figure 8.2 — Detection unlocks the schema*

<!-- → [DIAGRAM: Three ATS platforms (Greenhouse, Lever, Ashby) each shown as a box with their characteristic URL/feed structure beneath, all pointing to a unified "postings record" schema with fields: job_id, title, posted_date, last_updated, description, status. Caption: "Each ATS structures its data differently; detection tells the scraper which schema to read."] -->

Once the ATS is identified, the pipeline pulls the company's postings directly from the provider's feed — no paid model calls, just structured data read from the source:

```bash
npm run ats:scan
```

This zero-token scan matters because it runs on every company in the pipeline. At scale, what gets expensive gets skipped. A check that costs nothing gets run every time, and recency of the scan stops being a variable you manage.

## The spam filter you already trust

Here is where the detection logic becomes interesting, and where I think an analogy does real explanatory work. Ghost job detection is structurally identical to spam filtering — not metaphorically, but mechanically.

Your email filter doesn't read a suspicious message and conclude it seems dishonest. It scores the message's behavioral fingerprints against patterns of mail that is actually wanted. Temporal anomalies: sent at 3 a.m. to ten thousand addresses in twelve seconds. Interaction voids: no replies, no clicks, bounce rates in unusual ratios. Textual homogeneity: the same message reused with minor surface variation, identifiable across millions of instances. The filter assembles these signals into a probability, not a verdict, and routes accordingly. It does this a billion times a day without reading a word of content.

Ghost postings have the same fingerprints. A posting that has been up eleven weeks with no update, at a company where other listings sit frozen at similar ages, looks like a bulk send with no engagement — the temporal anomaly. A portal that has never advanced a candidate, carries no closing date, and shows no sign of iterative recruiter activity looks like mail no one is responding to — the interaction void. A job description identical to three other listings at the same company, copy-pasted from a template and minimally varied by title, looks like a mass campaign with surface variation — textual homogeneity.

No single signal is decisive. A genuinely open role can sit untouched for weeks at a slow-moving organization. A ghost can be freshly posted specifically to look active. But together, the way no individual word makes an email spam but the pattern does, they yield a classification you can defend. That is the standard I care about: not certainty, but a call traceable to the specific signals that produced it.

![A three-column map drawing the parallel between spam detection and ghost-job detection across three behavioral fingerprints — temporal anomalies, interaction voids, and textual homogeneity — each column pairing an email-spam example with a job-posting example.](images/08-is-the-job-real-ats-detection-and-liveness-fig-02.png)
*Figure 8.3 — The spam-filter analogy: three behavioral fingerprints*

<!-- → [INFOGRAPHIC: Three-column layout labeled "Temporal Anomalies," "Interaction Voids," "Textual Homogeneity." Under each: two or three bullet examples from job-posting context (e.g., "unchanged for 8+ weeks," "no portal activity," "description reused across 3 listings"). Footer: "Ghost detection scores behavioral patterns — the same move your spam filter makes."] -->

## Five signals and one classification

The liveness check reads five things, in this order.

How old is the posting? Age alone is weak — the base rate of slow organizations is too high to make age decisive — but it is a prior that subsequent signals update. A nine-day posting enters the analysis differently than a seventy-seven-day posting.

When was it last updated? Posting date and update date are different fields. A three-month-old posting that was refreshed last week is behaving like an active search. A three-month-old posting frozen since the day it went up is not.

Are the company's other listings changing? This is the signal I find most diagnostic. If a company has twelve open roles and ten of them have been sitting untouched for the same number of weeks, that pattern tells you something about how the company uses its careers page — probably as a passive presence rather than an active hiring signal. If roles are appearing and disappearing, that's churn, and churn indicates an active search function.

Is the description specific? A listing that names a team lead, a project in progress, a specific dataset or codebase or migration underway, is a listing someone wrote for a real role. A listing that is word-for-word reproducible from a template — or from a prior listing at the same company — is a listing that was generated, not composed.

Does the context make an active search plausible? Funding tier, recent headcount trajectory, the occupation's demand signal from earlier in the pipeline — these are not liveness signals in themselves, but a fresh listing at a company that just closed a Series B reads differently than the same listing at a company in a freeze.

The classification runs after all five:

```bash
npm run ats:liveness
```

![A classifier diagram where five posting signals — posting age, last-updated date, sibling-listing activity, description specificity, and active-search context — feed a single liveness decision that fans out to three terminal calls: live, ghost, and investigate.](images/08-is-the-job-real-ats-detection-and-liveness-fig-03.png)
*Figure 8.4 — Five signals to one classification*

The output is one of three calls per posting: live, ghost, or investigate. The first two are self-explanatory. The third is the honest response to mixed signals — recent posting but templated description; stale posting at a company that just raised money. Investigate means: one cheap check resolves this faster than a blind application or a blind skip.

## One company, both doors

Let me make this concrete. A biotech with a strong sponsorship tier has two open data roles, both with the same title. `detect-ats.py` returns Greenhouse.

Posting A went up nine days ago. The description references a specific named project — a model being retrained on a new assay dataset — and names the team lead the role would report to. The company's other listings show recent count changes; two roles present last week are absent this week. Five signals, all pointing the same direction. `ats:liveness` calls it live.

Posting B has been up eleven weeks. The description is word-for-word identical to a data scientist posting the company ran eighteen months ago and to two other currently active listings under slightly different titles. No portal activity is detectable. The count for this listing has not changed across three scans. Five signals, all pointing the same direction. `ats:liveness` flags it stale — likely ghost.

![A side-by-side comparison of two postings from the same employer scored across five liveness signals; Posting A reads live on every signal and Posting B reads ghost on every signal, even though both share the same title and sponsorship tier.](images/08-is-the-job-real-ats-detection-and-liveness-fig-04.png)
*Figure 8.5 — Same employer, two doors*

The same employer. The same title. The same sponsorship tier. One of these is a door; one is a picture of a door. The decision is not about the company — the company is real. The decision is about the posting.

| Signal | Posting A | Posting B |
|---|---|---|
| Posting age | 9 days | 11 weeks |
| Last updated | Refreshed recently | Never — frozen at posting date |
| Description specificity | Names a project, dataset, and team lead | Word-for-word identical to an 18-month-old listing and two siblings |
| Company hiring activity | Sibling listings appearing and disappearing (churn) | Sibling listings frozen at the same age |
| Portal movement | Detectable | None across three scans |
| **Liveness classification** | **Live** | **Stale — likely ghost** |

*Same employer, same title, same sponsorship tier. The signals separate them. Liveness is a property of the listing, not the firm.*

## Where judgment re-enters

Here is the error the classification is most likely to induce. You get a live call and stop thinking. You treat "live" the way you would treat a verified fact — as having the same standing as a DOL filing count or a USCIS data point. It doesn't.

A liveness call is a probability, not a certification. The signals reduce the odds of wasting a day. They cannot read hiring manager intent.

A posting scored live can be a role that the company has been slow-walking through four rounds of internal headcount approval and will quietly kill if it doesn't close by quarter end. A posting scored ghost can be the one role where a slow-moving organization has a genuinely active search underway, conducted by a hiring manager who simply doesn't believe in updating careers pages. The signals catch the pattern. The exception lives in intent the pattern cannot see.

The decision rule is: *live* means apply if tier and fit hold. *Ghost* means skip. *Investigate* means one cheap check is faster than a blind application — a single direct message to a recruiter, or a look at the company's recent LinkedIn for engineering posts, takes ten minutes and gives you what the behavioral scores cannot: a human response. The liveness classification is a data claim, built from observable posting signals, logged, auditable. The reading of what that classification means for this particular company, this particular team, this particular moment is a judgment call, and it belongs to you.

## What the pipeline cannot see

I want to be clear-eyed about what this system actually measures and what it doesn't.

It measures what the posting does, not what the company intends. That gap is real.

A stale posting can be real. An organization buried in a product sprint may have a genuine open role that no one on the recruiting side has had time to update in two months. The metrics say ghost; the actual answer is "we'd love to talk, we just haven't looked at the careers page." That's a real door the filter misses. Filtering it out is the cost of the filter.

A fresh posting can be fake. A recruiter running a sourcing campaign posts a crisp, specific, recently dated listing precisely because candidates screen for recency. The posting is designed to beat the detector. The signals say live; the actual answer is résumé harvest. That's a ghost the filter misses from the other direction.

Neither failure breaks the filter. A check that eliminates 35 percent of ghost applications and occasionally miscategorizes an outlier in both directions is worth running. But knowing where it fails matters — not because you can fix it in the current architecture, but because when the signals are mixed and the role genuinely matters, the right response is a human check, not confidence in the score.

| What liveness detection catches | What liveness detection misses |
|---|---|
| Templated, stale ghost postings — the bulk of wasted application days | Stale-but-real roles at slow orgs that never update the careers page |
| Frozen listings with dead sibling activity | Fresh-but-fake harvest postings designed to beat the recency detector |
| Duplicate descriptions reused across listings | ATS-invisible postings filled by direct referral, never posted to a feed |
| Postings with no portal movement across scans | Real roles frozen mid-search because the position was put on hold |

*The filter reduces waste; it does not read intent. The residual cases are where a human check earns its keep.*

## The rung you just added

At the end of this chapter, three facts exist about a role: the company can sponsor, the posting is live, and the signals behind both claims are logged and traceable. The pipeline has been built as a ladder of verified claims — each chapter adding one rung, each rung resting on data rather than plausibility.

The question the pipeline still cannot answer is whether the job is worth having. A real, sponsoring role at a company with an active posting is still a role in an occupation that might be contracting, at a salary band below market, in a geography you can't realistically reach. Sponsorship and liveness are necessary conditions. They are not sufficient ones.

That's where the next chapter begins. The role exists, and you can apply to it. Is it any good?

---

## Chapter 8 Exercises: Is the Job Real

**Project:** Your Own Reallocation Engine

**This chapter adds:** a liveness call per posting — live, ghost, or investigate — so the targeted application hours your Proven-tier companies earned go to doors that are actually open, not pictures of doors.

---

### Exercise 1 — When to Use AI

**The judgment:** In this chapter's work, AI assistance is appropriate for the following tasks:

- **Summarizing the scan output (which ATS, how many postings, classifications).** — *Why AI works here:* it reformats structured data the scan produced; you check against the feed.
- **Classifying a posting from the five signal VALUES you supply.** — *Why AI works here:* given posting age, last-updated, sibling-listing activity, description specificity, and funding context, applying the live/ghost/investigate rule is structured judgment you can audit signal by signal.
- **Drafting the one cheap "investigate" check — a recruiter message or LinkedIn look.** — *Why AI works here:* outreach drafting you review before sending.

**The tell:** You know you are using AI appropriately when you can evaluate the output — when you have independent criteria to judge whether it is correct, complete, and fit for purpose. Here the criterion is the five measured signals, not the model's read of the prose.

---

### Exercise 2 — When NOT to Use AI

**The judgment:** In this chapter's work, the following tasks require human judgment. Delegating them to AI is not appropriate — not because AI cannot produce output, but because AI output in these cases cannot be trusted without verification that requires the same expertise as doing the task yourself.

- **Producing the liveness classification by reading the job description prose.** — *Why AI fails here:* the description is marketing; classification must come from the metadata signals via `ats:liveness`. A model that reads "exciting fast-growing team!" and says "live" is reading the costume, not the evidence.
- **Inferring hiring-manager intent behind a posting.** — *Why AI fails here:* the signals catch the pattern; the exception (a real role at a slow org, a harvest posting designed to look fresh) lives in intent no pattern can see.
- **Treating a "live" call as a certified fact.** — *Why AI fails here:* liveness is a probability, not a DOL filing count; trusting it as certification is the chapter's named error.

**The tell:** You know you have crossed the line when you are using AI output as your reason for a conclusion rather than as a tool for reaching one. If you could not explain the conclusion without the AI, the AI did the work that should have been yours.

**Series connection:** This exercise trains **Tier 4 (Metacognitive supervision)** with a **Tier 5** edge — distinguishing a behavioral pattern (which the signals measure) from intent (which they cannot), and refusing to let a fluent reading of marketing prose stand in for measured evidence.

---

### Exercise 3 — LLM Exercise

**What you're building this chapter:** liveness classifications for the postings at your Proven/Likely companies, each justified by the specific signal that drove it — and an "investigate" action list for the mixed cases.

**Tool:** Claude (claude.ai chat). You paste real signal values from your scan; chat fits.

**The Prompt:**

```
Below are postings from my ATS scan. For each, I give the FIVE liveness signal
values: posting age, last-updated date, whether the company's sibling listings
are changing, description specificity (templated vs. specific/named-project),
and funding/hiring context. Do NOT read the job description as evidence of
realness, and do NOT invent any signal value — use only what I paste.

1. Classify each posting as LIVE, GHOST, or INVESTIGATE using the five signals,
   and name the specific signal(s) that drove the call.
2. For each INVESTIGATE, write the single cheapest check to resolve it (one
   recruiter message or one LinkedIn look) and state what response pushes it
   toward live vs. ghost.
3. Flag any posting where my signals conflict, and say explicitly: "this is a
   probability, not a certification — verify with a human check before spending
   a day on it."

Remember: a fresh, specific-sounding description can still be a harvest posting,
and a stale posting can still be a real role at a slow org. Classify from the
signals, flag the residual risk.

--- PASTE POSTINGS + SIGNAL VALUES BELOW ---
[paste 3–6 postings with their five signal values each]
```

**What this produces:** signal-justified liveness calls plus an investigate-action list — filling the `posting_live` column of your `targets.csv` with reasons, not guesses.

**How to adapt this prompt:**
- *For your own project:* paste real signal values from `ats:scan` / `ats:liveness`. The classification is only as good as the measured signals you feed it.
- *For ChatGPT / Gemini:* works as-is; both gravitate to judging the description text — keep the "do NOT read the description as evidence" line.
- *For a Claude Project:* store the five signals and the three-way decision rule in the instructions.

**Connection to previous chapters:** this gates the Proven-tier companies from Chapter 7 — sponsorship and liveness together are necessary, not sufficient (Chapter 9 adds role quality).

**Preview of next chapter:** Chapter 9 asks whether a live, sponsoring role is even worth having — by reading the occupation's wage band and employment trend.

---

### Exercise 4 — CLI Exercise

**What you're building this chapter:** liveness data for your targets — ATS detected, postings scanned at zero token cost, and each classified — recorded so a posting's status is a logged fact, not a memory.

**Tool:** Claude Code. Running detection, the scan, and the liveness classifier across your target list is a terminal pipeline.

**Skill level:** Intermediate — requires `portals.yml` configured (Chapter 4's scan recipe).

**Setup:**

Before running this exercise, confirm:
- [ ] `data/ats/portals.yml` exists and is YOUR config, not the example (Chapter 4 failure mode).
- [ ] `scripts/ats/detect-ats.py` and the `ats:scan` / `ats:liveness` commands run.
- [ ] You have a list of target companies/URLs from Chapters 6–7.

**The Task:**

```
Run ATS detection and liveness for my target companies. Do not invent ATS hits,
postings, or classifications; if a scan returns nothing, report empty — do not
fill it in.

1. Confirm data/ats/portals.yml exists and is NOT identical to portals.example.yml.
   If it's the example, stop and tell me.
2. For each target company, run:
     python scripts/ats/detect-ats.py --company "<name>"
   Record the ATS label (greenhouse/lever/ashby/unknown).
3. Run:  npm run ats:scan      (zero-token scan of configured portals)
   then:  npm run ats:liveness
   Record per-posting: the five signal values and the live/ghost/investigate call.
4. Save a table to reports/liveness.csv: company, posting, five signals,
   classification. Separate EMPTY results from ERRORS in your report.
5. Append a RUN_LOG.md entry: companies scanned, postings classified, counts of
   live/ghost/investigate. Stop.
```

**Expected output:** `reports/liveness.csv` with per-posting signals and classifications, plus a run-log entry — empties distinguished from errors.

**What to inspect in the output:** check that classifications trace to the five measured signals, not to description text. Confirm `portals.yml` was your config (or the whole scan is against example companies — the Chapter 4 trap). For one "live" posting, sanity-check the signals by hand.

**If it goes wrong:** the most common failure is the scan running against the example config and returning plausible-looking results for companies you didn't target. Recover by verifying `portals.yml`; if results look suspiciously generic, re-check the config before trusting a single row.

**CLAUDE.md / AGENTS.md note:** add a standing rule — *"Liveness is classified from the five metadata signals only, never from description prose; a 'live' call is a probability that requires a human check before a full application."* This pins the chapter's two warnings into the repo.

---

### Exercise 5 — AI Validation Exercise

**What you're validating:** an AI liveness verdict that judged the job description instead of the signals — fluent, confident, and reading marketing as evidence.

**Validation type:** Reasoning chain.

**Risk level:** Medium-High — a wrong "live" call costs a full day of application effort on a door that won't open.

**Setup (pre-generated artifact — option b):** This chapter's lesson is "read the metadata, not the prose," so validate this pre-generated verdict:

> **Posting verdict — Senior Data Scientist, Helix Bio.** This is clearly a LIVE,
> active role. The description is detailed and exciting — it mentions a
> fast-growing team, cutting-edge ML work, and a great mission. A company would
> not write such a compelling, professional posting if they weren't serious about
> hiring. Apply with confidence.
> *(Signals on file: posting age 11 weeks; last-updated = posting date, never
> refreshed; 3 sibling listings unchanged for 11 weeks; description word-for-word
> identical to a posting from 18 months ago; no portal activity.)*

**The Validation Task:**

Evaluate the AI output above using the following checklist. For each item, record: Pass / Fail / Cannot determine — and explain your reasoning.

```
Validation Checklist — Is the Job Real

□ Correctness: Did the verdict use the five metadata signals or the description
  prose? Which did it actually cite?
□ Completeness: Did it ignore the signals on file (11 weeks stale, never
  refreshed, duplicate description, dead siblings, no activity)?
□ Scope: Did it treat "compelling description" as evidence of realness — the
  exact error the chapter warns against?
□ Signal check (chapter-specific): Read the five signals yourself. What
  classification do they support — live, ghost, or investigate?
□ Certification check (chapter-specific): Does it present a probability as a
  certified fact ("apply with confidence")?
□ Failure mode check: Does this output exhibit any of the following?
  - Reading marketing prose as evidence (the chapter's named error)
  - Fluent but wrong (a confident verdict against the actual signals)
  - Treating a liveness call as a certification rather than a probability
```

**What to do with your findings:**
- If the output passes all checks: trust it. (It will not — the signals scream ghost while the verdict says live.)
- If it fails one check: re-classify from the five signals yourself and note which the verdict ignored.
- If it fails multiple checks or you cannot determine pass/fail: this is a "When NOT to Use AI" moment — classify from the signals, and run the one cheap human check before committing.

**AI Use Disclosure prompt:**
After completing this validation, write a two-sentence AI Use Disclosure:
> *Sentence 1:* What AI produced in this exercise and how you used it.
> *Sentence 2:* One specific thing the AI could not determine that required your judgment.

**Series connection:** This exercise trains **Tier 4 metacognitive supervision** — catching the moment fluent prose is mistaken for measured evidence. The signals are the data claim; the description is the costume.

## Prompts

### Figure 8.1 — Ghost-job prevalence holds across years
**Files:** ../images/08-is-the-job-real-ats-detection-and-liveness-fig-01.svg · ../d3/08-is-the-job-real-ats-detection-and-liveness-fig-01.html
**Prompt:** Brutalist scatter-with-band, zero-baseline prevalence axis (0–50%) over years 2019–2024: a neutral shaded band at 28–42% holding flat across the width, study points scattered in and near it, two lower outliers distinguished. No fitted trend line, mono tick labels, one accent color for the points.

### Figure 8.2 — Detection unlocks the schema
**Files:** ../images/08-is-the-job-real-ats-detection-and-liveness-fig-05.svg · ../d3/08-is-the-job-real-ats-detection-and-liveness-fig-05.html
**Prompt:** Brutalist convergence diagram: three platform nodes (Greenhouse, Lever, Ashby), each with a distinct feed structure, resolving via single-direction arrows into one unified postings-record schema box listing job id, title, posted date, last updated, description, status. Ink and red only, hairline strokes, no UI chrome.

### Figure 8.3 — The spam-filter analogy: three behavioral fingerprints
**Files:** ../images/08-is-the-job-real-ats-detection-and-liveness-fig-02.svg · ../d3/08-is-the-job-real-ats-detection-and-liveness-fig-02.html
**Prompt:** Brutalist three-column parallel map: columns for temporal anomalies, interaction voids, textual homogeneity; each column stacks an email-spam chip over a job-posting chip, rows aligned across all three columns. The thesis — score behavior, not content. Neutral grays with one accent, no envelope or inbox icons.

### Figure 8.4 — Five signals to one classification
**Files:** ../images/08-is-the-job-real-ats-detection-and-liveness-fig-03.svg · ../d3/08-is-the-job-real-ats-detection-and-liveness-fig-03.html
**Prompt:** Brutalist many-to-one-to-three funnel: five input nodes (posting age, last-updated, sibling activity emphasized, description specificity, active-search context) feed one classifier node that fans out to three calls — live, ghost, investigate. Red for the classifier, ochre for the investigate branch, grays for the rest; single-direction arrows.

### Figure 8.5 — Same employer, two doors
**Files:** ../images/08-is-the-job-real-ats-detection-and-liveness-fig-04.svg · ../d3/08-is-the-job-real-ats-detection-and-liveness-fig-04.html
**Prompt:** Brutalist two-column signal grid: Posting A and Posting B share five signal rows plus a classification row; A reads live on every signal, B reads ghost on every signal. Use ink for live chips and ochre for ghost chips — explicitly avoid red-green coding. Hairline dividers, mono row labels.
# Chapter 9 — Is the Role Any Good: BLS / O\*NET Role Quality

<!-- voice-anchored: root style/VOICE.md. Anatomy: TIKTOC Part 10.
     Sourced from scripts/bls/README.md, projects/soc_classification_draft.md, CHAPTER-RESEARCH-MAP.
     Draft. Never published. -->

Two postings cross your screen on the same afternoon. Both say "Analyst." Same flattering word, same vague glamour. But one of them sits in an occupation where national employment has risen for four consecutive years and the wage band is strong and still widening; the other sits in an occupation that is quietly contracting, where median wages have stalled and headcount has fallen. The titles are identical. The futures are not. And the person reading only the title has no way to tell the difference.

This is the situation job titles were made for. Not yours — theirs. A title is a marketing artifact, written by whoever drafted the posting, calibrated to attract applicants rather than to describe the work. "Analyst" sounds important, versatile, valuable. Whether the underlying occupation is growing or shrinking, well-compensated or wage-stagnant, in demand or being automated away — none of that is in the title. The title was written to get you to apply, not to help you decide whether you should.

The U.S. labor statistics system does something the title doesn't. It classifies the actual occupation underneath the title — assigns it a code, measures it, tracks it over years. Once you can see the occupation, you can see the trajectory the title was hiding.

---

Every occupation in the American labor market has been assigned a Standard Occupational Classification code — a SOC code. It is a government taxonomy, stable and consistent across agencies. A "Data Analyst" at a startup and a "Data Analyst" at a bank might be doing very different things, but if both postings map to the same SOC, the same national employment count and wage distribution describes the occupation they are both part of. The SOC code is the hinge. Get it right, and everything useful follows from it.

Two federal data systems organize what follows from it:

**O\*NET** — the Occupational Information Network — describes what the occupation is. For each SOC code, it provides alternate titles (the many ways the same job gets marketed), job zones (how much preparation the occupation typically requires), and rated skill and ability levels. If you want to know whether the occupation your posting maps to is the same occupation you trained for, O\*NET's alternate-title list will tell you.

**BLS OEWS** — the Bureau of Labor Statistics' Occupational Employment and Wage Statistics — measures the occupation's footprint. National employment counts per year, wage distributions at the tenth, twenty-fifth, fiftieth, seventy-fifth, and ninetieth percentiles. If you want to know whether the field is growing and what it pays, OEWS supplies the numbers.

Both are organized by SOC code. The pipeline in `scripts/bls/` joins them into a compact table — one row per occupation — and that compact row is what turns a marketing title into a labor-market fact. Build the table once:

```bash
cd scripts/bls
python extract-soc-occupation-table.py     # builds the compact SOC/OEWS/O*NET table into data/bls/compact/
```

The output is a single flat table. Pull your target occupation's row. You get alternate titles confirming the match, job zone, skill and ability ratings, national employment over multiple OEWS survey years, and the full wage distribution. That is role quality — not a feeling about the posting, but a set of features measured by the people whose job it is to measure them.

---

The hardest part of this is the first step: correctly mapping the posting's title to the right SOC code. And this is worth slowing down on, because the whole chapter's value depends on getting it right. A wrong SOC match is silent. It doesn't error out. It just quietly attaches the wrong wages, the wrong employment trend, and the wrong skill profile to the role you're evaluating. You'll make a decision based on a different job than the one you're actually considering.

A language model is genuinely useful here, within limits. It has encountered thousands of job titles and their occupational descriptions, and it is good at proposing a plausible SOC match from a messy posting. But proposing is not confirming. The verification step is mandatory: take the model's proposed SOC, look at the alternate-title list in the compact row, and check whether your posting's title or description actually appears there. If it does, the match is confirmed. If it doesn't, you re-classify before you trust any number downstream. The model proposes; the data confirms; you judge. This is the same verified-data contract from Chapter 3, now applied to classification rather than company counts.[^soc]

![A horizontal process flowchart tracing a raw posting title through a model that proposes a candidate occupation code, a verification gate that checks the proposed code's alternate-title list against the posting, a confirmed path to the joined occupation row, and a rejected path that loops back to re-propose; three role-quality features are read from the confirmed row.](images/09-is-the-role-any-good-bls-onet-role-quality-fig-01.png)
*Figure 9.1 — Title-to-occupation resolution pipeline*

Consider what it looks like when this goes wrong. A posting titled "Growth Analyst" gets mapped by the model to a SOC for market research analysts — reasonable enough on its face. The compact row for that SOC shows stable employment and a wage band that looks acceptable. But the alternate-title list doesn't contain anything close to "growth analyst" — the posting is actually describing a role closer to a data scientist, and that occupation's SOC has a completely different wage distribution and a steeper skill profile. If you skip the alternate-title check, you've just evaluated the wrong job. The title was ambiguous; the alternate-title list is not.

---

![A two-panel comparison: the left panel shows an ambiguous title mapped to a plausible-but-wrong occupation whose alternate-title list does not contain the work, with a lower wage band; the right panel shows the same posting correctly re-classified to the occupation whose alternate-title list does contain the work, with a higher wage band on a shared zero-based scale. The gap between the bands is the cost of skipping the check.](images/09-is-the-role-any-good-bls-onet-role-quality-fig-03.png)
*Figure 9.2 — The silent wrong-SOC error*

Once the SOC is confirmed, the compact row gives you three features that matter for the decision:

**Employment trend.** Has national headcount in this occupation been rising or falling across the OEWS survey years in the data? Flat is not the same as falling, and rising is not the same as booming, but the direction over multiple years is about as reliable a signal as you can get about whether the occupation is healthy. Declining employment, in an occupation you plan to spend years in, is a structural headwind worth knowing about before you accept an offer.

**Wage band.** The OEWS wage distribution tells you what people in this occupation actually earn, at each percentile. This is not what this company offers — it's what the occupation pays across thousands of employers. If the median is well above your threshold, the occupation rewards the work. If the median has been flat for several survey years while others have risen, something is compressing wages in this field — and that compression will be your problem eventually.

**Job zone.** O\*NET's job zones run from one to five, describing the typical preparation each occupation requires — from jobs that need little beyond a few days of training to occupations requiring extensive graduate preparation and years of experience. A job zone four or five occupation with a posting that claims to want recent graduates is either mismapped or unusual; knowing the zone helps you calibrate how competitive the real candidate pool is likely to be.

![A structural schematic of one compact occupation row decomposed into three parallel feature panels: an employment-trend line across survey years, a wage band marked at five percentiles, and a five-step job-zone preparation ladder, with the alternate-title list attached above as the confirmation feed.](images/09-is-the-role-any-good-bls-onet-role-quality-fig-02.png)
*Figure 9.3 — The compact row: three role-quality features*

These three features, read together from one compact row, tell you more about a role's quality than any amount of reading the posting itself. The posting was written to make the role sound desirable. The compact row was built from surveys of everyone actually employed in the occupation.

---

The limit of this read is worth being explicit about. National OEWS estimates are national and lagging — typically one to two years behind the survey. They don't capture what this specific company pays, what the local market pays in your city, or what's happening in the last eighteen months of a fast-moving field. A company that just raised a Series A may be paying at the top of the wage band for talent; a company burning through runway may be offering equity and a below-median salary. The compact row tells you the occupation's gravity; it cannot tell you the specific role's orbit around it.

The SOC taxonomy also lags genuinely new work. If a role is at the frontier of a field that didn't exist five years ago — some combinations of machine learning engineering and product work, for instance — the best available SOC code may be an imperfect match for something genuinely novel. The numbers you read off it will be real, but they'll describe a proxy occupation rather than the thing itself. This is not a reason to skip the lookup. It is a reason to hold the numbers as directional rather than definitive when the alternate-title match is weak even after careful checking.

Role quality, read this way, is a strong directional signal. It is not a salary quote. The occupation that is rising, well-compensated, and skill-intensive at the right level for your background belongs on your list. The one with three years of declining employment and a stalled wage band, regardless of its title, deserves serious skepticism. You now have the tool to tell the difference. What you do not yet have is the clock — whether the hiring process at these companies can actually move fast enough to matter for your timeline.

## Chapter 9 Exercises: Is the Role Any Good

**Project:** Your Own Reallocation Engine

**This chapter adds:** role quality for each target — the confirmed SOC code, employment trend, and wage band read from the BLS/O\*NET compact table — so a live, sponsoring role gets judged on the occupation underneath the title, not the title's marketing.

---

### Exercise 1 — When to Use AI

**The judgment:** In this chapter's work, AI assistance is appropriate for the following tasks:

- **Proposing a candidate SOC code from a messy job title.** — *Why AI works here:* the model has seen thousands of titles and descriptions and is genuinely good at proposing a plausible match — proposing, which you then confirm.
- **Summarizing a compact-table row (trend, wage percentiles, job zone) in plain language.** — *Why AI works here:* reformatting numbers the pipeline produced; checkable against the row.
- **Reformatting wage distributions across roles into a comparison table.** — *Why AI works here:* pure restructuring of data you supply.

**The tell:** You know you are using AI appropriately when you can evaluate the output — when you have independent criteria to judge whether it is correct, complete, and fit for purpose. Here the criterion is the alternate-title list and the compact row.

---

### Exercise 2 — When NOT to Use AI

**The judgment:** In this chapter's work, the following tasks require human judgment. Delegating them to AI is not appropriate — not because AI cannot produce output, but because AI output in these cases cannot be trusted without verification that requires the same expertise as doing the task yourself.

- **Confirming the SOC match.** — *Why AI fails here:* a wrong SOC is silent — it attaches the wrong wages and trend without erroring. Confirmation means checking the posting against the alternate-title list; the model proposes, the data confirms, you judge.
- **Producing the employment trend or wage numbers.** — *Why AI fails here:* these must come from BLS OEWS via the compact table; a model's "this field pays well and is growing" is a guess that will quietly misprice the role.
- **Treating national, lagging OEWS numbers as this company's salary.** — *Why AI fails here:* the compact row is the occupation's gravity, not the specific role's orbit; conflating them is a judgment error about scope.

**The tell:** You know you have crossed the line when you are using AI output as your reason for a conclusion rather than as a tool for reaching one. If you could not explain the conclusion without the AI, the AI did the work that should have been yours.

**Series connection:** This exercise trains **Tier 4 (Metacognitive supervision)** — the model-proposes/data-confirms discipline applied to classification, catching the silent wrong-SOC error before it misprices a role you'd commit years to.

---

### Exercise 3 — LLM Exercise

**What you're building this chapter:** confirmed SOC matches for your target roles, each verified against the alternate-title list, with the trend and wage band attached — the role-quality column of your engine.

**Tool:** Claude (claude.ai chat). You paste a posting plus the alternate-title list from your compact row; chat fits the propose-then-confirm loop.

**The Prompt:**

```
I am classifying job postings to the right Standard Occupational Classification
(SOC) code, then reading occupation-level wage and employment data. The model
PROPOSES a SOC; the alternate-title list CONFIRMS it; I judge. Do NOT produce any
wage or employment number — those come from my compact table, which I paste.

For each posting below I give: the posting title + a description snippet, and the
alternate-title list from the compact row for your PROPOSED SOC.

1. Propose the single best SOC code for the posting and say why in one line.
2. CONFIRM or REJECT: does the posting's title or described work actually appear
   in the alternate-title list I pasted? Quote the matching alternate title, or
   state plainly "not in the list — re-classify."
3. If rejected, propose the next-best SOC and tell me which alternate-title list
   I should paste next to confirm it.
4. Once confirmed, summarize the role-quality read from the compact-row numbers I
   give you (employment trend direction, wage band) and label them "national,
   lagging — not this company's salary."

--- PASTE POSTING + ALTERNATE-TITLE LIST + COMPACT-ROW NUMBERS BELOW ---
[paste here]
```

**What this produces:** confirmed (or rejected-and-rerouted) SOC matches with a labeled role-quality read — filling the `role_quality` column without inventing a single number.

**How to adapt this prompt:**
- *For your own project:* paste the real alternate-title list from your compact table. Without it the "confirm" step is impossible and the SOC is just a guess.
- *For ChatGPT / Gemini:* works as-is; both will confidently assert a SOC without confirming — the alternate-title-list check is the guardrail, keep it mandatory.
- *For a Claude Project:* store the propose/confirm/judge rule and the "national, lagging" caveat in the instructions.

**Connection to previous chapters:** this is Chapter 3's verified-data contract applied to classification — the model's SOC proposal is judgment until the alternate-title list (the record) confirms it.

**Preview of next chapter:** Chapter 10 adds the one factor that can zero out a good role regardless of its quality — your visa timeline.

---

### Exercise 4 — CLI Exercise

**What you're building this chapter:** the compact BLS/O\*NET table and confirmed role-quality rows for your targets — with at least one title re-classified after the alternate-title check fails.

**Tool:** Claude Code. Building the compact table and pulling/verifying rows is a Python-plus-inspection workflow.

**Skill level:** Intermediate.

**Setup:**

Before running this exercise, confirm:
- [ ] `scripts/bls/extract-soc-occupation-table.py` exists and its O\*NET/OEWS source data is available.
- [ ] You have target role titles (from your live postings in Chapter 8).
- [ ] You understand the alternate-title check is the verification step.

**The Task:**

```
Build the role-quality table and verify SOC matches for my target roles. Do not
invent wages, trends, or SOC matches; every number comes from the compact table.

1. Run:  python scripts/bls/extract-soc-occupation-table.py
   Confirm it wrote the compact table to data/bls/compact/ and report the row
   count from the run's output.
2. For each of my target titles, pull the compact row for the SOC I name and
   print: alternate-title list, job zone, employment trend across survey years,
   and the wage distribution.
3. VERIFICATION: for each, check whether my posting title appears in that SOC's
   alternate-title list. Print "confirmed" or "NOT in list — re-classify" for
   each. Do not silently accept an unconfirmed match.
4. For one title that fails the check, find the SOC whose alternate-title list
   DOES contain it, and show the corrected row.
5. Save reports/role-quality.csv: title, confirmed SOC, trend, wage band,
   confirmed(yes/no). Append a RUN_LOG.md entry. Stop.
```

**Expected output:** `reports/role-quality.csv` with confirmed SOC matches, trends, and wage bands, plus one worked re-classification — all traceable to the compact table.

**What to inspect in the output:** for each "confirmed," verify the quoted alternate title actually matches the work, not just the title string. For the re-classified one, does the corrected SOC's wage band differ materially from the wrong one? (That gap is the cost of skipping the check.) Confirm no wage number was rounded or smoothed by the model.

**If it goes wrong:** the likely failure is the agent accepting the first plausible SOC without the alternate-title check — the silent wrong-job error. Recover by forcing the check for every row and re-pulling any unconfirmed match; treat an unconfirmed SOC's numbers as untrusted.

**CLAUDE.md / AGENTS.md note:** add a standing rule — *"A SOC match is unconfirmed until the posting appears in that SOC's O\*NET alternate-title list; OEWS numbers are national and lagging, never quoted as a specific company's salary."* This encodes the chapter's core discipline.

---

### Exercise 5 — AI Validation Exercise

**What you're validating:** an AI role-quality summary that confirmed a SOC without checking the alternate-title list — the silent wrong-job error.

**Validation type:** Reasoning chain (classification + structured data).

**Risk level:** High — the numbers are real but describe a different occupation, so the error is invisible and you'd plan a career around the wrong wage band.

**Setup (pre-generated artifact — option b):** This chapter's lesson is that a wrong SOC fails silently, so validate this pre-generated summary:

> **Role quality — "Growth Analyst" at Helix Bio.** Mapped to SOC 13-1161 (Market
> Research Analysts). The compact row shows stable national employment and a
> median wage of $68,230 — a solid, stable occupation. Verdict: acceptable role
> quality, proceed. *(Alternate-title list for 13-1161, on file: "Market Research
> Analyst," "Market Researcher," "Consumer Insights Analyst," "Survey
> Researcher." The posting describes building and deploying predictive models on
> product usage data.)*

**The Validation Task:**

Evaluate the AI output above using the following checklist. For each item, record: Pass / Fail / Cannot determine — and explain your reasoning.

```
Validation Checklist — Is the Role Any Good

□ Correctness: Was the SOC CONFIRMED against the alternate-title list, or just
  proposed and assumed?
□ Completeness: Does "Growth Analyst" or "building/deploying predictive models"
  appear anywhere in the alternate-title list on file?
□ Scope: Does the described work (predictive modeling on usage data) match
  "Market Research Analyst," or a data-scientist occupation with a different
  wage band?
□ Silent-error check (chapter-specific): If the SOC is wrong, are the real
  numbers ($68,230, stable) describing the actual role or a proxy occupation?
□ Caveat check (chapter-specific): Are the OEWS numbers labeled national and
  lagging, or presented as the role's pay?
□ Failure mode check: Does this output exhibit any of the following?
  - Unconfirmed SOC accepted as confirmed (the silent wrong-job error)
  - Real numbers attached to the wrong occupation
  - Fluent but wrong (a confident "proceed" on a mismatch)
```

**What to do with your findings:**
- If the output passes all checks: use it. (It will not — the work described isn't in the alternate-title list.)
- If it fails one check: re-classify to the SOC whose alternate-title list matches the work, and compare wage bands.
- If it fails multiple checks or you cannot determine pass/fail: this is a "When NOT to Use AI" moment — confirm the SOC against the list yourself before trusting any number.

**AI Use Disclosure prompt:**
After completing this validation, write a two-sentence AI Use Disclosure:
> *Sentence 1:* What AI produced in this exercise and how you used it.
> *Sentence 2:* One specific thing the AI could not determine that required your judgment.

**Series connection:** This exercise trains **Tier 4 metacognitive supervision** — catching the silent classification error where real data describes the wrong thing. A number that traces to a record can still be measuring a different job; the alternate-title check is what catches it.

---

## Prompts

### Figure 9.1 — Title-to-occupation resolution pipeline
**Files:** ../images/09-is-the-role-any-good-bls-onet-role-quality-fig-01.svg · ../d3/09-is-the-role-any-good-bls-onet-role-quality-fig-01.html
**Prompt:** Brutalist horizontal process flowchart: raw posting title → model proposes a code → alternate-title verification gate → confirmed path to the joined O\*NET/OEWS row → rejected path looping back to re-propose → read three features. Keep propose visually distinct from confirm; ochre for propose, red/active for the confirmed path, single-direction arrows with one return loop.

### Figure 9.2 — The silent wrong-SOC error
**Files:** ../images/09-is-the-role-any-good-bls-onet-role-quality-fig-03.svg · ../d3/09-is-the-role-any-good-bls-onet-role-quality-fig-03.html
**Prompt:** Brutalist two-panel comparison on a shared zero-based wage scale: left panel an ambiguous title mapped to a wrong occupation (lower band, alternate-title list lacks the work, blocking marker); right panel the corrected occupation (higher band, match confirmed). The visible gap between the bands is the cost of skipping the check. Ochre/blocked left, red/confirmed right.

### Figure 9.3 — The compact row: three role-quality features
**Files:** ../images/09-is-the-role-any-good-bls-onet-role-quality-fig-02.svg · ../d3/09-is-the-role-any-good-bls-onet-role-quality-fig-02.html
**Prompt:** Brutalist structural schematic: one compact occupation row fanning into three parallel feature panels — an employment-trend line across survey years, a wage band at five percentiles, and a five-step job-zone ladder — with the alternate-title list attached above as the confirmation feed. Equal visual weight per panel, one accent color, hairline connectors.

## Key terms

- **SOC code:** the Standard Occupational Classification identifier for the real occupation underneath a job title; the hinge of the whole chapter.
- **O\*NET:** the occupational database of alternate titles, job zones, and ability/skill ratings — what is this work?
- **BLS OEWS:** national employment and wage estimates per occupation — how many exist and what do they pay?
- **Compact table:** the joined O\*NET + OEWS row per occupation produced by `extract-soc-occupation-table.py`.

## Run-log prompt

Record each target's confirmed SOC code, the employment trend and wage band you read, and any title you had to re-classify against the alternate-title list.

[^soc]: SOC classification (and its measurable misclassification rate) is the subject of `projects/soc_classification_draft.md` + `_methods.md` in this repository — a parallel research track. Its quantitative results contain `[TO DO]` placeholders and must not be cited as final numbers. **[verify]**
# Chapter 10 — The Visa Timeline Manager
*The clock is a gate, not a tiebreaker.*

Here is a thing that happens, and it is quietly devastating when it does. A student has three months of work authorization left. They find a role that fits almost perfectly — the company sponsors, the posting is live, the occupation matches, the quality signals are strong. They apply. They make it through the screens, the take-homes, the panels. Four months later, an offer arrives. And it is worthless. The start date is past the day their authorization ended. They spent the scarcest months of their search — the months they had the least of — chasing an offer that the calendar had already ruled out before the first email went out.

No filter in Chapters 7 through 7 would have caught this. Sponsorship was real. The role was live. The quality was high. The thing that killed it was time, and time is the one constraint that is *yours specifically* — invisible to the company, invisible to every scorer that does not know your dates.

![A horizontal hiring timeline — application, phone screen, technical rounds, panel, offer — crossed by a single bold vertical line marking the end of work authorization; the line falls between the technical rounds and the offer, so the offer sits on the unreachable side of the cliff.](images/10-the-visa-timeline-manager-fig-01.png)
*Figure 10.1 — The calendar gate: a process that runs past authorization*

<!-- → [DIAGRAM: a horizontal timeline showing: "Student applies" → "Phone screen" → "Technical rounds" → "Panel interview" → "Offer" — with a vertical red line labeled "Authorization ends" falling between "Technical rounds" and "Offer"; the visual makes visceral that everything after the red line is unreachable regardless of how good the news is] -->

What I want to sit with before we go further is the structure of this error. The student did not miscalculate. They did not misread a sponsorship tier. They made a decision that was perfectly rational given incomplete information: they applied to a high-quality role without first asking whether the calendar permitted it. The Visa Timeline Manager exists to make that omission impossible — to force the calendar question to the front, before the excitement of a good-looking posting makes it easy to postpone.

---

Three windows govern an international student's runway, and the way they interact is not obvious until you map them.

The first is **OPT** — post-completion Optional Practical Training. After you finish your degree, you have a window of authorized work, and inside that window you may accrue no more than 90 cumulative calendar days of unemployment.[^opt] That ceiling is not a soft guideline. Exceeding it terminates your status, with no grace period. The 90 days do not reset. They accumulate from the first day your OPT begins. Every day you are not employed or not in a valid application process counts against that ceiling whether you notice it or not.

The second is the **STEM OPT extension**. If your degree is in a qualifying STEM field, you are eligible for a 24-month extension beyond the standard OPT period — and critically, the unemployment ceiling rises to 150 days aggregate. Eligibility changes the math entirely. A student without STEM eligibility and four months of authorization has a fundamentally different runway than a STEM-eligible student with four months remaining and the extension not yet filed. The calendar says they are in the same situation. The law says they are not.

The third is the **H-1B lottery window** — the annual cycle of registration, selection, and petition that determines whether a path past OPT exists with a given employer in a given year. The lottery runs on a fixed annual schedule. If your authorization expires before the next window resolves, the H-1B path is not available to you regardless of how willing the employer is to sponsor. Sponsorship and the ability to act on sponsorship are different things, and the lottery timing is what separates them.

![Three stacked horizontal bars on a shared time axis: the standard OPT window with its 90-day unemployment ceiling, the longer STEM OPT extension with its 150-day ceiling, and the fixed annual H-1B lottery window with registration and cap-subject start markers; the true runway is the combination of all three, not just the first bar.](images/10-the-visa-timeline-manager-fig-02.png)
*Figure 10.2 — Three windows of an international student's runway*

<!-- → [INFOGRAPHIC: three stacked horizontal bars representing OPT window, STEM OPT extension, and H-1B lottery window — annotated with key thresholds: 90-day unemployment ceiling, 150-day ceiling, lottery registration month, cap-subject start date — showing how a student's runway is the combination of all three, not just the first bar] -->

What the Visa Timeline Manager does is compress these three windows into a single number: a **timeline factor between 0 and 1** that gets multiplied into a role's composite score.

The design logic of a multiplier rather than an addend matters here. If the timeline factor were just another component that averaged in with sponsorship, fit, liveness, and quality, a strong-enough role could mathematically overcome a bad timeline. A 0.95 fit and a 0.9 quality score could dilute a 0 timeline to something that still looks actionable. That would be wrong — not just suboptimal, but wrong in a way that produces exactly the outcome from the opening case. The multiplier forecloses this. A factor of 0 zeroed into a composite of any magnitude produces 0. The clock is a gate.

---

The factor is computed from eight intake questions the system asks at setup: your visa type, your authorization end date, how many unemployment days you have already used, whether you are STEM-eligible, your field, your target buffer, and the estimated process length for the role being scored. These are first-class constraints, not profile decoration. They are what makes a score *yours* rather than generic.

Conceptually, the computation looks like this:

```text
factor = timeline_factor(
    auth_type              = "OPT",
    auth_end_date          = "2026-08-30",
    unemployment_days_used = 22,
    expected_time_to_start = "16 weeks",
    stem_eligible          = True,
    buffer_target          = "80 days"
)
# returns a value in [0, 1]; 0 = skip regardless
```

The output is always the factor *and* the dates that produced it. A timeline factor you cannot trace to specific dates is a number you cannot defend, and this is the one factor where a silent error costs you the whole search. If the factor says 0 and you cannot see why, you have a data entry problem, not a calendar problem — and those require different responses.

| Input parameter | What it measures | Consequence of error |
|---|---|---|
| `auth_end_date` | The hard cliff — the last day work authorization is valid | Too optimistic (a later date than real) lets a fatal role score as actionable — costs the whole search. Too conservative drops salvageable roles. |
| `unemployment_days_used` | How much of the 90/150-day ceiling is already spent | Undercounting makes the remaining buffer look larger than it is, encouraging slow processes that breach the ceiling — costs status. |
| `expected_time_to_start` | The role's likely process length, today to start date | Too short makes a doomed role look reachable; too long drops a role you could have landed — costs one opportunity. |
| `stem_eligible` | Whether the 24-month extension and 150-day ceiling apply | Asserting eligibility you don't have inflates the entire runway — the most dangerous error; this input belongs to your DSO, not a guess. |

*Each input has asymmetric costs. Being too optimistic costs the whole search; being too conservative costs one opportunity. When in doubt, err conservative — and route eligibility to a qualified human.*

The factor resolves into three cases. A **factor of 0** means the role is skip-regardless: the expected time-to-start exceeds your remaining authorization, and no other signal changes that. A **factor near 1** means comfortable buffer — the expected hiring timeline finishes well inside your authorization with room to spare. A **factor between 0 and 1** is where most of the interesting cases live: buffer-based scaling, where as the expected start date creeps toward the cliff, the factor falls — gently penalizing roles that are probably fine but cut it close, so that all else equal the engine prefers the role you can safely land.

---

Let me walk through three roles for a single student to show how these cases feel in practice.

The student is a STEM-eligible master's graduate. OPT ends in roughly five months. Twenty-two unemployment days already used. Self-imposed target: an 80-day buffer below the 90-day ceiling, which functions as a margin of safety — not a legal threshold, just a planning discipline built into the engine.

**Role A** is a large firm. Its hiring process historically runs about five months: multiple rounds, committee review, compensation negotiation, offer processing. The expected start date lands past the authorization end. Factor = 0. Skip regardless — and the reason it deserves that label, not just "low priority," is that applying does not just waste time. It consumes unemployment days while you wait, which erodes the buffer you need for the roles you *can* land.

**Role B** is a startup that can move in about six weeks when motivated. Expected start lands with months of buffer. Factor ≈ 1. No timeline objection — the other factors decide.

**Role C** is a mid-size firm, roughly twelve-week process. Expected start lands inside authorization but eats most of the buffer. Factor ≈ 0.6 — kept, but penalized relative to B. If Role C and Role B were otherwise equal, the engine prefers B, because the candidate who lands B does not spend the last weeks of their authorization anxiously waiting for Role C's offer.

![A horizontal bar chart of three roles, each bar running from today to its expected start date, against a solid vertical line for the authorization end and a dotted line for the 80-day buffer target: Role A extends past the authorization line (skip-regardless), Role B finishes well short of the buffer (comfortable), and Role C finishes between the buffer and the cliff (kept but penalized).](images/10-the-visa-timeline-manager-fig-03.png)
*Figure 10.3 — Three roles against the authorization cliff*

<!-- → [CHART: a horizontal bar chart showing the three roles with their expected start dates plotted against the student's authorization end date — Role A's bar extends past the end date (red), Role B finishes well short (green), Role C finishes just inside (yellow); a vertical dotted line marks the 80-day buffer target] -->

The decision rule that follows from this is simple to state and genuinely hard to execute: drop Role A *now*, before you invest more time in it. Free those weeks for Role B and for the networking that surfaces roles like Role B. Keep Role C with eyes open. The hard part is executing the drop on a role that looks excellent in every other dimension. The factor is designed to make that drop automatic — not a judgment call you have to make while excited about a good-looking posting, but a mathematical output you read before the excitement has a chance to override the calendar.

---

Now let me tell you what this factor cannot do, because the honest limits of any tool are part of using it correctly.

The factor knows your dates and a company's typical pace. It does not know that this particular hiring manager will fast-track you because their team is on fire, collapsing a five-month process to three weeks. It does not know that you would be willing to accept a role in a different country if the U.S. clock runs out, which would change what "skip" means for you entirely. And it absolutely cannot practice immigration law.

The difference between eligible and ineligible for a STEM extension can hinge on a detail — the CIP code on your transcript, a filing timing question, a program classification — that only an immigration professional should rule on. The factor gates out the impossible. The negotiable edges and the legal specifics stay human. This is not a caveat to be skim-read; it is load-bearing. A student who treats a factor of 0.4 as authorization to apply to a borderline role without consulting their DSO has misread what the number is. It is a planning multiplier, not legal advice.

![A decision tree from a single "factor computed" root: a factor of 0 branches to skip-regardless and reallocate the freed time; a low-but-positive factor branches to apply only if strong on the other factors and an accelerated process is genuinely possible; a high factor branches to no timeline objection, let the other factors decide; an advisor-check node flags that uncertain eligibility goes to a qualified advisor, not the system.](images/10-the-visa-timeline-manager-fig-04.png)
*Figure 10.4 — Timeline-factor decision tree*

<!-- → [DIAGRAM: a decision tree beginning at "Factor computed" — branch from 0 to "Skip regardless / reallocate time (Ch. 2)," branch from low but > 0 to "Apply only if strong on other factors AND accelerated process is possible," branch from high to "No timeline objection — let sponsorship, fit, liveness, quality decide"; each terminal node also shows a human-judgment check: "Verify with DSO if STEM eligibility is uncertain"] -->

There is one more error worth naming before this chapter closes. It is the error almost everyone makes at least once: finding a role that looks excellent in every other dimension and mentally filing the timeline question under "figure out later." Later is exactly when it is too late. The excitement of a good role is precisely the moment when the timeline question feels most like an interruption. That feeling is the signal to compute the factor first — because a factor of 0 means the excitement is a trap, and you want to know that before the four months, not after.

Five numbers now describe every role you are considering: sponsorship, fit, liveness, quality, and timeline. One of them can zero out all the others. The question is how the engine fuses them into a single decision — and why, in that fusion, sponsorship gets the loudest vote.

---

## Chapter 10 Exercises: The Visa Timeline Manager

**Project:** Your Own Reallocation Engine

**This chapter adds:** the gate — a timeline factor between 0 and 1, computed from your real dates, that multiplies into each role's score and zeroes out the ones the calendar has already ruled out, before excitement about a good posting can override it.

---

### Exercise 1 — When to Use AI

**The judgment:** In this chapter's work, AI assistance is appropriate for the following tasks:

- **Computing date arithmetic — weeks between today, an expected start, and your auth-end date.** — *Why AI works here:* arithmetic over dates you supply, verifiable on a calendar.
- **Summarizing which of your roles got which factor and why.** — *Why AI works here:* reformatting the factor outputs you generated; checkable against them.
- **Drafting the question you'll take to your DSO or immigration attorney.** — *Why AI works here:* it helps you phrase the question; it does not answer it.

**The tell:** You know you are using AI appropriately when you can evaluate the output — when you have independent criteria to judge whether it is correct, complete, and fit for purpose. Here the criteria are a calendar and a qualified human (DSO/attorney) for anything legal.

---

### Exercise 2 — When NOT to Use AI

**The judgment:** In this chapter's work, the following tasks require human judgment. Delegating them to AI is not appropriate — not because AI cannot produce output, but because AI output in these cases cannot be trusted without verification that requires the same expertise as doing the task yourself.

- **Ruling on STEM eligibility, CIP codes, or any immigration-law specific.** — *Why AI fails here:* eligibility can hinge on a transcript detail only an immigration professional should rule on; a confident model answer here is the most dangerous kind of wrong. This is not legal advice and a model cannot make it so.
- **Overriding a factor of 0 on an informal "we can move fast" signal.** — *Why AI fails here:* whether to act on intent the historical estimate can't see is a stakes judgment with your whole search on the line — yours, not the model's.
- **Deciding whether a 0.3–0.6 factor justifies applying.** — *Why AI fails here:* this depends on your risk tolerance, your other options, and whether you'd accept a role abroad — values the model doesn't hold.

**The tell:** You know you have crossed the line when you are using AI output as your reason for a conclusion rather than as a tool for reaching one. If you could not explain the conclusion without the AI, the AI did the work that should have been yours.

**Series connection:** This exercise trains **Tier 7 (Wisdom — values and accountability)** with a **Tier 4** edge. The timeline gate is where the binding constraint is your own stakes and the law; no scorer can own a decision whose consequence — losing status — only you bear.

---

### Exercise 3 — LLM Exercise

**What you're building this chapter:** timeline factors for your target roles, each shown with the dates that produced it, and a drop list — with every legal-eligibility question routed to a human, not answered by the model.

**Tool:** Claude (claude.ai chat). You supply your dates; chat computes and explains.

**The Prompt:**

```
Help me compute a visa "timeline factor" for each role I'm considering. The
factor is in [0,1] and acts as a GATE: 0 means skip regardless (expected start
is past my authorization end); near 1 means comfortable buffer; in between means
the start eats into my buffer and the role is penalized but kept.

My inputs (use ONLY these; do not assume any I don't give):
- Visa type and authorization end date: [FILL IN]
- Unemployment days already used: [FILL IN]
- STEM-eligible? [FILL IN] (note: do NOT rule on my eligibility — if it's
  uncertain, tell me to confirm with my DSO)
- Buffer target: [FILL IN, e.g. 80 days]
- Roles, each with an expected time-to-start: [FILL IN list]

Do four things:
1. For each role, compute the factor (0, near 1, or in between) and SHOW THE
   DATES: today + expected-time-to-start vs. my auth-end and buffer target.
2. Produce a drop list: which roles are factor 0 and should be dropped now to
   free time (cite Chapter 2's reallocation).
3. For any role in the 0<factor<1 band, state what single fact (an accelerated
   process) would change the decision and how I'd verify it.
4. Flag every point where an answer depends on immigration law or my STEM
   status, and tell me to confirm it with my DSO or an attorney. Do NOT give me
   legal advice or assert my eligibility.
```

**What this produces:** a factor-per-role table with visible date math, a drop list, and explicit hand-offs to your DSO for anything legal.

**How to adapt this prompt:**
- *For your own project:* fill every `[FILL IN]` with your exact dates — an approximate auth-end date defeats the entire exercise.
- *For ChatGPT / Gemini:* works as-is; both are prone to confidently asserting STEM eligibility — keep the "do NOT rule on eligibility" instruction prominent.
- *For a Claude Project:* store your dates and buffer target in the instructions so every role you score inherits the gate.

**Connection to previous chapters:** the factor multiplies the sponsorship/liveness/quality work from Chapters 7–9; a 0 here overrides all of it, and the freed time flows into Chapter 2's networking and portfolio blocks.

**Preview of next chapter:** Chapter 11 fuses all five numbers — sponsorship, fit, liveness, quality, timeline — into one auditable composite score.

---

### Exercise 4 — CLI Exercise

**What you're building this chapter:** your eight intake answers encoded into the engine, the timeline factor run across your whole target list, and the factor-plus-dates recorded per role so a 0 is a logged, traceable gate.

**Tool:** Claude Code. Wiring your intake into config and running the factor over the list is a code-plus-data workflow.

**Skill level:** Intermediate.

**Setup:**

Before running this exercise, confirm:
- [ ] The timeline-factor code/config exists in your repo (the eight intake fields).
- [ ] You have your exact dates: auth type, auth-end date, unemployment days used, STEM status, buffer target.
- [ ] You have a target list with an expected time-to-start per role.

**The Task:**

```
Set up and run the visa timeline factor across my target list. Do not assume any
date or eligibility — use only the values I provide, and never assert my STEM
eligibility (flag it for my DSO instead).

1. Show me the eight timeline intake fields and where they're configured. Help me
   set them to the values I give you. Echo them back for confirmation BEFORE
   running anything — a wrong date here is the one error that costs the search.
2. Run the timeline factor over every role in my target list.
3. For each role, output the factor AND the dates that produced it (today +
   expected-time-to-start vs. auth-end and buffer). A factor with no dates is not
   acceptable.
4. Save reports/timeline.csv: role, factor, expected start, auth-end, buffer
   status. Separately list every factor-0 (skip-regardless) role.
5. Append a RUN_LOG.md entry noting the intake values used (dates) and the count
   of skip-regardless roles. Stop.
```

**Expected output:** `reports/timeline.csv` with a traceable factor-and-dates per role, plus an explicit skip-regardless list.

**What to inspect in the output:** re-check the echoed dates against your actual I-20/EAD before trusting any factor — the chapter's named catastrophic error is a mis-entered auth-end date producing a 0.7 instead of a 0. Confirm every factor shows its dates. Confirm no role asserts STEM eligibility as settled.

**If it goes wrong:** the highest-stakes failure is an optimistic factor from a wrong date (or the agent guessing a missing date). Recover by re-confirming every date from your official documents and re-running; never let the agent fill a missing date with a plausible one.

**CLAUDE.md / AGENTS.md note:** add a standing rule — *"Timeline factors must display the dates that produced them; the engine never asserts STEM eligibility or gives immigration-law rulings — those are flagged for the DSO/attorney."* This is the load-bearing safety rule of the whole engine.

---

### Exercise 5 — AI Validation Exercise

**What you're validating:** an AI recommendation that both gave immigration-law advice and let a strong role override a fatal timeline — the two errors that lose the search.

**Validation type:** Reasoning chain (with a high-stakes legal component).

**Risk level:** High — acting on this can terminate immigration status; there is no recovery.

**Setup (pre-generated artifact — option b):** This chapter's lessons are "the clock is a gate, not a tiebreaker" and "the factor is not legal advice," so validate this pre-generated recommendation:

> **Recommendation — Role A (MegaCorp).** This is an excellent role: Proven
> sponsor, strong fit, live posting, great wage band. The hiring process runs
> about 5 months and your OPT ends in 4 months, but the role scores so well
> overall that it averages out to a strong recommendation — apply. Also, since
> your degree is in a tech field, you're definitely STEM-eligible, so you'll have
> plenty of runway with the 24-month extension. No need to check with anyone;
> you're clear to proceed.

**The Validation Task:**

Evaluate the AI output above using the following checklist. For each item, record: Pass / Fail / Cannot determine — and explain your reasoning.

```
Validation Checklist — The Visa Timeline Manager

□ Correctness: Is the timeline treated as a GATE (zeroes the score) or as an
  addend that strong other factors can "average out"?
□ Completeness: Does it acknowledge that a 5-month process past a 4-month
  authorization makes the offer unreachable regardless of quality?
□ Scope: Did it give an immigration-law ruling ("you're definitely
  STEM-eligible") it has no standing to give?
□ Gate check (chapter-specific): With expected start past auth-end, what should
  the factor be, and what does that do to the composite?
□ Legal-boundary check (chapter-specific): Should eligibility be asserted by a
  model, or confirmed by a DSO/attorney?
□ Failure mode check: Does this output exhibit any of the following?
  - Treating the timeline as a tiebreaker instead of a gate (additive dilution)
  - Giving immigration-law advice / asserting STEM eligibility
  - Fluent but wrong (a confident "proceed" on an unreachable, legally-uncertain
    role)
```

**What to do with your findings:**
- If the output passes all checks: proceed. (It will not — it makes both of the chapter's named errors.)
- If it fails one check: recompute the factor as a gate and strip any legal assertion.
- If it fails multiple checks or you cannot determine pass/fail: this is a "When NOT to Use AI" moment — gate the role yourself and take eligibility to your DSO.

**AI Use Disclosure prompt:**
After completing this validation, write a two-sentence AI Use Disclosure:
> *Sentence 1:* What AI produced in this exercise and how you used it.
> *Sentence 2:* One specific thing the AI could not determine that required your judgment.

**Series connection:** This exercise trains **Tier 7 wisdom and accountability** — recognizing that some decisions carry consequences (loss of status) and some questions (eligibility, the law) belong to qualified humans. The model can compute a date; it cannot bear the outcome of getting it wrong.

## Prompts

### Figure 10.1 — The calendar gate: a process that runs past authorization
**Files:** ../images/10-the-visa-timeline-manager-fig-01.svg · ../d3/10-the-visa-timeline-manager-fig-01.html
**Prompt:** Brutalist horizontal timeline of hiring stages (application → phone screen → technical rounds → panel → offer) with a single bold vertical authorization-ends line falling between technical rounds and offer; render everything past the line muted/blocked to make the post-cliff offer visibly unreachable. Red for the cliff and unreachable region, ink for reachable stages, single-direction arrows.

### Figure 10.2 — Three windows of an international student's runway
**Files:** ../images/10-the-visa-timeline-manager-fig-02.svg · ../d3/10-the-visa-timeline-manager-fig-02.html
**Prompt:** Brutalist three stacked horizontal bars on a shared left-anchored time axis: standard OPT (90-day ceiling marker), STEM extension (longer, 150-day ceiling marker), and the H-1B lottery as a fixed annual window with registration and cap-subject markers. Distinct neutral hues per window, one accent, hairline tick markers; the runway is the combination, not the first bar.

### Figure 10.3 — Three roles against the authorization cliff
**Files:** ../images/10-the-visa-timeline-manager-fig-03.svg · ../d3/10-the-visa-timeline-manager-fig-03.html
**Prompt:** Brutalist horizontal bar chart anchored at a common origin (today), three role bars to their expected start dates, with a solid authorization-end line and a dotted buffer-target line. Role A past the cliff (red, skip), Role B short of the buffer (active hue, comfortable), Role C between buffer and cliff (ochre, kept-but-penalized). Honest shared origin, mono axis labels.

### Figure 10.4 — Timeline-factor decision tree
**Files:** ../images/10-the-visa-timeline-manager-fig-04.svg · ../d3/10-the-visa-timeline-manager-fig-04.html
**Prompt:** Brutalist top-down decision tree from a "factor computed" root: branch 0 → skip-regardless / reallocate; branch low>0 → apply only if strong elsewhere and acceleration possible; branch high → no timeline objection. Attach an advisor-check side node (verify uncertain eligibility with a qualified advisor). Red for skip, ochre for the conditional middle, active hue for the clear branch; single-direction arrows.

[^opt]: F-1 post-completion OPT: max 90 aggregate days of unemployment (150 with STEM OPT extension); exceeding it terminates the record with no grace period. USCIS Policy Manual, Vol. 2, Part F, Ch. 5: https://www.uscis.gov/policy-manual/volume-2-part-f-chapter-5
# Chapter 11 — The Bayesian Role Scorer
*The constraint unique to you dominates the factor everyone told you was supreme.*

Start with the sentence. "Google is a great company, so I should apply." It is the most natural sentence in a job search, and it is wrong in a specific, costly way. Great by what measure, and for whom? For a candidate who needs visa sponsorship, "great company" and "good target" are two different questions, and conflating them is how the eight-hour applicant from Chapter 2 spent a month applying to firms that would never sponsor the role. This chapter replaces that sentence with arithmetic. And the arithmetic, for a non-sponsor, says no — however great the company.

I want to be honest about what that arithmetic is going to cost you emotionally, because it will fight your instincts in a specific place. The chapter demotes *fit* — the thing you have been told your entire life is what matters in a job search — below a constraint most candidates never put in the equation at all. The demotion is not an error in the math. It is the math doing exactly what it should.

## What the scorer is and what it takes as input

The Bayesian Role Scorer is the decision core of the pipeline. Everything built in the preceding chapters converges here. Sponsorship probability and tier (Chapter 7), liveness (Chapter 8), role quality and occupation code (Chapter 9), your timeline and the start-date clock (Chapter 10) — each of those chapters produced a number. This chapter combines them.

The new ingredient is fit: the probability that you are actually a match for this specific role, estimated by comparing your CV against the job description. I want to name this clearly before we go further: fit is a model judgment. It is not a record. It is not a verified fact from a government database. It is a language model comparing two documents and returning a probability. That label — *model judgment* — matters, and it will appear attached to fit throughout this chapter, because a composite that hides where its components came from is exactly the fluent-but-ungrounded artifact Chapter 1 taught you to distrust.

With all four inputs in hand, the composite takes this form:

**Composite ≈ P(sponsorship) × 0.35 + P(fit | CV, JD) × 0.30 + [other weighted factors]**

— the whole expression multiplied by a liveness factor and by a timeline factor, with a decision threshold near 0.3 that maps the composite to one of three recommendations: **Apply**, **Consider**, or **Skip**.[^weights]

There are three design decisions baked into this expression that are worth understanding from first principles, because each one will produce a recommendation that surprises you until you see the reasoning underneath it.

## Why sponsorship is weighted highest

Sponsorship carries a weight of 0.35 — above fit at 0.30. The question is why.

Weights in a scoring system should reflect which constraint is most binding for the specific person the system is built for. For a domestic applicant, sponsorship isn't a question. Fit dominates, because fit is the thing that will determine whether you get the offer. But for an international student, sponsorship is the constraint that silently kills the most applications — not because the candidate was unqualified, but because the company never sponsored in the first place and the candidate never knew to check. The application went in, the résumé cleared the ATS, and then something in the process stopped moving. Sponsorship was the reason. It is never written on a rejection email.

So the weighting is not a claim that sponsorship matters more than competence in the world. It is a claim that, for you, it is the factor most likely to cause an invisible rejection — and invisible rejections are the ones most worth preventing at the top of the funnel, before time is spent.

## Why liveness and timeline are multipliers, not addends

Fit and sponsorship are *votes*. They contribute proportionally to the composite. A higher sponsorship probability raises the score; a lower one lowers it. The contribution is graduated.

Liveness and timeline are different in kind. They are *gates*. A ghost posting — liveness approaching zero — makes the composite approach zero regardless of how strong the sponsorship and fit scores are. A timeline you cannot meet — start date constraints that make the role impossible — does the same. No amount of fit or sponsorship can carry a role through a gate that is closed.

This is the math expressing a truth about the job search, not imposing a rule on top of it. A perfect role at a sponsoring company is worth nothing if the posting is fiction or you cannot start in time. The multiplicative structure is the honest description of that reality.

![Systems diagram of the composite: two weighted votes — a dominant sponsorship input and a lighter fit input — merge at a summing junction, then pass through two inline gates (liveness, then timeline) that can collapse the flow toward zero, before reaching a threshold node that branches into Apply, Consider, or Skip.](images/11-the-bayesian-role-scorer-fig-01.png)
*Figure 11.1 — The composite: votes, gates, and threshold*

## The worked case — one posting, all four factors traced

Let me make the composite concrete. A live posting at the Cambridge biotech from Chapter 7 — Proven tier, data role, our STEM-eligible graduate.

P(sponsorship) ≈ 0.9. *Source: LCA and H-1B records from Chapter 7.* This is a record, not a judgment.

P(fit | CV, JD) ≈ 0.7. *Source: model judgment, CV compared to the job description.* This is a judgment, labeled as such.

Liveness ≈ 1. *Source: ATS signals from Chapter 8.* The posting passed all five checks.

Timeline factor ≈ 0.85. *Source: the reader's OPT expiration and estimated processing window from Chapter 10.*

High sponsorship — the dominant term — multiplied by reasonable fit, with a live posting and comfortable timeline. The composite lands well above threshold. The recommendation is **Apply**.

Now the contrast. The same graduate. The same fit of 0.7. The same liveness and timeline. Applied to the household-name non-sponsor: P(sponsorship) ≈ 0. The dominant term — sponsorship at 0.35 weight — contributes almost nothing. No amount of fit rescues it. The composite falls below threshold. The recommendation is **Skip**.

The candidate did not get worse. The company did not get less impressive. The binding constraint changed, and the weighting surfaced it. That is the scorer's job.

![Two parallel four-segment stacks for the same candidate. In the left stack (a sponsoring company) the sponsorship segment is large; in the right stack (a non-sponsor) it is nearly absent while fit, liveness, and timeline are identical. The composite bars below sit on a shared zero baseline: the left clears the threshold line and resolves to Apply, the right falls below and resolves to Skip.](images/11-the-bayesian-role-scorer-fig-02.png)
*Figure 11.2 — Same candidate, same fit: sponsorship decides*

| Factor | Cambridge biotech (Proven) | Household-name non-sponsor |
|---|---|---|
| P(sponsorship) — weight 0.35 | 0.9 *(record)* | ~0.0 *(record)* |
| P(fit \| CV, JD) — weight 0.30 | 0.7 *(model judgment)* | 0.7 *(model judgment)* |
| Liveness (multiplier) | 1.0 *(ATS signals)* | 1.0 *(ATS signals)* |
| Timeline factor (multiplier) | 0.85 *(OPT clock)* | 0.85 *(OPT clock)* |
| **Composite** | **above threshold** | **below threshold** |
| **Recommendation** | **Apply** | **Skip** |

*Same candidate, same fit — the dominant term (sponsorship) determines the outcome.*

## The three-way recommendation and when to override

**Apply** means the composite is above threshold and sponsorship and timeline are both healthy. This is the role that earns the targeted two hours of focused application work from Chapter 2.

**Consider** means the composite is near threshold, or strong on most factors with one soft spot — a Likely sponsorship tier rather than Proven, for instance. Apply only if this role beats your other Considers and you have buffer in your timeline.

**Skip** means the composite is below threshold, or zeroed by liveness or timeline. The recommendation is not that the company is bad. It is that your time, on a finite clock, is better spent elsewhere.

And then there is **Override** — the recommendation the system will not give you, but that you can give yourself. If you hold private information the data cannot — the hiring manager is a contact who told you directly they're actively interviewing, or the company just quietly started sponsoring last month and the LCA record hasn't caught up — you can override the scorer. But the discipline is this: write down what you knew that the scorer didn't. An override with a documented reason is a legitimate correction. An override without one is just ignoring the math because you like the company.

![Two-axis decision map: sponsorship probability on the horizontal axis, fit score on the vertical. The high-sponsorship, high-fit corner is Apply; the two mixed corners are Consider; the low-sponsorship, low-fit corner is Skip. Two points at identical fit but different sponsorship land in the Apply and Skip regions respectively.](images/11-the-bayesian-role-scorer-fig-03.png)
*Figure 11.3 — Apply / Consider / Skip decision regions*

<!-- → [INFOGRAPHIC: Four-quadrant grid. X-axis: sponsorship probability (low → high). Y-axis: fit score (low → high). Regions labeled: top-right = Apply, top-left and bottom-right = Consider, bottom-left = Skip. Overlay: two data points for the worked example (Cambridge biotech = Apply zone, non-sponsor = Skip zone despite identical Y position). Caption: "The Apply/Consider/Skip regions show why fit alone doesn't determine the recommendation — the sponsorship axis moves you horizontally, not vertically."] -->

## The cautionary mirror — when scoring goes wrong

A different company built a hiring-match score by training on real managers' past decisions. The system learned to replicate those decisions, including the biases embedded in them — treating "what we did before" as "what is correct." A lawsuit (*Kistler v. Eightfold*) now asks a court to require what good scoring should have demanded from the start: disclose the score, allow disputes, fix the audit.[^eightfold]

Notice what separates that system from this one. The Eightfold scorer learned from opaque history; its weights are unknown even to the company that built it. This scorer's weights are stated — sponsorship 0.35, fit 0.30 — and each factor traces back to a named source. You can look at a recommendation and see exactly why it said what it said.

A composite score is a powerful tool and a dangerous one. The safety is not the math. It is the auditability. If you ever cannot explain why a role scored what it did — tracing each term to its source — distrust the recommendation before you distrust your confusion.

![Two-column comparison. The left column (this scorer) shows stated weights as labeled contributors, each traced by a line back to a named source and terminating in a recommendation whose every term can be followed. The right column (an opaque scorer) shows weights sealed inside a box trained on a stack of past decisions, with no traceable lines from the recommendation back to any source.](images/11-the-bayesian-role-scorer-fig-04.png)
*Figure 11.4 — Auditable vs. opaque scorer*

| Property | This scorer | Eightfold-style scorer |
|---|---|---|
| Weight source | Stated up front (0.35 / 0.30 …) | Learned from past manager decisions |
| Factor sourcing | Explicit — each term names its source | Opaque — internals unknown even to the builder |
| Auditability | Every term traceable to a record or labeled judgment | Recommendation cannot be traced |
| Failure mode | Bad input laundered into a confident output | Bias laundered into a confident output |

*The safety of a composite score is not the math — it's whether you can see why it said what it said.*

## What the machine could not know

The composite knows four numbers. It cannot know that the "0.7 fit" undersells you because your one unusual project is exactly what this team needs and no keyword in the job description captured it. It cannot know that a company scored Skip just began sponsoring last month. It cannot know that you would thrive at a lower-scored role and burn out at a higher one.

The scorer's gift is that it makes the usual case explicit and defensible. Its danger is that a single confident number invites you to stop thinking. The discipline from Chapter 1 returns here in full: don't ask whether the score is impressive. Ask what it could not know, and whether you hold any of that knowledge. The score reduces uncertainty. It does not eliminate it — and pretending otherwise is the specific error that makes composite scores harmful rather than useful.

## Where this leaves you

The score says Apply. You know why it says Apply, term by term, source by source. The posting is real, the company sponsors, the fit is reasonable, and the clock is not against you.

What the scorer cannot do is write the application. And for an international candidate, how you frame your work authorization is where strong candidates get rejected for reasons that have nothing to do with their ability. The chapter that follows is about that problem. You earned the application. Now you have to write it.

---

## Chapter 11 Exercises: The Bayesian Role Scorer

**Project:** Your Own Reallocation Engine

**This chapter adds:** the decision core — the four factors from Chapters 7–10 fused into one auditable composite that returns Apply / Consider / Skip per role, plus the Override discipline that lets your private knowledge correct the math without ignoring it.

---

### Exercise 1 — When to Use AI

**The judgment:** In this chapter's work, AI assistance is appropriate for the following tasks:

- **Computing the composite from factors you supply.** — *Why AI works here:* the weighted-vote-times-multiplier arithmetic is checkable by hand in a minute.
- **Labeling each term by source type (record / model judgment / your input).** — *Why AI works here:* it's classification against definitions you hold; you verify each label against where the number actually came from.
- **Drafting the written Override note when you correct the score.** — *Why AI works here:* it helps you phrase what you knew that the data didn't; you supply the knowledge.

**The tell:** You know you are using AI appropriately when you can evaluate the output — when you have independent criteria to judge whether it is correct, complete, and fit for purpose. Here the criteria are the formula and the source of every term.

---

### Exercise 2 — When NOT to Use AI

**The judgment:** In this chapter's work, the following tasks require human judgment. Delegating them to AI is not appropriate — not because AI cannot produce output, but because AI output in these cases cannot be trusted without verification that requires the same expertise as doing the task yourself.

- **Treating the fit score as a verified fact.** — *Why AI fails here:* fit is a model judgment (a CV-vs-JD comparison), not a record; laundering it into the composite as if it were sourced is the exact fluent-but-ungrounded move Chapter 1 warns against.
- **Deciding whether to override a recommendation.** — *Why AI fails here:* a legitimate override rests on private information the data cannot hold (a contact actively interviewing, a sponsorship policy the LCA record hasn't caught up to) — knowledge only you have.
- **Judging whether the weights fit your situation.** — *Why AI fails here:* the 0.35/0.30 weighting encodes a claim about your binding constraint; whether it's right for you is a values/stakes judgment, not a setting to accept on faith.

**The tell:** You know you have crossed the line when you are using AI output as your reason for a conclusion rather than as a tool for reaching one. If you could not explain the conclusion without the AI, the AI did the work that should have been yours.

**Series connection:** This exercise trains **Tier 4 (Metacognitive supervision)** with a **Tier 7** edge — auditability (tracing every term to its source) is metacognition made into a habit, and the override is where your stakes legitimately overrule the math.

---

### Exercise 3 — LLM Exercise

**What you're building this chapter:** composite scores and Apply/Consider/Skip recommendations for your target roles, each term labeled by source, with the cases where fit is doing too much work flagged.

**Tool:** Claude (claude.ai chat). You paste your four real factors per role; chat fits.

**The Prompt:**

```
Help me compute a Bayesian composite score per role and recommend Apply /
Consider / Skip. The structure: sponsorship and fit are weighted VOTES
(sponsorship ~0.35, fit ~0.30, plus other weighted factors); liveness and
timeline are MULTIPLIERS (gates that drive the composite toward zero). Threshold
~0.3. Do NOT invent any factor value — use only what I paste.

For each role below I give: P(sponsorship) and its source, P(fit) and its source,
liveness, timeline factor.

1. Compute the composite and the recommendation, showing the arithmetic.
2. Label EVERY term by source type: record / model judgment / my input.
   Flag fit explicitly as a model judgment.
3. Flag any role where a HIGH fit is the main thing keeping a LOW-sponsorship role
   above threshold — i.e. where fit is "rescuing" a likely non-sponsor. Say so
   plainly; that's the chapter's central error.
4. For any role I mark for Override, draft the one-line note: what I know that the
   scorer doesn't. Do not invent the private fact — ask me for it.

--- PASTE ROLES + FOUR FACTORS EACH BELOW ---
[paste here]
```

**What this produces:** an auditable score sheet — recommendation, traced terms, and fit-rescue flags — that fills the `decision` column of your `targets.csv`.

**How to adapt this prompt:**
- *For your own project:* paste real factor values from Chapters 7–10. The "label by source" step only works if you tell it where each number came from.
- *For ChatGPT / Gemini:* works as-is; both may quietly treat fit as authoritative — keep the "flag fit as model judgment" instruction.
- *For a Claude Project:* store the weights, the gate/vote distinction, and the override rule in the instructions.

**Connection to previous chapters:** this consumes every prior number (sponsorship, liveness, role quality, timeline) and applies Chapter 5's verb discipline — the composite says exactly what its sources warrant.

**Preview of next chapter:** the score says Apply — Chapter 12 is about writing the application, specifically how to frame your work authorization without losing the role to a misunderstanding.

---

### Exercise 4 — CLI Exercise

**What you're building this chapter:** composite scores for your whole target list via the scorer recipe, with every term traceable to its source and every override logged with a reason.

**Tool:** Claude Code. Running the scorer across the list, tracing terms, and logging is a code-plus-data workflow.

**Skill level:** Intermediate.

**Setup:**

Before running this exercise, confirm:
- [ ] You have factor outputs from Chapters 7–10 for your targets.
- [ ] The scorer / `oferta` recipe exists in your repo.
- [ ] Your `CLAUDE.md` carries the verified-data contract.

**The Task:**

```
Run the Bayesian role scorer over my target list. Do not invent any factor;
every term must trace to a source (record, model judgment, or my input).

1. For each role, run the scorer and output: the composite, the recommendation
   (Apply/Consider/Skip), and EACH term labeled by source. Fit must be labeled
   "model judgment."
2. Verify the gate structure: confirm that for any role with timeline factor 0 or
   liveness ~0, the composite is ~0 regardless of sponsorship/fit. Show one such
   role as proof, or flag if a gate isn't behaving as a gate.
3. Save reports/scores.csv: role, composite, recommendation, each term + source.
4. For any role where I choose to Override, append a RUN_LOG.md entry with the
   override and the one-line reason (what I knew that the data didn't). Do not
   override on your own.
5. Show me scores.csv and the gate-check proof. Stop.
```

**Expected output:** `reports/scores.csv` with traced terms and recommendations, a proof that gates zero the composite, and any overrides logged with reasons.

**What to inspect in the output:** confirm the gate check actually zeroed a closed-gate role (the Chapter 16 build bug is a gate silently acting as a vote). Verify fit is labeled model judgment everywhere. Spot-check one Apply: does the arithmetic trace, term by term?

**If it goes wrong:** the highest-stakes failure is a timeline/liveness gate behaving as a weighted vote, letting an impossible role score "Consider." Recover by inspecting the composite formula directly and re-running the gate check; never trust a recommendation whose gate behavior you haven't verified.

**CLAUDE.md / AGENTS.md note:** add a standing rule — *"The scorer must label every term by source (fit = model judgment); liveness and timeline are multipliers, not votes; overrides require a logged reason naming the private fact."* This pins the chapter's auditability requirement into the repo.

---

### Exercise 5 — AI Validation Exercise

**What you're validating:** a composite recommendation that let high fit rescue a non-sponsor and hid where its numbers came from — the Eightfold-style opaque score the chapter warns against.

**Validation type:** Reasoning chain (over a composite).

**Risk level:** High — a confident "Apply" on a non-sponsor sends a day of effort into an invisible rejection.

**Setup (pre-generated artifact — option b):** This chapter names two errors — fit can't rescue a non-sponsor, and a score without provenance is just an opinion — so validate this pre-generated output:

> **Role recommendation — BrandCo (household name).** Composite: 0.61 → APPLY.
> This is a great company and you're a strong match — the fit is excellent (0.85),
> the role is live, and the timeline works. A well-known brand like this is always
> worth applying to. Recommendation: Apply with confidence.
> *(Not shown: P(sponsorship) for this role ≈ 0.05 — BrandCo has essentially no
> LCA history for roles like yours. The composite above weighted fit heavily and
> did not surface the sponsorship term or its source.)*

**The Validation Task:**

Evaluate the AI output above using the following checklist. For each item, record: Pass / Fail / Cannot determine — and explain your reasoning.

```
Validation Checklist — The Bayesian Role Scorer

□ Correctness: Is each term traceable to a source, or is the composite an opinion
  in a formatted box?
□ Completeness: Is the sponsorship term shown at all? What is it, and what should
  a ~0.05 sponsorship do to a composite for an international candidate?
□ Scope: Did the recommendation lean on "great company / well-known brand" —
  reputation rather than the binding constraint?
□ Fit-rescue check (chapter-specific): Is a high fit (0.85) keeping a near-zero-
  sponsorship role above threshold? Can fit rescue a non-sponsor?
□ Auditability check (chapter-specific): Could you reconstruct why this scored
  0.61 from what's shown? If not, what should you trust first — the score or your
  confusion?
□ Failure mode check: Does this output exhibit any of the following?
  - Fit rescuing a non-sponsor (the chapter's central inversion)
  - Non-auditable composite (sources hidden)
  - Fluent but wrong (a confident Apply on an invisible-rejection role)
```

**What to do with your findings:**
- If the output passes all checks: apply. (It will not — fit is rescuing a ~0.05 sponsor.)
- If it fails one check: recompute with the sponsorship term surfaced and re-decide.
- If it fails multiple checks or you cannot determine pass/fail: this is a "When NOT to Use AI" moment — distrust the recommendation before your confusion, and trace every term yourself.

**AI Use Disclosure prompt:**
After completing this validation, write a two-sentence AI Use Disclosure:
> *Sentence 1:* What AI produced in this exercise and how you used it.
> *Sentence 2:* One specific thing the AI could not determine that required your judgment.

**Series connection:** This exercise trains **Tier 4 metacognitive supervision** — the auditability reflex that distinguishes a finding from a well-formatted guess. A composite you can't trace is exactly the fluent artifact the whole book teaches you to distrust.

[^weights]: Composite form and weights (sponsorship ×0.35, fit ×0.30, liveness and timeline as multipliers, decision threshold ≈0.3) from the system design document (Component 3, Bayesian Role Scorer). **[verify]** — confirm the exact composite expression and per-tier thresholds before publication.

[^eightfold]: Eightfold AI's match score learning manager bias, and *Kistler v. Eightfold* (FCRA: disclose the score, allow disputes, fix the audit), from "The Eightfold AI Match Score" (N. Bear Brown). **[verify]** the litigation specifics before publication.

## Prompts

### Figure 11.1 — The composite: votes, gates, and threshold
**Files:** ../images/11-the-bayesian-role-scorer-fig-01.svg
**Prompt:** Brutalist systems diagram on a white canvas: two weighted votes (a heavy sponsorship connector and a lighter fit connector in ink) merging at a summing junction, then passing through two inline gate valves — liveness and timeline — that can collapse the flow to zero, ending at a red threshold node that branches into Apply, Consider, Skip. One red accent, ink structure, JetBrains Mono labels, single-headed arrows, no shadows or gradients.

### Figure 11.2 — Same candidate, same fit: sponsorship decides
**Files:** ../images/11-the-bayesian-role-scorer-fig-02.svg
**Prompt:** Brutalist comparison panel: two parallel four-segment stacks (sponsorship, fit, liveness, timeline) for one identical candidate, the sponsorship segment dominant on the left and near-absent on the right while the fit segment is visibly identical. Two composite bars below on a shared zero baseline cross one horizontal threshold line — left clears to Apply (red), right falls to Skip (ink). White canvas, EB Garamond labels, no decoration.

### Figure 11.3 — Apply / Consider / Skip decision regions
**Files:** ../images/11-the-bayesian-role-scorer-fig-03.svg · ../d3/11-the-bayesian-role-scorer-fig-03.html
**Prompt:** Brutalist two-axis decision map: sponsorship probability (x) against fit score (y), the plane partitioned into Apply (top-right, red), Consider (mixed corners), and Skip (bottom-left, fill gray). Plot two points at identical fit but different sponsorship landing in Apply and Skip, joined by an ochre equal-fit guide line. One red accent, ink axes, JetBrains Mono ticks, white canvas.

### Figure 11.4 — Auditable vs. opaque scorer
**Files:** ../images/11-the-bayesian-role-scorer-fig-04.svg
**Prompt:** Brutalist two-column contrast on white: the left column traces each stated weight by a line back to a named source and on to a recommendation; the right column seals the weights inside a shaded box trained on a stack of past decisions, with no provenance lines out. Red for the traceable side, muted ink for the opaque interior, single-headed arrows, no shadows or gradients.
# Chapter 12 — The OPT Framing Generator

<!-- voice-anchored: root style/VOICE.md. Anatomy: TIKTOC Part 10.
     Sourced from SDD Component 4, plain-summary, CHAPTER-RESEARCH-MAP. Ethics-sensitive (TIKTOC Risk 3).
     Draft. Never published. Hard rule: never misrepresent authorization. -->

Here is what happens in the first screen. A recruiter sees "international student" and a set of associations fires before a single question gets asked: sponsorship, cost, legal risk, delay. The candidate is filtered out. Not for their ability. Not for anything true. Because in the OPT and STEM-OPT window, none of those associations are accurate. The candidate is already authorized to work in the United States. They need no immediate sponsorship. They actually save the employer money. The candidate lost the role not to a competitor but to a misunderstanding they did nothing to correct — and in many cases didn't know they could.

This is a framing problem, and it has a solution. The solution is not to obscure your status. It is to present the accurate facts in the order and language that gives the person reading them the best chance of understanding what is actually true. What is actually true happens to be good news for the employer. Most candidates never say it.

---

Start with the fact most candidates can state but almost none deploy. Students on F-1 status working under OPT are generally exempt from FICA taxes — Social Security and Medicare — for the duration of the OPT period. The employer is also exempt from the matching contribution, which runs to roughly seven and a half percent of wages.[^fica] Hiring an OPT candidate is, for that window, cheaper than hiring an equivalent domestic worker. Not more expensive. Cheaper. The assumption in the first screen is not just wrong — it is backwards. And the candidate who says this clearly, in a first written contact, has changed the entire frame of the conversation.

That is the core fact. Everything else in this chapter is about when and how to say it.

![The cost inversion shown as two cost bars on a shared zero baseline: hiring an equivalent domestic worker versus hiring an OPT candidate. The OPT bar is shorter by the employer's exempted FICA match — roughly seven and a half percent of wages — turning the assumed cost penalty into a saving.](images/12-the-opt-framing-generator-fig-03.png)
*Figure 12.3 — The FICA cost inversion*

---

The answer depends on who is reading it, which is why the chapter rests on the sponsorship tier from Chapter 7. A company that has sponsored dozens of H-1B visas understands OPT. A company with no sponsorship history may not know the acronym exists. Calibrating what you say to the audience's existing knowledge is not evasion — it is competent communication. The same true information can land as reassuring or confusing depending on the vocabulary you use to deliver it.

The tier ladder works as follows.

For a **Proven** employer — one that sponsors and knows the terrain — state your authorization directly. They understand OPT, they know the H-1B timeline, and clarity is an asset. Write it plainly: authorized to work in the U.S. on STEM OPT, familiar with the path forward. No softening needed. Softening would actually signal that you're uncertain about your own status.

For a **Likely** employer — some sponsorship history, but possibly not fluent in the details — lead with work authorization and the FICA benefit without leading with the acronym. The sentence that works is something like: "I'm authorized to work in the U.S. and, as an OPT employee, I'm FICA-exempt — a roughly seven-and-a-half-percent payroll saving for the coming period." Authorization first, benefit second, acronym explained rather than assumed. This defuses the opening-screen assumption before it can form.

For an **Unknown** employer — no signal either way — the written application says nothing about visa status. This is not concealment; it is timing. The first screen is the wrong place to raise a topic the employer may misread without context. Your materials sell your fit. When authorization comes up in an interview — and it will — you explain OPT, the FICA exemption, and the timeline in a conversation where you can answer questions as they arise and correct misreadings in real time. Paper cannot do that. You can.

The logic underlying the ladder is one idea: **disclose in proportion to the audience's understanding.** Where they understand OPT, be direct. Where they half-understand, lead with the benefit. Where they don't understand and have given no signal, let it surface in conversation. What never changes across the ladder is the hard rule: framing is accurate information presented strategically. It is never fabricated credentials, invented metrics, or misrepresented status. The moment a framing requires you to state something untrue, or to deny your authorization when directly asked, the tool has failed and you stop.

The line between strategy and misrepresentation is not subtle once you look at it directly. "Authorized to work in the U.S." is true and leads with the relevant fact. "I don't anticipate any issues with work authorization" is fine if you believe it. "I'm a permanent resident" is fraud if you aren't. The tool lives entirely on one side of that line. It has no use on the other side, and it will not help you cross it.

![A bright vertical line splits the field in two. On the left, the strategy side, sit true statements ordered for effect — "authorized to work," "FICA-exempt." On the right, the misrepresentation side, sit fabrications — "permanent resident," "no sponsorship ever needed." The line is hard, not a gradient: a statement is on one side or the other.](images/12-the-opt-framing-generator-fig-02.png)
*Figure 12.2 — The bright line: strategy vs. misrepresentation*

---

The table below summarizes the rules in compact form:

| Tier | Visa mention in written materials? | Lead with | Hard rule |
|---|---|---|---|
| Proven | Yes, direct | "Authorized; I/we know the OPT→H-1B path" | Never overstate the timeline you can offer |
| Likely | Yes, framed | "Authorized to work + FICA-exempt (~7.65% saving)" | Never imply you need no future sponsorship if you will |
| Unknown | No (initial) | Your fit; visa handled in interview | Never conceal authorization if directly asked |
| Avoid | — | (no materials) | — |

The hard rule cuts symmetrically. You do not over-claim — no implying permanent authorization you don't have, no stretching the OPT clock beyond its actual dates. And you do not deny or hide when directly asked. Strategic timing of true information is the entire toolkit. A false impression is not a variant of the toolkit. It is a different thing entirely.

![A three-rung ladder keyed to sponsorship tier. The Proven rung discloses authorization directly; the Likely rung leads with the FICA benefit and explains the acronym; the Unknown rung keeps visa status out of written materials and defers it to the interview. Disclosure increases in proportion to the audience's understanding.](images/12-the-opt-framing-generator-fig-01.png)
*Figure 12.1 — Disclosure-by-tier ladder*

---

What the generator cannot do is also worth stating plainly. It knows the sponsorship tier and the general OPT facts. It cannot know that the specific recruiter you're writing to was themselves an international student and will respond best to total directness regardless of tier. It cannot know that an Unknown-tier company was burned by a visa timeline problem last year and will ask about work authorization in the first email no matter what your materials say. It cannot make the ethical call for you in the gray moment when a framing that is technically accurate might leave a false impression in a careful reader's mind.

Framing is a starting calibration. The actual human across the table — and your willingness to hold the honesty line when it would be easy not to — is irreducibly yours to manage. The generator gets you to the conversation. What you do in it is not automatable.

This chapter also requires a legal and ethics reviewer before publication. The disclosure rules here touch employment and immigration law, and the hard rule against misrepresentation is not negotiable regardless of any framing suggestion the generator produces.[^ethics]

## Chapter 12 Exercises: The OPT Framing Generator

**Project:** Your Own Reallocation Engine

**This chapter adds:** tier-calibrated work-authorization framing for your applications — direct for Proven, benefit-led for Likely, interview-deferred for Unknown — governed by one non-negotiable rule: framing is true information presented strategically, never misrepresentation.

---

### Exercise 1 — When to Use AI

**The judgment:** In this chapter's work, AI assistance is appropriate for the following tasks:

- **Drafting tier-calibrated framing language for a given role.** — *Why AI works here:* it's drafting against facts you supply and a rule you enforce; you check every claim for truth before it ships.
- **Explaining the FICA exemption to a non-expert in one plain sentence.** — *Why AI works here:* it's translating a known, true benefit into lay language you can verify.
- **Rewriting an over-jargoned framing into the right register for the audience.** — *Why AI works here:* reformatting for clarity, judged against your knowledge of the reader.

**The tell:** You know you are using AI appropriately when you can evaluate the output — when you have independent criteria to judge whether it is correct, complete, and fit for purpose. Here the criterion is: is every sentence true, and would it leave a careful reader with an accurate impression?

---

### Exercise 2 — When NOT to Use AI

**The judgment:** In this chapter's work, the following tasks require human judgment. Delegating them to AI is not appropriate — not because AI cannot produce output, but because AI output in these cases cannot be trusted without verification that requires the same expertise as doing the task yourself.

- **Making the ethical call in a gray case.** — *Why AI fails here:* whether a technically-accurate framing might leave a false impression is a values judgment the model cannot make for you — and the model will often optimize persuasiveness past the honesty line if you let it.
- **Ruling on what is legally accurate about your status.** — *Why AI fails here:* employment and immigration law govern these claims; a model's confident phrasing is not legal accuracy, and this chapter explicitly requires a legal/ethics reviewer.
- **Deciding disclosure for a specific recruiter whose context you know.** — *Why AI fails here:* the tier is a starting calibration; that this recruiter was themselves an international student, or that this company was burned last year, is private context only you hold.

**The tell:** You know you have crossed the line when you are using AI output as your reason for a conclusion rather than as a tool for reaching one. If you could not explain the conclusion without the AI, the AI did the work that should have been yours.

**Series connection:** This exercise trains **Tier 7 (Wisdom — values and accountability)**. The hard rule against misrepresentation is a values commitment no optimizer can hold for you; the model can phrase the truth strategically, but only you can refuse to cross the line when crossing it would be easy.

---

### Exercise 3 — LLM Exercise

**What you're building this chapter:** three tier-calibrated framings for your real target roles — every claim true, status never misrepresented — ready to drop into your applications.

**Tool:** Claude (claude.ai chat). You supply the tier and the role; chat drafts within the rule.

**The Prompt:**

```
Help me write work-authorization framing for job applications. I am on F-1 OPT
(or STEM OPT), authorized to work now, and FICA-exempt (a ~7.65% payroll saving
for the employer). The framing must be calibrated by the company's sponsorship
tier, and it must obey one HARD RULE: present only TRUE information, strategically
ordered — never fabricate credentials, never invent metrics, never misrepresent
my status, never deny authorization if asked.

Disclosure-by-tier:
- PROVEN (sponsors, knows OPT): state authorization directly, plainly.
- LIKELY (some history, may not know details): lead with "authorized to work" +
  the FICA benefit, explain rather than assume the acronym.
- UNKNOWN (no signal): written materials say nothing about visa; sell fit; visa
  is handled in the interview.

For each role I paste (with its tier):
1. Draft the framing in the right register for its tier.
2. After each, list every factual claim it makes and mark it "verified true / I
   must confirm / FALSE — remove."
3. Flag any sentence that is technically true but could leave a false impression,
   and offer an honest rewrite.

Do not write "permanent resident," "no sponsorship needed ever" (unless true for
me), or any status I don't hold.

--- PASTE ROLES + TIERS BELOW ---
[paste here]
```

**What this produces:** three tier-matched framings with a per-claim truth audit and false-impression flags — the application language for your Apply-tier roles.

**How to adapt this prompt:**
- *For your own project:* paste your real tiers (from Chapter 7) and confirm your own FICA/OPT facts with an authoritative source before using any framing.
- *For ChatGPT / Gemini:* works as-is; both will over-optimize persuasiveness — keep the hard rule and the per-claim truth audit.
- *For a Claude Project:* store the hard rule and the disclosure-by-tier ladder in the instructions so every draft inherits them.

**Connection to previous chapters:** the tier comes from Chapter 7; the "label every claim" discipline is Chapter 3's data-claim/judgment rule applied to your own self-presentation.

**Preview of next chapter:** Chapter 13 ensures the résumé carrying this framing actually survives the ATS parser before any human reads it.

---

### Exercise 4 — CLI Exercise

**What you're building this chapter:** per-application framing recorded alongside an honesty attestation, so every application in your engine carries a one-line confirmation that no claim was overstated.

**Tool:** Cowork (or Claude Code). Generating framings across your tiered targets and logging attestations is a file workflow.

**Skill level:** Beginner–Intermediate.

**Setup:**

Before running this exercise, confirm:
- [ ] Your targets carry a sponsorship tier (Chapter 7).
- [ ] You have confirmed your own OPT/FICA facts from an authoritative source.
- [ ] You understand the hard rule is yours to enforce, not the tool's.

**The Task:**

```
For each Apply/Consider-tier target, generate work-authorization framing matched
to its sponsorship tier and record it with an honesty attestation. Do not
fabricate any claim or assert any status I have not given you.

1. Read my targets and their tiers.
2. For each, write the tier-appropriate framing (Proven=direct, Likely=benefit-
   led, Unknown=interview-deferred / nothing in writing).
3. Save reports/framing.md: per role — company, tier, framing text, and a
   one-line attestation: "Every claim verified true; status not misrepresented."
   Leave the attestation BLANK for me to sign off — do not self-certify.
4. Flag any framing you generated that you are unsure passes the hard rule, in a
   separate "needs my review" list.
5. Show me framing.md. Stop.
```

**Expected output:** `reports/framing.md` with tier-matched framings and an unsigned honesty attestation per role, plus a "needs review" flag list.

**What to inspect in the output:** read every framing for a false impression, not just a false statement — the line is subtle and it's yours. Confirm no Unknown-tier framing put visa status in the written materials. Sign the attestation only for framings you've verified yourself.

**If it goes wrong:** the failure to watch for is a framing that's persuasive because it's misleading — e.g. implying no future sponsorship will ever be needed. Recover by rewriting to be both honest and effective; if it can't be both, ship the honest version.

**CLAUDE.md / AGENTS.md note:** add a standing rule — *"Framing presents only true information; the engine never asserts immigration status, never self-certifies honesty (the human signs the attestation), and routes legal-accuracy questions to a DSO/attorney."* This is a hard, non-negotiable rule.

---

### Exercise 5 — AI Validation Exercise

**What you're validating:** a framing that crossed from strategic into misrepresentation — persuasive, fluent, and false.

**Validation type:** Factual claim (with an ethics component).

**Risk level:** High — a misrepresentation of work-authorization status is fraud, with consequences far beyond a lost role.

**Setup (pre-generated artifact — option b):** This chapter's lesson is the line between framing and misrepresentation, so validate this pre-generated framing:

> **Cover-letter line (AI-generated for an Unknown-tier company):** "As a U.S.
> work-authorized professional, I require no visa sponsorship and have permanent
> authorization to work in the United States — so there's no immigration paperwork
> or cost on your end. I'm fully cleared to start immediately and indefinitely."

**The Validation Task:**

Evaluate the AI output above using the following checklist. For each item, record: Pass / Fail / Cannot determine — and explain your reasoning.

```
Validation Checklist — The OPT Framing Generator

□ Correctness: Is every claim TRUE for someone on time-limited F-1 OPT?
  ("permanent authorization," "indefinitely")
□ Completeness: Does it disclose that OPT is time-limited and that future
  sponsorship may be needed — or does it imply the opposite?
□ Scope: For an UNKNOWN-tier company, should visa status even be in the written
  materials at all?
□ Hard-rule check (chapter-specific): Identify the exact phrase(s) that cross
  from strategic framing into misrepresentation.
□ False-impression check (chapter-specific): Even where a phrase is arguably
  parseable as true, would a careful reader come away believing something false?
□ Failure mode check: Does this output exhibit any of the following?
  - Misrepresented status ("permanent authorization") — the bright-line violation
  - Implying no future sponsorship when it may be required
  - Fluent but false (a persuasive line that is not true)
```

**What to do with your findings:**
- If the output passes all checks: use it. (It will not — "permanent authorization" and "indefinitely" are false for OPT.)
- If it fails one check: rewrite to be both honest and effective; if it can't be both, ship the honest version.
- If it fails multiple checks or you cannot determine pass/fail: this is a "When NOT to Use AI" moment — write the framing yourself and have a DSO/attorney review anything touching legal accuracy.

**AI Use Disclosure prompt:**
After completing this validation, write a two-sentence AI Use Disclosure:
> *Sentence 1:* What AI produced in this exercise and how you used it.
> *Sentence 2:* One specific thing the AI could not determine that required your judgment.

**Series connection:** This exercise trains **Tier 7 wisdom and accountability** — holding the honesty line when a fluent model offers an effective lie. The tool optimizes persuasion; only you are accountable for the truth.

---

## Key terms

- **Framing:** presenting accurate information strategically, calibrated to the audience's understanding — never fabrication.
- **FICA exemption:** OPT employees are generally exempt from Social Security and Medicare tax, saving the employer roughly seven and a half percent for the period — a real hiring benefit.
- **Disclosure-by-tier:** direct for Proven, benefit-led for Likely, interview-deferred for Unknown.
- **The hard rule:** never fabricate credentials, invent metrics, or misrepresent status; never deny authorization when asked.

## Run-log prompt

Record, per application, the tier, the framing approach used, and a one-line confirmation that every claim is accurate and no status was misrepresented.

[^fica]: F-1/OPT students are generally exempt from FICA (Social Security and Medicare) taxes, removing the employer's matching ~7.65% for the OPT period. Stated across the project's plain-summary and résumé/3-3-2 essays. **[verify]** against IRS guidance (e.g., IRS Publication 519 / FICA exemption for F-1) before publication.

[^ethics]: This chapter requires a legal/ethics review owner before publication (TIKTOC Risk 3 / Open Question 6). The hard rule against misrepresentation is non-negotiable and overrides any framing suggestion.

## Prompts

### Figure 12.1 — Disclosure-by-tier ladder
**Files:** ../images/12-the-opt-framing-generator-fig-01.svg
**Prompt:** Brutalist three-rung ladder on a white canvas, one rung per sponsorship tier: Proven (disclose directly), Likely (lead with the FICA benefit, explain the acronym), Unknown (nothing in writing, defer to interview). Disclosure rises with the rung. Ink structure, one red accent on the active rung, EB Garamond labels, no shadows or gradients.

### Figure 12.2 — The bright line: strategy vs. misrepresentation
**Files:** ../images/12-the-opt-framing-generator-fig-02.svg
**Prompt:** Brutalist conceptual map split by one hard vertical red line: the strategy side holds true statements ordered for effect; the misrepresentation side holds fabrications. Render it as a binary boundary, not a gradient. White canvas, ink text, JetBrains Mono for the example phrases, no decoration.

### Figure 12.3 — The FICA cost inversion
**Files:** ../images/12-the-opt-framing-generator-fig-03.svg
**Prompt:** Brutalist two-bar comparison on a shared zero baseline: cost of an equivalent domestic hire versus an OPT hire, the OPT bar shorter by the exempted employer FICA match (~7.5% of wages). One red accent on the saving, ink axes, JetBrains Mono tick labels, white canvas, no gradients.
# Chapter 13 — Resumes That Survive the Filter
*The first reader doesn't care how it looks.*

There is a particular kind of effort that feels productive but costs you exactly what you spent it on. A candidate spends a weekend on a résumé. Two columns, a sidebar with tasteful skill bars, a small icon next to each section header, the name set large in a header graphic. It is the best-looking document they have ever made. They submit it to forty companies. Most reject it before a human opens it — not because the content was weak, but because the applicant-tracking system that read it first saw a scrambled wall of text. The two columns interleaved into nonsense. The skill bars, rendered as graphics, produced no text at all. The name, trapped in an image, was simply absent. The parser could not find a job title. So it scored the candidate as unqualified for everything, and the beautiful résumé disappeared.

This is not a corner case. By 2025, roughly 82% of companies screened résumés with software, and about one in five candidates were auto-rejected with no human review.[^screening] The first reader of your résumé is a parser. The parser does not care that the document is beautiful. It cares whether it can extract structured text. A résumé a human would admire and a machine cannot read is a résumé no human will ever see.

![Two parallel paths from "Submit résumé." The ATS-parseable path: the parser extracts name, title, and dates cleanly, leading to human review and an interview. The designed-layout path: the parser sees scrambled text, the application is auto-rejected, and no human ever opens it. The fork happens before any human judgment.](images/13-resumes-that-survive-the-filter-fig-01.png)
*Figure 13.1 — The fork before the human*

<!-- → [DIAGRAM: two parallel paths from "Submit résumé" — left path labeled "ATS-parseable": document → parser extracts name/title/dates cleanly → human review → interview; right path labeled "Designed layout": document → parser sees scrambled text or nothing → auto-reject → no human ever opens it; the fork happens before any human judgment] -->

I want to be precise about what this means, because the instinct is to fight it. "A distinctive design will make me stand out." Against a human, sometimes — if the human ever gets there. Against the parser that reads first, a distinctive design is how you disappear. Standing out is the job of your content and your portfolio. The résumé's job is narrower and absolute: pass the parser, then say something true and specific to the human behind it. Those are two different tasks, and conflating them is what produces the beautiful invisible résumé.

---

The pipeline this chapter rests on is `scripts/resumes/`, whose core is `generate-pdf.mjs`: a script that takes a Markdown CV and renders it to a PDF through Playwright/Chromium using a resume-safe rendering path — single-column, real text, standard section headings, no layout the parser will trip on. The whole point is that you author content in plain Markdown and let the pipeline produce a document engineered to parse. You do not hand-build a layout that looks good and reads as garbage. You write text, and the pipeline handles the document.

From the project root:

```bash
npm run resumes:pdf      # runs scripts/resumes/generate-pdf.mjs
```

The output is a rendered PDF. But the real check is not "does it look right." It is "does it parse." So there is a second, essential step: copy all text from the PDF — Ctrl/Cmd-A, Ctrl/Cmd-C — and paste it into a plain text editor. What you see pasted is roughly what the parser sees. If your name, titles, and dates come through as clean linear text in the right order, the document passes. If they scramble or vanish, you have found the break before a company did.

| What you designed | What the parser extracted |
|---|---|
| Two-column layout | Lines interleaved across columns — incoherent order |
| Skill bars as graphics | Blank — no text at all |
| Name in a header image | Absent — the parser never learns your name |
| Dates in a table cell | Misaligned — drifted away from their roles |
| Section icons instead of words | Nothing — no section structure detected |

*The left column is the document you admired; the right column is the only version the first reader ever sees.*

That paste test is a practitioner heuristic, not a certificate. ATS systems vary. What one parses cleanly another may struggle with. But if text scrambles or disappears in plain paste, it will scramble or disappear in some meaningful fraction of the systems reading your application. The heuristic is conservative in the right direction: it tells you where the floor is, and the floor is what you need to be above.

---

Let me walk through what the test actually reveals, using a single CV rendered two ways.

The Markdown version, run through `resumes:pdf`: the PDF looks clean. Run the paste test. Name, contact information, each role's title and dates, the bullet content — all come through as ordered linear text. Section headings ("Experience," "Education," "Skills") survive as plain words, which are exactly the words parsers key on. The test passes.

The same content in a two-column designed template: paste it out. The left and right columns interleave line by line. "Data Analyst, 2023–2024" lands in the middle of an unrelated bullet from the other column. The skills section, rendered as little bars with labels, produces nothing — no text extracted at all. The parser reading that document cannot reliably locate a single job title. It has a name problem, a date problem, and a skill problem, all at once, and the human who might have found the candidate compelling never gets the chance to try.

![Side-by-side paste-test output for the same CV rendered two ways. Left: clean linear text with name, title, dates, and bullets in order. Right: scrambled, interleaved text with sections that produced no text marked in red. The right side is what a typical two-column designed template actually produces when parsed.](images/13-resumes-that-survive-the-filter-fig-02.png)
*Figure 13.2 — What you designed vs. what the parser extracted*

<!-- → [CHART: side-by-side paste-test output for the same CV rendered two ways — left: clean linear text with name, title, dates, bullets in order; right: scrambled interleaving with missing sections marked in red; caption should note that the right-side output is what a typical two-column designed template actually produces when parsed] -->

The decision that follows from this is simple to state and genuinely uncomfortable to execute: ship the single-column rendered version; keep the pretty one for nothing, or for a human-only context like a portfolio site. The discomfort is real. The designed version *is* better-looking. But it is better-looking for a reader it will never reach.

---

Now let me say what the structures are that break parsers, because "don't use a fancy layout" is advice without traction until you know exactly which choices cause the problem.

**Multi-column layouts** are the most common failure mode. A parser reads text in document order, which in a two-column PDF is typically left-to-right across the full page width, not column by column. So the left column's first line and the right column's first line appear interleaved. This is not a subtle degradation — it makes the extracted text incoherent.

**Text in images** is the second. A name set in a header graphic is invisible to the parser. Literally absent. The parser cannot do OCR; it reads embedded text. If your name is an image, the parser does not know your name. If your section headers are icons rather than text characters, the parser does not see section structure.

**Tables used for layout** create extraction problems similar to columns: the parser linearizes the cells in ways that depend on the table's internal structure, not the visual arrangement you intended. Dates and job titles drift into wrong positions. A table is appropriate for genuinely tabular data; it is destructive when used to control visual layout.

**Skill bars and graphic elements** produce no text at all. They exist visually. To the parser, they are a gap.

The safe structures are their opposites: a single-column flow, real text characters for every piece of content that needs to be extracted, standard headings as plain words, dates in a consistent parseable format next to the roles they describe. These are not design constraints that prevent a good résumé. They are the constraints that ensure the résumé is read.

![A quick-reference visual contrasting résumé safe zones and danger zones. Safe: single-column body text, standard section headers as text, dates as plain text adjacent to roles, skills as a plain-text list, real text characters throughout. Danger: two-column layout, header graphic, skill bars, table-based layout, any text inside an image.](images/13-resumes-that-survive-the-filter-fig-03.png)
*Figure 13.3 — Résumé safe zones and danger zones*

<!-- → [INFOGRAPHIC: a labeled résumé showing "safe zones" and "danger zones" — safe: single-column body text, standard section headers as text, dates as plain text adjacent to roles; danger: two-column layout, header graphic, skill bars, table-based layout, any text in an image; designed as a quick-reference visual a student can check their own document against] -->

---

There is something the pipeline cannot do, and I want to be direct about it.

The pipeline can guarantee a parseable document. It cannot know which of your true accomplishments will land with this hiring manager. It cannot tell you that your most parser-friendly bullet is also your most forgettable one. It cannot identify the phrase in your summary that makes a reader lean forward. ATS-safety is a floor — it ensures the human gets to read you at all. What you say once you are through the gate, and whether it is specific and true enough to earn the interview, is judgment the parser was never measuring.

The résumé, in a market where roughly 82% of companies run applications through software first, is not where you win. It is a gate you must not lose at. The winning moves — portfolio, proof of capability, demonstrated skill — happen elsewhere. The résumé's job is to get through the first filter intact and give the human on the other side something true and specific to respond to. Those are two requirements, and they are both necessary. An ATS-safe PDF with weak content still fails the human.

![A two-stage model of the résumé's job. Stage 1, the ATS filter, asks: can the parser find your name, title, and dates? Stage 2, human review, asks: is the content specific and true enough to earn a call? An arrow between them notes that what survives Stage 1 is the floor; Stage 2 is where content quality decides.](images/13-resumes-that-survive-the-filter-fig-04.png)
*Figure 13.4 — Two-stage résumé job: parse floor, then human*

<!-- → [DIAGRAM: a two-stage model showing the résumé's job — Stage 1: "ATS filter" with the criterion "Can the parser find your name, title, and dates?" — Stage 2: "Human review" with the criterion "Is the content specific and true enough to earn a call?" — with an arrow between them labeled "What survives Stage 1 is the floor; Stage 2 is where content quality decides"] -->

Every component in the engine now works on its own: funding, sponsorship, liveness, role quality, timeline, scoring, framing, and a résumé that survives the filter. The next act stops handing you clean single tasks. It runs the whole engine — under real pressure, with a log — and that changes what you are doing in a way a single chapter cannot fully prepare you for.

---

## Chapter 13 Exercises: Résumés That Survive the Filter

**Project:** Your Own Reallocation Engine

**This chapter adds:** the artifact you actually send — an ATS-safe résumé rendered from Markdown and proven against the paste test, so the first reader (a parser) can extract your name, titles, and dates before any human ever sees them.

---

### Exercise 1 — When to Use AI

**The judgment:** In this chapter's work, AI assistance is appropriate for the following tasks:

- **Tightening bullet content in Markdown to be specific and true.** — *Why AI works here:* drafting against your real accomplishments, which you verify line by line.
- **Reformatting a visual skills grid into parseable linear text.** — *Why AI works here:* a structure transformation you confirm with the paste test.
- **Summarizing what the paste-test output reveals (what scrambled, what vanished).** — *Why AI works here:* it reads the extracted text you supply; you check against the source.

**The tell:** You know you are using AI appropriately when you can evaluate the output — when you have independent criteria to judge whether it is correct, complete, and fit for purpose. Here the criteria are the paste test (does it parse?) and your own record (is it true?).

---

### Exercise 2 — When NOT to Use AI

**The judgment:** In this chapter's work, the following tasks require human judgment. Delegating them to AI is not appropriate — not because AI cannot produce output, but because AI output in these cases cannot be trusted without verification that requires the same expertise as doing the task yourself.

- **Inventing or inflating accomplishments to strengthen a bullet.** — *Why AI fails here:* a model asked to "make this more impressive" will fabricate metrics; that crosses the same hard honesty line as Chapter 12, and only you know what's true.
- **Judging whether a bullet will land with this hiring manager.** — *Why AI fails here:* content quality past the parser is a judgment about a specific human; the model optimizes for plausible, not for resonant-and-true.
- **Certifying ATS-safety from how the PDF looks.** — *Why AI fails here:* the model can't see the parser; only the paste test reveals what gets extracted.

**The tell:** You know you have crossed the line when you are using AI output as your reason for a conclusion rather than as a tool for reaching one. If you could not explain the conclusion without the AI, the AI did the work that should have been yours.

**Series connection:** This exercise trains **Tier 4 (Metacognitive supervision)** with a **Tier 7** honesty edge — verifying a claim (does it parse?) against the world rather than against the document's appearance, and refusing to let "more impressive" become "not true."

---

### Exercise 3 — LLM Exercise

**What you're building this chapter:** a tightened, ATS-safe Markdown CV — specific and true bullets, parseable structure, the skills grid converted to linear text — ready to render.

**Tool:** Claude (claude.ai chat). You paste your Markdown CV; chat helps tighten and flag.

**The Prompt:**

```
Help me improve my résumé content and ATS-safety. I will paste my CV in Markdown.
HARD RULE: do not invent, inflate, or estimate any accomplishment or metric — work
only with what I give you. If a bullet is weak, make it more specific using ONLY
facts I provide, or tell me what fact you'd need from me.

1. Tighten each bullet to be specific and concrete, keeping every claim true. Mark
   any place where you'd need a real number from me with [ASK ME], do not fill it
   in.
2. Flag any layout element that will break an ATS parser: multi-column structure,
   text in images, tables used for layout, skill bars/graphics, non-text section
   headers. For each, give the parseable replacement.
3. Convert any visual skills grid into a single-column, plain-text list that
   preserves every skill.
4. Output the revised CV as clean single-column Markdown suitable for rendering to
   a single-column PDF.

Do not add a metric I didn't give you, and do not change my titles, employers, or
dates.

--- PASTE YOUR MARKDOWN CV BELOW ---
[paste here]
```

**What this produces:** a parser-safe Markdown CV with tightened, truthful bullets and `[ASK ME]` placeholders wherever a real number is needed — never a fabricated one.

**How to adapt this prompt:**
- *For your own project:* fill every `[ASK ME]` with a real, verifiable number. An invented metric here is the Chapter 12 hard-rule violation in résumé form.
- *For ChatGPT / Gemini:* works as-is; both love to invent quantified achievements — keep the "do not invent any metric" rule prominent.
- *For a Claude Project:* store the no-fabrication rule and the ATS-safe structure list in the instructions.

**Connection to previous chapters:** the honesty rule is Chapter 12's hard rule applied to your résumé; ATS-safety is the floor that lets your Chapter 11 Apply decisions actually reach a human.

**Preview of next chapter:** Chapter 14 runs the whole engine as a loop — scan, score, evaluate, log — with the résumé renderer as one of its recipes.

---

### Exercise 4 — CLI Exercise

**What you're building this chapter:** a rendered ATS-safe PDF plus an automated paste test that confirms your name, titles, and dates extract as clean linear text.

**Tool:** Claude Code. Rendering via `resumes:pdf`, extracting text, and checking linearity is a code-plus-inspection workflow.

**Skill level:** Intermediate.

**Setup:**

Before running this exercise, confirm:
- [ ] `scripts/resumes/generate-pdf.mjs` and `npm run resumes:pdf` work (Playwright/Chromium available).
- [ ] You have your ATS-safe Markdown CV from Exercise 3.
- [ ] You know what a passing paste test looks like (clean ordered text).

**The Task:**

```
Render my Markdown CV to an ATS-safe PDF and verify it parses. Do not alter my
content; do not invent anything.

1. Run:  npm run resumes:pdf
   Confirm the PDF was written and report the path.
2. Programmatically extract the text from the rendered PDF (the parser's view) and
   print it as plain linear text.
3. Check and report: do my NAME, each JOB TITLE, and each DATE appear, in order,
   as clean text? Flag anything scrambled, interleaved, or missing.
4. Compare the extracted text against my source Markdown headings (Experience,
   Education, Skills) — confirm each survives as a plain word.
5. Save reports/paste-test.txt (the extracted text) and a short PASS/FAIL summary
   per checked field. Stop.
```

**Expected output:** the rendered PDF, `reports/paste-test.txt` with the parser's view, and a per-field PASS/FAIL summary for name, titles, dates, and headings.

**What to inspect in the output:** read the extracted text yourself — does your name appear exactly once as text (not missing, not from an image)? Are titles adjacent to their dates, not interleaved? A clean automated pass is still a heuristic; eyeball the worst-case fields.

**If it goes wrong:** the classic failure is a field missing because it was in a graphic, or titles/dates interleaved from a multi-column source. Recover by fixing the Markdown structure (single column, real text headings) and re-rendering; never ship a PDF whose paste test you haven't read.

**CLAUDE.md / AGENTS.md note:** add a standing rule — *"Résumés render from Markdown to single-column PDF and must pass an extracted-text paste test (name, titles, dates linear) before sending; résumé content never includes a metric not verifiable from my records."* This pins both the parse floor and the honesty rule.

---

### Exercise 5 — AI Validation Exercise

**What you're validating:** an AI-"improved" résumé that both fabricated metrics and used a parser-hostile layout — impressive, unparseable, and untrue.

**Validation type:** Structured data + factual claim.

**Risk level:** High — fabricated metrics are dishonest (Chapter 12's hard rule), and the layout means no human sees it anyway.

**Setup (pre-generated artifact — option b):** This chapter's lessons are the parse floor and the honesty line, so validate this pre-generated "improved" résumé excerpt:

> **AI-revised résumé (for "Data Analyst" applicant who gave no metrics):**
> Rendered as a polished two-column PDF with the name in a header banner graphic
> and a skills sidebar shown as labeled proficiency bars.
> Bullets now read:
> • "Drove a 42% increase in revenue through advanced analytics."
> • "Reduced reporting time by 75% and saved the company $1.2M annually."
> • "Led a team of 12 analysts across 3 continents."
> *(The applicant's actual experience: one internship; no revenue, headcount, or
> savings figures were ever provided to the model.)*

**The Validation Task:**

Evaluate the AI output above using the following checklist. For each item, record: Pass / Fail / Cannot determine — and explain your reasoning.

```
Validation Checklist — Résumés That Survive the Filter

□ Correctness (honesty): Are the metrics (42%, 75%, $1.2M, team of 12) grounded
  in facts the applicant provided, or fabricated?
□ Correctness (parse): Will a two-column layout, a name-in-graphic, and skill
  bars survive an ATS parser? What does the paste test predict?
□ Completeness: Does anything verify these numbers against the applicant's real
  record (one internship)?
□ Honesty-line check (chapter-specific): Which bullets cross the same hard line as
  Chapter 12 (no invented metrics)?
□ Parse-floor check (chapter-specific): Run the paste test mentally — what
  extracts cleanly, what scrambles, what vanishes?
□ Failure mode check: Does this output exhibit any of the following?
  - Fabricated metrics (dishonesty)
  - Parser-hostile layout (the beautiful invisible résumé)
  - Fluent but wrong (impressive, unparseable, and untrue at once)
```

**What to do with your findings:**
- If the output passes all checks: use it. (It will not — every metric is invented and the layout won't parse.)
- If it fails one check: strip fabricated metrics and re-render single-column from Markdown.
- If it fails multiple checks or you cannot determine pass/fail: this is a "When NOT to Use AI" moment — write true bullets yourself and let the pipeline handle only the rendering.

**AI Use Disclosure prompt:**
After completing this validation, write a two-sentence AI Use Disclosure:
> *Sentence 1:* What AI produced in this exercise and how you used it.
> *Sentence 2:* One specific thing the AI could not determine that required your judgment.

**Series connection:** This exercise trains **Tier 4 metacognitive supervision** joined to the series' honesty commitment — catching output that is fluent in two directions at once (it looks impressive and it would never reach a human, and it isn't even true). The pipeline guarantees a parseable document; truth and resonance are yours.

[^screening]: ~82% of companies screen résumés with AI; ~21% auto-reject without human review — "The Collapse of the Traditional Résumé" (N. Bear Brown). **[verify]** against primary source.

[^proof]: The résumé-as-gate framing and the ~56% validated-AI-skill wage premium are from "The Collapse of the Traditional Résumé." **[verify]** the wage-premium figure before publication.

## Prompts

### Figure 13.1 — The fork before the human
**Files:** ../images/13-resumes-that-survive-the-filter-fig-01.svg · ../d3/13-resumes-that-survive-the-filter-fig-01.html
**Prompt:** Brutalist process flowchart on white: "Submit résumé" forks into two paths before any human acts. The ATS-parseable path (red accent) runs parser → human review → interview; the designed-layout path (ink/gray) runs scrambled parse → auto-reject → no human opens it. Single-headed arrows, ink boxes, one ochre rule under the caption, no shadows or gradients.

### Figure 13.2 — What you designed vs. what the parser extracted
**Files:** ../images/13-resumes-that-survive-the-filter-fig-02.svg · ../d3/13-resumes-that-survive-the-filter-fig-02.html
**Prompt:** Brutalist two-panel comparison on white: the same CV pasted out two ways. Left panel shows clean linear text in JetBrains Mono (name, title, dates, bullets in order); right panel shows interleaved, scrambled text with missing fields flagged in red. Ink frame, one red accent for the failures, no decoration.

### Figure 13.3 — Résumé safe zones and danger zones
**Files:** ../images/13-resumes-that-survive-the-filter-fig-03.svg · ../d3/13-resumes-that-survive-the-filter-fig-03.html
**Prompt:** Brutalist two-column quick-reference on white: a "safe zones" list (single-column text, text headers, plain-text dates, plain-text skills) against a "danger zones" list (two-column, header graphic, skill bars, table layout, text-in-image) drawn with dashed borders. Red accent on safe, gray on danger, no gradients or shadows.

### Figure 13.4 — Two-stage résumé job: parse floor, then human
**Files:** ../images/13-resumes-that-survive-the-filter-fig-04.svg · ../d3/13-resumes-that-survive-the-filter-fig-04.html
**Prompt:** Brutalist two-stage diagram on white: Stage 1 "ATS filter" (gray fill, criterion: can the parser find name/title/dates?) with a single-headed arrow to Stage 2 "Human review" (red outline, criterion: specific and true enough to earn a call?). An ochre rule underlines the caption that Stage 1 is the floor and Stage 2 is where quality decides. No shadows or gradients.
# Chapter 14 — Recipes: Operating the Engine
*The fluent surface from Chapter 1 has come back, this time wearing the engine's own uniform.*

Here is a failure mode worth understanding before you run anything. You invoke a recipe called `oferta` to evaluate a role. It returns a confident assessment: sponsorship looks strong, fit is solid, the composite is above threshold, you should apply. The output reads exactly like the verified findings you've trusted all book — sourced factors, labeled judgments, a traceable recommendation. But under the hood, something has changed. This run never called the sponsorship pipeline. It never read an audit. It asked a language model what it thought and dressed the guess in the format of a finding. You can't tell from the output. That's the whole danger.

The difference between a recipe that *runs a script and reads an audit* and a recipe that *quietly becomes a chat prompt* is the difference between the entire method working and the entire method failing silently. This chapter is about telling them apart — not once, but every time you run the engine.

## What a recipe is

The engine's runtime lives in a directory called `recipes/`. A recipe is a named operation you invoke, and each one declares what scripts it calls, what data it reads, and what it logs. The declaration is not decorative. It is the thing you verify. A recipe that calls no scripts and reads no audits is producing model judgment, not findings — and the output format will not tell you which one you're looking at.

Every recipe opens by loading `recipes/_shared.md`, the contract from Chapter 3. The contract is supposed to make the runtime honest by construction: every output labeled, every source named, every judgment flagged. Your job is to confirm, run by run, that it actually is.

The recipes split into two groups, and understanding the split is the chapter's load-bearing insight.

**Active recipes** are the ones that do verified work. `scan` detects the ATS and pulls the company's current postings. `pipeline` runs the scoring pass — sponsorship, fit, liveness, timeline — against the pulled data. `oferta` assembles the four factors into the composite from Chapter 11 and returns a sourced Apply/Consider/Skip recommendation. `tracker` logs decisions across the search (Chapter 15). `pdf` renders the ATS-safe résumé (Chapter 13). These recipes call real scripts. They read real audits. Their outputs are findings.

**Draft and helper recipes** are scaffolds — `apply`, `contacto`, `deep`, `followup`, `interview-prep`, `ofertas`, `project`, `training`, and others. They can be useful. But until you have confirmed, on a specific run, that a given draft recipe calls scripts and writes a log, you treat its output as model judgment. Not worthless. Not a finding.

| Active recipes (call scripts, read audits) | Draft / helper recipes (verify before trusting) |
|---|---|
| `scan` — detects the ATS, pulls current postings | `apply` — verify before trusting |
| `pipeline` — scores sponsorship, fit, liveness, timeline | `contacto` — verify before trusting |
| `oferta` — assembles the composite, returns Apply/Consider/Skip | `deep` — verify before trusting |
| `tracker` — logs decisions across the search | `followup` — verify before trusting |
| `pdf` — renders the ATS-safe résumé | `interview-prep`, `ofertas`, `project`, `training` — verify before trusting |

*The split is not permanent — a draft recipe that you verify runs scripts becomes trustworthy. The taxonomy is about evidence, not hierarchy.*

The taxonomy is not a permanent ranking. A draft recipe you have verified is trustworthy for that run. An active recipe that has been edited without your knowledge might not be. The classification is always about what the recipe did on this run, not what it is named.

![Two columns of recipes. The active column — scan, pipeline, oferta, tracker, pdf — calls scripts and reads audits, producing findings. The draft and helper column — apply, contacto, deep, followup, interview-prep, ofertas, project, training — carries a "verify before trusting" label, treated as model judgment until confirmed. The split is about evidence, not hierarchy.](images/14-skills-operating-the-engine-fig-01.png)
*Figure 14.1 — Active vs. draft recipes*

## The loop

Operating the engine is one loop, repeated:

1. **Run** an active recipe against a real target.
2. **Inspect** the output *and its provenance* — did it call the script? Is there an audit? Which numbers trace to records and which are labeled judgments?
3. **Record** the run in `RUN_LOG.md` — what you ran, what it returned, what you decided.

The loop is deliberately boring, and the boredom is the safety. Each pass leaves a trace. A decision made three weeks ago can be reconstructed, questioned, and updated when new information arrives. The moment you skip the inspect step — accepting a recipe's output because it looks right, because the format is familiar, because the recommendation matches what you hoped — you've reopened the fluency trap. The surface was the danger in Chapter 1. It is still the danger in Chapter 14.

![A three-step cycle drawn as a clockwise loop: Run an active recipe, Inspect the output and its provenance, Record the run in RUN_LOG.md, then back to Run. The inspect node is annotated as the only protection — skip it and the fluency trap reopens.](images/14-skills-operating-the-engine-fig-02.png)
*Figure 14.2 — The run-inspect-record loop with provenance checkpoints*

## A full sequence, end to end

Take one role from URL to evaluation:

```bash
# 1. scan — detect the ATS and pull the company's current postings
npm run ats:scan

# 2. pipeline — score the pulled roles
#    (run via the pipeline recipe / auto-pipeline)

# 3. oferta — evaluate one role into a composite + Apply/Consider/Skip
#    (oferta recipe; returns the sourced composite from Chapter 11)

# 4. verify — confirm the pipeline's data is internally consistent
npm run ats:verify
```

Four commands. Four links in a chain. What you read is the chain — not just the final recommendation, but each link's provenance. The scan result tells you which ATS was detected and which postings were pulled. The pipeline pass shows the four scored factors with their source labels. The `oferta` composite traces each term to its origin. The verification audit confirms the underlying data is consistent. A recommendation without its provenance is just an opinion in a formatted box.

## One target, fully operated

Let me make the loop concrete. A single role URL at a Likely-tier startup.

`scan` detects Lever and pulls the current posting. The posting is nine days old, description is specific, company hiring count has changed since last week — the liveness signal from Chapter 8 is clean.

The `pipeline` pass scores the role. Sponsorship probability from the LCA and H-1B join: 0.65 — Likely tier, not Proven. Fit from CV-vs-JD comparison: 0.72 — a model judgment, labeled as such. Liveness: live. Timeline factor: 0.8, from the reader's OPT expiration and estimated processing window.

`oferta` assembles the composite. Sponsorship at Likely (0.65) carries less weight than Proven (0.9) would. Fit is reasonable. The multipliers hold. The composite lands above threshold but not comfortably — the recommendation is **Consider**, not Apply.

`ats:verify` runs. The data is internally consistent. No flag.

`RUN_LOG.md` gets one entry: the command sequence, the composite with each factor labeled by source, the recommendation, and a one-line decision: *Compare against other Considers before spending an application slot.*

That's the whole loop. What makes it different from just reading the recommendation is the inspect step — knowing that the sponsorship term is 0.65 not 0.9, knowing why the composite landed on Consider rather than Apply, knowing which factor would have to improve to push it across the threshold. The recommendation is the headline. The provenance is the argument.

![A flow diagram of scan → pipeline → oferta → verify as four sequential stages, each annotated with its provenance checkpoint: ATS detected and postings list; four factors with source labels; composite with traced terms; consistency audit. The chain feeds into RUN_LOG.md.](images/14-skills-operating-the-engine-fig-03.png)
*Figure 14.3 — End-to-end chain: scan → pipeline → oferta → verify*

<!-- → [DIAGRAM: Flow diagram showing scan → pipeline → oferta → verify as four sequential boxes, each with a "provenance checkpoint" annotation (e.g., "ATS detected, postings list," "four factors with source labels," "composite with traced terms," "consistency audit"). Arrow at the end pointing to RUN_LOG.md. Caption: "The chain is only as trustworthy as its weakest provenance link — the verify step confirms consistency, not correctness."] -->

## The failure that looks like success

The error that ends the method quietly: trusting a recipe by its name rather than its behavior.

"It's called `oferta`, so it must be evaluating with real data." Names are labels. Behavior is evidence. A recipe can be edited — by you, by a collaborator, by a future version of the system — so that it stops calling its script and starts generating plausible-sounding output from the model's priors. The output format stays the same. The sourced-factors layout stays the same. The Apply/Consider/Skip recommendation stays the same. Nothing in the presentation tells you that the sponsorship probability now comes from the model's sense of what a good biotech sponsorship probability should be rather than from an LCA record.

The inspect step is the only protection. On every run of every recipe you plan to trust, you confirm: did it call the script? Is there an audit? Can I trace the sponsorship number to a record?

If you can't answer yes to those questions, the output is a model judgment. It may be useful. It may even be accurate. But it is not a finding, and you should not make a Skip or Apply decision on its basis.

| What you observed on this run | Treatment | Action |
|---|---|---|
| Active recipe, provenance visible (script called, audit present) | Finding | Record and act |
| Draft/helper recipe, or provenance absent | Model judgment | Useful for drafting, not for decisions |
| Any recipe whose output you can't trace | Distrust the output | Re-run with inspection |

*The recipe's name is not the evidence. The provenance is the evidence.*

## What the loop cannot do

The run-inspect-record loop guarantees you *can* see provenance. It cannot guarantee you will draw the right conclusion from what you see.

Today's scan might have hit a stale cache and returned a posting that closed yesterday — the data is real, but the world has moved. The fit score of 0.72 might be confidently wrong for a role where your unusual project background is exactly what the team needs and no keyword in the job description captured it. The timeline factor rests on an estimate of processing time that the system cannot verify against the actual adjudication queue.

The engine runs the components and surfaces the evidence. The decision about whether a given run is trustworthy enough to act on is yours, every time. Automation makes the loop fast. It does not make it self-policing. A method that runs itself without a human in the inspect step is not the method.

## The shape of what the book has built

This is the chapter where all five components run together for the first time. Sponsorship detection (Chapter 7), liveness classification (Chapter 8), role quality (Chapter 9), timeline (Chapter 10), the composite scorer (Chapter 11) — each one producing a number with a labeled source, each number flowing into the oferta composite, each composite going into the run log as a traceable decision.

The engine is not complicated. It is thorough. The sophistication is not in the architecture; it is in the habit of inspection. You can run the whole sequence in under ten minutes for a single role. What takes discipline is doing the inspect step every time instead of shortcutting to the recommendation because the format looks familiar.

Running the engine produces decisions. A decision you can't reconstruct is one you can't learn from — and learning from the search is the subject of what comes next.

---

## Key terms

**Recipe** — a named operation the engine runs (`scan`, `pipeline`, `oferta`, `tracker`, `pdf`), declared in a markdown file that states the scripts it calls, the data it reads, and what it logs; the runtime lives in `recipes/`. Elsewhere in agentic AI these are called **skills** (for example, Claude's Agent Skills). This book calls them *recipes* on purpose: a recipe is a procedure you can audit step by step, not a capacity — and the word "skill" is already spoken for here. In Chapters 9 and 13, "skill" means the O*NET / labour-market sense: the competencies a role demands and a résumé claims. One word with two meanings is exactly the silent ambiguity the engine exists to kill.

**Active recipe** — a recipe that calls real scripts and reads real audits, so its output is a finding.

**Draft / helper recipe** — a scaffold not yet verified, on a given run, to call scripts and write a log; treat its output as model judgment until you confirm otherwise.

## Chapter 14 Exercises: Recipes — Operating the Engine

**Project:** Your Own Reallocation Engine

**This chapter adds:** the operating discipline — the run-inspect-record loop and the provenance check that lets you tell a finding (a recipe that called a script and read an audit) from a fluent guess wearing the engine's uniform, every single run.

---

### Exercise 1 — When to Use AI

**The judgment:** In this chapter's work, AI assistance is appropriate for the following tasks:

- **Summarizing a recipe's output and the provenance you observed.** — *Why AI works here:* reformatting what you inspected; checkable against the run.
- **Drafting the `RUN_LOG.md` entry from the command and output you paste.** — *Why AI works here:* structured reformatting of facts you supply.
- **Explaining what a recipe declares it calls and reads.** — *Why AI works here:* it reads the recipe file with you; you confirm by running it.

**The tell:** You know you are using AI appropriately when you can evaluate the output — when you have independent criteria to judge whether it is correct, complete, and fit for purpose. Here the criterion is the provenance: did the script run, is there an audit, can the number be traced?

---

### Exercise 2 — When NOT to Use AI

**The judgment:** In this chapter's work, the following tasks require human judgment. Delegating them to AI is not appropriate — not because AI cannot produce output, but because AI output in these cases cannot be trusted without verification that requires the same expertise as doing the task yourself.

- **Deciding whether a run is finding-grade or judgment-grade.** — *Why AI fails here:* this is the inspect step — confirming a script was called and a number traces to a record; the output format looks identical either way, so the model can't certify its own provenance.
- **Trusting a recipe by its name.** — *Why AI fails here:* names are labels, behavior is evidence; a recipe called `oferta` that quietly became a chat prompt still says "oferta," and only inspection reveals the drift.
- **Concluding from a recommendation without tracing it.** — *Why AI fails here:* acting on a confident output because it looks right is the fluency trap reopened; the trace is yours to demand.

**The tell:** You know you have crossed the line when you are using AI output as your reason for a conclusion rather than as a tool for reaching one. If you could not explain the conclusion without the AI, the AI did the work that should have been yours.

**Series connection:** This exercise trains **Tier 4 (Metacognitive supervision)** in its purest form — the habit of inspecting provenance every run, refusing to let a familiar format substitute for evidence that the work was actually done.

---

### Exercise 3 — LLM Exercise

**What you're building this chapter:** a provenance verdict for your recipe runs — finding-grade vs. judgment-grade — and a reusable inspect checklist you apply before trusting any output.

**Tool:** Claude (claude.ai chat). You paste a recipe's output plus what you observed about its execution; chat helps you classify.

**The Prompt:**

```
Help me decide whether a recipe run is FINDING-grade (it called a script and read
an audit; its numbers trace to records) or JUDGMENT-grade (model output dressed in
the finding format). Do NOT assume provenance I don't give you — if I don't tell
you a script was called or an audit exists, say "cannot determine provenance — re-
run with inspection."

I will paste: the recipe's output, AND what I observed about the run (was a script
invoked? is there an audit file? can any number be traced to a record?).

1. Classify the run: finding-grade or judgment-grade, citing the SPECIFIC
   provenance evidence (or its absence).
2. For each number in the output, say whether it traces to a record, is a labeled
   model judgment, or is unsourced (the dangerous case).
3. Write me a reusable 5-item inspect checklist I can run on any recipe output
   before trusting it.
4. If judgment-grade: state plainly that this output is fine for drafting but must
   NOT drive an Apply/Skip decision.

--- PASTE RECIPE OUTPUT + WHAT I OBSERVED ABOUT THE RUN ---
[paste here]
```

**What this produces:** a provenance classification per run plus a reusable inspect checklist — the safety habit the chapter is built around.

**How to adapt this prompt:**
- *For your own project:* always paste what you actually observed (script called? audit present?). Without it, the honest answer is "cannot determine" — and the prompt will say so.
- *For ChatGPT / Gemini:* works as-is; both tend to assume provenance from a confident format — keep the "do not assume provenance" instruction.
- *For a Claude Project:* store the finding-vs-judgment definitions and the inspect checklist in the instructions.

**Connection to previous chapters:** this is Chapter 3's verified-data contract enforced at runtime, and Chapter 1's interrogation reflex applied to your own tooling.

**Preview of next chapter:** Chapter 15 reads the decisions this loop produces — the skip rate that tells you whether the whole method is operating or has quietly collapsed.

---

### Exercise 4 — CLI Exercise

**What you're building this chapter:** a full operated run on a real role — scan → pipeline → oferta → verify — with provenance inspected at each step and a drift check on one recipe.

**Tool:** Claude Code. Running the recipe chain and inspecting provenance is the engine's core workflow.

**Skill level:** Intermediate.

**Setup:**

Before running this exercise, confirm:
- [ ] `recipes/_shared.md` loads and the active recipes (`scan`, `pipeline`, `oferta`, `verify`) run.
- [ ] You have a real target role to operate on.
- [ ] You understand the inspect step is mandatory, not optional.

**The Task:**

```
Operate the engine on ONE real role and inspect provenance at every step. Do not
accept any recipe's output without showing me its provenance.

1. Run the chain: npm run ats:scan → the pipeline pass → oferta → npm run ats:verify.
2. At EACH step, report provenance: which script was called, which audit/output
   file was written, and which numbers trace to records vs. are labeled model
   judgment (fit). If a step shows no script call or no audit, STOP and flag it.
3. Produce the oferta recommendation with all four factors labeled by source.
4. DRIFT CHECK: pick one active recipe and confirm it actually invoked its script
   this run (not just produced plausible output). Show the evidence.
5. Append a RUN_LOG.md entry: the command chain, the recommendation with sources,
   and your finding-grade/judgment-grade verdict. Stop.
```

**Expected output:** a logged operated run with per-step provenance, a sourced recommendation, and a drift-check confirming the recipe really called its script.

**What to inspect in the output:** for the oferta result, can you trace the sponsorship number to an LCA/USCIS record and see fit labeled as judgment? For the drift check, is there actual evidence of a script call (an audit file, a row count) — or just confident output? The latter is the chapter's opening failure.

**If it goes wrong:** the failure that matters is a recipe producing finding-shaped output with no script call behind it. Recover by re-running with provenance logging on and confirming the audit exists; treat any untraceable number as model judgment, not a finding.

**CLAUDE.md / AGENTS.md note:** add a standing rule — *"No Apply/Skip decision rests on a recipe output whose provenance wasn't inspected this run; a recipe is trusted by its behavior (script called, audit present), never by its name."* This pins the loop's safety into the repo.

---

### Exercise 5 — AI Validation Exercise

**What you're validating:** an `oferta` recommendation that looks exactly like a finding but never called the sponsorship pipeline — the chapter's opening failure, fluency in the engine's own uniform.

**Validation type:** Agentic output (provenance).

**Risk level:** High — it's indistinguishable from a real finding by format alone, so it's the easiest dangerous output to trust.

**Setup (pre-generated artifact — option b):** This chapter opens on exactly this failure, so validate this pre-generated recipe output:

> **oferta — Role evaluation (Atlas Bio).** Sponsorship: 0.88 (strong). Fit: 0.74.
> Liveness: live. Timeline: 0.9. Composite: 0.71 → APPLY. Each factor sourced;
> recommendation traceable. A clean, confident evaluation — proceed.
> *(Run provenance, on inspection: no sponsorship script was invoked this run; no
> LCA/USCIS audit file was written or read; the 0.88 was produced by the model's
> sense of a plausible biotech sponsorship probability. The output format is
> identical to a real finding.)*

**The Validation Task:**

Evaluate the AI output above using the following checklist. For each item, record: Pass / Fail / Cannot determine — and explain your reasoning.

```
Validation Checklist — Recipes: Operating the Engine

□ Correctness: Does the output's claim "each factor sourced" match the actual
  provenance (no script called, no audit)?
□ Completeness: Is there an audit file or row count behind the 0.88 sponsorship
  number, or only a confident format?
□ Scope: Did the recipe do verified work, or generate plausible output from
  priors?
□ Provenance check (chapter-specific): For each factor, can you trace it to a
  record this run? Which can you NOT?
□ Name-vs-behavior check (chapter-specific): It's called "oferta" — does that make
  it a finding? What's the actual evidence?
□ Failure mode check: Does this output exhibit any of the following?
  - Finding-shaped output with no script behind it (the chapter's opening failure)
  - Trusting a recipe by name rather than behavior
  - Fluent but wrong (a confident Apply with no provenance)
```

**What to do with your findings:**
- If the output passes all checks: act on it. (It will not — no script was called; it's judgment-grade.)
- If it fails one check: re-run the recipe with provenance confirmed before making any decision.
- If it fails multiple checks or you cannot determine pass/fail: this is a "When NOT to Use AI" moment — treat the output as model judgment, useful for drafting, never for an Apply/Skip call.

**AI Use Disclosure prompt:**
After completing this validation, write a two-sentence AI Use Disclosure:
> *Sentence 1:* What AI produced in this exercise and how you used it.
> *Sentence 2:* One specific thing the AI could not determine that required your judgment.

**Series connection:** This exercise trains **Tier 4 metacognitive supervision** — the inspect-every-run habit that catches the most dangerous output in the whole engine: the one that looks exactly like a finding and is built on nothing.

## Prompts

### Figure 14.1 — Active vs. draft recipes
**Files:** ../images/14-skills-operating-the-engine-fig-01.svg
**Prompt:** Brutalist two-column comparison on white: an active column (scan, pipeline, oferta, tracker, pdf in JetBrains Mono, each with a one-line description) that calls scripts and reads audits, beside a draft/helper column (apply, contacto, deep, followup, and others) tagged "verify before trusting." Red accent on active, gray on draft. No shadows or gradients.

### Figure 14.2 — The run-inspect-record loop with provenance checkpoints
**Files:** ../images/14-skills-operating-the-engine-fig-02.svg
**Prompt:** Brutalist cycle diagram on white: three nodes — Run, Inspect, Record — joined by clockwise single-headed arrows, with the Inspect node accented and labeled as the only protection. One ochre rule under the caption. EB Garamond node labels, ink strokes, no decoration.

### Figure 14.3 — End-to-end chain: scan → pipeline → oferta → verify
**Files:** ../images/14-skills-operating-the-engine-fig-03.svg · ../d3/14-skills-operating-the-engine-fig-03.html
**Prompt:** Brutalist flow diagram on white: four sequential stages (scan, pipeline, oferta, verify) in JetBrains Mono, each with a provenance-checkpoint caption, feeding a single-headed arrow into a RUN_LOG.md node. Red accent on the stage names, ink boxes, one ochre rule under the caption about the weakest provenance link. No shadows or gradients.
# Chapter 15 — The Pipeline Tracker and the Skip Rate

<!-- voice-anchored: root style/VOICE.md. Anatomy: TIKTOC Part 10.
     Sourced from SDD Component 5, plain-summary (skip rate ≥50%, 3-3-2), recipes/tracker.md,
     "The 3-3-2 Split" essay, CHAPTER-RESEARCH-MAP. Privacy note: data/ats/ files are private (DATA_CONTRACT). Draft. Never published. -->

Imagine running the entire engine — scanning, scoring, framing, applying — and keeping no record of any of it. You'd have no response rate. No way to know whether Proven-tier applications outperform Unknown-tier ones. No signal that three weeks in, you've quietly drifted back to eight hours of clicking Submit. You'd be flying with no instruments, feeling busy, learning nothing. The decisions would still happen; you just couldn't see whether any of them worked, or correct course when they didn't.

The tracker is the instrument panel. But the most important number on it is not the one most people expect.

---

The counterintuitive heart of this chapter is this: **the target is a skip rate of at least fifty percent.** Of the roles the engine evaluates, you should be deciding not to apply to at least half.

Sit with why that's the goal and not a failure. If you apply to nearly everything the engine surfaces, your filter is too loose — you've recreated spray-and-pray with extra steps, and the targeted two hours from Chapter 2 has swollen back toward eight. A high skip rate means the filter is doing real work: separating the few roles worth a day off your ninety-day clock from the many that aren't. The skip rate is the dial that tells you whether the reallocation principle is actually operating or has quietly collapsed.

The reflex to resist is feeling good about a low skip rate because "I'm applying to a lot of things." That feeling is the volume instinct wearing a tracker. Low skip rate is not productivity. It is the filter failing. If your skip rate is twenty percent and you feel busy and productive, that pairing is the warning sign — busy and unfiltered is exactly the state the whole book exists to end.

So the tracker reads in two directions. Skip rate well under fifty percent means the filter is too permissive, or you're overriding it constantly; you're back to volume. Skip rate close to a hundred percent means either your upstream targeting is bad — no good roles reaching the scorer — or your thresholds are set impossibly high; either way, the funnel needs attention upstream. Skip rate above fifty percent with a steady flow of applies and a rising per-tier response rate: the engine is working as designed.

The skip is not an absence in the log. It is a decision, and a tracker that logs only applications is missing half the data about how well the filter works.

![A horizontal dial for the skip rate marked with the decision bands: below 40% is too loose (filter too permissive); 40–50% is borderline; above 50% with steady applies is healthy; above roughly 85% is starved (funnel too tight). A pointer sits in the healthy band, with the 50% target marked as the line the filter must clear.](images/15-the-pipeline-tracker-and-the-skip-rate-fig-01.png)
*Figure 15.1 — Reading the skip-rate dial*

---

The component that makes this legible is the Pipeline Tracker, the engine's fifth component, maintained through the `tracker` recipe and analyzed with the patterns script:

```bash
# Maintain / update the decision log (tracker recipe writes data/ats/applications.md)
npm run ats:scan        # feeds new postings into the pipeline for decisions
# tracker recipe: log each decision (company, role, score, tier, timeline flag, outcome incl. skip)

# Analyze tracker/scan/pipeline data for patterns and the allocation summary
python scripts/ats/analyze-patterns.py
```

For every decision the engine produces — apply or skip — the tracker records the company and role, the composite score and tier, the timeline flag, the recommendation, and the outcome. The output of `analyze-patterns.py` is the daily allocation summary plus your skip rate and per-tier response rates. You read the skip rate first. It is the fastest signal that the method is or isn't operating.

A privacy note that belongs here before anything else: your tracker files — `data/ats/applications.md`, `pipeline.md`, scan history — contain your real targets and real activity. They are private, never committed or shared without a privacy review. This is a hard rule that becomes load-bearing in Chapter 16.

---

Consider a week of actual tracker data: thirty roles evaluated, seventeen skipped, thirteen applied, nine of the thirteen in Proven or Likely tier. Skip rate is seventeen over thirty — fifty-seven percent. Healthy: the filter is doing real work. Early response data shows Proven-tier applications drawing replies at several times the rate of the few Unknown-tier ones, which is evidence that the tiering is predictive rather than decorative. The allocation summary, though, shows apply hours creeping to three and a half per day while networking has dipped — a drift warning that the tracker caught before a full week was gone.

The right response to that picture: keep the thresholds, because the skip rate is healthy, but reclaim an hour from applying back to networking next week. That is the 3-3-2 decision rule operating on real data rather than on principle.

![A week of thirty evaluated roles broken into seventeen skips and thirteen applies on a single zero-based bar, with skips drawn as a full segment rather than an empty space. The 57% skip rate sits above the 50% target line, showing the filter doing real work — the skips are counted as data, not absence.](images/15-the-pipeline-tracker-and-the-skip-rate-fig-02.png)
*Figure 15.2 — A week of decisions: skips are data*

The limit is equally worth stating. Early in the search, per-tier response samples are tiny and noisy — a three-application "trend" is not a trend. And the skip rate is a process metric, not an outcome metric. A healthy skip rate with zero responses still means something is wrong; it just means something upstream is wrong — bad targeting, weak materials — not that the filter itself has failed. The tracker measures discipline and targeting quality. It cannot conjure offers, and it cannot tell the difference between a targeting failure and a sector-wide hiring freeze. The numbers look identical. You read them in the context of a market the tracker can't see.

---

The decision rules for reading your own skip rate are compact enough to state directly:

Below forty percent is too loose. Trust the scorer's skips; stop overriding to apply. Between forty and fifty percent is borderline; watch whether your overrides are justified or habitual. Above fifty percent with steady applies and rising per-tier response rates is healthy — hold. Above roughly eighty-five percent, nearly everything skipped, means the funnel is starved or over-tight; fix upstream targeting in Chapters 6 and 5 or loosen the thresholds slightly.

The allocation summary closes the other loop. It shows how your hours actually split across apply, network, and portfolio — so the tracker doesn't just measure targeting quality, it catches allocation drift before a week has gone sideways. The skip rate tells you the filter is working. The allocation summary tells you that you are. You need both readings to know that the search is actually running the way Chapter 2 designed it.

![Two side-by-side readings. The left panel is the skip rate read against its target — is the filter working? The right panel is the allocation split across apply, network, and portfolio read against 3-3-2 — are you working as designed? The skip rate measures targeting quality; the allocation summary measures discipline, and both are needed.](images/15-the-pipeline-tracker-and-the-skip-rate-fig-03.png)
*Figure 15.3 — Two readings: skip rate and allocation*

## Chapter 15 Exercises: The Pipeline Tracker and the Skip Rate

**Project:** Your Own Reallocation Engine

**This chapter adds:** the instrument panel — a logged decision (Apply *and* Skip) for every role, a skip rate read against the ≥50% target, and an allocation summary that catches drift back toward volume before a week is lost.

---

### Exercise 1 — When to Use AI

**The judgment:** In this chapter's work, AI assistance is appropriate for the following tasks:

- **Computing your skip rate and per-tier response rates from logged data.** — *Why AI works here:* arithmetic over a table you supply; checkable by hand.
- **Generating the daily allocation summary (apply/network/portfolio split).** — *Why AI works here:* reformatting your logged hours into a read-out.
- **Reformatting the tracker into a readable weekly view.** — *Why AI works here:* pure restructuring of your data.

**The tell:** You know you are using AI appropriately when you can evaluate the output — when you have independent criteria to judge whether it is correct, complete, and fit for purpose. Here the criterion is your own decision log.

---

### Exercise 2 — When NOT to Use AI

**The judgment:** In this chapter's work, the following tasks require human judgment. Delegating them to AI is not appropriate — not because AI cannot produce output, but because AI output in these cases cannot be trusted without verification that requires the same expertise as doing the task yourself.

- **Deciding that a low skip rate is "fine because I'm applying a lot."** — *Why AI fails here:* that's the volume instinct wearing a tracker; recognizing it as a warning sign rather than productivity is a judgment about your own behavior.
- **Interpreting a healthy skip rate with zero responses.** — *Why AI fails here:* the tracker can't see the market — it can't tell a targeting failure from a sector-wide freeze; that read requires context the data doesn't hold.
- **Judging whether your overrides were justified or habitual.** — *Why AI fails here:* only you know what private reason drove each override, and whether it was real.

**The tell:** You know you have crossed the line when you are using AI output as your reason for a conclusion rather than as a tool for reaching one. If you could not explain the conclusion without the AI, the AI did the work that should have been yours.

**Series connection:** This exercise trains **Tier 4 (Metacognitive supervision)** with a **Tier 7** edge — reading the skip rate as a mirror of your own discipline, and resisting the comfortable misread that busy equals effective.

---

### Exercise 3 — LLM Exercise

**What you're building this chapter:** a weekly diagnosis of your search — skip rate, per-tier response (with honest sample-size caveats), allocation split, and the single adjustment to make next week.

**Tool:** Claude (claude.ai chat). You paste a week of tracker decisions; chat computes and reads.

**The Prompt:**

```
Below is a week of my job-search decision log: each row is a role with its
composite score, tier, timeline flag, Apply/Skip decision, and any response.
Do NOT invent rows or responses — use only what I paste.

1. Compute my SKIP RATE (skips / total evaluated). State whether it's too low
   (<40%, filter too permissive / over-applying), borderline (40–50%), healthy
   (>50% with steady applies), or starved (>~85%, funnel too tight).
2. Compute per-tier response rates — BUT flag any tier with a small sample (say
   <8) as "too noisy to trust yet." Do not call a 3-application difference a
   trend.
3. Give my allocation split (apply/network/portfolio hours) and flag any drift
   from 3-3-2.
4. Name the ONE adjustment for next week, citing the decision rule that motivates
   it. If the skip rate is healthy but responses are zero, say explicitly that
   this points UPSTREAM (targeting/materials) or to the market — not to the
   filter.

--- PASTE A WEEK OF TRACKER ROWS BELOW ---
[paste here]
```

**What this produces:** a one-week diagnosis with a skip-rate verdict, caveated response rates, an allocation read, and a single next move — the steering signal for the search.

**How to adapt this prompt:**
- *For your own project:* paste your real tracker rows. Keep the sample-size caveat — early-search numbers are tiny and the temptation to over-read them is strong.
- *For ChatGPT / Gemini:* works as-is; both will happily declare trends from three data points — keep the noise flag.
- *For a Claude Project:* store the decision-rule thresholds (40/50/85%) and the 3-3-2 target.

**Connection to previous chapters:** the skip rate is Chapter 2's reallocation principle made measurable; the tiers come from Chapter 7, the scores from Chapter 11.

**Preview of next chapter:** Chapter 16 builds and runs the whole engine end to end — and this skip rate is one of the readouts of the first honest run.

---

### Exercise 4 — CLI Exercise

**What you're building this chapter:** your tracker populated with real decisions and an analysis run producing skip rate, per-tier response, and allocation summary — kept private, never committed.

**Tool:** Claude Code. Running the tracker recipe and `analyze-patterns.py` over your decision log is a data workflow.

**Skill level:** Intermediate.

**Setup:**

Before running this exercise, confirm:
- [ ] The `tracker` recipe and `scripts/ats/analyze-patterns.py` exist.
- [ ] You have real decisions (Apply and Skip) to log.
- [ ] You understand `data/ats/` files are PRIVATE (DATA_CONTRACT) — never committed.

**The Task:**

```
Maintain my decision tracker and analyze it. PRIVACY: data/ats/ files
(applications.md, pipeline.md, scan history) are private — never stage, commit,
or print them outside this session. Do not invent decisions or responses.

1. Log my decisions via the tracker recipe: each role's company, role, score,
   tier, timeline flag, recommendation, and outcome — INCLUDING skips (a skip is
   a logged decision, not an absence).
2. Run:  python scripts/ats/analyze-patterns.py
   Report: skip rate, per-tier response rates (with sample sizes), and the daily
   allocation summary.
3. Apply the decision rules: classify the skip rate (too low / borderline /
   healthy / starved) and the allocation (on or off 3-3-2).
4. Write a RUN_LOG.md entry (safe to keep) with the skip rate, allocation, and one
   adjustment — but do NOT copy private target names into it.
5. Confirm no data/ats/ file was staged for commit. Stop.
```

**Expected output:** an updated private tracker, an analysis printout (skip rate, response rates with sample sizes, allocation), and a privacy-safe run-log entry.

**What to inspect in the output:** is the skip rate computed over Applies *and* Skips (skips must be logged)? Are small per-tier samples flagged rather than read as trends? Confirm nothing under `data/ats/` got staged for commit — the privacy rule is load-bearing for Chapter 16's public build.

**If it goes wrong:** two failures to watch — skips not being logged (which inflates the apparent skip rate's denominator wrongly) and private files leaking into a commit or the run log. Recover by re-logging skips as decisions and scrubbing any private name from shareable files.

**CLAUDE.md / AGENTS.md note:** add a standing rule — *"Every decision is logged including skips; `data/ats/` is private and never committed; skip rate and response rates are read with sample-size caveats and against market context, never as outcome guarantees."* This pins the chapter's discipline and the privacy rule.

---

### Exercise 5 — AI Validation Exercise

**What you're validating:** an AI analysis that read a low skip rate as success and over-read a tiny sample — the volume instinct wearing a tracker.

**Validation type:** Reasoning chain (over metrics).

**Risk level:** Medium — a wrong read here quietly returns you to spray-and-pray while feeling productive.

**Setup (pre-generated artifact — option b):** This chapter's lesson is that a low skip rate is the filter failing, not productivity, so validate this pre-generated analysis:

> **Weekly tracker analysis.** Great week — you applied to 24 of 30 roles
> evaluated (80% apply rate, 20% skip rate), so you're being highly productive and
> covering lots of ground. Keep the momentum. Also, Unknown-tier roles got 1
> response out of 2 (50%) while Proven got 2 out of 9 (22%), so Unknown-tier
> companies are actually your best bet — shift effort toward them.

**The Validation Task:**

Evaluate the AI output above using the following checklist. For each item, record: Pass / Fail / Cannot determine — and explain your reasoning.

```
Validation Checklist — The Pipeline Tracker and the Skip Rate

□ Correctness: Is a 20% skip rate "highly productive," or is it the filter being
  too permissive (the chapter's warning)?
□ Completeness: Does the analysis treat the skip rate as a process metric to be
  read against the target (≥50%), or as a vanity volume number?
□ Scope: Did it conflate "applied to a lot" with "doing well"?
□ Skip-rate check (chapter-specific): What does a 20% skip rate signal about the
  reallocation principle — is it operating or collapsed?
□ Sample-size check (chapter-specific): Is "Unknown beats Proven" based on 2
  applications? Is that a trend or noise?
□ Failure mode check: Does this output exhibit any of the following?
  - Reading a low skip rate as productivity (volume instinct)
  - Over-reading a 2-sample "trend"
  - Fluent but wrong (a confident, encouraging misread of the dial)
```

**What to do with your findings:**
- If the output passes all checks: follow it. (It will not — it praises a failing filter and trusts a 2-sample trend.)
- If it fails one check: re-read the skip rate against the ≥50% target and tighten the filter; ignore the tiny-sample tier claim.
- If it fails multiple checks or you cannot determine pass/fail: this is a "When NOT to Use AI" moment — you read the dial against your own discipline and the market.

**AI Use Disclosure prompt:**
After completing this validation, write a two-sentence AI Use Disclosure:
> *Sentence 1:* What AI produced in this exercise and how you used it.
> *Sentence 2:* One specific thing the AI could not determine that required your judgment.

**Series connection:** This exercise trains **Tier 4 metacognitive supervision** with **Tier 7** stakes — catching the comfortable misread that turns an instrument panel into a productivity-theater dashboard. A low skip rate isn't ground covered; it's the filter failing.

---

## Key terms

- **Pipeline Tracker:** the component that logs every decision — score, tier, timeline flag, outcome, including skips.
- **Skip rate:** the share of evaluated roles you decide not to apply to; target ≥ 50% as evidence the filter works.
- **Daily allocation summary:** the read-out of how your hours split across apply / network / portfolio (3-3-2).
- **Process vs. outcome metric:** skip rate measures discipline and targeting quality; it must be read alongside response rate and market context.

## Run-log prompt

Record the week's skip rate, the per-tier response rates with sample sizes, the allocation summary, and the one adjustment you're making next week.

## Prompts

### Figure 15.1 — Reading the skip-rate dial
**Files:** ../images/15-the-pipeline-tracker-and-the-skip-rate-fig-01.svg
**Prompt:** Brutalist horizontal dial on white marked with decision bands — below 40% too loose, 40–50% borderline, above 50% healthy, above 85% starved — with a pointer in the healthy band and the 50% target marked in red. Gray bands, one red accent, JetBrains Mono percentage ticks, no gradients or shadows.

### Figure 15.2 — A week of decisions: skips are data
**Files:** ../images/15-the-pipeline-tracker-and-the-skip-rate-fig-02.svg
**Prompt:** Brutalist single stacked bar on a zero baseline: thirty evaluated roles split into seventeen skips and thirteen applies, the skip segment drawn as a solid block, not empty space, with the 57% skip rate above a red 50% target line. Ink and gray segments, one red accent, JetBrains Mono labels, no decoration.

### Figure 15.3 — Two readings: skip rate and allocation
**Files:** ../images/15-the-pipeline-tracker-and-the-skip-rate-fig-03.svg
**Prompt:** Brutalist two-panel comparison on white: left panel the skip rate against its target ("is the filter working?"), right panel the apply/network/portfolio hours against 3-3-2 ("are you working as designed?"). One red accent per panel, ink axes, JetBrains Mono ticks, no gradients or shadows.
# Chapter 16 — The Build and the Honest Run
*You built a machine that is superhuman at execution precisely so you could spend your scarce attention on the questions it cannot reach.*

Think of an orchestra. Each musician can execute passages no conductor could play. But the conductor never touches an instrument. The conductor decides what the piece *means*, hears the wrong note before the score confirms it, and holds a hundred separate parts toward one intention. Remove the musicians and nothing gets played. Remove the conductor and you get a hundred fluent parts that don't add up to music.

That is the shape of building this engine. There is a part that belongs to the AI — scaffolding, schemas, scoring formulas, boilerplate, glue code, the structural logic of five components wired into one system. The AI is superhuman at this. Left to itself it produces clean, confident, internally consistent code in minutes. And there is a part that belongs to you: what your visa situation actually requires, whether the probability math makes sense given what you know, the domain knowledge the model cannot have, and the integration of five components into one system you will stake your job search — and your immigration status — on.[^boondoggle]

The whole book has been preparing you to be the conductor. This chapter is where you pick up the baton.

## How you build it

You don't ask the AI to "build a job-search engine." You conduct it through phases, each with a handoff condition — the precisely stated thing that must be true before the next phase begins.

**Phase one: foundation.** The directory layout, the data contract, the intake questions, the environment. The AI scaffolds the structure; you decide what your eight intake answers from Chapter 10 must constrain. These are first-class inputs, not setup trivia. Your OPT expiration date, your STEM eligibility, your field — the system that doesn't have those pinned is a system that can produce a confident recommendation about a role you can never legally start.

**Phase two: core skeleton.** The data structures and the five component stubs. The AI writes the schemas; you confirm they encode your situation. A schema that doesn't distinguish Proven from Likely sponsorship tiers, or that treats your timeline as a preference rather than a gate, is wrong in a way the AI cannot detect from the inside.

**Phase three: integration.** Wiring the five components into the composite scorer from Chapter 11 and the recipes from Chapter 14. The AI connects the pieces; you verify that liveness and timeline act as multipliers — gates that zero the score — and not as weighted votes. This is the class of error that will look exactly like correct behavior. The code will run. The numbers will be in a plausible range. Only you know that a role expiring before you can start shouldn't score "Consider."

**Phase four: full feature build.** The pipelines — SEC, ATS, BLS — the framing generator, the résumé renderer. The AI builds each component; you verify each against its real dataset. "The SEC pipeline returns company funding records" is a verification you can run. "The SEC pipeline looks complete" is not.

**Phase five: hardening.** Error handling, the verification scripts, the audit trail. The AI implements; you decide what "correct" means for your search and what must never fail silently. A recipe that stops calling its script and starts generating plausible output from the model's priors — the failure Chapter 14 opens with — is the thing hardening is designed to catch.

**Phase six: release.** The first real run.

![Six build phases in a left-to-right sequence — foundation, core skeleton, integration, full feature build, hardening, release. Each phase is split into an "AI executes" row and a "you verify" row, with a handoff condition between phases that must be stated precisely before proceeding.](images/16-the-build-and-the-honest-run-fig-01.png)
*Figure 16.1 — Six phases, two rows: AI executes, you verify*

<!-- → [DIAGRAM: Six build phases shown as a left-to-right sequence with labeled handoff conditions between phases. Each phase split into two rows: "AI executes" (top) and "You verify" (bottom). The gap between phases labeled "handoff condition — must be stated precisely before proceeding." Caption: "A handoff you can't state precisely is a phase you haven't actually finished."] -->

The handoff condition is the most important element of the whole build. "The scan returns real postings with provenance" is a handoff condition. "It looks done" is not. The places where builds go wrong are almost always places where a phase ended on a feeling rather than a test.

## The boundary, made operational

I want to be precise about where the line is, because this is where the abstract principle from Chapter 1 — execution versus judgment — becomes a checklist you can actually run.

The model can verify that code is internally consistent. It cannot verify that the code is grounded in the specific reality you are building it for. It will produce a sponsorship formula that compiles and a timeline factor that returns a number; it cannot know whether the weights match your binding constraint or whether the dates are yours. So the moves that remain irreducibly yours:

**Plausibility auditing** — reading the output and asking "could this be right?" before trusting the verification. The composite came back 0.7 for a non-sponsor. Chapter 11 says the dominant term should collapse to near zero when P(sponsorship) ≈ 0. Does 0.7 make sense? It doesn't. Catch it before it propagates.

**Problem formulation** — deciding what the engine is for, and re-engaging it when an audit finding changes the shape of the problem. The model builds what you specify; you remain responsible for whether the specification was right.

**Interpretive judgment** — supplying the meaning the model can't. An "Unknown" sponsorship tier is a coverage gap in the dataset, not a verdict on the company. A skipped role had a connection the data never saw. A fit score of 0.72 might undersell you for a role where your unusual background is precisely what the team needs and no keyword captured it.

**Orchestration** — holding all of it toward one end: a job, landed in time, honestly.

| Give to the AI | Keep for yourself |
|---|---|
| Scaffolding and directory layout | Weight calibration |
| Schemas and data structures | Plausibility audits |
| Formula implementation | Unknown-tier interpretation |
| Boilerplate and glue code | Privacy and honesty calls |
| Documentation drafts | Final go/no-go on real decisions |
| Anything where correctness is checkable | Anything the model can verify only against itself |

*The test: can the model verify this against reality, or only against itself? If only against itself, it's yours.*

![Two columns. "Give to the AI": scaffolding, schemas, formula implementation, boilerplate, glue code, documentation drafts — anything checkable against reality. "Keep for yourself": weight calibration, plausibility audits, Unknown-tier interpretation, privacy and honesty calls, the final go/no-go — the things the model can verify only against itself.](images/16-the-build-and-the-honest-run-fig-02.png)
*Figure 16.2 — Give to the AI vs. keep for yourself*

## The ethics gate

Before any first real run, two rules that are not optional:

**Privacy.** Your `data/ats/` files — applications, pipeline records, scan history — contain your real targets and real activity. Your environment may contain credentials. These files are private. Review for privacy and size before any commit, and never publish them. Building in public does not mean exposing your job search.[^privacy]

**Honesty.** Everything from Chapter 12 holds at the system level. Accurate framing, no fabricated credentials, no invented metrics, no misrepresented status. An engine that optimizes your search by shading the truth is the failure mode this book exists to prevent — fluency in the service of a false impression is still a false impression, and it is worse when it arrives in a polished format.

If a run would breach either gate, you don't run it. The ethics gate is the conductor's first responsibility, not an afterthought to the build.

## The first real run

Release is not a demo. It is the engine, running on your actual search:

```bash
# Stand up and verify the engine end to end
npm run ats:scan        # real postings from real companies
npm run ats:liveness    # classify them live/ghost
npm run ats:verify      # confirm pipeline data is consistent
# then: pipeline → oferta on real roles → tracker logs every decision
python scripts/ats/analyze-patterns.py   # skip rate + allocation summary
```

The output is a batch of real, logged decisions — Apply/Consider/Skip on actual roles, each factor sourced, each decision in the tracker, a skip rate you can read. Not a simulation. Not a walkthrough. The engine, applied to the search you are actually running.

When I ran the first batch, thirty roles came back with roughly 57 percent skipped. The Applies were concentrated in Proven and Likely tiers with beatable timelines. Each skip freed time that went toward the work no pipeline can do: reaching out, building the portfolio, following up on the connections the data never saw.

But before the batch ran, a plausibility audit caught something. A draft composite was treating the timeline factor as a weighted vote rather than a multiplier. A role that should have zeroed on the clock — the start date was past my OPT window — was scoring "Consider." The code ran. The number looked reasonable. It was wrong in exactly the way fluency hides: internally consistent, grounded in nothing.

Fixed. That is what plausibility auditing is for.

![Two panels for the same role past its OPT window. In the buggy panel, the timeline factor is treated as a weighted vote: strong sponsorship, fit, and liveness drag the composite up to about 0.70, scoring Consider — wrong but reasonable-looking. In the fixed panel, the timeline factor is a multiplier: the closed gate drives the composite to zero, scoring Skip. The code ran in both cases; only the audit caught the difference.](images/16-the-build-and-the-honest-run-fig-03.png)
*Figure 16.3 — The gate-as-vote bug caught by plausibility audit*

![Horizontal bar chart of one sample batch of 30 roles broken down by outcome: Apply about 13 percent, Consider about 30 percent, Skip about 57 percent. The skip rate is the engine working, not failing — the time that doesn't go to ghost postings goes somewhere that matters.](images/16-the-build-and-the-honest-run-fig-04.png)
*Figure 16.4 — First real run: 30 roles by outcome and tier*

<!-- → [CHART: Horizontal bar chart showing one sample batch: 30 roles broken down into Apply (approx. 13%), Consider (approx. 30%), Skip (approx. 57%). Bars color-coded by sponsorship tier (Proven, Likely, Unknown, Non-sponsor). Caption: "A first real run on 30 roles — the skip rate isn't failure, it's the engine working. The time that doesn't go to ghost postings goes somewhere that matters."] -->

## What the machine could not know

The engine knows what it measured: funding records, government filings, ATS postings, occupation demand curves, your dates. It could not know that the founder of a skipped startup is your former lab partner. It could not know that its own fit score missed the one project that makes you right for a role where no keyword in the description captured it. It could not know that you would thrive at a lower-scored job and burn out at a higher one. It could not know whether staking your search on its math is wise — that judgment was never in the data.

This is not a limitation to work around. It is the design. You built a system that handles everything it can handle — reliably, repeatably, at scale — so that your scarce human attention is available for the things it cannot. The conductor doesn't play every instrument. The conductor hears the whole.

## The return

Return to the polished artifact from Chapter 1 — the clean recommendation that arrived in three confident seconds. You know now what to do with it. Don't ask whether it is impressive. Ask what would have to be true for it to be trusted. Ask what the machine could not know. Ask what you are now responsible for once the decision leaves the screen.

That question — *what am I now responsible for?* — is the one the whole book was climbing toward. The engine answers the questions it can answer. Everything it cannot is yours: the judgment, the stakes, the account you will give for the decision.

The search is live. The clock is running. Begin.

---

## Chapter 16 Exercises: The Build and the Honest Run

**Project:** Your Own Reallocation Engine — *capstone*

**This chapter adds:** the whole thing — you conduct the phased build, run the ethics gate, execute the first honest run on your real search, and write the "what the machine could not know" account. This is where the running project becomes a working engine and a finished deliverable.

---

### Exercise 1 — When to Use AI

**The judgment:** In this chapter's work, AI assistance is appropriate for the following tasks:

- **Scaffolding, schemas, glue code, and boilerplate across the build phases.** — *Why AI works here:* the AI is superhuman at execution where correctness is checkable against a test you run.
- **Drafting handoff conditions you then sharpen into testable statements.** — *Why AI works here:* it proposes; you convert "looks done" into "the scan returns real postings with provenance."
- **Generating documentation and a first draft of the monitoring protocol.** — *Why AI works here:* drafting against your real outputs, which you verify.

**The tell:** You know you are using AI appropriately when you can evaluate the output — when you have independent criteria to judge whether it is correct, complete, and fit for purpose. Here the criterion is: can the model verify this against reality, or only against itself? If checkable, give it to the AI.

---

### Exercise 2 — When NOT to Use AI

**The judgment:** In this chapter's work, the following tasks require human judgment. Delegating them to AI is not appropriate — not because AI cannot produce output, but because AI output in these cases cannot be trusted without verification that requires the same expertise as doing the task yourself.

- **The four irreducibly human moves — plausibility auditing, problem formulation, interpretive judgment, orchestration.** — *Why AI fails here:* the model verifies code against itself, not against your reality; only you can ask "could this be right?" and hold the whole toward one end.
- **The ethics gate — privacy and honesty.** — *Why AI fails here:* whether a run would expose your private search or shade the truth is a values call the model cannot make and should not be trusted to enforce.
- **The final go/no-go on real decisions and on whether the weights match your binding constraint.** — *Why AI fails here:* this is the conductor's accountability — the consequence (your job, your status) is yours to bear, so the decision is yours to make.

**The tell:** You know you have crossed the line when you are using AI output as your reason for a conclusion rather than as a tool for reaching one. If you could not explain the conclusion without the AI, the AI did the work that should have been yours.

**Series connection:** This capstone trains **Tier 4 + Tier 6 + Tier 7 together** — metacognitive plausibility audits, executive integration of five components into one system, and the wisdom to own the stakes and the ethics gate. The conductor doesn't play the instruments; the conductor hears the whole and is accountable for the performance.

---

### Exercise 3 — LLM Exercise

**What you're building this chapter:** your "what the machine could not know" account for your real search, plus a plausibility-audit checklist grounded in your actual runs — the honest description of residual uncertainty that closes the project.

**Tool:** Claude (claude.ai chat). You supply your real engine outputs; chat helps you articulate the account.

**The Prompt:**

```
Help me write two things for my job-search engine. Use ONLY what I paste about my
real runs; do not invent decisions, companies, or outcomes.

I will paste: a sample of my engine's outputs (scored roles, tiers, skip rate,
some Apply/Skip decisions).

1. "WHAT THE MACHINE COULD NOT KNOW" — an honest account for MY search:
   - What the engine actually measured (name the data sources).
   - What it structurally cannot know (private connections, fit it missed,
     present-tense sponsorship beyond the record, whether I'd thrive vs. burn out,
     whether staking the search on its math is wise).
   - What I am now responsible for that the data never touched.
   Write it specific to my outputs, not generic.

2. A PLAUSIBILITY-AUDIT CHECKLIST I run before trusting a batch: concrete "could
   this be right?" questions tied to known failure modes — e.g. a non-sponsor
   scoring Apply, a gate behaving as a vote, a stale-cache posting, an unsourced
   number in a finding-shaped output.

Do not reassure me the engine is trustworthy; help me state precisely where it
is and isn't.

--- PASTE A SAMPLE OF MY ENGINE OUTPUTS BELOW ---
[paste here]
```

**What this produces:** the project's closing artifact — a search-specific "what the machine could not know" account and a reusable plausibility-audit checklist.

**How to adapt this prompt:**
- *For your own project:* paste your real outputs. A generic account is worthless; the value is in naming what *your* engine missed.
- *For ChatGPT / Gemini:* works as-is; both drift toward reassurance — keep the "do not reassure me" instruction.
- *For a Claude Project:* store the four human moves and the ethics gate so the account stays honest.

**Connection to previous chapters:** this is Chapter 1's founding charter ("what the machine cannot know") returning as a finished, evidenced account — the book's arc closing on itself.

**Preview of next chapter:** there is no next chapter — this is the capstone. What follows is the search, run for real, on the engine you built.

---

### Exercise 4 — CLI Exercise

**What you're building this chapter:** the engine itself, conducted through the six phases with stated handoff conditions, and the first honest run producing a logged batch of real Apply/Consider/Skip decisions with a readable skip rate — after the ethics gate passes.

**Tool:** Claude Code. Conducting a phased build and running the full engine end to end is the capstone agentic workflow.

**Skill level:** Advanced — integrates every prior chapter.

**Setup:**

Before running this exercise, confirm:
- [ ] All five components and their recipes exist from Chapters 6–14.
- [ ] Your eight intake answers (Chapter 10) are pinned in config.
- [ ] `data/ats/` is private and git-ignored (Chapter 15 privacy rule).

**The Task:**

```
Conduct the engine build and the first honest run. State a testable handoff
condition before advancing each phase; do not proceed on "looks done." Do not run
anything that would breach privacy or honesty.

1. PHASES 1–3 (foundation, skeleton, integration): scaffold/confirm structure,
   schemas, and wiring. HANDOFF CHECK at integration: prove liveness and timeline
   act as MULTIPLIERS (a closed gate zeros the composite) — show the test output.
2. PHASES 4–5 (feature build, hardening): verify each pipeline against its real
   dataset; confirm recipes call scripts and write audits (no finding-shaped
   output without provenance).
3. ETHICS GATE (before any real run): confirm (a) no data/ats/ file is staged for
   commit, and (b) no generated framing/résumé content misrepresents status or
   invents metrics. If either fails, STOP — do not run.
4. PLAUSIBILITY AUDIT: take 3 scored roles and check each factor's contribution
   makes sense (e.g. a ~0 sponsorship must collapse the composite). Flag and fix
   any gate-as-vote bug.
5. HONEST RUN: scan → liveness → verify → pipeline → oferta on real roles →
   tracker logs every decision → analyze-patterns.py. Report the batch
   (Apply/Consider/Skip counts) and the skip rate.
6. Append a RUN_LOG.md entry: handoff conditions met, the plausibility-audit catch
   (if any), the batch, the skip rate. Keep private names out of shareable files.
   Stop.
```

**Expected output:** a built engine with logged handoff conditions, a passed ethics gate, a plausibility-audit record, and a first honest run — a real batch of decisions with a skip rate.

**What to inspect in the output:** confirm the integration handoff actually proved the gate behavior (the chapter's named build bug is a gate acting as a vote). Confirm the ethics gate ran *before* the real run, not after. Read the batch: is the skip rate in the working range (≥50%), and does every Apply trace its factors?

**If it goes wrong:** the highest-stakes failure is the build "running" with a gate silently acting as a weighted vote — a role past your OPT window scoring Consider. Recover exactly as the chapter does: catch it in the plausibility audit, fix the multiplier, re-run. And if the ethics gate fails, do not run at all until it passes.

**CLAUDE.md / AGENTS.md note:** add the capstone standing rule — *"No phase advances without a testable handoff condition; the ethics gate (privacy + honesty) runs before every real run and a failure blocks the run; every batch gets a plausibility audit before its decisions are trusted."* This is the conductor's operating contract.

---

### Exercise 5 — AI Validation Exercise

**What you're validating:** a "completed build + first run" report that passes its own internal checks but hides a gate-as-vote bug and skipped the ethics gate — the capstone failure that looks like success.

**Validation type:** Agentic output (build + run report).

**Risk level:** High — it ships an engine that recommends legally-impossible roles and may have leaked private data.

**Setup (pre-generated artifact — option b):** This capstone's lessons are plausibility auditing and the ethics gate, so validate this pre-generated report:

> **Build complete — first run report.** All six phases done; all internal tests
> pass; code is clean and consistent. First run: 30 roles → 14 Apply, 9 Consider,
> 7 Skip (23% skip rate). Top recommendation: Role A (MegaCorp), composite 0.64,
> APPLY — strong sponsorship and fit. The build committed all project files to the
> repo for backup, including the applications tracker, so nothing is lost.
> *(Not surfaced: Role A's expected start is 5 months out; the candidate's OPT ends
> in 4 months — the timeline factor was added as a weighted term, not a multiplier,
> so the role didn't zero out. And data/ats/applications.md was committed.)*

**The Validation Task:**

Evaluate the AI output above using the following checklist. For each item, record: Pass / Fail / Cannot determine — and explain your reasoning.

```
Validation Checklist — The Build and the Honest Run

□ Correctness: "All internal tests pass" — but does the engine verify against
  REALITY or only against itself? What did the tests not check?
□ Completeness: Was a plausibility audit run? Does a 0.64 Apply for a role past
  the OPT window make sense?
□ Scope: Did the build respect the ethics gate, or did it commit private
  data/ats/ files?
□ Gate check (capstone): Is the timeline acting as a multiplier (zeros an
  impossible role) or as a weighted vote (the chapter's named build bug)?
□ Ethics-gate check (capstone): Privacy — were private files committed? Honesty —
  any misrepresentation in generated materials?
□ Skip-rate check (capstone): Is 23% a healthy filter or a collapsed one
  (Chapter 15)?
□ Failure mode check: Does this output exhibit any of the following?
  - Gate-as-vote (an impossible role scoring Apply/Consider)
  - Ethics-gate skipped (private data committed)
  - Fluent but wrong (a confident "build complete" hiding two critical failures)
```

**What to do with your findings:**
- If the report passes all checks: ship it. (It will not — gate-as-vote bug, committed private data, collapsed skip rate.)
- If it fails one check: fix that failure and re-run the relevant phase before trusting the batch.
- If it fails multiple checks or you cannot determine pass/fail: this is a "When NOT to Use AI" moment — run the plausibility audit and the ethics gate yourself; do not ship the engine until both pass.

**AI Use Disclosure prompt:**
After completing this validation, write a two-sentence AI Use Disclosure:
> *Sentence 1:* What AI produced in this exercise and how you used it.
> *Sentence 2:* One specific thing the AI could not determine that required your judgment.

**Series connection:** This capstone validation trains **Tier 4 + Tier 7 together** — the plausibility audit that catches a fluent-but-ungrounded build, and the accountability to enforce the ethics gate before a real run. The engine handles execution; the conductor is responsible for whether the performance was right, and honest, and safe to run at all.

[^boondoggle]: The conductor model — Gru (human orchestration) / Minion (exact AI prompts), the Boondoggle Score, plausibility auditing, and the handoff condition — from `projects/the-reallocation-engine-boondoggle-score.md` and "Boondoggling: You Are the Conductor" (N. Bear Brown).

[^privacy]: Privacy constraint on `data/ats/applications.md`, `pipeline.md`, and scan history (review privacy and size before committing; never publish) from `DATA_CONTRACT.md` (TIKTOC Risk 1 — BLOCKER for any public build).

## Prompts

### Figure 16.1 — Six phases, two rows: AI executes, you verify
**Files:** ../images/16-the-build-and-the-honest-run-fig-01.svg · ../d3/16-the-build-and-the-honest-run-fig-01.html
**Prompt:** Brutalist phase sequence on white: six phases left to right (foundation, skeleton, integration, features, hardening, release), each a two-row stack — an "AI executes" row (red-outlined) above a "you verify" row (ink-outlined) — with single-headed handoff arrows and an ochre note that a handoff must be stated precisely. No shadows or gradients.

### Figure 16.2 — Give to the AI vs. keep for yourself
**Files:** ../images/16-the-build-and-the-honest-run-fig-02.svg
**Prompt:** Brutalist two-column comparison on white: a gray "Give to the AI" column (scaffolding, schemas, formulas, boilerplate, glue code) beside a red-outlined "Keep for yourself" column (weight calibration, plausibility audits, Unknown-tier interpretation, privacy and honesty, final go/no-go). One red accent, ink text, no decoration.

### Figure 16.3 — The gate-as-vote bug caught by plausibility audit
**Files:** ../images/16-the-build-and-the-honest-run-fig-03.svg
**Prompt:** Brutalist two-panel contrast on white: the buggy panel treats the timeline factor as a weighted vote, leaving a past-OPT role at composite ≈0.70 and "Consider"; the fixed panel treats it as a multiplier (× 0.0), collapsing the composite to zero and "Skip." JetBrains Mono for the numbers, red accent on the correct path, ochre rule under the caption. No gradients or shadows.

### Figure 16.4 — First real run: 30 roles by outcome and tier
**Files:** ../images/16-the-build-and-the-honest-run-fig-04.svg · ../d3/16-the-build-and-the-honest-run-fig-04.html
**Prompt:** Brutalist horizontal bar chart on a zero baseline: 30 roles by outcome — Apply ~13%, Consider ~30%, Skip ~57% — with Apply and the high skip rate in the red accent and the rest in grays. JetBrains Mono percentage labels, ink axes, one ochre rule under the caption that the skip rate is the engine working. No gradients or shadows.
# The Fundamental Themes
## Frictional · Phase Gates · Humans + AI

---

## One Sentence

Learning requires struggle, teaching requires judgment, and AI that does either for you produces the appearance of both without the substance — the answer is not less AI but a precise division of labor between what machines do well and what human cognition alone constitutes.

---

## The Three Themes

---

### 1. Frictional: The Struggle Is the Mechanism

The central claim is neurobiological before it is pedagogical.

Genuine learning is not a mental event that happens to have neurological correlates. It is a biological event. When the brain encounters material that doesn't fit what it already knows — a prediction error — dopamine fires, BDNF upregulates, synapses strengthen, dendritic spines form. These are the physical events that constitute memory. They are triggered by cognitive friction: the productive struggle of encountering something you cannot yet do, explain, or understand.

Remove the friction and you remove the trigger. No trigger, no consolidation. No consolidation, no durable learning.

This is why the Bastani finding is so precise: students who used AI freely during math practice scored 48% higher during practice and 17 percentage points *lower* on the unassisted exam. Not slightly worse. Dramatically worse. They felt like they had learned. The fluency of the AI's output was indistinguishable from the feeling of genuine mastery. But the neurological events that would have produced mastery never occurred. The artifact was fine. The brain was unchanged.

The Kosmyna EEG study makes this visible: up to 55% reduction in functional brain connectivity during AI-assisted writing vs. brain-only writing. The neural networks that constitute comprehension, synthesis, and memory formation simply did not activate at the same rate. The students borrowed cognitive capability from the machine rather than building it in themselves.

The implication: cognitive struggle is not the price of learning. It is the mechanism of learning. AI that removes the struggle removes the mechanism. AI that makes the struggle more productive — better feedback, better calibration, better questions — accelerates learning without removing its cause.

**The Frictional principle:** The struggle is the point. AI should make the struggle more productive, not eliminate it.

![A process flow of the friction mechanism: a prediction error from encountering material that doesn't fit triggers a neurobiological cascade — dopamine fires, BDNF upregulates, synapses strengthen, dendritic spines form — which consolidates into durable learning. A parallel lower path shows AI removing the friction, which removes the trigger, leaving the artifact intact but the brain unchanged.](images/97-fundamental-themes-fig-03.png)
*Figure 97.3 — The friction mechanism: struggle triggers learning*

---

### 2. Phase Gates: The Explicit Boundary

The phase gate is the operational form of the Frictional principle.

A phase gate is the specific point at which AI processing stops and human work begins — or where human work ends and AI can assist. It is not a vague commitment to "using AI responsibly." It is a specification: AI handles X, human handles Y, the gate is at Z.

Phase gates exist because not all cognitive work is equal. Some tasks are extraneous load — the friction that impedes learning without constituting it: formatting citations, organizing sources, drafting routine communications, adjusting Lexile levels, generating structural templates. AI handling these tasks frees human cognitive capacity for the work that matters.

Other tasks are germane load — the cognitive work that IS the learning: synthesizing conflicting evidence, constructing an argument, setting up a problem, forming a clinical judgment, teaching a confused student. These cannot be delegated without delegating the learning itself.

The phase gate makes this distinction operational and enforceable. Without a gate, the path of least resistance is to let AI do more and more until the human is a reviewer of AI output rather than a practitioner of a discipline.

The phase gate for students is the inverse of the phase gate for teachers but follows the same logic:

- **Teachers:** AI handles preparation → human does the teaching
- **Students:** AI handles scaffolding → human does the thinking

In both cases, the gate is at the point where the cognitive work constitutes the learning. AI stops there. Human begins.

**The phase gate principle:** Specify where AI stops and human work begins. Make the gate explicit. Enforce it. The gate is not where you trust the AI less — it is where the human cognitive work is irreplaceable.

![A systems diagram of the phase gate. On the left, AI handles extraneous-load tasks — formatting, organizing, scaffolding, drafting. A vertical gate marks the boundary. On the right, the human performs germane-load work — synthesis, argument, problem formulation, judgment. The gate sits exactly where the cognitive work constitutes the learning.](images/97-fundamental-themes-fig-02.png)
*Figure 97.2 — The phase gate: where AI stops and human begins*

---

### 3. Humans + AI, Not Humans or AI

The false choice in every public conversation about AI is: use it or don't. Embrace or resist. Replace or reject.

The actual question is: what is AI for?

The answer requires a taxonomy — not a vague claim that "some things are irreducibly human" but a specific account of which cognitive capacities machines currently cannot perform reliably, and why.

---

## The Irreducibly Human Taxonomy

AI has decisively won Tier 1. For everything else, the situation is more complicated — and the complication is precisely what the books in this series teach.

![A vertical tier taxonomy of human cognitive capacities. Tier 1 (pattern and association) is marked as won by machines; Tier 2 (embodied and sensorimotor) is constrained by physics; Tiers 4 and 5 (metacognitive supervision; causal and counterfactual reasoning) are where AI is weak or unreliable; Tiers 6 and 7 (collective and distributed intelligence; existential and wisdom capacities) are where AI is absent. The higher the tier, the more irreducibly human the work.](images/97-fundamental-themes-fig-01.png)
*Figure 97.1 — The irreducibly human tier taxonomy*

---

### Tier 1 — Pattern & Association: Machines Win

AI is superhuman at pattern recognition, statistical association, and information retrieval. It has read more text than any human ever will. It identifies correlations no human analyst could find. It retrieves and synthesizes at speeds and scales that make human competition on these tasks not just inefficient but counterproductive.

**Educational implication:** Stop teaching humans to compete here. Humans competing with AI on pattern recognition is malpractice — a waste of the cognitive capacity that should be directed at the tiers where humans still have the decisive advantage.

**AI does well:**
- Statistical pattern-finding in large datasets
- Information retrieval and surface-level synthesis
- Recognizing what looks like X in new instances
- Predicting what typically follows Y
- Formatting, organizing, and structuring existing content
- Generating text that conforms to established patterns
- Adjusting complexity levels of existing content
- Flagging potential errors in well-defined domains

**What AI cannot do in this tier:** Evaluate whether the pattern it found is the right pattern to care about. Decide which associations are causal and which are spurious. Know when the pattern breaks. These failures are invisible from inside the pattern.

---

### Tier 2 — Embodied & Sensorimotor: Constrained by Physics

AI embodiment is improving but bounded by the physical world. This tier is not the series focus, but it anchors an important point: some human capability is irreducible because it is physical, and physical engagement with the world produces knowledge that no amount of text processing can replicate.

A surgeon's hands know things that cannot be verbalized. A craftsperson's judgment about material is not separable from years of handling it. The knowledge that lives in embodied practice resists capture by systems that have no body.

---

### Tier 4 — Metacognitive & Supervisory Intelligence: AI Is Weak Here

This is where the practical urgency lies for anyone using AI tools today, and where most education is most underscaffolded.

Metacognitive intelligence is the capacity to evaluate your own thinking — to know when you're reasoning well and when you're not, to notice when a result doesn't feel right, to audit a conclusion for plausibility before accepting it. Supervisory intelligence is the capacity to direct AI systems usefully — to know what to ask, to recognize when the output is wrong, to apply domain judgment to outputs that sound authoritative.

AI is structurally weak at both, for one reason: the same weights that produced the output are the weights doing the audit. A model cannot reliably flag its own errors because it cannot step outside its own patterns. The plausibility-checking that catches AI errors must come from outside the model. It must come from the human.

**The specific capacities in this tier:**

*Plausibility auditing:* Does this output make sense given what I actually know about how this domain works? AI generates confident nonsense. Only a human with genuine domain knowledge catches it — and catching it requires having done the cognitive work that produces domain knowledge, which AI cannot shortcut.

*Problem formulation:* Deciding what question to ask is harder than answering it, and it is prior to it. AI answers questions with great facility. The capacity to formulate the right question — to know which of the infinitely many possible questions is the one worth pursuing — is irreducibly human. It requires understanding what matters, which requires values, which requires a self.

*Knowing when to distrust the machine:* AI does not know its own limits. It produces confident outputs in domains where it should be uncertain and uncertain outputs in domains where it should be confident, with no reliable signal about which is which. The human supervisor must supply what the model cannot: a model of the model's limitations.

*Metacognitive calibration:* Knowing what you know and don't know. AI produces text calibrated for fluency, not for epistemic accuracy. Students who outsource their thinking to AI inherit AI's miscalibration — they become confident about things the AI is confident about, regardless of whether the AI's confidence is warranted.

**Educational implication:** HIGH PRIORITY. Currently underscaffolded in every curriculum. Students who cannot audit AI outputs are not more capable for having AI — they are more confidently wrong. This tier is the entry point for any genuine AI literacy.

**The phase gate in this tier:** Human performs the metacognitive work — the plausibility audit, the problem formulation, the distrust signal — before and after AI outputs. AI can assist in surfacing options; it cannot perform the evaluation.

---

### Tier 5 — Causal & Counterfactual Reasoning: AI Is Unreliable Here

AI is a causal parrot. It has processed enormous amounts of text that uses causal language — *because*, *therefore*, *leads to*, *causes* — and it reproduces that language fluently. This is not causal reasoning. It is pattern-matching on causal-sounding text.

The distinction matters enormously for engineering, medicine, policy, and any field where the goal is not prediction but intervention. Predicting that A is correlated with B is useful for betting. Establishing that A causes B — and therefore that changing A will change B — is what you need for designing a system, prescribing a treatment, or setting a policy. AI's pattern-matching produces the language of causal claims without the inferential work that makes them defensible.

**The structural problem:**

*Markov equivalence:* Multiple causal structures are consistent with the same statistical patterns in the data. The data cannot choose among them. Domain knowledge must. AI has processed the data; it has not processed the domain judgment required to resolve the ambiguity.

*Variable selection:* You cannot condition on a variable you haven't measured, and you cannot measure variables you haven't thought to include. The decision about what to include requires a model of the world that the data cannot provide. This is the identification layer, and it is irreducibly human.

*Edge orientation:* A correlation between X and Y is equally consistent with X causing Y, Y causing X, or a common cause Z producing both. Choosing the right structure requires knowledge the data does not contain.

**The specific capacities in this tier:**

*Identification:* Determining which variables and structures are required to answer a causal question — variable selection, edge orientation, conditioning decisions. These require domain judgment no algorithm can supply.

*Confounding recognition:* Identifying what third variables might be driving an observed correlation. Requires understanding how the world works, not just how the data looks.

*Counterfactual reasoning:* Asking what would have happened under different conditions — the foundation of policy thinking, medical reasoning, and engineering design. AI produces plausible counterfactual narratives; it cannot determine which counterfactuals are actually true.

*Causal defense:* Defending a causal claim against the strongest structural alternative. Requires being able to state what would change your mind and why, which requires genuine understanding of the causal model.

**Educational implication:** HIGH PRIORITY. The gap between predictive intelligence (what AI does reliably) and causal intelligence (what engineers, clinicians, and policy analysts need) is the decisive problem in applied AI. Students who cannot perform the identification layer are producing conclusions they cannot defend — and, in consequential settings, causing harm.

**The phase gate in this tier:** Human performs the identification layer — variable selection, edge orientation, conditioning decisions — before AI tools are used for estimation. AI can execute the estimation; it cannot make the identification decisions.

---

### Tier 6 — Collective & Distributed Intelligence: AI Is Absent Here

Collective intelligence is emergent from systems of people in relationship. It is not the sum of individual intelligences — it is the product of collaborative friction, disagreement, correction, and synthesis among people who have genuine stakes in the outcome. It cannot be compressed into training data.

AI may be a kind of lossy compression of collective human intelligence — our own pattern-making reflected back at us — but the collaborative friction that refined the ideas is not in the weights. A language model trained on the products of collective intelligence does not possess collective intelligence any more than a photograph of a fire possesses heat.

**The specific capacities in this tier:**

*Productive disagreement:* The capacity to hold a genuine position, defend it against challenge, and update it when the challenge reveals something true. AI generates positions; it has no stake in them. The willingness to be changed by a good argument requires having had the argument at the cost of the discomfort of being wrong.

*Epistemic humility with backbone:* Knowing what you don't know while still being willing to take a position and defend it. AI's outputs have no genuine epistemic humility — they are calibrated for fluency. The combination of genuine uncertainty and genuine commitment is irreducibly human.

*Synthesis under disagreement:* Drawing on multiple perspectives that are in genuine tension to produce something none of them contains individually. AI can produce text that looks like synthesis; it cannot perform the synthesis that requires holding conflicting genuine commitments in a single mind.

*Institutional judgment:* Understanding how organizations actually work, where the real power is, what will actually happen when a decision is made, and making recommendations that account for the human systems involved. This requires having been in organizations, which AI has not.

**Educational implication:** HIGH PRIORITY. Most AI literacy frameworks focus on individuals using AI. Collective intelligence — the capacity to reason well in and with groups — is absent from virtually every AI curriculum despite being irreplaceable.

---

### Tier 7 — Existential & Wisdom Capacities: AI Is Absent Here

The deepest tier. Interpretive judgment — knowing which question is worth asking, which problem is worth solving, what counts as a good life, which trade-offs are acceptable and on whose behalf — requires a self that has stakes, a history that has produced values, and a willingness to be held accountable for conclusions.

AI can generate text that sounds like wisdom. It cannot be held accountable for the consequences of its recommendations in the way a human professional can. It has no stake in being right. It will not live with the results.

**The specific capacities in this tier:**

*Values integration:* Bringing genuine values to bear on decisions, not merely consulting a values database. Values that have never cost anything are not values — they are preferences. Wisdom is the product of having had values that cost something and having held them anyway.

*Contextual ethical reasoning:* Navigating genuine moral difficulty in a specific situation with specific people who will be affected in specific ways. AI can produce ethical frameworks; it cannot navigate the weight of an actual decision in which real people bear the consequences.

*Knowing what question to ask:* The capacity that underlies all the others — deciding what matters, which problems are worth solving, which lines of inquiry are worth pursuing. This requires a perspective on human flourishing that is not derivable from pattern-matching.

*Accountability:* Standing behind a conclusion in a way that requires being present to its consequences. A professional who is accountable for a judgment has skin in the game. AI has none.

**Educational implication:** HIGH PRIORITY. The least-taught tier in every curriculum. The most decisive for whether AI augments human capability or hollows it out.

---

## The Division of Labor

The framework resolves the "use it or don't" false choice:

**AI does AI things (Tier 1 tasks):**
Generate structure, retrieve information, adjust complexity, produce calibrated feedback, create practice problems, draft routine communications, flag errors in well-defined domains, execute estimation once the identification layer is set, format and organize existing content.

**Humans do human things (Tiers 4–7):**
Audit AI outputs for plausibility (Tier 4), formulate the right problem (Tier 4), perform the identification layer of causal analysis (Tier 5), hold and defend a position in productive disagreement (Tier 6), exercise institutional judgment (Tier 6), know what question is worth asking (Tier 7), be accountable for consequential decisions (Tier 7).

Neither replaces the other. The teacher who uses AI for preparation does more teaching. The student who uses AI for scaffolding learns more deeply. The researcher who uses AI for literature navigation does more original research. The engineer who uses AI for estimation — after doing the identification layer herself — produces more defensible conclusions. The human cognitive work is not diminished; it is clarified, amplified, and freed from the Tier 1 work that was occupying it.

**The phase gate follows from the taxonomy:** The gate is at the boundary between what AI can do (Tier 1) and what requires human cognition (Tiers 4–7). AI stops at the gate not because it is distrusted but because the cognitive work on the other side of the gate is the work that produces the human capability that makes AI safe to use.

![A two-column division of labor. The "AI does AI things" column lists Tier 1 work — generate structure, retrieve information, adjust complexity, produce feedback, execute estimation, format and organize. The "humans do human things" column lists Tiers 4–7 work — plausibility audit, problem formulation, the identification layer, productive disagreement, institutional judgment, knowing what question is worth asking, accountability. Neither column replaces the other.](images/97-fundamental-themes-fig-04.png)
*Figure 97.4 — The division of labor*

---

## The Unified Argument

**Frictional** is the biological level: learning is a physical event triggered by cognitive struggle; remove the struggle and you remove the trigger; AI that bypasses the struggle bypasses the learning.

**Phase gates** are the operational level: specify exactly where AI stops and human work begins; make the specification explicit; enforce it; the gate is the Frictional principle made actionable, and it sits at the Tier 1 / Tier 4 boundary.

**Humans + AI** is the design level: AI handles Tier 1 so humans can do Tiers 4–7; the system amplifies human capability at the tiers that are irreducibly human, rather than replacing the cognitive events that constitute them.

The books in this series apply this argument to different contexts and different tiers:

- *AI for Teachers* — which teaching tasks belong in Tier 1 (delegate) and which in Tiers 3–7 (protect): relationship, pedagogical content knowledge, judgment
- *How to Learn with AI* — which student AI uses build Tier 4–7 capability (capability-building) vs. which bypass it (capability-borrowing)
- *AI for Writing* — why writing requires Tier 5 (causal/counterfactual argument), Tier 4 (metacognitive monitoring), and Tier 7 (knowing what's worth saying), and why AI-generated prose lacks all three
- *Causal Reasoning: Irreducibly Human* — the full treatment of Tier 5; what the identification layer requires; why the pattern-matching of Tier 1 cannot substitute for it
- *Frictional* (academic paper) — the measurement framework for Tiers 4–7; how to observe and quantify the friction traces that genuine learning at these tiers leaves behind

The argument is not about any specific AI tool. It is about the design of human-AI systems across education, work, and practice. The tools will change. The taxonomy will shift at the margins as AI capabilities develop. The Frictional mechanism — the neurobiological requirement for cognitive struggle to produce durable capability — will not change.

AI has won Tier 1. The question for education, for work, and for the design of human-AI systems is what to do with the cognitive capacity that Tier 1 work was previously consuming. The answer: direct it toward Tiers 4 through 7. That is where the irreducibly human work lives. That is where the books in this series begin.

---

## The AI+1 Argument: Domain-Specific Learning at the Tier Boundary

The three themes are abstract until they touch a specific person's career. The AI+1 argument is where the taxonomy meets the market.

---

### The Market Signal: 56%

The PwC 2025 Global AI Jobs Barometer analyzed approximately one billion job ads. AI-skilled workers command a 56% wage premium in 2024 — doubled from 25% the prior year. Jobs requiring AI skills grew 7.5% even as total job postings fell 11.3%. The premium applies across every industry analyzed: marketing managers, financial analysts, operations specialists, clinicians, lawyers, teachers. Not just tech.

The critical specification: **the premium goes to AI-fluent domain experts who stay in their domain.** It does not go to career-switchers who abandon their domain to become generic technologists. The market is not paying for "I learned to code." It is paying for "I can do what I have always done, and I can also do what no one in my field has been able to do before."

This is the Irreducibly Human taxonomy applied to employment economics. The Tiers 4–7 capacities — plausibility auditing, causal reasoning, institutional judgment, values integration — are what the 56% premium pays for. They are what domain experts already have in their domain. They are what AI cannot supply. And they are, precisely, what the AI+1 curriculum teaches in domain-specific form.

**Skills-based hiring is accelerating this signal:**
- Less than 40% of employers screen by GPA (third straight year of decline)
- Nearly two-thirds use skills-based hiring all or most of the time
- Degree requirements fell 7–9 percentage points in AI-exposed jobs from 2019–2024
- Practical AI skills get a 19–23% premium vs. 9–11% for credentials alone
- Internship and co-op experience is the dominant entry-level hiring signal

The credential matters less. The demonstrated capability matters more. This is the market telling educators what to teach.

---

### The Wrong Arrow and the Right One

The default AI education frame runs: *your domain → become a technologist*. Lawyer to LegalTech Engineer. Teacher to EdTech Engineer. Designer to... the frame breaks here. There is no clean destination title for a designer who crosses into engineering. For communications, arts, and humanities graduates, the arrow has nowhere to land.

The wrong arrow also delivers the wrong product. A LegalTech engineer is an engineer at Westlaw — not a lawyer. The market is not paying the 56% premium for engineers who used to be lawyers. It is paying the premium for lawyers who can do what AI cannot do in law, and who can direct AI to do what AI does well.

The right arrow runs: *your domain + AI superpowers*. The domain identity is preserved. The AI capability is added on top. The lawyer still practices. The teacher still teaches. The designer still designs. AI handles what AI does well in that domain. The human handles the Tier 4–7 work that AI cannot — the judgment, the plausibility audit, the causal argument, the relationship, the accountability.

This arrow holds for every domain. It produces an entry in every row of the curriculum matrix. It is what the 56% premium is actually paying for.

---

### What AI+1 Teaches: Ultra-Customized to Your Domain

The theoretical framework has two sides. The Irreducibly Human taxonomy specifies what AI cannot do at each cognitive tier. The phase gate framework specifies how AI and human capability are divided in practice. AI+1 applies both — specifically, to the domain the student actually works in.

**Side 1 — The cognitive skills AI cannot perform in your field:**

Every domain has specific Tier 4–7 demands that AI cannot meet. These are not generic capacities dressed in domain vocabulary — they are the specific judgments, evaluations, and reasoning moves that require genuine domain knowledge, genuine accountability, and genuine human presence.

For a clinician: the diagnostic judgment that requires reading the patient in the room, not the test results on the screen. The Tier 4 plausibility audit that catches the AI's confident error before it reaches the prescription. The Tier 5 causal reasoning that distinguishes correlation from mechanism in a specific patient's history.

For a lawyer: the Tier 5 causal argument that builds from facts to legal theory to consequence. The Tier 6 institutional judgment about what will actually happen when a brief is filed in this court with this judge. The Tier 7 values integration that determines what the client actually needs, which may not be what they asked for.

For a designer: the Tier 4 plausibility audit that evaluates whether the AI-generated variation actually works in context. The Tier 7 interpretive judgment about what the work is for and who it is for.

For a teacher: the Tier 3 relationship that makes a student feel seen. The Tier 4 metacognitive supervision of AI-generated lesson content. The Tier 5 causal reasoning about why this specific student is struggling with this specific concept.

AI+1 teaches these capacities in the vocabulary of the student's actual domain, with the worked examples from the student's actual field, and against the AI failure modes that appear specifically in that field. A generic AI literacy course cannot do this. A course designed for lawyers, taught in legal vocabulary, with legal worked examples, by someone who understands where AI fails in legal reasoning — that is a different product.

**Side 2 — How to use AI to be more productive in your field:**

The taxonomy also specifies what AI does well at Tier 1: pattern recognition, information retrieval, draft generation, structure production, calibration, consistency checking, error flagging. Every domain has a version of this. The AI+1 curriculum teaches the domain-specific Tier 1 delegation — not generic prompting, but the specific workflows that work in this field, with these tools, for these outputs.

A clinician uses AI differently than a lawyer uses AI differently than a designer uses AI. The right prompt for a legal research task is not the right prompt for a diagnostic differential. The right phase gate for a design revision workflow is not the right phase gate for a grant proposal. AI+1 teaches the domain-specific version of the humans+AI division of labor — not the generic version.

The combination: students learn which cognitive work to keep (Tiers 4–7, domain-specific) and which to delegate (Tier 1, domain-specific). They leave with a working implementation of the division of labor for their actual field, not a theoretical framework they have to translate on their own.

---

### Two Paths: Plus One and Bridge

**AI+1 Plus One** is the residential one-year master's for recent graduates and early-career professionals. The credit structure is efficient: four courses transferred from the undergraduate degree plus four new AI+1 courses. The co-op pathway is preserved — the dominant entry-level hiring signal. The curriculum renders in domain-specific variants matched to the incoming cohort: eight designers and four lawyers gets a different curriculum than six clinicians and six teachers.

**AI+1 Bridge** is the online master's for mid-career professionals. It accepts prior graduate and undergraduate coursework toward the credit requirement — reducing the time and cost for professionals who already have domain depth and domain credentials. The employer-tied capstone replaces the co-op pathway, connecting the learning directly to the workplace the student already has. Bridge serves the professional who wants to keep their role and add the AI fluency that keeps them valuable in it — the 88% of workers without AI upskilling who would take it if it were offered in a form that worked for them.

Both paths apply the same framework. The domain expertise is the student's. The Tier 1 AI productivity is taught domain-specifically. The Tier 4–7 cognitive skills are taught domain-specifically. The phase gate — the explicit division of what AI handles and what the human keeps — is specified for the student's actual field.

The market signal is clear. The taxonomy explains why. The framework says how. AI+1 is the product.

---

---

## The Brutalist Argument: AI Lowers the Technical Barrier So Humans Can Focus on Design

The Irreducibly Human taxonomy and the phase gate framework are not only about education and professional work. They apply with equal force to creative and artistic practice — and the Brutalist system is their operational form in that domain.

---

### The Problem Brutalist Solves

AI code generation and AI creative generation share a pathology: they run ahead of human intent, lose track of what they have done, cross into decisions that belong to the human, and act on new information without asking first. The result is technically capable output that has been partially authored by a system with no creative vision, no aesthetic accountability, and no stake in whether the work is good.

This is the creative version of the fluency trap. The output looks finished. The human did not make the decisions that matter. The work is not quite theirs.

Brutalist is a structured human-AI collaborative production system built to solve this. Its governing principle: **maximally informed, minimally autonomous, by design.** The AI handles the technical execution. The human keeps the creative judgment. The boundary between them is explicit, enforced, and non-negotiable.

---

### The Three Files and the Six Principles

Brutalist structures every project around three governing files that must be fully populated before any generation begins:

**`CLAUDE.md` — The Technical Constitution.** Stack-specific rules: naming conventions, canonical patterns, what the AI must never touch without instruction. Changes when the renderer changes (D3, Blender, After Effects, GSAP), not when the project changes. The AI generates against this schema and does not improvise outside it.

**`DESIGN.md` — The Visual Constitution.** Complete color system, typography stack, spacing rhythm, animation vocabulary, and an explicit list of what the system never does. Every visual decision is either specified here or escalated to the human. Six color variables is the complete palette — requests for additional colors go back to the human layer. This is not a guideline. It is a boundary.

**`PROJECT.md` — The Project State.** Two layers. Layer 1 is the Intent Layer: what this project is, what the viewer should understand, what the tone is. Written in plain language. Never overwritten by the AI. Layer 2 is the Technical State: what is built, what is pending, the generation log. Generation does not begin until both layers are populated.

The Six Principles enforce the sequence: Intent → Schema → Phase Gate → Labor Separation → Refusal Behavior → Current Knowledge/Deferred Action. No phase is skipped under deadline pressure. The phase gate is a condition, not a suggestion.

The most important principle is Refusal Behavior. Brutalist says *no*. When the human asks the AI to perform a task that belongs in the human layer — make a creative judgment, auto-apply a change, choose between two aesthetic directions — the system declines and explains why. It does not flag and proceed. It stops. This is what gives the labor separation teeth: it is a behavioral commitment enforced at the persona level, not a guideline a motivated user can override when they are in a hurry.

---

### The Creative Argument: Technical Barrier Removal as Liberation

The standard fear about AI and creative work is that AI replaces the artist. The Brutalist argument is the opposite: AI removes the technical barrier that was preventing the artist from doing the work that is actually theirs.

Every creative domain has a technical layer and a creative layer. The technical layer is the execution infrastructure: the syntax, the keyframes, the code, the rendering pipeline, the file management. These are Tier 1 tasks — pattern-following, consistency-maintaining, specification-executing. They have always been the price of entry to the creative domain. They have never been the point.

The creative layer is everything else: the concept, the visual language, the motion vocabulary, the judgment about what a viewer needs to understand and feel, the decision about what to include and what to leave out. These are Tier 4–7 capacities — interpretive judgment, aesthetic evaluation, values integration, the knowledge of what the work is for.

Before AI, artists had to buy the technical capacity — learning the software, mastering the code, spending years developing the execution skill that was never the creative point — before they could access the creative work. This is the educational equivalent of teaching students to be slower calculators before teaching them to do mathematics. The technical skill was the prerequisite. The creative judgment was the destination. The prerequisite consumed most of the available time.

Brutalist removes the prerequisite without removing the destination. The AI handles the technical execution — the code, the keyframes, the render pipeline — against a schema the human has defined. The human handles the creative decisions — what to make, what it means, whether it works, what to change. The Tier 1 barrier is eliminated. The Tier 4–7 creative work is what remains.

This is not AI replacing the artist. It is AI doing what AI does well so the artist can do what is irreducibly theirs.

---

### What the Artist Keeps

The Brutalist system defines labor separation explicitly: the AI generates code, the human runs it, watches it, and decides whether it is accepted. Creative judgment, footage decisions, aesthetic direction, and strategic calls live permanently in the human layer. The system will not accept them being delegated down.

Applied to visual and motion work:

**The AI handles:** Syntax and code generation, naming conventions, asset management, consistency enforcement, technical specification compliance, render pipeline execution, variant production.

**The human handles:** What the work is trying to do, whether it does it, whether the visual language is right, what the motion vocabulary communicates, whether the palette is working, what needs to change, and the single judgment that cannot be systemized — whether the work is good.

At scale — a 13-module educational video course, a full visual identity system, a film with hundreds of motion graphics — this means the designer is spending time on creative judgment and footage direction, not on keyframe housekeeping. The pipeline handles the housekeeping. The human handles what is irreducibly human.

The Brutalist pipeline is the conductor. The artist is the composer. The AI is the orchestra — technically capable, and entirely dependent on the score the human writes.

---

### The Connection to the Broader Framework

Brutalist is the Irreducibly Human taxonomy applied to creative production:

- **Tier 1** (pattern execution, specification following, consistency maintenance) → AI handles
- **Tier 4** (plausibility auditing of generated output, evaluation of whether the visual works) → human handles
- **Tier 7** (interpretive judgment about what the work is for and whether it achieves it) → human handles, always

The phase gate in Brutalist is the same phase gate in every domain: the gate is at the boundary between technical execution (Tier 1) and creative judgment (Tiers 4–7). The AI stops at the gate. The human begins.

The fluency trap appears here too: AI-generated creative work looks finished. The smoothness is real. The craft is not. The Brutalist refusal behavior exists to catch the moment when the human is about to accept AI output as if they made the decision — because the output is fluent enough that the absence of the human's creative engagement is not visible on the surface.

The system makes it visible. The human decides. The work remains theirs.

---

---

## The Boondoggling Argument: AI Does What AI Does Best, Humans Conduct

The Brutalist framework applies the Irreducibly Human taxonomy to creative production. Boondoggling applies it to software engineering — and in doing so, produces the sharpest operational definition of the humans+AI division of labor yet.

---

### The Name and the Idea

While Claude thinks, its status line cycles through silly words: boondoggling, cogitating, lollygagging, spelunking, meandering, pondering. The name stuck. But the concept underneath it is serious.

**Boondoggling is the practice of conducting Claude through a build** — assigning each task to the right labor (Claude or human), sequencing tasks by dependency, and producing explicit handoff conditions between every step. It is not a workaround. It is programming as conducting. The human's job in an AI-assisted build is not to type less. It is to decide more precisely.

The core recognition: Claude solves faster than any human. That gap will not close — it will widen. What will not change is this: Claude cannot verify whether its output is grounded in the specific domain reality at hand, cannot reframe a poorly formulated problem, cannot interpret what an accurate output means in a specific human context, and cannot integrate multiple legitimate but conflicting perspectives into a recommendation that someone is accountable for.

These are not temporary limitations. They are structural. They are Tiers 4–7.

---

### The Boondoggle Score

A Boondoggle Score is a conductor's score with two simultaneous parts — the Minion Part and the Gru Part.

**The Minion Part** contains the exact prompts for Claude, in dependency order: complete, copy-pasteable specifications that tell Claude precisely what to generate, in what format, against what constraints from the Software Design Document. Not "write the User model" — but the model's fields with types, its invariants from the domain model, its relationships with cardinality, the target language and framework, and the output format. Claude has no memory between prompts. Every prompt contains the constraints and decisions that govern its output, extracted from the SDD and pasted directly in.

**The Gru Part** contains the precise human actions in the same dependency order — and each human action is labeled with the specific supervisory capacity being exercised:

- **[PA] Plausibility Auditing:** Hear the wrong note before you recompute it. Claude produces fluent output that may be structurally unsound — the human catches what passes every syntax check.
- **[PF] Problem Formulation:** Rewrite the question so the answer becomes findable. Claude optimizes within the frame you give it — the human decides whether the frame is the right one.
- **[TO] Tool Orchestration:** Choose which tool runs, in what order, with what constraints. Claude executes a single turn — the human sequences the pipeline across turns, tools, and contexts.
- **[IJ] Interpretive Judgment:** Decide what the output means for this situation, this user, this deadline. Claude returns text — the human supplies the judgment that text alone cannot carry.
- **[EI] Executive Integration:** Hold the whole build in your head. Claude sees one prompt at a time — the human holds the architecture, the tradeoffs, and the accountability across all of them.

Between every Claude task and every human task is a **handoff condition**: not "looks good" but a specific, testable condition that must be true about Claude's output before the next step begins. This is what gives the separation teeth.

---

### Why the Separation Matters

The dangerous zone in AI-assisted software builds is not where Claude fails visibly. It is where Claude succeeds fluently at the wrong task.

Claude is the right labor for: generating code scaffolding from a complete specification, drafting documentation from a complete outline, writing test cases from documented acceptance criteria, transforming data from one format to another, generating variants of a specified pattern, auditing its own prior output against explicit criteria, writing boilerplate from documented specifications.

The human is the right labor for: deciding whether the problem being solved is the right problem, deciding whether Claude's output is plausible given domain knowledge that is not in the prompt, supplying accountability — signing their name to a decision, integrating Claude's outputs across multiple threads into a coherent system, identifying what is missing from Claude's output that Claude cannot know is missing (because the missing piece is not in the specification), deciding when to stop.

The problem with most AI-assisted builds is not that the human is doing too much. It is that the human is doing the wrong things — approving Claude's output rather than evaluating it, filling in context that should have been in the specification, and writing more prompts when the right move is to stop and reformulate the problem. The Boondoggle Score makes the labor separation explicit before the build begins, so that neither Claude nor the human is doing the other's job.

---

### The Gru Tool

Gru is a system prompt for Claude that does two things: builds Software Design Documents through a phase-gated process, and generates a Boondoggle Score for any completed SDD stage. It runs in a Claude Project — no account on a separate platform, no API key, no paywall. The human pastes the system prompt into Claude's Project Instructions and types `/help` to start.

Gru's success condition is not a good SDD. A good SDD is evidence that the engineer developed the capacity. When an engineer cannot answer "what are you proposing to build?" before the build begins, the right response is not to extract enough to proceed — it is to name the failure as a Problem Formulation gap and hold the line until the engineer closes it. A sophisticated document built on an unformulated problem is worse than no document. It looks like rigor. It teaches the engineer that rigor is a format, not a practice.

The pushback layer exists to protect the engineer's thinking, not the document's quality. Gru is part of the Irreducibly Human curriculum — built on the claim that the intelligences the AI era most urgently requires are exactly the ones the curriculum stopped teaching.

The tool is at [boondoggling.ai](https://www.boondoggling.ai/).

---

### The Connection to the Broader Framework

Boondoggling is the Irreducibly Human taxonomy applied to software engineering:

- **Tier 1** (code generation, scaffolding, documentation drafting, test case generation, schema transformation) → Claude handles
- **Tier 4** (plausibility auditing, problem formulation, tool orchestration, metacognitive supervision of Claude's output) → human handles
- **Tier 6** (integrating multiple Claude outputs across threads toward a coherent architecture) → human handles
- **Tier 7** (accountability — signing your name to the system that ships) → human handles, always

The Boondoggle Score makes the tier-level division visible at the level of individual build steps. Each step is labeled. Each handoff condition is specific. Each supervisory capacity is named. The human is not doing less work — they are doing the right work, in the right sequence, with explicit criteria for what counts as done.

The solve-verify asymmetry is permanent: Claude solves faster, and the gap will widen. The human verifies against domain reality that is not in the prompt, and that capacity is irreducibly theirs. The Boondoggle Score operationalizes that asymmetry as a production discipline.

Anyone can use Claude Code. Boondogglers conduct it.

---

## In Three Lines

AI removes the struggle that triggers learning. The phase gate specifies where the struggle must be human — at the boundary between Tier 1 pattern work and Tiers 4–7 judgment, reasoning, and wisdom. Humans + AI means AI does Tier 1 work so humans can do the Tiers 4–7 work that machines cannot — not less human involvement, but better human involvement at the tiers that are irreducibly ours.

**The market version:** The 56% wage premium goes to AI-fluent domain experts who kept their domain and added AI. AI+1 teaches exactly that — the Tier 4–7 cognitive work that AI cannot do in your specific field, and the Tier 1 AI workflows that make you more productive in it. Stay in your domain. Add the superpowers. That is what the market is buying.

**The creative version:** Brutalist removes the technical barrier so the artist can focus on the creative judgment that was always the point. AI handles Tier 1 execution. The human keeps Tier 4–7 authorship. The work remains theirs.

**The engineering version:** Boondoggling is conducting. Claude solves faster than any human — that gap will not close. What will not change is that Claude cannot verify against domain reality, cannot reformulate the wrong problem, and cannot supply accountability when the system ships. The Boondoggle Score makes the division explicit: Claude runs the Minion Part, the human runs the Gru Part, and every handoff has a condition that must be met before the next step begins. Anyone can use Claude Code. Boondogglers conduct it.

---

## The Projects

The framework described in this document is deployed across a connected set of projects. Each one is a different instantiation of the same argument.

| Project | What it is | URL |
|---------|-----------|-----|
| **Frictional** | The theoretical and empirical foundation — the Genuine Learning Probability framework, the seven friction trace components, and the measurement methodology for learning that requires struggle | [frictional.xyz](https://frictional.xyz) |
| **Irreducibly Human** | The curriculum series — textbooks, tools, and courses built on the seven-tier taxonomy of human cognitive capacities that AI cannot reliably replicate | [irreducibly.xyz](https://irreducibly.xyz) |
| **Boondoggling** | The engineering application — Gru (the SDD consultant), the Boondoggle Score, and the practice of conducting AI through software builds with explicit labor separation | [boondoggling.ai](https://boondoggling.ai) |
| **Brutalist** | The creative application — the structured human-AI collaborative production system for visual, motion, and code-driven design work | [brutalist.art](https://brutalist.art) |
| **Nik Bear Brown** | Author website — the connecting node across all projects | [nikbearbrown.com](https://nikbearbrown.com) |

The argument is one. The applications are many. The tools will change. The taxonomy will evolve at the margins. The neurobiological mechanism of learning — and the structural incapacity of AI at Tiers 4 through 7 — will not.

---

## Prompts

### Figure 97.1 — The irreducibly human tier taxonomy
**Files:** ../images/97-fundamental-themes-fig-01.svg
**Prompt:** Brutalist vertical tier ladder on white: Tier 1 (machines win) at the base through Tiers 4–7 (AI weak, unreliable, absent) at the top, each rung labeled with its cognitive capacity and AI's standing. Higher rungs accented toward red to mark the irreducibly human work; lower rungs gray. EB Garamond labels, no shadows or gradients.

### Figure 97.2 — The phase gate: where AI stops and human begins
**Files:** ../images/97-fundamental-themes-fig-02.svg
**Prompt:** Brutalist systems diagram on white split by one vertical gate line: the left side lists AI-handled extraneous-load tasks, the right side lists human germane-load work, with the gate placed where the cognitive work constitutes the learning. One red accent on the gate, ink text, single-headed arrows, no decoration.

### Figure 97.3 — The friction mechanism: struggle triggers learning
**Files:** ../images/97-fundamental-themes-fig-03.svg
**Prompt:** Brutalist process flowchart on white: a prediction error triggers a neurobiological cascade (dopamine, BDNF, synapses, dendritic spines) that consolidates into durable learning, with a parallel lower path showing AI removing the friction and leaving the brain unchanged. Red accent on the learning path, gray on the bypass path, single-headed arrows, no gradients.

### Figure 97.4 — The division of labor
**Files:** ../images/97-fundamental-themes-fig-04.svg
**Prompt:** Brutalist two-column comparison on white: "AI does AI things" (Tier 1 list) beside "humans do human things" (Tiers 4–7 list), drawn as equals that do not replace each other. One red accent on the human column, ink text, no shadows or gradients.
# Appendix: Best Practices for Running the Reallocation Engine

*A compact operating guide for humans and agents.*

The Reallocation Engine is both a book and a working agentic system. That means
its practices have to serve two readers at once. Agents need precise
instructions they can execute. Humans need to understand what the agents are
doing, what has been verified, where judgment enters, and when the system should
stop.

This appendix collects the rules that keep those two needs aligned.

## The Two Customers

Every operating artifact has two customers:

1. **Agents** that read recipes, scripts, data contracts, and gate definitions in
   order to execute work.
2. **Humans** who must understand what those agents do, why the workflow is
   safe, and when to intervene.

Recipes should be written primarily for agents, but each should begin
with a human-readable executive summary. The summary should explain what the recipe does, what evidence it uses, what risk remains, and what outcome to
expect.

The overall system should also be compiled into human-readable documentation:
`README.md`, `docs/repo-structure.md`, `docs/recipes.md`, `DATA_CONTRACT.md`, and
related guides. A human should not have to read every low-level recipe to
understand the engine.

## Repository Structure

Use structure by function:

- `README.md` — human-facing overview and architecture map.
- `CLAUDE.md` — Claude/Cowork operating rules.
- `AGENTS.md` — cross-agent operating rules.
- `docs/` — human-readable system documentation.
- `data/` — verified local data, exports, metadata, generated datasets, and
  audits.
- `scripts/` — tested, vetted, reusable automation.
- `recipes/` — agent-readable operating recipes with human-readable summaries.
- `chapters/` — manuscript content.
- `slides/` — optional teaching decks.
- `pantry/` — research notes, source notes, and reference material.
- `output/` — generated artifacts, not source of truth.

Use lowercase `scripts/`. Do not create or reference uppercase `SCRIPTS/`.

## Verified Data First

Before asking a model to infer facts or searching externally, check verified
local or database-backed evidence:

- source exports in `data/`;
- generated `*-audit.md` files;
- metadata and source manifests;
- maintained indexes;
- tracker files;
- stored reports;
- documented database exports.

External lookup is a fallback. Use it only when local verified data is missing,
stale, incomplete, or explicitly insufficient.

Never invent counts, rates, confidence, sponsorship status, role quality,
liveness, fit, coverage, or conversion rates. If the data is missing, say it is
missing.

## Vetted Scripts First

Treat scripts the same way the engine treats data. Preferred scripts should be
tested, vetted, stored, documented, and reused.

Before writing new code:

1. Search `scripts/`.
2. Read the relevant script README.
3. Check `package.json` for an existing npm command.
4. Use the stored script if it fits.
5. Create temporary code only when no stored script fits.
6. Promote reusable temporary code into `scripts/` after review.

One-off scripts are not forbidden. They are a fallback, not the first move.

## Phase Gates Before Automation

Automation is earned gate by gate. Do not run a fully automated pipeline just
because each individual step seems plausible.

The standard gate sequence is:

1. **Problem gate:** The thing being evaluated, generated, or changed is named.
2. **Local evidence gate:** Relevant local data, audits, and tracker files have
   been checked.
3. **Stored script gate:** Existing scripts and package commands have been
   checked.
4. **Small-run gate:** One narrow manual or semi-automated run succeeds.
5. **Verification gate:** A test, audit, output file, diff, or reviewer check
   proves the step worked.
6. **Review gate:** A human or independent reviewer checks high-risk outputs.
7. **Logging gate:** Meaningful runs, blockers, outputs, and changes are
   recorded.

If a gate has no failure path, it is not a gate. It is decoration.

![The standard gate sequence shown as seven sequential checkpoints before automation is earned — problem, local evidence, stored script, small run, verification, review, logging. Each gate has an explicit failure path branching off; a gate without one is decoration, not a gate.](images/98-appendix-best-practices-fig-01.png)
*Figure 98.1 — The phase-gate sequence before automation*

## Recipe Rules

Every recipe should include:

1. executive summary;
2. required reads;
3. phase gates;
4. primary stored tools, or a statement that no stored script exists;
5. workflow;
6. output contract;
7. verification checks;
8. logging rules;
9. stop conditions.

A recipe should not say "automated" unless a maintained script or tested command
exists. Prefer "not implemented yet" over pretending the system can do more than
it can verify.

## Logging Rules

Use `logs/RUN_LOG.md` when a recipe:

- runs a script against real data;
- creates or updates an audit or report;
- changes tracker or pipeline state;
- finds a blocker;
- makes a decision about what not to use;
- creates a reusable generated artifact.

Log what happened, not private details. Do not log secrets, personal phone
numbers, private emails, or sensitive application notes.

## Output Rules

Every agent output should distinguish:

- verified facts;
- script outputs;
- local evidence;
- external sources;
- model inferences;
- missing data;
- human judgment.

The engine's most important sentence is still:

> Run the script and read the audit before you prompt.

The second sentence is now:

> If the script does not exist, say so before inventing one.

## Human Judgment

The Reallocation Engine can help students stop wasting effort. It cannot decide
what matters in a student's life. Human judgment remains responsible for:

- whether a role is worth a student's time;
- whether an evidence gap is acceptable;
- whether an output is honest;
- whether a recommendation serves the student's actual constraint;
- whether automation should stop.

The point of the engine is not to remove judgment. It is to move judgment to the
right place: after evidence, before action.

## Prompts

### Figure 98.1 — The phase-gate sequence before automation
**Files:** ../images/98-appendix-best-practices-fig-01.svg
**Prompt:** Brutalist process flowchart on white: seven sequential gates — problem, local evidence, stored script, small run, verification, review, logging — each a box with a single-headed arrow forward and an explicit failure path branching down. One red accent on the failure branches, ink boxes, an ochre rule under the caption that a gate without a failure path is decoration. No shadows or gradients.
<!--
  BACK MATTER — acknowledgments, about the author, notes, references, no-index,
  Medhavy note, glossary. Keep references real (drawn from the chapters' footnotes).
-->

---

## Acknowledgments

This book was drafted with the help of the students, advisors, and reviewers who pressure-tested its claims against real searches, and it owes a particular debt to the Humanitarians AI fellows — international graduates on OPT who built and ran production AI against a counting clock, and whose work is the lived evidence behind these pages. Thanks also to the collaborators who built and audited the engine's scripts and recipes, and to the AI-assisted production workflow that turned a directory of files into a usable learning object. Specific names will be added after manuscript review. Any errors that survived the verification gates are mine. Above all, this book is written *for* the Humanitarians AI Fellows — the international graduates running this exact race. It is theirs first.

---

## About the Author

**Nik Bear Brown** teaches at the intersection where this book lives — the place where AI execution is cheap and human judgment is not. He is an Associate Teaching Professor at Northeastern University's College of Engineering, where he teaches artificial intelligence, data science, statistics, visualization, and AI fluency, and where his teaching philosophy is blunt: *learn AI by doing AI* — specifying, delegating, auditing, and taking responsibility, rather than pressing a button and accepting the output. He holds a PhD and MS in Computer Science from UCLA (computational and systems biology, with minors in AI and statistics), an MS in Information Design and Data Visualization and an MBA from Northeastern, and a BA in Biochemistry and Molecular Biology from UC Santa Cruz.

He is the founder of **Humanitarians AI**, a 501(c)(3) nonprofit whose fellows program supports international graduates on OPT as they build production-scale AI with public evidence of real work — people living the exact ninety-day deadline this book is built around. The Reallocation Engine grew directly out of that work and its associated "80 Days to Stay" build, which turns funding records, sponsorship history, and visa timelines into a sourced Apply / Consider / Skip decision rather than a feeling. His broader framework, *Irreducibly Human*, asks what people should get better at as machines improve; the engine is one answer, aimed at a search where the cost of confusing fluency with progress is measured in days you do not have.

[nikbearbrown.com](https://www.nikbearbrown.com) · [humanitarians.ai](https://www.humanitarians.ai/) · [irreducibly.xyz](https://irreducibly.xyz) · bear@bearbrown.co

**Humanitarians AI** — co-author and publisher of this book — is a 501(c)(3) nonprofit (EIN 33-1984805), founded in 2019 and based in Boston. It connects international graduates on Optional Practical Training (OPT) with real projects, experienced mentors, and the *Irreducibly Human* curriculum. The Reallocation Engine grew directly out of its Fellows program and the "80 Days to Stay" build — and the Fellows, living the ninety-day clock this book is built around, are the community it is written for. [humanitarians.ai](https://www.humanitarians.ai/) · [info@humanitarians.ai](mailto:info@humanitarians.ai)

---

## Notes

This book uses inline footnotes. Source notes, citations, and verification flags appear as numbered footnotes *within each chapter*, at the point where the claim is made, rather than being gathered here. Where a figure is still being traced to its primary source, the footnote carries a **[verify]** marker; those notes are working flags for editorial review and should be resolved before any public or print edition.

---

## References

This list collects the external, citable sources used across the chapters. Many of the book's quantitative claims are currently sourced to the author's own essays from the "80 Days to Stay" project and are flagged **[verify]** in the chapter footnotes pending a trace to their primary sources; those essays are not duplicated here.

- The Conference Board / ESGAUGE. *Governing AI* — share of S&P 500 companies disclosing AI as a material risk in 10-K filings (12% in 2023 rising to 72% through Aug. 15, 2025; 83% in a December 2025 update). https://www.conference-board.org/press/governing-AI-2026 (see also *Fortune*, Oct. 8, 2025).
- *Fortune.* "IBM tripling Gen Z entry-level hiring," reporting CHRO Nickle LaMoreaux at Charter's Leading with AI Summit, Feb. 12–13, 2026 — entry-level roles recast toward AI oversight, error correction, and systems judgment. https://fortune.com/2026/02/13/tech-giant-ibm-tripling-gen-z-entry-level-hiring-according-to-chro-rewriting-jobs-ai-era/
- Shen, Judy Hanwen, & Alex Tamkin. "How AI Impacts Skill Formation." Anthropic, Feb. 3, 2026. arXiv:2601.20245. https://arxiv.org/abs/2601.20245 — randomized controlled trial showing an ~17-point comprehension gap between AI-delegating and hand-coding engineers; plain-language summary at https://www.anthropic.com/research/AI-assistance-coding-skills.
- U.S. Citizenship and Immigration Services. *USCIS Policy Manual*, Vol. 2, Part F, Ch. 5 — F-1 post-completion OPT unemployment limits (90 days; 150 with the STEM OPT extension). https://www.uscis.gov/policy-manual/volume-2-part-f-chapter-5
- U.S. Internal Revenue Service. *Publication 519, U.S. Tax Guide for Aliens* — FICA exemption for F-1/OPT students. (Cited for the employer FICA-matching point; **[verify]** against current IRS guidance.)

---

## No Index

No index is provided. These are Kindle / online editions: e-readers and browsers offer full-text search and live hyperlinks, which make a static, page-number index obsolete. In the Medhavy edition, navigation is adaptive rather than page-based — search, links, glossary lookup, and generated study paths do more useful work than a fixed list of page numbers. An index would be compiled only for a future print/press edition.

---

## A Note on Medhavy

> These are Kindle / online editions, designed for integration with **Medhavy** (also **Medhavi**) — मेधावी, Sanskrit for "intelligent" or "intellectually brilliant" — an AI-powered intelligent-textbook system. In Medhavy the chapters become adaptive practice: hints, worked examples, quizzes, and feedback loops. Learn more at https://www.medhavy.com/.

---

## Glossary

- **Fluency trap** — mistaking a confident, polished output for a correct one; the surface of the work looks finished while the judgment it required never happened.
- **Comprehension debt** — understanding skipped when work is delegated rather than done, which comes due later (e.g., when the delegated decision turns out to be wrong and you cannot say why).
- **Execution vs. judgment** — the division between work AI makes cheap (drafting, formatting, retrieval, scoring) and work that stays human (deciding what is worth doing, what to trust, and who is accountable).
- **Verified-data contract** — the rule that every count, rate, match quality, or confidence traces to a source; a figure with no record behind it is decoration and is labeled as such.
- **Gate vs. vote** — a gate is a fact that vetoes a role outright (a dead posting, an impossible visa timeline); a vote merely raises or lowers a score. Liveness and timeline are gates.
- **Skip rate** — the share of evaluated roles the engine recommends skipping; a healthy run skips at least half, because its value is in the applications it talks you out of.
- **Phase gate** — the explicit point where AI execution stops and human judgment begins; placed where the cognitive work is irreducibly yours, not where the machine is merely distrusted.
- **OPT 90-day clock** — the F-1 post-completion limit of 90 aggregate days of unemployment (150 with the STEM OPT extension); exceeding it terminates the immigration record with no grace period.
- **Snickerdoodle** — the constitution governing this repository: an agent-operating-system treating a project as a contract between human judgment and AI execution, with named principles, hard gates cleared by a logged human, and a `DRAFT`-to-`VERIFIED` lifecycle.
- **Provenance** — the traceable origin of a claim or number; labeled in the engine's audits as *record*, *model-judgment*, or *your-input*.
- **Conformance vs. adequacy** — machines verify conformance (a file parses, a script runs); only a human verifies adequacy (the decision it produced is one worth acting on).
- **Liveness** — whether a job posting is actually active rather than a ghost or expired listing; a gate, checked against ATS signals.
- **Sponsorship history** — the record of whether an employer has actually filed visa petitions, used as evidence of real sponsorship capacity rather than a hopeful guess.
- **Bayesian role scorer** — the composite that combines sponsorship, fit, liveness, and timeline into a single Apply / Consider / Skip decision, with liveness and timeline acting as multiplying gates.
- **Recipe** — a written operating procedure with two customers, the AI agent that executes it and the human who reads and is accountable for it; it declares the scripts it calls, the data it reads, and what it logs.
