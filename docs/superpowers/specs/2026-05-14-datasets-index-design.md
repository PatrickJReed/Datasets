# Datasets Index — Design Spec

**Date:** 2026-05-14
**Owner:** Patrick Reed
**Status:** Approved, ready for implementation planning

## Purpose

A curated, evergreen index of public datasets relevant to training AI models, with a bias toward **human, neurological, and aging biology**. Each dataset gets a structured profile so that future queries — by Patrick or by an agent acting on his behalf — can quickly answer: *does this dataset fit the model I want to train?*

This is an **index, not a mirror**. It tracks where datasets live, how to access them, what they contain, and what they might be useful for. It does not host data, download data, or wrap APIs.

## Scope

**In scope:**
- Public or controlled-access (DUA-gated) datasets that a single researcher or small team could plausibly train on.
- Human, neuro, and aging biology as the primary focus, with adjacent methodological-transfer datasets (e.g., perturbation imaging in non-neural cells) included when they're useful pretraining substrates.
- Modalities: bulk and single-cell transcriptomics, epigenomics, proteomics, GWAS/WGS, cellular imaging (cell painting), medical imaging (MRI/fMRI/EEG), clinical/phenotypic.

**Out of scope (YAGNI):**
- Auto-scrapers, API wrappers, download scripts.
- Notebooks of usage examples.
- A database backend. Markdown + git is the database.
- Mirroring or republishing data.

## Repository Structure

```
Datasets/
├── README.md                    # Master index: intro, quick-find table, category links
├── CONTRIBUTING.md              # Schema definition + how to add a dataset
├── datasets/                    # One file per dataset (the source of truth)
│   ├── neuropainting.md
│   ├── rxrx1.md
│   ├── jump-cell-painting.md
│   ├── tahoe-100m.md
│   ├── psychencode.md
│   ├── encode.md
│   ├── commonmind.md
│   ├── amp-ad-rosmap.md
│   └── …
├── categories/                  # Curated lenses over the same datasets
│   ├── neuro.md
│   ├── aging.md
│   ├── perturbation-imaging.md
│   ├── single-cell.md
│   └── foundation-model-candidates.md
├── templates/
│   └── dataset-template.md      # The canonical schema
└── docs/superpowers/specs/      # Design specs and plans
```

### Why this shape

A hybrid markdown approach (YAML frontmatter + markdown body) gives us:
- **Human-readable** — open any file and you can read it.
- **Git-diffable** — every change is reviewable.
- **Agent-parseable** — frontmatter is structured YAML; an LLM or script can filter, group, and rank datasets without bespoke parsing.

Alternatives considered:
- *Pure README*: balloons quickly, hard to search.
- *YAML/JSON database + tooling*: enforces schema but adds friction every time you want to jot something down.
- *Markdown + frontmatter*: best of both. README can be hand-maintained at first; auto-generation can be added later if friction warrants it.

## Per-Dataset Schema

Every `datasets/<slug>.md` file begins with YAML frontmatter and contains a fixed set of body sections. The frontmatter is the **filterable** layer; the body is the **narrative** layer.

### Frontmatter fields

```yaml
---
name: psychENCODE
aliases: [PEC]
host: Synapse / PsychENCODE Knowledge Portal
url: https://psychencode.synapse.org
access: controlled  # one of: open | registered | controlled
modalities: [bulk-rna-seq, scRNA-seq, atac-seq, chip-seq, methylation, wgs, genotype]
species: human
tissue: [prefrontal-cortex, multiple-brain-regions]
conditions: [schizophrenia, bipolar, autism, control]
n_subjects: ~2700
n_samples: ~15000
age_range: fetal-to-adult
scale_gb: ~50000           # rough order-of-magnitude in GB
license: PsychENCODE DUA
year: 2015-ongoing
tags: [neuro, psychiatric, multi-omic, developmental]
ai_relevance: [foundation-model, regulatory-genomics, disease-classification, multimodal]
compute_hint: gpu-multi    # one of: cpu | gpu-single | gpu-multi | cluster
benchmark_splits: false    # do canonical train/val/test splits exist?
last_reviewed: 2026-05-14
---
```

Field notes:
- `access` distinguishes truly open data from registration-only and from controlled (DUA / IRB) access.
- `scale_gb` is a rough order of magnitude, not a precise figure — useful for "can I train on this on my hardware?"
- `compute_hint` answers the same question from the training side.
- `benchmark_splits` flags datasets that come with canonical evaluation splits (e.g., RxRx1) vs. those that need them defined.
- `last_reviewed` lets us spot stale entries during periodic scans.

### Body sections (in order)

1. **Summary** — 2-4 sentences. What is this dataset, who made it, what makes it distinctive.
2. **Features** — what's actually in the data: assays, dimensions, sample counts, metadata, known caveats.
3. **Potential AI use cases** — 3-6 bullets. Concrete model types or tasks this dataset could support (foundation model pretraining, supervised classification, multimodal alignment, contrastive learning, generative modeling, etc.).
4. **Access notes** — how to actually get the data: portal account, DUA process, expected wait time, gotchas.
5. **Notable papers** — 1-5 references that anchor the dataset in the literature.
6. **Related** — cross-links to other dataset files using `[[wiki-style]]` references.

## README Layout

The root `README.md` is the entry point. Structure:

