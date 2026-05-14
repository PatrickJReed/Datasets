---
name: Human Cell Atlas
aliases: [HCA]
host: Chan Zuckerberg Initiative / HCA Data Portal
url: https://data.humancellatlas.org/
access: open
modalities: [scRNA-seq, snRNA-seq, spatial-transcriptomics, atac-seq]
species: human
tissue: [multi-tissue, whole-body]
conditions: [control, developmental, multiple-conditions]
n_subjects: ~10000
n_samples: ~50000000
age_range: fetal-to-adult
scale_gb: ~15000
license: per-project (mostly open)
year: 2017-ongoing
tags: [reference, single-cell, atlas, multi-tissue, developmental]
ai_relevance: [foundation-model, single-cell-foundation-model, cell-type-annotation, cross-tissue]
compute_hint: gpu-multi
benchmark_splits: false
last_reviewed: 2026-05-14
---

## Summary

The Human Cell Atlas (HCA) is an international consortium effort to map every cell type in the human body across tissues, developmental stages, and conditions. The HCA Data Portal aggregates curated, harmonized single-cell datasets contributed by labs worldwide, spanning roughly 50 tissues and ~50 million cells profiled primarily by scRNA-seq and snRNA-seq. Metadata is standardized against established ontologies (CL, UBERON, MONDO) enabling systematic cross-study queries. The Chan Zuckerberg Initiative's CELLxGENE platform provides additional curation, interactive exploration, and a programmatic Census API. The HCA is the primary training corpus for published single-cell foundation models including scGPT and Geneformer.

## Features

- ~50 million cells and nuclei across ~50 tissue types with standardized cell-type ontology annotations
- Harmonized metadata including tissue, donor age and sex, developmental stage, and disease status
- Spans fetal, neonatal, pediatric, and adult developmental windows enabling trajectory modeling
- CZ CELLxGENE Census provides an indexed, cloud-native API for streaming cell subsets by tissue or cell type
- Covers both atlas-grade reference datasets and disease-focused submissions under a unified metadata schema
- Continuously growing; new datasets submitted by contributing labs on a rolling basis

## Potential AI use cases

- Pretraining single-cell foundation models (scGPT, Geneformer, scFoundation, UCE) on broad human transcriptomic diversity
- Cell-type annotation models trained against standardized ontology labels and validated across held-out tissues
- Cross-tissue transfer learning to generalize from well-characterized to data-sparse tissue types
- Developmental trajectory modeling across fetal-to-adult time series for differentiation and lineage inference
- Multi-tissue gene program discovery using paired cross-tissue profiles from the same donors or projects

## Access notes

The majority of HCA datasets are open access and downloadable without registration from the HCA Data Portal and CellxGENE. Individual projects may carry project-specific licenses; users should verify per-project terms for commercial use. The CZ CELLxGENE Census provides a Python API (cellxgene-census package) for efficient, indexed access to a curated, versioned snapshot without downloading the full corpus, which at ~15 TB is impractical for most single-workstation workflows. Snapshots are versioned to support reproducibility.

## Notable papers

- Regev et al., 2017 — The Human Cell Atlas (eLife) — founding vision paper
- Tabula Sapiens Consortium, 2022 — Tabula Sapiens: A multiple-organ, single-cell transcriptomic atlas of humans (Science)
- Megill et al., 2023 — CELLxGENE Census: a large-scale collection of harmonized single-cell data (bioRxiv)

## Related

`[[allen-brain-cell-atlas]]`, `[[gtex]]`, `[[tahoe-100m]]`
