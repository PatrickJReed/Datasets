---
name: Allen Brain Cell Atlas
aliases: [ABC Atlas]
host: Allen Institute
url: https://portal.brain-map.org/atlases-and-data/bkp/abc-atlas
access: open
modalities: [scRNA-seq, snRNA-seq, merfish, atac-seq]
species: [human, mouse]
tissue: [whole-brain]
conditions: [control]
n_subjects: unknown
n_samples: ~32000000
age_range: adult
scale_gb: ~3000
license: CC BY 4.0
year: 2023-ongoing
tags: [neuro, single-cell, atlas, reference, spatial]
ai_relevance: [single-cell-foundation-model, cell-type-annotation, spatial-transcriptomics]
compute_hint: gpu-multi
benchmark_splits: false
last_reviewed: 2026-05-14
---

## Summary

The Allen Brain Cell Atlas (ABC Atlas) is the Allen Institute's comprehensive cellular census of the mouse and human brain, integrating scRNA-seq, snRNA-seq, MERFISH spatial transcriptomics, and snATAC-seq from whole-brain dissections. The mouse component profiles roughly 32 million cells and nuclei across all major brain regions with matched spatial data from MERFISH, establishing a hierarchical cell-type taxonomy of over 5,000 cell clusters organized into class, subclass, supertype, and cluster levels. A companion human brain atlas (Siletti et al.) provides cross-species correspondence. The ABC Atlas is now the primary reference for brain cell-type annotation and spatial mapping, superseding earlier region-by-region Allen Institute resources.

## Features

- ~32 million cells and nuclei spanning scRNA-seq, snRNA-seq, and snATAC-seq modalities across the whole mouse brain
- MERFISH spatial transcriptomics panels providing subcellular-resolution spatial coordinates for cell-type mapping
- Hierarchical cell-type taxonomy with over 5,000 clusters organized by class, subclass, supertype, and cluster
- Matched human brain single-nucleus RNA-seq enabling cross-species comparative analysis
- Data distributed as AnnData/H5AD objects via the Allen Brain Map portal and CellxGene mirrors
- Continuously updated resource with new brain regions, modalities, and species added over time

## Potential AI use cases

- Pretraining scRNA-seq and snRNA-seq foundation models with a brain-biased corpus covering all major cell types
- Cell-type annotation transfer to external neuroscience datasets using the hierarchical taxonomy as reference labels
- Spatial transcriptomics modeling with MERFISH coordinates as supervision signal for spatial context learning
- Cross-species brain mapping by aligning mouse and human cell-type embeddings across shared gene programs
- Multi-modal integration across RNA, ATAC, and spatial modalities as a benchmark for single-cell multi-omics models

## Access notes

All data are openly downloadable without registration or a data use agreement under CC BY 4.0. AnnData files are available directly from the Allen Brain Map portal. Many subsets are also mirrored on CellxGene, providing a query interface and the option to stream individual cell subsets without downloading the full corpus. At roughly 3 TB total the full dataset requires multi-GPU infrastructure for whole-atlas training runs; region- or modality-specific subsets are more tractable on a single workstation.

## Notable papers

- Yao et al., 2023 — A transcriptomic and epigenomic cell atlas of the mouse primary motor cortex (Nature) — whole-mouse-brain taxonomy
- Siletti et al., 2023 — Transcriptomic diversity of cell types across the adult human brain (Science) — human companion atlas

## Related

`[[sea-ad]]`, `[[hca]]`, `[[psychencode]]`
