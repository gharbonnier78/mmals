# Chronicle — 24 August 2026

## Minimal sufficient dynamic inference becomes an explicit MMALS research direction

**Event type:** research transition / hypothesis formation  
**Evidence status:** conceptual synthesis only; no new experimental validation  
**Affected program:** MMALS core / continual learning / regime inference / systems engineering

A new formulation emerged from the discussion of stochastic-chaotic dynamical systems and minimal explanatory models:

> Seek the smallest explainable inference system that remains dynamically sufficient for previously demonstrated situations and adapts to new evidence with the least justified structural growth.

The proposed lifecycle is:

`REUSE -> ADAPT -> FORK -> CANDIDATE NEW REGIME -> VERIFY -> REMEMBER`,

with later `MERGE / PRUNE / RETIRE` when evidence supports simplification.

The key competence constraint is **generalization without material loss of previously demonstrated competence**, expressed operationally through benchmark-specific non-regression tolerances rather than an unrealistic promise of zero loss.

A new regime must not be inferred merely because a point is distant in latent space. The working hypothesis is that regime compatibility should combine representation, route, functional behavior, transition dynamics, uncertainty, competence, and memory evidence. A novelty signal therefore triggers a hypothesis, not a permanent architectural decision.

The interdisciplinary synthesis motivating this direction includes:

- signal sampling and reconstruction: minimal information sufficient to recover relevant structure;
- observability and delay embeddings: infer latent dynamics from partial observations;
- fluid/conservation reasoning: local constraints can restrict global behavior;
- differential geometry: globally complex spaces may be handled through locally simple charts and transition maps;
- deterministic chaos: modeled dynamics can remain intrinsically hard to forecast exactly;
- stochastic dynamics: probabilistic components may coexist with deterministic dynamics;
- attractors, transitions, and committors: transition risk can remain inferable when precise trajectories are not;
- information/compression: intrinsic dynamical dimension may be smaller than raw observed dimension.

These are **research bridges and analogies, not established equivalences**.

The direction is explicitly compatible with the current MMALS scientific discipline: it must be compared against fixed-capacity learners, always-expand learners, fixed MoE, replay/distillation/regularization CL baselines, and the current evidence-qualified MMALS line.

The present RC2I qualification sequence is not replaced. This extension is a parallel hypothesis program to be tested only after current evidence work remains reproducible and closed.

A related question was recorded around the term **world model**. MMALS should not be called a world model merely because it adapts across regimes. It becomes world-model-like only if it learns explicit predictive transition dynamics and, where relevant, action-conditioned consequences supporting prediction/planning/control.

**Research consequence:** the MMALS program now has an explicit candidate principle of **minimal sufficient dynamic inference / complexity-on-evidence**, connecting continual learning, regime inference, local geometry, observability, information preservation, and systems-engineering governance under one falsifiable research objective.

See: `docs/program/MMALS_DYNAMIC_MINIMAL_INFERENCE_PROGRAM_2026-08-24.md`.
