#Single Cell RNA-seq Analysis

## Project Overview
Analysis of single-cell RNA sequencing data from peripheral blood mononuclear cells (PBMCs). PBMCs are white blood cells that include T cells, B cells, natural killer cells, and other immune system components. These cells change gene expression patterns during infection or vaccination, making them valuable for medical research.

## Data
Pre-processed scRNA-seq count matrix with cell type labels from original researchers. Data is already normalized and cleaned.

## Part 1: Dimensionality Reduction
Compare three methods for visualizing high-dimensional gene expression data:
- Autoencoder (implement neural network for latent space representation)
- t-SNE 
- PCA
## Part 2: Cell Type Classification
Build classifier to predict cell types for unlabeled cells. Methods discussed in lab include random forests and ensemble approaches.
