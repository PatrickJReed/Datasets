---
name: CommonMind Consortium
aliases: [CMC]
host: Synapse / CommonMind Knowledge Portal
url: https://www.synapse.org/commonmind
access: controlled
modalities: [bulk-rna-seq, atac-seq, methylation, wgs, genotype]
species: human
tissue: [prefrontal-cortex, anterior-cingulate]
conditions: [schizophrenia, bipolar, control]
n_subjects: ~1000
n_samples: ~1500
age_range: adult
scale_gb: ~3000
license: CommonMind DUA
year: 2015-ongoing
tags: [neuro, psychiatric, multi-omic, postmortem]
ai_relevance: [regulatory-genomics, disease-classification, eQTL, multimodal]
compute_hint: gpu-single
benchmark_splits: false
last_reviewed: 2026-05-14
---

## Summary

The CommonMind Consortium (CMC) is a postmortem brain resource focused on schizophrenia and bipolar disorder, providing bulk RNA-seq with matched genotype from dorsolateral prefrontal cortex (DLPFC) and anterior cingulate cortex (ACC) from roughly 1,000 donors. It is a frequent partner dataset to psychENCODE — CMC data are included in many PEC integrative analyses — and its deep clinical phenotyping and well-characterized eQTL maps have made it a go-to reference cohort for psychiatric genomics. The relatively modest scale (~3 TB) makes it tractable on a single GPU workstation.

## Features

- Bulk RNA-seq from DLPFC and ACC, including many donors with data from both regions
- ATAC-seq, bisulfite methylation, and WGS for subsets of the cohort
- Donor-level genotype enabling cis- and trans-eQTL analyses
- Curated eQTL maps widely used as external reference in fine-mapping studies
- High-quality clinical phenotyping including diagnosis, medication history, and neuropathology
- Data versioned and distributed via Synapse, with documented QC pipelines

## Potential AI use cases

- eQTL and regulatory-variant prediction from sequence or chromatin context features
- Case/control classification for schizophrenia and bipolar using transcriptomic profiles
- Pretraining on bulk postmortem transcriptomes before fine-tuning on smaller disease cohorts
- Multi-omic integration with matched ATAC-seq and methylation for chromatin accessibility models
- Cross-cohort transfer learning in combination with psychENCODE or GTEx brain samples

## Access notes

Access requires a Synapse account plus acceptance of the CommonMind Consortium Data Use Agreement. Approval typically takes 2–4 weeks. The Synapse project page lists versioned data releases; users should confirm the current canonical release before planning downloads. Raw data are ~3 TB, manageable on a single workstation with adequate storage.

## Notable papers

- Fromer et al., 2016 — gene expression elucidates functional impact of polygenic risk for schizophrenia (Nature Neuroscience)
- Hoffman et al., 2019 — CommonMind Consortium provides transcriptomic and epigenomic data for schizophrenia and bipolar disorder

## Related

`[[psychencode]]`, `[[gtex]]`, `[[amp-ad]]`
