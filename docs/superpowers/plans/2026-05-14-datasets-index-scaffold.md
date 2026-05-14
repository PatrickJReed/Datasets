# Datasets Index Scaffold — Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Scaffold the Datasets index repo and seed it with 15 dataset profiles, 5 category files, a CONTRIBUTING guide, a dataset template, and a hand-built README with a quick-find table.

**Architecture:** Markdown-only repo. Each dataset is one file in `datasets/` with YAML frontmatter (filterable) and a fixed set of body sections (narrative). Category files in `categories/` curate views over the dataset files using wiki-style `[[links]]`. README is hand-maintained in v1.

**Tech Stack:** Markdown + YAML frontmatter, git. No code, no tooling, no tests in v1.

**Reference spec:** `docs/superpowers/specs/2026-05-14-datasets-index-design.md`

---

## Notes on TDD for this plan

This is a documentation repo, not a code repo. There are no unit tests. The "test" for each task is **visual verification**: open the file in a markdown previewer or `cat` it, confirm the frontmatter is valid YAML, confirm `[[wiki-links]]` point to files that exist (or to files this plan will create).

After every task, commit. Frequent commits matter even for docs — each dataset profile is independently useful.

---

## File Structure

```
Datasets/
├── .gitignore                                       # Task 1
├── README.md                                        # Task 2 (skeleton), Task 10 (quick-find table)
├── CONTRIBUTING.md                                  # Task 1
├── templates/
│   └── dataset-template.md                          # Task 1
├── datasets/
│   ├── neuropainting.md                             # Task 3
│   ├── rxrx1.md                                     # Task 3
│   ├── jump-cell-painting.md                        # Task 3
│   ├── tahoe-100m.md                                # Task 3
│   ├── psychencode.md                               # Task 4
│   ├── commonmind.md                                # Task 4
│   ├── gtex.md                                      # Task 4
│   ├── amp-ad.md                                    # Task 5
│   ├── adni.md                                      # Task 5
│   ├── sea-ad.md                                    # Task 5
│   ├── allen-brain-cell-atlas.md                    # Task 6
│   ├── hca.md                                       # Task 6
│   ├── encode.md                                    # Task 7
│   ├── uk-biobank.md                                # Task 8
│   └── openneuro.md                                 # Task 8
├── categories/
│   ├── neuro.md                                     # Task 9
│   ├── aging.md                                     # Task 9
│   ├── perturbation-imaging.md                      # Task 9
│   ├── single-cell.md                               # Task 9
│   └── foundation-model-candidates.md               # Task 9
└── docs/superpowers/{specs,plans}/                  # Already exists
```

---

## Task 1: Scaffold — `.gitignore`, `CONTRIBUTING.md`, `templates/dataset-template.md`

**Files:**
- Create: `.gitignore`
- Create: `CONTRIBUTING.md`
- Create: `templates/dataset-template.md`

- [ ] **Step 1: Write `.gitignore`**

Create `.gitignore` with this exact content:

```
.DS_Store
*.swp
*.swo
.idea/
.vscode/
__pycache__/
*.pyc
.env
```

- [ ] **Step 2: Write `templates/dataset-template.md`**

Create `templates/dataset-template.md` with this exact content:

```markdown
---
name: <Dataset full name>
aliases: [<short acronyms or alternate names>]
host: <Hosting organization or portal>
url: <Canonical landing URL>
access: <open | registered | controlled>
modalities: [<modality-1>, <modality-2>]
species: <human | mouse | multi | other>
tissue: [<tissue-1>, <tissue-2>]
conditions: [<condition-1>, <condition-2>]
n_subjects: <approximate count or range>
n_samples: <approximate count or range>
age_range: <e.g., fetal-to-adult | 55-95 | mixed>
scale_gb: <rough order of magnitude in GB>
license: <license name or DUA reference>
year: <YYYY or YYYY-ongoing>
tags: [<tag-1>, <tag-2>]
ai_relevance: [<use-case-1>, <use-case-2>]
compute_hint: <cpu | gpu-single | gpu-multi | cluster>
benchmark_splits: <true | false>
last_reviewed: <YYYY-MM-DD>
---

## Summary

<2-4 sentences. What is this dataset, who made it, what makes it distinctive.>

## Features

<Bulleted list of what's actually in the data: assays, dimensions, sample counts, key metadata, known caveats.>

## Potential AI use cases

- <Concrete model type or task this dataset could support>
- <Another use case>
- <Another use case>

## Access notes

<How to actually get the data: portal account, DUA process, expected wait, gotchas.>

## Notable papers

- <Citation 1>
- <Citation 2>

## Related

<Wiki-style links to other dataset files in this repo, e.g., [[psychencode]], [[commonmind]].>
```

- [ ] **Step 3: Write `CONTRIBUTING.md`**

Create `CONTRIBUTING.md` with this exact content:

