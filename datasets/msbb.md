---
name: Mount Sinai Brain Bank AD Cohort
aliases: [MSBB, Mount Sinai/JJ Peters VA Medical Center Brain Bank]
host: Mount Sinai NIH AD Research Center / AD Knowledge Portal (Synapse)
url: https://www.synapse.org/Synapse:syn3159438
access: controlled
modalities: [bulk-rna-seq, snRNA-seq, proteomics, methylation, wgs, genotype, neuropath]
species: human
tissue: [frontal-pole, superior-temporal-gyrus, parahippocampal-gyrus, inferior-frontal]
conditions: [alzheimers, control]
n_subjects: ~360
n_samples: ~1400
age_range: 60-100
scale_gb: ~3000
license: AD Knowledge Portal DUA
year: 2018-ongoing
tags: [aging, alzheimers, multi-omic, postmortem, multi-region]
ai_relevance: [disease-classification, multi-omic, regional-comparison, neuropath]
compute_hint: gpu-single
benchmark_splits: false
last_reviewed: 2026-05-14
---

## Summary

Mount Sinai / JJ Peters VA Medical Center Brain Bank AD cohort, contributed to AMP-AD. ~360 donors with four matched cortical regions per subject: Brodmann area 10 (frontal pole), BA22 (superior temporal gyrus), BA36 (parahippocampal gyrus), and BA44 (inferior frontal). The multi-region per-subject design is distinctive — most AD cohorts sample one region per donor.

## Features

- Bulk RNA-seq across four cortical regions per donor (~1,400 samples)
- snRNA-seq on a subset of donors
- Proteomics (TMT-MS), methylation arrays, WGS, genotype
- Standardized neuropathology with continuous CDR scoring
- Deep clinical and demographic metadata
- Designed as a replication and regional-comparison cohort for ROSMAP

## Potential AI use cases

- Regional comparison within AD pathology (four matched regions per donor)
- Multi-region transcriptome models with within-subject region effects
- AD classification benchmarks with matched-region controls
- Cross-cohort generalization studies pairing MSBB with ROSMAP and Mayo
- Multi-omic integration on a smaller, multi-region cohort

## Access notes

AD Knowledge Portal DUA via Synapse. Approval typically 2-4 weeks. Standard publication policies; no additional institutional layer beyond the Synapse DUA.

## Notable papers

- Wang et al., 2018 — The Mount Sinai cohort of large-scale genomic, transcriptomic and proteomic data in Alzheimer's disease (Scientific Data)

## Related

`[[amp-ad]]`, `[[rosmap]]`, `[[mayo-rnaseq]]`, `[[sea-ad]]`, `[[nacc]]`.
