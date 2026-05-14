---
name: Brain Initiative Cell Census Network
aliases: [BICCN]
host: NIH BRAIN Initiative / NeMO Archive
url: https://nemoarchive.org/
access: open
modalities: [scRNA-seq, snRNA-seq, snATAC-seq, merfish, patch-seq, anatomical-tracing, electrophysiology]
species: multi
tissue: [whole-brain, motor-cortex, multiple-brain-regions]
conditions: [control]
n_subjects: unknown
n_samples: ~30000000
age_range: adult
scale_gb: ~10000
license: per-study (mostly open, some dbGaP-controlled human samples)
year: 2017-2022
tags: [neuro, single-cell, multimodal, atlas, umbrella, consortium]
ai_relevance: [single-cell-foundation-model, cell-type-annotation, spatial-transcriptomics, multimodal, cross-species]
compute_hint: gpu-multi
benchmark_splits: false
last_reviewed: 2026-05-14
---

## Summary

NIH BRAIN Initiative consortium (2017-2022) producing comprehensive cell census atlases of mouse, marmoset, and human brain at single-cell resolution. Work spans transcriptomics, epigenomics, spatial transcriptomics, morphology, and connectivity, with cross-species comparison as an organizing principle. The successor program BICAN (BRAIN Initiative Cell Atlas Network, 2022-onward) is extending the effort to the whole human brain. NeMO Archive serves as the raw-data repository; ABC Atlas surfaces the integrated mouse and human atlases.

## Features

- scRNA-seq and snRNA-seq across mouse, marmoset, and human brain
- snATAC-seq for chromatin accessibility, often paired with the transcriptomic atlases
- MERFISH spatial transcriptomics for in-situ cell-type mapping
- Patch-seq: multimodal recordings linking electrophysiology, morphology, and transcriptome on the same neurons
- Anatomical tracing and connectivity datasets
- Cross-species primary motor cortex (M1) flagship — direct comparison of homologous cell types
- Hierarchical cell-type taxonomies harmonized across modalities

## Potential AI use cases

- Pretraining cross-species single-cell foundation models
- Multimodal alignment models (transcriptome ↔ morphology ↔ electrophysiology)
- Spatial-transcriptomic modeling and cell-type deconvolution
- Cell-type-aware representations transferable to disease cohorts (AD, psychiatric)
- Cross-species transfer learning (mouse pretraining → human fine-tuning)

## Access notes

Most data is open via NeMO Archive (`nemoarchive.org`); some human samples are dbGaP-controlled. Integrated atlas products are accessible through the Allen Brain Map / ABC Atlas portal. Many BICCN datasets are also mirrored on CZ CELLxGENE for query-by-cell-type access. BICAN data is increasingly being released through the same channels.

## Notable papers

- BICCN Consortium, 2021 (Nature special issue on mouse primary motor cortex multimodal atlas)
- Yao et al., 2023 (mouse whole-brain transcriptomic taxonomy, Nature)
- Siletti et al., 2023 (human brain atlas, Science)
- Bakken et al., 2021 (cross-species M1 comparison, Nature)

## Related

`[[allen-brain-cell-atlas]]`, `[[hca]]`, `[[sea-ad]]`, `[[psychencode]]`. ABC Atlas is the user-facing portal for a large fraction of BICCN's mouse and human transcriptomic data; NeMO Archive is the raw-data archive that also holds BICCN's MERFISH, snATAC, and Patch-seq layers not currently surfaced in ABC.
