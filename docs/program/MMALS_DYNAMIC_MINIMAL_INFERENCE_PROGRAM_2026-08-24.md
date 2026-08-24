# MMALS program extension — Minimal Sufficient Dynamic Inference

**Date:** 2026-08-24  
**Status:** research-program hypothesis; not validated MMALS evidence  
**Scope:** MMALS core / continual learning / regime inference / system-of-systems extension

## 1. Research objective

Explore whether MMALS can evolve toward the **smallest explainable inference system that remains dynamically sufficient for the situations it has already learned and can adapt to new evidence without unnecessary growth**.

The working principle is:

> Reuse first. Adapt when established competence can be preserved. Fork when specialization is needed. Create a candidate new regime only when existing hosts are no longer dynamically compatible with the evidence.

This is an architectural hypothesis, not a current result.

## 2. Candidate lifecycle

For incoming evidence `x` and a bank of hosts `H={H_i}`:

1. **REUSE** — an existing host is already competent and calibrated.
2. **ADAPT** — update an existing host if the new competence can be gained without material degradation of previously demonstrated competence.
3. **FORK** — inherit from a useful host but specialize when joint adaptation creates incompatible constraints or forgetting.
4. **NEW REGIME** — create a candidate regime/host when the observation is outside the demonstrated domains of validity of existing hosts.
5. **VERIFY** — a novelty or distance signal is only a hypothesis trigger; it does not prove a real, stable, or causal regime.
6. **REMEMBER** — preserve the evidence, previous competence contract, transformation, and rationale.
7. **MERGE / PRUNE / RETIRE** — reduce unnecessary complexity when evidence later shows two regimes are equivalent, redundant, obsolete, or unsupported.

The preferred order is therefore:

`REUSE -> ADAPT -> FORK -> CANDIDATE NEW REGIME`

and complexity should increase only when supported by evidence.

## 3. Non-regression competence contract

A candidate adaptation `H_i^t -> H_i^(t+1)` should be accepted only if it improves or satisfies the new target while preserving previously demonstrated competence within an explicit tolerance.

Conceptually:

`L_new(H_i^(t+1)) <= target_new`

and

`L_old(H_i^(t+1)) <= L_old(H_i^t) + epsilon`

The operational definition of `L_old`, `L_new`, `epsilon`, calibration, coverage, and safety constraints must be benchmark-specific and preregistered. Strict zero-regression everywhere is not assumed to be realistic.

## 4. Minimality objective

A future MMALS objective may explicitly penalize unnecessary system complexity:

`min C(H, theta)`

subject to demonstrated competence, calibration, memory, evidence, and action constraints.

Candidate complexity terms include:

- number of active hosts;
- parameter count and memory footprint;
- routing and communication cost;
- replay / evidence-memory cost;
- inference latency and energy;
- human explanation and audit burden.

Minimality therefore means **minimal sufficient system complexity**, not simply fewest parameters.

## 5. Dynamic compatibility instead of one global distance

A single Euclidean latent distance is unlikely to be sufficient for regime decisions. Candidate evidence should combine several notions of compatibility, for example:

- representation / latent distance `D_z`;
- route distance `D_r`;
- output or functional distance `D_y`;
- local sensitivity / Jacobian or transformation distance;
- transition-dynamics compatibility;
- calibrated uncertainty;
- host competence and memory consistency.

Working hypothesis:

`D_MMALS = f(D_representation, D_behavior, D_transition, D_competence, D_memory, uncertainty)`.

A host may eventually learn not only an inference function but also a **local geometry / domain-of-validity model** describing where that inference remains trustworthy.

## 6. Regimes are hypotheses, not clusters

Keep the following distinctions explicit:

- statistical cluster != dynamical regime;
- dynamical regime != causal regime;
- large distance != proof of novelty;
- novelty detector != justification for permanent architectural growth.

A candidate regime should require persistence, held-out evidence, functional relevance, calibration, and where appropriate intervention or transition evidence.

## 7. Interdisciplinary research bridges to examine

These are sources of mathematical tools and analogies, not claims of equivalence.

### 7.1 Sampling and reconstruction

Signal theory asks when a constrained continuous object can be reconstructed from a finite set of observations. Related MMALS question: **what is the smallest observation/state representation that preserves the dynamics and decisions that matter?**

Relevant notions to study include sampling, sufficient representations, delay embeddings, Takens-style reconstruction, and observability.

### 7.2 Local-to-global conservation

