---
name: Autism Brain Imaging Data Exchange I
aliases: [ABIDE I]
host: INDI / NITRC + mirrored on NIMH Data Archive (NDA)
url: http://fcon_1000.projects.nitrc.org/indi/abide/
access: open
modalities: [mri, fmri]
species: human
tissue: [whole-brain]
conditions: [autism-spectrum-disorder, control]
n_subjects: ~2100
n_samples: ~2100
age_range: 7-64
scale_gb: ~500
license: CC BY-NC-SA (typical, per-site)
year: 2014
tags: [neuro, autism, imaging, benchmark, multi-site]
ai_relevance: [disease-classification, imaging, multi-site-harmonization]
compute_hint: gpu-single
benchmark_splits: false
last_reviewed: 2026-05-14
---

## Summary

Retrospective aggregation of structural and resting-state functional MRI from ~1100 autism spectrum disorder (ASD) participants and ~1000 typical controls, contributed by 17 international sites. The first large open multi-site autism imaging dataset, widely used as a benchmark for ASD classification and for stress-testing multi-site harmonization methods.

## Features

- T1 anatomical MRI and resting-state fMRI per subject
- Phenotypic measures (age, sex, ADOS, ADI-R, IQ proxies) for most subjects
- 17 acquisition sites with heterogeneous protocols — explicitly multi-site by design
- Preprocessed pipelines distributed via the Preprocessed Connectomes Project (CCS, CPAC, DPARSF, NIAK)

## Potential AI use cases

- ASD vs control classification benchmarks (long history of methods papers)
- Multi-site domain adaptation and harmonization research
- Pretraining/finetuning baselines for autism-focused models
- Functional-connectivity feature extraction and graph models

## Access notes

Open download via the NITRC/INDI portal. Some sites also share data through NDA. No DUA required for the standard release. Heterogeneity across sites is a feature, not a bug — count on it for harmonization studies.

## Notable papers

- Di Martino et al., 2014 — The autism brain imaging data exchange (Molecular Psychiatry)

## Related

`[[abide-ii]]`, `[[abcd]]`, `[[openneuro]]`. ABIDE II extends ABIDE I with additional sites and modalities; ABCD provides a much larger pediatric typical-development reference.
