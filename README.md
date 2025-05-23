Autoencoder and Classification Pipeline for scRNA‑seq Data

Overview

This project implements a two‑stage computational biology pipeline to analyze single‑cell RNA sequencing (scRNA‑seq) data:

Part 1: Autoencoder Embeddings – Train and evaluate a deep autoencoder to learn a low‑dimensional representation of normalized PBMC scRNA‑seq counts.

Part 2: Classification – Use the learned embeddings to train a classifier (e.g., random forest) for cell‑type prediction and assess performance.

The goal is to compare nonlinear autoencoder embeddings against traditional methods (PCA, t‑SNE) for clustering quality and to demonstrate how these embeddings can improve downstream classification accuracy.