Continuity equations and divergence theorems illustrate how local constraints can impose global structure. Related MMALS question: **which local invariants, conservation-like constraints, or compatibility conditions reduce the space of admissible system evolutions?**

No physical conservation law is assumed for MMALS without explicit derivation and evidence.

### 7.3 Local geometry and manifolds

A globally complex state space may admit locally simpler charts and transition rules. Related MMALS hypothesis: a single global metric may be inferior to regime-dependent local geometries with explicit transition maps.

### 7.4 Deterministic chaos and stochastic dynamics

Chaos is deterministic sensitivity to initial conditions, not absence of a model. Stochastic dynamics include an explicit probabilistic component. A system can contain both. Related MMALS question: **can useful regime or risk probabilities remain inferable when exact long-horizon trajectories are not?**

### 7.5 Attractors, transitions, and committors

Instead of predicting an entire future trajectory, one may estimate the probability of reaching one region/regime before another. This suggests a possible bridge between dynamical-systems committors, MMALS inferred context, and belief-state decision models. This bridge is unvalidated and should be tested rather than asserted.

### 7.6 Information and compression

Observed dimensionality can be much larger than intrinsic dynamical dimensionality. MMALS should test whether compression preserves task competence, transition structure, uncertainty, and auditability rather than rewarding compression alone.

## 8. Relationship to continual learning

This extension reframes stability-plasticity as a **structural choice** as well as a parameter-update problem:

- preserve the current host;
- transform it;
- fork it;
- instantiate a new regime;
- later merge/prune when evidence permits.

This must be compared against established continual-learning methods rather than treated as intrinsically superior.

## 9. Relationship to a world model

A **world model** is generally an internal predictive model of how relevant state evolves, often conditionally on actions, that can support prediction, planning, control, or simulation.

This MMALS direction is **world-model-like but is not automatically a world model**. It would move closer to one only if MMALS demonstrates explicit predictive transition dynamics and, for control settings, action-conditioned outcomes rather than only adaptive classification/routing.

A useful future question is therefore:

> Can MMALS evolve from inferred-context continual learning into a compact, auditable, regime-aware predictive model of a complex system without sacrificing previously demonstrated competence?

## 10. Falsifiable comparison program

At minimum compare:

- fixed-capacity / always-update learner;
- always-expand learner;
- fixed mixture-of-experts;
- replay / distillation / regularization CL baselines;
- MMALS adaptive `reuse -> adapt -> fork -> new-regime` policy.

Report jointly:

- old-domain retention / forgetting;
- new-domain learning;
- calibration and abstention;
- regime-detection precision/recall where ground truth is meaningful;
- false regime births and unnecessary forks;
- host count and parameter growth;
- latency, energy, memory, replay cost;
- routing and selection regret;
- robustness across seeds and datasets;
- human-understandable evidence trail.

Ablate distance terms, local geometry, transition evidence, memory constraints, fork rules, and complexity penalties.

## 11. Scientific stop conditions

Reject or narrow the extension if evidence shows that:

- regime birth is unstable or mostly an artifact of representation distance;
- forks grow without measurable retained/new competence benefit;
- a fixed MoE or standard CL baseline matches performance at lower cost;
- local geometries add complexity without predictive or diagnostic value;
- non-regression constraints materially block necessary plasticity;
- minimality penalties merely suppress useful capacity;
- the system cannot explain why a host was reused, transformed, forked, merged, or created.

## 12. Near-term sequence

Do **not** displace the current RC2I qualification line. Treat this as a parallel program extension:

1. finish current RC2I / multi-dataset qualification;
2. formalize a `host domain-of-validity` contract;
3. implement a toy-but-nontrivial reuse/adapt/fork/new-regime controller;
4. run synthetic controlled regime-shift experiments with known ground truth;
5. test false-positive regime creation under smooth drift and stochastic noise;
6. compare against fixed MoE, always-update, always-expand, replay and standard CL baselines;
7. only then test learned local geometry / transition-aware distances;
8. later investigate belief-state / committor / action-conditioned extensions.

## 13. Engineering-system perspective

The long-term systems-engineering objective is not to imitate physics, geometry, signal processing, or information theory. It is to **borrow precise mathematical tools from them when they help describe, observe, compress, partition, predict, or govern evolving complex systems**.

The unifying research question is:

> What is the smallest auditable adaptive model that preserves the information and dynamics required to make reliable decisions about an evolving complex system?
