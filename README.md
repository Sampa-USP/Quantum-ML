# Quantum Machine Learning — Image Classification via Quantum k-NN

This repository explores **image classification** using the **Quantum k-Nearest Neighbors (QkNN)** algorithm.  
The foundation is the scheme proposed by Dang *et al.* (2018), which combines:  
1) classical feature extraction,  
2) quantum state preparation to parallelize similarity calculation,  
3) **quantum minimum search** (Dürr–Høyer) to locate the k nearest neighbors,  
4) decision through measurement.  

> Main reference  
> **Image Classification Based on Quantum KNN Algorithm** — Yijie Dang, Nan Jiang, Hao Hu, Zhuoxiao Ji, Wenyin Zhang (2018).  
> arXiv: [1805.06260](https://arxiv.org/abs/1805.06260)  •  DOI (Springer): [10.1007/s11128-018-2004-9](https://link.springer.com/article/10.1007/s11128-018-2004-9)

---

## Objetivos

- Reproduzir (em simuladores) o *pipeline* QkNN para *datasets* clássicos de visão.
- Comparar **complexidade** e **acurácia** vs. k-NN clássico.
- Investigar variantes de métrica (Hamming, Euclidiana, Mahalanobis) e impacto no circuito.

## Repository Structure

- **notebooks/**
  - `01_features_caltech101.ipynb` — feature extraction from Caltech-101 dataset
  - `02_qknn_pipeline.ipynb` — full quantum k-NN pipeline (state preparation, similarity, minimum search, classification)
  - `03_classical_baselines.ipynb` — classical k-NN with different distance metrics
  - `99_utils_demo.ipynb` — demo and utilities

- **qml/**
  - `features.py` — classical feature extraction (color histograms, texture, etc.)
  - `qstates.py` — quantum state preparation from feature vectors
  - `distances.py` — quantum distance/similarity estimation
  - `minsearch.py` — Dürr–Høyer quantum minimum search implementation
  - `runner.py` — orchestration of the QkNN pipeline

- **scripts/**
  - `build_site.py` — static site builder (converts notebooks to HTML for GitHub Pages)
  - `download_data.py` — dataset downloader and pre-processor

- **reports/**
  - evaluation results, accuracy metrics, and plots

- `requirements.txt` — list of dependencies  
- `README.md` — project overview and references  
