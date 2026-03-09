# Overview

This repository contains the code used for the Master’s thesis experiments. The implementation is written in **R** and executed on **Azure Machine Learning (AzureML)**.

`master_thesis_AzureML.Rmd` is the **main script** containing the full experimental code. The R Markdown file is organized into several main sections.

## 1. Environment Setup

This section prepares the runtime environment and loads all required packages.

Key libraries include:

* `ggplot2` – visualization
* `dplyr`, `tidyr` – data manipulation
* `Rtsne` – t-SNE implementation
* `smacof`, `fmds` – multidimensional scaling
* `keras3` – loading the MNIST dataset
* `patchwork`, `gridExtra` – figure layout

## 2. Data Preparation

The **Iris dataset** is used as a small benchmark dataset for testing dimensionality reduction methods. As an initial step, Principal Component Analysis (PCA) is applied to the Iris data to obtain a preliminary low-dimensional visualization of the dataset.
The **MNIST dataset** is loaded using the `keras3` package.

## 3. Core Functions

* **P matrix** – Constructs the probability matrix representing pairwise similarities in the **high-dimensional space**. The similarities are computed using a **Gaussian distribution**, similar to the approach used in *t-SNE*, where high-dimensional distances are converted into probability-based similarities.

* **Q matrix** – Constructs the probability matrix representing pairwise similarities in the **low-dimensional embedding space**. As in *t-SNE*, pairwise distances in the low-dimensional representation are transformed into probabilities.

* **NE-based MDS function** – Performs dimensionality reduction using a **Neighborhood Embedding based multidimensional scaling approach**. 

* **SKLAN-based MDS function** – Performs dimensionality reduction using a **SKLAN-based multidimensional scaling method**.

* **Assessment function** – Evaluates the performance of dimensionality reduction methods using multiple **evaluation metrics**. These metrics measure how well the low-dimensional embeddings preserve structural properties of the original high-dimensional data.


## 4. Exploratory Plots

This section contains a collection of plots used to illustrate and analyze the detailed behavior of different dimensionality reduction methods discussed in the thesis.

The visualizations include:

* **t-SNE transformation plots**, which demonstrate how the data transforms during the embedding process.
* Plots showing the influence of **Z and perplexity in NE-based MDS**, illustrating how these parameters affect the resulting low-dimensional embedding.
* **Gradient descent heatmaps** for different dimensionality reduction methods, which visualize the optimization landscape and help analyze convergence behavior.


## 5. Visualization
This section shows the 2D visualizations of the embeddings produced by different dimensionality reduction methods.

## 6. Assessment
This section evaluates the performance of different dimensionality reduction methods using several evaluation metrics.
The methods are assessed on both the Iris dataset and the MNIST dataset.
