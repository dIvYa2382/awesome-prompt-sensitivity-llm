# research_decisions.md

**Project:** Lab 02 – AI Tools for Research
**Topic:** Prompt sensitivity and the stability of LLM-generated research conclusions
**Author:** Divya Joshi (Enrollment No.: MDE2026014)
**Date:** 21 October 2026

## Evidence Ledger Convention

- **VERIFIED** – confirmed directly in the source manuscript, the assignment specification, or an executed run.
- **INFERRED** – an interpretation that requires empirical testing.
- **UNKNOWN** – evidence not yet available.

Statements about the findings of cited works are VERIFIED only as *reported in the source review*. Primary-source verification of the original publications is pending.

---

## 1. Scope of the Source Review

| Field | Summary | Label |
|---|---|---|
| Topic | Prompt sensitivity of large language models and its effect on the stability of research conclusions (literature synthesis, hypothesis evaluation, causal interpretation, research ideation). | VERIFIED |
| Type | Narrative review with a conceptual framework. It reports no experiments or measured results. | VERIFIED |
| Guiding questions | Definition and sources of prompt sensitivity; its distinction from sampling stochasticity and factual error; its effect on research conclusions; detection and mitigation methods; requirements for a reliable LLM-assisted research workflow. | VERIFIED |
| Formal constructs | Task tuple P = (I, Q, C, F); prompt sensitivity S(P, P') (Eq. 3); variance decomposition (Eq. 6); prompt-stability score S_p (Eq. 7); Conclusion Stability Index, CSI (Eq. 8). | VERIFIED |
| Taxonomy | Lexical, semantic and inferential stability are distinct (Eq. 5, Table 1); sensitivity–consistency regimes (Table 3); accuracy–stability matrix (Table 4). | VERIFIED |
| Methods compared | Chain-of-thought, self-consistency, prompt ensembles, few-shot prompting, retrieval-augmented generation, structured evidence tables, LLM-as-a-judge, stability-aware prompt optimization (Table 5). | VERIFIED |
| Principal studies synthesized | POSIX [3], ProSA [17], Errica et al. [5], Hua et al. [6], Chen et al. [4], Si et al. [12] (Table 6). | VERIFIED |
| Dataset | None. The review identifies the absence of a standardized scientific-conclusion benchmark (Sec. 8.1). | VERIFIED |
| Quantitative effect sizes of cited studies | Not reported in the review; require the primary publications. | UNKNOWN |

## 2. Methodological Principles

- Remain within the research area of the source review and narrow the scope where necessary.
- Use the review as an evidence base rather than as text to be reproduced.
- Treat Eq. 3, Eq. 7 and the CSI as conceptual constructs; the review states that they require empirical validation (Sec. 2.2, 4.1, 8.2).
- Do not introduce unverified papers, datasets, repository links, code executions, experiments or metrics.
- Freeze the primary metric, test partition and comparison protocol before inspecting results.
- Maintain an accurate record of AI assistance, including accepted, modified and rejected suggestions.

## 3. Decision Log

| ID | Decision | Rationale | Source / Evidence | Next Action |
|---|---|---|---|---|
| D-01 | Remain within prompt sensitivity and the stability of LLM-generated research conclusions. | The assignment requires continuity with the completed review. (VERIFIED) | Assignment Sec. 2; review Sec. 1 | Select one gap from `research_gaps.md` and record the choice here. |
| D-02 | Verify the original publications [3], [4], [5], [6], [11], [12], [17] before relying on them. | The review is a secondary source for their findings. (VERIFIED) | Assignment Sec. 6; review Table 6 | Open each primary paper and update its label in the verification table (`research_gaps.md`, Sec. 5). |
| D-03 | Treat Eq. 3, Eq. 7 and the CSI as conceptual rather than established metrics. | The review characterizes them as conceptual and pending validation. (VERIFIED) | Review Sec. 2.2, 4.1, 8.2 | Define the conclusion distance D explicitly before applying Eq. 7. |
| D-04 | Defer any novelty claim. | No independent literature search has been conducted. (UNKNOWN) | Prompt 02 specification | Conduct the novelty and feasibility search (Prompt 04). |
| D-05 | Provisionally favor Pathway B (controlled comparative study) or a small Pathway C (targeted modification) test; final selection deferred. | The review proposes no implementation or baseline to reproduce. (INFERRED) | Assignment Sec. 3; review Sec. 8 | Confirm the pathway after Prompts 03 and 04. |

## 3a. Sources and Evidence

| Ref | Source | Used for | Status |
|---|---|---|---|
| S1 | Source review: *Prompt Sensitivity and Its Effect on the Stability of LLM-Generated Research Conclusions* (D. Joshi, ACM Comput. Surv. format, Sep. 2026) | Scope, equations, tables, stated limitations and future directions | VERIFIED (read directly) |
| S2 | Assignment specification: *AI Tools for Research – AI-assisted coding, vibe coding and evidence-based experimentation* | Pathways (Sec. 3), gates (Sec. 4), prompt specifications (Sec. 6), integrity rules (Sec. 10) | VERIFIED (read directly) |
| S3 | Chatterjee et al. (2024), POSIX, Findings of EMNLP 2024 – review ref. [3] | Prompt sensitivity index | Listed in review; primary check pending |
| S4 | Chen et al. (2026), Prompt Stability Matters, PMLR 328 – review ref. [4] | Stability-aware prompt optimization | Listed in review; primary check pending |
| S5 | Errica et al. (2025), What Did I Do Wrong?, NAACL 2025 – review ref. [5] | Sensitivity vs consistency | Listed in review; primary check pending |
| S6 | Hua et al. (2025), Flaw or Artifact?, EMNLP 2025 – review ref. [6] | Evaluation-induced sensitivity | Listed in review; primary check pending |
| S7 | Liu & Chu (2026), Understanding the Prompt Sensitivity, ACL 2026 – review ref. [11] | Theoretical account of sensitivity | Listed in review; primary check pending |
| S8 | Si, Yang & Hashimoto (2025), Can LLMs Generate Novel Research Ideas?, ICLR 2025 – review ref. [12] | Research-ideation evaluation | Listed in review; primary check pending |
| S9 | Zhuo et al. (2024), ProSA, Findings of EMNLP 2024 – review ref. [17] | Instance-level sensitivity | Listed in review; primary check pending |

Bibliographic details are copied from the review's reference list. Titles, venues, DOIs and years must be confirmed against the primary sources before they are placed in the `.bib` file.

## 3b. Consolidated Next Actions

1. Select the target gap(s) from `research_gaps.md` (current candidate: G1 combined with G3).
2. Verify the primary sources S3–S9 and update the labels in `research_gaps.md`, Sec. 5.
3. Define the conclusion distance D and the semantic-equivalence criteria for prompt variants.
4. Run the novelty and feasibility search (Prompt 04) before any novelty claim.
5. Proceed to Prompt 03 (literature-to-experiment mapping) once the gap is chosen.
6. Record the AI assistance used so far in `ai_assistance_log.md`.

