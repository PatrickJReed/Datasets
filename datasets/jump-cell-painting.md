---
name: JUMP Cell Painting Consortium
aliases: [JUMP-CP, JUMP]
host: Broad Institute / JUMP-CP Consortium
url: https://jump-cellpainting.broadinstitute.org/
access: open
modalities: [cell-painting, fluorescence-microscopy]
species: human
tissue: [u2os, a549]
conditions: [compound-perturbation, crispr-perturbation, orf-overexpression, control]
n_subjects: unknown
n_samples: ~3000000
age_range: cell-line
scale_gb: ~115000
license: CC0
year: 2023
tags: [perturbation, imaging, morphological-profiling, multi-modal-perturbation]
ai_relevance: [foundation-model, morphological-profiling, perturbation-response, multimodal, drug-discovery]
compute_hint: cluster
benchmark_splits: false
last_reviewed: 2026-05-14
---

## Summary

The JUMP Cell Painting Consortium (JUMP-CP) is a large industry-academic collaboration coordinated by the Broad Institute that produced the largest open Cell Painting dataset to date. Spanning approximately 3 million images acquired across chemical, CRISPR knockout, and ORF overexpression perturbations on shared human cell lines, JUMP-CP uniquely enables cross-perturbation-modality learning — connecting the morphological effects of small molecules, gene knockouts, and gene overexpressions within a common experimental framework. The consortium includes partners from major pharmaceutical companies and is released under a permissive CC0 license to maximize reuse.

## Features

- ~3 million 5-channel Cell Painting images (DNA, ER, RNA, AGP/cytoskeleton, mitochondria)
- Three perturbation modalities in a common experimental design: ~120,000 compounds, ~15,000 CRISPR guide RNAs, and ~12,000 ORF overexpressions
- Two primary cell lines: U2OS and A549, both widely used reference lines for morphological profiling
- Rich perturbation metadata including compound identifiers, gene targets, and batch information
- Precomputed CellProfiler morphological feature vectors available separately (~1 TB), far smaller than the raw image corpus (~115 TB)
- Self-supervised image embeddings (e.g., from DINO-style models) available or reproducible from published code

## Potential AI use cases

- Large-scale pretraining of vision foundation models on high-content biological imaging
- Learning a shared embedding space across perturbation modalities (chemical, genetic knockout, genetic overexpression), enabling cross-modal retrieval and prediction
- In silico compound screening by querying morphological profiles against known-target profiles
- Drug repurposing by identifying small molecules with profiles similar to beneficial genetic perturbations
- Benchmarking morphological profiling pipelines and batch-correction strategies at unprecedented scale

## Access notes

Raw images are publicly available via the AWS Registry of Open Data (no login required). The full raw dataset is ~115 TB and requires cluster-scale storage and compute. Researchers primarily working with features rather than raw pixels should start with the precomputed CellProfiler profiles (~1 TB), which are also available on S3. The CC0 license imposes no restrictions on commercial use. Full download instructions and dataset manifests are maintained at the consortium's landing page.

## Notable papers

- Chandrasekaran et al., 2023 — JUMP-CP overview paper describing the consortium design, perturbation libraries, and initial analyses (Nature Methods / bioRxiv preprint)

## Related

`[[rxrx1]]`, `[[neuropainting]]`
