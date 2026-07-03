Single-Cell RNA-seq Analysis (PBMC 3k)

A single-cell RNA-seq analysis pipeline built with Scanpy, using the public PBMC 3k dataset (3,000 peripheral blood mononuclear cells).

Workflow


Environment setup – install/import Scanpy, Pandas
Data loading – sc.datasets.pbmc3k()
Quality control – flag mitochondrial genes, compute QC metrics (total counts, gene counts, % mito)
Filtering – remove low-quality cells (min 200 genes, <2500 genes, <5% mito) and rare genes (<3 cells)
Normalization – total-count normalization (target sum 1e4) + log1p transform
Highly variable genes (HVGs) – select informative genes for downstream analysis
Dimensionality reduction – scaling + PCA
Neighborhood graph & UMAP – 2D embedding of cell-cell similarity
Clustering – Leiden algorithm to identify distinct cell populations, visualized on UMAP


Requirements

bashpip install scanpy leidenalg pandas

Usage

Open and run Single_cell_RNAseq_analysis.ipynb sequentially (Google Colab or local Jupyter). No external data download needed — the dataset is fetched automatically via Scanpy.

Output

A UMAP embedding of PBMCs colored by Leiden cluster assignment, representing distinct immune cell subpopulations (e.g., T cells, B cells, monocytes, NK cells).

Tools

scanpy · leidenalg · pandas · PCA · UMAP · Leiden clustering
