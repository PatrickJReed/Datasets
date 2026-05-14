---
name: Adolescent Brain Cognitive Development Study
aliases: [ABCD]
host: ABCD Study Consortium / data via NIMH Data Archive (NDA)
url: https://abcdstudy.org/
access: controlled
modalities: [mri, fmri, dti, behavioral, neurocog, genotype, hormones, environment]
species: human
tissue: [whole-brain]
conditions: [typical-development, preclinical-mental-health]
n_subjects: ~12000
n_samples: ~80000
age_range: 9-19
scale_gb: ~50000
license: NDA Data Use Certification
year: 2016-ongoing
tags: [neuro, neurodev, longitudinal, multimodal, large-cohort, pediatric]
ai_relevance: [foundation-model, imaging, multimodal, brain-age, development, brain-decoding]
compute_hint: gpu-multi
benchmark_splits: false
last_reviewed: 2026-05-14
---

## Summary

NIH-funded longitudinal study of brain development in ~12,000 children enrolled at ages 9-10 across 21 US sites, with annual or biennial follow-up through young adulthood. The largest pediatric multimodal MRI cohort by a wide margin, paired with extensive behavioral, cognitive, genetic, hormonal, and environmental measures. ABCD has become a reference substrate for developmental neuroimaging and brain-age work.

## Features

- Structural MRI (T1, T2), diffusion (DTI), resting-state fMRI, and task fMRI (MID, SST, n-back) per visit
- Repeated standardized neurocognitive battery and mental-health screens
- Genome-wide genotyping with imputation; hormone and pubertal staging measures
- Detailed family, environment, and socioeconomic measures suitable for confound control
- Multi-site design with harmonized acquisition protocols across Siemens, GE, and Philips scanners
- Annual data releases (ABCD 5.x as of 2024) with cumulative longitudinal depth

## Potential AI use cases

- Developmental imaging foundation models pretrained on the largest pediatric multimodal corpus available
- Brain-age estimation and trajectory modeling across adolescence
- Multimodal mental-health prediction (imaging + behavior + genetics + environment)
- Site-harmonization and domain-adaptation benchmark
- Transfer learning to smaller pediatric clinical cohorts
- Causal/observational analyses leveraging the longitudinal design

## Access notes

NDA Data Use Certification (DUC) is required, plus institutional sign-off. Approval typically 2-4 weeks. Access via miNDAR cloud workspace or direct download. ABCD-specific publication and data-use policies apply on top of NDA's; check ABCD Study's data sharing page for any embargo periods on current releases.

## Notable papers

- Casey et al., 2018 — The Adolescent Brain Cognitive Development (ABCD) study: imaging acquisition (Developmental Cognitive Neuroscience)
- Volkow et al., 2018 — The conception of the ABCD study (Developmental Cognitive Neuroscience)
- Karcher & Barch, 2021 — The ABCD study: understanding the development of risk for mental and physical health outcomes (Annual Review of Clinical Psychology)

## Related

`[[adni]]`, `[[uk-biobank]]`, `[[abide-i]]`, `[[ncanda]]`, `[[openneuro]]`. ABCD is the pediatric counterpart to UK Biobank's adult/aging multimodal scale.
