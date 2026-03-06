# Liver_cancer
# Deciphering Cell-Cell Communication in HCC and iCCA using Tensor Decomposition

[![Python 3.12](https://img.shields.io/badge/python-3.12.12-blue.svg)](https://www.python.org/)
[![Status](https://img.shields.io/badge/status-active-success.svg)]()
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This repository contains the complete computational pipeline, custom scripts, and Jupyter notebooks used for the manuscript: **"Decoding Cell-Cell Communication Patterns in Hepatocellular Carcinoma and Intrahepatic Cholangiocarcinoma"**.

## 📖 Overview
Hepatocellular carcinoma (HCC) and intrahepatic cholangiocarcinoma (iCCA) exhibit highly heterogeneous tumor microenvironments. In this study, we applied a systematic framework integrating **LIANA** (consensus ligand-receptor interactions) and **Tensor-cell2cell** (non-negative tensor factorization) on single-cell RNA sequencing (scRNA-seq) data. 

Our pipeline extracts multi-dimensional cell-cell communication (CCC) programs, stratifying them into conserved signaling axes and disease-polarized contexts. Downstream biological validations were conducted using **PROGENy** (pathway activity inference) and **GSEA** (Gene Set Enrichment Analysis).

## 🗂️ Analytical Pipeline & Repository Structure
The analysis is modularized into 6 sequential Jupyter Notebooks to ensure full reproducibility and transparency:

* **`01_Data_Preprocessing.ipynb`**: Data loading and clinical metadata mapping.
* **`02_Quality_Control_and_Integration.ipynb`**: Strict quality control, doublet removal (`Scrublet`), and batch-effect integration using `Harmony`.
* **`03_Cell_Cell_Communication_LIANA.ipynb`**: Inference of consensus ligand-receptor interactions across samples.
* **`04_Tensor_Factorization.ipynb`**: 4D communication tensor construction and auto-rank non-negative tensor factorization.
* **`05_Tensor_Downstream_Analysis.ipynb`**: Extraction of CCC networks, Sender-Receiver joint loadings, and Top LR-Cell pair clustermaps.
* **`06_Pathway_and_GSEA_Analysis.ipynb`**: Biological validation via PROGENy pathway inference and KEGG GSEA.

## 🚀 Installation & Reproducibility

We highly recommend using `conda` to create an isolated virtual environment before installing the dependencies to avoid conflicts.

```bash
# 1. Clone this repository
git clone https://github.com/sondoanletrung-arch/Liver_cancer.git
cd Liver_cancer

# 2. Create and activate a conda environment
conda create -n ccc_tensor_env python=3.12.12
conda activate ccc_tensor_env

# 3. Install required packages
pip install -r requirements.txt
