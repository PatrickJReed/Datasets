---
name: Simons Simplex Collection
aliases: [SSC]
host: Simons Foundation Autism Research Initiative / SFARI Base
url: https://www.sfari.org/resource/simons-simplex-collection/
access: controlled
modalities: [exome, genotype, phenotype, behavioral]
species: human
tissue: [blood]
conditions: [autism-spectrum-disorder, unaffected-sibling, parent]
n_subjects: ~10000
n_samples: ~10000
age_range: pediatric-to-adult
scale_gb: ~5000
license: SFARI Base DUA
year: 2010-ongoing
tags: [neuro, autism, genetics, family-based, trios, de-novo]
ai_relevance: [disease-risk, rare-variant, de-novo-variant, family-based-modeling]
compute_hint: gpu-single
benchmark_splits: false
last_reviewed: 2026-05-15
---

## Summary

~2,800 "simplex" families (one autistic child + unaffected sibling + both parents, the canonical quad design) collected by SFARI to enable rare and de novo variant analysis. Exome sequencing + genotyping + deep phenotyping (cognitive, behavioral, medical). The substrate for the first wave of large-scale de novo mutation studies in autism.

## Features

- ~2,800 quads (proband, unaffected sibling, mother, father)
- Whole-exome sequencing on all family members
- Genome-wide genotyping
- Deep autism phenotyping (ADOS, ADI-R, Vineland, cognitive testing)
- Family-based design enables transmission tests and de novo variant calling
- Distributed alongside biospecimens for downstream assays

## Potential AI use cases

- De novo variant burden prediction
- Rare-variant constraint and pathogenicity scoring
- Gene-discovery models that leverage transmission information
- Polygenic + rare-variant integrated risk modeling
- Family-based phenotype-genotype mapping

## Access notes

SFARI Base DUA required. Approval typically 4-8 weeks. Genomic data accessed via SFARI Base cloud workspace or dbGaP for selected releases.

## Notable papers

- Iossifov et al., 2014 — The contribution of de novo coding mutations to autism spectrum disorder (Nature)
- Sanders et al., 2015 — Insights into autism spectrum disorder genomic architecture and biology from 71 risk loci (Neuron)

## Related

`[[spark]]`, `[[pgc]]`, `[[psychencode]]`. SPARK is the much larger successor with broader phenotype coverage; SSC remains the gold-standard quad design.
