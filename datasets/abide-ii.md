---
name: Autism Brain Imaging Data Exchange II
aliases: [ABIDE II]
host: INDI / NITRC + mirrored on NIMH Data Archive (NDA)
url: http://fcon_1000.projects.nitrc.org/indi/abide/abide_II.html
access: open
modalities: [mri, fmri, dti]
species: human
tissue: [whole-brain]
conditions: [autism-spectrum-disorder, control]
n_subjects: ~2050
n_samples: ~2050
age_range: 5-64
scale_gb: ~1000
license: CC BY-NC-SA (typical, per-site)
year: 2017
tags: [neuro, autism, imaging, benchmark, multi-site]
ai_relevance: [disease-classification, imaging, multi-site-harmonization, longitudinal]
compute_hint: gpu-single
benchmark_splits: false
last_reviewed: 2026-05-14
---

## Summary

Extension of ABIDE I with additional sites, expanded phenotyping, and broader modality coverage. ~1100 ASD and ~940 controls from 19 sites, including some longitudinal collections. Designed to complement ABIDE I rather than replace it — many studies pool both releases.

## Features

- T1, T2 anatomical MRI, DTI, and resting-state fMRI
- Improved phenotypic depth (medication use, behavioral measures, IQ subscales)
- Some sites contribute longitudinal sessions
- 19 acquisition sites with similar multi-site heterogeneity to ABIDE I

## Potential AI use cases

- ASD classification with larger effective N when pooled with ABIDE I
- Longitudinal autism modeling (limited but available subset)
- DTI-augmented multi-modal classification
- Domain-adaptation across the ABIDE I/II site mix

## Access notes

Open download via the INDI portal, same channel as ABIDE I. Pool with ABIDE I freely but track site origin — site is the dominant batch covariate.

## Notable papers

- Di Martino et al., 2017 — Enhancing studies of the connectome in autism using the autism brain imaging data exchange II (Scientific Data)

## Related

`[[abide-i]]`, `[[abcd]]`, `[[openneuro]]`.
