---
name: Seattle Alzheimer's Disease Brain Cell Atlas
aliases: [SEA-AD]
host: Allen Institute / SEA-AD Portal
url: https://portal.brain-map.org/explore/seattle-alzheimers-disease
access: open
modalities: [scRNA-seq, snRNA-seq, mfish, histology, clinical]
species: human
tissue: [middle-temporal-gyrus, dlpfc]
conditions: [alzheimers, control]
n_subjects: ~84
n_samples: ~1500000
age_range: 65-100
scale_gb: ~500
license: CC BY 4.0
year: 2023-ongoing
tags: [aging, alzheimers, single-cell, atlas]
ai_relevance: [single-cell-foundation-model, disease-classification, cell-type-annotation]
compute_hint: gpu-single
benchmark_splits: false
last_reviewed: 2026-05-14
---

## Summary

The Seattle Alzheimer's Disease Brain Cell Atlas (SEA-AD) is an Allen Institute resource providing deep single-nucleus RNA-seq and spatial transcriptomics of human cortex across a continuous spectrum of AD neuropathological severity. Unlike cohorts defined by clinical diagnosis alone, SEA-AD stratifies donors by quantitative neuropathological scores, enabling cell-type-resolved analysis of how individual populations change across the full trajectory from cognitively normal to end-stage disease. The atlas spans roughly 1.5 million nuclei from ~84 donors profiled in middle temporal gyrus and DLPFC, with matched MERFISH spatial data and histology, and is freely downloadable under a CC BY 4.0 license.

## Features

- snRNA-seq profiling of ~1.5 million nuclei with harmonized cell-type taxonomy across donors
- MERFISH spatial transcriptomics in a subset of donors enabling spatial mapping of disease-associated cell states
- Donor-level quantitative neuropathological staging (Braak, CERAD, NIA-Reagan, amyloid and tau burden)
- Matched histological images from the same tissue blocks as the molecular profiling
- Coverage of middle temporal gyrus (primary region) and DLPFC across the same donors
- Fully open access; data distributed as AnnData/H5AD objects via the Allen Brain Map portal

## Potential AI use cases

- Fine-tuning single-cell foundation models (scGPT, Geneformer, scFoundation) to AD neuropathology
- Cell-type-specific disease-state classification along a continuous neuropathological severity axis
- Integration of MERFISH spatial context with snRNA-seq for spatially resolved disease modeling
- Disease-stage prediction from cell-type composition and transcriptomic profiles
- Cell-type annotation transfer to external AD or aging cohorts using SEA-AD as reference atlas

## Access notes

All data are openly downloadable without registration or a DUA. AnnData files are available directly from the Allen Brain Map portal and are also mirrored on Synapse. At ~500 GB the dataset is manageable on a workstation with a high-capacity SSD; individual region or donor subsets can be downloaded selectively. The portal provides interactive data exploration tools before download.

## Notable papers

- Gabitto et al., 2024 — integrated multimodal atlas of the human middle temporal gyrus across the AD continuum (Nature Neuroscience)

## Related

`[[allen-brain-cell-atlas]]`, `[[amp-ad]]`, `[[hca]]`
