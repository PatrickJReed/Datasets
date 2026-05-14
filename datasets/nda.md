---
name: NIMH Data Archive
aliases: [NDA, NDAR]
host: NIMH / NIH
url: https://nda.nih.gov/
access: controlled
modalities: [mri, fmri, eeg, clinical, behavioral, genotype, wgs, omics]
species: human
tissue: [whole-brain]
conditions: [autism, adhd, mental-health, neurodevelopment, control]
n_subjects: ~250000
n_samples: ~500000
age_range: pediatric-to-adult
scale_gb: ~500000
license: NDA Data Use Certification
year: 2007-ongoing
tags: [neuro, neurodev, mental-health, aggregator, multimodal, longitudinal]
ai_relevance: [foundation-model, imaging, multimodal, brain-decoding, development]
compute_hint: gpu-multi
benchmark_splits: false
last_reviewed: 2026-05-14
---

## Summary

NIH's central archive for mental health and neurodevelopment research data. Hosts large flagship cohorts including ABCD (Adolescent Brain Cognitive Development, ~12k longitudinal subjects), ABIDE (Autism Brain Imaging Data Exchange), NCANDA (adolescent alcohol use), and the National Database for Autism Research collections. Functions as both a data archive and a federated repository where investigators must deposit NIMH-funded data.

## Features

- ABCD: longitudinal multimodal (MRI, fMRI, DTI, behavioral, genetic) study of ~12k children followed into adulthood
- ABIDE I/II: ~2k subjects with structural and resting-state MRI for autism
- NCANDA: longitudinal adolescent brain + alcohol use
- Smaller collections across autism (NDAR umbrella), ADHD, anxiety, depression
- Genetic data (GWAS, WGS) for many participants in the deposited cohorts
- Standardized data dictionary and Global Unique Identifiers (GUIDs) for cross-study linkage

## Potential AI use cases

- Developmental neuroimaging foundation models (ABCD scale is hard to beat for pediatric brain)
- Multimodal mental-health prediction (imaging + behavior + genetics)
- Cross-cohort transfer learning across autism, ADHD, control
- Brain-age estimation across the lifespan when combined with adult cohorts
- Longitudinal trajectory modeling

## Access notes

NDA Data Use Certification (DUC) required, plus institutional sign-off. Approval typically 2-4 weeks. Data accessed via miNDAR (cloud) or direct download. Many constituent studies (ABCD, ABIDE) also have their own access agreements layered on top.

## Notable papers

- Hall et al., 2012 (NDAR / NDA introduction)
- Volkow et al., 2018 (ABCD study design, Developmental Cognitive Neuroscience)
- Di Martino et al., 2014 (ABIDE I, Molecular Psychiatry)

## Related

`[[openneuro]]`, `[[adni]]`, `[[uk-biobank]]`. NDA and OpenNeuro overlap conceptually (neuroimaging archive) but NDA is controlled-access and broader in modality; OpenNeuro is open and BIDS-only.
