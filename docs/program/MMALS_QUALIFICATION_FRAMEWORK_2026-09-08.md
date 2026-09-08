# MMALS qualification framework — from observed performance to latent capability claims

**Date:** 2026-09-08  
**Status:** research qualification plan; not validated MMALS evidence  
**Scope:** MMALS core / continual learning / regime inference / future predictive extensions

## 1. Why this qualification framework exists

The immediate trigger is the argument developed by Quattrociocchi, Capraro, and Marcus in *Statistical approximation is not general intelligence* (Nature 650, 792, 2026; DOI 10.1038/d41586-026-00495-y) and in the longer author version reviewed on 2026-09-08.

The transferable engineering lesson is narrower and stronger than the ontological claim in the title:

> **Observed performance does not, by itself, identify the latent capability that produced it.**

For MMALS this means:

- high task accuracy does not demonstrate continual-learning competence;
- continual-learning gains do not demonstrate mutualistic organization;
- good routing does not demonstrate correct regime inference;
- prediction does not demonstrate a world model;
- a benchmark pass does not by itself qualify the system for a broader claim.

Qualification must therefore be **claim-relative** and trace each claim through evidence, uncertainty, and a decision rule.

## 2. Qualification principle

Use the chain:

`REQUIREMENT / RESEARCH CLAIM -> TESTABLE CLAIM -> EVIDENCE -> UNCERTAINTY -> DECISION`

Every higher-order MMALS claim must be decomposed into lower-order observable properties. Evidence at one layer is necessary but not automatically sufficient for the next layer.

The framework deliberately separates six qualification layers:

1. task performance;
2. continual adaptation;
3. robustness under novelty / distribution shift;
4. uncertainty and abstention;
5. MMALS architectural claims: regime inference, structural adaptation, mutualistic benefit, minimality;
6. world-model-like predictive capability, only if that research direction is later activated.

## 3. Qualification matrix

| Layer | Claim to qualify | Minimum evidence | Key metrics / tests | Main false inference to avoid | Current MMALS status |
|---|---|---|---|---|---|
| **Q0 — Task competence** | A host/system performs the declared task | Held-out IID evaluation; repeated seeds; baseline comparison | Accuracy/loss or task metric; confidence intervals; seed variability | `good score -> general competence` | Existing evidence on current benchmark families; still benchmark-bounded |
| **Q1 — Continual adaptation** | MMALS learns new situations while preserving useful prior competence | Ordered task/regime sequences; replay/regularization/fixed-MoE baselines | average accuracy; forgetting/retention; backward transfer; forward transfer where meaningful; adaptation sample cost; runtime/memory | `final accuracy -> continual-learning quality` | Core program; already central to RC2I and multi-dataset qualification |
| **Q2 — Novelty / OOD robustness** | Competence persists, or failure is detected, under declared shifts | Predeclared shift taxonomy; unseen transformations/domains; smooth drift vs abrupt change; held-out regime tests | per-shift performance; worst-group/worst-shift loss; degradation curves; OOD detection; safe/risky region characterization | `one OOD dataset -> general robustness` | Partly planned; requires explicit shift taxonomy and controlled regime experiments |
| **Q3 — Uncertainty / abstention** | MMALS knows when evidence is insufficient and can abstain/escalate | Calibration sets separated from selection/evidence sets; shifted-domain calibration; selective prediction tests | Brier/NLL; calibration curves; ECE only as one estimator; risk-coverage / selective-risk curves; abstention utility/cost | `high confidence -> knowledge` or `low ECE -> trustworthy system` | Calibration appears in current design principles; needs explicit qualification protocol |
| **Q4a — Regime inference** | A candidate regime corresponds to a persistent, functionally relevant difference | Synthetic/controlled ground truth first; persistence tests; held-out confirmation; false-birth tests under noise/drift | regime precision/recall where ground truth exists; detection delay; false regime births; missed regimes; stability across seeds | `cluster/distance -> dynamical regime` | Explicit research hypothesis; not yet demonstrated |
| **Q4b — Structural decision quality** | REUSE / ADAPT / FORK / NEW REGIME choices improve the competence-cost trade-off | Compare controller decisions against always-update, always-expand, fixed MoE, replay/CL baselines; oracle upper bound where possible | routing/selection regret; retained/new competence; number of forks/hosts; unnecessary growth; adaptation cost; decision latency | `plausible routing -> useful structural adaptation` | Candidate lifecycle specified; controller qualification still future work |
| **Q4c — Mutualistic benefit** | Cooperation among hosts produces benefit not attributable to mere extra capacity or ensembling | Matched-capacity baselines; communication ablation; isolate directional host-to-host contributions; remove/reverse exchanges | marginal gain per interaction; synergy beyond best host / matched ensemble; cost-normalized benefit; dependency asymmetry; harm rate | `collective gain -> mutualism` | **Not currently demonstrated as a scientific claim**; needs dedicated falsification |
| **Q4d — Minimal sufficient complexity** | MMALS grows only when simpler structures no longer satisfy the competence contract | Complexity-regularized comparisons; prune/merge tests; matched performance frontiers | hosts/params/memory/energy/latency/audit burden vs competence; Pareto frontier; unnecessary-fork rate | `smaller -> sufficient` or `larger -> adaptive` | Program hypothesis; must be evaluated jointly with competence |
| **Q5a — Predictive state sufficiency** | Internal state preserves information needed to predict declared future variables | Train/test future prediction from internal state; compare raw/history/compressed alternatives; multi-horizon tests | predictive log loss/error; information-preservation proxies; horizon-dependent degradation | `useful embedding -> sufficient state` | Future extension only |
| **Q5b — Transition / intervention validity** | The model captures how relevant state changes, including under action/intervention where applicable | Action-conditioned or controlled intervention experiments; counterfactual/transition holdouts; unseen dynamics tests | transition error; intervention effect error; planning model error; change-detection accuracy | `next-step prediction -> causal/dynamical model` | Not currently demonstrated |
| **Q5c — Decision usefulness of predictive model** | Learned dynamics improve planning/control/decision quality on tasks not used to define the representation | Separate model-learning and downstream decision tests; new tasks over related environments | regret/return/decision loss; transfer to held-out downstream tasks; robustness to dynamics change | `good predictor -> useful world model` | Not currently demonstrated; only qualifies a future world-model claim |

