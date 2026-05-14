---
name: RxRx1
aliases: [RxRx1]
host: Recursion
url: https://www.rxrx.ai/rxrx1
access: open
modalities: [cell-painting, fluorescence-microscopy]
species: human
tissue: [hepg2, huvec, rpe, u2os]
conditions: [siRNA-perturbation, control]
n_subjects: unknown
n_samples: ~125000
age_range: cell-line
scale_gb: ~50
license: CC BY-NC 4.0
year: 2019
tags: [perturbation, imaging, morphological-profiling, benchmark]
ai_relevance: [foundation-model, morphological-profiling, batch-effect, classification]
compute_hint: gpu-single
benchmark_splits: true
last_reviewed: 2026-05-14
---

## Summary

RxRx1 is Recursion's first large public Cell Painting benchmark dataset, designed specifically around the batch-effects problem in biological imaging. Identical siRNA perturbation experiments were replicated across many imaging batches, providing ground-truth labels that allow rigorous measurement of how well a model can retrieve and classify perturbations despite technical variation. With ~125,000 images spanning four cell types and 1,138 siRNA treatments, it became a standard benchmark for morphological profiling and domain adaptation in the machine learning and computational biology communities.

## Features

- 6-channel fluorescence microscopy following the standard Cell Painting protocol
- Four human cell types: HepG2 (hepatocellular carcinoma), HUVEC (endothelial), RPE (retinal pigment epithelium), U2OS (osteosarcoma)
- 1,138 siRNA targets across 51 experimental batches, with deliberate batch-to-batch replicate structure
- Canonical train/validation/test splits, including a Kaggle competition split
- Raw TIFF images and precomputed CellProfiler morphological feature vectors
- Known batch-effect confounding built in by design, making it a controlled testbed for correction methods

## Potential AI use cases

- Pretraining convolutional or vision-transformer backbones on fluorescence microscopy images
- Benchmarking domain-adaptation and batch-effect correction methods, given the known replicate structure
- Classification baselines for siRNA treatment identification
- Transfer learning to larger Recursion datasets (RxRx2, RxRx3, RxRx19) or to the JUMP Cell Painting Consortium data
- Evaluation of self-supervised representation learning for biological perturbations

## Access notes

Raw TIFFs and CellProfiler features are available for open download via the rxrx.ai portal. Images are hosted on Amazon S3; the download scripts provided by Recursion pull directly from that bucket. The ~50 GB scale is manageable on a single GPU workstation. CC BY-NC 4.0 licensing applies — commercial use requires separate arrangements with Recursion.

## Notable papers

- Sypetkowski et al., 2023 — primary RxRx1 benchmark paper describing the dataset design, batch-effect structure, and baseline results
- Taylor et al. / Recursion RxRx2 and RxRx3 papers — extend the paradigm to CRISPR and compound perturbations on the same imaging platform

## Related

`[[neuropainting]]`, `[[jump-cell-painting]]`

**Sister datasets in the RxRx series (not yet profiled in this repo):**
- **RxRx2** — CRISPR knockout perturbations across human cell lines, complementing RxRx1's siRNA approach with permanent gene edits
- **RxRx3** — compound (small-molecule) perturbations, enabling morphological profiling of drug treatments at scale
- **RxRx19** — a COVID-19-focused screen measuring morphological responses to SARS-CoV-2 infection and antiviral compounds across multiple cell lines
