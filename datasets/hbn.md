---
name: Healthy Brain Network
aliases: [HBN, CMI-HBN]
host: Child Mind Institute / mirrored on OpenNeuro and FCP-INDI
url: https://healthybrainnetwork.org/
access: registered
modalities: [mri, fmri, dti, eeg, eye-tracking, voice, behavioral, clinical]
species: human
tissue: [whole-brain]
conditions: [autism, adhd, anxiety, depression, learning-disorders, control, mixed]
n_subjects: ~5000
n_samples: ~5000
age_range: 5-21
scale_gb: ~50000
license: CC BY-NC-SA (data) + HBN DUA
year: 2015-ongoing
tags: [neuro, neurodev, pediatric, transdiagnostic, multimodal, deep-phenotyping]
ai_relevance: [disease-classification, transdiagnostic, multimodal, brain-age, imaging]
compute_hint: gpu-multi
benchmark_splits: false
last_reviewed: 2026-05-15
---

## Summary

Child Mind Institute's ongoing transdiagnostic pediatric study. Recruits children and adolescents (5-21) from the New York region with a broad inclusion philosophy — ~80% have at least one psychiatric diagnosis, but no one diagnosis dominates. Combines structural and functional MRI, DTI, dense EEG, eye-tracking, voice, and deep clinical/behavioral phenotyping. Released openly in rolling waves.

## Features

- ~5,000 participants with serial data releases (HBN-1 through HBN-13 as of 2024)
- T1, T2, DTI, resting-state and task fMRI
- High-density EEG with task batteries
- Eye-tracking and voice recordings
- Standardized psychiatric assessments (K-SADS) and broad behavioral instruments
- Genotyping for a subset
- Transdiagnostic by design: useful for dimensional rather than categorical modeling

## Potential AI use cases

- Transdiagnostic dimensional modeling (avoid forced categorical labels)
- Multimodal foundation models on pediatric neuroimaging (MRI + EEG)
- Brain-age estimation across childhood and adolescence
- Phenotype clustering to surface data-driven subtypes
- Cross-modal alignment (eye-tracking + fMRI, voice + MRI)

## Access notes

Registration-based access via the HBN data portal and OpenNeuro mirror. No DUA for the open MRI/EEG release; some clinical/sensitive measures require a separate access agreement.

## Notable papers

- Alexander et al., 2017 — An open resource for transdiagnostic research in pediatric mental health and learning disorders (Scientific Data)

## Related

`[[abcd]]`, `[[abide-i]]`, `[[ncanda]]`. ABCD has more subjects and longitudinal depth but narrower inclusion (typical-development focused); HBN has broader clinical heterogeneity.