```markdown
# Contributing to the Datasets Index

This repo is a curated index of public datasets relevant to training AI models, with a focus on **human, neurological, and aging biology**. Each dataset gets one markdown file in `datasets/` and shows up in the quick-find table in `README.md` and in any applicable category files under `categories/`.

## Adding a new dataset

1. **Copy the template.** `cp templates/dataset-template.md datasets/<slug>.md` where `<slug>` is kebab-case (e.g., `psychencode`, `amp-ad`, `uk-biobank`).
2. **Fill in the frontmatter.** Every field is required unless you genuinely don't know the value, in which case write `unknown` (not blank).
3. **Write the body.** Six sections in order: Summary, Features, Potential AI use cases, Access notes, Notable papers, Related.
4. **Update the README quick-find table** in `README.md`. Add one row for the new dataset.
5. **Update applicable category files.** Add a one-line bullet with a `[[wiki-link]]` and a hook describing why it belongs in that category.
6. **Commit.** One commit per dataset is ideal.

## Inclusion criteria

A dataset earns a profile if it meets all three:

1. **Accessible** — publicly available, even if behind a Data Use Agreement (DUA).
2. **Trainable** — plausibly usable for model training by a single researcher or small team.
3. **Relevant** — human / neuro / aging fit, OR strong methodological-transfer value to those domains.

## Frontmatter field reference

| Field | Type | Notes |
|---|---|---|
| `name` | string | Full canonical name. |
| `aliases` | list | Acronyms or alternate names. Empty list `[]` is fine. |
| `host` | string | Hosting organization or portal (e.g., "Synapse / AD Knowledge Portal"). |
| `url` | string | Canonical landing URL. |
| `access` | enum | `open` (free download), `registered` (account required), `controlled` (DUA/IRB). |
| `modalities` | list | E.g., `bulk-rna-seq`, `scRNA-seq`, `atac-seq`, `cell-painting`, `mri`, `wgs`, `gwas`. |
| `species` | string | Usually `human`. |
| `tissue` | list | E.g., `prefrontal-cortex`, `whole-brain`, `blood`, `multi`. |
| `conditions` | list | Disease focus, e.g., `alzheimers`, `schizophrenia`, `control`. |
| `n_subjects` | string | Approximate count (`~2700`) or range. |
| `n_samples` | string | Approximate count, may differ from subjects. |
| `age_range` | string | E.g., `55-95`, `fetal-to-adult`, `mixed`. |
| `scale_gb` | number | Rough order-of-magnitude in GB. |
| `license` | string | License name or DUA reference. |
| `year` | string | `YYYY` or `YYYY-ongoing`. |
| `tags` | list | Free-form short tags. |
| `ai_relevance` | list | High-level AI use case tags: `foundation-model`, `disease-classification`, `multimodal`, `regulatory-genomics`, `morphological-profiling`, etc. |
| `compute_hint` | enum | `cpu`, `gpu-single`, `gpu-multi`, `cluster`. Rough hint for training feasibility. |
| `benchmark_splits` | bool | Does the dataset come with canonical train/val/test splits? |
| `last_reviewed` | date | `YYYY-MM-DD`. Update when you verify the entry. |

## Categories

A dataset can appear in multiple category files. Categories are curated lenses, not strict taxonomies. Add a dataset to a category file if a reader looking for that lens would want to find it.

Current categories:
- `neuro` — brain tissue or neuropsychiatric.
- `aging` — age-range coverage relevant to aging biology.
- `perturbation-imaging` — cell-painting and morphological profiling.
- `single-cell` — scRNA-seq, snRNA-seq, multiome.
- `foundation-model-candidates` — large/diverse enough to pretrain on.
```

- [ ] **Step 4: Verify the three files exist and look right**

Run: `ls -la .gitignore CONTRIBUTING.md templates/dataset-template.md`
Expected: All three files listed, none empty.

Open `templates/dataset-template.md` in a preview and confirm the YAML frontmatter renders as a code block, not as actual frontmatter (the file itself is a template).

- [ ] **Step 5: Commit**

```bash
git add .gitignore CONTRIBUTING.md templates/dataset-template.md
git commit -m "Add gitignore, CONTRIBUTING guide, and dataset template"
```

---

## Task 2: README skeleton (without quick-find table)

**Files:**
- Create: `README.md`

- [ ] **Step 1: Write the README skeleton**

Create `README.md` with this exact content. The quick-find table at the bottom is a placeholder header — we'll populate it in Task 10 once all dataset files exist.

```markdown
# Datasets

A curated, evergreen index of public datasets relevant to training AI models, with a focus on **human, neurological, and aging biology**.

This is an **index, not a mirror**. It tracks where datasets live, how to access them, what they contain, and what they might be useful for. It does not host data.

## How this repo is organized

- **`datasets/`** — one markdown file per dataset. Source of truth. Each file has YAML frontmatter (filterable) and a fixed set of body sections (narrative).
- **`categories/`** — curated lenses over the datasets (neuro, aging, perturbation imaging, single-cell, foundation-model candidates). A dataset can appear in multiple categories.
- **`templates/dataset-template.md`** — the canonical schema for a dataset entry.
- **`CONTRIBUTING.md`** — how to add a dataset, plus the frontmatter field reference.

## Categories

- [Neuro](categories/neuro.md) — brain tissue and neuropsychiatric datasets.
- [Aging](categories/aging.md) — datasets with age-range coverage relevant to aging biology.
- [Perturbation imaging](categories/perturbation-imaging.md) — cell-painting and morphological profiling.
- [Single-cell](categories/single-cell.md) — scRNA-seq, snRNA-seq, multiome.
- [Foundation-model candidates](categories/foundation-model-candidates.md) — large/diverse enough to pretrain on.

## Status legend

| Field | Values |
|---|---|
| `access` | `open` — free download · `registered` — account needed · `controlled` — DUA or IRB required |
| `compute_hint` | `cpu` · `gpu-single` · `gpu-multi` · `cluster` |
| `benchmark_splits` | `true` if the dataset ships canonical train/val/test splits |

## Quick-find table

<!-- Populated in Task 10 of the scaffold plan. -->

## Adding a dataset

See [CONTRIBUTING.md](CONTRIBUTING.md).
```

- [ ] **Step 2: Commit**

```bash
git add README.md
git commit -m "Add README skeleton with category links and status legend"
```

---

## Task 3: Perturbation imaging datasets — Neuropainting, RxRx1, JUMP, Tahoe-100M

**Files:**
- Create: `datasets/neuropainting.md`
- Create: `datasets/rxrx1.md`
- Create: `datasets/jump-cell-painting.md`
- Create: `datasets/tahoe-100m.md`

For each dataset below, create the file with the specified frontmatter and a body that follows the template's six sections. Frontmatter is fully specified; body sections have concrete bullet outlines that the engineer (or subagent) fills in using public knowledge. If a fact isn't known, write `unknown` rather than guessing.

- [ ] **Step 1: Create `datasets/neuropainting.md`**

```yaml
---
name: Neuropainting
aliases: []
host: Recursion / Allen Institute collaboration
url: https://www.rxrx.ai/neuropainting
access: open
modalities: [cell-painting, fluorescence-microscopy]
species: human
tissue: [ipsc-derived-neurons]
conditions: [genetic-perturbation, control]
n_subjects: unknown
n_samples: ~1000000
age_range: cell-line
scale_gb: ~2000
license: CC BY 4.0
year: 2024-ongoing
tags: [neuro, perturbation, imaging, morphological-profiling, ipsc]
ai_relevance: [foundation-model, morphological-profiling, perturbation-response, contrastive-learning]
compute_hint: gpu-multi
benchmark_splits: false
last_reviewed: 2026-05-14
---
```

Body sections to write:

- **Summary** — Neuropainting is a Cell Painting-style morphological imaging dataset focused on iPSC-derived neurons under genetic perturbation. Released by Recursion in collaboration with the Allen Institute. Notable for bringing the Cell Painting paradigm into a neural-cell context, where most large morphological datasets historically used U2OS or A549.
- **Features** — Multi-channel fluorescence microscopy across organelle stains; perturbations across a large library of gene knockouts/knockdowns; CellProfiler or DINO-style embeddings often used downstream.
- **Potential AI use cases** — pretraining vision foundation models on neural morphology; learning perturbation-response embeddings; transfer learning to disease-relevant phenotypes; contrastive learning across perturbation classes.
- **Access notes** — open download via Recursion's rxrx.ai portal.
- **Notable papers** — Recursion Neuropainting white paper / preprint (look up specific citation).
- **Related** — `[[rxrx1]]`, `[[jump-cell-painting]]`.

