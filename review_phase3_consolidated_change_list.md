# Phase 3 — Consolidated Change List

> **Source reviews** (these stay authoritative for per-issue detail):
> - [review_phase1_global_pass.md](review_phase1_global_pass.md)
> - [review_phase2_ch1_introduction.md](review_phase2_ch1_introduction.md)
> - [review_phase2_ch2_background.md](review_phase2_ch2_background.md)
> - [review_phase2_ch3_related_work.md](review_phase2_ch3_related_work.md)
> - [review_phase2_ch4_methodology_results.md](review_phase2_ch4_methodology_results.md)
> - [review_phase2_ch5_summary.md](review_phase2_ch5_summary.md)
>
> This document is the **action plan**, not a new issue log. Per-chapter files contain the exact rewrites.
> Appendices A/B/C were **not deep-reviewed** per user instruction, but the blocker to un-comment them still stands.
>
> **No edits have been applied.** This plan assumes a follow-up editing session.

---

## Part 1 — Master decision checklist (resolve BEFORE editing)

These decisions are cross-chapter or thesis-wide. Resolving them first lets the edit pass be mechanical. Mark each row ✅ / ✏️ / ❌ before starting edits.

| # | Decision | Options | Recommendation | Scope |
|---|---|---|---|---|
| D1 | **Appendices A/B/C** | (a) uncomment + finalise all three, (b) delete them and remove the two forward references in Ch.4 | (a) — two chapters already reference them | Ch.4 L708, L710 + [thesis.tex:1060-1161](thesis.tex#L1060-L1161) |
| D2 | **Chapter 5 title** | (a) keep `Summary`, (b) rename to `Discussion and Conclusion` | (b) — standard for this thesis type | [thesis.tex:982](thesis.tex#L982) |
| D3 | **US-spelling global sweep** | single sed-style pass with manual review | approve; see Part 3.1 | whole thesis |
| D4 | **Tier count wording** | (a) "three tiers" (Naive / statistical / ML), (b) "two tiers" (statistical vs ML) | (a) — used in Ch.1 & Ch.4 consistently; Ch.2 is the outlier | Ch.2 §2.3 preamble |
| D5 | **Acronym re-expansion policy** | (a) expand once thesis-wide, (b) expand once per chapter | (a) — cleaner; drops duplicate expansions of PCC/DES/SES/MAE/RMSE | Ch.2, Ch.4, Ch.5 |
| D6 | **α symbol clash (SES vs Ridge)** | (a) subscript as $\alpha_\text{SES}$ / $\alpha_\text{Ridge}$, (b) clarifying sentence at each occurrence | (a) — unambiguous | Ch.2 §2.3, Ch.4 §4.4 |
| D7 | **MAPE** | total removal from prose, comments, and any column headers | approve | Ch.2 L304, Ch.4 L477-478, L740 |
| D8 | **Em-dash in Naive table cell (L721)** | (a) `N/A`, (b) `--` (en-dash), (c) blank | (a) — most readable | [thesis.tex:721](thesis.tex#L721) |
| D9 | **`\log_{1p}` notation** | (a) keep, (b) `\log(1+x)`, (c) `\texttt{log1p}` | (c) — unambiguous and matches the numpy/pandas function name | Ch.4 L650, L751 |
| D10 | **"approximately" / `$\approx$` in deterministic counts** | (a) replace with exact values from notebooks, (b) keep | (a) — pipeline is seeded | Ch.4 §4.2 (C4-2-17, C4-2-25) |
| D11 | **Feature-importance legend vocabulary** | align `historical and operational` vs `lag, rolling, and operational` | approve alignment to `lag, rolling, and operational` | Ch.4 L846, L851 |
| D12 | **Social/ethical/SDG paragraph** | (a) add to §5.1 Discussion only, (b) add to both §5.1 and §5.3 | (a) — keep Conclusion tight on RQ answers; per Phase 1 rubric this must appear in Discussion | Ch.5 §5.1 |
| D13 | **Practical-implications paragraph in Discussion** | (a) add dedicated paragraph to §5.1 (currently distributed), (b) keep distributed | (a) — rubric expects explicit coverage | Ch.5 §5.1 |
| D14 | **Seed-only / benchmark-comparability limitation** | (a) add as a new §5.2 item, (b) omit | (a) — increases defence robustness | Ch.5 §5.2 (C5-2-19) |
| D15 | **Abstract numbers** | include RMSE and MAE alongside $R^2$ and hours-scale error | approve | Ch.1 Abstract (Phase-2 AB-4) |
| D16 | **PCC definition placement** | first use in Abstract [thesis.tex:98](thesis.tex#L98) should include a one-line PCC definition | approve | Ch.1 Abstract + §1.1 |
| D17 | **ERP/MES reverse-acronym fix** | `Enterprise Resource Planning (ERP)` / `Manufacturing Execution Systems (MES)` order everywhere | approve | Ch.1 L97, §1.2 |
| D18 | **DES hyphenation** | canonical form `Discrete-Event Simulation` (with hyphen) | approve | whole thesis |
| D19 | **CV acronym disambiguation** | reserve `CV` for cross-validation; spell "coefficient of variation" in full | approve | Ch.2, Ch.4 §4.2 |
| D20 | **RQ1 verb** | `forecast` throughout (Abstract uses it); not `predict` | approve | Ch.1 §1.3, Ch.4 §4.5, Ch.5 §5.3 |
| D21 | **Ridge α value** | confirm `α = 500` (L724) against nb04/05 | approve verification | Ch.4 L724 |
| D22 | **Numerical verification batch** | re-confirm the nine "needs nb04/05 verification" values in Ch.4 §9 before edit pass | approve — list in Part 4.2 | Ch.4 |
| D23 | **Feature name `open planned workload` → `open planned minutes`** | align Ch.5 §5.1 to Ch.4 canonical | approve | Ch.5 L989 |
| D24 | **BOM re-expansion at L1044** | remove parenthetical `(BOMs)` — already defined in Ch.4 | approve | Ch.5 L1044 |
| D25 | **Bibliography orphans & ResearchGate** | (a) cite all 8 orphans in Ch.3 / Appendix, (b) delete them; replace ResearchGate URLs with peer-reviewed venues | (b) for orphans that can't be placed; verify ResearchGate entries and replace with venue | references.bib |

---

## Part 2 — Priority-ordered blocker list (must-fix before compile)

These are the items that will either break the build, violate the rubric, or make the thesis undefendable.

### Tier 0 — blocks final build
| # | Blocker | Fix | Source |
|---|---|---|---|
| B1 | Three appendices commented out; two forward refs at [thesis.tex:708](thesis.tex#L708), [thesis.tex:710](thesis.tex#L710) will render as `??` | Uncomment + finalise [thesis.tex:1060-1161](thesis.tex#L1060-L1161), or delete the two forward refs | Phase 1 B1; Ch.4 C4-4-3, C4-4-4 |
| B2 | Chapter 5 has no preamble — compiled PDF shows bare title | Add 3-5 sentence preamble between [L982](thesis.tex#L982) and [L985](thesis.tex#L985) | Phase 1 B2; Ch.5 C5-0-2 |
| B3 | Unreferenced figure `fig:rq2_ablation` ([thesis.tex:839](thesis.tex#L839)) | Add one sentence near L815 or L841 citing it | Ch.4 C4-6-26 |
| B4 | Unreferenced table `tab:missingness_mechanisms` (Ch.2) and `tab:related_work_summary` (Ch.3) | Add a `Table~\ref{…}` citation or drop the `\label` | Phase 1 §5.1; Ch.2 DQ-1-1; Ch.3 MF-10 |

### Tier 1 — blocks rubric
| # | Blocker | Fix | Source |
|---|---|---|---|
| B5 | **MAPE** appears in 4 places | Delete all four | Phase 1 M1-M4 |
| B6 | **Em-dash `---`** in Naive table cell ([thesis.tex:721](thesis.tex#L721)) | Replace with `N/A` | Phase 1 E1; Ch.4 C4-4-5 |
| B7 | Ch.4 §4.4.3 MAPE paragraph ([thesis.tex:740](thesis.tex#L740)) also contains factual error ("Saturday and Sunday panel rows" — panel is ISO-weekly) | Delete the whole MAPE justification sentence | Ch.4 C4-4-23 |
| B8 | Missing **social/ethical/SDG** paragraph in §5.1 Discussion | Add per C5-1-21 | Ch.5 C5-1-21 |
| B9 | Missing explicit **practical-implications** paragraph in §5.1 Discussion | Add per C5-1-21 | Ch.5 C5-1-21 |
| B10 | Ch.2 L304 MAPE defence sentence references "the proposal" (Exposé) | Delete sentence | Ch.2 FA-3 |
| B11 | Three Exposé references in Ch.2 (FA-3, DQ-2-2, DQ-3-4) and one in Ch.1 (L154, SC-13) | Delete or rewrite without "the Expose/proposal" | Ch.1 SC-13; Ch.2 FA-3, DQ-2-2, DQ-3-4 |
| B12 | MAPE comment block at [thesis.tex:477-478](thesis.tex#L477-L478) | Delete | Ch.4 C4-0-1 |

### Tier 2 — grammar / typo that cause reader friction
| # | Blocker | Fix | Source |
|---|---|---|---|
| B13 | [L732](thesis.tex#L732) `Ridge and XGBoost, are trained` — spurious comma | Delete comma | Ch.4 C4-4-14 |
| B14 | [L734](thesis.tex#L734) broken sentence `is not to rank algorithms, it also quantifies ...` | Full rewrite per C4-4-15 | Ch.4 C4-4-15 |
| B15 | [L740](thesis.tex#L740) typo `weeks that meet with large errors` | Rewrite per C4-4-22 | Ch.4 C4-4-22 |
| B16 | [L762](thesis.tex#L762) broken sentence `on the hours scale to the log scale, reflects` | Rewrite per C4-5-14 | Ch.4 C4-5-14 |
| B17 | [L864](thesis.tex#L864) typo `discomposes` → `perturbs`/`decomposes` | Fix | Ch.4 C4-7-2 |
| B18 | [L1001](thesis.tex#L1001) typo `transfered` + missing space `data.This` + broken subject/verb agreement | Full rewrite per C5-2-3 | Phase 1 T1; Ch.5 C5-2-3 |
| B19 | [L1011](thesis.tex#L1011) anthropomorphism `the model cannot comprehend` | `cannot anticipate` | Phase 1 T2; Ch.5 C5-2-14 |
| B20 | [L1034](thesis.tex#L1034) article/number mismatch `an operating manufacturing plants` | Fix to singular | Ch.5 C5-4-2 |
| B21 | [L989](thesis.tex#L989) dangling clause `lags describing a different aspect of the problem` | Rewrite per C5-1-8 | Ch.5 C5-1-8 |
| B22 | [L766](thesis.tex#L766) spurious comma before `splits them into three operational regimes` | Delete comma | Ch.4 C4-5-17 |
| B23 | [L941](thesis.tex#L941) misplaced "only" in `only fails gracefully` | Rewrite per C4-7-35 | Ch.4 C4-7-35 |

---

## Part 3 — Global sweeps (apply BEFORE per-chapter edits)

### 3.1 American-English spelling (single pass)

Sed-style replacement with manual review. **Do not touch `\label{}` IDs** — labels stay as they are to preserve `\ref{}` integrity. Only fix the visible text.

```
centre                → center                   (incl. work centre, per-work-centre, per work centre)
centres               → centers
centred               → centered
behaviour             → behavior
summarise             → summarize                 (all inflections: summarised/summarises/summarising)
organise              → organize                  (organised/organising)
organisational        → organizational
optimise              → optimize                  (optimising/optimisation)
minimise              → minimize                  (minimising)
specialise            → specialize                (specialising)
prioritise            → prioritize                (prioritised)
regularise            → regularize                (regularised/regularising)
normalise             → normalize                 (normalises)
visualise             → visualize                 (visualises)
realise               → realize                   (realised)
parameterise          → parameterize              (parameterised)
emphasise             → emphasize                 (emphasising)
initialise            → initialize                (initialised/initialise)
anonymise             → anonymize                 (anonymised)
winsorise             → winsorize                 (winsorised)
finalise              → finalize                  (finalisation)
modelling             → modeling                  (modelled)
labelling             → labeling                  (labelled — only in commented-out draft appendix)
colour                → color                     (coloured)
artefact              → artifact
operationalise        → operationalize            (operationalising)
```

**Excluded from bulk replace (manual):**
- `analyse` → `analyze`: verify no `catalyse` / `hydrolyse` false positives.
- `programme` / `whilst` / `learnt` / `amongst` / `towards`: grep confirmed absent, but re-check after any rewrites land.

**Verification command:** `grep -nE '(centre|behaviou|organis|summaris|optimis|minimis|specialis|regularis|normalis|visualis|realis|parameteris|emphasis|modelling|labell|colour|artefact|operationalis|initialis|anonymis|winsoris|finalisa)' docs/thesis/thesis.tex` must return **zero non-comment hits**.

### 3.2 Compound-modifier hyphens (manual but mechanical)

| From | To | Where |
|---|---|---|
| `per work center` | `per-work-center` | bulk |
| `per work centre` | `per-work-center` | bulk (after 3.1) |
| `work center dummies` | `work-center dummies` | Ch.4 |
| `plant wide` | `plant-wide` | Ch.4 §4.8 |
| `short horizon` | `short-horizon` | Ch.4 §4.8 |
| `eight hour shift` | `eight-hour shift` | Ch.4 §4.8, Ch.5 §5.3 |
| `pool level` / `resource level` | `pool-level` / `resource-level` | Ch.5 §5.2 |
| `parallel machine` | `parallel-machine` | Ch.5 §5.2 |
| `setup time ratios` | `setup-time ratios` | Ch.5 §5.2 |
| `planner facing` | `planner-facing` | Ch.5 §5.2 |
| `accuracy robustness trade-off` | `accuracy-robustness trade-off` | Ch.5 §5.3 |
| `domain driven` | `domain-driven` | Ch.5 §5.3 |
| `four table schema` | `four-table schema` | Ch.5 §5.4 |
| `insufficient history failure mode` | `insufficient-history failure mode` | Ch.5 §5.4 |
| `plant specific` | `plant-specific` | Ch.5 §5.4 |
| `Sub weekly` | `Sub-weekly` | Ch.5 §5.4 heading |
| `Shift level` | `Shift-level` | Ch.5 §5.4 |
| `Two stage` | `Two-stage` | Ch.5 §5.4 |
| `tier level mix indicators` | `tier-level mix indicators` | Ch.5 §5.4 |
| `routing step dispersion` | `routing-step dispersion` | Ch.5 §5.4 |
| `material specific variance` | `material-specific variance` | Ch.5 §5.4 |
| `actual to planned minutes` | `actual-to-planned minutes` | Ch.5 §5.4 |
| `industrial capacity planning tools` | `industrial capacity-planning tools` | Ch.5 §5.4 |

### 3.3 MAPE removal

1. [Ch.2 L304](thesis.tex#L304): delete or rewrite sentence per Phase-1 M1.
2. [Ch.4 L477-478](thesis.tex#L477-L478): delete the 2-line MAPE comment block.
3. [Ch.4 L740](thesis.tex#L740): delete the entire MAPE justification sentence (factual error + rubric violation).
4. **Verify** after: `grep -n MAPE docs/thesis/thesis.tex` returns zero.

### 3.4 Em-dash removal

1. [Ch.4 L721](thesis.tex#L721): replace `---` in Naive row's Library column with `N/A`.
2. Appendix draft dashes at L1083, L1120 will disappear when appendices are uncommented — fix at that time (convert `---` to `:`).
3. **Verify** after: `grep -n -- '---' docs/thesis/thesis.tex` returns only comment-internal matches (or nothing).

### 3.5 Acronym handling (policy = expand once thesis-wide)

Remove these duplicate expansions:
| Line | Term | Action |
|---|---|---|
| [Ch.4 L481](thesis.tex#L481) | `Predictive Capacity Consumption (PCC)` | drop parenthetical; just `PCC` |
| [Ch.4 L481](thesis.tex#L481) | `Discrete-Event Simulation (DES)` | drop parenthetical |
| [Ch.4 L512](thesis.tex#L512) | `Discrete-Event Simulation` re-expansion | `DES` |
| [Ch.4 L708](thesis.tex#L708) | `Simple Exponential Smoothing (SES)` | `SES` |
| [Ch.4 L740](thesis.tex#L740) | `Mean Absolute Error ($\text{MAE}$)` and `Root Mean Squared Error ($\text{RMSE}$)` | remove both expansions |
| [Ch.5 L989](thesis.tex#L989) | `Predictive Capacity Consumption as formulated...` | `PCC as formulated...` |
| [Ch.5 L1018](thesis.tex#L1018) | `Predictive Capacity Consumption, defined as...` | `PCC, defined as...` |
| [Ch.5 L1044](thesis.tex#L1044) | `bill of materials (BOMs)` | `BOM` |

First-use expansions to **add** (per Phase 1 §6):
- Abstract [thesis.tex:31-40](thesis.tex#L31-L40): spell `ARIMA` on first use.
- §1.2 / §1.1: fix `ERP (Enterprise Resource Planning)` → `Enterprise Resource Planning (ERP)` order. Same for MES.
- Ch.4 L578: define `IQR` as `interquartile range` on first use.
- Ch.4 L723/L738: define AIC on first use (currently used at L723 before definition at L738 — swap order).

### 3.6 DES hyphenation

Canonical: `Discrete-Event Simulation` (with hyphen). Enforce globally. Currently inconsistent (`Discrete Event Simulation` in Ch.1 L144).

**Verification:** `grep -nE 'Discrete[- ]Event' docs/thesis/thesis.tex` — all hits should render `Discrete-Event`.

### 3.7 Tier-count wording

Replace Ch.2 §2.3 preamble "two tiers" → "three tiers" (one industry baseline, two statistical time-series models, two feature-based ML models) to align with Ch.1 and Ch.4.

### 3.8 AI-smell repeat transitions

| Line | Current | Replacement |
|---|---|---|
| [Ch.4 L859](thesis.tex#L859) | `Taken together, the ablation and the feature-importance analysis identify ...` | `Jointly, the ablation and the feature-importance analysis identify ...` |
| [Ch.4 L976](thesis.tex#L976) | `Taken together, the four dimensions suggest ...` | `In aggregate, the four dimensions suggest ...` |
| [Ch.4 L814](thesis.tex#L814) | `In other words, the ML tier does not outperform ARIMA ...` | Delete the opener; start with `The ML tier does not outperform ARIMA ...` |
| [Ch.1 L40](thesis.tex#L40) | `Additionally, a sensitivity analysis reveals ...` | `The sensitivity analysis reveals ...` |
| [Ch.1 L95, L112](thesis.tex#L95) | `leverage` / `leveraged` | `use` / `apply` |
| [Ch.5 L1026](thesis.tex#L1026) | tricolon `directionally accurate, robust, and operationally deployable` | Rewrite per C5-3-19 |

---

## Part 4 — Chapter-by-chapter edit batches

After the global sweeps (Part 3), apply these per-chapter batches. Each batch points to its Phase-2 file for exact rewrites.

### 4.1 Edit order (recommended)

1. Ch.2 Background — fixes oldest issues first, and Ch.2 has the Exposé references that cascade into others.
2. Ch.1 Introduction — Abstract numbers, RQ wording, PCC placement.
3. Ch.3 Related Work — shortest chapter, lowest risk.
4. Ch.4 Methodology and Results — the big one; do **after** global US-spelling + hyphen sweeps.
5. Ch.5 Summary — must-add paragraphs come last so they reference the stable wording in Ch.1/4.
6. Appendices — fill in A/B/C (Phase-1 B1); skip deep review per user instruction.
7. References.bib — orphans, ResearchGate, double-brace acronyms (Phase 1 §9).

### 4.2 Numerical verifications against nb04/05 (batch)

**Do this before editing** so that no value is rewritten incorrectly. Confirm each of these against the canonical notebooks:

| Value | Location | Canon source |
|---|---|---|
| Ridge $\alpha = 500$ | [Ch.4 L724](thesis.tex#L724) | nb04/05 hyperparameter config |
| XGBoost hours-scale $R^2 = 0.595$ | [Ch.4 L762](thesis.tex#L762) | nb04 / back-transform eval |
| XGBoost hours-scale MAE 6.2 h / median 4.6 h | [Ch.4 L762](thesis.tex#L762) | nb04 |
| 72.2% within-1-shift, 92.0% within-2-shift | [Ch.4 L762, L968; Ch.5 L1020](thesis.tex#L762) | nb04 |
| Plant MAE 91.7 h/week, 31.3% of 292.5 h/week | [Ch.4 L775](thesis.tex#L775) | nb04 |
| WC16 MAE ≈ 16 h | [Ch.4 L970](thesis.tex#L970) | nb04 per-WC |
| Ridge CV stability $R^2 = 0.36 \pm 0.17$ | [Ch.4 L742](thesis.tex#L742) | nb04 / nb05 |
| Train times: XGBoost 8.4 s, Ridge 2.8 s, ARIMA 20.1 s, SES 0.1 s, Naive 0.0 s | [Ch.4 L795-799](thesis.tex#L795-L799) | nb04/nb05 |
| 1-year panel size 1,080; 6-month 640 | [Ch.4 L874, L876](thesis.tex#L874) | nb05 RQ3 config |

**Ridge ablation gain** should display as `+0.063` consistently with XGBoost `+0.150` (both 3-dp) per Phase-1 §7.

### 4.3 Per-chapter batches

#### Ch.2 Background — see [review_phase2_ch2_background.md](review_phase2_ch2_background.md)
Priority items:
- Exposé references (FA-3, DQ-2-2, DQ-3-4) — 3 deletions.
- Tier count "two tiers" → "three tiers".
- ARIMA `\item[ARIMA]` reverse acronym at L246.
- α symbol clash between SES (L244) and Ridge (L271).
- MAPE sentence at L304.
- Little's MCAR citation (DQ-1-6).
- tab:missingness_mechanisms unreferenced.
- MRP II vs MRP-II standardisation.
- Section intros <2 paragraphs (§2.2, §2.3, §2.4).

#### Ch.1 Introduction — see [review_phase2_ch1_introduction.md](review_phase2_ch1_introduction.md)
Priority items:
- Abstract: add RMSE, MAE (AB-4).
- PCC defined on first use (AB + §1.1) (P1-7).
- ERP/MES reverse acronym order (P1-8, M1-3).
- RQ1 verb `predict` → `forecast` (RQ-1).
- Exposé reference at [L154](thesis.tex#L154) — delete (SC-13).
- Single-sentence paragraph at [L140](thesis.tex#L140) (RQ-4).
- Ch.5 cross-ref at end of Ch.1: check if it still says "Summary" — update to whatever D2 resolves.

#### Ch.3 Related Work — see [review_phase2_ch3_related_work.md](review_phase2_ch3_related_work.md)
Priority items:
- `favour` (L407) and `researches` (L363) typos.
- Gap 3 logic reorder at [L454](thesis.tex#L454) (RG-3-3).
- SHAP not expanded at [L415](thesis.tex#L415) (DL-12).
- Industry 5.0 reference at [L426](thesis.tex#L426) (SD-4).
- `taylor2018prophet` orphan — cite at first Prophet mention or drop.
- Table 2 `tab:related_work_summary` unreferenced.
- Ridge Regression vs Ridge regression capitalisation.
- 2,120 training rows claim — verify.
- `position of its contribution` typo (CH3-1).
- DES redefined at L428 (SD-7).

#### Ch.4 Methodology and Results — see [review_phase2_ch4_methodology_results.md](review_phase2_ch4_methodology_results.md)
Priority items (after global sweeps):
- MAPE paragraph at L740 **deleted entirely** (B7, C4-4-23).
- MAPE comment block at L477-478 deleted (B12, C4-0-1).
- Em-dash at L721 → N/A (B6, C4-4-5).
- Broken sentences at L732, L734, L762, L740, L766, L941 (B13-B16, B22, B23).
- Typo `discomposes` at L864 (B17, C4-7-2).
- Unreferenced figure `fig:rq2_ablation` (B3, C4-6-26).
- Forward refs to `app:hyperparameters` at L708, L710 — contingent on D1.
- Subsection heading `Planning Features` → `Planning-Feature Ablation` (C4-6-13).
- Captions with section refs (Ch.4 C4-6-32).
- Single-sentence paragraphs at L636, L658, L666 (C4-3-2, C4-3-23, C4-3-28).
- `Taken together` at L859, L976 (§3.8).
- XGBoost hyperparameter table: either list all 8 or add `(full grid in Appendix A)` contingent on D1.

#### Ch.5 Summary — see [review_phase2_ch5_summary.md](review_phase2_ch5_summary.md)
Priority items:
- Chapter title decision (D2) and preamble (B2, C5-0-2).
- **Add Practical-implications paragraph** to §5.1 (B9, C5-1-21 part a).
- **Add Social/ethical/SDG paragraph** to §5.1 (B8, C5-1-21 part b).
- Ch.5 L1001 garbled sentence (B18, C5-2-3).
- Ch.5 L1011 anthropomorphism (B19, C5-2-14).
- Ch.5 L1034 article/number mismatch (B20, C5-4-2).
- Ch.5 L989 dangling clause (B21, C5-1-8).
- Ch.5 L1044 BOM redefinition (C5-4-15).
- Ch.5 L1026 tricolon / compound-modifier closer (C5-3-19).
- Ch.5 L1020 unit mismatch "minute scale is 4.6 hours" (C5-3-4).
- Ch.5 L1024 "less than 0.011" — ARIMA worst case equals 0.011 exactly (C5-3-15).
- Optional §5.2 addition on seed / benchmark comparability (D14, C5-2-19).

#### Appendices — no deep review; must still address B1
- Uncomment A/B/C ([thesis.tex:1060-1161](thesis.tex#L1060-L1161)).
- Fill [FILL IN ...] placeholder in Appendix C.
- Verify every table row matches canonical nb04/05.
- Convert `---` to `:` in appendix captions (L1083, L1120).
- Fix `labelled` → `labeled` in commented draft (L1135 if retained).

#### references.bib
Source: Phase 1 §9.
- Remove orphans `taylor2018prophet`, `owen2024supplychain`, `david2024defect`, `karmaker2025`, `hu2021timeseries`, `goyal2024synthetic`, `hoppe2025synthetic`, `wen2021augmentation` — unless one can be cited in a future revision (e.g., `taylor2018prophet` at first Prophet mention in Ch.3).
- Replace ResearchGate URLs on `owen2024supplychain` / `karmaker2025` with the primary venue or drop both.
- Double-brace acronyms in titles: `MRP`, `MRP II`, `ARIMA`, `XGBoost`, `LSTM`, `SES`, `ERP`, `MES`, `DES`, `CRP`, `IIoT`, `OEE`, `SVR`.
- Run IEEE field completeness pass: every `@article` has `journal/volume/pages/year`; every `@inproceedings` has `booktitle/year`; every `@book` has `publisher/year`; every `@misc` has `howpublished` or `url+urldate`.

---

## Part 5 — Verification plan (run AFTER editing)

Commands the user runs (or Claude runs on request) once edits are committed:

1. **MAPE purge:**
   `grep -n MAPE docs/thesis/thesis.tex` → expect zero output.
2. **Em-dash purge:**
   `grep -n -- '---' docs/thesis/thesis.tex` → expect zero output outside `%%%` banners.
3. **US spelling:**
   `grep -nE '(centre|behaviou|organis|summaris|optimis|specialis|regularis|normalis|visualis|realis|parameteris|emphasis|modelling|labell|colour|artefact|operationalis|initialis|anonymis|winsoris|finalisa)' docs/thesis/thesis.tex` → expect only matches inside `\label{}` IDs (which we preserve).
4. **Cross-references resolve:** compile `pdflatex docs/thesis/thesis.tex` and check the `.log` for `Warning: There were undefined references` and for `Warning: Citation ... undefined`.
5. **Figure/table in TOC:** verify `fig:rq2_ablation`, `tab:missingness_mechanisms`, `tab:related_work_summary` appear in the List of Figures / List of Tables with a page number (i.e., actually referenced).
6. **RQ traceability:** every RQ verbatim wording in §1.3 matches the answer opening in §5.3.
7. **Abstract standalone:** read Abstract cold — does it include $R^2$, RMSE, MAE, hours-scale error, and a one-line PCC definition?
8. **Rubric items:**
   - §5.1 contains explicit practical-implications paragraph ✓
   - §5.1 contains explicit social/ethical/SDG paragraph ✓
   - §5.2 lists ≥6 limitations with concrete content (no boilerplate) ✓
   - §5.3 closes all three RQs explicitly ✓
9. **Chapter 5 preamble present:** manual inspection of [thesis.tex:983](thesis.tex#L983).
10. **Orphan bib purge:** `bibtex` run produces no warnings about unused keys (or confirms the remaining orphans are intentional).

---

## Part 6 — Summary of what's NOT in this plan

- **Figure / plot regeneration.** The plan assumes figures at `docs/thesis/figures/*.pdf` match the canonical numbers. If figures were produced under non-canonical params, they need regeneration — out of scope for this review.
- **Additional notebooks.** The plan does not require re-running nb04/05; only reading their canonical values.
- **Appendix content verification.** Deep review of appendix content was skipped per user instruction; only the "uncomment + fill" action remains.
- **Multi-seed stability study** (mentioned as a *limitation* in C5-2-19; adding it would be new work, not a review finding).
- **Language or voice rewrite beyond the flagged items.** The review flags specific constructions; it does not propose a stylistic rewrite of passages that read correctly.

---

## Part 7 — Suggested editing session structure

1. **Session 1 (30 min):** work through Part 1 decision checklist with the user; record D1-D25 answers at the top of this file.
2. **Session 2 (60 min):** run Part 3 global sweeps (US spelling, hyphens, MAPE, em-dash, DES, acronyms, tier-count, AI-smell openers). Commit after this step.
3. **Session 3 (60 min):** Ch.2 + Ch.1 + Ch.3 batches (shorter chapters). Commit.
4. **Session 4 (90 min):** Ch.4 batch. Commit.
5. **Session 5 (60 min):** Ch.5 batch, including the two new Discussion paragraphs. Commit.
6. **Session 6 (45 min):** Appendices (uncomment + fill), references.bib audit. Commit.
7. **Session 7 (30 min):** run Part 5 verification; fix regressions; final PDF build.

Total editing effort estimate: **6-8 hours of focused work** if decisions are resolved up front.

---

**End of Phase 3 plan.** The per-chapter Phase-2 files remain the source of truth for every individual rewrite; this document exists to sequence them.