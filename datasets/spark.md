---
name: SPARK (Simons Foundation Powering Autism Research)
aliases: [SPARK]
host: Simons Foundation Autism Research Initiative / SFARI Base
url: https://sparkforautism.org/
access: controlled
modalities: [exome, genotype, wgs, phenotype, behavioral, parent-report]
species: human
tissue: [saliva, blood]
conditions: [autism-spectrum-disorder, unaffected-relative]
n_subjects: ~250000
n_samples: ~250000
age_range: pediatric-to-adult
scale_gb: ~50000
license: SFARI Base DUA
year: 2016-ongoing
tags: [neuro, autism, genetics, large-cohort, family-based, longitudinal]
ai_relevance: [disease-risk, rare-variant, polygenic, large-cohort, recontact]
compute_hint: gpu-multi
benchmark_splits: false
last_reviewed: 2026-05-15
---

## Summary

Successor and dramatic expansion of SSC. ~100,000+ enrolled families and ~250,000 individuals as of 2024, with ongoing recruitment via a remote-first design (saliva kits by mail, online phenotyping). Exome sequencing for most enrolled, increasingly transitioning toward WGS. Designed for both research releases and participant recontact for follow-up studies.

## Features

- ~250k individuals across enrolled families (probands + relatives)
- Exome sequencing (early waves) and WGS (newer waves)
- Genome-wide genotyping
- Parent- and self-report phenotype data, including longitudinal updates
- Recontactable cohort — participants can be invited into follow-up studies
- Ancestry diversity is broader than SSC (still skewed European)

## Potential AI use cases

- Large-cohort rare-variant burden and gene discovery
- Polygenic score development and validation in autism
- Phenotype heterogeneity modeling (clustering, latent factor models)
- Longitudinal trajectory modeling as participants age
- Pre-screening for follow-up imaging or biospecimen studies

## Access notes

SFARI Base DUA required. Approval typically 4-8 weeks. Data delivered via SFARI Base cloud workspace. Some derived releases (e.g., gene-discovery results) are openly available; raw genomes/exomes remain controlled.

## Notable papers

- Feliciano et al., 2017 — SPARK study design (Neuron)
- Zhou et al., 2022 — Integrating de novo and inherited variants in 42,607 autism cases (Nature Genetics, partly SPARK)

## Related

`[[ssc]]`, `[[pgc]]`, `[[abcd]]`. SPARK provides scale that SSC lacks; SSC retains the cleaner family design. ABCD complements both with imaging on a non-autism developmental cohort.
