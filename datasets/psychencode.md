---
name: psychENCODE
aliases: [PEC]
host: Synapse / PsychENCODE Knowledge Portal
url: https://psychencode.synapse.org
access: controlled
modalities: [bulk-rna-seq, scRNA-seq, atac-seq, chip-seq, methylation, wgs, genotype]
species: human
tissue: [prefrontal-cortex, multiple-brain-regions]
conditions: [schizophrenia, bipolar, autism, control]
n_subjects: ~2700
n_samples: ~15000
age_range: fetal-to-adult
scale_gb: ~50000
license: PsychENCODE DUA
year: 2015-ongoing
tags: [neuro, psychiatric, multi-omic, developmental]
ai_relevance: [foundation-model, regulatory-genomics, disease-classification, multimodal]
compute_hint: gpu-multi
benchmark_splits: false
last_reviewed: 2026-05-14
---

## Summary

PsychENCODE is an NIH-funded consortium generating multi-omic data on the genomic regulation of the human brain in psychiatric disease. It covers developmental and adult brain tissue across schizophrenia, bipolar disorder, autism spectrum disorder, and neurotypical controls. The PEC2 phase expanded substantially into single-cell profiling, adding scRNA-seq and snATAC-seq alongside the original bulk assays. Together the consortium datasets constitute one of the most comprehensive multi-omic resources for studying psychiatric disease mechanisms at the molecular level.

## Features

- Bulk RNA-seq, scRNA-seq, ATAC-seq, ChIP-seq, bisulfite methylation, and WGS across donor cohorts
- Donor-level genotype enabling cis-regulatory and eQTL analyses
- Rich clinical and neuropathological metadata per donor
- Multiple brain regions, with an emphasis on prefrontal cortex and anterior cingulate
- Developmental time series spanning fetal through adult stages
- PEC2 single-cell atlases enabling cell-type-resolved regulatory analyses

## Potential AI use cases

- Multi-omic foundation model pretraining on paired assay data from the same donors
- Learning regulatory grammars in disease-associated chromatin and transcription in brain tissue
- Integrative case/control classification across schizophrenia, bipolar, and ASD cohorts
- Developmental trajectory modeling from fetal to adult brain using time-series transcriptomes
- Transfer learning to smaller psychiatric cohorts via representation learning on PEC bulk or single-cell data

## Access notes

Access requires a Synapse account plus acceptance of the PsychENCODE Data Use Agreement, which requires institutional sign-off from an authorized organizational representative. Approval typically takes 2–6 weeks depending on institution. Raw data volume is large (~50 TB); users should plan for cloud or HPC storage and should consult the portal for versioned data releases before downloading.

## Notable papers

- Akbarian et al., 2015 — PsychENCODE consortium launch and overview (Science)
- Gandal et al., 2018 — transcriptomic and genetic convergence across psychiatric disorders
- Wang et al., 2018 — comprehensive functional genomic characterization of the human brain
- PEC2 capstone papers (2023–2024) — single-cell atlases and integrative analyses across the full cohort

## Related

`[[commonmind]]`, `[[encode]]`, `[[gtex]]`, `[[amp-ad]]`
