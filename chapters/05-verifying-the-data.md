# Chapter 5 — Verifying the Data

*A number that traces to a real record can still be measuring the wrong thing.*

Chapter 3 established a floor: every count, rate, and coverage number in this system must trace to a script output or an audit report, never to a model's best guess. That floor matters enormously. It is the difference between building on evidence and building on fluent fabrication.

But a floor is not a ceiling. Chapter 3 guarantees the number is real — that it came from counting rows in a public record, not from a language model estimating what the number probably was. This chapter asks a harder question: even if the number is real, is it trustworthy? Does it measure what you think it measures? Does the headline figure hold up when you look at the assumptions underneath it?

The distinction is not subtle. You can have a perfectly audited, perfectly script-sourced count that is quietly measuring the wrong thing. A join failure can make a prolific sponsor look like a non-filer. A base-rate mismatch can make a genuine signal look stronger than it is. A name-matching gap can exclude an entire corporate family from the dataset without leaving any evidence the missingness check can see. These are not data-pipeline bugs — they are epistemic failures. The numbers are real. The interpretation is wrong.

The methods in this chapter come from a companion book, *Computational Skepticism for AI*, where they are developed in full technical depth. I'm drawing on them here because they apply directly to the DOL and USCIS datasets this book runs on. If the reasoning feels compact in places, that's intentional — this is the practitioner application, not the derivation. What matters here is the procedure and what it surfaces.

<!-- → [INFOGRAPHIC: Three-tier stack. Bottom tier labeled "Chapter 3 guarantee: numbers trace to real records." Middle tier (this chapter) labeled "Chapter 5 asks: are the right things being measured?" Top tier labeled "Trustworthy inference." An arrow on the left side labels the gap between tiers 1 and 2: "Coverage gaps, name-matching failures, base-rate mismatch." Caption: "The floor the contract provides. This chapter builds the next tier."] -->

## The opening question: why are there exactly N rows?

Before I run any analysis on the LCA disclosure data, I ask a question that sounds almost too simple: *why are there exactly N rows in this dataset?*

The question comes from the epistemic-frame interrogation developed in *Computational Skepticism for AI*. The point is this: a dataset is not a census. It is a recording made by a particular instrument under particular conditions. The row count is not a fact about the world — it is a fact about the recording. Something determined where the data collection started, where it stopped, what joined successfully, and what got dropped quietly along the way. Unless you know what that something was, you don't fully know what the dataset represents.

For the DOL LCA disclosure data, the answer is more specific than it first appears. The dataset contains every Labor Condition Application that employers filed before hiring a foreign worker on an H-1B, H-1B1, or E-3 visa. So the row count is bounded by: who filed, in what time window, for what visa category, under what employer name, and whether the filing was accepted into the disclosure system. Each of those conditions is a filter the dataset silently applies before you ever open it.

Here is the practical consequence for this book: an employer who sponsored consistently but always filed under slightly different name variations — "Google LLC" in one quarter, "Google Inc." in another, "Alphabet Inc." in a third — will produce rows scattered across three employer-name buckets. An aggregation that groups by employer name and counts filings will treat these as three different companies, each with a modest filing count, instead of one company with a substantial one. The dataset is not wrong. The join is not broken. The rows are real. But the count you compute from them is not the count you meant to compute.

This is the "why exactly N rows?" move applied to the join problem. The boundary of the dataset is not just the schema — it is the schema plus every reference the schema's contents imply. The LCA dataset references employer names. Employer names reference legal entities. Legal entities undergo mergers, renamings, and restructurings. The full count lives somewhere in that chain. The dataset gives you a sample of it, bounded by however the names happened to be entered in the filing system.

<!-- → [DIAGRAM: One company (Alphabet / Google LLC / Google Inc.) shown as three separate employer-name buckets in the LCA filing data, each with a small filing count. A dotted box around all three labeled "Same legal filer." An arrow pointing to the aggregated true count. Caption: "Name-matching failures don't break the dataset. They fragment it. The rows are real; the employer grouping is not."] -->

