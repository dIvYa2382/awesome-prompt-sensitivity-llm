# research_gaps.md

**Project:** Lab 02 – AI Tools for Research
**Topic:** Prompt sensitivity and the stability of LLM-generated research conclusions
**Author:** Divya Joshi (Enrollment No.: MDE2026014)
**Date:** 21 October 2026

Labels: **VERIFIED** (confirmed in the source review or by execution), **INFERRED** (interpretation requiring testing), **UNKNOWN** (evidence not yet available). Section, table and equation numbers refer to the source review. No novelty is claimed for any gap below; novelty requires a separate literature search.

---

## 1. Evidence Extracted from the Source Review

| Category | Items (as reported in the review) | Location |
|---|---|---|
| Central methods | Prompt perturbation testing; sensitivity vs consistency; chain-of-thought; self-consistency; prompt ensembles; few-shot prompting; retrieval-augmented generation; structured evidence tables; LLM-as-a-judge; stability-aware prompt optimization | Sec. 4, 6; Table 5 |
| Evaluation settings of cited studies | Multiple tasks and models [3, 17]; text classification [5]; seven LLMs, six benchmarks, twelve templates [6]; 100+ NLP researchers [12] | Table 6 |
| Reported findings | Wording and templates can alter model behavior [3]; sensitivity varies by task and model [17]; sensitivity and consistency are distinct [5]; part of the apparent sensitivity is an evaluation artifact [6]; stability as an optimization objective can improve consistency [4]; LLM-generated ideas rated novel but weaker in feasibility and diversity [12] | Sec. 1, 4.2, 5.4, 7.3; Table 6 |
| Stated limitations | Eq. 3 is not a direct measure of scientific inference; Eq. 7 and the CSI require a defensible distance and empirical validation; no single method guarantees correctness; none of the studies in Table 6 tests scientific-conclusion stability | Sec. 2.2, 4.1, 8.2, 10; Tables 5–6 |
| Unresolved questions | No standard definition of stability; difficulty establishing semantic equivalence; metric-induced artificial sensitivity; consistency does not imply correctness; model-version drift; domain-specific risk; no conclusion-level benchmark | Sec. 7.1–7.6, 8.1 |

These items are VERIFIED as statements made in the review. Their accuracy with respect to the cited publications is UNKNOWN pending primary-source checks.

## 2. Gap Matrix: Source Evidence → Research Question → Experiment

| ID | Candidate gap | Source in review | Origin | Possible experiment |
|---|---|---|---|---|
| G1 | Conclusion-level stability under meaning-preserving prompt perturbation | Sec. 9 (scale mismatch); Sec. 4.1; Table 6 | Mismatch reported; test design INFERRED | Fixed evidence, multiple validated paraphrased prompts; compare conclusion category and confidence |
| G2 | Evaluation procedure inflating measured instability | Sec. 7.3; Sec. 9; Table 6 [6] | Reported; extension to conclusion-level outputs INFERRED | Score identical outputs with lexical, embedding, NLI and judge-based evaluators against a human-labelled subset |
| G3 | Separation of prompt variance from sampling variance | Eq. 6; Sec. 3.1; Table 2; Sec. 8.3 | Direction reported; design INFERRED | Prompts × repeated runs at fixed evidence; variance-component analysis |
| G4 | Framing effects on hypothesis and causal conclusions | Sec. 5.2, 5.3, 8.5 | Risk stated without a cited test; experiment INFERRED | Positive, neutral and skeptical framings on fixed evidence; compare conclusion strength and causal level |
| G5 | Empirical validity of the Conclusion Stability Index | Sec. 8.2; Sec. 10 | Reported (stated as not an established metric) | Simplified CSI vs human ratings; weight-sensitivity analysis |

## 3. Detailed Gap Specifications

### G1 – Conclusion-Level Stability under Meaning-Preserving Prompt Perturbation
- **Source evidence:** Sec. 9 notes that most prompt-sensitivity studies evaluate task outputs, whereas scientific conclusions require judgments about evidence strength, contradictions, uncertainty and causality. Sec. 4.1 states that Eq. 7 requires an explicit, defensible conclusion distance. Table 6 records that [3], [5] and [17] do not measure inferential stability.
- **Reported vs inferred:** The scale mismatch and the undefined conclusion distance are reported. The suitability of a small fixed-evidence study to test them is inferred.
- **Research question:** With evidence and claim held fixed, how frequently do the conclusion category (supports / insufficient / contradicts) and the stated confidence change across human-validated, meaning-preserving prompts?
- **Evidence required:** Per-item agreement with the majority category; Eq. 7 with an explicit distance D; a same-prompt repeated-sampling control.
- **Pre-conditions:** Confirm that prior work does not already measure this (UNKNOWN). Prompt equivalence requires human validation (Sec. 7.2).

### G2 – Evaluation Procedure Inflating Measured Instability
- **Source evidence:** Sec. 7.3 and Sec. 9; Table 6, entry [6].
- **Reported vs inferred:** Reported. Application to conclusion-level outputs is inferred.
- **Research question:** On a fixed set of outputs, how much of the measured instability disappears when lexical matching is replaced by embedding similarity, natural language inference or an LLM judge, relative to a human-labelled subset?
- **Evidence required:** Instability rate per evaluator; agreement of each evaluator with human labels.
- **Pre-conditions:** Verify the setting and claims of [6]. The review notes that judge and generator may share errors (Table 5).

