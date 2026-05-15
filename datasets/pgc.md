---
name: Psychiatric Genomics Consortium
aliases: [PGC]
host: PGC consortium; summary statistics via PGC website (downloads page)
url: https://pgc.unc.edu/
access: open
modalities: [gwas-summary-statistics, polygenic-scores]
species: human
tissue: [blood]
conditions: [schizophrenia, bipolar, mdd, adhd, autism, ocd, ptsd, eating-disorder, cross-disorder]
n_subjects: ~1500000
n_samples: ~1500000
age_range: mixed
scale_gb: ~50
license: per-wave terms (typically open; check the PGC downloads page)
year: 2007-ongoing
tags: [neuro, psychiatric, gwas, summary-statistics, meta-analysis, multi-wave]
ai_relevance: [polygenic-scores, disease-risk, gene-prioritization, regulatory-genomics]
compute_hint: cpu
benchmark_splits: false
last_reviewed: 2026-05-14
---

## Summary

The Psychiatric Genomics Consortium runs the largest meta-analyses of psychiatric GWAS. Practical research use is at the **per-disorder per-wave** level — researchers cite "PGC SCZ wave 3," "PGC BD 2021," etc. — but the consortium publishes them under a unified pipeline and download portal. Summary statistics are open; individual-level data sits behind the contributing studies (often dbGaP, often via NRGR for sample distribution).

## Features

- Per-disorder summary-statistic releases with harmonized formats
- Major waves include: schizophrenia (Trubetskoy et al., 2022 wave 3, ~76k cases), bipolar (Mullins et al., 2021, ~41k cases), MDD (Howard et al., 2019; later updates), ADHD (Demontis et al., 2023), autism (Grove et al., 2019), OCD, PTSD, eating disorders
- Cross-disorder meta-analyses (Cross-Disorder Group, 2019)
- Largely European ancestry historically, with expanding multi-ancestry efforts
- Sumstats are typically a few GB per disorder

## Potential AI use cases

- Polygenic-score model development and benchmarking
- Mendelian randomization and instrumental-variable methods
- Variant prioritization combined with regulatory annotations (ENCODE, psychENCODE)
- Multi-disorder transfer learning across psychiatric phenotypes
- Pretraining substrate for variant-effect models when paired with functional data
- Trans-ancestry score portability research

## Access notes

Most summary statistics are open download (Excel or tab-delimited GWAS summary formats) from the PGC website. Some recent waves have brief embargoes or registration requirements — check the per-wave instructions. Individual-level data is held by contributing studies, not PGC; expect dbGaP or institutional DUAs for those, and NRGR-distributed samples for many psychiatric cohorts.

## Notable papers

- Trubetskoy et al., 2022 — Mapping genomic loci implicates genes and synaptic biology in schizophrenia (Nature)
- Mullins et al., 2021 — Genome-wide association study identifies 64 risk loci for bipolar disorder (Nature Genetics)
- Howard et al., 2019 — Genome-wide meta-analysis of depression identifies 102 independent variants (Nature Neuroscience)
- Grove et al., 2019 — Identification of common genetic risk variants for autism (Nature Genetics)
- Demontis et al., 2023 — Genome-wide analyses of ADHD identify 27 risk loci (Nature Genetics)
- Cross-Disorder Group of the PGC, 2019 — Genomic relationships, novel loci, and pleiotropic mechanisms across eight psychiatric disorders (Cell)

## Related

`[[ssc]]`, `[[spark]]`, `[[psychencode]]`, `[[commonmind]]`. PGC summary stats are typically combined with brain transcriptome data (psychENCODE, CMC) for variant-to-function studies.