- [ ] **Step 2: Create `datasets/rxrx1.md`**

```yaml
---
name: RxRx1
aliases: [RxRx1]
host: Recursion
url: https://www.rxrx.ai/rxrx1
access: open
modalities: [cell-painting, fluorescence-microscopy]
species: human
tissue: [hepg2, huvec, rpe, u2os]
conditions: [siRNA-perturbation, control]
n_subjects: unknown
n_samples: ~125000
age_range: cell-line
scale_gb: ~50
license: CC BY-NC 4.0
year: 2019
tags: [perturbation, imaging, morphological-profiling, benchmark]
ai_relevance: [foundation-model, morphological-profiling, batch-effect, classification]
compute_hint: gpu-single
benchmark_splits: true
last_reviewed: 2026-05-14
---
```

Body sections to write:

- **Summary** — Recursion's first public Cell Painting benchmark dataset. Designed around the batch-effects problem: identical experiments performed across many imaging batches, with ground-truth siRNA labels.
- **Features** — 6-channel fluorescence microscopy; 4 cell types; 1138 siRNAs across 51 experiments; canonical Kaggle competition splits.
- **Potential AI use cases** — pretraining; benchmarking domain-adaptation methods (batch effect correction); classification baselines; transfer learning to RxRx2/3/19 and JUMP.
- **Access notes** — open S3 download via rxrx.ai. Includes raw TIFFs and CellProfiler features.
- **Notable papers** — Sypetkowski et al., 2023 (RxRx1 benchmark paper); follow-up work on RxRx2/3.
- **Related** — `[[neuropainting]]`, `[[jump-cell-painting]]`. Cross-reference RxRx2 (CRISPR), RxRx3 (compound), RxRx19 (COVID) in the body even though they don't have their own files yet.

- [ ] **Step 3: Create `datasets/jump-cell-painting.md`**

```yaml
---
name: JUMP Cell Painting Consortium
aliases: [JUMP-CP, JUMP]
host: Broad Institute / JUMP-CP Consortium
url: https://jump-cellpainting.broadinstitute.org/
access: open
modalities: [cell-painting, fluorescence-microscopy]
species: human
tissue: [u2os, a549]
conditions: [compound-perturbation, crispr-perturbation, orf-overexpression, control]
n_subjects: unknown
n_samples: ~3000000
age_range: cell-line
scale_gb: ~115000
license: CC0
year: 2023
tags: [perturbation, imaging, morphological-profiling, multi-modal-perturbation]
ai_relevance: [foundation-model, morphological-profiling, perturbation-response, multimodal, drug-discovery]
compute_hint: cluster
benchmark_splits: false
last_reviewed: 2026-05-14
---
```

Body sections to write:

- **Summary** — Industry-academic consortium producing the largest open Cell Painting dataset to date. Spans chemical, CRISPR, and ORF perturbations on a common cell line, enabling cross-perturbation-modality learning.
- **Features** — ~3M images at 5-channel Cell Painting; ~120k compounds, ~15k CRISPR guides, ~12k ORFs; metadata-rich; CellProfiler features and DINO embeddings available.
- **Potential AI use cases** — large-scale pretraining; learning a shared embedding across perturbation modalities; in-silico screening; drug repurposing.
- **Access notes** — open download via AWS S3 (Registry of Open Data). CellProfiler features are much smaller (~1TB) than raw images.
- **Notable papers** — Chandrasekaran et al., 2023 (JUMP-CP overview).
- **Related** — `[[rxrx1]]`, `[[neuropainting]]`.

- [ ] **Step 4: Create `datasets/tahoe-100m.md`**

```yaml
---
name: Tahoe-100M
aliases: []
host: Vevo Therapeutics
url: https://www.vevotx.com/tahoe-100m
access: open
modalities: [scRNA-seq, compound-perturbation]
species: human
tissue: [multi-cancer-cell-lines]
conditions: [compound-perturbation, control]
n_subjects: unknown
n_samples: ~100000000
age_range: cell-line
scale_gb: ~500
license: CC BY 4.0
year: 2025
tags: [perturbation, single-cell, drug-discovery, foundation-model]
ai_relevance: [foundation-model, perturbation-response, drug-response, virtual-cell]
compute_hint: gpu-multi
benchmark_splits: false
last_reviewed: 2026-05-14
---
```

Body sections to write:

- **Summary** — Largest open single-cell perturbation atlas to date. 100M cells across ~50 cancer cell lines treated with ~1000 compounds. Released by Vevo Therapeutics as a substrate for virtual-cell foundation models.
- **Features** — scRNA-seq read counts; compound treatment metadata; cell-line identity; batch metadata; suitable for cross-cell-line generalization studies.
- **Potential AI use cases** — pretraining scRNA-seq foundation models with perturbation context; learning compound-response embeddings; virtual cell modeling; transfer to disease cohorts.
- **Access notes** — open download via Hugging Face / partner mirrors.
- **Notable papers** — Tahoe-100M preprint (2025) — look up exact citation.
- **Related** — `[[jump-cell-painting]]`, `[[hca]]`.

- [ ] **Step 5: Verify all four files exist**

Run: `ls datasets/`
Expected: `neuropainting.md jump-cell-painting.md rxrx1.md tahoe-100m.md`

For each file, confirm the YAML frontmatter parses (no unquoted special characters in values). Quick sanity check: `head -25 datasets/neuropainting.md` should show the closing `---` on a line by itself.

- [ ] **Step 6: Commit**

```bash
git add datasets/neuropainting.md datasets/rxrx1.md datasets/jump-cell-painting.md datasets/tahoe-100m.md
git commit -m "Add perturbation imaging dataset profiles (Neuropainting, RxRx1, JUMP-CP, Tahoe-100M)"
```

---

## Task 4: Brain bulk transcriptomics — psychENCODE, CommonMind, GTEx

**Files:**
- Create: `datasets/psychencode.md`
- Create: `datasets/commonmind.md`
- Create: `datasets/gtex.md`

- [ ] **Step 1: Create `datasets/psychencode.md`**

