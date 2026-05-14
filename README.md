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

| Dataset | Modality | Focus | Access | Scale | Detail |
|---|---|---|---|---|---|
| ADNI | MRI, PET, CSF, clinical | Longitudinal AD biomarkers | controlled | ~5 TB | [link](datasets/adni.md) |
| Allen Brain Cell Atlas | scRNA-seq, MERFISH, snATAC | Whole-brain cell-type reference (human + mouse) | open | ~3 TB | [link](datasets/allen-brain-cell-atlas.md) |
| AMP-AD (ROSMAP, MSBB, Mayo) | Multi-omic + clinical | Alzheimer's disease cohorts | controlled | ~30 TB | [link](datasets/amp-ad.md) |
| BICCN | scRNA-seq, snATAC, MERFISH, Patch-seq, tracing | Multi-species brain cell census umbrella | open | ~10 TB | [link](datasets/biccn.md) |
| CommonMind (CMC) | Bulk RNA-seq, ATAC, methylation, WGS | Schizophrenia, bipolar postmortem brain | controlled | ~3 TB | [link](datasets/commonmind.md) |
| ENCODE | ChIP, ATAC, DNase, RNA-seq, Hi-C | Regulatory genome reference | open | ~500 TB | [link](datasets/encode.md) |
| GTEx | Bulk RNA-seq, WGS | Multi-tissue transcriptome reference | controlled | ~5 TB | [link](datasets/gtex.md) |
| Human Cell Atlas (HCA) | scRNA-seq, spatial | Cross-tissue single-cell reference | open | ~15 TB | [link](datasets/hca.md) |
| JUMP Cell Painting | Cell Painting | Compound + CRISPR + ORF perturbation imaging | open | ~115 TB | [link](datasets/jump-cell-painting.md) |
| Neuropainting | Cell Painting | iPSC-neuron genetic perturbation imaging | open | ~2 TB | [link](datasets/neuropainting.md) |
| OpenNeuro | MRI, fMRI, EEG, MEG, iEEG | Aggregator of BIDS neuroimaging studies | open | ~200 TB | [link](datasets/openneuro.md) |
| psychENCODE (PEC) | Multi-omic | Psychiatric disease brain consortium | controlled | ~50 TB | [link](datasets/psychencode.md) |
| RxRx1 | Cell Painting | siRNA-perturbation benchmark | open | ~50 GB | [link](datasets/rxrx1.md) |
| SEA-AD | snRNA-seq, MERFISH | AD-affected cortex single-cell atlas | open | ~500 GB | [link](datasets/sea-ad.md) |
| Tahoe-100M | scRNA-seq | 100M-cell compound perturbation atlas | open | ~500 GB | [link](datasets/tahoe-100m.md) |
| UK Biobank | Genetics, MRI, proteomics, EHR | 500k population cohort | controlled | ~2 PB | [link](datasets/uk-biobank.md) |

## Adding a dataset

See [CONTRIBUTING.md](CONTRIBUTING.md).