## The six-step interrogation procedure

The six-step procedure in *Computational Skepticism for AI* is designed for any dataset you intend to base a deployment on. I'll walk through it applied to the sponsorship dataset — the LCA-to-H-1B join that the Sponsorship Scorer in Chapter 7 will run.

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

<!-- → [TABLE: Four columns — Diagnostic question / What it surfaces / Where to find the answer / What to do if the answer is unfavorable. Rows: Base rate / Prior probability before seeing the signal / SIC-level LCA filing frequency in the audit / Lower the effective threshold, require stronger corroboration; Calibration / Whether the scorer's stated probability is reliable / Calibration curve if available; cross-validate on holdout / Treat stated probabilities as ordinal ranks, not face-value probabilities; Cost distribution / Whether false positives or false negatives are more costly / Depends on application deadline and role fit / Adjust threshold accordingly; Freshness / Whether historical filings predict current posture / Filing date in the LCA data; recency filter in the audit / Downweight filings older than 18 months; flag acquisitions] -->

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

<!-- → [TABLE: Two columns — What this chapter's method guarantees / What it cannot guarantee. Rows: The N rows in the dataset represent real filings / That all filings by this employer are in the dataset; The employer-name grouping reflects the filing record / That name-matching failures don't fragment prolific sponsors; The sponsorship signal is calibrated against base rates / That historical filing rates predict current hiring posture; Output verbs are warranted by the evidence / That the right visa category is covered for this candidate; Coverage gaps are labeled in the audit / That the gaps don't systematically exclude a particular type of employer. Caption: "What this chapter adds to the floor Chapter 3 built."] -->

## Worked example: one company end to end

Let me make this concrete with the kind of trace Step 5 requires.

Take a mid-sized Cambridge biotech — the type of company Chapter 3 used to contrast verified and model-generated answers. It's a reasonable sponsorship candidate: talent-competitive field, specialized roles, graduate-intensive hiring.

I run the sponsorship dataset query. The result comes back: twelve LCA filings over three years, 80% H-1B approval rate, predominantly filed under job titles in "Life Sciences Researchers" SOC codes. The Sponsorship Scorer returns 0.68. So far, so good.

Now the trace. I pull the raw LCA rows for this employer. The name appears in two variants: "BioTechCo LLC" (ten rows) and "BioTechCo, LLC" (two rows — note the comma). The USCIS approval data has this employer under "BIOTECHCO LLC" (all caps, no comma). The join script normalized case but did not strip punctuation. The two rows filed under "BioTechCo, LLC" did not join to the USCIS data. They appear in the LCA count but not in the approval count. The approval rate calculation is therefore based on ten LCA filings, not twelve.

This does not change the conclusion dramatically — the employer is still a genuine historical sponsor. But it illustrates the mechanism. The gap is not a data error. Both records are correct. The join is the fragmentation point. And the dataset's missingness check reported zero missing values — because the rows are present, just in separate buckets that don't join.

Now the base rate check. In this SIC code (pharmaceutical and medicine manufacturing), the three-year LCA filing rate among employers in the DOL's universe is approximately 8%. The scorer returned 0.68. Working through the Bayes update: prior 0.08, likelihood ratio based on the observed filing count, posterior approximately 0.38–0.45 depending on assumptions. The 0.68 overstates the posterior probability by somewhere between 50% and 75%.

What does this mean for an F-1 student considering this company? It means the verified-data finding is: "We observe twelve LCA filings in three years and an 80% historical approval rate." It does not mean "this company sponsors." It means this company has a demonstrated filing history that makes them a reasonable target for further investigation — specifically, a direct inquiry about current H-1B sponsorship posture for the specific role and visa type relevant to you.

That's a more conservative conclusion than the raw score implies. It is also an honest one.

## The bridge to Chapter 6

Chapter 6 builds the first complete tool: the funding detector, which queries SEC Form D filings to find companies that just raised capital and are therefore under pressure to hire.

The method from this chapter travels with it. For every number the funding detector produces — round size, recency, investor profile — the same four questions apply: what is the base rate of companies in this category that are actually hiring? Is the signal calibrated? What does a false positive cost? What has changed since the filing date?

The practical difference from a user perspective is significant. A company that just closed a Series B and has zero verified sponsorship history is a different kind of lead than a company with fifteen LCA filings that raised no capital in three years. Neither signal alone is sufficient. Both together, interrogated against base rates, interpreted with calibrated verbs, and labeled with their coverage gaps, are what a trustworthy inference looks like.

That is the architecture of every chapter from here forward. The verified-data contract provides the floor: numbers trace to records. The epistemic-frame interrogation provides the next tier: those records are measuring what you think they're measuring, within documented limits. The verb taxonomy provides the output discipline: the system says exactly what the evidence warrants, and no more.

---

## Exercises

**Warm-up**

1. State the distinction this chapter draws between Chapter 3's guarantee and Chapter 5's question. In one sentence each: what does Chapter 3 guarantee, and what additional question does this chapter require you to ask?
   *Tests whether you can articulate the floor vs. the honest ceiling without conflating them.*

2. Name the six steps of the epistemic-frame interrogation procedure. For each step, identify what kind of failure it is designed to surface that the exploratory data analysis alone would miss.
   *Tests structural recall of the procedure and the reasoning behind each step.*

3. What is the "why exactly N rows?" question, and why is it asked before looking at any histograms or summaries? What does the row count tell you that the data itself does not?
   *Tests the opening move of the interrogation and the concept of boundary vs. schema.*

**Application**

4. Download the DOL LCA disclosure file for the most recent quarter available. Apply Steps 1–3 of the six-step procedure: lock a prediction about the employer count and coverage, run the exploratory analysis, and test the metadata against the data. Write up one gap between your prediction and what you found. What does the gap indicate about the dataset's epistemic frame?
   *Tests the prediction-lock discipline applied to a real public dataset.*

5. Take the name-matching gap described in the worked example — "BioTechCo LLC" vs. "BioTechCo, LLC" — and write a normalization function in pseudocode or your preferred language that would merge these two variants. Then identify two types of name variation this function would still miss, and explain why they're harder to handle without additional data.
   *Tests the gap between knowing coverage failures exist and knowing how to address them.*

6. A company in the tech sector has twelve LCA filings over three years and an 82% H-1B approval rate. The Sponsorship Scorer returns 0.71. The LCA filing rate for employers in this company's SIC code is 12%. Using the four diagnostic questions from this chapter, write the calibrated finding — what the evidence warrants saying, stated with the appropriate epistemic verb. Do not write the word "sponsors" as an unqualified present-tense claim.
   *Tests base-rate calibration and the verb taxonomy together on a realistic example.*

**Synthesis**

7. The coverage gap for non-H-1B visa categories (TN, L-1, O-1) means the sponsorship dataset will systematically undercount certain types of employers. Identify one type of employer — by industry, size, or organizational structure — that is most likely to be undercounted for this reason. Explain the mechanism, name the coverage gap in the audit, and write the label you would attach to any output concerning this employer type.
   *Tests the honest-ceiling reasoning applied to a specific structural gap.*

8. Design a two-sentence output format for the Sponsorship Scorer that applies the verb taxonomy correctly. Sentence one should be a data claim (use "observe" or "find"). Sentence two should be an explicit calibration note (use "does not warrant" or "is consistent with"). Test your format on the Cambridge biotech example.
   *Tests the practical application of the verb taxonomy in system output design.*

**Challenge**

9. The six-step procedure, the base-rate calibration, and the verb taxonomy together form a method for building trustworthy inferences on top of verified data. Identify one realistic scenario — a specific type of company, role, or visa situation — in which all three checks pass and the inference is still systematically misleading. What would a fourth check look like? What evidence would it require, and who would be responsible for producing it?
   *Tests whether you can find the limits of the method itself, not just apply it correctly.*
