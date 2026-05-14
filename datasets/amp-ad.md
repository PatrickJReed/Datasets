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
tags: [aging, alzheimers, multi-omic, longitudinal, umbrella, program]
ai_relevance: [disease-classification, multi-omic, aging-trajectory, multimodal]
compute_hint: gpu-multi
benchmark_splits: false
last_reviewed: 2026-05-14
---

## Summary

**Umbrella / program — not a single dataset.** AMP-AD is an NIH / industry public-private partnership coordinating multi-omic data generation across Alzheimer's disease cohorts under a unified access portal (the AD Knowledge Portal on Synapse). For trainable datasets, see the constituent profiles: `[[rosmap]]` (Rush, the -omics flagship), `[[msbb]]` (Mount Sinai, multi-region), and `[[mayo-rnaseq]]` (Mayo, tauopathy contrast). Newer AMP-AD additions continue to expand tissue coverage, modality depth, and ancestry diversity.

This page documents the program's coordination identity — the harmonized DUA architecture, cross-cohort integrative work, and shared metadata standards. It is not a dataset you would train on directly.

## Features

- Unified portal (AD Knowledge Portal on Synapse) for cross-cohort discovery
- Per-study DUAs that share a common framework but require separate approval
- Shared sample metadata standards across cohorts
- Cross-cohort integrative analyses (network reconstructions, polygenic links, pathway burden)
- Active expansion through AMP-AD 2.0 funding cycle with additional sites and modalities

## Potential AI use cases

For training tasks, use the constituent datasets directly:
- ROSMAP for richest -omics depth and longitudinal cognition
- MSBB for multi-region per-donor design
- Mayo RNAseq for tauopathy contrast and cerebellar reference

Use AMP-AD as a unit when:
- Cross-cohort generalization is itself the research question (train on ROSMAP, evaluate on MSBB + Mayo, etc.)
- Building integrative models that explicitly leverage the harmonized metadata across cohorts
- Sample-efficient meta-analyses pooling effect sizes

## Access notes

Synapse account required, plus a separate DUA for each cohort. Multiple DUAs can be active simultaneously. Initial approval is typically 2-4 weeks per DUA, though ROSMAP also requires a separate RADC application that can extend to months. Raw data volume (~30 TB total across cohorts) typically requires cloud or HPC storage.

## Notable papers

- De Jager et al., 2018 — Multi-omic atlas of frontal cortex for aging and AD (Scientific Data; ROSMAP)
- Wang et al., 2018 — Mount Sinai cohort multi-omic release (Scientific Data; MSBB)
- Allen et al., 2016 — Mayo Clinic cohort RNAseq release (Scientific Data; Mayo)
- Integrative AMP-AD network and polygenic-burden papers across 2018-2024

## Related

Constituents: `[[rosmap]]`, `[[msbb]]`, `[[mayo-rnaseq]]`. Adjacent: `[[adni]]`, `[[sea-ad]]`, `[[nacc]]`, `[[psychencode]]`, `[[uk-biobank]]`.
