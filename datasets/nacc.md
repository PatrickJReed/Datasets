---
name: National Alzheimer's Coordinating Center
aliases: [NACC]
host: University of Washington / NIA-funded
url: https://naccdata.org/
access: controlled
modalities: [clinical, neuropsych, neuropath, mri, genotype]
species: human
tissue: [whole-brain]
conditions: [alzheimers, mild-cognitive-impairment, frontotemporal-dementia, lewy-body, control]
n_subjects: ~50000
n_samples: ~200000
age_range: 60-100
scale_gb: ~5000
license: NACC DUA
year: 1999-ongoing
tags: [aging, alzheimers, dementia, longitudinal, clinical, neuropath]
ai_relevance: [disease-classification, longitudinal, biomarker, multimodal]
compute_hint: gpu-single
benchmark_splits: false
last_reviewed: 2026-05-14
---

## Summary

NIA-funded coordinating center for the network of Alzheimer's Disease Research Centers (ADRCs) across US academic medical centers. Aggregates standardized clinical, neuropsychological, and neuropathological data from ~50k participants enrolled at ~37 ADRCs. The Uniform Data Set (UDS) provides harmonized visit-level data across centers; the Neuropathology Data Set (NP) provides postmortem characterization for the autopsy subset. Genotype data is linked through NIAGADS for participants who consented.

## Features

- Uniform Data Set (UDS) v3: harmonized clinical and cognitive assessments at annual visits
- Neuropathology Data Set: standardized postmortem characterization (~25% of participants)
- MRI subset through the NACC imaging program
- Linkage to NIAGADS for genomic data and to ADRC biospecimen banks
- Coverage across multiple dementia syndromes, not just AD (FTD, LBD, mixed)
- Spans 1999-present with substantial longitudinal follow-up

## Potential AI use cases

- AD progression and conversion modeling from longitudinal UDS visits
- Clinical-to-neuropath prediction (does cognitive profile predict pathology?)
- Multimodal disease classification combining UDS + NP + MRI
- Dementia-subtype discrimination (AD vs FTD vs LBD vs mixed)
- Cohort enrichment for downstream multi-omic studies (link out to AMP-AD)

## Access notes

NACC DUA via the NACC portal. Approval typically 2-4 weeks. Data delivered as CSV exports. Imaging access is a separate request; genotype access goes through NIAGADS independently.

## Notable papers

- Beekly et al., 2007 (NACC UDS introduction)
- Besser et al., 2018 (NACC UDS v3 description)
- Beach et al., 2012 (NACC neuropathology data)

## Related

`[[amp-ad]]`, `[[adni]]`, `[[sea-ad]]`. NACC is the clinical/neuropath backbone; AMP-AD adds the -omics layer; ADNI adds the longitudinal biomarker imaging. Many participants are cross-enrolled.
