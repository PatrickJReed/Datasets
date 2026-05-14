---
name: Genotype-Tissue Expression Project
aliases: [GTEx]
host: NHGRI / GTEx Portal
url: https://gtexportal.org/
access: registered
modalities: [bulk-rna-seq, wgs, genotype]
species: human
tissue: [multi-tissue, 13-brain-regions, blood, muscle, skin, other]
conditions: [control]
n_subjects: ~980
n_samples: ~17000
age_range: 20-70
scale_gb: ~5000
license: GTEx DUA (open summary, controlled raw)
year: 2017
tags: [reference, multi-tissue, eQTL, regulatory-genomics]
ai_relevance: [foundation-model, regulatory-genomics, multitissue, eQTL]
compute_hint: gpu-single
benchmark_splits: false
last_reviewed: 2026-05-14
---

## Summary

The Genotype-Tissue Expression (GTEx) project is the canonical reference resource for human gene expression across 54 tissues from roughly 980 deceased donors, each profiled by bulk RNA-seq with matched whole-genome sequencing. Its breadth across tissues — including 13 brain regions — makes it foundational for studying tissue-specific gene regulation, generating eQTL and sQTL catalogs that are widely used for variant interpretation and fine-mapping. GTEx v8 is the current canonical release and is the most widely cited version in the literature.

## Features

- Bulk RNA-seq from up to 54 tissue types per donor, including 13 distinct brain regions
- WGS per donor enabling eQTL, sQTL, and colocalization analyses
- Rich tissue and donor metadata including age, sex, cause of death, and ischemic time
- cis- and trans-eQTL catalogs at multiple significance thresholds; splicing QTL (sQTL) maps
- v8 release covers 17,382 samples across 838 donors; v10 expands further
- Precomputed normalized expression matrices and covariate files ready for downstream analysis

## Potential AI use cases

- Multi-tissue foundation model pretraining using paired cross-tissue transcriptomes from the same donors
- Tissue-specificity prediction — learning which genes are housekeeping versus tissue-restricted
- Reference baseline for disease-cohort transcriptomes, enabling transfer or normalization against healthy tissue
- eQTL prediction from DNA sequence context, using GTEx variant-gene association maps as training labels
- Regulatory genomics models leveraging the scale and tissue diversity for cross-tissue generalization

## Access notes

Summary statistics, normalized expression matrices, and eQTL tables are freely available on the GTEx portal without registration. Subject-level raw RNA-seq reads and WGS are controlled-access and require a dbGaP data use agreement. dbGaP approval typically takes 4–8 weeks and requires institutional sign-off. For most ML use cases, the open summary-level data are sufficient; raw reads are only needed for reprocessing or de-novo alignment.

## Notable papers

- GTEx Consortium, 2020 — The GTEx Consortium atlas of genetic regulatory effects across human tissues (Science)
- GTEx Consortium, 2017 — Genetic effects on gene expression across human tissues (Nature) — v7 release

## Related

`[[psychencode]]`, `[[commonmind]]`, `[[encode]]`
