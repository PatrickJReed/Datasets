---
name: UK Biobank
aliases: [UKB]
host: UK Biobank
url: https://www.ukbiobank.ac.uk/
access: controlled
modalities: [gwas, wgs, exome, mri, dxa, clinical, proteomics, metabolomics, ehr]
species: human
tissue: [whole-body, brain, retina, blood]
conditions: [population-cohort, multiple-conditions]
n_subjects: ~500000
n_samples: ~500000
age_range: 40-73
scale_gb: ~2000000
license: UK Biobank Access (paid)
year: 2006-ongoing
tags: [aging, population, multi-omic, imaging, longitudinal]
ai_relevance: [foundation-model, aging-trajectory, disease-risk, multimodal, imaging]
compute_hint: cluster
benchmark_splits: false
last_reviewed: 2026-05-14
---

## Summary

UK Biobank is a half-million-person prospective population cohort recruited across the UK between 2006 and 2010, with participants aged 40–73 at enrollment and followed through linked electronic health records and ongoing imaging revisits. Its depth and breadth are unmatched: whole-genome sequencing is complete for the full cohort, brain and cardiac MRI has been collected on roughly 100,000 participants, and Olink proximity-extension assays have profiled ~1,500 proteins in ~50,000 samples. The combination of genetics, multi-organ imaging, metabolomics, proteomics, and decades of EHR linkage makes it the single largest open-by-application multimodal human dataset and the dominant resource for population-scale AI research on human health and aging.

## Features

- Whole-genome sequencing for all ~500,000 participants; exome sequencing also available
- Brain MRI (T1, T2-FLAIR, diffusion, susceptibility, resting-state fMRI) on ~100,000 subjects — the largest such publicly accessible collection
- Cardiac and abdominal MRI enabling multi-organ phenotyping; retinal fundus photography
- Olink proteomics (~1,500 proteins) on ~50,000 subjects; NMR metabolomics (Nightingale) on ~120,000 subjects
- Longitudinal EHR linkage to Hospital Episode Statistics, primary care records, cancer registry, and death records
- DXA bone and body-composition measures; accelerometry from wrist-worn devices on ~100,000 participants

## Potential AI use cases

- Biological age estimation and aging-trajectory modeling from multimodal phenotypes
- Multimodal foundation model pretraining on paired genetics, imaging, and proteomics
- Polygenic risk score development and genome-wide association study replication at scale
- Brain MRI foundation models leveraging the largest available neuroimaging corpus
- Disease-onset prediction and early-warning systems using linked longitudinal EHR data

## Access notes

Access requires a formal application through the UK Biobank Access Management System, institutional sign-off, and payment of a data access fee (tiered by project scope). Review by the UK Biobank Access Sub-Committee typically takes 2–6 months. Approved researchers access data via the UK Biobank Research Analysis Platform (RAP), a DNAnexus cloud environment; data cannot be bulk-downloaded to local systems. Imaging data requires a separate imaging application linked to the primary project.

## Notable papers

- Sudlow et al., 2015 — UK Biobank: an open access resource for identifying the causes of a wide range of complex diseases (PLOS Medicine)
- Bycroft et al., 2018 — The UK Biobank resource with deep phenotyping and genomic data (Nature)
- Littlejohns et al., 2020 — The UK Biobank imaging enhancement of 100,000 participants (Nature Communications)

## Related

`[[adni]]`, `[[amp-ad]]`, `[[gtex]]`
