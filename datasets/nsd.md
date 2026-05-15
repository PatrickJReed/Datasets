---
name: Natural Scenes Dataset
aliases: [NSD]
host: Allen Institute / University of Minnesota / OpenNeuro mirror
url: http://naturalscenesdataset.org/
access: open
modalities: [fmri-7t, behavioral]
species: human
tissue: [whole-brain]
conditions: [typical-adult]
n_subjects: 8
n_samples: ~213000
age_range: 19-32
scale_gb: ~2000
license: CC BY 4.0
year: 2021
tags: [neuro, imaging, vision, dense-sampling, high-field, foundation-model]
ai_relevance: [brain-decoding, vision-language, image-fmri-alignment, dense-sampling]
compute_hint: gpu-multi
benchmark_splits: true
last_reviewed: 2026-05-15
---

## Summary

7T fMRI dataset that scanned 8 subjects for 30-40 hours each while viewing ~73,000 unique natural images from MS-COCO. The deepest per-subject visual-system fMRI dataset ever released, and the substrate for almost all current image-from-fMRI decoding work (MindEye, Brain-Diffuser, et al.). Open download, comes with canonical splits.

## Features

- 8 subjects, 30-40 hours of 7T fMRI per subject
- ~10,000 unique images per subject (plus shared 1,000-image set across subjects)
- High-resolution functional acquisition (1.8mm isotropic)
- Behavioral memory task data alongside the visual stimulation
- Preprocessed in subject native space and on the fsaverage cortical surface
- Canonical train / shared-test splits documented for benchmarking

## Potential AI use cases

- Image-from-fMRI decoding and reconstruction
- Vision-language alignment using fMRI as a third modality
- Encoding models for individual-subject visual cortex
- Benchmark for fMRI foundation models (within-subject deep sampling)
- Cross-subject generalization research

## Access notes

Open download via the NSD website and OpenNeuro mirror. ~2 TB for full preprocessed; smaller subsets available. No DUA. The accompanying COCO image annotations are essential — included in the release.

## Notable papers

- Allen et al., 2022 — A massive 7T fMRI dataset to bridge cognitive neuroscience and artificial intelligence (Nature Neuroscience)

## Related

`[[ibc]]`, `[[narratives]]`, `[[hbn]]`, `[[abcd]]`. NSD and IBC are the two canonical deep within-subject task-fMRI datasets; HBN and ABCD provide the breadth.
