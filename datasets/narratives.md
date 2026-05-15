---
name: Narratives
aliases: []
host: Hasson Lab / OpenNeuro
url: https://openneuro.org/datasets/ds002345
access: open
modalities: [fmri]
species: human
tissue: [whole-brain]
conditions: [typical-adult]
n_subjects: ~345
n_samples: ~750
age_range: 18-53
scale_gb: ~50
license: CC0
year: 2021
tags: [neuro, imaging, language, narrative, naturalistic, story-listening]
ai_relevance: [language-brain-alignment, naturalistic-decoding, foundation-model, fmri-language]
compute_hint: gpu-single
benchmark_splits: false
last_reviewed: 2026-05-15
---

## Summary

Aggregated fMRI dataset of ~345 subjects listening to 27 distinct spoken stories. The standard substrate for language-brain alignment research, particularly the line of work mapping LLM (GPT-2, GPT-3, etc.) embeddings to neural responses during naturalistic comprehension.

## Features

- ~345 unique subjects across studies, ~750 total scanning sessions
- 27 distinct narratives ranging from short anecdotes to ~50-minute stories
- Time-aligned story transcripts and audio
- BIDS-formatted; multi-study aggregation harmonized
- Mix of within-subject (multiple stories per subject) and between-subject coverage

## Potential AI use cases

- LLM-to-brain alignment (encoding models from transformer embeddings)
- Naturalistic language decoding from fMRI
- Cross-subject and cross-story generalization benchmarks
- Multimodal alignment with audio features
- Foundation-model pretraining for language-related fMRI

## Access notes

CC0 — fully open. Available as a single OpenNeuro deposit. Story audio and aligned transcripts are part of the release.

## Notable papers

- Nastase et al., 2021 — The "Narratives" fMRI dataset for evaluating models of naturalistic language comprehension (Scientific Data)

## Related

`[[nsd]]`, `[[ibc]]`. The standard deep-within-subject neuroimaging triad: vision (NSD), language (Narratives), task battery (IBC).