## 4. Why the layers must remain separate

The core logical rule is:

`evidence(Q_n) does not automatically imply Q_(n+1)`

Examples:

- Q0 task performance is necessary evidence for Q1 but does not establish continual adaptation.
- Q1 continual-learning gains do not establish Q4c mutualistic benefit.
- Q4a correct regime detection does not establish Q4b that structural actions are optimal or useful.
- Q5a predictive sufficiency does not establish Q5b interventional validity.
- Q5b transition validity does not establish Q5c decision usefulness.

This separation is specifically intended to prevent capability inflation by terminology.

## 5. Mandatory baselines and controls

At minimum, future MMALS qualification campaigns should include:

- single fixed-capacity learner;
- always-update learner;
- replay baseline;
- representative regularization/distillation continual-learning baseline;
- fixed mixture-of-experts;
- always-expand architecture;
- MMALS adaptive controller;
- matched-capacity ensemble where mutualistic benefit is claimed;
- oracle or privileged-information reference in controlled synthetic studies when useful to estimate achievable upper bounds.

Whenever MMALS has more parameters, memory, routing compute, replay data, or training opportunities than a comparator, report the asymmetry explicitly and include cost-normalized comparisons.

## 6. Qualification of the word "mutualistic"

The biological metaphor must not be accepted as evidence.

A defensible MMALS mutualism claim should require evidence that interaction between components gives a reproducible benefit **beyond what is explained by simple capacity, ensembling, or independent specialization**.

Candidate operational tests:

1. **No-exchange ablation:** remove information/resource exchange between hosts while preserving capacity.
2. **Matched ensemble control:** compare against independent experts combined only at inference.
3. **Contribution intervention:** selectively disable one host's contribution to another and measure marginal effect.
4. **Bidirectionality / asymmetry analysis:** determine whether benefit is mutual, commensal, parasitic, or simply centralized routing.
5. **Cost accounting:** subtract communication, memory, latency, and update cost from the claimed benefit.
6. **Persistence:** require the benefit across seeds, task orders, and more than one benchmark family.

Until such evidence exists, use **"mycelium-inspired"** or **"cooperative modular"** as architectural descriptions and treat **"mutualistic"** as a research hypothesis.

## 7. OOD / novelty qualification must use a shift taxonomy

Do not report a generic "OOD score" alone. Predeclare which novelty is being tested, for example:

- covariate / appearance shift;
- label-prior shift where relevant;
- concept/conditional shift;
- smooth drift;
- abrupt regime change;
- recurring regime;
- compositional novelty;
- corrupted/noisy observations;
- missing information;
- dynamics change;
- action/intervention change in future control experiments.

Qualification should identify **where** MMALS generalizes, **where** it fails safely, and **where** it fails silently.

