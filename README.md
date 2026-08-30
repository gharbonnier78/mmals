# MMALS Research Chronicle

**Repository description:**
Research article and reproducibility package for MMALS: a mycelium-inspired continual-learning program moving from functional route memory to auditable inferred-context learning, with v0.x-to-v1.1-RC2H evidence, baseline comparisons, and child-level explanations for each milestone.

<p align="center">
  <a href="./paper/MMALS_Full_Story_PhD_Article.pdf">
    <img src="https://img.shields.io/badge/Open-Article-0B5FFF?style=for-the-badge&logo=adobeacrobatreader&logoColor=white" alt="Open PDF">
  </a>
</p>

## What this package contains

```text
paper/
  main.tex
  references.bib
  MMALS_Full_Story_PhD_Article.pdf
metrics/
  compact_mmals_milestone_metrics.csv
  selected extracted scorecards and gate CSVs
notebooks/
  latest RC2H notebook, when available
docs/
  selected evidence PDFs, program notes, and chronicle entries
raw_evidence/
  original evidence ZIPs used for metrics and traceability
```

## Scientific status

This is a research draft, not a peer-reviewed paper and not a production certification. The current strongest claim is:

> MMALS has a promising auditable inferred-context continual-learning mechanism with replay-beating evidence on FashionMNIST overlap-chain tests, but the automatic selector is not yet sufficiently reliable to replace safe anchored policies.

The latest conclusion is that a future **RC2I dual-anchor conservative selector** should use both:

- `context_gap_selected` / guarded RC1b context-gap
- `proto_global_head_ce_kl_guard_035` / true CE-KL guarded global head

and should prevent context-only global policies from overriding the safe anchor family in evidence/robust modes unless much stronger validation evidence exists.

## Program extension — 24 August 2026

A new **research-program hypothesis** has been recorded without changing the validated core claim or displacing RC2I qualification:

> Explore whether MMALS can become the smallest explainable inference system that remains dynamically sufficient for previously demonstrated situations and adapts to new evidence with the least justified structural growth.

Candidate lifecycle:

```text
REUSE -> ADAPT -> FORK -> CANDIDATE NEW REGIME -> VERIFY -> REMEMBER
                                  |
                                  +-> later MERGE / PRUNE / RETIRE when justified
```

The direction introduces a falsifiable **minimal sufficient dynamic inference / complexity-on-evidence** principle, a benchmark-specific non-regression competence contract, dynamic-compatibility distances, local domains of validity, and explicit tests against fixed MoE, always-update, always-expand, replay and standard continual-learning baselines.

It also records research bridges to sampling/reconstruction, observability, local-to-global constraints, differential geometry, stochastic dynamics, deterministic chaos, attractors/committors, and information-preserving compression. These are candidate mathematical tools and analogies, **not evidence that the domains are equivalent**.

- Program note: [`docs/program/MMALS_DYNAMIC_MINIMAL_INFERENCE_PROGRAM_2026-08-24.md`](docs/program/MMALS_DYNAMIC_MINIMAL_INFERENCE_PROGRAM_2026-08-24.md)
- Chronicle entry: [`docs/chronicle/2026-08-24_dynamic_minimal_inference.md`](docs/chronicle/2026-08-24_dynamic_minimal_inference.md)

The note also keeps the term **world model** bounded: this MMALS direction is world-model-like only if future experiments establish explicit predictive transition dynamics and, where relevant, action-conditioned consequences useful for prediction, planning, or control.

## Build instructions

From the repository root:

```bash
cd paper
pdflatex -interaction=nonstopmode main.tex
pdflatex -interaction=nonstopmode main.tex
```

The BibTeX file is included for future editing, but the current paper also contains an inline `thebibliography` block so it can compile without `bibtex`.

## Recommended publication workflow

1. Create a GitHub repository named for example:

   ```text
   mmals-research-chronicle
   ```

2. Add this package.
3. Keep `paper/MMALS_Full_Story_PhD_Article.pdf` as the main downloadable artifact.
4. Add the latest evidence ZIPs only if you want the repository to be heavier. Otherwise keep extracted CSV summaries in `metrics/`.
5. Tag releases by milestone, for example:

   ```text
   v1.1-rc2h-article-draft
   ```

## Next research step

The program extension above is **parallel** to, not a replacement for, the current evidence sequence. Before strong public claims, run:

```text
RC2I smoke -> RC2I evidence -> RC2I robust on FashionMNIST
then multi-dataset robust qualification:
MNIST, FashionMNIST, RotatedMNIST, PermutedMNIST
then v0.11-style comparative campaign with cost, parameters, runtime, memory, forgetting, and auditability.
```

Only after the current line is closed reproducibly should the dynamic-minimal-inference extension start with controlled regime-shift experiments, false regime-birth tests, and comparisons of `reuse/adapt/fork/new-regime` against simpler baselines.

## Suggested citation

```bibtex
@misc{harbonnier2026mmalschronicle,
  title={Mycelium-Inspired Mutualistic Adaptive Learning Systems (MMALS): A Research Chronicle from Bio-Inspired Functional Memory to Auditable Inferred-Context Continual Learning},
  author={Harbonnier, Guillaume},
  year={2026},
  note={Research draft and reproducibility package}
}
```
