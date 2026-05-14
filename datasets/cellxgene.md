---
name: CZ CELLxGENE
aliases: [CELLxGENE, CZ CELLxGENE Census]
host: Chan Zuckerberg Initiative
url: https://cellxgene.cziscience.com/
access: open
modalities: [scRNA-seq, snRNA-seq, spatial-transcriptomics]
species: multi
tissue: [multi-tissue, whole-body]
conditions: [control, developmental, multiple-conditions]
n_subjects: ~3000
n_samples: ~100000000
age_range: fetal-to-adult
scale_gb: ~5000
license: per-study (mostly open)
year: 2021-ongoing
tags: [reference, single-cell, atlas, aggregator, query-api]
ai_relevance: [foundation-model, single-cell-foundation-model, cell-type-annotation, cross-tissue]
compute_hint: gpu-multi
benchmark_splits: false
last_reviewed: 2026-05-14
---

## Summary

Chan Zuckerberg Initiative aggregator and query interface for harmonized single-cell data. Distinct from HCA: where HCA is the consortium and data submission framework, CELLxGENE is the curated portal plus the Census API that exposes ~100M cells across studies as a single queryable corpus. Cell types are harmonized to the Cell Ontology, and the Census release schedule provides versioned snapshots — making it the standard pretraining substrate for recent single-cell foundation models.

## Features

- Discover portal: browse, filter, and visualize individual studies
- Census API: query a harmonized corpus of ~100M cells programmatically (TileDB-SOMA-backed)
- Standardized cell-type annotation using the Cell Ontology (CL)
- Cross-tissue coverage spanning ~70 tissues from the aggregated submissions
- Versioned releases (LTS and weekly) for reproducibility
- Direct integration with scvi-tools and other ecosystem libraries

## Potential AI use cases

- Pretraining single-cell foundation models (scGPT, Geneformer, scFoundation, UCE all use CELLxGENE-derived corpora)
- Cell-type annotation models trained against the harmonized ontology
- Cross-tissue transfer learning with consistent annotation
- Benchmarking integration and batch-correction methods
- Quick cohort assembly for downstream supervised tasks

## Access notes

Open. Census API installable via pip (`cellxgene-census`). Versioned releases mean you can pin a specific snapshot for reproducibility. Individual studies retain their own licenses but are uniformly accessible via the portal.

## Notable papers

- Megill et al., 2023 (CELLxGENE Census, bioRxiv)
- CZ CELLxGENE Discover platform paper (2021)

## Related

`[[hca]]`, `[[allen-brain-cell-atlas]]`, `[[sea-ad]]`, `[[biccn]]`, `[[bican]]`. CELLxGENE harmonizes and surfaces data contributed via HCA and the BRAIN Initiative atlases, among many others — when training a single-cell foundation model the Census is usually a better starting point than chasing individual portal downloads.