```yaml
---
name: psychENCODE
aliases: [PEC]
host: Synapse / PsychENCODE Knowledge Portal
url: https://psychencode.synapse.org
access: controlled
modalities: [bulk-rna-seq, scRNA-seq, atac-seq, chip-seq, methylation, wgs, genotype]
species: human
tissue: [prefrontal-cortex, multiple-brain-regions]
conditions: [schizophrenia, bipolar, autism, control]
n_subjects: ~2700
n_samples: ~15000
age_range: fetal-to-adult
scale_gb: ~50000
license: PsychENCODE DUA
year: 2015-ongoing
tags: [neuro, psychiatric, multi-omic, developmental]
ai_relevance: [foundation-model, regulatory-genomics, disease-classification, multimodal]
compute_hint: gpu-multi
benchmark_splits: false
last_reviewed: 2026-05-14
---
```

Body sections:

- **Summary** — NIH-funded consortium generating multi-omic data on the genomic regulation of the human brain in psychiatric disease. Covers developmental and adult brain across schizophrenia, bipolar, autism, and controls. PEC2 expanded into single-cell.
- **Features** — Bulk RNA-seq, scRNA-seq, ATAC-seq, ChIP-seq, methylation, WGS; donor-level genotype; rich clinical metadata; multiple brain regions.
- **Potential AI use cases** — multi-omic foundation model pretraining; learning regulatory grammars in disease vs control; integrative case/control classification; developmental trajectory modeling.
- **Access notes** — Synapse account required, plus PEC DUA approval (institutional sign-off). Expect 2-6 week turnaround.
- **Notable papers** — Akbarian et al., 2015 (consortium launch); Gandal et al., 2018; PEC2 capstone papers.
- **Related** — `[[commonmind]]`, `[[encode]]`, `[[gtex]]`, `[[amp-ad]]`.

- [ ] **Step 2: Create `datasets/commonmind.md`**

```yaml
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
```

Body sections:

- **Summary** — Postmortem brain consortium focused on schizophrenia and bipolar disorder. Bulk RNA-seq and matched genotype on DLPFC and ACC from ~1000 donors. Frequent partner dataset to psychENCODE; CMC data is included in many PEC analyses.
- **Features** — Bulk RNA-seq, ATAC-seq, methylation, WGS; eQTL maps; high-quality clinical phenotyping.
- **Potential AI use cases** — eQTL/regulatory-variant prediction; case/control classification; pretraining on bulk transcriptome.
- **Access notes** — Synapse + CMC DUA. Approval typically 2-4 weeks.
- **Notable papers** — Fromer et al., 2016 (Nature Neuroscience).
- **Related** — `[[psychencode]]`, `[[gtex]]`, `[[amp-ad]]`.

- [ ] **Step 3: Create `datasets/gtex.md`**

```yaml
---
name: Genotype-Tissue Expression Project
aliases: [GTEx]
host: NHGRI / GTEx Portal
url: https://gtexportal.org/
access: registered
modalities: [bulk-rna-seq, wgs, genotype]
species: human
tissue: [multi-tissue, 13-brain-regions, blood, muscle, skin, other]
conditions: [control]
n_subjects: ~980
n_samples: ~17000
age_range: 20-70
scale_gb: ~5000
license: GTEx DUA (open summary, controlled raw)
year: 2017
tags: [reference, multi-tissue, eQTL, regulatory-genomics]
ai_relevance: [foundation-model, regulatory-genomics, multitissue, eQTL]
compute_hint: gpu-single
benchmark_splits: false
last_reviewed: 2026-05-14
---
```

Body sections:

- **Summary** — Reference dataset of human gene expression across 54 tissues, including 13 brain regions, from ~980 deceased donors with matched WGS. Foundational for tissue-specific eQTL and as a transcriptome reference.
- **Features** — Bulk RNA-seq across many tissues per donor; WGS; rich tissue metadata; eQTL and sQTL releases at multiple resolutions; v8 is current canonical release.
- **Potential AI use cases** — multi-tissue foundation model pretraining; tissue-specificity prediction; reference baseline for disease-cohort transcriptomes; eQTL prediction.
- **Access notes** — Summary statistics open. Subject-level raw data is controlled via dbGaP DUA. Expect 4-8 weeks for dbGaP.
- **Notable papers** — GTEx Consortium, 2020 (Science).
- **Related** — `[[psychencode]]`, `[[commonmind]]`, `[[encode]]`.

- [ ] **Step 4: Verify and commit**

Run: `ls datasets/psychencode.md datasets/commonmind.md datasets/gtex.md`
Expected: All three files listed.

```bash
git add datasets/psychencode.md datasets/commonmind.md datasets/gtex.md
git commit -m "Add brain bulk transcriptomics dataset profiles (psychENCODE, CommonMind, GTEx)"
```

---

## Task 5: AD / aging cohorts — AMP-AD, ADNI, SEA-AD

**Files:**
- Create: `datasets/amp-ad.md`
- Create: `datasets/adni.md`
- Create: `datasets/sea-ad.md`

- [ ] **Step 1: Create `datasets/amp-ad.md`**

```yaml
---
name: Accelerating Medicines Partnership — Alzheimer's Disease
aliases: [AMP-AD]
host: Synapse / AD Knowledge Portal
url: https://adknowledgeportal.synapse.org/
access: controlled
modalities: [bulk-rna-seq, scRNA-seq, proteomics, methylation, atac-seq, wgs, gwas, clinical]
species: human
tissue: [multiple-brain-regions, blood, csf]
conditions: [alzheimers, mild-cognitive-impairment, control]
n_subjects: ~5000
n_samples: ~50000
age_range: 60-100
scale_gb: ~30000
license: AD Knowledge Portal DUA (per study)
year: 2014-ongoing
tags: [aging, alzheimers, multi-omic, longitudinal, umbrella]
ai_relevance: [disease-classification, multi-omic, aging-trajectory, multimodal]
compute_hint: gpu-multi
benchmark_splits: false
last_reviewed: 2026-05-14
---
```

Body sections:

- **Summary** — NIH/industry umbrella program aggregating multi-omic data across Alzheimer's disease cohorts. Hosts the three classical postmortem cohorts (ROSMAP, MSBB, Mayo) plus newer additions. The AD Knowledge Portal is the unified access point.
- **Features** — Per-study: bulk and single-cell RNA-seq, proteomics, methylation, ATAC-seq, WGS, GWAS, clinical, neuropath. ROSMAP adds longitudinal cognition; MSBB adds Mount Sinai brain bank breadth; Mayo adds aging controls.
- **Potential AI use cases** — multi-omic disease classification; aging trajectory modeling; foundation-model pretraining on aging brain; biomarker discovery; cross-cohort generalization.
- **Access notes** — Synapse account + study-specific DUA. Several DUAs available simultaneously. Plan for 4-8 weeks total.
- **Notable papers** — Bennett et al., 2018 (ROSMAP); Wang et al., 2018 (MSBB); Allen et al., 2016 (Mayo). Capstone integrative papers from 2020-onward.
- **Related** — `[[adni]]`, `[[sea-ad]]`, `[[psychencode]]`, `[[uk-biobank]]`.

