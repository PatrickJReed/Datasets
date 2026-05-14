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
