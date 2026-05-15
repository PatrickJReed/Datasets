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
| ABCD | MRI, fMRI, DTI, behavioral, genotype | Longitudinal pediatric multimodal cohort (~12k) | controlled | ~50 TB | [link](datasets/abcd.md) |
| ABIDE I | MRI, fMRI | Multi-site autism imaging benchmark (~2.1k) | open | ~500 GB | [link](datasets/abide-i.md) |
| ABIDE II | MRI, fMRI, DTI | ABIDE extension with additional sites and modalities | open | ~1 TB | [link](datasets/abide-ii.md) |
| ADNI | MRI, PET, CSF, clinical | Longitudinal AD biomarkers | controlled | ~5 TB | [link](datasets/adni.md) |
| Allen Brain Cell Atlas | scRNA-seq, MERFISH, snATAC | Whole-brain cell-type reference (human + mouse) | open | ~3 TB | [link](datasets/allen-brain-cell-atlas.md) |
| CommonMind (CMC) | Bulk RNA-seq, ATAC, methylation, WGS | Schizophrenia, bipolar postmortem brain | controlled | ~3 TB | [link](datasets/commonmind.md) |
| CZ CELLxGENE | scRNA-seq, spatial | Harmonized single-cell aggregator + Census API | open | ~5 TB | [link](datasets/cellxgene.md) |
| ENCODE | ChIP, ATAC, DNase, RNA-seq, Hi-C | Regulatory genome reference | open | ~500 TB | [link](datasets/encode.md) |
| GTEx | Bulk RNA-seq, WGS | Multi-tissue transcriptome reference | controlled | ~5 TB | [link](datasets/gtex.md) |
| HBN | MRI, fMRI, DTI, EEG, behavioral, clinical | Transdiagnostic pediatric multimodal cohort (~5k) | registered | ~50 TB | [link](datasets/hbn.md) |
| Human Cell Atlas (HCA) | scRNA-seq, spatial | Cross-tissue single-cell reference | open | ~15 TB | [link](datasets/hca.md) |
| IBC | fMRI | Deep within-subject task-fMRI battery (~12 subjects, ~150 h each) | open | ~500 GB | [link](datasets/ibc.md) |
| JUMP Cell Painting | Cell Painting | Compound + CRISPR + ORF perturbation imaging | open | ~115 TB | [link](datasets/jump-cell-painting.md) |
| Mayo Clinic AMP-AD Cohort | Bulk RNA-seq, WGS, methylation | AD + PSP + pathological aging postmortem | controlled | ~1 TB | [link](datasets/mayo-rnaseq.md) |
| MSBB | Bulk RNA-seq, snRNA, proteomics, WGS | Multi-region AD postmortem cohort (~360) | controlled | ~3 TB | [link](datasets/msbb.md) |
| NACC | Clinical, neuropsych, neuropath, MRI | ADRC-network dementia coordinating center | controlled | ~5 TB | [link](datasets/nacc.md) |
| Narratives | fMRI | Story-listening fMRI corpus (~345 subjects, 27 stories) | open | ~50 GB | [link](datasets/narratives.md) |
| NCANDA | MRI, fMRI, DTI, behavioral, substance-use | Longitudinal adolescent neurodevelopment + alcohol | controlled | ~5 TB | [link](datasets/ncanda.md) |
| Neuropainting | Cell Painting | iPSC-neuron genetic perturbation imaging | open | ~2 TB | [link](datasets/neuropainting.md) |
| NSD | 7T fMRI | Deep visual-system fMRI on ~73k natural scenes (8 subjects) | open | ~2 TB | [link](datasets/nsd.md) |
| PGC | GWAS summary statistics | Psychiatric GWAS meta-analyses across disorders | open | ~50 GB | [link](datasets/pgc.md) |
| psychENCODE (PEC) | Multi-omic | Psychiatric disease brain consortium | controlled | ~50 TB | [link](datasets/psychencode.md) |
| ROSMAP | Bulk + scRNA-seq, proteomics, methylation, WGS, longitudinal | Flagship AMP-AD cohort (Rush; -omics gold standard) | controlled | ~15 TB | [link](datasets/rosmap.md) |
| RxRx1 | Cell Painting | siRNA-perturbation benchmark | open | ~50 GB | [link](datasets/rxrx1.md) |
| SEA-AD | snRNA-seq, MERFISH | AD-affected cortex single-cell atlas | open | ~500 GB | [link](datasets/sea-ad.md) |
| SPARK | Exome, WGS, genotype, phenotype | Large autism family cohort (~250k individuals) | controlled | ~50 TB | [link](datasets/spark.md) |
| SSC | Exome, genotype, phenotype | Simons Simplex autism quads (~2.8k families) | controlled | ~5 TB | [link](datasets/ssc.md) |
| Tahoe-100M | scRNA-seq | 100M-cell compound perturbation atlas | open | ~500 GB | [link](datasets/tahoe-100m.md) |
| UK Biobank | Genetics, MRI, proteomics, EHR | 500k population cohort | controlled | ~2 PB | [link](datasets/uk-biobank.md) |

## Umbrella / program context pages

These are not trainable datasets in their own right — they coordinate funding, DUAs, or sample sourcing across constituent cohorts. The constituents earn their own profiles and appear in the quick-find table above. See [CONTRIBUTING.md](CONTRIBUTING.md#granularity--what-counts-as-a-dataset) for the granularity rule.

- [AMP-AD](datasets/amp-ad.md) — AD coordination program above ROSMAP, MSBB, Mayo.
- [BICCN](datasets/biccn.md) — BRAIN Initiative cell census program; trainable output is [ABC Atlas](datasets/allen-brain-cell-atlas.md).
- [BICAN](datasets/bican.md) — BICCN successor; trainable constituents are still ramping.

## Adding a dataset

See [CONTRIBUTING.md](CONTRIBUTING.md).