- [ ] **Step 2: Create `datasets/adni.md`**

```yaml
---
name: Alzheimer's Disease Neuroimaging Initiative
aliases: [ADNI]
host: USC LONI / ADNI
url: https://adni.loni.usc.edu/
access: controlled
modalities: [mri, pet, csf-biomarkers, clinical, genotype]
species: human
tissue: [whole-brain, csf]
conditions: [alzheimers, mild-cognitive-impairment, control]
n_subjects: ~2300
n_samples: ~15000
age_range: 55-90
scale_gb: ~5000
license: ADNI DUA
year: 2004-ongoing
tags: [aging, alzheimers, imaging, longitudinal, biomarker]
ai_relevance: [disease-classification, longitudinal, imaging-foundation-model, biomarker]
compute_hint: gpu-multi
benchmark_splits: false
last_reviewed: 2026-05-14
---
```

Body sections:

- **Summary** — Longitudinal neuroimaging study of AD progression. Structural and functional MRI, amyloid and tau PET, CSF biomarkers, cognitive testing, and genotype across thousands of subjects with serial visits. The reference dataset for AD biomarker work.
- **Features** — T1, T2, FLAIR, DTI, fMRI; amyloid (florbetapir, florbetaben) and tau PET; CSF Aβ/tau/p-tau; cognitive scores; APOE genotype.
- **Potential AI use cases** — imaging foundation models for brain; AD classification and progression prediction; multimodal MRI+PET+CSF fusion; longitudinal trajectory modeling.
- **Access notes** — ADNI DUA via LONI. Usually approved within 1-2 weeks. Download via LONI IDA.
- **Notable papers** — Petersen et al., 2010; Weiner et al., 2017.
- **Related** — `[[amp-ad]]`, `[[sea-ad]]`, `[[openneuro]]`.

- [ ] **Step 3: Create `datasets/sea-ad.md`**

```yaml
---
name: Seattle Alzheimer's Disease Brain Cell Atlas
aliases: [SEA-AD]
host: Allen Institute / SEA-AD Portal
url: https://portal.brain-map.org/explore/seattle-alzheimers-disease
access: open
modalities: [scRNA-seq, snRNA-seq, mfish, histology, clinical]
species: human
tissue: [middle-temporal-gyrus, dlpfc]
conditions: [alzheimers, control]
n_subjects: ~84
n_samples: ~1500000
age_range: 65-100
scale_gb: ~500
license: CC BY 4.0
year: 2023-ongoing
tags: [aging, alzheimers, single-cell, atlas]
ai_relevance: [single-cell-foundation-model, disease-classification, cell-type-annotation]
compute_hint: gpu-single
benchmark_splits: false
last_reviewed: 2026-05-14
---
```

Body sections:

- **Summary** — Allen Institute single-cell atlas of AD-affected vs control human cortex. Deep cell-type resolution combined with continuous AD neuropathological scoring, enabling cell-type-specific disease trajectory analysis.
- **Features** — snRNA-seq at ~1.5M nuclei; MERFISH spatial transcriptomics; matched histology; donor-level neuropathological staging.
- **Potential AI use cases** — single-cell foundation model fine-tuning to AD; cell-type-specific disease modeling; spatial transcriptomics + scRNA integration; disease-stage prediction.
- **Access notes** — open download via the Allen Brain Map portal. No DUA.
- **Notable papers** — Gabitto et al., 2024 (Nature Neuroscience).
- **Related** — `[[allen-brain-cell-atlas]]`, `[[amp-ad]]`, `[[hca]]`.

- [ ] **Step 4: Verify and commit**

```bash
git add datasets/amp-ad.md datasets/adni.md datasets/sea-ad.md
git commit -m "Add AD/aging cohort profiles (AMP-AD, ADNI, SEA-AD)"
```

---

## Task 6: Single-cell atlases — Allen Brain Cell Atlas, HCA

**Files:**
- Create: `datasets/allen-brain-cell-atlas.md`
- Create: `datasets/hca.md`

- [ ] **Step 1: Create `datasets/allen-brain-cell-atlas.md`**

```yaml
---
name: Allen Brain Cell Atlas
aliases: [ABC Atlas]
host: Allen Institute
url: https://portal.brain-map.org/atlases-and-data/bkp/abc-atlas
access: open
modalities: [scRNA-seq, snRNA-seq, merfish, atac-seq]
species: [human, mouse]
tissue: [whole-brain]
conditions: [control]
n_subjects: unknown
n_samples: ~32000000
age_range: adult
scale_gb: ~3000
license: CC BY 4.0
year: 2023-ongoing
tags: [neuro, single-cell, atlas, reference, spatial]
ai_relevance: [single-cell-foundation-model, cell-type-annotation, spatial-transcriptomics]
compute_hint: gpu-multi
benchmark_splits: false
last_reviewed: 2026-05-14
---
```

Body sections:

- **Summary** — Allen Institute's comprehensive cellular atlas of the mouse and human brain. Combines scRNA-seq, snRNA-seq, MERFISH spatial transcriptomics, and snATAC-seq across whole brain. The current reference for brain cell-type taxonomy.
- **Features** — ~32M cells/nuclei across modalities; whole-brain coverage; hierarchical cell-type taxonomy; spatial coordinates for MERFISH subset.
- **Potential AI use cases** — pretraining scRNA-seq foundation models with brain bias; cell-type annotation transfer; spatial-transcriptomics modeling; cross-species brain mapping.
- **Access notes** — open download via Allen Brain Map. CellxGene mirrors available for many subsets.
- **Notable papers** — Yao et al., 2023 (Nature mouse atlas); Siletti et al., 2023 (Science human atlas).
- **Related** — `[[sea-ad]]`, `[[hca]]`, `[[psychencode]]`.

- [ ] **Step 2: Create `datasets/hca.md`**

```yaml
---
name: Human Cell Atlas
aliases: [HCA]
host: Chan Zuckerberg Initiative / HCA Data Portal
url: https://data.humancellatlas.org/
access: open
modalities: [scRNA-seq, snRNA-seq, spatial-transcriptomics, atac-seq]
species: human
tissue: [multi-tissue, whole-body]
conditions: [control, developmental, multiple-conditions]
n_subjects: ~10000
n_samples: ~50000000
age_range: fetal-to-adult
scale_gb: ~15000
license: per-project (mostly open)
year: 2017-ongoing
tags: [reference, single-cell, atlas, multi-tissue, developmental]
ai_relevance: [foundation-model, single-cell-foundation-model, cell-type-annotation, cross-tissue]
compute_hint: gpu-multi
benchmark_splits: false
last_reviewed: 2026-05-14
---
```

