---
name: Neuropainting
aliases: []
host: Recursion / Allen Institute collaboration
url: https://www.rxrx.ai/neuropainting
access: open
modalities: [cell-painting, fluorescence-microscopy]
species: human
tissue: [ipsc-derived-neurons]
conditions: [genetic-perturbation, control]
n_subjects: unknown
n_samples: ~1000000
age_range: cell-line
scale_gb: ~2000
license: CC BY 4.0
year: 2024-ongoing
tags: [neuro, perturbation, imaging, morphological-profiling, ipsc]
ai_relevance: [foundation-model, morphological-profiling, perturbation-response, contrastive-learning]
compute_hint: gpu-multi
benchmark_splits: false
last_reviewed: 2026-05-14
---

## Summary

Neuropainting is a large-scale Cell Painting-style morphological imaging dataset focused on iPSC-derived neurons subjected to genetic perturbation, released by Recursion in collaboration with the Allen Institute. It extends the Cell Painting paradigm — historically applied to cancer cell lines such as U2OS and A549 — into a disease-relevant neural-cell context, making it one of the first datasets at this scale to characterize neuronal morphology under systematic genetic perturbation. The dataset is released openly via Recursion's rxrx.ai portal and is intended as a substrate for foundation models that must understand neuronal biology.

## Features

- Multi-channel fluorescence microscopy following a Cell Painting-style staining protocol targeting nuclei, mitochondria, ER, cytoskeleton, and other organelles
- Large library of gene knockouts and knockdowns covering hundreds to thousands of perturbation targets
- iPSC-derived neurons as the cell model, distinguishing this dataset from most prior large-scale morphological datasets
- Paired unperturbed controls in each imaging batch, enabling perturbation-vs-control comparisons
- Suitable for computing CellProfiler morphological feature vectors or self-supervised (e.g., DINO-style) image embeddings
- Batch metadata enabling systematic batch-effect analysis across imaging runs

## Potential AI use cases

- Pretraining vision foundation models on neural-cell morphology, capturing features not present in cancer-line datasets
- Learning perturbation-response embeddings that map genetic knockouts to phenotypic profiles in a latent space
- Transfer learning to disease-relevant phenotypes (e.g., neurodegeneration models) by fine-tuning on Neuropainting representations
- Contrastive learning across perturbation classes to identify functionally similar genes via shared morphological signatures
- Benchmarking domain adaptation methods when combining with non-neuronal Cell Painting datasets

## Access notes

Data are openly downloadable through Recursion's rxrx.ai portal at the URL above. No registration wall beyond standard portal access is expected, though users should confirm current terms on the portal as the dataset is described as ongoing. Raw images are large (~2 TB); downstream CellProfiler features or precomputed embeddings, if released, will be substantially smaller.

## Notable papers

- Recursion Neuropainting white paper / preprint (2024) — primary release description; see rxrx.ai for the current citation

## Related

`[[rxrx1]]`, `[[jump-cell-painting]]`
