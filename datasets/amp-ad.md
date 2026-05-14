---
name: Accelerating Medicines Partnership — Alzheimer's Disease
aliases: [AMP-AD]
host: Synapse / AD Knowledge Portal
url: https://adknowledgeportal.synapse.org/
access: controlled
modalities: [bulk-rna-seq, scRNA-seq, proteomics, methylation, atac-seq, wgs, gwas, clinical]
species: human
tissue: [multiple-brain-regions, blood, csf]
conditions: [alzheimers, mild-cognitive-impairment, control]
n_subjects: ~5000
n_samples: ~50000
age_range: 60-100
scale_gb: ~30000
license: AD Knowledge Portal DUA (per study)
year: 2014-ongoing
tags: [aging, alzheimers, multi-omic, longitudinal, umbrella]
ai_relevance: [disease-classification, multi-omic, aging-trajectory, multimodal]
compute_hint: gpu-multi
benchmark_splits: false
last_reviewed: 2026-05-14
---

## Summary

AMP-AD is an NIH/industry public–private partnership that aggregates multi-omic data from multiple postmortem Alzheimer's disease cohorts under a single access portal, the AD Knowledge Portal. The program's three classical cohorts — ROSMAP (Rush), MSBB (Mount Sinai), and Mayo Clinic — together provide bulk RNA-seq, single-cell profiling, proteomics, methylation, ATAC-seq, WGS, GWAS, and longitudinal clinical data from roughly 5,000 donors. Newer additions to the portal continue to expand tissue coverage, modality depth, and racial/ethnic diversity. At ~30 TB of raw data it is the largest publicly accessible multi-omic resource for studying the aging human brain in Alzheimer's disease.

## Features

- Bulk RNA-seq from multiple brain regions per donor across ROSMAP, MSBB, and Mayo cohorts
- snRNA-seq and scRNA-seq atlases from cortex and other regions added in later phases
- Proteomics (TMT mass spectrometry) from frontal cortex in ROSMAP and MSBB
- WGBS/EPIC methylation arrays and ATAC-seq for chromatin accessibility in subsets
- WGS and GWAS arrays enabling variant-level analyses and GWAS fine-mapping
- ROSMAP adds serial cognitive assessments and full neuropathological staging (NIA-Reagan, CERAD, Braak); MSBB adds breadth across four cortical regions; Mayo adds non-demented aging controls and cerebellum

## Potential AI use cases

- Multi-omic disease classification distinguishing AD from MCI and control across independent cohorts
- Aging trajectory and biological-clock modeling from transcriptomic and methylation profiles
- Foundation-model pretraining on large-scale postmortem brain transcriptomes
- Cross-cohort generalization benchmarking for brain-disease models
- Biomarker discovery via integration of molecular, imaging, and clinical endpoints
- Graph-based or multimodal models fusing RNA-seq, proteomics, and neuropathology scores

## Access notes

Access requires a Synapse account plus acceptance of a study-specific Data Use Agreement for each cohort (ROSMAP, MSBB, Mayo, and others are separate DUAs). Multiple DUAs can be active simultaneously. Initial approval typically takes 2–4 weeks per DUA depending on institutional sign-off requirements. Raw data volume (~30 TB total) requires cloud or HPC storage; the portal provides versioned data releases and study-level metadata manifests.

## Notable papers

- Bennett et al., 2018 — overview of the Religious Orders Study and Memory and Aging Project (ROSMAP; Alzheimer's and Dementia)
- Wang et al., 2018 — multi-omic characterization of the Mount Sinai Brain Bank (MSBB) AD cohort (Nature Neuroscience)
- Allen et al., 2016 — characterization of the Mayo Clinic brain bank cohort (Acta Neuropathologica Communications)
- Jager et al., 2018 — AMP-AD phase 1 integrative network analyses linking genomics to neuropathology (Nature Neuroscience)

## Related

`[[adni]]`, `[[sea-ad]]`, `[[psychencode]]`, `[[uk-biobank]]`