Body sections:

- **Summary** — International effort to map every cell type in the human body. The HCA Data Portal aggregates curated, harmonized single-cell datasets across tissues, donors, and conditions. CZ CELLxGENE provides additional curation and a query interface.
- **Features** — Curated, harmonized scRNA-seq with standardized cell-type ontologies; spans developmental stages and ~50 tissues; includes both atlas-grade and disease-focused submissions.
- **Potential AI use cases** — pretraining single-cell foundation models (e.g., scGPT, Geneformer); cell-type annotation models; cross-tissue transfer learning; developmental trajectory modeling.
- **Access notes** — open download. CZ CELLxGENE Census provides an indexed API.
- **Notable papers** — Regev et al., 2017 (HCA vision paper); Tabula Sapiens, 2022; CELLxGENE Census, 2023.
- **Related** — `[[allen-brain-cell-atlas]]`, `[[gtex]]`, `[[tahoe-100m]]`.

- [ ] **Step 3: Verify and commit**

```bash
git add datasets/allen-brain-cell-atlas.md datasets/hca.md
git commit -m "Add single-cell atlas profiles (Allen Brain Cell Atlas, HCA)"
```

---

## Task 7: Regulatory genomics — ENCODE

**Files:**
- Create: `datasets/encode.md`

- [ ] **Step 1: Create `datasets/encode.md`**

```yaml
---
name: Encyclopedia of DNA Elements
aliases: [ENCODE]
host: ENCODE Data Coordination Center / Stanford
url: https://www.encodeproject.org/
access: open
modalities: [chip-seq, atac-seq, dnase-seq, rna-seq, methylation, hi-c]
species: [human, mouse]
tissue: [multi-tissue, multi-cell-line]
conditions: [control]
n_subjects: unknown
n_samples: ~25000
age_range: mixed
scale_gb: ~500000
license: CC0
year: 2003-ongoing
tags: [reference, regulatory-genomics, multi-modal, epigenome]
ai_relevance: [foundation-model, regulatory-genomics, sequence-models, multimodal]
compute_hint: cluster
benchmark_splits: false
last_reviewed: 2026-05-14
---
```

Body sections:

- **Summary** — Foundational NIH consortium mapping functional elements in the human and mouse genome. ChIP-seq, ATAC-seq, DNase-seq, RNA-seq, methylation, and Hi-C across hundreds of biosamples. Underpins essentially all modern regulatory-genomics models.
- **Features** — ~25k experiments spanning 100+ cell lines and tissues; uniform processing pipelines; rich biosample ontology; ENCODE 4 added single-cell and long-read modalities.
- **Potential AI use cases** — pretraining sequence foundation models (Enformer, Borzoi, scBasset lineage); cell-type-specific TF binding prediction; chromatin accessibility prediction; multimodal regulatory grammars.
- **Access notes** — open download via encodeproject.org. Bulk metadata API available.
- **Notable papers** — ENCODE Consortium, 2012 (Nature); ENCODE 3/4 capstone papers, 2020.
- **Related** — `[[psychencode]]`, `[[gtex]]`.

- [ ] **Step 2: Verify and commit**

```bash
git add datasets/encode.md
git commit -m "Add ENCODE regulatory genomics profile"
```

---

## Task 8: Population and imaging cohorts — UK Biobank, OpenNeuro

**Files:**
- Create: `datasets/uk-biobank.md`
- Create: `datasets/openneuro.md`

- [ ] **Step 1: Create `datasets/uk-biobank.md`**

```yaml
---
name: UK Biobank
aliases: [UKB]
host: UK Biobank
url: https://www.ukbiobank.ac.uk/
access: controlled
modalities: [gwas, wgs, exome, mri, dxa, clinical, proteomics, metabolomics, ehr]
species: human
tissue: [whole-body, brain, retina, blood]
conditions: [population-cohort, multiple-conditions]
n_subjects: ~500000
n_samples: ~500000
age_range: 40-73
scale_gb: ~2000000
license: UK Biobank Access (paid)
year: 2006-ongoing
tags: [aging, population, multi-omic, imaging, longitudinal]
ai_relevance: [foundation-model, aging-trajectory, disease-risk, multimodal, imaging]
compute_hint: cluster
benchmark_splits: false
last_reviewed: 2026-05-14
---
```

Body sections:

- **Summary** — Half-million-person UK population cohort with deep phenotyping: genetics, brain/cardiac/abdominal MRI, retinal imaging, blood biomarkers, proteomics, metabolomics, and linked EHR/death records. The single largest open-by-application multimodal human dataset.
- **Features** — WGS for full cohort; brain MRI on ~100k subjects (largest such dataset publicly available); Olink proteomics on ~50k subjects; longitudinal EHR; aging-relevant given enrollment age range.
- **Potential AI use cases** — biological-age estimation; multimodal foundation models on human; disease-risk prediction; brain-MRI foundation models; aging-trajectory modeling.
- **Access notes** — formal application process; access fee; approval takes 2-6 months. Data accessed via UKB RAP (DNAnexus) cloud platform.
- **Notable papers** — Sudlow et al., 2015; Bycroft et al., 2018; Littlejohns et al., 2020 (imaging extension).
- **Related** — `[[adni]]`, `[[amp-ad]]`, `[[gtex]]`.

- [ ] **Step 2: Create `datasets/openneuro.md`**

```yaml
---
name: OpenNeuro
aliases: []
host: Stanford / OpenNeuro
url: https://openneuro.org/
access: open
modalities: [mri, fmri, eeg, meg, ieeg, pet]
species: human
tissue: [whole-brain]
conditions: [multiple-conditions, control]
n_subjects: ~100000
n_samples: ~1000-studies
age_range: mixed
scale_gb: ~200000
license: CC0 (typical, per-dataset)
year: 2017-ongoing
tags: [neuro, imaging, multimodal, aggregator]
ai_relevance: [foundation-model, imaging, brain-decoding, multimodal]
compute_hint: gpu-multi
benchmark_splits: false
last_reviewed: 2026-05-14
---
```

Body sections:

- **Summary** — Open aggregator of BIDS-formatted human neuroimaging datasets. Hosts >1000 studies spanning MRI, fMRI, EEG, MEG, iEEG, and PET. The de facto standard archive for sharing neuroimaging data.
- **Features** — BIDS-standardized; metadata-rich; large aggregate diversity of paradigms, populations, scanners; easy to combine across studies.
- **Potential AI use cases** — pretraining neuroimaging foundation models; brain-state decoding; multimodal (EEG+fMRI) alignment; cross-cohort transfer learning.
- **Access notes** — open download via openneuro.org or S3. CLI (`openneuro-cli`) available.
- **Notable papers** — Markiewicz et al., 2021 (eLife).
- **Related** — `[[adni]]`, `[[uk-biobank]]`.

- [ ] **Step 3: Verify and commit**

```bash
git add datasets/uk-biobank.md datasets/openneuro.md
git commit -m "Add population and imaging cohort profiles (UK Biobank, OpenNeuro)"
```

---

## Task 9: Category files

**Files:**
- Create: `categories/neuro.md`
- Create: `categories/aging.md`
- Create: `categories/perturbation-imaging.md`
- Create: `categories/single-cell.md`
- Create: `categories/foundation-model-candidates.md`

Each category file follows the same shape: a one-paragraph definition of the lens, then a bulleted list of dataset references using wiki-style links plus a one-line hook. Use relative markdown links `[name](../datasets/<slug>.md)` next to the `[[wiki-link]]` reference so GitHub rendering also works.

- [ ] **Step 1: Create `categories/neuro.md`**

```markdown
# Neuro

Datasets covering brain tissue, neural cells, neuropsychiatric conditions, or neuroimaging.

## Datasets

- [[neuropainting]] · [neuropainting](../datasets/neuropainting.md) — Cell Painting on iPSC-derived neurons with genetic perturbation.
- [[psychencode]] · [psychencode](../datasets/psychencode.md) — Multi-omic brain consortium across schizophrenia, bipolar, autism, controls.
- [[commonmind]] · [commonmind](../datasets/commonmind.md) — Postmortem DLPFC/ACC transcriptomics with matched genotype.
- [[amp-ad]] · [amp-ad](../datasets/amp-ad.md) — AD multi-omic umbrella (ROSMAP, MSBB, Mayo).
- [[adni]] · [adni](../datasets/adni.md) — Longitudinal AD neuroimaging and CSF biomarkers.
- [[sea-ad]] · [sea-ad](../datasets/sea-ad.md) — Single-cell AD cortex atlas with neuropath staging.
- [[allen-brain-cell-atlas]] · [allen-brain-cell-atlas](../datasets/allen-brain-cell-atlas.md) — Whole-brain single-cell + spatial reference for human and mouse.
- [[openneuro]] · [openneuro](../datasets/openneuro.md) — Open aggregator of BIDS-formatted human neuroimaging studies.
- [[uk-biobank]] · [uk-biobank](../datasets/uk-biobank.md) — Brain MRI on ~100k subjects (aging-relevant slice).
```

- [ ] **Step 2: Create `categories/aging.md`**

```markdown
# Aging

Datasets with age-range coverage relevant to aging biology — late-life cohorts, longitudinal designs, or age-stratified atlases.

## Datasets

- [[amp-ad]] · [amp-ad](../datasets/amp-ad.md) — Multi-omic AD across ages 60-100.
- [[adni]] · [adni](../datasets/adni.md) — Longitudinal AD progression, 55-90.
- [[sea-ad]] · [sea-ad](../datasets/sea-ad.md) — AD-affected vs control cortex, 65-100.
- [[uk-biobank]] · [uk-biobank](../datasets/uk-biobank.md) — Half-million-person cohort, 40-73, with longitudinal EHR.
- [[gtex]] · [gtex](../datasets/gtex.md) — Multi-tissue transcriptome across 20-70.
- [[psychencode]] · [psychencode](../datasets/psychencode.md) — Fetal-to-adult brain (covers developmental aging).
```

- [ ] **Step 3: Create `categories/perturbation-imaging.md`**

```markdown
# Perturbation imaging

Cell Painting and morphological-profiling datasets where cells are imaged under genetic or chemical perturbations.

## Datasets

- [[jump-cell-painting]] · [jump-cell-painting](../datasets/jump-cell-painting.md) — Largest open Cell Painting dataset, spanning compound, CRISPR, and ORF perturbations.
- [[rxrx1]] · [rxrx1](../datasets/rxrx1.md) — Recursion's siRNA-perturbation benchmark with canonical splits.
- [[neuropainting]] · [neuropainting](../datasets/neuropainting.md) — Cell Painting in iPSC-derived neurons.
- [[tahoe-100m]] · [tahoe-100m](../datasets/tahoe-100m.md) — Single-cell transcriptomic analogue (compound perturbation at 100M scale).
```

- [ ] **Step 4: Create `categories/single-cell.md`**

```markdown
# Single-cell

scRNA-seq, snRNA-seq, multiome, and spatial transcriptomic datasets.

## Datasets

- [[hca]] · [hca](../datasets/hca.md) — Curated, harmonized cross-tissue single-cell atlas.
- [[allen-brain-cell-atlas]] · [allen-brain-cell-atlas](../datasets/allen-brain-cell-atlas.md) — Whole-brain single-cell + MERFISH spatial.
- [[sea-ad]] · [sea-ad](../datasets/sea-ad.md) — AD-affected cortex at single-cell resolution.
- [[tahoe-100m]] · [tahoe-100m](../datasets/tahoe-100m.md) — 100M cells under compound perturbation.
- [[psychencode]] · [psychencode](../datasets/psychencode.md) — Single-cell components in PEC2.
- [[amp-ad]] · [amp-ad](../datasets/amp-ad.md) — Single-cell sub-studies within ROSMAP and others.
```

- [ ] **Step 5: Create `categories/foundation-model-candidates.md`**

```markdown
# Foundation-model candidates

Datasets large or diverse enough to plausibly pretrain a foundation model on, either on their own or as a major component of a pretraining mix.

## Datasets

- [[jump-cell-painting]] · [jump-cell-painting](../datasets/jump-cell-painting.md) — ~3M Cell Painting images, multi-perturbation-modality. Imaging foundation model substrate.
- [[tahoe-100m]] · [tahoe-100m](../datasets/tahoe-100m.md) — 100M single-cell transcriptomes with perturbation context.
- [[hca]] · [hca](../datasets/hca.md) — ~50M curated single-cell transcriptomes across tissues.
- [[allen-brain-cell-atlas]] · [allen-brain-cell-atlas](../datasets/allen-brain-cell-atlas.md) — Whole-brain single-cell at ~32M cells.
- [[encode]] · [encode](../datasets/encode.md) — Reference epigenome corpus for sequence-to-function pretraining.
- [[uk-biobank]] · [uk-biobank](../datasets/uk-biobank.md) — Multimodal human foundation model substrate (genetics + imaging + EHR).
- [[openneuro]] · [openneuro](../datasets/openneuro.md) — Aggregate neuroimaging pretraining corpus.
- [[gtex]] · [gtex](../datasets/gtex.md) — Multi-tissue bulk transcriptome reference.
```

