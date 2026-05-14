---
name: Tahoe-100M
aliases: []
host: Vevo Therapeutics
url: https://www.vevotx.com/tahoe-100m
access: open
modalities: [scRNA-seq, compound-perturbation]
species: human
tissue: [multi-cancer-cell-lines]
conditions: [compound-perturbation, control]
n_subjects: unknown
n_samples: ~100000000
age_range: cell-line
scale_gb: ~500
license: CC BY 4.0
year: 2025
tags: [perturbation, single-cell, drug-discovery, foundation-model]
ai_relevance: [foundation-model, perturbation-response, drug-response, virtual-cell]
compute_hint: gpu-multi
benchmark_splits: false
last_reviewed: 2026-05-14
---

## Summary

Tahoe-100M is the largest open single-cell perturbation atlas released to date, comprising approximately 100 million transcriptomic profiles from ~50 human cancer cell lines treated with ~1,000 compounds. Released by Vevo Therapeutics in 2025, it was designed explicitly as a substrate for training virtual-cell foundation models that can predict how cells respond to chemical perturbations. Its scale — two orders of magnitude larger than prior open perturbation single-cell datasets — makes it qualitatively different from predecessors like LINCS L1000 or Perturb-seq collections, enabling learning of complex nonlinear drug-response landscapes across diverse genetic backgrounds.

## Features

- Single-cell RNA-seq read counts across ~100 million cells
- ~50 cancer cell lines representing diverse tissue origins, enabling cross-cell-line generalization studies
- ~1,000 compound perturbations with associated chemical metadata
- Matched unperturbed control cells per cell line and batch
- Batch metadata to support batch-effect analysis and correction
- Data formatted for compatibility with common single-cell frameworks (expected AnnData/h5ad)

## Potential AI use cases

- Pretraining scRNA-seq foundation models with explicit perturbation context, learning gene-program responses to chemical treatment
- Learning compound-response embeddings that generalize across cell lines and can be queried for in silico drug screening
- Virtual cell modeling: predicting unseen drug-cell-line response combinations from the learned landscape
- Transfer learning to primary patient tissue or disease cohorts by fine-tuning on Tahoe-100M representations
- Benchmarking perturbation prediction models (e.g., CPA, scGEN, GEARS variants) at a scale not previously possible with open data

## Access notes

Data are available for open download via Hugging Face and/or partner mirrors maintained by Vevo Therapeutics. The ~500 GB scale requires substantial local storage but is tractable on a multi-GPU workstation or cloud instance with appropriate disk provisioning. CC BY 4.0 licensing permits broad reuse including commercial applications with attribution.

## Notable papers

- Tahoe-100M preprint (2025) — primary release describing the experimental design, scale, and baseline modeling results; see the Vevo Therapeutics website or preprint servers for the current citation

## Related

`[[jump-cell-painting]]`, `[[hca]]`
