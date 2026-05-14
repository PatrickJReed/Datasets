---
name: Mayo Clinic AMP-AD Cohort
aliases: [Mayo RNAseq, Mayo, Mayo Clinic Brain Bank AMP-AD]
host: Mayo Clinic / AD Knowledge Portal (Synapse)
url: https://www.synapse.org/Synapse:syn5550404
access: controlled
modalities: [bulk-rna-seq, wgs, methylation, neuropath, clinical]
species: human
tissue: [cerebellum, temporal-cortex]
conditions: [alzheimers, progressive-supranuclear-palsy, pathological-aging, control]
n_subjects: ~280
n_samples: ~600
age_range: 60-100
scale_gb: ~1000
license: AD Knowledge Portal DUA
year: 2016-ongoing
tags: [aging, alzheimers, psp, multi-omic, postmortem, cross-disorder]
ai_relevance: [disease-classification, cross-disorder, neuropath, regional-comparison]
compute_hint: gpu-single
benchmark_splits: false
last_reviewed: 2026-05-14
---

## Summary

Mayo Clinic's AMP-AD cohort, centered on bulk RNA-seq of temporal cortex and cerebellum from ~280 donors spanning AD, progressive supranuclear palsy (PSP), pathological aging, and control. Distinctive contributions: tauopathy contrast via the PSP subgroup, cerebellar reference tissue, and a "pathological aging" intermediate group (significant amyloid without dementia) that ROSMAP and MSBB don't emphasize.

## Features

- Bulk RNA-seq on temporal cortex and cerebellum (most subjects have both)
- WGS and methylation arrays on subsets
- Standardized neuropathology including Braak staging and PSP-specific characterization
- Well-defined PSP subgroup useful for cross-tauopathy modeling
- Pathological aging group provides a preclinical-AD intermediate

## Potential AI use cases

- Cross-disorder transcriptomic modeling (AD vs PSP — both tauopathies, different distributions)
- Cerebellum as a regional contrast tissue (canonical "spared" region in AD)
- AD subtyping leveraging the pathological-aging intermediate group
- Replication cohort for ROSMAP and MSBB findings
- Tau-specific signature discovery

## Access notes

AD Knowledge Portal DUA via Synapse. Approval typically 2-4 weeks.

## Notable papers

- Allen et al., 2016 — Human whole genome genotype and transcriptome data for Alzheimer's and other neurodegenerative diseases (Scientific Data)

## Related

`[[amp-ad]]`, `[[rosmap]]`, `[[msbb]]`, `[[sea-ad]]`, `[[nacc]]`.
