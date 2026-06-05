# Chapter 10 — The Visa Timeline Manager
*The clock is a gate, not a tiebreaker.*

Here is a thing that happens, and it is quietly devastating when it does. A student has three months of work authorization left. They find a role that fits almost perfectly — the company sponsors, the posting is live, the occupation matches, the quality signals are strong. They apply. They make it through the screens, the take-homes, the panels. Four months later, an offer arrives. And it is worthless. The start date is past the day their authorization ended. They spent the scarcest months of their search — the months they had the least of — chasing an offer that the calendar had already ruled out before the first email went out.

No filter in Chapters 7 through 7 would have caught this. Sponsorship was real. The role was live. The quality was high. The thing that killed it was time, and time is the one constraint that is *yours specifically* — invisible to the company, invisible to every scorer that does not know your dates.

<!-- → [DIAGRAM: a horizontal timeline showing: "Student applies" → "Phone screen" → "Technical rounds" → "Panel interview" → "Offer" — with a vertical red line labeled "Authorization ends" falling between "Technical rounds" and "Offer"; the visual makes visceral that everything after the red line is unreachable regardless of how good the news is] -->

What I want to sit with before we go further is the structure of this error. The student did not miscalculate. They did not misread a sponsorship tier. They made a decision that was perfectly rational given incomplete information: they applied to a high-quality role without first asking whether the calendar permitted it. The Visa Timeline Manager exists to make that omission impossible — to force the calendar question to the front, before the excitement of a good-looking posting makes it easy to postpone.

---

Three windows govern an international student's runway, and the way they interact is not obvious until you map them.

The first is **OPT** — post-completion Optional Practical Training. After you finish your degree, you have a window of authorized work, and inside that window you may accrue no more than 90 cumulative calendar days of unemployment.[^opt] That ceiling is not a soft guideline. Exceeding it terminates your status, with no grace period. The 90 days do not reset. They accumulate from the first day your OPT begins. Every day you are not employed or not in a valid application process counts against that ceiling whether you notice it or not.

The second is the **STEM OPT extension**. If your degree is in a qualifying STEM field, you are eligible for a 24-month extension beyond the standard OPT period — and critically, the unemployment ceiling rises to 150 days aggregate. Eligibility changes the math entirely. A student without STEM eligibility and four months of authorization has a fundamentally different runway than a STEM-eligible student with four months remaining and the extension not yet filed. The calendar says they are in the same situation. The law says they are not.

The third is the **H-1B lottery window** — the annual cycle of registration, selection, and petition that determines whether a path past OPT exists with a given employer in a given year. The lottery runs on a fixed annual schedule. If your authorization expires before the next window resolves, the H-1B path is not available to you regardless of how willing the employer is to sponsor. Sponsorship and the ability to act on sponsorship are different things, and the lottery timing is what separates them.

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

<!-- → [TABLE: three-column table showing: input parameter | what it measures | consequence of error — rows for auth_end_date, unemployment_days_used, expected_time_to_start, and stem_eligible; the "consequence of error" column makes visible that each input has asymmetric costs: being too optimistic costs the whole search, being too conservative costs one opportunity] -->

The factor resolves into three cases. A **factor of 0** means the role is skip-regardless: the expected time-to-start exceeds your remaining authorization, and no other signal changes that. A **factor near 1** means comfortable buffer — the expected hiring timeline finishes well inside your authorization with room to spare. A **factor between 0 and 1** is where most of the interesting cases live: buffer-based scaling, where as the expected start date creeps toward the cliff, the factor falls — gently penalizing roles that are probably fine but cut it close, so that all else equal the engine prefers the role you can safely land.

---

Let me walk through three roles for a single student to show how these cases feel in practice.

The student is a STEM-eligible master's graduate. OPT ends in roughly five months. Twenty-two unemployment days already used. Self-imposed target: an 80-day buffer below the 90-day ceiling, which functions as a margin of safety — not a legal threshold, just a planning discipline built into the engine.

**Role A** is a large firm. Its hiring process historically runs about five months: multiple rounds, committee review, compensation negotiation, offer processing. The expected start date lands past the authorization end. Factor = 0. Skip regardless — and the reason it deserves that label, not just "low priority," is that applying does not just waste time. It consumes unemployment days while you wait, which erodes the buffer you need for the roles you *can* land.

**Role B** is a startup that can move in about six weeks when motivated. Expected start lands with months of buffer. Factor ≈ 1. No timeline objection — the other factors decide.

**Role C** is a mid-size firm, roughly twelve-week process. Expected start lands inside authorization but eats most of the buffer. Factor ≈ 0.6 — kept, but penalized relative to B. If Role C and Role B were otherwise equal, the engine prefers B, because the candidate who lands B does not spend the last weeks of their authorization anxiously waiting for Role C's offer.

<!-- → [CHART: a horizontal bar chart showing the three roles with their expected start dates plotted against the student's authorization end date — Role A's bar extends past the end date (red), Role B finishes well short (green), Role C finishes just inside (yellow); a vertical dotted line marks the 80-day buffer target] -->

The decision rule that follows from this is simple to state and genuinely hard to execute: drop Role A *now*, before you invest more time in it. Free those weeks for Role B and for the networking that surfaces roles like Role B. Keep Role C with eyes open. The hard part is executing the drop on a role that looks excellent in every other dimension. The factor is designed to make that drop automatic — not a judgment call you have to make while excited about a good-looking posting, but a mathematical output you read before the excitement has a chance to override the calendar.

---

Now let me tell you what this factor cannot do, because the honest limits of any tool are part of using it correctly.

