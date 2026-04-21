# Phase 2 — Chapter 2 Deep Review: Background

**Source:** [thesis.tex:182-355](thesis.tex#L182-L355)
**Sections:** Preamble (L184-188), §2.1 Production Planning Hierarchy, §2.2 Deterministic Planning to PCC, §2.3 Time-Series Forecasting in Manufacturing, §2.4 Data Quality and Methodological Risks.
**Each issue:** Location · Quoted span · Category · Why flagged · Proposed rewrite.

User reviews before Ch. 3 begins.

---

## A. Chapter 2 Preamble ([thesis.tex:184-188](thesis.tex#L184-L188))

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| CH2-1 | [184](thesis.tex#L184) | "In the background chapter, all theoretical foundations required to understand the research questions, methodology and scope of the thesis are presented." | tone | Self-referential passive opener ("In the background chapter... are presented"). Also missing Oxford comma in "research questions, methodology and scope" — elsewhere (e.g., [133](thesis.tex#L133)) the thesis uses Oxford comma. | "This chapter presents the theoretical foundations required to understand the research questions, methodology, and scope of the thesis." |
| CH2-2 | [185](thesis.tex#L185) | "Each section corresponds to a different approach and aspect of the problem." | tone | Vague filler sentence. | Delete. Or replace with a concrete roadmap sentence: "The chapter proceeds from production planning theory to the modeling and data-quality concepts used in Chapter~\ref{chap:methodology}." |
| CH2-3 | [186](thesis.tex#L186) | "presents the definition of Deterministic Planning and its limitations, followed by the term Predictive Capacity Consumption (PCC)…" | conceptual / acronym | "Deterministic Planning" capitalized as a proper term but never defined as one in the thesis. Also PCC is re-parenthesized here — if Ch. 1 defines PCC (per P1-7 in Ch.1 review), the `(PCC)` parenthetical is a re-definition. | "presents deterministic CRP planning and its limitations, and then defines PCC in contrast with demand forecasting." |
| CH2-4 | [187](thesis.tex#L187) | "time-series forecasting uses and methods in the industry of manufacturing" | tone | "In the industry of manufacturing" is awkward; "uses and methods" is redundant. | "time-series forecasting methods used in manufacturing" |
| CH2-5 | [188](thesis.tex#L188) | "explains how data problems are affecting the model performance" | tense / tone | Present continuous is unusual for a general statement; use simple present. "The model performance" also reads British. | "explains how data problems affect model performance" |
| CH2-6 | [188](thesis.tex#L188) | "the forecast-origin discipline that rules out data leakage" | tone | "Rules out" is informal for a methodological concept. | "the forecast-origin discipline that prevents data leakage" |

---

## B. §2.1 The Production Planning Hierarchy ([thesis.tex:190-201](thesis.tex#L190-L201))

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| PPH-1 | [190-193](thesis.tex#L190-L193) | Section intro is 1 paragraph only (L192-193) before the first subsection. | structure | Phase 1 §4.2 flagged `sec:pp_hierarchy` as needing ≥2 intro paragraphs. | Add a second paragraph after L193 stating what the two subsections will cover, and why this layered view motivates PCC: "Subsection~\ref{subsec:mrp2} outlines the MRP II framework; Subsection~\ref{subsec:crp} then focuses on CRP, whose deterministic routing formula is the point at which planning diverges from shop-floor execution." |
| PPH-2 | [192](thesis.tex#L192) | "a hierarchy of decisions exists that translates high-level business plans into executable schedules" | tone | "Exists that translates" is weak scaffolding. | "In production planning, a hierarchy of decisions translates high-level business plans into executable schedules," |
| PPH-3 | [193](thesis.tex#L193) | "Manufacturing Resource Planning (MRP-II) as the framework and Capacity Requirements Planning (CRP) as the specific planning function" | acronym | (1) `MRP-II` hyphenation vs `MRP II` — decide globally. (2) CRP was already defined in Ch. 1 [93](thesis.tex#L93); re-parenthesizing is an IEEE convention violation. | "Manufacturing Resource Planning (MRP II) as the framework and CRP as the specific planning function" (apply global `MRP II` decision from Ch. 1 P1-3). |
| PPH-4 | [197](thesis.tex#L197) | "Manufacturing Resource Planning (MRP-II) is an integrated system for planning and controlling all resources of a manufacturing firm." | acronym | Re-definition within 4 lines of [193](thesis.tex#L193). | Drop the parenthetical: "MRP II is an integrated system for planning and controlling all resources of a manufacturing firm." |
| PPH-5 | [198](thesis.tex#L198) | "The hierarchy operates top-down, as illustrated in Figure~\ref{fig:mrp2_hierarchy}: a Sales and Operations Plan (S\&OP) establishes the long-term demand outlook, which is refined into a Master Production Schedule (MPS) for specific finished goods." | tone | 30-word sentence with three nested acronyms (S&OP, MPS, and the later BOM on [199](thesis.tex#L199)). Acceptable but dense. | Split at "outlook,": "The hierarchy operates top-down (Figure~\ref{fig:mrp2_hierarchy}). A Sales and Operations Plan (S\&OP) sets the long-term demand outlook, which is refined into a Master Production Schedule (MPS) for specific finished goods." |
| PPH-6 | [200](thesis.tex#L200) | "Finished Goods (FG) are customer ready deliverable end items, Semi-Finished Goods (SFG) are intermediate products assembled from lower-level components and produced to replenish internal stock, and Raw Materials (RAW) are purchased or in-house base inputs that undergo initial processing." | tone / typo | (1) `customer ready` should be hyphenated `customer-ready`. (2) Sentence is 45 words; three definitions in one sentence is dense. (3) FG/SFG/RAW are defined here but never reused in the thesis outside this paragraph — verify before investing in definition. | Either: (a) split into three short sentences, or (b) convert to a tight bullet list. Also hyphenate `customer-ready`. If FG/SFG/RAW are unused elsewhere, drop the acronyms: "Finished goods are customer-ready end items, semi-finished goods are intermediate assemblies that replenish internal stock, and raw materials are base inputs that undergo initial processing." |
| PPH-7 | [201](thesis.tex#L201) | "ERP systems integrate production planning, material management, and shop-floor execution data into a single platform~\cite{jacobs2011}, providing the operation transaction logs and routing master data that serve as inputs to the PCC pipeline." | tone | 30-word sentence, but acceptable. Verify ERP defined earlier (yes, Ch. 1 [97](thesis.tex#L97)). | Keep. |
| PPH-8 | [201](thesis.tex#L201) | "This thesis targets the CRP layer, more specifically, the gap between planned and actual capacity consumption." | tone | "More specifically" with double comma is awkward. | "This thesis targets the CRP layer, specifically the gap between planned and actual capacity consumption." |
| PPH-9 | [206](thesis.tex#L206) | Figure 1 caption: "The MRP-II planning hierarchy (adapted from Jacobs et al.~\cite{jacobs2011})." | cross-ref / caption | Caption is too short; not self-contained. Per Phase 1 caption rule, a caption should describe what is shown. | "Figure 1. The MRP II planning hierarchy: Sales and Operations Planning (S\&OP) $\rightarrow$ Master Production Schedule (MPS) $\rightarrow$ Material Requirements Planning (MRP) $\rightarrow$ Capacity Requirements Planning (CRP) $\rightarrow$ shop-floor execution. Adapted from Jacobs et al.~\cite{jacobs2011}." *Note: avoid `—`; use `$\rightarrow$` or commas.* |
| PPH-10 | [212](thesis.tex#L212) | "A work center is a grouping of machines, personnel, or both at which manufacturing operations (e.g., assembly, pressing, welding) are performed and where capacity is expressed in machine hours or labor hours that is measured and constrained~\cite{swamidass2000crp}." | tone / grammar | (1) 36-word sentence. (2) `hours that is measured and constrained` — singular `is` disagrees with plural `hours`. | "A work center is a grouping of machines, personnel, or both at which manufacturing operations (e.g., assembly, pressing, welding) are performed. Its capacity, expressed in machine-hours or labor-hours, is measured and constrained~\cite{swamidass2000crp}." |
| PPH-11 | [220](thesis.tex#L220) | "unscheduled machine breakdowns, operator fatigue, missing materials, or even confirmation lags" | tone | `or even` is conversational. | "unscheduled machine breakdowns, operator fatigue, missing materials, or confirmation lags" |
| PPH-12 | [220](thesis.tex#L220) | "Empirical studies of discrete manufacturing processes consistently find that actual operation durations are right-skewed and approximately log-normal around their planned values, with variability driven by queueing, setup variance, and stochastic downtime~\cite{hopp2011factory}." | tone | 33-word sentence. | Split: "Empirical studies of discrete manufacturing find that actual operation durations are right-skewed and approximately log-normal around their planned values. Variability is driven by queueing, setup variance, and stochastic downtime~\cite{hopp2011factory}." |
| PPH-13 | [221](thesis.tex#L221) | "the planned capacity load computed by CRP almost never matches the actual capacity consumed on the shop floor and this persistent gap is the central problem that this thesis focuses on." | tone / register | (1) `almost never` is colloquial hedging. (2) Sentence ends with preposition. (3) Repeats the thesis motivation already stated in Ch. 1 §1.1 [103](thesis.tex#L103). | "As a result, the planned capacity load computed by CRP rarely matches the actual capacity consumed on the shop floor; this persistent gap is the central problem addressed by this thesis." |

---

## C. §2.2 From Deterministic Planning to PCC ([thesis.tex:223-230](thesis.tex#L223-L230))

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| PCC-1 | [225](thesis.tex#L225) | "Predictive Capacity Consumption (PCC) is defined in this thesis as the task of forecasting the total actual machine-hours consumed per work center per ISO week, learned from historical production event logs." | acronym | If Ch. 1 P1-7 is applied, PCC is already defined. This is the formal definition, so acceptable here — but then remove the parenthetical `(PCC)` and treat this as the canonical definition sentence. | "Predictive Capacity Consumption is defined in this thesis as the task of forecasting the total actual machine-hours consumed per work center per ISO week, learned from historical production event logs." (if Ch. 1 defines PCC). If Ch. 1 does *not* define PCC, keep the parenthetical here and remove it from Ch. 1. |
| PCC-2 | [226](thesis.tex#L226) | "demand forecasting, which operates at the sales and market level by predicting order volumes at the customer level" | tone | "At the sales and market level... at the customer level" is repetitive. | "demand forecasting, which predicts order volumes at the customer or market level" |
| PCC-3 | [227](thesis.tex#L227) | "PCC predicts \textit{how long} machines will actually run to fulfill those orders" | tone | `actually` is filler. | "PCC predicts \textit{how long} machines will run to fulfill those orders" |
| PCC-4 | [227](thesis.tex#L227) | "the static routing assumption of \eqref{eq:crp_deterministic} cannot capture" | cross-ref | Equation reference format: `\eqref{eq:crp_deterministic}` renders as `(1)` in IEEE style. Verify consistency: elsewhere the thesis uses `Equation~\ref{eq:…}`. | Choose one style. Recommend `Equation~\eqref{eq:crp_deterministic}` (IEEE-compatible) throughout. |
| PCC-5 | [230](thesis.tex#L230) | "This shift from deterministic planning to predictive modeling enables production planners to proactively identify potential bottlenecks and schedule misalignments before stochastic events such as machine breakdowns, operator fatigue, and data entry latency that most often cause missed delivery deadlines, rather than reacting to deviations after the fact." | tone | 43-word sentence; "proactively", "after the fact" are colloquial; "most often cause" is awkward. | Split: "This shift from deterministic planning to predictive modeling enables planners to identify bottlenecks and schedule misalignments before the stochastic events that cause missed deadlines: machine breakdowns, operator fatigue, and data entry latency. Planners can act on forecasts instead of reacting to deviations after they occur." |
| PCC-6 | §2.2 structure | Section has 2 short paragraphs total, no subsections, no transition to §2.3. | structure | Phase 1 didn't flag sec:pcc for thin intro, but the section itself is very short (5 lines). | Add one bridging sentence at the end tying §2.2 to §2.3: "The next section introduces the five forecasting methods compared in this thesis to evaluate whether PCC can close the gap left by CRP." |

---

## D. §2.3 Time-Series Forecasting in Manufacturing ([thesis.tex:232-308](thesis.tex#L232-L308))

### D.0 Section intro ([L234-235](thesis.tex#L234-L235))

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| TS-0-1 | [234](thesis.tex#L234) | "This section introduces five forecasting methods that are evaluated in this thesis, organized into **two tiers**: univariate statistical baselines and feature-based machine learning models." | conceptual / RQ | **Tier-count inconsistency.** Ch. 1 §1.4 [146](thesis.tex#L146) and [149](thesis.tex#L149) frame the comparison in **three tiers** (industry baselines, per-work-center statistical time-series, feature-based ML). Ch. 2 here collapses to two. Ch. 4 uses three ([784](thesis.tex#L784) "The models separate into three performance tiers"). | Align to three: "organized into three tiers: an industry baseline (Naive), per-work-center statistical time-series (SES, ARIMA), and feature-based ML (Ridge, XGBoost)." |
| TS-0-2 | [234-235](thesis.tex#L234-L235) | Section intro is 2 sentences in 1 paragraph. | structure | Phase 1 §4.2 flagged `sec:ts_methods` as needing ≥2 intro paragraphs. | Add a second paragraph previewing the three subsections and naming the accuracy metrics that will be defined in §2.3.3. |

### D.1 §2.3.1 Statistical Baselines ([L237-256](thesis.tex#L237-L256))

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| SB-1 | [237](thesis.tex#L237) | Heading "Statistical Baselines (Naive, SES, and ARIMA)" | acronym | SES and ARIMA used in the heading before expansion. Ch.1 abstract AB-2 proposes defining them on first Abstract use; here the subsection body then expands SES at [244](thesis.tex#L244) and ARIMA at [246](thesis.tex#L246) using the reverse-acronym pattern. | Keep the heading as-is if acronyms are already defined in Abstract (per AB-2). Otherwise change to "Statistical Baselines: Naive, Simple Exponential Smoothing, and ARIMA". |
| SB-2 | [239](thesis.tex#L239) | "work-in-progress (WIP, the set of jobs that have been released to the shop floor but not yet completed), or operations already released by MRP" | acronym / tone | The parenthetical structure `(WIP, the set of jobs…)` is nonstandard; reads like WIP *is* the set rather than being defined *by* the set. | "work-in-progress (WIP) — jobs released to the shop floor but not yet completed — or operations already released by MRP". *Avoid em-dash per CLAUDE.md.* Better: "work-in-progress (WIP), defined as jobs released to the shop floor but not yet completed, or operations already released by MRP." |
| SB-3 | [244](thesis.tex#L244) | "Simple Exponential Smoothing (SES) Weights past observations exponentially" | acronym | In `\item[Simple Exponential Smoothing (SES)]` format, the definition is fine. But verify first SES use (heading [237](thesis.tex#L237)) is after this body expansion when the TOC is generated. Typically headings render before bodies; readers may encounter SES unexpanded. | If AB-2 applied, OK. Otherwise, change the heading to spell out first. |
| SB-4 | [244](thesis.tex#L244) | "Controlled by a smoothing parameter $\alpha \in (0, 1)$" | notation | `$\alpha$` here collides with `$\alpha$` used for Ridge regularization at [271-275](thesis.tex#L271-L275). Two different concepts, same symbol. | Use a different symbol for SES: e.g., $\alpha_{\text{SES}}$, or define SES smoothing as $\lambda$ and keep Ridge as $\alpha$. Document in a footnote on first use. |
| SB-5 | [246](thesis.tex#L246) | "\item[ARIMA] The Autoregressive Integrated Moving Average model follows the classical Box-Jenkins approach" | acronym | ARIMA used in the label before the body expansion — reverse acronym. Swap. | "\item[Autoregressive Integrated Moving Average (ARIMA)] follows the classical Box-Jenkins approach…" |
| SB-6 | [248-250](thesis.tex#L248-L250) | "\textbf{AR (p):} Models dependence on past values / \textbf{I (d):} Differencing to achieve stationarity / \textbf{MA (q):} Models dependence on past forecast errors" | notation | `p`, `d`, `q` are variables but appear in roman text, not math mode. | "\textbf{AR $(p)$:}", "\textbf{I $(d)$:}", "\textbf{MA $(q)$:}". |
| SB-7 | [252](thesis.tex#L252) | "Order $(p, d, q)$ is **auto-selected per work center using autocorrelation analysis**." | conceptual / numerical | **Contradicts Ch. 4** [723](thesis.tex#L723) which says `$(p,d,q)$ auto-selected by AIC`. Autocorrelation analysis is a manual diagnostic, not an automated selection criterion. | "Order $(p, d, q)$ is auto-selected per work center by minimum Akaike Information Criterion (AIC) using \texttt{pmdarima} \texttt{auto\_arima}." *Also defines AIC on first use — fixes Phase 1 §6 acronym flag.* |
| SB-8 | [255-256](thesis.tex#L255-L256) | Closing two sentences of §2.3.1 | tone | OK content. | Keep. |

### D.2 §2.3.2 Machine Learning on Tabular Data ([L258-287](thesis.tex#L258-L287))

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| ML-1 | [260](thesis.tex#L260) | "historical lag features (i.e., past observed values of the target series at preceding time steps $t-1$, $t-2$, etc.)" | tone | "etc." after listing `t-1, t-2` is redundant. | "historical lag features (past observed values at preceding time steps, e.g., $t{-}1$, $t{-}2$)" |
| ML-2 | [262](thesis.tex#L262) | "Before presenting the two specific models used in this thesis, it is worth distinguishing two complementary ideas that feature-based ML relies on." | tone / AI-smell | "It is worth" is weak scaffolding. | "Two complementary ideas underpin feature-based ML:" |
| ML-3 | [262](thesis.tex#L262) | Paragraph is 4 sentences, 95 words total. | tone | Dense but acceptable. Consider splitting the final sentence. | Split "Selecting one representative from each family makes it possible to disentangle the accuracy contribution of feature engineering from the contribution of model complexity." into a standalone paragraph linking to the model choice rationale at [287](thesis.tex#L287). |
| ML-4 | [271-275](thesis.tex#L271-L275) | Ridge formula and explanation. | notation | `$\alpha$` symbol conflicts with SES smoothing at [244](thesis.tex#L244). See SB-4. | Apply SB-4 disambiguation (use $\alpha_{\text{SES}}$ for SES and keep $\alpha$ for Ridge). |
| ML-5 | [275](thesis.tex#L275) | "The penalty shrinks coefficients toward zero, which stabilizes estimates when predictors are correlated (for example, when several lag and rolling-mean features encode similar autocorrelation structure) and reduces variance at the cost of a small bias~\cite{hastie2009elements}." | tone | 34-word sentence with a long parenthetical. | Split: "The penalty shrinks coefficients toward zero, which stabilizes estimates when predictors are correlated, for example when several lag and rolling-mean features encode similar autocorrelation structure. This reduces variance at the cost of a small bias~\cite{hastie2009elements}." |
| ML-6 | [278](thesis.tex#L278) | "XGBoost is a scalable implementation of gradient boosting that fits an additive ensemble of shallow regression trees~\cite{chen2016xgboost}." | tone | OK. | Keep. |
| ML-7 | [279-285](thesis.tex#L279-L285) | XGBoost formula + explanation. | notation | Formula OK. Explanation is dense but acceptable. Verify `$\gamma T + \tfrac{1}{2}\lambda \lVert w \rVert_2^{\,2}$` matches Chen 2016 notation. | Keep; verify citation details. |
| ML-8 | [285](thesis.tex#L285) | "Because trees handle axis-aligned splits, categorical encodings, and feature interactions natively, gradient-boosted trees tend to outperform deep neural networks on structured tabular data of the size considered in this thesis~\cite{grinsztajn2022, shwartzziv2022tabular}." | tone | 33 words — OK. "Of the size considered" is vague; name the scale. | "...on structured tabular data at the sample sizes used in this thesis (~2{,}120 training rows; see Section~\ref{sec:research_design})~\cite{grinsztajn2022, shwartzziv2022tabular}." |
| ML-9 | [287](thesis.tex#L287) | "XGBoost and Ridge Regression were selected to span the model complexity spectrum" | tense | `were selected` (past) is inconsistent with the present-tense framing elsewhere in §2.3 ("XGBoost is…", "Ridge... extends..."). | "XGBoost and Ridge Regression span the model-complexity spectrum in this thesis:" |

### D.3 §2.3.3 Forecast Accuracy Metrics ([L289-308](thesis.tex#L289-L308))

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| FA-1 | [291](thesis.tex#L291) | "three standard regression and forecasting metrics: Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and the coefficient of determination ($R^2$)" | acronym | MAE, RMSE, $R^2$ are already defined in RQ1 at [133](thesis.tex#L133). Re-definition is an IEEE violation. | Drop parentheticals: "three standard metrics: MAE, RMSE, and $R^2$, as defined in Section~\ref{sec:research_questions}~\cite{hyndman2021,hastie2009elements}." |
| FA-2 | [302](thesis.tex#L302) | "MAE measures the average absolute error in the target scale" | tone | `in the target scale` → `on the target scale`. | "MAE measures the average absolute error on the target scale…" |
| FA-3 | [304](thesis.tex#L304) | **"Percentage-based errors such as MAPE are excluded from comparative model evaluation in this thesis, even though they were mentioned in the proposal. In weekly work-center forecasting, low-load or idle weeks create near-zero (and sometimes zero) targets, which makes percentage errors unstable or undefined and can distort model ranking~\cite{hyndman2021}. Therefore, model comparisons in this thesis use only $R^2$, MAE, and RMSE, and MAPE is not used for model ranking or reported in comparative result tables."** | MAPE / scope / tone | **Two combined problems.** (1) Phase 1 M1 mandates removal of all MAPE mentions. (2) "Even though they were mentioned in the proposal" references the Exposé, which CLAUDE.md scope-locks: "The Expose is dead. Do not reference its methodology, models, or scope." (3) Entire paragraph is defensive boilerplate, 72 words for a single methodological stance. | **Delete the entire paragraph.** MAPE does not need to be justified as excluded — simply define only the three metrics used. If the user wants to retain a short note on why percentage metrics are unstable for this task, use: "Percentage-based metrics are unsuitable here because near-zero or zero-load weeks make them unstable or undefined~\cite{hyndman2021}." (18 words; no MAPE, no Exposé.) |
| FA-4 | [306](thesis.tex#L306) | "Ranking decisions prioritize $R^2$ as the primary comparative metric, use MAE for operational interpretability of typical error magnitude, and use RMSE to assess sensitivity to occasional large misses." | tone | Parallel verbs OK but 32-word sentence. Acceptable. | Keep. |
| FA-5 | [308](thesis.tex#L308) | "decision-oriented reliability views (forecast error within fixed shift-based tolerance bands) and with disaggregated per-work-center diagnostics" | conceptual | Mentions `shift-based tolerance bands` and `per-work-center diagnostics` — forward references to Ch. 4 §4.5. | Add cross-reference: "decision-oriented reliability views (forecast error within fixed shift-based tolerance bands, Section~\ref{subsec:rq1_operational}) and disaggregated per-work-center diagnostics (Section~\ref{subsec:rq1_per_wc})". |
| FA-6 | §2.3.3 structure | Subsection is 4 paragraphs + 3 equations. No subsection-level issues beyond FA-3. | OK | Keep after MAPE removal. |

---

## E. §2.4 Data Quality and Methodological Risks ([thesis.tex:310-355](thesis.tex#L310-L355))

### E.0 Section intro ([L312](thesis.tex#L312))

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| DQ-0-1 | [312](thesis.tex#L312) | 1-paragraph section intro. | structure | Phase 1 §4.2 flagged `sec:data_quality` as needing ≥2 intro paragraphs. | Add a second paragraph preview: "Subsection~\ref{subsec:missingness} reviews Rubin's missingness taxonomy and the mechanism adopted here; Subsection~\ref{subsec:leakage} defines data leakage; Subsection~\ref{subsec:cv_ts} describes the time-aware evaluation protocols used throughout Chapter~\ref{chap:methodology}." |

### E.1 §2.4.1 Missingness Mechanisms ([L314-339](thesis.tex#L314-L339))

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| DQ-1-1 | [316](thesis.tex#L316) | "Following Rubin's taxonomy~\cite{rubin1973, little2002statistical}, missing data in industrial systems is categorized into three mechanisms:" | cross-ref | No reference to Table~\ref{tab:missingness_mechanisms} in prose. Phase 1 §5.1 flagged this table as unused. | "Following Rubin's taxonomy~\cite{rubin1973, little2002statistical}, missing data in industrial systems is categorized into three mechanisms, summarized in Table~\ref{tab:missingness_mechanisms}:" |
| DQ-1-2 | [319](thesis.tex#L319) | "This is the safest case, as simple imputation strategies such as mean or median substitution remain unbiased without causing errors in model training and evaluation." | tone | "Without causing errors" is imprecise. | "remain unbiased and do not distort model training or evaluation." |
| DQ-1-3 | [320](thesis.tex#L320) | "The gap is conditioned on an observed field such as a downtime event flag, making it MAR." | tone | Short, OK. | Keep. |
| DQ-1-4 | [321](thesis.tex#L321) | "MNAR cannot be corrected without external domain knowledge and must be acknowledged as a limitation." | tone | OK. | Keep. |
| DQ-1-5 | [324-337](thesis.tex#L324-L337) | Table 1 (tab:missingness_mechanisms) | cross-ref / caption | Table is now referenced once DQ-1-1 is fixed. Caption is self-contained — OK. | Apply DQ-1-1. |
| DQ-1-6 | [339](thesis.tex#L339) | "Statistical testing rejects MCAR on the dataset, and conditional missingness rates grouped by work center and shift confirm the MAR pattern." | logic / citation | Asserts a statistical test without naming it (Little's MCAR test). No citation or reference to where in the notebooks the test was run. | "Little's MCAR test~\cite{little1988test} rejects MCAR on the dataset (notebook \texttt{02\_preprocessing.ipynb}), and conditional missingness rates grouped by work center and shift confirm the MAR pattern." *Requires adding the citation to references.bib.* |
| DQ-1-7 | [339](thesis.tex#L339) | "a domain-informed zero fill for the scrap field (where a missing scrap entry in ERP practice denotes no scrap reported rather than an unknown value)" | tone | Verbose parenthetical. | "a domain-informed zero fill for the scrap field, since missing scrap in ERP practice denotes no scrap reported rather than an unknown value." |

### E.2 §2.4.2 Data Leakage ([L341-345](thesis.tex#L341-L345))

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| DQ-2-1 | [343](thesis.tex#L343) | "Data leakage is a methodological failure in which a model is trained on information that would not be available at the forecast origin in a real deployment~\cite{sasse2025leakage}." | tone | 28 words, OK. | Keep. |
| DQ-2-2 | [345](thesis.tex#L345) | "An earlier exploratory setup that contained leakage reached $R^2 \approx 0.98$; the corrected pipeline, with the forecast-origin constraint strictly enforced, yields $R^2 = 0.355$, which is lower but reflects honest out-of-sample performance." | conceptual / scope / numerical | (1) "An earlier exploratory setup" is a veiled Exposé reference — user must decide whether to keep it per CLAUDE.md scope-lock. (2) $R^2 = 0.355$ canonical is $0.3546$; rounding OK at 3dp. (3) $R^2 \approx 0.98$ is the contaminated baseline — verify this number is recorded in a notebook the committee can inspect. | If user accepts referencing prior work: reframe neutrally — "A preliminary pipeline without the forecast-origin constraint reached $R^2 \approx 0.98$ on the same test panel; the corrected pipeline, with the constraint strictly enforced, yields $R^2 = 0.355$ — a substantial reduction that reflects honest out-of-sample performance." *Avoid em-dash:* use a comma or colon. Otherwise **delete the sentence entirely**, since the honest corrected number ($R^2 = 0.355$) is reported in Ch. 4 without needing the leakage contrast. Flag for user decision. |
| DQ-2-3 | §2.4.2 structure | Subsection is 2 paragraphs, 6 sentences total. | structure | Thin but acceptable for a focused methodological subsection. | Keep. |

### E.3 §2.4.3 Evaluation Protocols ([L347-355](thesis.tex#L347-L355))

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| DQ-3-1 | [349](thesis.tex#L349) | "A standard $k$-fold cross-validation shuffles observations independently of time and is therefore unsuitable for forecasting tasks: it allows a model to be trained on weeks that occur \emph{after} the weeks it is evaluated on, which is another manifestation of the forecast-origin violation discussed above~\cite{cerqueira2020evaluating}." | tone | 43 words. Split. | "Standard $k$-fold cross-validation shuffles observations independently of time and is therefore unsuitable for forecasting tasks. It allows a model to train on weeks that occur \emph{after} the weeks it is evaluated on, which is another form of the forecast-origin violation discussed above~\cite{cerqueira2020evaluating}." |
| DQ-3-2 | [353](thesis.tex#L353) | "week-blocked five-fold cross-validation on the training set is used both to select hyperparameters for the feature-based models (Ridge and XGBoost) and as a stability check on the single chronological holdout" | acronym | CV first mentioned here in context of cross-validation. Phase 1 §6 flagged `CV` ambiguous. | "week-blocked five-fold cross-validation (CV) on the training set is used both to select hyperparameters…" (reserving `CV` for cross-validation; use "coefficient of variation" spelled out wherever needed in Ch. 4). |
| DQ-3-3 | [353](thesis.tex#L353) | "The spread of scores across folds provides a practical estimate of how sensitive a given model is to the specific train/test cut-off." | tone | OK, slight wordiness. | "The spread of scores across folds estimates how sensitive a model is to the train/test cut-off." |
| DQ-3-4 | [355](thesis.tex#L355) | "An earlier exploratory setup that mistakenly shuffled work-center-weeks produced optimistic scores precisely because it allowed cross-week (and, indirectly, cross-work-center) information flow; the contrast with the corrected protocols is documented in Section~\ref{subsec:leakage}." | conceptual / scope | Second reference to "earlier exploratory setup" in §2.4 (also at [345](thesis.tex#L345)). Per CLAUDE.md scope-lock, re-evaluate. | If DQ-2-2 is kept, keep this too with consistent framing. If DQ-2-2 is deleted, delete this sentence too. Both stand or fall together. |

---

## F. Chapter 2 Cross-Cutting Findings

| # | Finding | Action |
|---|---|---|
| XC-1 | **MAPE in Ch. 2:** FA-3 is the only MAPE occurrence in Ch. 2 (matches Phase 1 M1 at [304](thesis.tex#L304)). Delete that paragraph. | Apply FA-3. |
| XC-2 | **Em-dashes in Ch. 2 prose:** none found. | OK. |
| XC-3 | **British-US in Ch. 2:** none found. Ch. 2 uses American spelling throughout. | OK. |
| XC-4 | **AI-smell in Ch. 2:** `it is worth` (ML-2), vague sentence openers mild but not egregious. No `Moreover`, `Furthermore`, `Additionally`, `Taken together`, `leverage`, `delve`, `pivotal`, `crucial`, `paramount` detected. | Fix ML-2. |
| XC-5 | **Acronym hygiene:** MRP II / MRP-II still inconsistent (PPH-3, PPH-4); FG/SFG/RAW defined but never reused (PPH-6); SES/ARIMA introduction patterns (SB-1, SB-5); MAE/RMSE/$R^2$ re-defined (FA-1); AIC not defined (SB-7 fixes). | Apply PPH-3/4, PPH-6, SB-1, SB-5, SB-7, FA-1. |
| XC-6 | **Tier-count inconsistency (two vs three tiers):** TS-0-1. Affects Ch. 1 §1.4 framing coherence. | Apply TS-0-1. |
| XC-7 | **ARIMA order selection method inconsistency:** SB-7 (autocorrelation analysis vs AIC). Methodology must agree between §2.3.1 and Ch. 4 table. | Apply SB-7. |
| XC-8 | **Symbol clash $\alpha$:** SES smoothing ([244](thesis.tex#L244)) and Ridge regularization ([271](thesis.tex#L271)). | Apply SB-4 / ML-4. |
| XC-9 | **Exposé references in Ch. 2:** FA-3 ("mentioned in the proposal"), DQ-2-2 ("earlier exploratory setup"), DQ-3-4 ("earlier exploratory setup"). Three occurrences. **User decision required.** | Decide: remove all three, or keep as honest reporting without naming the Exposé. |
| XC-10 | **Cross-reference integrity:** tab:missingness_mechanisms now referenced once DQ-1-1 applied; no other broken refs. | Apply DQ-1-1. |
| XC-11 | **Section-intro thinness:** §2.1 (PPH-1), §2.3 (TS-0-2), §2.4 (DQ-0-1). | Add second intro paragraph to each. |
| XC-12 | **Tense discipline:** §2.3.2 has one past-tense outlier (ML-9). Otherwise consistent. | Apply ML-9. |
| XC-13 | **Citation density:** 15 citations across Ch. 2 (L198, L198, L201, L212, L213, L220×2, L226, L227, L244, L246, L262, L265, L275, L278, L285, L291, L304, L312, L316, L343, L349, L353). Dense and well-placed. | OK. |
| XC-14 | **Numerical consistency:** $R^2 = 0.355$ at [345](thesis.tex#L345) matches canonical $0.3546$ rounded; `$R^2 \approx 0.98$` unverified (exploratory; not in canonical nb04/05). | DQ-2-2 flags for user decision. |

---

## Chapter 2 Summary (user checklist)

**Preamble:** CH2-1 to CH2-6 (6 issues). Notable: rewrite passive opener; fix Oxford comma; "rules out" → "prevents".

**§2.1 Production Planning Hierarchy:** PPH-1 to PPH-13 (13 issues). Notable: add second intro paragraph (PPH-1); global MRP II decision (PPH-3, PPH-4); FG/SFG/RAW usage audit (PPH-6); fix singular/plural `hours that is` (PPH-10); extend Fig. 1 caption (PPH-9).

**§2.2 PCC:** PCC-1 to PCC-6 (6 issues). Notable: decide PCC definition location (Ch.1 vs here); standardize equation reference style (PCC-4); add §2.3 bridge (PCC-6).

**§2.3 Time-Series Methods:** TS-0-1, TS-0-2, SB-1 to SB-8, ML-1 to ML-9, FA-1 to FA-6 (27 issues). Notable:
- **Tier-count alignment (TS-0-1)** — match Ch. 1 and Ch. 4.
- **ARIMA selection method (SB-7)** — correct "autocorrelation analysis" to "AIC via pmdarima auto_arima". Defines AIC on first use.
- **$\alpha$ symbol clash (SB-4/ML-4)** — rename SES smoothing symbol.
- **ARIMA reverse acronym (SB-5)** — swap `\item[ARIMA]` to `\item[Autoregressive Integrated Moving Average (ARIMA)]`.
- **MAPE defense paragraph (FA-3)** — delete entire paragraph at [304](thesis.tex#L304).

**§2.4 Data Quality:** DQ-0-1, DQ-1-1 to DQ-1-7, DQ-2-1 to DQ-2-3, DQ-3-1 to DQ-3-4 (15 issues). Notable:
- Reference tab:missingness_mechanisms in prose (DQ-1-1).
- Cite Little's MCAR test (DQ-1-6) — requires bib addition.
- **Decide on Exposé "earlier exploratory setup" references (DQ-2-2, DQ-3-4).** Remove all three (FA-3, DQ-2-2, DQ-3-4) if enforcing scope-lock strictly.
- Define CV acronym on first use (DQ-3-2).

**Cross-cutting:** XC-1 to XC-14 (14 observations). No MAPE beyond FA-3; no em-dashes; Ch. 2 is clean US English.

**Total Chapter 2 issues:** ~67 flagged.

---

### Items requiring user decisions before Ch. 3 review

1. **MRP-II vs MRP II** — apply one form globally (this is also pending from Ch. 1 P1-3). Recommend `MRP II`.
2. **"Earlier exploratory setup" / "the proposal" references** (FA-3, DQ-2-2, DQ-3-4). Three options: (a) delete all three, (b) retain DQ-2-2 and DQ-3-4 as neutral "preliminary pipeline" phrasing, delete FA-3, (c) keep all three. CLAUDE.md lean suggests (a) or (b).
3. **Tier count: two vs three tiers** (TS-0-1). Recommend three tiers to match Ch. 1 and Ch. 4.
4. **PCC definition placement** (PCC-1). Recommend Ch. 1 preamble defines, §2.2 is the formal definition without re-parenthesizing.
5. **$\alpha$ disambiguation** (SB-4 / ML-4). Recommend keeping Ridge as $\alpha$ and renaming SES to $\alpha_{\text{SES}}$ or $\lambda_{\text{SES}}$.

Once these five are decided, the remaining ~62 issues are mechanical fixes.

---

**Next:** Ch. 3 Related Work ([thesis.tex:360-470](thesis.tex#L360-L470)) after user confirms Ch. 2 findings.