## 8. Uncertainty is a separate qualification object

Accuracy and calibration must be evaluated separately. A system can be accurate but poorly calibrated, or better calibrated while still being wrong too often.

Do not rely on ECE alone. Use at least:

- proper scoring rule: Brier score and/or negative log-likelihood;
- reliability/calibration curves;
- an ECE variant with estimator choices documented;
- risk-coverage/selective-risk analysis when abstention is available;
- calibration under declared distribution shifts;
- decision-relative cost of false confidence vs abstention.

For MMALS, uncertainty should influence structural actions only after showing that it predicts competence failure or regime incompatibility better than simpler signals.

## 9. Qualification sequence for the current program

This framework must **not displace the current RC2I sequence**.

### Phase A — close the validated continual-learning line

1. RC2I smoke;
2. RC2I evidence;
3. RC2I robust on FashionMNIST;
4. multi-dataset robust qualification on MNIST, FashionMNIST, RotatedMNIST, PermutedMNIST;
5. comparative campaign with accuracy, forgetting, cost, parameters, runtime, memory, and auditability.

### Phase B — add qualification layers without changing the core claim

6. add explicit calibration / abstention protocol;
7. define and preregister shift taxonomy;
8. characterize degradation by shift rather than one aggregate robustness score;
9. formalize host domains of validity.

### Phase C — qualify structural regime adaptation

10. controlled synthetic regimes with known ground truth;
11. false-regime-birth tests under noise and smooth drift;
12. REUSE / ADAPT / FORK / NEW REGIME controller vs simpler baselines;
13. matched-capacity and cost-normalized comparisons;
14. merge/prune/retire tests.

### Phase D — test the specifically MMALS claim

15. mutualism-focused ablations and matched-ensemble controls;
16. quantify whether exchange creates synergy beyond capacity;
17. reject or narrow the mutualism claim if gains disappear under matched controls.

### Phase E — only if predictive/world-model research is activated

18. predictive-state sufficiency;
19. transition-dynamics prediction;
20. action-conditioned/interventional validity where relevant;
21. downstream planning/decision transfer on tasks not used to train the representation.

## 10. Recommended decision vocabulary

For each claim use:

- **PASS** — prespecified evidence threshold met;
- **FAIL** — evidence contradicts the claim or violates the threshold;
- **NOT DEMONSTRATED** — evidence is insufficient to decide;
- **OUT OF SCOPE** — claim not part of the current qualification phase.

Avoid translating `NOT DEMONSTRATED` into `FAIL`, and avoid translating one `PASS` into a broader claim.

## 11. Scientific stop / narrowing conditions

Narrow or reject an MMALS claim if:

- matched-capacity baselines remove the apparent benefit;
- regime birth is mostly driven by representation distance without functional relevance;
- uncertainty does not predict error or structural incompatibility reliably enough to improve decisions;
- structural branching increases cost without improving retained/new competence;
- mutualistic gains vanish under communication or contribution ablation;
- a simpler fixed MoE or standard continual-learning method matches the competence-cost frontier;
- world-model-like claims rely only on next-step prediction and fail intervention or downstream-decision tests.

## 12. Literature anchors for this framework

This is a synthesis and proposed qualification architecture, not a direct reproduction of any one source.

- Quattrociocchi, W., Capraro, V., Marcus, G. (2026). *Statistical approximation is not general intelligence*. Nature 650, 792. DOI 10.1038/d41586-026-00495-y.
- Legg, S., Hutter, M. (2007). *Universal Intelligence: A Definition of Machine Intelligence*. Minds and Machines 17, 391–444.
- Wang, L., Zhang, X., Su, H., Zhu, J. (2023/updated). *A Comprehensive Survey of Continual Learning: Theory, Method and Application*. arXiv:2302.00487.
- Yu, H., Liu, J., Zhang, X., Wu, J., Cui, P. (2024). *A Survey on Evaluation of Out-of-Distribution Generalization*. arXiv:2403.01874.
- Posocco, N., Bonnefoy, A. (2021). *Estimating Expected Calibration Errors*. arXiv:2109.03480.
- Warrier, A. et al. (2025). *Benchmarking World-Model Learning*. arXiv:2510.19788.

## 13. Central reusable principle

> **Never infer a latent capability from an observed score without testing the invariances, interventions, adaptations, or decision consequences that the capability claim entails.**

MMALS qualification should therefore aim not to prove that the architecture is "intelligent", "mutualistic", or a "world model" in the abstract, but to establish progressively which precise capabilities are demonstrated, under which domains of validity, at what cost, and with what remaining uncertainty.