- [ ] **Step 6: Verify and commit**

Run: `ls categories/`
Expected: All five files.

```bash
git add categories/
git commit -m "Add category files (neuro, aging, perturbation-imaging, single-cell, foundation-model-candidates)"
```

---

## Task 10: README quick-find table

**Files:**
- Modify: `README.md`

- [ ] **Step 1: Replace the `<!-- Populated in Task 10 -->` placeholder in `README.md`**

Find this exact line in `README.md`:

```
<!-- Populated in Task 10 of the scaffold plan. -->
```

Replace it with the table below. Sort rows alphabetically by dataset name.

```markdown
| Dataset | Modality | Focus | Access | Scale | Detail |
|---|---|---|---|---|---|
| Allen Brain Cell Atlas | scRNA-seq, MERFISH, snATAC | Whole-brain cell-type reference (human + mouse) | open | ~3 TB | [link](datasets/allen-brain-cell-atlas.md) |
| AMP-AD (ROSMAP, MSBB, Mayo) | Multi-omic + clinical | Alzheimer's disease cohorts | controlled | ~30 TB | [link](datasets/amp-ad.md) |
| ADNI | MRI, PET, CSF, clinical | Longitudinal AD biomarkers | controlled | ~5 TB | [link](datasets/adni.md) |
| CommonMind (CMC) | Bulk RNA-seq, ATAC, methylation, WGS | Schizophrenia, bipolar postmortem brain | controlled | ~3 TB | [link](datasets/commonmind.md) |
| ENCODE | ChIP, ATAC, DNase, RNA-seq, Hi-C | Regulatory genome reference | open | ~500 TB | [link](datasets/encode.md) |
| GTEx | Bulk RNA-seq, WGS | Multi-tissue transcriptome reference | registered/controlled | ~5 TB | [link](datasets/gtex.md) |
| Human Cell Atlas (HCA) | scRNA-seq, spatial | Cross-tissue single-cell reference | open | ~15 TB | [link](datasets/hca.md) |
| JUMP Cell Painting | Cell Painting | Compound + CRISPR + ORF perturbation imaging | open | ~115 TB | [link](datasets/jump-cell-painting.md) |
| Neuropainting | Cell Painting | iPSC-neuron genetic perturbation imaging | open | ~2 TB | [link](datasets/neuropainting.md) |
| OpenNeuro | MRI, fMRI, EEG, MEG, iEEG | Aggregator of BIDS neuroimaging studies | open | ~200 TB | [link](datasets/openneuro.md) |
| psychENCODE (PEC) | Multi-omic | Psychiatric disease brain consortium | controlled | ~50 TB | [link](datasets/psychencode.md) |
| RxRx1 | Cell Painting | siRNA-perturbation benchmark | open | ~50 GB | [link](datasets/rxrx1.md) |
| SEA-AD | snRNA-seq, MERFISH | AD-affected cortex single-cell atlas | open | ~500 GB | [link](datasets/sea-ad.md) |
| Tahoe-100M | scRNA-seq | 100M-cell compound perturbation atlas | open | ~500 GB | [link](datasets/tahoe-100m.md) |
| UK Biobank | Genetics, MRI, proteomics, EHR | 500k population cohort | controlled | ~2 PB | [link](datasets/uk-biobank.md) |
```

- [ ] **Step 2: Verify links resolve**

Run:
```bash
for f in datasets/allen-brain-cell-atlas.md datasets/amp-ad.md datasets/adni.md datasets/commonmind.md datasets/encode.md datasets/gtex.md datasets/hca.md datasets/jump-cell-painting.md datasets/neuropainting.md datasets/openneuro.md datasets/psychencode.md datasets/rxrx1.md datasets/sea-ad.md datasets/tahoe-100m.md datasets/uk-biobank.md; do
  test -f "$f" || echo "MISSING: $f"
done
```
Expected: no `MISSING:` output.

- [ ] **Step 3: Commit**

```bash
git add README.md
git commit -m "Populate README quick-find table with 15 seed datasets"
```

---

## Final verification

- [ ] **Step 1: Tree check**

Run: `find . -type f -not -path './.git/*' | sort`

Expected output (order doesn't matter, but every line must appear):
```
./.gitignore
./CONTRIBUTING.md
./README.md
./categories/aging.md
./categories/foundation-model-candidates.md
./categories/neuro.md
./categories/perturbation-imaging.md
./categories/single-cell.md
./datasets/adni.md
./datasets/allen-brain-cell-atlas.md
./datasets/amp-ad.md
./datasets/commonmind.md
./datasets/encode.md
./datasets/gtex.md
./datasets/hca.md
./datasets/jump-cell-painting.md
./datasets/neuropainting.md
./datasets/openneuro.md
./datasets/psychencode.md
./datasets/rxrx1.md
./datasets/sea-ad.md
./datasets/tahoe-100m.md
./datasets/uk-biobank.md
./docs/superpowers/plans/2026-05-14-datasets-index-scaffold.md
./docs/superpowers/specs/2026-05-14-datasets-index-design.md
./templates/dataset-template.md
```

- [ ] **Step 2: Frontmatter validity spot-check**

Run on three randomly chosen dataset files:
```bash
for f in datasets/psychencode.md datasets/rxrx1.md datasets/uk-biobank.md; do
  echo "=== $f ==="
  awk '/^---$/{c++; if(c==2) exit} {print}' "$f"
done
```
Expected: each file's frontmatter prints cleanly, starts with `---`, has the closing `---` reached, and lists every required field from the template.

- [ ] **Step 3: Git log review**

Run: `git log --oneline`
Expected: ~10 commits, one per task plus the initial spec commit. Each commit message describes a coherent unit of work.

---

## Out-of-scope (do NOT do in this plan)

- No `scripts/build_readme.py`. Wait until hand-maintenance is actually painful.
- No frontmatter linter.
- No dataset profiles beyond the 15 in the seed list.
- No deep literature digging beyond the 1-2 anchor citations per dataset listed above.
- No `download.sh` or other access automation. This is an index.

If during execution you discover a fact that contradicts the frontmatter values in this plan (e.g., a more accurate `n_subjects`), update the file rather than asking — these values are best-effort and meant to be revised. Note such corrections in the commit message.
