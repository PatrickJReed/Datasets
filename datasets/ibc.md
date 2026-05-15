---
name: Individual Brain Charting
aliases: [IBC]
host: NeuroSpin (CEA Saclay) / OpenNeuro mirror
url: https://project.inria.fr/IBC/
access: open
modalities: [fmri, mri]
species: human
tissue: [whole-brain]
conditions: [typical-adult]
n_subjects: 12
n_samples: ~30000
age_range: 22-40
scale_gb: ~500
license: CC BY 4.0
year: 2018-ongoing
tags: [neuro, imaging, dense-sampling, task-battery, multi-task]
ai_relevance: [brain-decoding, task-representation, cognitive-atlas, dense-sampling]
compute_hint: gpu-single
benchmark_splits: false
last_reviewed: 2026-05-15
---

## Summary

Deep within-subject task-fMRI dataset: 12 subjects scanned across an extensive battery of cognitive tasks (~hundreds of conditions spanning vision, language, attention, memory, motor, social cognition, math, decision-making). Each subject has many tens of hours of scanning, making it the densest task-fMRI atlas at the individual level.

## Features

- 12 subjects, deeply sampled with serial sessions (~150+ hours total accumulated across the cohort)
- Hundreds of distinct task conditions spanning major cognitive domains
- BIDS-formatted and openly distributed via OpenNeuro and the NeuroSpin portal
- Continuing data acquisition with periodic releases adding new task domains

## Potential AI use cases

- Brain-state decoding with rich cognitive labels
- Cognitive-atlas construction and task-representation models
- Within-subject deep modeling complementary to NSD (visual) and Narratives (language)
- Cross-task transfer learning
- Benchmark for low-N high-depth fMRI methods

## Access notes

Open download via OpenNeuro and the IBC portal. No DUA. Data is released in BIDS format with task event files.

## Notable papers

- Pinho et al., 2018 — Individual Brain Charting, a high-resolution fMRI dataset for cognitive mapping (Scientific Data)
- Pinho et al., 2020 — Subsequent releases extending the task battery (Scientific Data)

## Related

`[[nsd]]`, `[[narratives]]`. The triad of NSD (vision), Narratives (language), and IBC (task battery) provides the deep within-subject coverage for cognitive neuroimaging foundation models.
