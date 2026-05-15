---
name: BRAIN Initiative Cell Atlas Network
aliases: [BICAN]
host: NIH BRAIN Initiative / NeMO Archive
url: https://www.portal.brain-bican.org/
access: open
modalities: [scRNA-seq, snRNA-seq, snATAC-seq, multiome, merfish, patch-seq]
species: multi
tissue: [whole-brain, multiple-brain-regions]
conditions: [control]
n_subjects: unknown
n_samples: unknown
age_range: adult
scale_gb: unknown
license: per-study (mostly open)
year: 2022-ongoing
tags: [neuro, single-cell, multimodal, atlas, umbrella, program, consortium]
ai_relevance: [single-cell-foundation-model, cell-type-annotation, spatial-transcriptomics, multimodal, cross-species]
compute_hint: gpu-multi
benchmark_splits: false
last_reviewed: 2026-05-14
---

## Summary

**Umbrella / program — not a single dataset.** Successor to `[[biccn]]`, launched 2022. Goal is a complete cell atlas of the human brain at single-cell resolution, with complementary work in mouse and non-human primates. Funded across 16+ centers (Allen, Salk, Broad, MIT, Karolinska, etc.) using NeMO Archive as the shared data repository.

Trainable BICAN constituents are still ramping as of mid-2026 — most flagship datasets are pre-release or partial. Re-evaluate this page periodically and split out specific atlases as they earn standalone citations. For now, treat BICAN as program context.

## Features

- Whole-human-brain single-cell coverage as the stated endpoint, far beyond BICCN's regional flagships
- snRNA-seq, snATAC-seq, multiome, MERFISH, Patch-seq, with some centers adding connectomics
- Standardized cell-type ontology aligned with BICCN's
- Multi-center coordination on sample sourcing and donor metadata
- Open release via NeMO Archive with anticipated CELLxGENE mirrors

## Potential AI use cases

- Cross-species single-cell foundation model pretraining at unprecedented human scale
- Cell-type annotation and harmonization across centers and modalities
- Spatial-transcriptomics modeling on MERFISH whole-brain coverage
- Transfer learning to disease cohorts (AD, psychiatric) using a healthy human-brain reference
- Multi-resolution atlases (region → cell type → state) for hierarchical models

## Access notes

Open via NeMO Archive. Some human samples are dbGaP-controlled. Watch the BICAN portal for staged data releases — many flagship datasets are still pre-release or partially released.

## Notable papers

- BICAN program announcement, NIH (2022)
- Initial BICAN flagship preprints (2024-2025) — check the consortium publication list

## Related

`[[biccn]]`, `[[allen-brain-cell-atlas]]`, `[[hca]]`, `[[cellxgene]]`. Direct successor to BICCN; NeMO Archive serves both programs.