1. **Intro** — one paragraph: what this repo is, what it isn't, who it's for.
2. **Quick-find table** — a single markdown table listing every dataset with columns: name, modality, focus, access, scale, link to the detail file. Sortable in any editor, renderable on GitHub.
3. **By category** — links into `categories/neuro.md`, `categories/aging.md`, etc.
4. **How to add a dataset** — link to `CONTRIBUTING.md`.
5. **Status legend** — defines the meaning of `access`, `compute_hint`, and any status markers used in the table.

The README is **hand-maintained in v1**. If maintenance friction grows real, a `scripts/build_readme.py` that regenerates the table from frontmatter can be added later.

## Categories

Files in `categories/` are curated lenses, not data. Each category file:
- Names the lens (e.g., "Neuro").
- Briefly states what qualifies a dataset for inclusion.
- Lists relevant datasets as `[[wiki-links]]` with a one-line hook per entry.

Initial categories:
- `neuro.md` — anything brain-tissue or neuropsychiatric.
- `aging.md` — anything with age-range coverage relevant to aging biology (AD cohorts, longitudinal studies, age-stratified atlases).
- `perturbation-imaging.md` — cell-painting and morphological-profiling datasets.
- `single-cell.md` — scRNA-seq, snRNA-seq, multiome.
- `foundation-model-candidates.md` — datasets large/diverse enough to pretrain on.

A dataset can appear in multiple categories. The frontmatter `tags` field is authoritative; category files are curated by hand for now.

## Seed Datasets (v1 population)

The first commit ships dataset profiles for these 15 entries — the seven Patrick named plus eight high-value neighbors that round out the human/neuro/aging coverage:

**Patrick's named set:**
1. Neuropainting
2. RxRx1 (with cross-links to RxRx2, RxRx3, RxRx19)
3. Tahoe-100M
4. AMP-AD (umbrella: ROSMAP, MSBB, Mayo)
5. psychENCODE
6. ENCODE
7. CommonMind (CMC)

**High-value neighbors:**
8. JUMP Cell Painting Consortium
9. GTEx (brain-region slice highlighted)
10. Allen Brain Cell Atlas
11. SEA-AD (Seattle Alzheimer's Disease Brain Cell Atlas)
12. ADNI
13. UK Biobank (aging-relevant subset emphasized)
14. OpenNeuro
15. Human Cell Atlas (HCA)

For each, the v1 commit includes a complete `datasets/<slug>.md` with filled-in frontmatter and at least the Summary, Features, and Potential AI use cases body sections. Access notes and notable papers can be filled in opportunistically.

## Dataset Identification Process (ongoing)

This is how new datasets get added over time. Not automated — a checklist for manual scans.

### Sources to scan periodically

- **Aggregator portals:** Synapse (AD Knowledge Portal, PEC, CMC), dbGaP, NIH NDA, NIMH Data Archive, OpenNeuro, EBI/EGA, GEO, ArrayExpress, CZ CELLxGENE, HCA Data Portal.
- **Atlases / consortia:** Allen Brain Map, BICCN, SEA-AD, Human Protein Atlas, Tabula Sapiens, GTEx.
- **Aging / clinical cohorts:** UK Biobank, All of Us, FinnGen, ADNI, ROSMAP/MSBB/Mayo, ABCD, HCP.
- **Industrial / perturbation:** Recursion (RxRx series), JUMP-CP, Tahoe, Arc Virtual Cell Atlas, Pertpy benchmark suites.
- **Regulatory genomics:** ENCODE, ROADMAP Epigenomics, FANTOM5, ENCODE-EpiMap.

### Inclusion criteria

A dataset earns a profile if it meets all three:
1. **Accessible** — publicly available, even if DUA-gated.
2. **Trainable** — plausibly usable for model training by a single researcher or small team (not "you need a national lab").
3. **Relevant** — human / neuro / aging fit, OR strong methodological-transfer value to those domains.

### When to scan

No fixed cadence in v1. Add datasets opportunistically as they surface. Once the index proves useful, a quarterly review of the sources above is a reasonable rhythm.

## Implementation Phasing

**Phase 1 — Scaffold (this spec's implementation plan):**
- `git init` (already done).
- Write `README.md`, `CONTRIBUTING.md`, `templates/dataset-template.md`.
- Write `datasets/<slug>.md` for the 15 seed entries.
- Write `categories/neuro.md`, `categories/aging.md`, `categories/perturbation-imaging.md`, `categories/single-cell.md`, `categories/foundation-model-candidates.md`.
- Hand-build the README quick-find table from the seed entries.
- Initial commit.

**Phase 2 — Organic growth (not part of this spec):**
- Add datasets opportunistically.
- Update `last_reviewed` when entries are re-checked.

**Phase 3 — Tooling (only if earned):**
- `scripts/build_readme.py` to regenerate the quick-find table from frontmatter.
- A frontmatter linter.
- Trigger: when hand-maintenance becomes a meaningful chore (likely past ~30 entries).

## Open questions

None outstanding. Schema, seed list, and structure approved.

## Success criteria

- A new dataset can be added in under 10 minutes by copying the template.
- Given a model-training question ("what scRNA-seq aging data exists?"), the answer can be found in the index in under 60 seconds.
- An agent given access to the repo can answer filter-style questions (e.g., "list all open-access human brain multi-omic datasets with >1000 subjects") by parsing frontmatter alone.
