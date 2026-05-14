---
name: Religious Orders Study and Memory and Aging Project
aliases: [ROSMAP, ROS, MAP]
host: Rush Alzheimer's Disease Center / AD Knowledge Portal (Synapse)
url: https://www.radc.rush.edu/
access: controlled
modalities: [bulk-rna-seq, scRNA-seq, snRNA-seq, proteomics, methylation, atac-seq, wgs, gwas, clinical, neuropath]
species: human
tissue: [dlpfc, pcc, multiple-brain-regions, blood]
conditions: [alzheimers, mild-cognitive-impairment, control]
n_subjects: ~3500
n_samples: ~15000
age_range: 65-100
scale_gb: ~15000
license: AD Knowledge Portal DUA + RADC application
year: 1994-ongoing
tags: [aging, alzheimers, multi-omic, longitudinal, postmortem, gold-standard]
ai_relevance: [disease-classification, multi-omic, aging-trajectory, biomarker, eQTL]
compute_hint: gpu-multi
benchmark_splits: false
last_reviewed: 2026-05-14
---

## Summary

Combined cohort of the Religious Orders Study (ROS, est. 1994) and the Memory and Aging Project (MAP, est. 1997), both run by David Bennett's group at the Rush Alzheimer's Disease Center. Defined by annual cognitive and clinical visits during life followed by brain donation at death. Subjects enroll cognitively normal (mean age ~80) and follow-up extends decades. ROSMAP is the single most-cited postmortem AD cohort in -omics literature and is the workhorse cohort for AMP-AD.

## Features

- Bulk RNA-seq on ~1,200 DLPFC samples (most-studied), plus PCC and other regions for many subjects
- snRNA-seq subsets including the Mathys et al., 2019 atlas and subsequent expansions
- Proteomics (TMT-MS), WGBS/EPIC methylation, ATAC-seq, WGS, genotype
- Annual longitudinal cognition spanning decades for many subjects
- Standardized neuropathology: Braak, CERAD, NIA-Reagan, amyloid load, tau density, vascular pathology
- Rich clinical phenotyping (depression, sleep, motor, diet) suitable for confound control

## Potential AI use cases

- AD/MCI/control classification with rich multi-omic feature sets
- Aging trajectory and biological-clock modeling from longitudinal cognition + molecular profiles
- Cell-type-specific disease modeling via the snRNA-seq subsets
- eQTL/sQTL/pQTL prediction
- Multi-omic integration models (RNA + protein + methylation + neuropath)
- Cross-cohort generalization studies against MSBB and Mayo

## Access notes

Two-layer access: the RADC application governs the underlying ROS and MAP studies, while the AD Knowledge Portal DUA via Synapse governs the -omic releases. RADC review can take several months; the AD Knowledge Portal DUA alone is typically 2-4 weeks. Some -omic releases have specific publication policies — check the study wiki before submitting.

## Notable papers

- Bennett et al., 2018 — Religious Orders Study and Rush Memory and Aging Project (Journal of Alzheimer's Disease, cohort description issue)
- De Jager et al., 2018 — A multi-omic atlas of the human frontal cortex for aging and Alzheimer's disease research (Scientific Data)
- Mathys et al., 2019 — Single-cell transcriptomic analysis of Alzheimer's disease (Nature)
- Mostafavi et al., 2018 — A molecular network of the aging human brain (Nature Neuroscience)
- Wingo et al., 2020 — Integrating human brain proteomes with genome-wide association data implicates new proteins in Alzheimer's disease pathogenesis (Nature Genetics)

## Related

`[[amp-ad]]`, `[[msbb]]`, `[[mayo-rnaseq]]`, `[[sea-ad]]`, `[[nacc]]`, `[[adni]]`. ROSMAP is the -omics flagship within AMP-AD; SEA-AD provides higher-resolution single-cell on a smaller donor set; NACC adds the clinical/neuropath network depth.
