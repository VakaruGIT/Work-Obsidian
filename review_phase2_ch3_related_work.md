# Phase 2 — Chapter 3 Deep Review: Related Work

**Source:** [thesis.tex:360-466](thesis.tex#L360-L466)
**Sections:** Preamble (L362-366), §3.1 ML in Manufacturing Forecasting, §3.2 DL vs. Traditional on Tabular, §3.3 Synthetic Data in Manufacturing Research, §3.4 Research Gaps.
**Each issue:** Location · Quoted span · Category · Why flagged · Proposed rewrite.

User reviews before Ch. 4 begins.

---

## A. Chapter 3 Preamble ([thesis.tex:362-366](thesis.tex#L362-L366))

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| CH3-1 | [362](thesis.tex#L362) | "This chapter reviews the existing literature across three areas that together motivate the thesis and position of its contribution." | tone / typo | `position of its contribution` — should be `position its contribution`. Also three areas claimed but §3.4 Research Gaps is a fourth section. | "This chapter reviews the existing literature across three substantive areas and then distills the four research gaps this thesis addresses." |
| CH3-2 | [363](thesis.tex#L363) | "Section~\ref{sec:rw_manufacturing} **researches** machine learning applications in manufacturing" | tone / grammar | "Researches" is wrong — a section cannot research. | "Section~\ref{sec:rw_manufacturing} **reviews** machine learning applications in manufacturing and adjacent forecasting domains…" |
| CH3-3 | [363](thesis.tex#L363) | "showing that no single model universally dominates and that none of the reviewed studies targets capacity consumption as a prediction task" | tone | 19-word subordinate clause inside a 34-word sentence. Acceptable, but dense. | Consider splitting into two sentences, but acceptable if kept. |
| CH3-4 | [364](thesis.tex#L364) | "demonstrating that tree-based and linear models outperform neural architectures on small datasets and that feature engineering contributes more to accuracy than model complexity" | tone | OK content, 23 words in subordinate clause. | Keep. |
| CH3-5 | [366](thesis.tex#L366) | "Section~\ref{sec:rw_gaps} identifies the four research gaps that this thesis addresses." | tone | Short summary sentence OK. | Keep. |
| CH3-6 | Overall | Preamble is one paragraph of 5 sentences. | structure | Adequate for a chapter roadmap. No second paragraph needed. | Keep structure. |

---

## B. §3.1 ML in Manufacturing Forecasting ([thesis.tex:368-402](thesis.tex#L368-L402))

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| MF-1 | [368](thesis.tex#L368) | Section heading "ML in Manufacturing Forecasting" | acronym / style | Section headings elsewhere use full forms ("Machine Learning on Tabular Data" at §2.3.2). Convention should be consistent across chapters. | "Machine Learning in Manufacturing Forecasting" |
| MF-2 | [370](thesis.tex#L370) | "Machine learning has been widely applied to time-series forecasting across domains adjacent to manufacturing capacity planning, including demand forecasting, energy load forecasting, and financial forecasting." | tone | 26 words, four `forecasting` repetitions. | "Machine learning has been widely applied to time-series forecasting across adjacent domains: demand, energy load, and finance." |
| MF-3 | [372](thesis.tex#L372) | "Menculini et al.~\cite{menculini2021} compared the **Prophet model and deep learning models** against ARIMA on wholesale food price series" | tone / citation | "Prophet model and deep learning models" reads awkwardly due to double "model(s)". Also `Prophet` is used for the first time without citation or definition. This is the ideal place to cite `taylor2018prophet` — an orphan bib entry in Phase 1 §9.1. | "Menculini et al.~\cite{menculini2021} compared Prophet~\cite{taylor2018prophet} and several deep-learning models against ARIMA on wholesale food-price series. They found that no single model dominates across series, while ARIMA remains a competitive baseline on short or stationary sequences." |
| MF-4 | [373](thesis.tex#L373) | "Albahli~\cite{albahli2025} evaluated Long Short-Term Memory (LSTM) networks against Prophet" | acronym | LSTM introduced correctly (full form first). | Keep. |
| MF-5 | [374](thesis.tex#L374) | "Sherly et al.~\cite{A2025105703} explored a hybrid approach combining ARIMA and Prophet, showing that the complementary strengths of both models produce more robust forecasts than either model alone on non-stationary data." | tone | 31 words, acceptable. | Keep. |
| MF-6 | [375](thesis.tex#L375) | "Across these studies, a consistent observation emerges: model performance is highly data-dependent and no universally superior architecture exists~\cite{hyndman2021}." | tone / AI-smell | "A consistent observation emerges" is anthropomorphic scaffolding. | "These studies consistently show that model performance is highly data-dependent, with no universally superior architecture~\cite{hyndman2021}." |
| MF-7 | [377](thesis.tex#L377) | "Within manufacturing specifically, machine learning has been applied primarily to operational metrics rather than capacity consumption." | tone | "Within manufacturing specifically" redundant (chapter is titled Related Work in manufacturing). | "Within manufacturing, machine learning has targeted operational metrics rather than capacity consumption." |
| MF-8 | [378](thesis.tex#L378) | "Flores-Huam{\'a}n et al.~\cite{flores-huaman2024lead} applied machine learning to lead-time prediction in wind tower manufacturing and found that feature-based models outperform autoregressive baselines when process-level features are included." | tone | 32 words, OK. Strong evidence of thesis's own argument from another domain. | Keep. |
| MF-9 | [379](thesis.tex#L379) | "Belmouadden et al.~\cite{belmouadden2025decision} developed a real-time decision support system for capacity optimization in multi-product process manufacturing, demonstrating that data-driven approaches can capture shop-floor variability that deterministic planning methods miss." | tone | 33 words, OK. | Keep. |
| MF-10 | [381-398](thesis.tex#L381-L398) | Table 2 `tab:related_work_summary` | cross-ref | Phase 1 §5.1 flagged this table as unreferenced in prose. | Add at end of [379](thesis.tex#L379): "Table~\ref{tab:related_work_summary} summarizes the reviewed studies alongside this thesis." |
| MF-11 | [383](thesis.tex#L383) | Table 2 caption: "Overview of selected related work in manufacturing and time-series forecasting." | caption | Caption is generic; could state what the comparison axis is (target variable + key finding). | "Selected related work in manufacturing and time-series forecasting: key findings and target variables, with this thesis's contribution in the final row." |
| MF-12 | [390-394](thesis.tex#L390-L394) | Table rows use `et al.` with `~\cite{}` | cross-ref | Consistent — OK. | Keep. |
| MF-13 | [395](thesis.tex#L395) | Table row "\textbf{This thesis} & \textbf{Planning-state features are the decisive ML enabler; feature value $>$ model complexity} & \textbf{Capacity consumption (machine-hours)}" | tone | `feature value $>$ model complexity` uses math symbol for a qualitative comparison. | "Planning-state features outperform model complexity as the accuracy driver" |
| MF-14 | [400](thesis.tex#L400) | "These studies share a key limitation: they either operate on univariate time series without access to forward-looking planning information, or they target operational metrics such as lead time and defect rate rather than actual machine-hour consumption." | tone | 35 words, OK. | Keep. |
| MF-15 | [401](thesis.tex#L401) | "No reviewed study includes planning-state features (such as the open order backlog or work-in-progress at a work center) as predictors, and no study frames the forecasting of actual machine-hours per work center per week as a supervised regression problem on a tabular feature matrix." | tone | 44-word sentence; two distinct claims fused. | Split: "No reviewed study includes planning-state features (such as the open order backlog or work-in-progress at a work center) as predictors. Nor does any study frame the forecasting of actual machine-hours per work center per week as a supervised regression problem on a tabular feature matrix." |
| MF-16 | [402](thesis.tex#L402) | "This thesis extends the comparison to include feature-based ML models alongside statistical baselines and demonstrates that planning-state features are the decisive factor in enabling ML to outperform autoregressive models: without them, XGBoost ($R^2 = 0.204$) is outperformed by ARIMA ($R^2 = 0.271$); with them, XGBoost reaches $R^2 = 0.355$, showing that the value lies in the features, not in model complexity." | tone / redundancy | 63-word sentence; duplicates the finding already stated in Ch. 1 §1.4 [150](thesis.tex#L150), Ch. 5 §5.1 [987](thesis.tex#L987), Abstract [38-39](thesis.tex#L38-L39), and Gap 2 [447](thesis.tex#L447). Repetition risk. | Tighten: "This thesis addresses both limitations: it adds feature-based ML models alongside statistical baselines and isolates, by ablation, the role of planning-state features — the mechanism that lifts XGBoost from $R^2 = 0.204$ (below ARIMA) to $R^2 = 0.355$ (best model)." *Avoid em-dash:* "…isolates by ablation the role of planning-state features, the mechanism that lifts XGBoost from $R^2 = 0.204$ (below ARIMA at $0.271$) to $R^2 = 0.355$ (best model)." |

---

## C. §3.2 Deep Learning vs. Traditional Models on Tabular Data ([thesis.tex:405-421](thesis.tex#L405-L421))

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| DL-1 | [407](thesis.tex#L407) | "Grinsztajn et al.~\cite{grinsztajn2022} **revealed** that tree-based models outperformed neural networks across 45 datasets." | tone | "Revealed" is dramatic. | "Grinsztajn et al.~\cite{grinsztajn2022} showed that tree-based models outperformed neural networks across 45 datasets." |
| DL-2 | [407](thesis.tex#L407) | "the tree-based models had a significant advantage" | tone | Definite article unnecessary; "significant" used in the colloquial sense (not the statistical sense). | "tree-based models held a clear advantage" |
| DL-3 | [407](thesis.tex#L407) | "The authors attribute this to properties of tabular data that **favour** tree-based inductive biases" | British-US | **British spelling** `favour`. Ch. 3 otherwise uses US English; Phase 1 §3 flags Ch. 1-3 as US. | "The authors attribute this to properties of tabular data that **favor** tree-based inductive biases" |
| DL-4 | [407](thesis.tex#L407) | "including non-smooth decision boundaries and rotational non-invariance, properties that neural networks struggle to handle without large amounts of training data" | tone | "Struggle to handle" anthropomorphizes NNs. Also sentence cumulative length is 53 words. | Split after `rotational non-invariance.`: "These properties cannot be efficiently learned by neural networks without very large training sets." |
| DL-5 | [409](thesis.tex#L409) | "**The research from** Shwartz-Ziv and Armon~\cite{shwartzziv2022tabular} reached a similar conclusion." | tone | "The research from X" is awkward scaffolding. | "Shwartz-Ziv and Armon~\cite{shwartzziv2022tabular} reached a similar conclusion:" |
| DL-6 | [409](thesis.tex#L409) | "The study argued that the research community's focus on deep learning for tabular data may be misplaced." | tone / hedging | OK. "May be misplaced" is calibrated hedging. | Keep. |
| DL-7 | [409](thesis.tex#L409) | "Together with the evidence from Grinsztajn et al.~\cite{grinsztajn2022}, this suggests that careful feature engineering and preprocessing often deliver larger gains than increasing model complexity alone." | citation | Re-cites `grinsztajn2022` in the same paragraph, two sentences after the initial cite. IEEE style tolerates repetition for clarity, but consider: "Together with the evidence above,…" | "Together with the evidence above, this suggests that careful feature engineering and preprocessing often deliver larger gains than increasing model complexity alone." |
| DL-8 | [411](thesis.tex#L411) | "In the manufacturing industry, features like work center identifiers, shift indicators and planning-state quantities, being heterogeneous and interacting in complex ways, are much better captured by tree-based models than by neural networks." | tone | 35-word sentence with a `being …` participle clause that reads awkwardly. Missing Oxford comma before `and planning-state quantities`. | "In manufacturing, features such as work-center identifiers, shift indicators, and planning-state quantities are heterogeneous and interact in complex ways. Tree-based models capture these interactions more effectively than neural networks." |
| DL-9 | [411](thesis.tex#L411) | "With just 2,120 training rows across 20 different work centers, the dataset synthetically generated for this thesis falls within the regime where tree-based models hold a structural advantage~\cite{grinsztajn2022}." | numerical | Verify `2,120 training rows`. Panel is 3,040 WC-weeks; drop first 5 weeks per WC (20 × 5 = 100) gives 2,940; 70% train = 2,058. Alternatively (3,040 − 100) × (weeks in train block / total weeks) must reconcile. Does `2,120` match nb04/05? Flag for user verification against canonical split sizes. | After verification, either (a) correct the number, or (b) state the actual split size. If canonical `2,120` is the correct figure, add a footnote or Section-reference: "With 2,120 training rows across 20 work centers (Section~\ref{sec:research_design}), the dataset falls within the regime…" |
| DL-10 | [413](thesis.tex#L413) | "Beyond raw accuracy, interpretability is a practical requirement for production planning tools." | tone | OK bridging sentence. | Keep. |
| DL-11 | [414](thesis.tex#L414) | "Ridge Regression produces one coefficient per feature, directly expressing the marginal contribution of each planning signal to the forecast~\cite{hastie2009elements}." | style | Capitalization `Ridge Regression` — elsewhere the thesis uses `Ridge regression` (e.g. Ch. 1 RQ2 [135](thesis.tex#L135)) and also `Ridge Regression` (Ch. 2 [275](thesis.tex#L275)). Choose one. | Standardize to `Ridge regression` (sentence case for the second word) per IEEE and typical ML literature. Apply globally. |
| DL-12 | [415](thesis.tex#L415) | "XGBoost supports **SHAP-based** feature importance~\cite{lundberg2017shap}, enabling planners to understand which signals drive each individual prediction." | acronym | SHAP is first used here without expansion. | "XGBoost supports SHapley Additive exPlanations (SHAP) feature importance~\cite{lundberg2017shap}, enabling planners to see which signals drive each individual prediction." |
| DL-13 | [416](thesis.tex#L416) | "Deep learning models such as LSTM~\cite{hochreiter1997lstm} offer no comparable transparency without significant additional tooling." | tone | OK. | Keep. |
| DL-14 | [416](thesis.tex#L416) | Trailing whitespace after sentence. | typo / style | Remove. |
| DL-15 | [417](thesis.tex#L417) | "For an operational deployment where planners must justify and act on forecasts, this interpretability gap is a practical reason to prefer tree-based and linear models over neural architectures, independent of accuracy considerations." | tone | 35 words, acceptable. `independent of accuracy considerations` is slightly awkward. | "…a practical reason to prefer tree-based and linear models, independent of accuracy." |
| DL-16 | [419-420](thesis.tex#L419-L420) | "These findings are directly relevant to this thesis. The dataset used here is structured tabular data with **2,120 training rows**, well within the regime where the literature predicts tree-based and linear models to outperform deep learning." | redundancy | The `2,120 training rows` claim already appeared at [411](thesis.tex#L411). Restating within a dozen lines is redundant. | Trim: "These findings motivate the model selection in this thesis: interpretable linear and tree-based models on structured tabular data, alongside statistical time-series baselines (see Section~\ref{sec:modeling})." — consolidates DL-16 and DL-17. |
| DL-17 | [420](thesis.tex#L420) | "This expectation is consistent with the model-design rationale used in this thesis: the main comparison emphasizes interpretable linear and tree-based approaches on structured tabular data, alongside statistical time-series baselines." | redundancy | Duplicates content with [287](thesis.tex#L287) in Ch. 2. | Fold into DL-16 rewrite. |

---

## D. §3.3 Synthetic Data in Manufacturing Research ([thesis.tex:423-430](thesis.tex#L423-L430))

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| SD-1 | [425](thesis.tex#L425) | Blank line after `\section{…}` and before first body paragraph creates an extra vertical gap. | style | Minor — inconsistent with §3.1 opening (no extra blank line at [369](thesis.tex#L369)). | Remove the extra blank line at [425](thesis.tex#L425). |
| SD-2 | [426](thesis.tex#L426) | "Even when access is granted, the data is often anonymized to the point where controlled experiments become infeasible or **companies expect results with guaranteed quality**." | tone / logic | "Companies expect results with guaranteed quality" is unclear — the "or" implies it's a separate reason, but what does it mean? | "Even when access is granted, the data is often anonymized to the point where controlled experiments become infeasible, or the data owner imposes confidentiality restrictions that prevent publication of full pipelines." (verify this matches your actual intent; if not, rephrase with a clear alternative) |
| SD-3 | [426](thesis.tex#L426) | "Buggineni et al.~\cite{buggineni2024synthetic} note that synthetic data generation is increasingly adopted in manufacturing research as a solution to data scarcity, enabling researchers to create artificial datasets for training and evaluating ML models when real production data is insufficient or unavailable." | tone | 40-word sentence. Acceptable but long. "Artificial datasets" and "synthetic data" are used inconsistently in the same sentence. | "Buggineni et al.~\cite{buggineni2024synthetic} note that synthetic data generation is increasingly adopted in manufacturing research to address data scarcity: researchers can train and evaluate ML models when real production data is unavailable." |
| SD-4 | [426](thesis.tex#L426) | "Liaskovska et al.~\cite{liaskovska2025synthetic} further demonstrate that synthetic production data calibrated to domain benchmarks is a valid basis for evaluating optimization and forecasting methods in **Industry 5.0** contexts, provided the synthetic data-generating process is documented and validated." | conceptual / citation | `Industry 5.0` is introduced without a citation or definition. The thesis's broader framing is Industry 4.0 (cited in Ch. 1 [99](thesis.tex#L99) via `\cite{VAIDYA2018233}`). Mixing 4.0 and 5.0 without distinction is confusing. | "Liaskovska et al.~\cite{liaskovska2025synthetic} further demonstrate that synthetic production data calibrated to domain benchmarks is a valid basis for evaluating optimization and forecasting methods in modern manufacturing contexts, provided the data-generating process is documented and validated." *(Remove `Industry 5.0` unless the thesis discusses it elsewhere — it does not.)* |
| SD-5 | [428](thesis.tex#L428) | "The specific advantage of synthetic data for this thesis is that it enables a controlled factorial experiment for RQ3 (Data Quality Sensitivity)" | tone | `specific advantage` mildly redundant. | "For this thesis, synthetic data enables a controlled factorial experiment for RQ3 (Data Quality Sensitivity):" |
| SD-6 | [428](thesis.tex#L428) | "This isolation of individual data quality effects is practically impossible with real production data, where multiple quality issues co-occur and cannot be disentangled." | tone | OK. | Keep. |
| SD-7 | [428](thesis.tex#L428) | "The synthetic dataset used here is generated via Discrete-Event Simulation (DES)~\cite{fishman2001des} and validated through **different** realism checks against known manufacturing benchmarks" | tone / acronym | (1) DES re-defined; already defined at Ch. 1 §1.4 [144](thesis.tex#L144). Drop the parenthetical. (2) "different realism checks" — `different` is vague. | "The synthetic dataset is generated via DES~\cite{fishman2001des} and validated through a realism scorecard of manufacturing-domain checks, described in Chapter~\ref{chap:methodology}." |
| SD-8 | [430](thesis.tex#L430) | "The use of synthetic data does not **promise** that the results can be transferred directly to any specific real factory." | tone | "Does not promise" personifies the dataset. | "The use of synthetic data does not guarantee that results transfer directly to a specific real factory." |
| SD-9 | [430](thesis.tex#L430) | "This thesis does not claim that synthetic data replaces real production data, but rather demonstrates a complete and reproducible methodology." | tone | OK. | Keep. |
| SD-10 | [430](thesis.tex#L430) | "The process pipeline is structured around a standard production event log schema: operations confirmations, routing master data, and orders, so that practitioners can substitute real exports for the synthetic input without modifying the pipeline logic." | redundancy | Duplicates Ch. 1 §1.4 SC-9 content at [149](thesis.tex#L149) almost verbatim. | "The pipeline is structured around a standard production event-log schema (see Section~\ref{sec:master_data}) so that practitioners can substitute real ERP exports for the synthetic input without modifying the logic." |
| SD-11 | [430](thesis.tex#L430) | "The methodology is the contribution, not the synthetic data itself." | redundancy | Same claim appears in Ch. 1. Fine here as closing statement, but ensure Ch. 1 is tightened (see SC-14). | Keep as §3.3 closer. |

---

## E. §3.4 Research Gaps ([thesis.tex:432-466](thesis.tex#L432-L466))

### E.1 Intro ([L434](thesis.tex#L434))

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| RG-0 | [434](thesis.tex#L434) | "The literature reviewed in this chapter reveals four gaps that motivate and define the scope of this thesis." | tone | OK. Single-sentence paragraph but it's an intro for an enumerated list, so acceptable. | Keep. |

### E.2 Gap 1 — Capacity consumption prediction is underexplored ([L438-442](thesis.tex#L438-L442))

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| RG-1-1 | [440](thesis.tex#L440) | "The task of forecasting actual machine-hours consumed per work center per week from confirmed production event logs, which is the quantity that CRP computes incorrectly using static routing assumptions, has received **almost no** dedicated study." | tone | (1) 38-word sentence with nested relative clause. (2) `almost no` colloquial. | "The task of forecasting actual machine-hours per work center per week from confirmed production event logs has received little dedicated study, despite being the quantity that CRP computes incorrectly using static routing assumptions." |
| RG-1-2 | [441-442](thesis.tex#L441-L442) | "None of the studies reviewed in Section~\ref{sec:rw_manufacturing} target this specific prediction task. The reviewed studies focus on demand volumes, energy consumption, or lead times. None of them model the actual machine-hours logged by confirmed shop-floor operations." | redundancy | Three consecutive sentences restating the same claim (`None of … / The reviewed studies focus … / None of them …`). | Consolidate: "The studies reviewed in Section~\ref{sec:rw_manufacturing} target demand volumes, energy consumption, or lead times — none model the actual machine-hours logged by confirmed shop-floor operations." *Avoid em-dash:* "…target demand volumes, energy consumption, or lead times; none model the actual machine-hours logged by confirmed shop-floor operations." |

### E.3 Gap 2 — Planning-state features have not been studied as an ML enabler ([L444-448](thesis.tex#L444-L448))

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| RG-2-1 | [445](thesis.tex#L445) | "Existing comparative studies evaluate model architectures on historical time-series data alone." | tone | OK. | Keep. |
| RG-2-2 | [446](thesis.tex#L446) | "No reviewed study includes forward-looking planning information (such as open order backlog, work-in-progress, or operations released but not yet started) as predictors, and no study isolates the contribution of such features through a controlled ablation experiment." | tone | 35 words, OK. Also `work-in-progress` unexpanded to WIP after earlier definition at [239](thesis.tex#L239). | "…(such as open order backlog, WIP, or operations released but not yet started)…" |
| RG-2-3 | [447](thesis.tex#L447) | "This thesis demonstrates that these features are the decisive factor: without them, XGBoost ($R^2 = 0.204$) is outperformed by ARIMA ($R^2 = 0.271$); with them, XGBoost reaches $R^2 = 0.355$." | redundancy | Third restatement of the same ablation numbers in Ch. 3 (also at [402](thesis.tex#L402) and [412](thesis.tex#L412)). | Consider trimming to avoid triple repetition. E.g., at this gap, reference Section~\ref{sec:rq2}: "This thesis demonstrates, through a controlled ablation in Section~\ref{subsec:rq2_ablation}, that planning features are the decisive factor: XGBoost moves from $R^2 = 0.204$ (below ARIMA) to $R^2 = 0.355$ (best model) when planning features are added." |
| RG-2-4 | [448](thesis.tex#L448) | "The absence of planning signals in existing benchmarks means that the observed model rankings may not hold in a deployment where forward-looking order information is available." | tone | OK; good hedging. | Keep. |

### E.4 Gap 3 — No reproducible end-to-end pipeline ([L450-454](thesis.tex#L450-L454))

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| RG-3-1 | [451-452](thesis.tex#L451-L452) | "Most ML manufacturing papers use proprietary datasets or describe model training at a high level without publishing preprocessing and feature engineering code. This limits reproducibility and makes it difficult for practitioners to adapt findings to their own systems." | tone | OK. | Keep. |
| RG-3-2 | [453](thesis.tex#L453) | "This thesis publishes a fully reproducible pipeline with fixed random seeds, version-controlled scripts, and a documented schema that maps directly to standard production event log exports." | tone | OK. | Keep. |
| RG-3-3 | [454](thesis.tex#L454) | "As a result, practitioners cannot determine whether a published model will remain accurate when applied to data extracted from a real ERP system with typical quality problems." | logic | **Logical flow error.** This sentence describes the *problem* that Gap 3 identifies, but it appears *after* [453](thesis.tex#L453) which describes the thesis's *solution*. The order is backwards — the reader gets "solution (thesis publishes pipeline) → problem (practitioners cannot determine)". | Swap: move [454](thesis.tex#L454) to *before* [453](thesis.tex#L453), or reword as a consequence of NOT having reproducible pipelines that survives unchanged. Current placement suggests the thesis's pipeline doesn't help — the opposite of the intended claim. Proposed reorder: L451 (problem) → L452 (consequence) → L454 (why it matters to practitioners) → L453 (thesis addresses this). |

### E.5 Gap 4 — Data quality robustness is not treated as a primary research question ([L456-460](thesis.tex#L456-L460))

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| RG-4-1 | [457](thesis.tex#L457) | "Most forecasting studies either use clean data or include a brief sensitivity analysis as a supplementary experiment." | tone | OK. | Keep. |
| RG-4-2 | [458](thesis.tex#L458) | "No study identified in this review conducts a full factorial experiment with controlled injection of realistic industrial noise types and systematic measurement of degradation across multiple model families." | tone | 28 words, OK. | Keep. |
| RG-4-3 | [459](thesis.tex#L459) | "This thesis addresses this gap through a six-scenario data quality experiment across five models as a core research question (RQ3)." | tone | OK. | Keep. |
| RG-4-4 | [460](thesis.tex#L460) | "The consequence is that model robustness rankings reported in clean-data studies may reverse under realistic industrial conditions." | tone | OK; good hedging. | Keep. |

### E.6 Closing ([L464-466](thesis.tex#L464-L466))

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| RG-C-1 | [464](thesis.tex#L464) | "This thesis addresses all four gaps: it targets capacity consumption prediction specifically, isolates the role of planning-state features through ablation, publishes a fully reproducible pipeline, and treats data quality robustness as a primary research question." | tone | 35 words, good parallel structure. | Keep. |
| RG-C-2 | [466](thesis.tex#L466) | "Chapter~\ref{chap:methodology} describes how the experimental pipeline was constructed to address each of these gaps in turn." | tone | OK chapter bridge. | Keep. |

---

## F. Chapter 3 Cross-Cutting Findings

| # | Finding | Action |
|---|---|---|
| XC-1 | **MAPE in Ch. 3:** none. | OK. |
| XC-2 | **Em-dashes (`---`) in Ch. 3:** none. | OK. |
| XC-3 | **British-US violations in Ch. 3:** `favour` at [407](thesis.tex#L407) is the only finding. | Apply DL-3 (`favour` → `favor`). |
| XC-4 | **AI-smell in Ch. 3:** `revealed` (DL-1), `a consistent observation emerges` (MF-6), `promise` personification (SD-8), `Within manufacturing specifically` (MF-7), `researches` verb error (CH3-2). No `Taken together`, `delve`, `leverage`, `Moreover`, `Furthermore`. | Apply MF-6, MF-7, DL-1, SD-8. |
| XC-5 | **Acronym hygiene:** LSTM expanded correctly (MF-4). SHAP not expanded (DL-12). DES re-parenthesized at [428](thesis.tex#L428) after being defined in Ch. 1 (SD-7). WIP not applied in [446](thesis.tex#L446) after earlier definition (RG-2-2). | Apply DL-12, SD-7, RG-2-2. |
| XC-6 | **Orphan bib entry un-orphaned:** `taylor2018prophet` was orphan per Phase 1 §9.1. MF-3 proposes citing it for Prophet. Will un-orphan it. | Apply MF-3. |
| XC-7 | **Repetition of the core finding (XGBoost $R^2$: 0.204 → 0.355):** appears in Abstract [38-39](thesis.tex#L38-L39), Ch. 1 SC-11 [150](thesis.tex#L150), Ch. 3 §3.1 closing [402](thesis.tex#L402), Ch. 3 §3.4 Gap 2 [447](thesis.tex#L447), Ch. 5 §5.1 [987](thesis.tex#L987). **Five occurrences of the same numbers.** | Reduce to: Abstract (once), Ch. 1 §1.4 (contribution list), Ch. 4 §4.6 (detailed ablation), Ch. 5 §5.1 (discussion). Remove from Ch. 3 — reference §4.6 instead (MF-16 / RG-2-3 proposals already trim). |
| XC-8 | **Numerical consistency:** `2,120 training rows` claimed at [411](thesis.tex#L411) and [419](thesis.tex#L419). Needs verification against nb04/05 canonical split sizes. | DL-9 flags user to verify. |
| XC-9 | **Cross-reference integrity:** tab:related_work_summary unreferenced — apply MF-10. No other broken refs in Ch. 3. | Apply MF-10. |
| XC-10 | **Tense discipline:** Ch. 3 uses simple past for reported studies and present for thesis claims. Consistent. | OK. |
| XC-11 | **Citation density:** 13 unique citations in Ch. 3 (menculini2021, albahli2025, A2025105703, flores-huaman2024lead, belmouadden2025decision, grinsztajn2022, shwartzziv2022tabular, hastie2009elements, lundberg2017shap, hochreiter1997lstm, buggineni2024synthetic, liaskovska2025synthetic, hyndman2021). Healthy. | OK. |
| XC-12 | **Style: Ridge Regression vs Ridge regression** (DL-11) — inconsistent capitalization globally. | Apply global sentence-case `Ridge regression`. |
| XC-13 | **Industry 4.0 vs Industry 5.0** (SD-4): Ch. 1 uses 4.0; Ch. 3 §3.3 introduces 5.0 without cross-discussion. Reader confusion. | Apply SD-4 (drop 5.0 reference). |
| XC-14 | **Logic error in Gap 3** (RG-3-3): problem sentence placed after solution sentence. | Reorder paragraph. |
| XC-15 | **Single-sentence paragraphs:** none in Ch. 3 (RG-0 is intro-for-list, permissible). | OK. |
| XC-16 | **Section intro thinness:** §3.1 opens with 1-sentence paragraph [370](thesis.tex#L370) before Menculini paragraph. Thin but acceptable for a literature-review section. | OK. |

---

## Chapter 3 Summary (user checklist)

**Preamble:** CH3-1 to CH3-6 (6 issues). Notable: fix `researches` → `reviews` (CH3-2); fix `position of its contribution` typo (CH3-1).

**§3.1 ML in Manufacturing Forecasting:** MF-1 to MF-16 (16 issues). Notable:
- **Table reference (MF-10)** — add `Table~\ref{tab:related_work_summary}` in prose.
- **Un-orphan `taylor2018prophet`** by citing at first Prophet mention (MF-3).
- Fix `revealed`, `a consistent observation emerges`, `researches` (MF-6, CH3-2).
- Trim 63-word duplicate-finding sentence (MF-16).

**§3.2 DL vs Tabular:** DL-1 to DL-17 (17 issues). Notable:
- **British spelling** `favour` → `favor` (DL-3).
- **SHAP acronym** not defined (DL-12).
- **`Ridge Regression` vs `Ridge regression`** (DL-11) — globally standardize.
- Verify `2,120 training rows` against nb04/05 (DL-9).
- Trim redundant closing paragraphs (DL-16, DL-17).

**§3.3 Synthetic Data:** SD-1 to SD-11 (11 issues). Notable:
- **Industry 5.0** reference (SD-4) — remove.
- **DES re-definition** (SD-7).
- `companies expect results with guaranteed quality` unclear (SD-2).

**§3.4 Research Gaps:** RG-0, RG-1-1, RG-1-2, RG-2-1 to RG-2-4, RG-3-1 to RG-3-3, RG-4-1 to RG-4-4, RG-C-1, RG-C-2 (13 items). Notable:
- **Logic reordering in Gap 3** (RG-3-3) — problem before solution.
- **Tripled restatement of core finding** in Gap 2 (RG-2-3) — reduce.
- Consolidate 3 redundant sentences at end of Gap 1 (RG-1-2).

**Cross-cutting:** XC-1 to XC-16 (16 observations).

**Total Chapter 3 issues:** ~64 flagged.

---

### Items requiring user decisions before Ch. 4 review

1. **Ridge Regression vs Ridge regression** (DL-11): standardize globally. Recommend `Ridge regression`.
2. **Repetition of XGBoost $R^2$ 0.204/0.355 numbers**: appears 5 times across Abstract + Ch. 1/3/5. Keep in Abstract + Ch. 1 contribution + Ch. 4 ablation + Ch. 5 discussion. **Remove from Ch. 3 §3.1 closing and Ch. 3 §3.4 Gap 2** (reference Section~\ref{subsec:rq2_ablation}). Confirm this trimming plan.
3. **Industry 5.0** (SD-4): drop unless the thesis discusses 5.0 elsewhere (it does not).
4. **`2,120 training rows`** (DL-9 / XC-8): verify against nb04/05 canonical split sizes. If incorrect, note the actual figure.
5. **Gap 3 paragraph ordering** (RG-3-3): confirm the proposed reorder.

Once these five are decided, the remaining ~59 issues are mechanical.

---

**Next:** Ch. 4 Methodology and Results ([thesis.tex:472-976](thesis.tex#L472-L976)) — the longest chapter, heaviest on numerical consistency, British-US conflicts (bulk of `work centre` usage begins here), MAPE occurrences, and figure/table caption audits.