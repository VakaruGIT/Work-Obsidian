# Phase 1 — Global-Pass Review Report

**Source:** [docs/thesis/thesis.tex](thesis.tex) (1,164 lines)
**Bib:** [docs/thesis/references.bib](references.bib)
**Scope:** Global findings only. No chapter-by-chapter deep review yet.
**Deliverable convention:** every flagged issue includes a proposed rewrite or concrete action.

User gates Phase 2 (chapter-by-chapter) after reviewing this report.

---

## 0. Critical Submission Blockers

| # | Issue | Location | Action |
|---|---|---|---|
| B1 | **All three appendices are commented-out drafts.** Appendix A (Feature Definitions), Appendix B (Hyperparameters), Appendix C (Data Quality Degradation) contain only `% TODO` markers and `% DRAFT` blocks wrapped in `%`. Compiled PDF will render empty chapter headings. | [thesis.tex:1060-1161](thesis.tex#L1060-L1161) | Uncomment the draft tables, fill in `[FILL IN …]` placeholder in Appendix C, verify against nb04/05, ensure every row matches canonical numbers. |
| B2 | **Chapter 5 "Summary" has no introductory paragraph.** The `\chapter{Summary}` declaration is immediately followed by `\section{Discussion}`. IMC convention expects a 1–2 paragraph chapter preamble. | [thesis.tex:982-985](thesis.tex#L982-L985) | Add 1–2 sentence preamble between `\chapter{Summary}\label{chap:summary}` and `\section{Discussion}\label{sec:discussion}` stating what the chapter will do (discuss findings, state limitations, conclude, point to future work). |
| B3 | **MAPE still appears in the final pipeline.** User rubric mandates its full removal; CLAUDE.md confirms MAPE is meaningless for zero-target idle weeks. See §1 below. | [thesis.tex:304,477-478,740](thesis.tex#L304) | Remove all four mentions (prose, comments, Table 5 column header). |

---

## 1. MAPE — Hard Ban (user rubric)

Only $R^2$, RMSE, MAE are permitted. All MAPE references must be removed or replaced.

| # | Line | Context | Proposed fix |
|---|---|---|---|
| M1 | [304](thesis.tex#L304) | Chapter 2 background sentence contrasting metrics. | Delete the sentence or rephrase to discuss only $R^2$, RMSE, MAE. If the point is "metric choice matters in intermittent-demand settings," retain the MAPE criticism but cite it as an excluded metric rather than an evaluated one. |
| M2 | [477](thesis.tex#L477) | Comment: `% DO NOT report MAPE as a primary metric (misleading near-zero denominators).` | Delete the comment (policy is now enforced; comment is obsolete). |
| M3 | [478](thesis.tex#L478) | Comment: `% Primary metrics: R-squared, MAE. MAPE may appear in tables but with caveats.` | Delete the comment. Replace with a single-line comment: `% Primary metrics: R^2, RMSE, MAE.` |
| M4 | [740](thesis.tex#L740) | Column or cell in the Chapter 4 results table (tab:rq2_models or a per-WC variant). | Drop the MAPE column entirely. Re-align table column spec and caption wording. |

**Verification after fix:** `grep -n MAPE docs/thesis/thesis.tex` must return zero results.

---

## 2. Em-Dashes

### 2.1 ASCII `---` (TeX renders as em-dash)
| # | Line | Context | Fix |
|---|---|---|---|
| E1 | [721](thesis.tex#L721) | `Naive & Industry baseline & --- & $\hat{y}_{t+1} = y_t$ on the log scale \\` — table cell used as "no library" placeholder. | Replace `---` with `--` (en-dash) or a literal `None` / `N/A`: `Naive & Industry baseline & N/A & …` |
| E2 | [1083](thesis.tex#L1083) | Commented draft caption fragment `\textit{Operational Features --- week $t{-}1$ (3)}` | When the appendix is uncommented, replace `---` with `:`: `Operational Features: week $t{-}1$ (3)`. |
| E3 | [1120](thesis.tex#L1120) | Commented draft caption `Model Hyperparameters --- Main Models (5)` | When uncommented, change to `Model Hyperparameters: Main Models (5)`. |

### 2.2 Unicode em-dash `—` (only in LaTeX comments; never rendered)
Lines 89, 160, 180, 358, 470, 476, 980, 1065, 1110, 1136 — **all inside `%` comments**. Fix only if you prefer a clean source file; no PDF impact. Suggested: global replace of comment `—` with ` - ` for visual consistency.

**Verification:** `grep -n -- '---' docs/thesis/thesis.tex` must return only comment-internal matches after E1 is fixed.

---

## 3. American English Spelling — MAJOR INCONSISTENCY

**Headline finding:** the thesis mixes US and UK spelling. Roughly, Chapters 1–3 use "work center" (US), Chapter 4 and most of Chapter 5 switch to "work centre" (UK). User's choice (per CLAUDE.md examples and Abstract) is **American English**.

### 3.1 "work center" vs "work centre"
- **center** (US) at lines: 33, 34, 103, 133, 212 (×2), 213, 225, 239, 252, 401, 411 (×3), 440, 529, 784 — used throughout Abstract, Intro, Background, Related Work.
- **centre** (UK) at lines: 658, 699, 722, 723, 747, 762 (subsection label too), 764, 771 (×3), 816, 830, 838, 846, 857, 859, 872 (adjective), 879, 908, 937, 941, 961, 966, 968, 970, 972, 974, 976, 987, 991, 995, 1003 (×2), 1005, 1009, 1011, 1013, 1018, 1026, 1038, 1044, 1127, 1129, 1130 — concentrated in Ch. 4 onward.

**Action:** global replace `work centre` → `work center`, `per-work-centre` → `per-work-center` (including subsection label `\label{subsec:rq1_per_wc}` caption text and Figure 3 caption). Verify no references use the old label wording.

### 3.2 Other British variants
| Line | UK form | Proposed US replacement |
|---|---|---|
| [586](thesis.tex#L586) | `statistical behaviour` | `statistical behavior` |
| [586](thesis.tex#L586) | `summarized` (already US — OK) | — |
| [596](thesis.tex#L596) | `expected behaviour` | `expected behavior` |
| [654](thesis.tex#L654) | `organised`, `summarised` | `organized`, `summarized` |
| [658](thesis.tex#L658) | `work centre performance` | `work center performance` |
| [699](thesis.tex#L699) | `summarises`, `modelling` | `summarizes`, `modeling` |
| [771](thesis.tex#L771) | `coloured` | `colored` |
| [846](thesis.tex#L846) | `coloured` | `colored` |
| [872](thesis.tex#L872) | `centred on the target mean` | `centered on the target mean` |
| [816](thesis.tex#L816) | `modelling choice` | `modeling choice` |
| [879](thesis.tex#L879) | `normalises` | `normalizes` |
| [976](thesis.tex#L976) | `organisational` | `organizational` |
| [1001](thesis.tex#L1001) | `parameterised`, `transfered` (also typo — see §10) | `parameterized`, `transferred` |
| [1013](thesis.tex#L1013) | `operationalising` | `operationalizing` |
| [1038](thesis.tex#L1038) | `modelling with transfer learning` | `modeling with transfer learning` |
| [1135](thesis.tex#L1135) | `labelled` (comment draft) | `labeled` |

**Verification:** `grep -nE '(organis|summaris|behaviour|modelling|labell|colour|centred|normalis|operationalis|parameteris)' docs/thesis/thesis.tex` must return zero non-comment hits.

### 3.3 Already consistent (US)
`utilizes` (33), `fulfill` (227), `analyze` (checked, none). No `whilst`, `amongst`, `towards`, `learnt`, `programme` present.

---

## 4. Structural Integrity

### 4.1 Single-sentence paragraphs
| Line | Text opening | Verdict |
|---|---|---|
| [140](thesis.tex#L140) | Closing line of RQ list intro | Merge into preceding paragraph or extend with a motivating clause. |
| [658](thesis.tex#L658) | `Operational features capture work centre performance …` | Expand to 2–3 sentences OR remove the stand-alone label and absorb into group description (Section 4.3). |
| [666](thesis.tex#L666) | Short group-description paragraph in features section | Expand or merge with adjacent group. |
| [931](thesis.tex#L931) | Single-sentence wrap-up after RQ3 scenario list | Expand to 2 sentences that both state the finding and preview §5.1. |

### 4.2 Sections with `<2` paragraphs before a subsection (IMC rule: every section needs ≥1 intro paragraph, preferably 2)
- `sec:pp_hierarchy` — only 1 paragraph before subsections begin.
- `sec:ts_methods` — 1 paragraph intro only.
- `sec:data_quality` — 1 paragraph intro only.
- `sec:data_generation` — 1 paragraph intro only.
- `sec:preprocessing` — 1 paragraph intro only.
- `sec:modeling` — 1 paragraph intro only.
- `sec:rq1`, `sec:rq2`, `sec:rq3` — each has only 1 paragraph of framing before the first subsection.
- `sec:future_work` — 1 paragraph intro only.

**Action:** add a second paragraph to each section intro giving (a) what the section will do, (b) what it builds on from prior sections or RQs.

### 4.3 Subsections with only 1 paragraph
- `subsec:rq1_overall` ([thesis.tex:751](thesis.tex#L751))
- `subsec:rq1_operational` ([thesis.tex:762](thesis.tex#L762))

**Action:** expand each to at least 2 paragraphs or merge into parent subsection.

---

## 5. Cross-Reference Integrity

### 5.1 Labels declared but never referenced (unused)
- `tab:missingness_mechanisms` — defined in Ch. 2; no `\ref` in prose.
- `tab:related_work_summary` — defined in Ch. 3; no `\ref`.

**Action:** either add an explicit `Table~\ref{…}` call in the surrounding paragraph, or drop the label.

### 5.2 `\ref` / `\label` mismatches
No broken references detected at global scan. Verify during Phase 2 chapter passes by compiling and running `pdflatex` with log checking.

### 5.3 Captions
Most captions are self-contained. Flag Figure `fig:rq2_feature_importance` caption (around [846](thesis.tex#L846)) for removal of the sentence that refers to "Section~\ref{subsec:rq2_ablation}" — captions should not cite sections. Move that sentence to prose.

---

## 6. Acronym First-Use Audit

| Acronym | First use | First definition | Status |
|---|---|---|---|
| PCC | [137](thesis.tex#L137) | [186](thesis.tex#L186), more formally [225](thesis.tex#L225) | **Used before defined.** Define in Abstract or §1.1 on first appearance. |
| CRP | used consistently; defined [213](thesis.tex#L213) | OK |
| MRP / MRP II | [213](thesis.tex#L213) and later | Define `MRP` (Material Requirements Planning) and `MRP II` (Manufacturing Resource Planning) on first use. Check .bib double-braces. |
| DES | [144](thesis.tex#L144) as "Discrete Event Simulation"; also "Discrete-Event Simulation" at [428, 481, 512, 517, 538](thesis.tex#L428). | **Hyphenation inconsistent.** Choose one (recommend "Discrete-Event Simulation") and apply globally. |
| WC | used implicitly; first appears as "work center (WC)" — verify explicit parenthetical introduction on first use. Flag if absent. |
| SES | defined in §2.3 ([244](thesis.tex#L244)); section heading at [237](thesis.tex#L237) uses acronym first. | Introduce full form in section title or in first sentence before using `SES`. |
| ARIMA | Abstract mentions at [35](thesis.tex#L35); defined later. | Spell out on first use in Abstract: "ARIMA (autoregressive integrated moving average)". |
| AIC | used at [723](thesis.tex#L723); defined [738](thesis.tex#L738). | Swap order: define on first use. |
| IQR | used at [578](thesis.tex#L578); never expanded. | Add "(interquartile range)" on first use. |
| CV | ambiguous — "cross-validation" at [491](thesis.tex#L491) and "coefficient of variation" at [609, 613, 617](thesis.tex#L609). | Use `CV` for only one meaning. Recommend: spell out "coefficient of variation" fully each time, reserve "CV" for cross-validation. |
| ERP, MES | [97](thesis.tex#L97) uses reverse pattern `ERP (Enterprise Resource Planning)` and `MES (Manufacturing Execution System)` — **full form should precede acronym**. Also MES is singular at L97 but plural at [106](thesis.tex#L106). | Rewrite: "Enterprise Resource Planning (ERP) systems" and "Manufacturing Execution Systems (MES)"; then pluralize consistently. |
| RMSE, MAE, $R^2$ | defined in RQ1 [133](thesis.tex#L133). | OK |
| XGBoost | used in Abstract; treated as proper noun. | OK if bib title uses `{XGBoost}` double-braces. |

---

## 7. Numerical Consistency vs Canonical Numbers (nb04/05)

Canonical values per [docs/markdown/03_research_context.md](../markdown/03_research_context.md):

| Metric | Canon | Found in thesis |
|---|---|---|
| XGBoost test $R^2$ | 0.3546 | Reported as 0.355 (rounded) — OK. |
| XGBoost test RMSE (log) | 1.1393 | Confirm in Table 3 / §4.5. |
| XGBoost test MAE (log) | 0.7085 | Confirm in Table 3 / §4.5. |
| Ridge test $R^2$ | 0.3253 | 0.325 / 0.33 rounded — OK. |
| ARIMA test $R^2$ | 0.2705 | 0.271 rounded — OK. |
| SES test $R^2$ | 0.2709 | Check §4.5. |
| Naive test $R^2$ | −0.6465 | Check §4.5. |
| XGBoost history-only $R^2$ | 0.2043 | 0.204 — OK. |
| Ridge history-only $R^2$ | 0.2628 | 0.263 — OK. |
| XGBoost ablation gain | +0.1503 | Reported as +0.150 — OK. |
| **Ridge ablation gain** | **+0.0625** | **Reported as +0.063 ([thesis.tex:987](thesis.tex#L987)). Rounding is inconsistent with XGBoost (both should be to 3dp or 2dp).** Fix: use +0.063 (as shown) but then XGBoost should be +0.150 (matches). Verify all tables use 3dp. |
| 6-month XGBoost $\Delta R^2$ | −0.464 | Confirmed in Appendix C draft [1155](thesis.tex#L1155). |

**Action:** Phase 2 chapter pass will re-verify Abstract, §1.2, §4.5, §4.6, §4.7, §5.1, §5.3 for exact-match rounding to 3 decimals.

---

## 8. RQ Wording Diff

| Location | RQ1 | RQ2 | RQ3 |
|---|---|---|---|
| **§1.3 research_questions** ([thesis.tex:133](thesis.tex#L133)) | "How accurately can Machine Learning models predict weekly capacity consumption per work center …" | (next item) | (next item) |
| **Ch. 4 Results §§4.5–4.7** | "how accurately the capacity consumption of a work centre can be predicted one week ahead" ([747](thesis.tex#L747)) | "how each of the five models compare" (paraphrased) | "how each scenario degrades $R^2$" |
| **Ch. 5 Conclusion §5.3** ([thesis.tex:1018](thesis.tex#L1018)) | Answered explicitly but not always re-quoted verbatim. |

**Flag:**
- RQ1 verb changes: `predict` (intro) → `forecasts` (Abstract/§4.5). Choose one. User has used `forecast` in Abstract ([31](thesis.tex#L31)); propose standardizing on `forecast`.
- Target phrase is `weekly capacity consumption per work center` in §1.3 but becomes `one week ahead` in §4.5. Reconcile.
- Conclusion must re-quote RQ wording verbatim before answering. Verify in Phase 2.

---

## 9. Citation and Bibliography Audit

### 9.1 Orphan bib entries (defined in `references.bib`, never cited)
- `taylor2018prophet`
- `owen2024supplychain`
- `david2024defect`
- `karmaker2025`
- `hu2021timeseries`
- `goyal2024synthetic`
- `hoppe2025synthetic`
- `wen2021augmentation`

**Action:** either cite them in Related Work / Appendix, or delete from `references.bib`. Orphans inflate the bibliography without academic justification.

### 9.2 Vendor / non-peer-reviewed URLs
- `owen2024supplychain` — ResearchGate URL. Replace with peer-reviewed source or remove.
- `karmaker2025` — ResearchGate URL. Same.

Per user rubric: no vendor blogs, Wikipedia, commercial URLs. ResearchGate is acceptable only when it hosts a peer-reviewed preprint; verify the underlying venue and cite the venue, not ResearchGate.

### 9.3 Double-brace acronyms in titles
Verify every bib entry with an acronym in its title uses `{{ACRONYM}}` to prevent BibTeX lowercasing. Known acronyms to check: `MRP`, `MRP II`, `ARIMA`, `XGBoost`, `LSTM`, `SES`, `ERP`, `MES`, `DES`, `CRP`, `IIoT`, `OEE`, `SVR`. A spot-check in Phase 2 will confirm.

### 9.4 IEEE field completeness (per entry type)
- `@article` → needs `journal`, `volume`, `pages`, `year`.
- `@inproceedings` → needs `booktitle`, `year`, optional `pages`, `publisher`.
- `@book` → needs `publisher`, `year`, `address`.
- `@misc` → needs `howpublished` or `url` + `urldate`.

**Action:** run field audit in Phase 2; produce table of entries missing required fields.

### 9.5 Duplicate / consistency checks
- No duplicates detected by key name. Verify no two entries share the same DOI or title under different keys.
- Author formatting: inspect for mixed `Last, First` vs `First Last`. Standardize to `Last, First and Last, First` per IEEE BibTeX convention.

### 9.6 `\cite{}` format
All inline citations use `\cite{…}` — OK. No `\citep` / `\citet` detected.

---

## 10. AI-Smell and Filler

| # | Line | Finding | Fix |
|---|---|---|---|
| A1 | [859](thesis.tex#L859), [976](thesis.tex#L976) | `Taken together,` opens two paragraphs. | Replace one with a specific lead-in: "The ablation and feature importance together show …" (L859) or "Across the four dimensions, …" (L976). |
| A2 | [814](thesis.tex#L814) | `In other words,` | Prefer to restate the claim directly. Delete or replace with a specific connector. |
| A3 | [95](thesis.tex#L95), [112](thesis.tex#L112) | `leverage` / `leveraged` | Replace with `use`, `apply`, or a concrete verb. |
| A4 | [1026](thesis.tex#L1026) | Tricolon `directionally accurate, robust, and operationally deployable` | Keep the specific claims, drop the rhetorical triplet: "The model is directionally accurate on 15 of 20 work centers and robust to moderate data quality degradation." |
| A5 | [40](thesis.tex#L40) | `Additionally, a sensitivity analysis reveals …` | Replace `Additionally,` with nothing or a specific transition ("The sensitivity analysis shows …"). |
| A6 | Scan | No `delve`, `pivotal`, `crucial`, `paramount`, `realm`, `landscape`, `tapestry`, `navigate`, `underscore` detected. | Good. |

### 10.1 Typos / mechanical errors
| # | Line | Error | Fix |
|---|---|---|---|
| T1 | [1001](thesis.tex#L1001) | `transfered` + missing space `data.This` | `transferred`; `data. This` |
| T2 | [1011](thesis.tex#L1011) | `the model cannot comprehend from historical data` — awkward anthropomorphism. | Rewrite: "which the model cannot capture from historical data alone". |

---

## 11. Tone and Hedging Spot Checks

To be re-verified in Phase 2. Initial global impression:
- Hedging is generally calibrated (neither "proves conclusively" nor "might possibly suggest").
- Voice mix is mostly objective past / present for general truths.
- Watch for sentences >40 words in §4 methodology (several candidates in preprocessing and modeling sections).

---

## 12. What Still Needs the Chapter-Deep Pass (Phase 2 preview)

- Full sentence-craft audit (length variety, passive density, nominalization chains).
- Verbatim re-quoting of RQs in Conclusion.
- Practical + social/ethical/SDG implications in Discussion: confirm explicit coverage.
- Figure and table caption self-containment beyond L846.
- `references.bib` full field-by-field IEEE audit.
- Every `\cite{}` key manually resolved against `references.bib`.
- Acronym parenthetical-introduction confirmation on each first use.

---

## Summary of Required Actions (user checklist)

1. Uncomment and fill all three appendices (Critical).
2. Add Chapter 5 preamble (Critical).
3. Remove all four MAPE mentions (Rubric).
4. Fix em-dash at [721](thesis.tex#L721); also E2/E3 when appendices uncommented.
5. Global replace: `work centre` → `work center` (plus all other British spellings in §3.2).
6. Add/expand paragraphs in all sections listed in §4.2.
7. Expand or merge the four single-sentence paragraphs in §4.1.
8. Reference or remove unused table labels (§5.1).
9. Reorder ERP/MES acronym definitions (§6).
10. Fix DES hyphenation globally.
11. Disambiguate `CV` (cross-validation vs coefficient of variation).
12. Standardize Ridge / XGBoost rounding to 3dp across tables.
13. Resolve RQ wording drift (forecast vs predict).
14. Clear bib orphans or cite them.
15. Remove ResearchGate-sourced vendor entries or replace with peer-reviewed venues.
16. Fix AI-smell openers (`Taken together`, `In other words`, `Additionally`, `leverage`).
17. Fix typos at [1001](thesis.tex#L1001) and awkward phrasing at [1011](thesis.tex#L1011).

**User confirms this report before Phase 2 begins.** Phase 2 chapter order default: Ch. 1 → Ch. 2 → Ch. 3 → Ch. 4 → Ch. 5 → Appendices.