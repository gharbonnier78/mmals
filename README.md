# MMALS Research Chronicle

**Repository description:**
Research article and reproducibility package for MMALS: a mycelium-inspired continual-learning program moving from functional route memory to auditable inferred-context learning, with v0.x-to-v1.1-RC2H evidence, baseline comparisons, and child-level explanations for each milestone.

<p align="center">
  <a href="./paper/MMALS_Full_Story_PhD_Article_ready.pdf">
    <img src="https://img.shields.io/badge/Open-High%20Level%20View-0B5FFF?style=for-the-badge&logo=adobeacrobatreader&logoColor=white" alt="Open High Level View PDF">
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
  selected evidence PDFs, when available
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

Before strong public claims, run:

```text
RC2I smoke -> RC2I evidence -> RC2I robust on FashionMNIST
then multi-dataset robust qualification:
MNIST, FashionMNIST, RotatedMNIST, PermutedMNIST
then v0.11-style comparative campaign with cost, parameters, runtime, memory, forgetting, and auditability.
```

## Suggested citation

```bibtex
@misc{harbonnier2026mmalschronicle,
  title={Mycelium-Inspired Mutualistic Adaptive Learning Systems (MMALS): A Research Chronicle from Bio-Inspired Functional Memory to Auditable Inferred-Context Continual Learning},
  author={Harbonnier, Guillaume},
  year={2026},
  note={Research draft and reproducibility package}
}
```
