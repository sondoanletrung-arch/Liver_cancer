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
pip install -r requirements.txt ```

## 📊 Data Availability & Execution Guide
The raw scRNA-seq data from 31 HCC and 12 iCCA samples utilized in this study are publicly available in the Gene Expression Omnibus (GEO) under the accession number GSE151530.

To run the pipeline:

# 1. Download the matrix, barcodes, features and metadata files from GEO.

# 2. Place them into the ./data/GSE151530/ directory.

# 3. Execute the notebooks sequentially from 01 to 06. The pipeline will automatically generate the processed .h5ad objects, CSV tables, and all manuscript figures in the ./results/ directory.

## 🙏 Acknowledgments
We extend our deepest gratitude to the developers of the open-source systems biology tools that made this analysis possible. A special thanks goes to the authors of the comprehensive **[Cell-Cell Communication Protocols (ccc-protocols)](https://ccc-protocols.readthedocs.io/en/latest/index.html)**, from which the foundation of our Tensor-cell2cell computational pipeline was adapted. 

Specifically, we acknowledge:
* **Tensor-cell2cell** (Armingol et al. 2022) for the powerful 4D communication tensor factorization framework.
* **LIANA** (Dimitrov et al. 2022) for providing a robust consensus platform for ligand-receptor inference.
* We also thank **Ma et al. (2021)** for the **GSE151530** dataset.
