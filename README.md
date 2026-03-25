# Single-cell RNA-seq Analysis of Kawasaki Disease (IVIG Treatment)

## Overview

This project analyzes single-cell RNA sequencing (scRNA-seq) data from Kawasaki disease patients to characterize immune cell populations and transcriptional changes before and after IVIG treatment, with comparison to healthy controls.

The objectives are:

* Identify major immune cell types present in peripheral blood
* Compare cell-type composition across conditions (before IVIG, after IVIG, healthy)
* Detect differentially expressed genes associated with treatment response
* Interpret biological signals relevant to inflammation and immune regulation

---

## Dataset

Publicly available scRNA-seq data comprising:

* Kawasaki disease patients (before IVIG)
* Kawasaki disease patients (after IVIG)
* Healthy controls

---

## Methods

### Preprocessing and Quality Control

* Load and merge individual sample matrices into a single AnnData object
* Filter low-quality cells and genes
* Compute QC metrics (number of genes, total counts, mitochondrial percentage)
* Normalize counts and log-transform data

### Feature Selection and Dimensionality Reduction

* Identify highly variable genes
* Perform PCA for dimensionality reduction

### Neighborhood Graph and Clustering

* Construct nearest-neighbor graph
* Cluster cells using the Leiden algorithm

### Visualization

* Compute UMAP embedding
* Visualize clusters and metadata (e.g., condition)

### Differential Expression (DE)

* Identify marker genes for each cluster using one-vs-rest testing
* Perform differential expression between conditions (before IVIG vs after IVIG)
* Rank genes by statistical significance and effect size
* Use marker genes to annotate cell types

---

## Results

### Cell-type Identification

Major immune cell populations identified:

* T cells
* B cells
* Plasma cells
* Monocytes
* NK cells
* Platelets
* RBC contamination

Cluster annotation was performed using canonical marker genes and ranked DE results.

### Cell-type Composition Across Conditions

* Differences in relative proportions of immune cell types across conditions were observed
* Monocyte and inflammatory populations are elevated before IVIG treatment
* Post-IVIG samples show reduced inflammatory cell signatures

### Differential Expression Findings

* Inflammatory genes (e.g., S100A8, S100A9, cytokine-associated genes) are enriched before treatment
* Reduced expression of inflammatory markers is observed after IVIG
* Cluster-specific marker genes highlight functional differences across immune subsets

---

## Project Structure

```
scrna-kawasaki-ivig/
│
├── data/              # Processed data files
├── notebooks/         # Analysis notebooks
├── results/           # Figures and plots
├── requirements.txt   # Dependencies
└── README.md
```

---

## Reproducibility

Install dependencies:

```
pip install -r requirements.txt
```

Run analysis:

```
jupyter notebook notebooks/
```

---

## Key Insights

* Monocytes show strong inflammatory activation in Kawasaki disease
* IVIG treatment reduces inflammatory gene expression and alters immune composition
* Distinct immune cell populations contribute differently to disease and treatment response

---

## Future Work

* Pathway and gene set enrichment analysis
* Cell–cell interaction analysis
* Integration with additional datasets

---

## Author

Shamitha K V

---

## License

MIT License
