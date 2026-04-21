# Chapter 5 — Summary: Phase 2 Deep Review

> File: `docs/thesis/thesis.tex`, lines **982-1047** (chapter title → last Future-Work item)
> Review depth: strict, with extra attention to rubric-level items (practical implications, social/ethical/SDG, RQ traceability).
> **No edits** applied.

Columns: **#** · **Location** · **Quoted span** · **Category** · **Why flagged** · **Proposed rewrite**.

---

## §5.0 Chapter title and preamble (L982)

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| C5-0-1 | [thesis.tex:982](docs/thesis/thesis.tex#L982) | `\chapter{Summary}\label{chap:summary}` | structure | Chapter contains Discussion, Limitations, Conclusion, and Future Work. The title "Summary" undersells it and is unusual for an IMC Bachelor's thesis (the rubric distinguishes Discussion / Conclusion / Future Work). Phase-1 flag ST-3. | Change the title (keep the label for back-refs): `\chapter{Discussion and Conclusion}\label{chap:summary}`. Alternatively `\chapter{Discussion, Conclusion, and Future Work}` if a longer title is acceptable in the class. |
| C5-0-2 | [thesis.tex:982-985](docs/thesis/thesis.tex#L982-L985) | (no chapter preamble) | structure | Phase-1 blocker **BL-2**: chapter has zero introductory paragraphs before `\section{Discussion}`. Every other chapter has a preamble. | Add one paragraph bridging Ch.4 → Ch.5: `This chapter synthesises the findings of the three research questions, reflects on the methodological limits of the study, and identifies directions for future work. Section~\ref{sec:discussion} interprets the results in the context of the broader literature; Section~\ref{sec:limitations} reviews the scope boundaries that constrain external validity; Section~\ref{sec:conclusion} states the answers to RQ1-RQ3 and their practical consequences; and Section~\ref{sec:future_work} lists six extensions of the methodology.` |

---

## §5.1 Discussion (L985-995)

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| C5-1-1 | [thesis.tex:987](docs/thesis/thesis.tex#L987) | `The central finding of this thesis, that XGBoost with planning-state features outperforms all other evaluated approaches but only when those features are available, shifts the locus of the ML advantage from model complexity to feature construction.` | tone | 32-word lead sentence with an interrupting clause. Reads well for the first half, clunks at `shifts the locus`. | `The central finding of this thesis is that XGBoost with planning-state features outperforms all other evaluated models, but only when those features are available. This shifts the locus of the ML advantage from model complexity to feature construction.` |
| C5-1-2 | [thesis.tex:987](docs/thesis/thesis.tex#L987) | `is outperformed by a per work centre ARIMA at $R^2 = 0.271$` | spelling | British `centre`. | `per-work-center ARIMA at $R^2 = 0.271$` |
| C5-1-3 | [thesis.tex:987](docs/thesis/thesis.tex#L987) | `The gain of $+0.150$ in $R^2$ is attributable to the planning features alone.` | numerical | Matches canonical ablation. ✓ | — |
| C5-1-4 | [thesis.tex:989](docs/thesis/thesis.tex#L989) | `Predictive Capacity Consumption as formulated in this thesis is not a pure time-series prediction problem.` | acronym | PCC spelled out again (indirect). Earlier paragraph at L987 already refers to it by the RQ framing. Consistent with the redefinition pattern flagged in Ch.2/Ch.4 reviews. | `PCC as formulated in this thesis is not a pure time-series prediction problem.` |
| C5-1-5 | [thesis.tex:989](docs/thesis/thesis.tex#L989) | `forecast how much capacity those operations will actually consume` | tone | OK. | — |
| C5-1-6 | [thesis.tex:989](docs/thesis/thesis.tex#L989) | `forward-looking planning-state features (priority-weighted backlog, open planned workload, WIP count, released but not started operations, and the load due in the following week)` | concept | Feature name mismatch: Ch.4 §4.3.3 calls this `open_planned_min` ("open planned minutes"), not `open planned workload`. Use the canonical name. | `forward-looking planning-state features (priority-weighted backlog, open planned minutes, WIP count, released-but-not-started operations, and the load due in the following week)` |
| C5-1-7 | [thesis.tex:989](docs/thesis/thesis.tex#L989) | `and, as Section~\ref{subsec:rq3_results} shows, removing them from the feature set slightly improves both ML models ($+0.019$ for XGBoost, $+0.011$ for Ridge)` | numerical | Matches Table~\ref{tab:rq3_delta}. ✓ | — |
| C5-1-8 | [thesis.tex:989](docs/thesis/thesis.tex#L989) | `The signal carried by planning features is therefore not redundant with the autoregressive information encoded in lags describing a different aspect of the problem.` | grammar | Broken sentence. The trailing clause `describing a different aspect of the problem` dangles — it is meant to describe the planning features, not "lags". | `The signal carried by planning features is therefore not redundant with the autoregressive information encoded in lags: the two groups capture different aspects of the problem.` |
| C5-1-9 | [thesis.tex:991](docs/thesis/thesis.tex#L991) | `The moderate absolute accuracy of the best model ($R^2 \approx 0.36$) is a structural property of the task rather than an artefact of synthetic data randomness.` | spelling | British `artefact`. | `artifact` |
| C5-1-10 | [thesis.tex:991](docs/thesis/thesis.tex#L991) | `weekly aggregation over hundreds of operations per work centre smooths that variance substantially through the law of large numbers` | spelling | British `centre`. | `per work center` |
| C5-1-11 | [thesis.tex:991](docs/thesis/thesis.tex#L991) | `the residual unpredictability in the weekly target is not stochastic noise but the portion of capacity for the coming week that cannot be reconstructed from the information set available at the end of the previous week` | tone | 35-word clause; the idea is clean but the sentence is long. | `the residual unpredictability is not noise; it is the portion of next week's capacity that cannot be reconstructed from the information available at the end of the previous week.` |
| C5-1-12 | [thesis.tex:991](docs/thesis/thesis.tex#L991) | `why per work centre ARIMA remains competitive in their absence` | spelling | British. | `per-work-center ARIMA` |
| C5-1-13 | [thesis.tex:991](docs/thesis/thesis.tex#L991) | `the only learnable structure available from the univariate history of each work centre` | spelling | British. | `each work center` |
| C5-1-14 | [thesis.tex:991](docs/thesis/thesis.tex#L991) | `the gap between ARIMA and XGBoost without planning features is small` | numerical | $0.271 - 0.204 = 0.067$ — "small" is fair. Worth quantifying. | `the gap between ARIMA ($R^2 = 0.271$) and XGBoost without planning features ($R^2 = 0.204$) is small ($\Delta R^2 = 0.067$).` |
| C5-1-15 | [thesis.tex:993](docs/thesis/thesis.tex#L993) | `These results are consistent with the broader empirical literature on tabular structured data. Grinsztajn et al.\ \cite{grinsztajn2022} and Shwartz-Ziv and Armon \cite{shwartzziv2022tabular} report that tree-based and regularised linear models consistently match or outperform deep sequence models on tabular benchmarks when informative features can be engineered from the raw data.` | spelling | British `regularised`. | `regularized linear models` |
| C5-1-16 | [thesis.tex:993](docs/thesis/thesis.tex#L993) | `the advantage of gradient-boosted trees over per work centre statistical baselines is mediated by planning-state features derived from the ERP order and routing tables, and it disappears when those features are withheld.` | spelling | British. | `over per-work-center statistical baselines` |
| C5-1-17 | [thesis.tex:995](docs/thesis/thesis.tex#L995) | `The methodological asymmetry between the two tiers is a calculated design choice that reflects the real-world deployment trade-off (Section~\ref{sec:asymmetry}).` | concept | `Two tiers` — Ch.4 says the comparison sits between **two tiers** (statistical vs ML), but the thesis otherwise frames five models as **three tiers** (Naive / statistical / ML). Be explicit here to avoid tier-count confusion. | `The methodological asymmetry between the per-work-center statistical tier and the feature-based ML tier is a calculated design choice that reflects the real-world deployment trade-off (Section~\ref{sec:asymmetry}).` |
| C5-1-18 | [thesis.tex:995](docs/thesis/thesis.tex#L995) | `Per work centre statistical models can be trained directly on the univariate capacity series and require no feature pipeline, whereas Ridge and XGBoost depend on the planning-state extractor described in Section~\ref{sec:features}.` | spelling | British. | `Per-work-center statistical models` |
| C5-1-19 | [thesis.tex:995](docs/thesis/thesis.tex#L995) | `The gap between feature-based ML ($R^2 \approx 0.33$ to $0.36$) and per work centre statistical models ($R^2 \approx 0.27$) therefore directly quantifies the return on investment in MRP integration and feature engineering for PCC.` | spelling + tone | British; also `directly` twice in consecutive sentences. | `The gap between feature-based ML ($R^2 \approx 0.33$--$0.36$) and per-work-center statistical models ($R^2 \approx 0.27$) quantifies the return on investment in MRP integration and feature engineering for PCC.` |
| C5-1-20 | [thesis.tex:995](docs/thesis/thesis.tex#L995) | `It directly answers whether practitioners should invest in an ML pipeline over autoregressive baselines.` | tone | Sentence rephrases the previous claim and reads as filler. Merge or delete. | Delete the sentence, or merge: `... quantifies the return on investment in MRP integration and feature engineering for PCC — the central quantitative input to a practitioner's build-vs-buy decision.` |
| C5-1-21 | §5.1 overall | (missing paragraph) | rubric | **Rubric gap**: Discussion chapter has no explicit paragraph on **practical manufacturing implications** beyond the methodological argument, and no paragraph on **social / ethical / SDG implications** (SDG 9 Industry, Innovation and Infrastructure; SDG 12 Responsible Consumption and Production; sustainability via improved capacity utilisation, reduced overtime/energy waste). Phase-1 rubric item. | Add **two new paragraphs** at the end of §5.1: <br>**(a) Practical implications.** `For production planners the operational takeaway is that a moderate-accuracy PCC forecast (median error below one 8-hour shift for the best model) is sufficient to inform overtime planning, shift-staffing adjustments, and order-release sequencing at a weekly horizon. For IT departments the takeaway is that the computational footprint is negligible (XGBoost trains in $8.4$ s and forecasts all twenty work centers in under one second), so the investment is in the data-extraction pipeline rather than in modelling infrastructure.` <br>**(b) Societal and ethical implications.** `Better anticipation of capacity demand contributes to the UN Sustainable Development Goals on Industry, Innovation and Infrastructure (SDG 9) and Responsible Consumption and Production (SDG 12). More accurate capacity forecasts reduce reactive overtime, decrease idle machine energy consumption, and support smoother workforce scheduling, which has a direct impact on workers' work-life balance. At the same time, ML-assisted planning decisions that are routed to a human planner rather than executed autonomously preserve accountability for staffing and release decisions. The feature-based approach relies only on operational ERP data and does not incorporate personal or performance-sensitive information, limiting the privacy footprint of the system.` |

---

## §5.2 Limitations (L997-1013)

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| C5-2-1 | [thesis.tex:999](docs/thesis/thesis.tex#L999) | `This thesis has several methodological and scope limitations. Where already addressed as design choices in Chapter~\ref{chap:methodology}, they are reframed here in terms of what they mean for external validity.` | tone | Good bridge. OK. | — |
| C5-2-2 | [thesis.tex:1001](docs/thesis/thesis.tex#L1001) | `realistically parameterised` | spelling | British. | `realistically parameterized` |
| C5-2-3 | [thesis.tex:1001](docs/thesis/thesis.tex#L1001) | `The research therefore demonstrates that the methodology works on realistically parameterised data.This can be transfered to a specific facility which requires retraining on the factory's own historical event log and re-validating the planning-feature extraction against its ERP schema and adjust the preprocessing pipeline if necessary.` | grammar + typo | **Multiple issues**: (a) missing space after period between `data.This`; (b) `transfered` → `transferred`; (c) subject/verb agreement broken — `to a specific facility which requires retraining ... and adjust the preprocessing pipeline`; (d) sentence runs 45+ words with three coordinated clauses. | `The research therefore demonstrates that the methodology works on realistically parameterized data. Transferring it to a specific facility requires retraining on the factory's own historical event log, re-validating the planning-feature extraction against the ERP schema, and adjusting the preprocessing pipeline where necessary.` |
| C5-2-4 | [thesis.tex:1003](docs/thesis/thesis.tex#L1003) | `\textbf{Single plant, single-machine work centres.} The simulation models twenty machine work centres located in one plant.` | spelling | British × 2 in heading and first sentence. | `\textbf{Single plant, single-machine work centers.} The simulation models twenty machine work centers located in one plant.` |
| C5-2-5 | [thesis.tex:1003](docs/thesis/thesis.tex#L1003) | `parallel machine work centres, multi-stage routings across plants, and shared resources between production lines` | spelling | British `centres`; also `parallel machine` missing hyphen. | `parallel-machine work centers, multi-stage routings across plants, and shared resources between production lines` |
| C5-2-6 | [thesis.tex:1003](docs/thesis/thesis.tex#L1003) | `the WIP and released but not started counts assume a one-to-one relationship between work centres and machines, and would need to be redefined as pool level rather than resource level quantities in a parallel machine setting.` | spelling + hyphen | British `centres`; missing hyphens on `pool level`, `resource level`, `parallel machine`. Also `released but not started` should be hyphenated as a compound modifier. | `the WIP and released-but-not-started counts assume a one-to-one relationship between work centers and machines; they would need to be redefined as pool-level rather than resource-level quantities in a parallel-machine setting.` |
| C5-2-7 | [thesis.tex:1005](docs/thesis/thesis.tex#L1005) | `\textbf{Residual information loss from weekly aggregation.} Aggregating operation records to weekly summaries per work centre, as described in Section~\ref{sec:features}, dilutes variance in material complexity, setup time ratios, and individual order priority.` | spelling | British `centre`; also `setup time ratios` — missing hyphen `setup-time ratios`. | `Aggregating operation records to weekly summaries per work center, as described in Section~\ref{sec:features}, dilutes variance in material complexity, setup-time ratios, and individual order priority.` |
| C5-2-8 | [thesis.tex:1005](docs/thesis/thesis.tex#L1005) | `The four work centres with $R^2 < 0$ on the test partition are those where the remaining variance within each week dominates the signal that the weekly feature set can encode.` | spelling | British. | `four work centers` |
| C5-2-9 | [thesis.tex:1007](docs/thesis/thesis.tex#L1007) | `\textbf{Weekly granularity only.} The rationale for weekly aggregation is given in Section~\ref{sec:aggregation}.` | structure | OK. | — |
| C5-2-10 | [thesis.tex:1007](docs/thesis/thesis.tex#L1007) | `some environments require forecasts at the shift or daily level for rapid production cycles, and it remains unclear whether the feature-based ML advantage persists at finer granularities, where many idle periods create zero values in the target.` | hedging + hyphen | `Shift or daily level` — `shift-level` missing hyphen. Slightly overlong (33 words) but acceptable. | `some environments require forecasts at the shift or daily level for rapid production cycles. Whether the feature-based ML advantage persists at finer granularities, where many idle periods create zero-valued targets, remains open.` |
| C5-2-11 | [thesis.tex:1009](docs/thesis/thesis.tex#L1009) | `\textbf{Tier comparability.} The methodological asymmetry between univariate time-series models and feature-based ML models is justified in Section~\ref{sec:asymmetry} as a reflection of the real-world deployment trade-off.` | tone | OK. | — |
| C5-2-12 | [thesis.tex:1009](docs/thesis/thesis.tex#L1009) | `As a limitation, the reported gap quantifies the combined value of pooling and planning-feature engineering, rather than isolating algorithmic contribution alone. Isolating that contribution would require fitting per work centre models with the same feature set.` | spelling | British `centre`. | `per-work-center models` |
| C5-2-13 | [thesis.tex:1011](docs/thesis/thesis.tex#L1011) | `\textbf{No external variables.} The model does not incorporate demand shocks, supply disruptions, workforce changes, or macroeconomic indicators.` | tone | OK. | — |
| C5-2-14 | [thesis.tex:1011](docs/thesis/thesis.tex#L1011) | `In such volatile environments, these factors can trigger regime changes that the model cannot comprehend from historical data alone.` | tone | `Comprehend` is an odd verb for a model. Use `anticipate` / `capture` / `reflect`. | `In such volatile environments, these factors can trigger regime changes that the model cannot anticipate from historical data alone.` |
| C5-2-15 | [thesis.tex:1011](docs/thesis/thesis.tex#L1011) | `The present thesis deliberately restricts the scope to information available from the ERP event log and master data.` | tone | Good restatement. OK. | — |
| C5-2-16 | [thesis.tex:1013](docs/thesis/thesis.tex#L1013) | `\textbf{No live system integration.} The pipeline processes static CSV exports of the four ERP tables described in Section~\ref{sec:master_data}.` | tone | OK. | — |
| C5-2-17 | [thesis.tex:1013](docs/thesis/thesis.tex#L1013) | `operationalising the forecast in a planner facing tool` | spelling + hyphen | British `operationalising`; missing hyphen `planner-facing`. | `operationalizing the forecast in a planner-facing tool` |
| C5-2-18 | [thesis.tex:1013](docs/thesis/thesis.tex#L1013) | `The organisational and technical effort of such an integration is outside the scope of this thesis.` | spelling | British. | `The organizational and technical effort of such an integration is outside the scope of this thesis.` |
| C5-2-19 | §5.2 overall | (missing limitations) | rubric | **Missing limitations** worth adding: (a) **single random seed** (`SEED = 42`) — no multi-seed stability study, so reported standard deviations rely on CV folds rather than independent runs; (b) **benchmark comparison** — results are not directly comparable to published ERP/MES forecasting benchmarks because the synthetic dataset is unique to this thesis; (c) **three-year upper bound** on history — the RQ3 analysis tests shorter histories but not longer ones (two years was already sufficient for XGBoost, but no evidence that four or five years would continue to help). | Add a new paragraph: `\textbf{Single random seed and benchmark comparability.} All experiments are seeded with a single random state ($\text{SEED} = 42$); cross-validation standard deviations are reported, but no multi-seed replication study was conducted. Consequently, the reported differences between models may include a small run-to-run contribution that is not separately quantified. Moreover, the use of a synthetic dataset, although necessary for the controlled RQ3 experiments, prevents direct numerical comparison with published PCC or ERP-forecasting benchmarks. External validity would be strengthened by replicating the study with additional seeds and on a real ERP export as outlined in Section~\ref{sec:future_work}.` |

---

## §5.3 Conclusion (L1016-1026)

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| C5-3-1 | [thesis.tex:1018](docs/thesis/thesis.tex#L1018) | `This thesis develops and evaluates an end-to-end pipeline for Predictive Capacity Consumption, defined as the weekly forecast of actual machine-hour consumption per work centre from historical ERP event logs and planning-state data.` | spelling + acronym | British `centre`; PCC redefined yet again. | `This thesis develops and evaluates an end-to-end pipeline for PCC, defined as the weekly forecast of actual machine-hour consumption per work center from historical ERP event logs and planning-state data.` |
| C5-3-2 | [thesis.tex:1018](docs/thesis/thesis.tex#L1018) | `The three research questions posed in Section~\ref{sec:research_questions} are answered as follows.` | RQ | Good signposting. OK. | — |
| C5-3-3 | [thesis.tex:1020](docs/thesis/thesis.tex#L1020) | `\textbf{RQ1, Forecast Accuracy.} XGBoost with the full feature set achieves $R^2 = 0.355$ on the held-out test partition, with $\text{RMSE} = 1.139$ and $\text{MAE} = 0.709$ on the log scale.` | numerical + RQ | Matches canonical. ✓ RQ1 wording alignment: Ch.1 §1.3 uses `Forecast Accuracy` — aligned. ✓ | — |
| C5-3-4 | [thesis.tex:1020](docs/thesis/thesis.tex#L1020) | `The corresponding median forecast error on the original minute scale is $4.6$ hours per work centre per week.` | spelling + concept | British `centre`; also "minute scale" — L762 says "hours scale" and the value $4.6$ is in hours. The phrasing "corresponding median forecast error on the original minute scale is $4.6$ hours" conflates units. | `The corresponding median forecast error on the hours scale is $4.6$ hours per work center per week.` |
| C5-3-5 | [thesis.tex:1020](docs/thesis/thesis.tex#L1020) | `Of the $460$ work-centre-weeks in the test partition, $72.2\%$ of forecasts fall within one standard eight-hour shift of the realised capacity.` | spelling | British `centre`, `realised`. | `Of the $460$ work-center-weeks in the test partition, $72.2\%$ of forecasts fall within one standard eight-hour shift of the realized capacity.` |
| C5-3-6 | [thesis.tex:1020](docs/thesis/thesis.tex#L1020) | `One of the twenty work centres reaches the reliable tier ($R^2 \geq 0.30$), fifteen fall into the directional tier ($0 \leq R^2 < 0.30$), and four produce forecasts below the training set mean.` | spelling | British. | `One of the twenty work centers reaches the reliable tier` |
| C5-3-7 | [thesis.tex:1020](docs/thesis/thesis.tex#L1020) | `The accuracy is moderate in absolute terms but substantial relative to the alternatives considered in this thesis.` | hedging | `Substantial relative to the alternatives` — accurate claim; tone OK. | — |
| C5-3-8 | [thesis.tex:1022](docs/thesis/thesis.tex#L1022) | `\textbf{RQ2, Model Trade-Off.} The five main models fall into three clearly separated tiers on the test partition: the industry baseline Naive forecast ($R^2 = -0.647$), the per work centre statistical tier (SES at $R^2 = 0.271$, ARIMA at $R^2 = 0.271$), and the feature-based ML tier (Ridge at $R^2 = 0.325$, XGBoost at $R^2 = 0.355$).` | spelling + numerical | British `per work centre`; numbers match canonical. ✓ | `... the per-work-center statistical tier (SES at $R^2 = 0.271$, ARIMA at $R^2 = 0.271$), and the feature-based ML tier (Ridge at $R^2 = 0.325$, XGBoost at $R^2 = 0.355$).` |
| C5-3-9 | [thesis.tex:1022](docs/thesis/thesis.tex#L1022) | `The gap between tiers is explained by the planning-feature ablation: without those features XGBoost drops to $R^2 = 0.204$ and is outperformed by ARIMA, and with them it becomes the most accurate model in the comparison.` | numerical | Matches. ✓ | — |
| C5-3-10 | [thesis.tex:1022](docs/thesis/thesis.tex#L1022) | `The $+0.150$ gain in $R^2$ attributable to planning features is the central result of this thesis.` | tone | Strong, clear statement. ✓ | — |
| C5-3-11 | [thesis.tex:1022](docs/thesis/thesis.tex#L1022) | `The real value is in the feature pipeline, not in model complexity, and a regularised linear model (Ridge) retains the majority of the ML advantage at a fraction of the implementation cost.` | spelling + tone | British `regularised`. "Real value" is slightly informal; "main value" or "operational value" reads cleaner. | `The main value is in the feature pipeline, not in model complexity: a regularized linear model (Ridge) retains the majority of the ML advantage at a fraction of the implementation cost.` |
| C5-3-12 | [thesis.tex:1024](docs/thesis/thesis.tex#L1024) | `\textbf{RQ3, Data Quality Sensitivity.} Moderate data quality degradations common to ERP pipelines, namely $20\%$ missing features, $10\%$ target corruption, and $\sigma = 0.3$ Gaussian sensor noise, produce $|\Delta R^2| \leq 0.021$ for every model tested, and the tier ordering established under RQ2 is preserved throughout.` | tone | OK. | — |
| C5-3-13 | [thesis.tex:1024](docs/thesis/thesis.tex#L1024) | `Reducing the training window to one year causes XGBoost to collapse from $R^2 = 0.355$ to $R^2 = 0.016$ ($\Delta R^2 = -0.339$), and to $R^2 = -0.110$ ($\Delta R^2 = -0.464$) at six months.` | numerical | Matches canonical. ✓ | — |
| C5-3-14 | [thesis.tex:1024](docs/thesis/thesis.tex#L1024) | `Ridge is more resilient under the same limitations, retaining $R^2 = 0.302$ at one year and $R^2 = 0.245$ at six months.` | numerical | Matches. ✓ | — |
| C5-3-15 | [thesis.tex:1024](docs/thesis/thesis.tex#L1024) | `SES and ARIMA are effectively immune to every tested degradation, moving by less than $0.011$ in $R^2$ under the worst case.` | numerical | Table~\ref{tab:rq3_family} worst $\Delta R^2$: SES $-0.008$, ARIMA $-0.011$. The claim `less than 0.011` is technically wrong for ARIMA (it equals 0.011). Fix or reword. | `SES and ARIMA are effectively immune to every tested degradation, with worst-case $|\Delta R^2|$ of $0.008$ and $0.011$, respectively.` |
| C5-3-16 | [thesis.tex:1024](docs/thesis/thesis.tex#L1024) | `The practical implication is the model selection rule set out in Section~\ref{sec:business}: XGBoost when at least two years of weekly history and a planning-feature pipeline are available, Ridge when history is shorter but features are present, and per work centre SES or ARIMA when neither condition holds.` | spelling | British `per work centre`. | `per-work-center SES or ARIMA when neither condition holds` |
| C5-3-17 | [thesis.tex:1026](docs/thesis/thesis.tex#L1026) | `Forward-looking planning information extracted from production orders and routing tables is the enabling factor for feature-based ML to outperform per work centre statistical baselines in PCC.` | spelling | British. | `per-work-center statistical baselines` |
| C5-3-18 | [thesis.tex:1026](docs/thesis/thesis.tex#L1026) | `With it, XGBoost provides the best absolute accuracy and Ridge the best accuracy robustness trade-off.` | hyphen | Missing hyphen: `accuracy-robustness trade-off`. | `With it, XGBoost provides the best absolute accuracy, and Ridge the best accuracy-robustness trade-off.` |
| C5-3-19 | [thesis.tex:1026](docs/thesis/thesis.tex#L1026) | `Simple, interpretable models combined with domain driven feature engineering provide production planners with directionally accurate, robust, and operationally deployable capacity forecasts.` | hyphen + AI-smell | `Domain driven` missing hyphen. Closing sentence contains a **tricolon** (`directionally accurate, robust, and operationally deployable`) — Phase-1 AI-smell pattern flagged in user's rubric. | `Simple, interpretable models combined with domain-driven feature engineering give production planners capacity forecasts that are accurate at the directional level, stable under realistic data-quality degradation, and cheap enough to run as a weekly batch job alongside the MRP run.` |
| C5-3-20 | §5.3 overall | (missing paragraph) | rubric | **Rubric gap**: conclusion does not include a paragraph on **social / ethical / SDG implications**, and its paragraph on practical implications is compressed into the RQ-answer framing. If C5-1-21 adds those paragraphs to §5.1 Discussion, it may be enough. If the rubric demands both in Discussion and in Conclusion, duplicate the practical-implications summary (two sentences) here. | Optional — check with thesis guidelines; otherwise add: `These results support a pragmatic deployment path that reduces reactive overtime and idle machine energy consumption, contributing to UN SDGs 9 and 12. Because the forecast feeds a planner-facing decision rather than an autonomous scheduler, the human planner retains final control over staffing and release decisions.` |

---

## §5.4 Future Work (L1029-1047)

| # | Location | Quoted span | Category | Why flagged | Proposed rewrite |
|---|---|---|---|---|---|
| C5-4-1 | [thesis.tex:1029](docs/thesis/thesis.tex#L1029) | `This thesis identifies several directions for future work, each relaxing a scope restriction from Section~\ref{sec:limitations} or extending the methodology beyond the main study.` | tone | OK. | — |
| C5-4-2 | [thesis.tex:1034](docs/thesis/thesis.tex#L1034) | `\textbf{Validation on real production data.} The pipeline accepts any ERP event log export conforming to the four table schema described in Section~\ref{sec:master_data}. The most direct extension is to replace the synthetic input files with real data from an operating manufacturing plants, refit all five models under the same chronological protocol, and measure the change in $R^2$ relative to the synthetic baseline.` | grammar | `an operating manufacturing plants` — article/number mismatch. Also `four table schema` missing hyphen. | `The pipeline accepts any ERP event-log export conforming to the four-table schema described in Section~\ref{sec:master_data}. The most direct extension is to replace the synthetic input files with real data from an operating manufacturing plant, refit all five models under the same chronological protocol, and measure the change in $R^2$ relative to the synthetic baseline.` |
| C5-4-3 | [thesis.tex:1034](docs/thesis/thesis.tex#L1034) | `This would reveal the transferability gap and whether planning features remain advantageous on real data.` | tone | OK. | — |
| C5-4-4 | [thesis.tex:1036](docs/thesis/thesis.tex#L1036) | `\textbf{Online and incremental learning.} The current pipeline retrains from scratch every week.` | tone | OK. | — |
| C5-4-5 | [thesis.tex:1036](docs/thesis/thesis.tex#L1036) | `For plants in which the capacity signal drifts rapidly through product introductions, routing changes, or workforce restructuring, online learning approaches that update the model incrementally with each new confirmation may provide faster adaptation.` | tone | 34-word sentence. OK. | — |
| C5-4-6 | [thesis.tex:1036](docs/thesis/thesis.tex#L1036) | `Investigating how online XGBoost or gradient-based Ridge variants compare with periodic full retraining is a natural extension that is particularly relevant for plants with limited training history, where the RQ3 analysis indicated the largest accuracy losses.` | tone | 37 words; dense. | `Whether online XGBoost or gradient-based Ridge variants compare favourably with periodic full retraining is a natural question, particularly for plants with limited training history — the regime where the RQ3 analysis showed the largest accuracy losses.` |
| C5-4-7 | [thesis.tex:1038](docs/thesis/thesis.tex#L1038) | `\textbf{Multi-plant modelling with transfer learning.}` | spelling | British `modelling`. | `\textbf{Multi-plant modeling with transfer learning.}` |
| C5-4-8 | [thesis.tex:1038](docs/thesis/thesis.tex#L1038) | `Transfer and multi-task learning could allow a model trained on one plant to inform predictions for a plant with only limited history, addressing the insufficient history failure mode identified in Section~\ref{subsec:rq3_robustness}.` | hyphen | `Insufficient history failure mode` — the compound adjective should be hyphenated: `insufficient-history failure mode`. | `addressing the insufficient-history failure mode identified in Section~\ref{subsec:rq3_robustness}.` |
| C5-4-9 | [thesis.tex:1038](docs/thesis/thesis.tex#L1038) | `Shared feature representations across plants, combined with plant specific fixed effects analogous to the work centre dummies used in this thesis, are a good starting point candidate.` | spelling + hyphen + tone | British `centre`; missing hyphen `plant-specific`; awkward phrase `good starting point candidate`. | `Shared feature representations across plants, combined with plant-specific fixed effects analogous to the work-center dummies used in this thesis, are a natural starting point.` |
| C5-4-10 | [thesis.tex:1040](docs/thesis/thesis.tex#L1040) | `\textbf{Sub weekly granularity.} Shift level or daily capacity forecasts would provide higher resolution information for short-cycle production environments.` | hyphen | `Sub weekly` → `Sub-weekly`; `shift level` → `shift-level`; `higher resolution` → `higher-resolution`. | `\textbf{Sub-weekly granularity.} Shift-level or daily capacity forecasts would provide higher-resolution information for short-cycle production environments.` |
| C5-4-11 | [thesis.tex:1040](docs/thesis/thesis.tex#L1040) | `Finer time steps have many idle periods with zero values, which breaks the assumptions of standard regression.` | concept | Accurate but could reference the aggregation rationale in §4.3.2. OK. | — |
| C5-4-12 | [thesis.tex:1040](docs/thesis/thesis.tex#L1040) | `Two stage formulations, in which a classifier predicts whether a work centre is active in the target period and a regressor predicts load conditional on activity, are a promising direction for preserving the feature-based ML advantage at finer time scales.` | spelling + hyphen | British `centre`; `Two stage` → `Two-stage`. | `Two-stage formulations, in which a classifier predicts whether a work center is active in the target period and a regressor predicts load conditional on activity, are a promising direction for preserving the feature-based ML advantage at finer time scales.` |
| C5-4-13 | [thesis.tex:1042](docs/thesis/thesis.tex#L1042) | `\textbf{Closed-loop integration with MRP.} The final application of PCC is to feed the forecast back into the MRP and CRP planning runs, replacing the static routing-based load calculation with ML-predicted actual consumption.` | tone | OK. | — |
| C5-4-14 | [thesis.tex:1042](docs/thesis/thesis.tex#L1042) | `This raises questions about how forecast updates affect the planning cycle and release decisions. It requires real-time ERP integration, not just batch processing.` | tone | OK, though terse. | Optional: combine for flow: `This raises questions about how forecast updates affect the planning cycle and release decisions, and requires real-time ERP integration rather than the batch pipeline used in this thesis.` |
| C5-4-15 | [thesis.tex:1044](docs/thesis/thesis.tex#L1044) | `\textbf{Richer master data features.} The aggregation step discards week variation in routing and bill of materials (BOMs) complexity.` | acronym | `Bill of materials (BOMs)` — the acronym is **BOM**, plural **BOMs**. Parenthetical re-expansion style inconsistent (Ch.4 already uses BOM). Also "week variation" reads as "one week's variation"; intended meaning is "within-week variation". | `The aggregation step discards within-week variation in routing and BOM complexity.` |
| C5-4-16 | [thesis.tex:1044](docs/thesis/thesis.tex#L1044) | `Extracting more granular categorical features from the ERP master data, for example tier level mix indicators or routing step dispersion measures, before aggregation may allow XGBoost to capture additional material specific variance` | hyphen | `Tier level` → `tier-level`; `routing step` → `routing-step`; `material specific` → `material-specific`. | `Extracting more granular categorical features from the ERP master data — for example tier-level mix indicators or routing-step dispersion measures — before aggregation may allow XGBoost to capture additional material-specific variance ...` **⚠️ note:** the proposed `---` here violates the em-dash ban. Use commas or parentheses instead: `Extracting more granular categorical features from the ERP master data (for example tier-level mix indicators or routing-step dispersion measures) before aggregation may allow XGBoost to capture additional material-specific variance` |
| C5-4-17 | [thesis.tex:1044](docs/thesis/thesis.tex#L1044) | `close some of the gap on the four unreliable work centres identified in Section~\ref{subsec:rq1_per_wc}` | spelling | British. | `four unreliable work centers` |
| C5-4-18 | [thesis.tex:1046](docs/thesis/thesis.tex#L1046) | `\textbf{Execution efficiency as forecast target.} This thesis predicts absolute capacity consumption for the coming week. An alternative formulation, adopted in some industrial capacity planning tools, treats the planned load due in the forecast week as a deterministic ERP baseline and trains ML only to predict the deviation ratio of actual to planned minutes.` | hyphen + tone | `Actual to planned` → `actual-to-planned`; `industrial capacity planning tools` → `industrial capacity-planning tools`. | `An alternative formulation, adopted in some industrial capacity-planning tools, treats the planned load due in the forecast week as a deterministic ERP baseline and trains ML only to predict the actual-to-planned deviation ratio.` |
| C5-4-19 | [thesis.tex:1046](docs/thesis/thesis.tex#L1046) | `This approach separates planned load from execution variance, letting ML focus on what it can predict. The feature pipeline here is directly reusable.` | tone | OK. | — |

---

## Cross-cutting findings for Chapter 5

### 1. British → US spelling (bulk conversion)
Same policy as Ch.4 — single global pass. Instances in Ch.5:

| Term (British) | Term (US) | Lines |
|---|---|---|
| `centre/centres` (incl. `work centre`, `work centres`, `work-centre`, `per work centre`) | `center/centers` | L987, L991 (×2), L993, L995 (×2), L1003 (×5), L1005 (×2), L1009, L1013 (re-written), L1020 (×2), L1022, L1024, L1026, L1038, L1040, L1044 |
| `artefact` | `artifact` | L991 |
| `regularised` | `regularized` | L993, L1022 |
| `realised` | `realized` | L1020 |
| `parameterised` | `parameterized` | L1001 |
| `modelling` | `modeling` | L1038 |
| `organisational` | `organizational` | L1013 |
| `operationalising` | `operationalizing` | L1013 |

### 2. Missing hyphens in compound modifiers
- `pool level` → `pool-level` (L1003)
- `resource level` → `resource-level` (L1003)
- `parallel machine` → `parallel-machine` (L1003)
- `setup time ratios` → `setup-time ratios` (L1005)
- `planner facing tool` → `planner-facing tool` (L1013)
- `accuracy robustness trade-off` → `accuracy-robustness trade-off` (L1026)
- `domain driven` → `domain-driven` (L1026)
- `four table schema` → `four-table schema` (L1034)
- `insufficient history failure mode` → `insufficient-history failure mode` (L1038)
- `plant specific` → `plant-specific` (L1038)
- `Sub weekly` → `Sub-weekly` (L1040 heading)
- `Shift level` → `Shift-level` (L1040)
- `Two stage` → `Two-stage` (L1040)
- `tier level mix indicators` → `tier-level mix indicators` (L1044)
- `routing step dispersion` → `routing-step dispersion` (L1044)
- `material specific variance` → `material-specific variance` (L1044)
- `actual to planned minutes` → `actual-to-planned minutes` (L1046)
- `industrial capacity planning tools` → `industrial capacity-planning tools` (L1046)

### 3. Typos and grammar
- [L1001](docs/thesis/thesis.tex#L1001): `data.This` missing space; `transfered` → `transferred`; whole sentence broken subject/verb agreement — full rewrite required.
- [L989](docs/thesis/thesis.tex#L989): dangling clause — "lags describing a different aspect of the problem" — logic inverted.
- [L1020](docs/thesis/thesis.tex#L1020): "on the original minute scale is $4.6$ hours" — unit mismatch.
- [L1034](docs/thesis/thesis.tex#L1034): `an operating manufacturing plants` — article/number.
- [L1044](docs/thesis/thesis.tex#L1044): `bill of materials (BOMs)` — acronym already defined; expansion inconsistent.

### 4. AI-smell
- [L1026](docs/thesis/thesis.tex#L1026): tricolon `directionally accurate, robust, and operationally deployable` — the user's rubric explicitly flags tricolons.
- `Taken together` — **not present** in Ch.5 (good, contrast with Ch.4 two occurrences).
- `delve`, `tapestry`, `realm`, `pivotal`, `crucial`, `leverage` — **not present**. Good.

### 5. MAPE / em-dashes
- **MAPE**: not present in Ch.5. Good.
- **em-dashes**: not present in rendered prose. The only `---` appearances are at the `%%%` banner and none in rendered text.

### 6. Cross-reference integrity
- `chap:methodology` (L999) — ✓ defined L472.
- `sec:realism` (L1001) — ✓ defined L584.
- `sec:features` (L1005) — ✓ defined L652.
- `sec:aggregation` (L1007) — ✓ defined L642.
- `sec:asymmetry` (L1009) — ✓ defined L730.
- `sec:master_data` (L1013, L1034) — ✓ defined L521.
- `sec:research_questions` (L1018) — ✓ defined in Ch.1.
- `sec:business` (L1024) — ✓ defined L964.
- `sec:limitations` (L1031) — ✓ defined L997.
- `subsec:rq3_results` (L989) — ✓ defined L881.
- `subsec:rq2_ablation` (L987) — ✓ defined L810.
- `subsec:rq3_robustness` (L1038) — ✓ defined L939.
- `subsec:rq1_per_wc` (L1044) — ✓ defined L764.
- `sec:discussion`, `sec:conclusion`, `sec:future_work` — ✓ all defined in this chapter.

### 7. RQ traceability (Phase-1 item)
| RQ | Ch.1 definition (L128-ish) | Ch.4 result | Ch.5 Conclusion | Consistent? |
|---|---|---|---|---|
| RQ1 Forecast Accuracy | "how accurately can weekly capacity consumption per work center be forecast" | §4.5 reports $R^2=0.355$, MAE $4.6$h median, $72.2\%$ within one shift | L1020 repeats all three numbers | ✓ |
| RQ2 Model Trade-Off | "which family of forecasting methods offers the best trade-off between accuracy, interpretability, and implementation effort" | §4.6 ranks five models; isolates planning features via ablation | L1022 repeats tier split; highlights +0.150 gain as "central result" | ✓ |
| RQ3 Data Quality Sensitivity | "how sensitive are PCC forecasts to realistic ERP data-quality problems, and which model families are most robust" | §4.7 runs six scenarios × five models; identifies history length as dominant risk | L1024 restates $|\Delta R^2| \leq 0.021$ for moderate degradations and the two history-reduction outliers | ✓ |

All three RQs are explicitly closed in Ch.5. Good.

### 8. Rubric items worth attention
| Rubric item | Present in Ch.5? | Action |
|---|---|---|
| Practical manufacturing implications | Partially (L1024, L1026 in Conclusion) | Add a dedicated paragraph in §5.1 Discussion. **C5-1-21.** |
| Social/ethical/SDG implications | **Missing** | Add a dedicated paragraph in §5.1 Discussion (and optionally mirror in §5.3 Conclusion). **C5-1-21** and **C5-3-20.** |
| Conclusion focuses on 2-5 key findings | ✓ (RQ1, RQ2, RQ3 + central result + model-selection rule) | OK — don't bloat. |
| Chapter structure | ✗ Missing preamble (C5-0-2) and title mismatch (C5-0-1) | Fix both. |
| Limitations list | ✓ 7 items, specific not boilerplate | OK; optional to add seed / benchmark-comparability limitation (**C5-2-19**). |
| Hedging calibration | OK — no overclaim ("proves", "demonstrates conclusively") detected; moderate accuracy acknowledged repeatedly. | — |

---

## Items requiring user decisions before Phase 3

1. **Chapter title** — keep `Summary` or rename to `Discussion and Conclusion`? (C5-0-1)
2. **Missing chapter preamble** — accept proposed paragraph at C5-0-2?
3. **Practical + Social/Ethical/SDG paragraphs** — approve the two-paragraph addition to §5.1 Discussion (C5-1-21)? Also approve the optional short summary in §5.3 Conclusion (C5-3-20), or is §5.1 alone sufficient?
4. **Additional limitations paragraph** on seed + benchmark comparability (C5-2-19) — in scope or out?
5. **Tricolon in Conclusion closer** (L1026, C5-3-19) — accept the rewrite, or keep a cleaner version of the original?
6. **BOM acronym handling** at L1044 (C5-4-15) — trust that BOM is already defined and drop the parenthetical re-expansion?
7. **British-spelling sweep** — confirm global sed-style pass (same as Ch.4 decision).
8. **Feature name `open planned workload` → `open planned minutes`** at L989 (C5-1-6) — fix to match Ch.4 canonical term?

---

**End of Chapter 5 review.** Total flagged issues: **~70** (fewer than Ch.4 because Ch.5 is shorter and has less technical machinery; rubric gaps around social/ethical and chapter preamble dominate the critical finds). Next: **Phase 3 consolidated change list** (skipping the Appendices deep review per your instruction).