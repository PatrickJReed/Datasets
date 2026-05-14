---
name: Alzheimer's Disease Neuroimaging Initiative
aliases: [ADNI]
host: USC LONI / ADNI
url: https://adni.loni.usc.edu/
access: controlled
modalities: [mri, pet, csf-biomarkers, clinical, genotype]
species: human
tissue: [whole-brain, csf]
conditions: [alzheimers, mild-cognitive-impairment, control]
n_subjects: ~2300
n_samples: ~15000
age_range: 55-90
scale_gb: ~5000
license: ADNI DUA
year: 2004-ongoing
tags: [aging, alzheimers, imaging, longitudinal, biomarker]
ai_relevance: [disease-classification, longitudinal, imaging-foundation-model, biomarker]
compute_hint: gpu-multi
benchmark_splits: false
last_reviewed: 2026-05-14
---

## Summary

The Alzheimer's Disease Neuroimaging Initiative (ADNI) is a longitudinal multi-site study launched in 2004 to develop and validate biomarkers for AD detection and progression monitoring. It follows roughly 2,300 participants across cognitively normal, MCI, and AD groups through serial neuroimaging, CSF sampling, cognitive testing, and genotyping visits spanning up to a decade. ADNI has been continuously expanded through ADNI-GO, ADNI-2, and ADNI-3 phases, with each phase adding new modalities such as tau PET and increasing diversity recruitment. It remains the primary reference dataset for AD neuroimaging biomarker research worldwide.

## Features

- Structural MRI (T1, T2, FLAIR) and diffusion tensor imaging across multiple serial visits per participant
- Amyloid PET (florbetapir, florbetaben) and tau PET (flortaucipir) with longitudinal follow-up
- CSF Aβ42, total-tau, and phospho-tau biomarker panels from lumbar punctures
- Composite cognitive scores (ADAS-Cog, MMSE, CDR) and neuropsychological battery at each visit
- APOE genotyping and genome-wide SNP arrays enabling genetic stratification
- Harmonized image preprocessing pipelines and FreeSurfer-derived volumetrics distributed alongside raw scans

## Potential AI use cases

- Imaging foundation models for the aging brain trained on large-scale serial MRI volumes
- AD onset and progression prediction from multimodal MRI, PET, CSF, and cognitive trajectories
- Multimodal fusion models combining imaging, biofluid, and genetic inputs for risk stratification
- Longitudinal trajectory modeling and time-to-conversion estimation
- Transfer learning to smaller neuroimaging cohorts using ADNI-pretrained representations

## Access notes

Access requires a registered account on the LONI Image and Data Archive (IDA) and acceptance of the ADNI Data Use Agreement. Applications are reviewed by the ADNI Data and Publications Committee; approval typically takes 1–2 weeks. Data are downloaded through the LONI IDA web interface or API. At roughly 5 TB, full download is feasible on a well-provisioned workstation but cloud storage is recommended for iterative experiments.

## Notable papers

- Petersen et al., 2010 — ADNI design, cohort description, and baseline results (Journal of Alzheimer's Disease)
- Weiner et al., 2017 — recent progress and future plans for the ADNI study (Alzheimer's and Dementia)

## Related

`[[amp-ad]]`, `[[sea-ad]]`, `[[openneuro]]`
