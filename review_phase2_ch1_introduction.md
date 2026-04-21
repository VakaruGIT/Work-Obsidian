# Phase 2 — Chapter 1 Deep Review: Introduction

**Source:** [thesis.tex:91-176](thesis.tex#L91-L176), plus [Abstract lines 29-43](thesis.tex#L29-L43) (adjacent).
**Sections covered:** Abstract, Ch.1 preamble, §1.1 Motivation, §1.2 Problem Statement, §1.3 Research Questions, §1.4 Scope and Contributions, §1.5 Structure.
**Each issue:** Location · Quoted span · Category · Why flagged · Proposed rewrite.
**Categories:** conceptual / tone / structure / AI-smell / logic / citation / cross-ref / numerical / RQ / acronym / tense / hedging / typo / British-US / MAPE / em-dash.

User reviews and accepts (or edits) before Phase 2 moves to Ch. 2.

---

## A. Abstract ([thesis.tex:29-43](thesis.tex#L29-L43))

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| AB-1 | [34](thesis.tex#L34) | "with logic that is designed to replicate a variety of realistic data quality problems" | tone | Padded relative clause; "a variety of" is filler. | "designed to replicate realistic data quality problems" |
| AB-2 | [35](thesis.tex#L35) | "Different forecasting approaches are compared: Naive, Exponential Smoothing, ARIMA, Ridge Regression, and XGBoost." | acronym | ARIMA not expanded on first use in the Abstract. SES is spelled out as "Exponential Smoothing" (good), but ARIMA is opaque to a non-specialist reader skimming the Abstract. | "Five forecasting approaches are compared: Naive persistence, Simple Exponential Smoothing (SES), Autoregressive Integrated Moving Average (ARIMA), Ridge regression, and XGBoost." |
| AB-3 | [36-37](thesis.tex#L36-L37) | "The contribution is not focused on which complex model wins but rather on the fact that forward-looking planning-state information from Enterprise Resource Planning (ERP) systems materially improves capacity forecasting" | tone / AI-smell | "is not focused on X but rather on Y" is a weak, roundabout construction. "On the fact that" adds no information. | "The contribution is that forward-looking planning-state information from Enterprise Resource Planning (ERP) systems materially improves capacity forecasting for the coming week." |
| AB-4 | [38-39](thesis.tex#L38-L39) | "integrating planning-state features increased XGBoost accuracy by $+0.150$. This yielded $R^2 = 0.355$, allowing XGBoost to outperform autoregressive baselines." | numerical / conceptual | "Increased accuracy by +0.150" is ambiguous without the metric. Abstract also omits RMSE and MAE — the rubric requires all three. | "Integrating planning-state features raised XGBoost's $R^2$ from $0.204$ to $0.355$ (gain $+0.150$), with test RMSE of $1.14$ and MAE of $0.71$ on the log scale, allowing XGBoost to outperform the per-work-center ARIMA baseline ($R^2 = 0.271$)." |
| AB-5 | [40](thesis.tex#L40) | "Additionally, a sensitivity analysis reveals…" | AI-smell | "Additionally," is a flagged boilerplate opener. | Drop the connector: "A sensitivity analysis shows that models are robust to missing values and noise but vulnerable to short training history." |
| AB-6 | [40-41](thesis.tex#L40-L41) | "are vulnerable to short historical training data" | tone | Awkward phrase. | "are vulnerable to insufficient training history" |
| AB-7 | Missing | (no SDG / implication closing sentence) | structure | User rubric: Abstract should close with a one-sentence practical or societal implication. Currently ends on a vulnerability note. | Add one sentence, e.g., "These findings indicate that practical Machine Learning deployment for capacity planning hinges on feature engineering from existing ERP data rather than on model complexity, a result immediately applicable to small and mid-size manufacturers under Industry 4.0 programs." |

---

## B. Chapter 1 Preamble ([thesis.tex:91-99](thesis.tex#L91-L99))

*Four paragraphs before §1.1 Motivation. Functions as the chapter opener.*

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| P1-1 | [93](thesis.tex#L93) | "Production planning plays an important role in ensuring that each one of the manufacturing operations runs efficiently and cost-effectively." | tone | "Plays an important role" is a thesis-opening cliché. "Each one of the manufacturing operations" is wordy. | "Production planning determines whether manufacturing operations run efficiently and profitably." |
| P1-2 | [93](thesis.tex#L93) | "companies would need to know exactly how much capacity is needed to fulfill demand" | tone | Double "need/needed". | "companies would need to forecast exactly how much capacity each operation will consume" |
| P1-3 | [93](thesis.tex#L93) | "Capacity Requirements Planning (CRP) and Manufacturing Resource Planning (MRP-II)" | acronym | `MRP-II` hyphenation disagrees with CLAUDE.md / .bib convention `MRP II`. Decide one form globally. | "Capacity Requirements Planning (CRP) and Manufacturing Resource Planning (MRP II)" — and apply consistently through the thesis and .bib. |
| P1-4 | [93](thesis.tex#L93) | "This issue currently leads to capacity problems" | tone | `currently` adds nothing; the antecedent of "this issue" is vague (is it CRP, routing times, or static parameters?). | "The gap between static routing times and actual execution creates two opposing failure modes:" (then keep the overload/underload list). |
| P1-5 | [95](thesis.tex#L95) | "an opportunity to close this gap emerges by learning different relationships between the planned schedules and actual execution" | tone | "Emerges by" is awkward; "different relationships" is imprecise. | "Machine learning can close this gap by learning the relationships between planned schedules and actual execution" |
| P1-6 | [95](thesis.tex#L95) | "can be leveraged by data-driven prediction models" | AI-smell | `leveraged` is on the AI-smell list. | "can be used by data-driven prediction models" or "by Machine Learning models" |
| P1-7 | [95](thesis.tex#L95) | "the application of Machine Learning to predictive capacity consumption remains a topic with limited academic research." | tone / conceptual | "A topic with limited academic research" is circumlocution. Also "predictive capacity consumption" should be capitalized and acronymized on first use — see next row. | "the application of Machine Learning to Predictive Capacity Consumption (PCC) has received little academic study." (this also defines PCC on its first appearance — see §6 of the Phase 1 report). |
| P1-8 | [97](thesis.tex#L97) | "ERP (Enterprise Resource Planning) and MES (Manufacturing Execution System) systems" | acronym | **Reverse acronym pattern.** The full form must precede the acronym on first use. Also "MES ... systems" is redundant (MES already contains "System"). | "Enterprise Resource Planning (ERP) and Manufacturing Execution Systems (MES)" — and once MES is defined once correctly, do not re-introduce it at [106](thesis.tex#L106). |
| P1-9 | [99](thesis.tex#L99) | "three questions that grow from that challenge" | tone | "Grow from" is anthropomorphic for a research question. | "three questions that follow from that challenge" or "three research questions derived from that challenge". |
| P1-10 | [99](thesis.tex#L99) | "ARIMA" (used without expansion) | acronym | First expansion is implicit elsewhere; Abstract and Preamble should both define it. | Once AB-2 is fixed, here it is OK to use `ARIMA` unexpanded. |
| P1-11 | [99](thesis.tex#L99) | "which modeling family delivers the best balance of forecast accuracy, training cost, and interpretability" | tone | Tricolon ("accuracy, training cost, and interpretability") is fine when the three items are genuinely distinct; the same triplet is also in RQ2 at [135](thesis.tex#L135). Verify no further repetition in Ch. 4 framing. | Keep for now, but in §4.5 Results do not repeat the triplet verbatim. |

---

## C. §1.1 Motivation ([thesis.tex:101-115](thesis.tex#L101-L115))

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| M1-1 | [103](thesis.tex#L103) | "underloaded work centers that suffer from overstaffing or idle machine time are considered as wasted resources" | tone / British-US | "Considered as" is Britishism / redundant. Also "suffer from" anthropomorphizes work centers. | "underloaded work centers leave staff idle and machines unused, both of which waste resources" |
| M1-2 | [103](thesis.tex#L103) | "Both of the outcomes share the same root cause. A planned capacity load cannot reflect the actual capacity consumed on shop-floor level." | structure | Two short sentences with awkward period splitting the chain of reasoning. | "Both outcomes share a single root cause: a planned capacity load cannot reflect the actual capacity consumed at the shop-floor level." |
| M1-3 | [105-106](thesis.tex#L105-L106) | Extra blank line between paragraphs then "New systems such as ERP (Enterprise Resource Planning) and MES (Manufacturing Execution Systems)" | structure / acronym | Extra blank line at [105](thesis.tex#L105) creates inconsistent paragraph spacing. AND this is the second definition of ERP/MES — reverse-acronym again — within nine lines of the first at [97](thesis.tex#L97). Remove. | Delete the extra blank line. Rephrase without re-defining: "ERP and MES hold two information categories relevant to capacity forecasting:" |
| M1-4 | [106](thesis.tex#L106) | "MES (Manufacturing Execution Systems)" (plural) | acronym | Inconsistent with [97](thesis.tex#L97) where MES is singular. Choose one and apply globally. Recommendation: plural (`Systems`) is standard. | Apply plural consistently; update [97](thesis.tex#L97) to `Manufacturing Execution Systems (MES)`. |
| M1-5 | [108-109](thesis.tex#L108-L109) | "\textbf{Historical Event Logs:} What was executed in the past / \textbf{Forward Planning-State:} What is now planned for the future" | tone | Capitalization is inconsistent with academic register; clauses use "is now" vs "was" without parallel tense. | `\textbf{Historical event logs:} what has been executed; \textbf{Forward planning state:} what is currently planned.` |
| M1-6 | [112](thesis.tex#L112) | "hybrid approaches can leverage production-state information to improve forecast accuracy" | AI-smell | `leverage` flagged again. | "hybrid approaches can exploit production-state information" or "use production-state information" |
| M1-7 | [113](thesis.tex#L113) | trailing whitespace after paragraph end | typo / style | Minor — `\t\t` before a blank line; inconsistent indentation. | Remove trailing whitespace. |
| M1-8 | [115](thesis.tex#L115) | "It is unclear which modeling family (statistical baselines, classical time-series, or feature-based ML) performs best for this task \cite{menculini2021,albahli2025}" | logic | Framing OK, but the two cited papers are referenced here without a sentence explaining what *they* claim (are they equivocal? do they disagree?). | "It is unclear which modeling family performs best for this task: Menculini et al.\ \cite{menculini2021} find that classical time-series models remain competitive in manufacturing, while Albahli \cite{albahli2025} reports gradient boosting as the strongest class. (paraphrase to the actual claims after re-reading the sources.)" |
| M1-9 | §1.1 structure | Only one paragraph after the bullet list before §1.2. | structure | §1.1 has three bodies separated by the bulleted list. Paragraph structure is OK, but the section lacks a closing transition sentence. | Add a one-sentence bridge at the end of [115](thesis.tex#L115): "This thesis tests that investment directly by comparing five models with and without planning-state features." |

---

## D. §1.2 Problem Statement ([thesis.tex:118-126](thesis.tex#L118-L126))

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| PS-1 | [120](thesis.tex#L120) | "Despite new advancements in manufacturing systems or data collection techniques" | tone | "Or" should be "and" (both conjuncts are true simultaneously). "New advancements" is redundant ("advancement" already implies newness). | "Despite advances in manufacturing systems and data collection," |
| PS-2 | [120](thesis.tex#L120) | "traditional Capacity Requirements Planning (CRP) solutions" | acronym | CRP is already defined at [93](thesis.tex#L93); re-defining here is an IEEE convention violation. | "traditional CRP solutions" |
| PS-3 | [120](thesis.tex#L120) | "However, it structurally fails to acknowledge real shop-floor issues, including inherent process variance, unscheduled machine breakdowns or maintenance windows, operator fatigue, and unpredictable shift handovers." | tone | Good content, but sentence is 39 words. Split for readability. | "CRP structurally cannot acknowledge the real shop-floor sources of variation: process variance, unscheduled machine breakdowns, maintenance windows, operator fatigue, and shift handovers." |
| PS-4 | [120](thesis.tex#L120) | Trailing space at end of line. | typo / style | Remove. |
| PS-5 | [122](thesis.tex#L122) | "The mentioned problems create one persistent gap between the planned capacity load and the actual capacity that is consumed on the shop floor." | tone | "The mentioned problems" is clumsy; "one persistent gap" is awkward (should be "a persistent gap"). | "Together these problems create a persistent gap between the planned capacity load and the actual capacity consumed on the shop floor." |
| PS-6 | [122](thesis.tex#L122) | "Between these problems lies a challenge of accurately mapping one deterministic planning signal (material requirements planning) to a noisy and dispersed outcome (actual machine hours)" | tone / acronym | "Between these problems lies" is backwards-phrased. Also `material requirements planning` should be `Material Requirements Planning (MRP)` on first use, per §6 Phase 1 report; MRP II was already defined at [93](thesis.tex#L93), but bare MRP (without the "II") has not been. | "The resulting challenge is to accurately map a deterministic planning signal — Material Requirements Planning (MRP) output — to a noisy, dispersed outcome: actual machine hours." *Note: we cannot use an em-dash. Use a colon or two clauses:* "The resulting challenge is to accurately map a deterministic planning signal, namely Material Requirements Planning (MRP) output, to a noisy and dispersed outcome: actual machine hours." |
| PS-7 | [124](thesis.tex#L124) | "Missing At Random (MAR) issues \cite{rubin1973, little2002statistical}" | acronym / conceptual | MAR defined inline here, but Ch. 2 defines it formally at §2.3. Cross-reference Ch. 2 for details. | "Missing At Random (MAR) missingness — defined formally in Section~\ref{sec:data_quality} — \cite{rubin1973, little2002statistical}, confirmation lags, and quantity outliers" |
| PS-8 | [126](thesis.tex#L126) | "This research addresses this gap by evaluating distinct modeling families on a simulated, manufacturing dataset that replicates a real-world scenario." | typo / tone | Comma after "simulated" is incorrect — not a list. "A real-world scenario" is vague. | "This research addresses the gap by evaluating five modeling families on a simulated manufacturing dataset calibrated against the statistical properties of real ERP event logs." |
| PS-9 | [126](thesis.tex#L126) | "The final goal is to determine which one of the approaches provides the optimal balance of predictive accuracy, and robustness to data quality problems for weekly Predictive Capacity Consumption." | tone / numerical | "The final goal" is informal; awkward comma after "accuracy"; "optimal" is an overclaim (thesis produces a best-of-five, not an optimum). PCC first mentioned here — placement is late. | "The goal is to identify which approach offers the best balance of predictive accuracy and robustness to data quality problems for weekly Predictive Capacity Consumption (PCC)." *Note: this only defines PCC if P1-7 is not applied. If P1-7 is applied (PCC defined at [95](thesis.tex#L95)), then just: "...the best balance of predictive accuracy and robustness to data quality problems for weekly PCC."* |

---

## E. §1.3 Research Questions ([thesis.tex:128-140](thesis.tex#L128-L140))

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| RQ-1 | [133](thesis.tex#L133) | "How accurately can Machine Learning models predict \emph{weekly} capacity consumption per work center…" | RQ / consistency | Verb mismatch with Abstract and §4.5: Abstract and Ch. 4 use `forecast` / `forecasts`. Phase 1 report flagged this; here is the root occurrence. Standardize on `forecast`. | "How accurately can Machine Learning models forecast weekly capacity consumption per work center…" |
| RQ-2 | [135](thesis.tex#L135) | "Which modeling family (industry baselines such as Naive and Exponential Smoothing, per-work-center statistical time-series such as ARIMA, or feature-based ML such as Ridge Regression and XGBoost) delivers the best balance of forecast accuracy, training cost, and interpretability for Predictive Capacity Consumption?" | RQ / tone | 40-word sentence with nested parenthetical. Also re-introduces "Predictive Capacity Consumption" without using the already-defined PCC acronym. Also `per-work-center` contains British-US conflict with Ch. 4 subsection label `per-work-centre`. | "Which modeling family provides the best balance of forecast accuracy, training cost, and interpretability for PCC: industry baselines (Naive, SES), per-work-center statistical time-series (ARIMA), or feature-based ML (Ridge regression, XGBoost)?" |
| RQ-3 | [137](thesis.tex#L137) | "which model families are most robust to these degradations?" | RQ | OK — but answer wording in §4.7 must trace back to this. | Keep. |
| RQ-4 | [140](thesis.tex#L140) | "These questions are designed to provide actionable insights for manufacturing companies considering ML-based capacity planning." | structure | **Single-sentence paragraph** flagged in Phase 1. | Expand: "Together, the three questions address the accuracy, cost, and reliability of ML-based capacity planning for discrete manufacturing. They are designed to give practitioners a concrete basis for deciding whether to invest in a feature-based ML pipeline or retain simpler statistical methods already available in most ERP installations." |

---

## F. §1.4 Scope and Contributions ([thesis.tex:142-155](thesis.tex#L142-L155))

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| SC-1 | [144](thesis.tex#L144) | "a three-year synthetic manufacturing data set (event log)" | typo | `data set` → `dataset`; used as `dataset` at [144](thesis.tex#L144) later in same sentence (L144 is long). | "a three-year synthetic manufacturing dataset (event log)" |
| SC-2 | [144](thesis.tex#L144) | "The data is generated through the logic of Discrete Event Simulation (DES)" | acronym / consistency | DES hyphenation: here "Discrete Event Simulation" (unhyphenated); later in Ch. 4 it's "Discrete-Event Simulation" (hyphenated at lines 428, 481, 512, 517, 538). Choose one form globally. | "…generated through a Discrete-Event Simulation (DES)…" (recommended — standard term in simulation literature is hyphenated). |
| SC-3 | [144](thesis.tex#L144) | Sentence is 56 words. | tone | Too long. Split. | "This study focuses on a three-year synthetic manufacturing dataset of 31,949 operation transaction records across 20 work centers. The data is generated via a calibrated Discrete-Event Simulation (DES) \cite{fishman2001des} that reproduces the statistical properties of production event logs from discrete manufacturing. The baseline dataset includes four categories of injected data quality problems that persist across all experiments: MAR missingness, posting lags, quantity outliers, and duplicate confirmations. On top of this baseline, RQ3 evaluates six additional degradation scenarios…" |
| SC-4 | [146](thesis.tex#L146) | "The total actual machine hours consumed on each work center per week is the target variable that the models predict." | tone | "That the models predict" is redundant — "target" already implies what the models predict. | "The target variable is the total actual machine-hours consumed per work center per ISO week." |
| SC-5 | [146](thesis.tex#L146) | "transformed into logarithmic scale to reduce skewness" | tone | "Into logarithmic scale" should be "to a logarithmic scale" or "log-transformed". | "log-transformed (via \texttt{log1p}) to reduce skewness (raw skew $1.78$ to $-2.21$ after transform, see Section~\ref{sec:preprocessing})." |
| SC-6 | [146](thesis.tex#L146) | "Five representative forecasting solutions, spanning three model tiers (industry baselines, per-work-center statistical time series, and feature-based ML), are analyzed and compared using a chronological train/validation/test (70/15/15) split with week-blocked cross-validation." | tone | 38-word sentence with nested parenthetical. | Split into two sentences: "Five forecasting solutions spanning three model tiers are compared: industry baselines, per-work-center statistical time-series, and feature-based ML. Models are evaluated on a chronological 70/15/15 train/validation/test split with week-blocked cross-validation." |
| SC-7 | [149](thesis.tex#L149) | "From Discrete Event Simulation (DES)-based data generation" | acronym | DES already defined at [144](thesis.tex#L144). Re-definition is an IEEE convention violation. Also, the hyphenation is still inconsistent (`Discrete Event Simulation` vs `Discrete-Event Simulation`). | "From DES-based data generation, through feature engineering, to evaluation." |
| SC-8 | [149](thesis.tex#L149) | "A complete and reproducible five step pipeline…" | typo | `five step` should be hyphenated `five-step`. | "A complete and reproducible five-step pipeline…" |
| SC-9 | [149](thesis.tex#L149) | Item 1 is 44 words; "allows practitioners to substitute real ERP exports for the synthetic input without modifying the pipeline logic" | tone | OK content; long but acceptable. Minor: "standardized production event log schema" could drop "standardized". Keep if meaningful to Chapter 4 schema. | (no change required unless user wants tightening) |
| SC-10 | [150](thesis.tex#L150) | "which is 2.4$\times$ the gain observed for Ridge ($+0.063$)" | numerical | Arithmetic check: $0.150 / 0.063 = 2.381$. Rounds to 2.4. OK. Verify Ridge canonical gain is $+0.0625$ ($0.3253 - 0.2628$); rounded $+0.063$ matches. | Keep. |
| SC-11 | [150](thesis.tex#L150) | Item 2 is 68 words. | tone | Very long single sentence. | Split after "XGBoost ($R^2 = 0.204$) is outperformed by ARIMA ($R^2 = 0.271$)." Start new sentence at "With planning features (open planned workload, backlog, WIP), XGBoost becomes the best model…" |
| SC-12 | [151](thesis.tex#L151) | "per-work-center statistical models (SES, ARIMA) are effectively unaffected" | numerical | Verify: canonical RQ3 table shows SES/ARIMA worst case $-0.011$ for target corruption; "$|\Delta R^2| \leq 0.011$" matches. OK. | Keep. |
| SC-13 | [154](thesis.tex#L154) | "The original research proposal (Exposé) framed the study around daily granularity and three models (ARIMA, Prophet, LSTM)." | conceptual / scope | **CLAUDE.md SCOPE LOCK:** "The Expose is dead. Do not reference its methodology, models, or scope." The current note explicitly references Expose methodology and models. This contradicts the scope-lock directive. | Recommendation — either (a) delete the entire "Note on scope refinement" block entirely and cover any remaining scope-change justification in the Limitations section without naming the Expose, or (b) rewrite without naming the prior document: "Weekly aggregation was adopted over finer granularities because daily per-work-center series exhibit excessive zero-inflation. Five representative models — one per tier plus targeted comparisons — were selected to ensure each received rigorous cross-validation treatment." **Flag for user decision.** |
| SC-14 | [154](thesis.tex#L154) | "Both changes are data-driven decisions that strengthen rather than limit the study's validity." | tone / hedging | Self-praising closer. | Remove entirely, or state neutrally: "Both scope decisions are documented in Section~\ref{sec:research_design}." |

---

## G. §1.5 Structure of the Thesis ([thesis.tex:157-176](thesis.tex#L157-L176))

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| ST-1 | [159-161](thesis.tex#L159-L161) | Comment block `% ADAPTED FROM EXPOSE…` | conceptual | References the Exposé (scope-locked) directly in the LaTeX source. Even though comments are not rendered, per CLAUDE.md's "Expose is dead" directive, remove the reference. | Replace with `% Chapter-structure list` or delete entirely. |
| ST-2 | [168](thesis.tex#L168) | "Chapter~\ref{chap:background}: Background introduces the production planning hierarchy (CRP, MRP-II)…" | acronym | MRP-II hyphenation again — decide globally (see P1-3). | Apply global form `MRP II`. |
| ST-3 | [176](thesis.tex#L176) | Chapter 5 is called "Summary" here but the chapter's own title is also "Summary" ([982](thesis.tex#L982)). By IMC convention the final chapter is typically "Conclusion" (with Discussion and Future Work as earlier sections/chapters) or "Discussion and Conclusion". | structure / conceptual | Having Discussion, Limitations, Conclusion, and Future Work all nested under a chapter called "Summary" is unusual and hides the Conclusion's status. | **Flag for user decision.** Option 1: rename Ch. 5 to `Discussion and Conclusion`. Option 2: split into `Chapter 5: Discussion` and `Chapter 6: Conclusion`. Option 3: keep as-is but add a preamble (see Phase 1 report B2). |
| ST-4 | [164-176](thesis.tex#L164-L176) | The `\begin{samepage}` enforces an unbroken list | structure | Minor: if the list grows or the chapter changes, `samepage` may push the list to the next page alone. No action required unless layout breaks during final compile. | (no action unless PDF shows issue) |
| ST-5 | General | §1.5 is only 15 lines including comments. | structure | §1.5 is thin but the content (chapter roadmap) does not need more. Acceptable. | Keep. |

---

## H. Chapter 1-Level Cross-Cutting Findings

| # | Finding | Action |
|---|---|---|
| X-1 | **No MAPE occurrences in Ch. 1** — confirmed. Phase 1 findings (L304, L477-478, L740) are all outside Ch. 1. | None required in Ch. 1. |
| X-2 | **No ASCII em-dashes `---` in Ch. 1** — confirmed. | None required. |
| X-3 | **No British-US conflicts in Ch. 1 prose except `per-work-center` at [135](thesis.tex#L135).** Ch. 1 is overall US. | Keep Ch. 1 as-is; the inconsistency begins in Ch. 4. |
| X-4 | **Citation density in §1.1 is healthy:** 6 citations across 15 lines. IEEE numeric format used throughout. | OK. |
| X-5 | **Acronyms introduced but not consistently followed:** ERP and MES defined twice (L97 and L106) with reverse pattern; MRP II vs MRP-II; DES vs Discrete-Event. | See M1-3, M1-4, P1-3, P1-8, SC-2, SC-7, ST-2. |
| X-6 | **Tense discipline:** Ch. 1 uses present tense for general truths and present-passive for thesis contribution claims. Consistent. | OK. |
| X-7 | **RQ traceability from §1.3 to Abstract:** RQ1 uses `predict`; Abstract uses `forecast`. Resolve at RQ-1 above. | Apply RQ-1 fix. |

---

## Chapter 1 Summary (user checklist)

Before Ch. 2 review begins, user accepts or edits:

**Abstract:** AB-1 through AB-7 (7 issues). Notable: add RMSE/MAE numbers; drop `Additionally,`; consider adding implication closer.

**Preamble:** P1-1 through P1-11 (11 issues). Notable: define PCC here (P1-7); fix ERP/MES reverse acronym (P1-8); kill `leverage` (P1-6).

**§1.1 Motivation:** M1-1 through M1-9 (9 issues). Notable: fix "considered as" (M1-1); remove duplicate ERP/MES (M1-3, M1-4); add bridge sentence to §1.2 (M1-9).

**§1.2 Problem Statement:** PS-1 through PS-9 (9 issues). Notable: fix sentence length (PS-3); define MRP (PS-6); fix "optimal" overclaim (PS-9).

**§1.3 Research Questions:** RQ-1 through RQ-4 (4 issues). Notable: standardize `forecast` (RQ-1); fix long nested RQ2 (RQ-2); expand single-sentence paragraph (RQ-4).

**§1.4 Scope:** SC-1 through SC-14 (14 issues). Notable: DES hyphenation (SC-2); five-step hyphen (SC-8); split 68-word contribution sentence (SC-11); **decide what to do about the Exposé note (SC-13)** — this conflicts with CLAUDE.md scope lock; remove self-praise (SC-14).

**§1.5 Structure:** ST-1 through ST-5 (5 issues). Notable: remove Expose comment (ST-1); decide on Ch. 5 title (ST-3).

**Cross-cutting:** X-1 through X-7 (7 observations). No MAPE, no em-dashes, mostly US spelling (except `per-work-center` label in RQ2).

**Total Chapter 1 issues:** ~60 flagged (7 Abstract + 53 Ch.1).

---

**Next:** After user reviews and confirms, proceed to Ch. 2 Background ([thesis.tex:182-357](thesis.tex#L182-L357)). Ch. 2 will be the heaviest acronym-audit chapter since it formally defines CRP, MRP, MRP II, SES, ARIMA, MAR, MCAR, MNAR, DES.