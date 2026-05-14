---
name: NIMH Repository and Genomics Resource
aliases: [NRGR, NIMH-RGR]
host: Rutgers University Cell and DNA Repository / NIMH
url: https://www.nimhgenetics.org/
access: controlled
modalities: [genotype, wgs, exome, gwas, biospecimens, clinical]
species: human
tissue: [blood, lymphoblastoid-cell-lines]
conditions: [schizophrenia, bipolar, autism, adhd, depression, control]
n_subjects: ~200000
n_samples: ~250000
age_range: mixed
scale_gb: ~50000
license: NIMH-RGR DUA + dbGaP for genomic data
year: 1998-ongoing
tags: [neuro, psychiatric, genetics, biorepository, multi-condition]
ai_relevance: [disease-risk, gwas, regulatory-genomics, cross-disorder]
compute_hint: gpu-single
benchmark_splits: false
last_reviewed: 2026-05-14
---

## Summary

NIMH-funded biorepository and genomic data resource for psychiatric and neurodevelopmental disorders, operated by the Rutgers University Cell and DNA Repository. Distributes biological samples (DNA, lymphoblastoid cell lines, plasma) and accompanying genotype/sequencing data for major psychiatric cohorts. A primary substrate for the Psychiatric Genomics Consortium (PGC) and many large GWAS meta-analyses.

## Features

- Sample collection for schizophrenia, bipolar disorder, autism, ADHD, MDD, and control families
- Genotype arrays, exome sequencing, and WGS depending on study
- Family-based collections (trios, multiplex pedigrees) enabling de novo and segregation analysis
- Long-term sample preservation suitable for repeat assays
- Cross-disorder coverage useful for shared-architecture studies

## Potential AI use cases

- Cross-disorder genetic risk modeling
- Rare-variant burden prediction for psychiatric phenotypes
- Polygenic score development and transfer across ancestries
- Integration with brain transcriptome (psychENCODE, CMC) for variant-to-function inference

## Access notes

Sample requests reviewed by NIMH-RGR access committee (typically 4-8 weeks). Genomic data is distributed via dbGaP; expect controlled-access timelines of 4-8 weeks beyond the NRGR request. Some PGC summary statistics are open.

## Notable papers

- NIMH Repository and Genomics Resource (Massachusetts General Hospital and Rutgers reports)
- PGC schizophrenia, bipolar, autism, and cross-disorder papers (2014-onwards)

## Related

`[[psychencode]]`, `[[commonmind]]`, `[[amp-ad]]`. NRGR provides the genetic substrate; psychENCODE and CMC provide the brain-tissue molecular phenotypes for many of the same disorders.
