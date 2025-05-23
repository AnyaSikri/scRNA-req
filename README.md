Autoencoder and Classification Pipeline for scRNA‑seq Data

Overview

This repository contains a two-part computational biology project analyzing single-cell RNA sequencing (scRNA‑seq) data from peripheral blood mononuclear cells (PBMCs). The pipeline demonstrates how nonlinear embedding methods (autoencoders) can capture complex biological patterns and improve downstream cell-type classification.

Part 1: Autoencoder Embeddings

Objective: Learn a compact latent representation of high-dimensional scRNA‑seq count data that preserves meaningful cell-type distinctions.

Approach:

Data Loading & Preprocessing: Imported raw count matrices from data/raw/, applied normalization (e.g., log-transform, scaling), and split into training/validation sets, saving processed data to data/processed/.

Model Definition: Implemented a symmetrical deep autoencoder in src/autoencoder.py, with configurable latent dimension, optional batch normalization, and L1 regularization.

Training Loop: Trained the autoencoder over multiple epochs with early stopping based on validation reconstruction loss, using PyTorch. Monitored training and validation losses to prevent overfitting.

Embedding Extraction: Once trained, extracted the encoder’s bottleneck (latent codes) for all cells and saved these embeddings to results/.

Visualization & Comparison: Plotted 2D projections of the latent space alongside PCA and t‑SNE embeddings, generating publication‑quality figures in results/figures/ to compare cluster separation.

Part 2: Classification

Objective: Evaluate whether autoencoder-derived embeddings improve cell-type prediction compared to standard dimensionality-reduction methods.

Approach:

Embedding Import: Loaded latent embeddings from Part 1 or recomputed them on-the-fly in Part2_Classification.ipynb.

Classifier Pipeline: Implemented a scikit‑learn workflow in src/classifier.py to train a random forest classifier on embeddings, with cell-type labels as targets.

Hyperparameter Optimization: Used Bayesian optimization to tune forest parameters (e.g., number of trees, max depth, min samples leaf), and performed 5‑fold cross-validation to select the best model.

Evaluation: Assessed classifier performance on a held‑out test set, reporting overall accuracy, confusion matrix, and feature importances. Compared results against classifiers trained on PCA or t‑SNE embeddings.
