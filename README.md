# Assignment 5: Manifold Learning & Data Analysis   
**Course/Project**: DA25M002  
**Author**: Prabhat Pandey (DA25M002)  
**Date**: _(replace with submission date)_

---

##  Overview

This repository contains the implementation and evaluation of manifold learning techniques and dimensionality reduction on the *Yeast* dataset (in `.arff` format).  

The goal is to explore and visualize how high-dimensional data can be embedded in lower-dimensional spaces (2D/3D) while preserving important structure, and to analyze the effects these embeddings have on classification performance.

Key tasks include:

- Preprocessing the Yeast dataset (train & test splits in ARFF format)  
- Applying PCA, t-SNE, and Isomap  
- Visualizing the embeddings  
- Evaluating classification accuracy (e.g. via nearest neighbor or other classifiers)  
- Performing statistical / correlation analysis on features  
- Documenting observations and insights in the PDF

---

##  Repository Structure

assignment_5_major_prabhat_DA25M002-/
- assignment5_maj prabhat.ipynb # Jupyter notebook (main analysis)
-  assignment5_maj prabhat.pdf # Final report
-   east.arff # Yeast dataset (ARFF format)
-     east-train.arff # Training split
- yeast-test.arff # Test split
-  yeast.xml # Dataset metadata
-   requirements.txt # Required dependencies


---

##  Key Concepts

- **t-SNE (t-Distributed Stochastic Neighbor Embedding):** Focuses on preserving *local* structure of data  
- **Isomap:** Preserves *global* geometric relationships via geodesic distances  
- **PCA:** Used for baseline dimensionality reduction  
- **Veracity Analysis:** Detects noisy labels, outliers & ambiguous samples through manifold topology inspection  

---

##  Technical Highlights

- **Data Loading:** Yeast dataset parsed from `.arff` using `scipy.io.arff`  
- **Feature Scaling:** Standardized using `StandardScaler`  
- **Feature Analysis:** Skewness, kurtosis, correlation, and intrinsic dimensionality estimation  
- **Dimensionality Reduction:** Comprehensive hyperparameter tuning for t-SNE (perplexity, learning rate, init)  
- **Visualization:** Cluster-based scatter plots using `matplotlib`  
- **Data Veracity Inspection:**  
  - Centroid proximity for noisy labels  
  - k-NN distance-based outlier detection  
  - Neighborhood entropy for hard-to-learn samples  

---

##  Key Results

| Category | Samples | % of Total | Observation |
|-----------|----------|------------|--------------|
| Multi-label Genes | 2385 | 98.7% | Highly pleiotropic structure |
| Noisy / Ambiguous Samples | 824 | 34.1% | Overlapping functional roles |
| Outliers | 101 | 4.2% | Possible artifacts / rare states |
| Hard-to-Learn Samples | 84 | 3.5% | Boundary ambiguity in clusters |

**Optimal t-SNE Parameters:**  
`Perplexity = 5`, `Learning Rate = 200`, `Init = PCA`  
**Final KL Divergence:** `2.023`

---

##  Requirements

Install all dependencies with:
numpy
pandas
matplotlib
scikit-learn
scipy

 ## Visual Insights

t-SNE and Isomap visualizations reveal dense manifold structures with overlapping clusters of gene functions.
Multi-label regions appear highly entangled, confirming biological interdependence among functional categories.

(You can add PNG screenshots of your t-SNE / Isomap plots here)

## Observations & Insights

Gene expression data exhibits high manifold complexity

Non-linear methods (t-SNE, Isomap) outperform PCA in cluster separability

Noise and overlap are intrinsic to multi-functional gene data

Classifier performance is expected to degrade in regions of high neighborhood entropy

## Future Work

Incorporate UMAP for better scalability and local-global balance

Extend to interactive dashboards using Plotly or Bokeh

Combine manifold learning with explainable AI for interpretability

Explore biological correlations between cluster proximity and gene ontology

## Acknowledgement

This project was developed as part of DA5401 – Data Analysis and Visualization coursework under the M.Tech in AI & Data Science program at IIT Madras.

Author: Major Prabhat Pandey
Roll No: DA25M002
Institution: Indian Institute of Technology, Madras 🇮🇳

```bash
pip install -r requirements.txt
