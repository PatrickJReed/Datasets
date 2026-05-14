---
name: Encyclopedia of DNA Elements
aliases: [ENCODE]
host: ENCODE Data Coordination Center / Stanford
url: https://www.encodeproject.org/
access: open
modalities: [chip-seq, atac-seq, dnase-seq, rna-seq, methylation, hi-c]
species: multi
tissue: [multi-tissue, multi-cell-line]
conditions: [control]
n_subjects: unknown
n_samples: ~25000
age_range: mixed
scale_gb: ~500000
license: CC0
year: 2003-ongoing
tags: [reference, regulatory-genomics, multi-modal, epigenome]
ai_relevance: [foundation-model, regulatory-genomics, sequence-models, multimodal]
compute_hint: cluster
benchmark_splits: false
last_reviewed: 2026-05-14
---

## Summary

The Encyclopedia of DNA Elements (ENCODE) is the flagship NIH consortium for systematically mapping functional elements across the human and mouse genomes. Launched in 2003, it has grown to encompass roughly 25,000 experiments spanning ChIP-seq, ATAC-seq, DNase-seq, RNA-seq, bisulfite methylation, and Hi-C across hundreds of cell lines and primary tissues. Uniform processing pipelines managed by the ENCODE Data Coordination Center ensure cross-experiment comparability. ENCODE data underpin essentially every modern regulatory-genomics model, from early convolutional architectures to recent large-scale sequence foundation models.

## Features

- ~25,000 experiments across 100+ cell lines and primary tissue types for human and mouse
- Six core assay modalities: ChIP-seq (TF and histone marks), ATAC-seq, DNase-seq, bulk RNA-seq, whole-genome bisulfite methylation, and Hi-C
- Uniform processing pipelines with versioned pipeline code; QC metrics exposed per experiment
- Rich biosample ontology (UBERON, CL) enabling systematic tissue and cell-type grouping
- ENCODE 4 expanded to single-cell ATAC-seq, long-read RNA-seq, and ORCA chromatin imaging
- Bulk metadata and file manifests accessible via a REST API; ENCODE search portal supports faceted filtering

## Potential AI use cases

- Pretraining sequence-to-function foundation models (Enformer, Borzoi, Sei, scBasset lineage) using thousands of regulatory tracks as supervision
- Cell-type-specific transcription factor binding prediction from DNA sequence
- Chromatin accessibility prediction and cis-regulatory element annotation
- Learning multimodal regulatory grammars by jointly modeling histone, TF, and accessibility tracks
- Serving as the reference annotation layer for variant-effect scoring and non-coding variant interpretation

## Access notes

All processed files and metadata are publicly downloadable from encodeproject.org under CC0 with no registration required. Raw FASTQ files are hosted on AWS S3 and GCP and can be accessed through the ENCODE portal file download links or the metadata API. Bulk manifest downloads listing all files for a given assay type are straightforward to generate via the search API. Dataset size is substantial (~500 TB for all processed files); most modeling workflows work from the uniformly processed bigWig or bed signal files rather than raw reads.

## Notable papers

- ENCODE Consortium, 2012 — An integrated encyclopedia of DNA elements in the human genome (Nature)
- ENCODE Consortium, 2020 — Expanded encyclopaedias of DNA elements in the human and mouse genomes (Nature) — ENCODE 3 capstone
- ENCODE Consortium, 2023 — The ENCODE4 catalogue of candidate cis-regulatory elements (Nature)

## Related

`[[psychencode]]`, `[[gtex]]`
