# Datasets

A curated, evergreen index of public datasets relevant to training AI models, with a focus on **human, neurological, and aging biology**.

This is an **index, not a mirror**. It tracks where datasets live, how to access them, what they contain, and what they might be useful for. It does not host data.

## How this repo is organized

- **`datasets/`** — one markdown file per dataset. Source of truth. Each file has YAML frontmatter (filterable) and a fixed set of body sections (narrative).
- **`categories/`** — curated lenses over the datasets (neuro, aging, perturbation imaging, single-cell, foundation-model candidates). A dataset can appear in multiple categories.
- **`templates/dataset-template.md`** — the canonical schema for a dataset entry.
- **`CONTRIBUTING.md`** — how to add a dataset, plus the frontmatter field reference.

## Categories

- [Neuro](categories/neuro.md) — brain tissue and neuropsychiatric datasets.
- [Aging](categories/aging.md) — datasets with age-range coverage relevant to aging biology.
- [Perturbation imaging](categories/perturbation-imaging.md) — cell-painting and morphological profiling.
- [Single-cell](categories/single-cell.md) — scRNA-seq, snRNA-seq, multiome.
- [Foundation-model candidates](categories/foundation-model-candidates.md) — large/diverse enough to pretrain on.

## Status legend

| Field | Values |
|---|---|
| `access` | `open` — free download · `registered` — account needed · `controlled` — DUA or IRB required |
| `compute_hint` | `cpu` · `gpu-single` · `gpu-multi` · `cluster` |
| `benchmark_splits` | `true` if the dataset ships canonical train/val/test splits |

## Quick-find table

<!-- Populated in Task 10 of the scaffold plan. -->

## Adding a dataset

See [CONTRIBUTING.md](CONTRIBUTING.md).