The factor knows your dates and a company's typical pace. It does not know that this particular hiring manager will fast-track you because their team is on fire, collapsing a five-month process to three weeks. It does not know that you would be willing to accept a role in a different country if the U.S. clock runs out, which would change what "skip" means for you entirely. And it absolutely cannot practice immigration law.

The difference between eligible and ineligible for a STEM extension can hinge on a detail — the CIP code on your transcript, a filing timing question, a program classification — that only an immigration professional should rule on. The factor gates out the impossible. The negotiable edges and the legal specifics stay human. This is not a caveat to be skim-read; it is load-bearing. A student who treats a factor of 0.4 as authorization to apply to a borderline role without consulting their DSO has misread what the number is. It is a planning multiplier, not legal advice.

<!-- → [DIAGRAM: a decision tree beginning at "Factor computed" — branch from 0 to "Skip regardless / reallocate time (Ch. 2)," branch from low but > 0 to "Apply only if strong on other factors AND accelerated process is possible," branch from high to "No timeline objection — let sponsorship, fit, liveness, quality decide"; each terminal node also shows a human-judgment check: "Verify with DSO if STEM eligibility is uncertain"] -->

There is one more error worth naming before this chapter closes. It is the error almost everyone makes at least once: finding a role that looks excellent in every other dimension and mentally filing the timeline question under "figure out later." Later is exactly when it is too late. The excitement of a good role is precisely the moment when the timeline question feels most like an interruption. That feeling is the signal to compute the factor first — because a factor of 0 means the excitement is a trap, and you want to know that before the four months, not after.

Five numbers now describe every role you are considering: sponsorship, fit, liveness, quality, and timeline. One of them can zero out all the others. The question is how the engine fuses them into a single decision — and why, in that fusion, sponsorship gets the loudest vote.

---

## Exercises

**Warm-up**

1. *(Recall — single-concept)* Explain, in one paragraph, why the timeline factor is implemented as a multiplier rather than an addend in the composite score. What outcome would a purely additive design allow that the multiplier forecloses?
   *Tests: understanding the gate logic vs. vote logic distinction.*
   *Difficulty: Low*

2. *(Distinguish — single-concept)* A student has a timeline factor of 0 for Role A and 0.55 for Role B. Role A has better sponsorship, fit, and quality scores. Write the decision and the reasoning. Then name the one thing that could change the factor for Role A without changing any of the other inputs.
   *Tests: reading the gate correctly; identifying expected-time-to-start as the lever.*
   *Difficulty: Low*

3. *(Apply — single-concept)* A STEM-eligible student and a non-STEM-eligible student both have four months of OPT remaining and 30 unemployment days used. Describe the difference in their timelines. How does STEM eligibility change which roles they can safely target?
   *Tests: the runway difference between OPT and STEM OPT; impact of the 150-day ceiling.*
   *Difficulty: Low*

**Application**

4. *(Compute — multi-input)* A student has OPT ending in 18 weeks, 15 unemployment days used, is STEM-eligible but has not yet filed the extension, and is evaluating a role whose typical process runs 14 weeks. Compute whether the factor is 0, near 1, or somewhere between — and identify what single action would most improve the student's timeline position before applying.
   *Tests: applying the factor components; identifying STEM extension filing as a runway-widening action.*
   *Difficulty: Medium*

5. *(Analyze — system behavior)* A student enters their authorization end date incorrectly — they enter a date three weeks later than the actual end. The factor comes back at 0.7 instead of 0. Trace the downstream consequences: what decisions does the 0.7 produce that the correct 0 would have prevented?
   *Tests: understanding that factor accuracy depends entirely on input accuracy; asymmetric cost of optimistic errors.*
   *Difficulty: Medium*

6. *(Evaluate — decision)* A role has a timeline factor of 0.3. The sponsorship tier is Proven, the fit is strong, and the liveness score is high. Make the case for applying and the case for skipping, then state which you would choose and what additional information would change the decision.
   *Tests: using the factor as one input in a multi-factor decision; identifying accelerated process as the key unknown.*
   *Difficulty: Medium*

**Synthesis**

7. *(Integrate — cross-chapter)* A student's Chapter 7 shortlist has twelve Proven-tier companies. After running the timeline factor, three are skip-regardless. Of the remaining nine, four have factors below 0.5. Using the freed-time logic from Chapter 2, describe how the factor output reshapes the student's week — which activities expand, which contract, and why the three hard drops are actually time gains.
   *Tests: connecting timeline gating to the time-budget logic of Chapter 2; treating skips as resource releases.*
   *Difficulty: High*

8. *(Diagnose — edge case)* A student near the end of their authorization receives an informal signal from a hiring manager that "we can move very fast if we want to." The role's timeline factor, computed from the company's historical process, is 0. Should the student apply? Walk through the reasoning, including what the factor can and cannot know, and what the student would need to verify before treating the informal signal as actionable.
   *Tests: limits of historical estimates; understanding what human judgment must add to the factor's output.*
   *Difficulty: High*

**Challenge**

9. *(Design — open-ended)* The current factor uses a single "expected time-to-start" estimate and a single buffer target. Propose an extension that would handle uncertainty in process length — for example, a probability distribution over possible process lengths rather than a point estimate. Describe what inputs the extension would require, how the factor output would change, and what the tradeoff is between precision and usability for a student managing twelve targets simultaneously.
   *Tests: thinking about uncertainty quantification; the design tradeoff between model sophistication and practical use.*
   *Difficulty: High/Open-ended*

[^opt]: F-1 post-completion OPT: max 90 aggregate days of unemployment (150 with STEM OPT extension); exceeding it terminates the record with no grace period. USCIS Policy Manual, Vol. 2, Part F, Ch. 5: https://www.uscis.gov/policy-manual/volume-2-part-f-chapter-5
