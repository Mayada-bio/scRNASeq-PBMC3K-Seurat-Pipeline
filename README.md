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
📊 Key Results & Visualizations
Annotated UMAP Clustering: Successful resolution of 9 discrete immune cell populations (Naive CD4+ T, Memory CD4+ T, CD14+ Monocytes, CD8+ T, B Cells, FCGR3A+ Monocytes, NK Cells, Dendritic Cells, and Platelets).

Quality Control Standard Operations: Elimination of dead/dying cells and doublets via strict mitochondrial read (percent.mt) and transcript density metrics (nFeature_RNA & nCount_RNA).

Biomarker Profile Analysis: Expression validation across cell types visualized via FeaturePlot projections, DotPlot expression intensity, and DoHeatmap top marker profiling.
📂 Repository Structure
.
├── Layer2B_SingleCell_RNASeq_Seurat_Pipeline.ipynb   # Main Jupyter/Colab Executable Notebook
├── pbmc3k_cluster_marker_genes.csv                   # Exported Differential Expression Marker Genes
└── README.md                                          # Documentation & Executive Summary
💻 Dependencies & Environment Setup
Language: R (v4.x)

Key R Packages: Seurat (v5), ggplot2, dplyr, patchwork

Execution Platform: Google Colab / Linux x86_64

👤 Author & Contact
Mayada Mohammed Elfadil, M.Sc.

Bioinformatician & Medical Laboratory Specialist

📍 Riyadh, Saudi Arabia

🔗 GitHub Profile
