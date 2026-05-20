---
title: "Birdformer"
collection: portfolio
permalink: /portfolio/birdformer/
excerpt: "From-scratch PyTorch transformer encoder for bird-vs-reptile passage classification, with a hand-built multi-head attention mechanism, MLM variant, and PCA/t-SNE embedding visualization. [GitHub repository](https://github.com/joncking/birdformer/tree/main)."
date: 2026-05-20
---

[View the repository](https://github.com/joncking/birdformer/tree/main)

Birdformer is a small transformer learning project built around Louis Figuier's
public-domain Project Gutenberg text, *Reptiles and Birds*. The goal is not to
ship a competitive language model; it is to build the moving parts of a
transformer encoder by hand in PyTorch and use that stack for a concrete
bird-vs-reptile passage classification task.

The model code spells out token embeddings, positional embeddings, a
multi-head self-attention mechanism, feed-forward blocks, residual connections,
layer normalization, classifier and masked-language-modeling heads, and the
training loops. The classifier uses a `[cls]` token representation to predict
whether a text chunk came from the bird or reptile sections of the source book,
while the MLM variant keeps the same encoder mechanics available for masked
token prediction experiments.

## Embedding View

After training, the project extracts learned `[cls]` embeddings from the
encoder and projects them into two dimensions with PCA and t-SNE. The plot
below shows the PCA view of the resulting representation space.

![PCA projection of Birdformer classifier embeddings for bird and reptile text chunks.](/images/portfolio/birdformer-embeddings-pca.png)

`Author's note: this PCA projection is also how I feel thinking about birds and reptiles`

The repo also includes an interactive marimo embedding explorer for inspecting
clusters and nearby passages, plus scripts for cleaning the source text,
building the vocabulary, training the classifier, training the MLM demo, and
regenerating the embedding plots.
