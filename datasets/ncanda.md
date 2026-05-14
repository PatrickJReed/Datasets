---
name: National Consortium on Alcohol and Neurodevelopment in Adolescence
aliases: [NCANDA]
host: NIAAA / data via NIMH Data Archive (NDA)
url: https://ncanda.org/
access: controlled
modalities: [mri, fmri, dti, neurocog, behavioral, substance-use, genotype]
species: human
tissue: [whole-brain]
conditions: [typical-development, adolescent-substance-use]
n_subjects: ~830
n_samples: ~6000
age_range: 12-30
scale_gb: ~5000
license: NDA Data Use Certification
year: 2012-ongoing
tags: [neuro, neurodev, longitudinal, multimodal, substance-use]
ai_relevance: [disease-classification, longitudinal, brain-age, imaging]
compute_hint: gpu-single
benchmark_splits: false
last_reviewed: 2026-05-14
---

## Summary

NIAAA-funded longitudinal study of brain development and the effects of substance use across adolescence and young adulthood. ~830 participants enrolled at ages 12-21 across five sites, with annual follow-up over 8+ years. Designed to disentangle premorbid risk from substance-induced effects on adolescent brain development.

## Features

- Annual T1, DTI, and resting-state fMRI; some task fMRI
- Detailed substance use, family history, neurocognitive, and psychosocial measures
- Five-site design with harmonized acquisition
- Genotyping data available for a subset
- Longitudinal depth that ABCD will eventually match but currently exceeds at older ages

## Potential AI use cases

- Brain-age estimation across adolescence to young adulthood
- Trajectory modeling for substance-use onset and progression
- Causal mediation studies (premorbid vs induced effects)
- Cross-cohort transfer learning with ABCD on overlapping age ranges

## Access notes

NDA DUC required. Approval typically 2-4 weeks. NCANDA-specific publication policies overlay NDA's; check the NCANDA data sharing page for current release status.

## Notable papers

- Brown et al., 2015 — The National Consortium on Alcohol and Neurodevelopment in Adolescence (NCANDA): a multisite study (Alcoholism: Clinical and Experimental Research)
- Pfefferbaum et al., 2018 — Altered brain developmental trajectories in adolescents after initiating drinking (American Journal of Psychiatry)

## Related

`[[abcd]]`, `[[abide-i]]`, `[[uk-biobank]]`. NCANDA covers the late-adolescent to young-adult window where ABCD's longitudinal coverage is still being filled in.