### G3 – Separation of Prompt Variance from Sampling Variance
- **Source evidence:** Eq. 6 and its caveat that it is not a strict statistical identity (Sec. 3.1); Table 2 lists decoding stochasticity without a representative study; Sec. 8.3 recommends varying prompt, evidence and sampling independently.
- **Reported vs inferred:** The direction is reported. The two-factor design is inferred.
- **Research question:** At fixed evidence, what proportion of conclusion variation is attributable to prompt wording, to repeated sampling, and to their interaction?
- **Evidence required:** Prompts × runs grid; variance-component analysis with confidence intervals.
- **Pre-conditions:** Confirm that the selected model permits seed and temperature control, and test whether temperature 0 is deterministic (UNKNOWN).

### G4 – Framing Effects on Hypothesis and Causal Conclusions
- **Source evidence:** Sec. 5.2 (positive vs skeptical framing), Sec. 5.3 (causal wording), Sec. 8.5 (perturbation list).
- **Reported vs inferred:** The review states these as risks without citing an empirical test. The experiment is inferred.
- **Research question:** With evidence fixed, do framing and causal-mechanism wording shift conclusion strength, uncertainty language or the causal level asserted?
- **Evidence required:** Paired comparison across framings using a written annotation rubric.
- **Pre-conditions:** Define the rubric and obtain a second rater. Novelty is UNKNOWN.

### G5 – Empirical Validity of the Conclusion Stability Index
- **Source evidence:** Sec. 8.2 proposes the CSI for future empirical validation and states that its weights are domain-dependent; Sec. 10 reiterates this.
- **Reported vs inferred:** Reported.
- **Research question:** Does a simplified CSI track human judgments of conclusion stability, and how sensitive is the resulting ranking to the choice of weights?
- **Evidence required:** Correlation with human ratings; weight-perturbation analysis.
- **Pre-conditions:** Requires gold conclusions and evidence/uncertainty labels. The review states that no such benchmark exists (Sec. 8.1), so annotation effort is substantial.

## 4. Ranking of the Top Three Gaps

Scores range from 1 (weak) to 5 (strong). They are judgment-based (INFERRED) and assume a modest compute budget.

| Rank | Gap | Significance | Resources | Feasibility | Total |
|---|---|---|---|---|---|
| 1 | G1 – Conclusion-level stability | 5 | 4 | 4 | 13 |
| 2 | G3 – Prompt vs sampling variance | 4 | 5 | 4 | 13 |
| 3 | G2 – Evaluation artifacts at conclusion level | 4 | 4 | 3 | 11 |

G1 and G3 are tied on total score. G1 is ranked first because it addresses the central mismatch identified in Sec. 9, and G3 can be incorporated into the same design as a variance control, so the two are naturally combined. G2 is ranked third because it requires a human-labelled subset and a judge model. G4 can be run as one prompt condition within G1. G5 depends on outputs and labels produced under G1 and is therefore a later extension.

## 5. Claims Requiring Verification Against Primary Sources

| Item | Verification required | Label |
|---|---|---|
| Hua et al. [6] | Evaluation setting (7 LLMs, 6 benchmarks, 12 templates) and the claim that a substantial portion of sensitivity is an evaluation artifact | UNKNOWN |
| POSIX [3] | Measured quantity (relative change in response likelihood); few-shot claim | UNKNOWN |
| ProSA [17] | Relationships among confidence, robustness and model scale. Table 5 attributes the few-shot effect to [17] while Table 6 attributes it to [3]; the correct attribution must be confirmed | UNKNOWN |
| Errica et al. [5] | Definitions of sensitivity and consistency; restriction to classification | UNKNOWN |
| Chen et al. [4], Liu & Chu [11] | Both dated 2026; confirm venue, availability and claims | UNKNOWN |
| Si et al. [12] | The 100+ researcher study and its novelty, feasibility and diversity findings | UNKNOWN |
| Review, Table 5 | Prompt ensembles and structured evidence tables are listed as conceptual or review-derived | VERIFIED |
| Review, Table 2 | Decoding stochasticity is listed without a cited study | VERIFIED |
| Review, Eq. 4 and 7 | The distance D is not concretely defined | VERIFIED |

## 6. Sources and Evidence

- **S1** – Source review, *Prompt Sensitivity and Its Effect on the Stability of LLM-Generated Research Conclusions* (Sec. 1–10, Tables 1–6, Eq. 1–8). Read directly; VERIFIED.
- **S2** – Assignment specification, *AI Tools for Research* (Prompt 02, Sec. 3, Sec. 10). Read directly; VERIFIED.
- **S3–S9** – Primary works cited in the review: POSIX [3], Chen et al. [4], Errica et al. [5], Hua et al. [6], Liu & Chu [11], Si et al. [12], ProSA [17]. Listed in the review's reference list; primary-source verification pending (see Sec. 5).

No evidence outside S1 and S2 has been consulted.

## 7. Next Actions

| # | Action | Gap(s) | Output |
|---|---|---|---|
| 1 | Verify S3–S9 against the primary publications and update the labels in Sec. 5 | All | Updated verification table |
| 2 | Resolve the attribution inconsistency between Table 5 and Table 6 for the few-shot finding ([17] vs [3]) | G1, G3 | Corrected attribution |
| 3 | Define the conclusion distance D and criteria for semantic equivalence of prompt variants | G1, G3, G5 | Written definition |
| 4 | Conduct the novelty and feasibility search for the top-ranked gaps (Prompt 04) | G1, G3, G2 | Novelty/feasibility matrix and go/no-go decision |
| 5 | Select the target gap and record the decision in `research_decisions.md` | G1 + G3 (current candidate) | Updated decision log |
| 6 | Proceed to Prompt 03 (literature-to-experiment mapping) | Selected gap | Mapping table and minimum viable experiment |
