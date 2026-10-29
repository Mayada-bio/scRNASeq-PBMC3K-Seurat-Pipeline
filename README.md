# 🧬 Single-Cell RNA-Seq (scRNA-Seq) Processing & Immune Cell Annotation Pipeline

## 📌 Project Overview
This repository contains a robust, publication-grade Single-Cell RNA-Sequencing (scRNA-Seq) data analysis pipeline built with **Seurat v5** in **R**. The workflow processes the benchmark **10X Genomics PBMC 3K** dataset (~2,700 Peripheral Blood Mononuclear Cells) to perform cell quality control, dimensional reduction, unsupervised clustering, and biological annotation of primary immune subpopulations.

---

## 🛠️ Pipeline Architecture & Methodology

```text
[Raw 10X Matrix Ingestion] 
       │
       ▼
[Stringent Single-Cell Quality Control (QC)]
 ├── nFeature_RNA: 200 - 2,500
 └── percent.mt < 5%
       │
       ▼
[Log-Normalization & Feature Selection]
 └── Selection of Top 2,000 Highly Variable Genes (HVGs)
       │
       ▼
[Dimensional Reduction & Clustering]
 ├── Data Scaling & Principal Component Analysis (PCA)
 ├── SNN Graph Construction & Louvain Community Detection (Res = 0.5)
 └── Non-Linear UMAP Embedding Projection
       │
       ▼
[Cell Type Marker Identification & Biological Annotation]
 └── Canonical Biomarker Mapping (Wilcoxon Rank-Sum Test)
