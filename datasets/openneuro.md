---
name: OpenNeuro
aliases: []
host: Stanford / OpenNeuro
url: https://openneuro.org/
access: open
modalities: [mri, fmri, eeg, meg, ieeg, pet]
species: human
tissue: [whole-brain]
conditions: [multiple-conditions, control]
n_subjects: ~100000
n_samples: ~1000-studies
age_range: mixed
scale_gb: ~200000
license: CC0 (typical, per-dataset)
year: 2017-ongoing
tags: [neuro, imaging, multimodal, aggregator]
ai_relevance: [foundation-model, imaging, brain-decoding, multimodal]
compute_hint: gpu-multi
benchmark_splits: false
last_reviewed: 2026-05-14
---

## Summary

OpenNeuro is an open aggregator and archive for BIDS-formatted human neuroimaging data, hosted at Stanford and launched in 2017 as the successor to OpenfMRI. It hosts more than 1,000 datasets spanning MRI, fMRI, EEG, MEG, intracranial EEG (iEEG), and PET across tens of thousands of participants and a wide range of experimental paradigms, clinical populations, and acquisition hardware. Standardization under the Brain Imaging Data Structure (BIDS) specification makes cross-study combination tractable, and the CC0 licensing on the vast majority of datasets removes legal barriers to large-scale ML use. OpenNeuro has become the de facto standard archive for neuroimaging data sharing and the primary source corpus for neuroimaging foundation model development.

## Features

- BIDS-standardized structure across all datasets, enabling automated ingestion and cross-study pooling
- Broad modality coverage: structural and functional MRI, diffusion MRI, EEG, MEG, iEEG, and PET in a single archive
- Diverse paradigms — task-based fMRI, resting-state, naturalistic viewing, clinical epilepsy, sleep, and more
- Rich scanner and acquisition metadata; many datasets include participant demographic and clinical variables
- Public S3 bucket and `openneuro-cli` for efficient bulk access; DataLad integration for versioned retrieval
- Continuously growing: new datasets added weekly; versioned snapshots preserve reproducibility

## Potential AI use cases

- Pretraining neuroimaging foundation models on aggregate MRI and fMRI volumes across scanners and populations
- Brain-state and cognitive-state decoding using task-labeled fMRI across diverse paradigms
- Multimodal alignment between simultaneous EEG and fMRI recordings available in several datasets
- Cross-cohort transfer learning and domain adaptation across heterogeneous scanner environments
- Normative modeling of brain structure and function using population-level aggregate data

## Access notes

All datasets are openly downloadable without registration via openneuro.org or directly from the public AWS S3 bucket (`s3://openneuro.org`). The `openneuro-cli` Node.js package enables efficient programmatic download with resumable transfers. DataLad (`datalad install`) supports versioned, on-demand retrieval. At roughly 200 TB aggregate, full download requires significant storage; selective per-dataset or per-subject download is recommended for most ML workflows.

## Notable papers

- Markiewicz et al., 2021 — The OpenNeuro resource for sharing of neuroscience data (eLife)

## Related

`[[adni]]`, `[[uk-biobank]]`
